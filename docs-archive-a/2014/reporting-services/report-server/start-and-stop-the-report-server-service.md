---
title: Iniciar e parar o serviço do Servidor de Relatório | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- stopping Report Server service
- Report Server Windows service, starting
- Report Server service, starting
- starting Report Server service
ms.assetid: 6ec69ac3-27b0-472d-91e1-733af9078ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b751fd1a31830ffdc96cb296fa39d08e396c8c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573632"
---
# <a name="start-and-stop-the-report-server-service"></a><span data-ttu-id="452be-102">Iniciar e parar o serviço Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="452be-102">Start and Stop the Report Server Service</span></span>
  <span data-ttu-id="452be-103">O servidor de relatório é implementado como um serviço do Windows que contém o serviço Web do servidor de relatório, o Gerenciador de Relatórios e um aplicativo executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="452be-103">A report server is implemented as a Windows service that contains the Report Server Web service, Report Manager, and a background processing application.</span></span> <span data-ttu-id="452be-104">O serviço deve ser executado se você desejar usar alguma funcionalidade do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="452be-104">The service must be running if you want to use any report server functionality.</span></span> <span data-ttu-id="452be-105">Parar o serviço para todas as operações do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="452be-105">Stopping the service stops all report server operations.</span></span>  
  
 <span data-ttu-id="452be-106">Enquanto o serviço está parado, as solicitações para o relatório agendado e o processamento de assinaturas que teria ocorrido caso o serviço fosse executado são adicionados à fila.</span><span class="sxs-lookup"><span data-stu-id="452be-106">While the service is stopped, requests for scheduled report and subscription processing that would have occurred had the service been running are added to the queue.</span></span> <span data-ttu-id="452be-107">Isso ocorre porque os trabalhos que são executados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent criam os eventos.</span><span class="sxs-lookup"><span data-stu-id="452be-107">This is because jobs that are run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent create the events.</span></span> <span data-ttu-id="452be-108">Se desejar evitar operações pendentes enquanto o serviço está desabilitado, pare o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent também.</span><span class="sxs-lookup"><span data-stu-id="452be-108">If you want to avoid a backlog of operations while the service is off, consider stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent as well.</span></span>  
  
 <span data-ttu-id="452be-109">Você pode usar uma variedade de ferramentas para iniciar ou parar o serviço de Servidor de Relatório, incluindo a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager e a ferramenta Serviços fornecida no [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="452be-109">You can use a variety of tools to start or stop the Report Server service, including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, and the Services tool provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span></span>  
  
 <span data-ttu-id="452be-110">Se estiver fazendo mais do que iniciar ou parar o serviço, como alterar a conta de serviço, use a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="452be-110">If you are doing more than starting or stopping the service, such as changing the service account, you must use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="452be-111">O uso de outras ferramentas para alterar a conta de serviço pode romper a instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="452be-111">Using other tools to change the service account can break your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="452be-112">Para obter mais informações, veja [Configurar a conta de serviço do servidor de relatório &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="452be-112">For more information, see [Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="452be-113">Você não pode pausar e retomar o serviço.</span><span class="sxs-lookup"><span data-stu-id="452be-113">You cannot pause and resume the service.</span></span> <span data-ttu-id="452be-114">Não há nenhum parâmetro de início.</span><span class="sxs-lookup"><span data-stu-id="452be-114">There are no start parameters.</span></span> <span data-ttu-id="452be-115">Embora não haja nenhuma dependência explícita, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deverá estar em execução se você der suporte a assinaturas ou operações de relatório agendadas no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="452be-115">Although there are no explicit dependencies, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running if you support any subscriptions or scheduled report operations on the report server.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-the-reporting-services-configuration-tool"></a><span data-ttu-id="452be-116">Para iniciar ou parar o serviço usando a ferramenta Configuração do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="452be-116">To start or stop the service using the Reporting Services Configuration tool</span></span>  
  
1.  <span data-ttu-id="452be-117">Inicie a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e conecte-se ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="452be-117">Start [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and connect to the report server.</span></span>  
  
2.  <span data-ttu-id="452be-118">Na página Status do Servidor de Relatórios, clique em **Parar** ou **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="452be-118">On the Report Server Status page, click **Stop** or **Start**.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-services-in-administrative-tools"></a><span data-ttu-id="452be-119">Para iniciar ou parar o serviço usando Serviços em Ferramentas Administrativas</span><span class="sxs-lookup"><span data-stu-id="452be-119">To start or stop the service using Services in Administrative Tools</span></span>  
  
-   <span data-ttu-id="452be-120">Em Ferramentas Administrativas, abra Serviços, clique com o botão direito do mouse em **SQL Server Reporting Services (MSSQLSERVER)** e clique em **Parar** ou **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="452be-120">In Administrative Tools, open Services, right-click **SQL Server Reporting Services (MSSQLSERVER)**, and click **Stop** or **Restart**.</span></span>  
  
 <span data-ttu-id="452be-121">Se estiver executando várias instâncias ou se o servidor de relatório for executado como uma instância nomeada, verifique se o nome da instância entre parênteses corresponde à instância do servidor de relatório que deseja parar ou reiniciar.</span><span class="sxs-lookup"><span data-stu-id="452be-121">If you are running multiple instance or if the report server is running as a named instance, verify that the instance name in parentheses corresponds to the report server instance you want to stop or restart.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-sql-server-configuration-manager"></a><span data-ttu-id="452be-122">Para iniciar ou parar o serviço usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="452be-122">To start or stop the service using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="452be-123">Inicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="452be-123">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
2.  <span data-ttu-id="452be-124">Selecione SQL Server Services, clique com o botão direito do mouse em **SQL Server Reporting Services**e clique em **Parar** ou **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="452be-124">Select SQL Server Services, right-click **SQL Server Reporting Services**, and click **Stop** or **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452be-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="452be-125">See Also</span></span>  
 [<span data-ttu-id="452be-126">Reporting Services Configuration Manager &#40;Modo Nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="452be-126">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
