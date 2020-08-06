---
title: Exibir pacotes de Integration Services no SQL Server Management Studio (serviço SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- viewing packages
- connections [Integration Services], packages
ms.assetid: 783e653c-0f1f-45ed-b3ef-5ba07b019f27
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4ba86320f1b1a685eab6e80399f3e8c21bd110eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678837"
---
# <a name="view-integration-services-packages-in-sql-server-management-studio-ssis-service"></a><span data-ttu-id="10200-102">Exibir pacotes do Integration Services no SQL Server Management Studio (serviço SSIS)</span><span class="sxs-lookup"><span data-stu-id="10200-102">View Integration Services Packages in SQL Server Management Studio (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="10200-103">Esse tópico discute o serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , um serviço do Windows para o gerenciamento de pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10200-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="10200-104">dá suporte ao serviço para compatibilidade de versões anteriores com versões anteriores do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10200-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="10200-105">A partir do [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], você pode gerenciar objetos como pacotes no servidor do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="10200-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="10200-106">Este procedimento descreve como se conectar ao [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] em [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e exibir uma lista dos pacotes gerenciados pelo serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10200-106">This procedure describes how to connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and view a list of the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
### <a name="to-connect-to-integration-services"></a><span data-ttu-id="10200-107">Para se conectar ao Integration Services</span><span class="sxs-lookup"><span data-stu-id="10200-107">To connect to Integration Services</span></span>  
  
1.  <span data-ttu-id="10200-108">Clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Microsoft SQL Server**e clique em **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="10200-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="10200-109">Na caixa de diálogo **Conectar ao Servidor** , selecione **Integration Services** na lista **Tipo de servidor** , forneça um nome de servidor na caixa **Nome do servidor** e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="10200-109">In the **Connect to Server** dialog box, select **Integration Services** in the **Server type** list, provide a server name in the **Server name** box, and then click **Connect**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="10200-110">Se você não consegue se conectar ao [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], provavelmente o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] não está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="10200-110">If you cannot connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is likely not running.</span></span> <span data-ttu-id="10200-111">Para saber o status do serviço, clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Microsoft SQL Server**, aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="10200-111">To learn the status of the service, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="10200-112">No painel esquerdo, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="10200-112">In the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="10200-113">No painel direito, localize o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10200-113">In the right pane, find the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="10200-114">Inicie o serviço se ainda não estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="10200-114">Start the service if it is not already running.</span></span>  
  
     [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="10200-115">é aberto.</span><span class="sxs-lookup"><span data-stu-id="10200-115">opens.</span></span> <span data-ttu-id="10200-116">Por padrão, a janela do Pesquisador de Objetos é aberta e posicionada no canto inferior esquerdo do estúdio.</span><span class="sxs-lookup"><span data-stu-id="10200-116">By default the Object Explorer window is open and positioned in the lower-left corner of the studio.</span></span> <span data-ttu-id="10200-117">Se o Pesquisador de Objetos não for aberto, clique em **Pesquisador de Objetos** no menu **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="10200-117">If Object Explorer is not open, click **Object Explorer** on the **View** menu.</span></span>  
  
### <a name="to-view-the-packages-that-integration-services-service-manages"></a><span data-ttu-id="10200-118">Para visualizar os pacotes gerenciados pelo serviço Integration Services</span><span class="sxs-lookup"><span data-stu-id="10200-118">To view the packages that Integration Services service manages</span></span>  
  
1.  <span data-ttu-id="10200-119">No Pesquisador de Objetos, expanda a pasta Pacotes Armazenados.</span><span class="sxs-lookup"><span data-stu-id="10200-119">In Object Explorer, expand the Stored Packages folder.</span></span>  
  
2.  <span data-ttu-id="10200-120">Expanda as subpastas Pacotes Armazenados para exibir os pacotes.</span><span class="sxs-lookup"><span data-stu-id="10200-120">Expand the Stored Packages subfolders to show packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10200-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10200-121">See Also</span></span>  
 <span data-ttu-id="10200-122">[Gerenciamento de Pacotes &#40;serviço SSIS&#41;](service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="10200-122">[Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="10200-123">Usar o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10200-123">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
