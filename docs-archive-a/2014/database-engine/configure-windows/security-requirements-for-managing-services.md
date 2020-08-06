---
title: Requisitos de segurança para gerenciar serviços | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent service, security
- services [SQL Server], security
- SQL Server services, security
- WMI Providers [SQL Server]
- server configuration [SQL Server]
- security [SQL Server], services
- services [SQL Server], WMI
ms.assetid: 1874a317-ddb2-425d-98d9-b53e1be6fc6a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 46a777858c01bf3057093d34b29b9a2093668e97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684337"
---
# <a name="security-requirements-for-managing-services"></a><span data-ttu-id="6c76c-102">Requisitos de segurança para gerenciar serviços</span><span class="sxs-lookup"><span data-stu-id="6c76c-102">Security Requirements for Managing Services</span></span>
  <span data-ttu-id="6c76c-103">Para gerenciar o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Services, use o SQL Server Configuration Manager ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c76c-103">To manage the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Services, use either SQL Server Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6c76c-104">Gerencie os serviços em servidores agrupados com o Administrador Clusterizado.</span><span class="sxs-lookup"><span data-stu-id="6c76c-104">Manage the services on clustered servers with the Cluster Administrator.</span></span>  
  
 <span data-ttu-id="6c76c-105">Para gerenciar o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e definir as opções de configuração de servidor, você deve ser um membro da função de servidor fixa **serveradmin** ou **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="6c76c-105">To manage the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service and set the server configuration options, you must be a member of the **serveradmin** fixed server role or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="6c76c-106">Membros do grupo **Administradores** do Windows podem iniciar e interromper serviços e configurar as opções de servidor que o Windows fornece.</span><span class="sxs-lookup"><span data-stu-id="6c76c-106">Members of the Windows **Administrators** group can start and stop services and configure the server options that Windows provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c76c-107">Para operar corretamente, as contas usadas para os serviços devem ser configuradas com o domínio, sistema de arquivo e permissões de registro corretos.</span><span class="sxs-lookup"><span data-stu-id="6c76c-107">To operate properly, the accounts used for the services must be configured with the correct domain, file system, and registry permissions.</span></span> <span data-ttu-id="6c76c-108">Para obter informações sobre as permissões necessárias, consulte [Configurar contas de serviço e permissões do Windows](configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6c76c-108">For information about the required permissions, see [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md).</span></span>  
  
## <a name="windows-management-instrumentation"></a><span data-ttu-id="6c76c-109">Instrumentação de Gerenciamento do Windows</span><span class="sxs-lookup"><span data-stu-id="6c76c-109">Windows Management Instrumentation</span></span>  
 <span data-ttu-id="6c76c-110">O SQL Server Configuration Manager e [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] usam Instrumentação de Gerenciamento do Windows (WMI) para exibir e modificar algumas das propriedades de servidor.</span><span class="sxs-lookup"><span data-stu-id="6c76c-110">SQL Server Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] use Windows Management Instrumentation (WMI) to display and modify some of the server properties.</span></span> <span data-ttu-id="6c76c-111">Para administrar serviços e obter o status dos serviços, o usuário deve ter direitos para acessar o objeto WMI.</span><span class="sxs-lookup"><span data-stu-id="6c76c-111">To manage services and obtain the status of the services, the user must have rights to access the WMI object.</span></span> <span data-ttu-id="6c76c-112">Em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as seguintes páginas de propriedades de servidor usam o WMI:</span><span class="sxs-lookup"><span data-stu-id="6c76c-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the following server property pages use WMI:</span></span>  
  
-   <span data-ttu-id="6c76c-113">Iniciar serviços automaticamente</span><span class="sxs-lookup"><span data-stu-id="6c76c-113">Autostart Services</span></span>  
  
-   <span data-ttu-id="6c76c-114">Parâmetros de inicialização</span><span class="sxs-lookup"><span data-stu-id="6c76c-114">Startup Parameters</span></span>  
  
-   <span data-ttu-id="6c76c-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="6c76c-115">Security</span></span>  
  
-   <span data-ttu-id="6c76c-116">Diversas configurações de servidor</span><span class="sxs-lookup"><span data-stu-id="6c76c-116">Misc Server Settings</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6c76c-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6c76c-117">Related Tasks</span></span>  
 [<span data-ttu-id="6c76c-118">Configurar o WMI para mostrar o status do servidor nas ferramentas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6c76c-118">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
## <a name="related-content"></a><span data-ttu-id="6c76c-119">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="6c76c-119">Related Content</span></span>  
 [<span data-ttu-id="6c76c-120">Provedor WMI para conceitos de gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="6c76c-120">WMI Provider for Configuration Management Concepts</span></span>](../../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
