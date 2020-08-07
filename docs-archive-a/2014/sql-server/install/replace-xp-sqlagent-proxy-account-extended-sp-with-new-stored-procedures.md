---
title: Substituir o uso da xp_sqlagent_proxy_account procedimento armazenado estendido por novos procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- xp_sqlagent_proxy_account
ms.assetid: 0e3cc931-6237-41dd-bf0d-0c03f4d8fff2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d124ab73f4b4315550134f28ffad232b4a1c0ec2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576141"
---
# <a name="replace-usage-of-the-xp_sqlagent_proxy_account-extended-stored-procedure-with-new-stored-procedures"></a><span data-ttu-id="674cc-102">Substituir a utilização do procedimento armazenado estendido xp_sqlagent_proxy_account por novos procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="674cc-102">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>
  <span data-ttu-id="674cc-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent oferece suporte a vários proxies.</span><span class="sxs-lookup"><span data-stu-id="674cc-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent supports multiple proxies.</span></span> <span data-ttu-id="674cc-104">Você define esses proxies usando um novo conjunto de procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="674cc-104">You define these proxies by using a new set of stored procedures.</span></span> <span data-ttu-id="674cc-105">Para obter mais informações sobre os novos procedimentos armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consulte os seguintes tópicos dos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="674cc-105">For more information about the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   <span data-ttu-id="674cc-106">‘sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-107">‘sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-108">‘sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-109">‘sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-110">‘sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-111">‘sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-112">‘sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-113">‘sp_help_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-114">‘sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-115">‘sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="674cc-116">‘sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])’</span><span class="sxs-lookup"><span data-stu-id="674cc-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="674cc-117">Depois de atualizar para [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o, todas as instruções que usam o procedimento armazenado estendido **xp_sqlagent_proxy_account** não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="674cc-117">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], any statements that use the **xp_sqlagent_proxy_account** extended stored procedure will not work.</span></span> <span data-ttu-id="674cc-118">Use **sp_xp_cmdshell_proxy_account** em vez de **xp_sqlagent_proxy_account** para definir o proxy para **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="674cc-118">Use **sp_xp_cmdshell_proxy_account** instead of **xp_sqlagent_proxy_account** to set the proxy for **xp_cmdshell**.</span></span>  
  
## <a name="component"></a><span data-ttu-id="674cc-119">Componente</span><span class="sxs-lookup"><span data-stu-id="674cc-119">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="674cc-120">Agent</span><span class="sxs-lookup"><span data-stu-id="674cc-120">Agent</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="674cc-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="674cc-121">See Also</span></span>  
 [<span data-ttu-id="674cc-122">Problemas de atualização do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="674cc-122">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
