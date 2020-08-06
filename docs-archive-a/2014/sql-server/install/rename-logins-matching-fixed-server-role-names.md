---
title: Renomear logons que correspondem a nomes de função de servidor fixa | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- user-defined login names [SQL Server]
- fixed server roles [SQL Server]
- renamed logins [SQL Server]
- logins [SQL Server], names
ms.assetid: 10a1d77c-3153-474f-a6a0-969556794467
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 296ae4d4051e79e3c5d3bc158ef3e87c9164ecd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683316"
---
# <a name="rename-logins-matching-fixed-server-role-names"></a><span data-ttu-id="9dbbb-102">Renomear logons que coincidem com nomes de funções fixas do servidor</span><span class="sxs-lookup"><span data-stu-id="9dbbb-102">Rename logins matching fixed server role names</span></span>
  <span data-ttu-id="9dbbb-103">O Supervisor de Atualização detectou um ou mais nomes de logon definidos pelo usuário que coincidem com nomes de funções fixas do servidor.</span><span class="sxs-lookup"><span data-stu-id="9dbbb-103">Upgrade Advisor detected one or more user-defined login names that match the names of fixed server roles.</span></span> <span data-ttu-id="9dbbb-104">Os nomes de funções de servidor fixas são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="9dbbb-104">Fixed server role names are reserved.</span></span> <span data-ttu-id="9dbbb-105">Renomeie o logon antes de atualizar.</span><span class="sxs-lookup"><span data-stu-id="9dbbb-105">Rename the login before you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9dbbb-106">Componente</span><span class="sxs-lookup"><span data-stu-id="9dbbb-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9dbbb-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="9dbbb-107">Description</span></span>  
 <span data-ttu-id="9dbbb-108">Os seguintes nomes de funções de servidor fixas são exclusivos e não podem ser usados como nomes de logon definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9dbbb-108">The following fixed server role names are reserved and cannot be used as user-defined login names.</span></span>  
  
-   <span data-ttu-id="9dbbb-109">**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="9dbbb-109">**sysadmin**</span></span>  
  
-   <span data-ttu-id="9dbbb-110">**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="9dbbb-110">**serveradmin**</span></span>  
  
-   <span data-ttu-id="9dbbb-111">**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="9dbbb-111">**setupadmin**</span></span>  
  
-   <span data-ttu-id="9dbbb-112">**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="9dbbb-112">**securityadmin**</span></span>  
  
-   <span data-ttu-id="9dbbb-113">**processadmin**</span><span class="sxs-lookup"><span data-stu-id="9dbbb-113">**processadmin**</span></span>  
  
-   <span data-ttu-id="9dbbb-114">**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="9dbbb-114">**dbcreator**</span></span>  
  
-   <span data-ttu-id="9dbbb-115">**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="9dbbb-115">**diskadmin**</span></span>  
  
-   <span data-ttu-id="9dbbb-116">**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="9dbbb-116">**bulkadmin**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9dbbb-117">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="9dbbb-117">Corrective Action</span></span>  
 <span data-ttu-id="9dbbb-118">Antes de atualizar, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9dbbb-118">Before upgrading, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="9dbbb-119">Execute esta instrução para registrar os SIDs (identificadores de segurança) dos logons:</span><span class="sxs-lookup"><span data-stu-id="9dbbb-119">Record the security identifiers (SIDs) of the logins by executing the following statement.</span></span>  
  
    ```  
    SELECT name, sid   
    FROM master.dbo.syslogins   
    WHERE name IN('sysadmin', 'serveradmin','setupadmin', 'securityadmin','processadmin', 'dbcreator','diskadmin','bulkadmin')  
    ```  
  
2.  <span data-ttu-id="9dbbb-120">Descarte os logons.</span><span class="sxs-lookup"><span data-stu-id="9dbbb-120">Drop the logins.</span></span>  
  
3.  <span data-ttu-id="9dbbb-121">Use o procedimento do sistema **sp_addlogin** para criar novos logons.</span><span class="sxs-lookup"><span data-stu-id="9dbbb-121">Use the **sp_addlogin** system procedure to create new logins.</span></span> <span data-ttu-id="9dbbb-122">Especifique o SID retornado na etapa 1 no parâmetro \*\* \@ Sid\*\* para cada logon correspondente.</span><span class="sxs-lookup"><span data-stu-id="9dbbb-122">Specify the SID returned in step 1 in the **\@sid** parameter for each corresponding login.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbbb-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9dbbb-123">See Also</span></span>  
 <span data-ttu-id="9dbbb-124">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="9dbbb-124">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="9dbbb-125">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="9dbbb-125">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
