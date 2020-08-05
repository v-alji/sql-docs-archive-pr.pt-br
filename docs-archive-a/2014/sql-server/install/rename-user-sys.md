---
title: Renomear usuário sys | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sys user names [SQL Server]
ms.assetid: d622d646-83e4-4b6f-9a21-77b301af04b5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3af9d31a54adc5645cab6fcc7104ae7ff27a61b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569043"
---
# <a name="rename-user-sys"></a><span data-ttu-id="955ec-102">Renomear usuário sys</span><span class="sxs-lookup"><span data-stu-id="955ec-102">Rename user sys</span></span>
  <span data-ttu-id="955ec-103">O Supervisor de Atualização detectou o nome de usuário **sys** em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="955ec-103">Upgrade Advisor detected the user name **sys** in a database.</span></span> <span data-ttu-id="955ec-104">Esse nome é reservado.</span><span class="sxs-lookup"><span data-stu-id="955ec-104">This name is reserved.</span></span> <span data-ttu-id="955ec-105">Renomeie o usuário antes de atualizar.</span><span class="sxs-lookup"><span data-stu-id="955ec-105">Rename the user before you upgrade.</span></span> <span data-ttu-id="955ec-106">Se isso não for feito, o banco de dados ficará em estado suspeito após o processo de atualização e não estará disponível até que banco de dados fique online novamente.</span><span class="sxs-lookup"><span data-stu-id="955ec-106">If the user is not renamed, the database will be in a suspect state after the upgrade process and will be unavailable until the database is brought online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="955ec-107">Componente</span><span class="sxs-lookup"><span data-stu-id="955ec-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="955ec-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="955ec-108">Description</span></span>  
 <span data-ttu-id="955ec-109">O usuário **sys** é reservado.</span><span class="sxs-lookup"><span data-stu-id="955ec-109">User **sys** is reserved.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="955ec-110">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="955ec-110">Corrective Action</span></span>  
  
### <a name="before-upgrade-procedure"></a><span data-ttu-id="955ec-111">Antes do procedimento de atualização</span><span class="sxs-lookup"><span data-stu-id="955ec-111">Before Upgrade Procedure</span></span>  
 <span data-ttu-id="955ec-112">Antes da atualização, faça o seguinte em cada banco de dados que contém o usuário **sys**:</span><span class="sxs-lookup"><span data-stu-id="955ec-112">Before you upgrade, in each database that contains user **sys**, do the following:</span></span>  
  
1.  <span data-ttu-id="955ec-113">Crie um usuário novo.</span><span class="sxs-lookup"><span data-stu-id="955ec-113">Create a new user.</span></span>  
  
2.  <span data-ttu-id="955ec-114">Use as instruções a seguir para exibir todas as permissões que são concedidas pelo usuário **sys** e ao usuário **sys**.</span><span class="sxs-lookup"><span data-stu-id="955ec-114">Use the following statements to display all permissions that are granted by user **sys** and granted to user **sys**.</span></span>  
  
    ```  
    -- Return permissions granted by user sys.  
    SELECT * FROM sysprotects WHERE grantor = USER_ID('sys')  
    -- Return permissions granted to user sys.  
    SELECT * FROM sysprotects WHERE uid = USER_ID('sys')  
    ```  
  
3.  <span data-ttu-id="955ec-115">Para transferir a propriedade de todos os objetos do **sys** para o novo usuário, use **sp_changeobjectowner**.</span><span class="sxs-lookup"><span data-stu-id="955ec-115">To transfer ownership of all objects owned by **sys** to the new user, use **sp_changeobjectowner**.</span></span>  
  
4.  <span data-ttu-id="955ec-116">Descarte o usuário **sys**.</span><span class="sxs-lookup"><span data-stu-id="955ec-116">Drop user **sys**.</span></span>  
  
5.  <span data-ttu-id="955ec-117">Para restaurar as permissões originais capturadas na etapa 2, use a cláusula AS *new_user* da instrução GRANT.</span><span class="sxs-lookup"><span data-stu-id="955ec-117">To restore the original permissions captured in step 2, use the AS *new_user* clause of the GRANT statement.</span></span>  
  
6.  <span data-ttu-id="955ec-118">Modifique os scripts para referenciarem o novo usuário.</span><span class="sxs-lookup"><span data-stu-id="955ec-118">Modify scripts to reference the new user.</span></span> <span data-ttu-id="955ec-119">Por exemplo, os scripts que contêm instruções como `SELECT * FROM sys.my`_`table` devem ser alterados para `SELECT * FROM new_user.my_table`.</span><span class="sxs-lookup"><span data-stu-id="955ec-119">For example, scripts that contain statements such as `SELECT * FROM sys.my`_`table` must be changed to `SELECT * FROM new_user.my_table`.</span></span>  
  
### <a name="after-upgrade-procedure"></a><span data-ttu-id="955ec-120">Depois do procedimento de atualização</span><span class="sxs-lookup"><span data-stu-id="955ec-120">After Upgrade Procedure</span></span>  
 <span data-ttu-id="955ec-121">Se o usuário **sys** não foi renomeado antes da atualização, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="955ec-121">If the user **sys** was not renamed prior to upgrading, do the following:</span></span>  
  
1.  <span data-ttu-id="955ec-122">Execute a instrução `ALTER DATABASE db_name SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="955ec-122">Execute the statement `ALTER DATABASE db_name SET ONLINE`.</span></span> <span data-ttu-id="955ec-123">O banco de dados estará no modo SINGLE_USER.</span><span class="sxs-lookup"><span data-stu-id="955ec-123">The database will be in SINGLE_USER mode.</span></span>  
  
2.  <span data-ttu-id="955ec-124">Siga todas as etapas da seção Antes do procedimento de atualização.</span><span class="sxs-lookup"><span data-stu-id="955ec-124">Follow all steps in the Before Upgrade Procedure section.</span></span>  
  
3.  <span data-ttu-id="955ec-125">Execute a instrução `ALTER DATABASE db_name SET MULTI_USER`.</span><span class="sxs-lookup"><span data-stu-id="955ec-125">Execute the statement `ALTER DATABASE db_name SET MULTI_USER`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="955ec-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="955ec-126">See Also</span></span>  
 <span data-ttu-id="955ec-127">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="955ec-127">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="955ec-128">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="955ec-128">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
