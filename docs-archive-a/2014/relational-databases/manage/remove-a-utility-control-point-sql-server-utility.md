---
title: Remover um ponto de controle do utilitário (Utilitário do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c048a416-900e-4c77-8243-e0f0d8b94068
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fe4ebb9de3f7644b4cff5c7dbfb34e50be7e8993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583578"
---
# <a name="remove-a-utility-control-point-sql-server-utility"></a><span data-ttu-id="392fb-102">Remover um ponto de controle do utilitário (Utilitário do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="392fb-102">Remove a Utility Control Point (SQL Server Utility)</span></span>
  <span data-ttu-id="392fb-103">Este tópico descreve como remover um UCP (ponto de controle do utilitário) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="392fb-103">This topic describes how to remove a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utility control point (UCP) from the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="392fb-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="392fb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="392fb-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="392fb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="392fb-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="392fb-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="392fb-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="392fb-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="392fb-108">**Para remover um ponto de controle do utilitário, usando:**</span><span class="sxs-lookup"><span data-stu-id="392fb-108">**To remove a Utility Control Point, using:**</span></span>  
  
     [<span data-ttu-id="392fb-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="392fb-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="392fb-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="392fb-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="392fb-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="392fb-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="392fb-112">Antes de usar esse procedimento para remover o UCP do utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , observe os requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="392fb-112">Before you use this procedure to remove the UCP from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, note the following requirements.</span></span> <span data-ttu-id="392fb-113">O procedimento armazenado executará verificações de pré-requisito da operação.</span><span class="sxs-lookup"><span data-stu-id="392fb-113">The stored procedure will run prerequisite checks as part of the operation.</span></span>  
  
-   <span data-ttu-id="392fb-114">Para executar esse procedimento, todas as instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devem ser removidas do UCP.</span><span class="sxs-lookup"><span data-stu-id="392fb-114">Before you run this procedure, all managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed from the UCP.</span></span> <span data-ttu-id="392fb-115">Observe que o UCP é uma instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="392fb-115">Note that the UCP is a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="392fb-116">Para obter mais informações, veja [Remover uma instância do SQL Server do Utilitário do SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="392fb-116">From more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
-   <span data-ttu-id="392fb-117">Esse procedimento deve ser executado em um computador que seja um UCP.</span><span class="sxs-lookup"><span data-stu-id="392fb-117">This procedure must be run on a computer that is a UCP.</span></span>  
  
-   <span data-ttu-id="392fb-118">Se a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em que o UCP foi removido tiver um conjunto de coleta de dados que não seja do Utilitário, o banco de dados UMDW (sysutility_mdw) não será removido do procedimento.</span><span class="sxs-lookup"><span data-stu-id="392fb-118">If the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the UCP was removed has a non-Utility data collection set, the UMDW database (sysutility_mdw) will not be dropped by the procedure.</span></span> <span data-ttu-id="392fb-119">Nesse caso, o banco de dados UMDW (sysutility_mdw) deverá ser removido manualmente antes do UCP ser recriado.</span><span class="sxs-lookup"><span data-stu-id="392fb-119">If this is the case, the UMDW database (sysutility_mdw) must be dropped manually before the UCP can be created again.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="392fb-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="392fb-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="392fb-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="392fb-121">Permissions</span></span>  
 <span data-ttu-id="392fb-122">Esse procedimento deve ser executado por um usuário com permissões de `sysadmin`; as mesmas permissões necessárias para criar um UCP.</span><span class="sxs-lookup"><span data-stu-id="392fb-122">This procedure must be run by a user with `sysadmin` permissions; the same permissions required to create a UCP.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="392fb-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="392fb-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-utility-control-point"></a><span data-ttu-id="392fb-124">Para remover um ponto de controle do utilitário</span><span class="sxs-lookup"><span data-stu-id="392fb-124">To remove a Utility Control Point</span></span>  
  
1.  <span data-ttu-id="392fb-125">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="392fb-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="392fb-126">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="392fb-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="392fb-127">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="392fb-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```  
EXEC msdb.dbo.sp_sysutility_ucp_remove;  
```  
  
## <a name="see-also"></a><span data-ttu-id="392fb-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="392fb-128">See Also</span></span>  
 <span data-ttu-id="392fb-129">[Recursos e tarefas do Utilitário do SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="392fb-129">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="392fb-130">[Usar o Gerenciador do Utilitário para gerenciar o Utilitário do SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="392fb-130">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="392fb-131">Solucionar problemas do Utilitário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="392fb-131">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
