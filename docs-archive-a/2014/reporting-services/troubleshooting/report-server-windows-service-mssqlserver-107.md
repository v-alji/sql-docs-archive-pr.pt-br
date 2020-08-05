---
title: Serviço Windows do Servidor de Relatório (MSSQLServer) 107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- MSSQLServer 107 error
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8651f98b47b698fbe3cfb6a152b9220a84ed7256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572937"
---
# <a name="report-server-windows-service-mssqlserver-107"></a><span data-ttu-id="34c03-102">Serviço Servidor de Relatório do Windows (MSSQLServer) 107</span><span class="sxs-lookup"><span data-stu-id="34c03-102">Report Server Windows Service (MSSQLServer) 107</span></span>
    
## <a name="details"></a><span data-ttu-id="34c03-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="34c03-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34c03-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="34c03-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="34c03-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="34c03-105">Event ID</span></span>|<span data-ttu-id="34c03-106">107</span><span class="sxs-lookup"><span data-stu-id="34c03-106">107</span></span>|  
|<span data-ttu-id="34c03-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="34c03-107">Event Source</span></span>|<span data-ttu-id="34c03-108">Serviço Servidor de Relatório do Windows</span><span class="sxs-lookup"><span data-stu-id="34c03-108">Report Server Windows Service</span></span>|  
|<span data-ttu-id="34c03-109">Componente</span><span class="sxs-lookup"><span data-stu-id="34c03-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="34c03-110">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="34c03-110">Message Text</span></span>|<span data-ttu-id="34c03-111">O serviço Servidor de Relatório do Windows (MSSQLSERVER) não pode se conectar ao banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="34c03-111">Report Server Windows Service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="34c03-112">Explicação</span><span class="sxs-lookup"><span data-stu-id="34c03-112">Explanation</span></span>  
 <span data-ttu-id="34c03-113">O serviço Servidor de Relatório do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode se conectar ao banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="34c03-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service cannot connect to the report server database.</span></span> <span data-ttu-id="34c03-114">Esse erro ocorrerá durante a reinicialização do serviço se uma conexão com o banco de dados do servidor de relatório não puder ser estabelecida.</span><span class="sxs-lookup"><span data-stu-id="34c03-114">This error occurs during a service restart if a connection to the report server database cannot be established.</span></span> <span data-ttu-id="34c03-115">As condições em que esse erro ocorre incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="34c03-115">Conditions under which this error occurs include the following:</span></span>  
  
-   <span data-ttu-id="34c03-116">O serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] não está sendo executado quando o serviço Servidor de Relatório é iniciado.</span><span class="sxs-lookup"><span data-stu-id="34c03-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is not running when the Report Server service starts.</span></span>  
  
-   <span data-ttu-id="34c03-117">A conexão com o serviço [!INCLUDE[ssDE](../../includes/ssde-md.md)] falha porque as conexões remotas ou o protocolo TCP/IP não estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="34c03-117">The connection to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service fails because remote connections or the TCP/IP protocol is not enabled.</span></span>  
  
-   <span data-ttu-id="34c03-118">O banco de dados do servidor de relatório não está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="34c03-118">The report server database is not configured correctly.</span></span>  
  
-   <span data-ttu-id="34c03-119">A conta de serviço não está configurada corretamente ou a conta já não tem permissões no banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="34c03-119">The service account is not configured correctly, or the account no longer has permissions on the report server database.</span></span> <span data-ttu-id="34c03-120">Isso pode ocorrer se você não usar ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para configurar a conta ou o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="34c03-120">This can occur if you do not use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set up the account or the report server database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34c03-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="34c03-121">User Action</span></span>  
 <span data-ttu-id="34c03-122">Inicie o serviço [!INCLUDE[ssDE](../../includes/ssde-md.md)] , se ele não estiver em execução ainda, e certifique-se de que as conexões remotas estão habilitadas para o protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="34c03-122">Start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service if it is not running and check that remote connections are enabled for TCP/IP protocol.</span></span>  
  
 <span data-ttu-id="34c03-123">Use a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para configurar o banco de dados do servidor de relatório e a conta do serviço.</span><span class="sxs-lookup"><span data-stu-id="34c03-123">Use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to configure the report server database and service account.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="34c03-124">Somente interno</span><span class="sxs-lookup"><span data-stu-id="34c03-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c03-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34c03-125">See Also</span></span>  
 <span data-ttu-id="34c03-126">[Configurar a conta de serviço do servidor de relatório &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="34c03-126">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="34c03-127">[Reporting Services Configuration Manager &#40;Modo Nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="34c03-127">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 [<span data-ttu-id="34c03-128">Iniciar e parar o serviço Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="34c03-128">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
