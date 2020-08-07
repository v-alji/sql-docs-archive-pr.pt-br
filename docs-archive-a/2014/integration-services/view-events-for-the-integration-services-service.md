---
title: Exibir eventos para o serviço de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- events [Integration Services]
- service [Integration Services], events
- Integration Services service, events
ms.assetid: 37e23946-10d1-4116-8568-8fd24067102e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a513c8fc917da2987f3619c8eb9011e1170f7dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582001"
---
# <a name="view-events-for-the-integration-services-service"></a><span data-ttu-id="2abd2-102">Exibir eventos para o serviço do Integration Services</span><span class="sxs-lookup"><span data-stu-id="2abd2-102">View Events for the Integration Services Service</span></span>
  <span data-ttu-id="2abd2-103">Há duas ferramentas nas quais você pode exibir eventos do serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="2abd2-103">There are two tools in which you can view events for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service:</span></span>  
  
-   <span data-ttu-id="2abd2-104">A caixa de diálogo **Visualizador do Arquivo de Log** em [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2abd2-104">The **Log File Viewer** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2abd2-105">A caixa de diálogo **Visualizador do Arquivo de Log** inclui opções para exportar, filtrar e pesquisar o log.</span><span class="sxs-lookup"><span data-stu-id="2abd2-105">The **Log File Viewer** dialog box includes options to export, filter, and search the log.</span></span> <span data-ttu-id="2abd2-106">Para obter mais informações sobre as opções do **Visualizador do Arquivo de Log**, consulte [Ajuda F1 do Visualizador do Arquivo de Log](../relational-databases/logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="2abd2-106">For more information about the options in the **Log File Viewer**, see [Log File Viewer F1 Help](../relational-databases/logs/log-file-viewer-f1-help.md).</span></span>  
  
-   <span data-ttu-id="2abd2-107">O Visualizador de Eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="2abd2-107">The Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="2abd2-108">Para obter descrições dos eventos registrados pelo serviço [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , consulte [Eventos registrados pelo serviço Integration Services](service/events-logged-by-the-integration-services-service.md).</span><span class="sxs-lookup"><span data-stu-id="2abd2-108">For descriptions of the events logged by the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, see [Events Logged by the Integration Services Service](service/events-logged-by-the-integration-services-service.md).</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-sql-server-management-studio"></a><span data-ttu-id="2abd2-109">Para exibir eventos do serviço para Integration Services no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2abd2-109">To view service events for Integration Services in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="2abd2-110">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2abd2-110">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="2abd2-111">No menu **Arquivo** , clique em **Conectar Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-111">On the **File** menu, click **Connect Object Explorer**.</span></span>  
  
3.  <span data-ttu-id="2abd2-112">Na caixa de diálogo **Conectar ao Servidor** , selecione o tipo de servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , selecione ou localize o servidor com o qual se conectará e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-112">In the **Connect to Server** dialog box, select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server type, select or locate the server to connect to, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="2abd2-113">No Pesquisador de Objetos, clique com o botão direito do mouse em [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e clique em **Exibir Logs**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-113">In Object Explorer, right-click [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and click **View Logs**.</span></span>  
  
5.  <span data-ttu-id="2abd2-114">Para exibir eventos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , selecione **SQL Server Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-114">To view [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] events, select **SQL Server Integration Services**.</span></span> <span data-ttu-id="2abd2-115">A opção **Eventos NT** é automaticamente marcada e desmarcada com a opção **SQL Server Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="2abd2-115">The **NT Events** option is automatically selected and cleared with the **SQL Server Integration Services** option.</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-windows-event-viewer"></a><span data-ttu-id="2abd2-116">Para exibir eventos de serviço para Integration Services em Visualizador de Eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="2abd2-116">To view service events for Integration Services in Windows Event Viewer</span></span>  
  
1.  <span data-ttu-id="2abd2-117">No **Painel de Controle**, se você estiver usando o Modo de exibição Clássico, clique em **Ferramentas Administrativas**ou, se estiver usando o Modo exibição de Categoria, clique em **Desempenho e Manutenção** e em **Ferramentas Administrativas**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-117">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="2abd2-118">Clique em **Visualizador de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-118">Click **Event Viewer**.</span></span>  
  
3.  <span data-ttu-id="2abd2-119">Na caixa de diálogo **Visualizador de Eventos** , clique em **Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-119">In the **Event Viewer** dialog box, click **Application**.</span></span>  
  
4.  <span data-ttu-id="2abd2-120">No snap-in **Aplicativo** , localize uma entrada na coluna **Fonte** que tem o valor **SQLISService**, clique com o botão direito do mouse na entrada e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-120">In the **Application** snap-in, locate an entry in the **Source** column that has the value **SQLISService**, right-click the entry, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="2abd2-121">Opcionalmente, clique na seta para cima ou para baixo para exibir o próximo evento ou o anterior.</span><span class="sxs-lookup"><span data-stu-id="2abd2-121">Optionally, click the up or down arrow to show the previous or next event.</span></span>  
  
6.  <span data-ttu-id="2abd2-122">Opcionalmente, clique no ícone Copiar para Área de Transferência para copiar as informações do evento.</span><span class="sxs-lookup"><span data-stu-id="2abd2-122">Optionally, click the Copy to Clipboard icon to copy the event information.</span></span>  
  
7.  <span data-ttu-id="2abd2-123">Escolha exibir dados de evento que usam bytes ou palavras.</span><span class="sxs-lookup"><span data-stu-id="2abd2-123">Choose to display event data using bytes or words.</span></span>  
  
8.  <span data-ttu-id="2abd2-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2abd2-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="2abd2-125">No menu **Arquivo** , clique em **Sair** para fechar a caixa de diálogo **Visualizador de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="2abd2-125">On the **File** menu, click **Exit** to close the **Event Viewer** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2abd2-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2abd2-126">See Also</span></span>  
 <span data-ttu-id="2abd2-127">[Gerenciar o serviço de Integration Services](../../2014/integration-services/manage-the-integration-services-service.md) </span><span class="sxs-lookup"><span data-stu-id="2abd2-127">[Manage the Integration Services Service](../../2014/integration-services/manage-the-integration-services-service.md) </span></span>  
 [<span data-ttu-id="2abd2-128">Adicionar um log para contadores de desempenho de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="2abd2-128">Add a Log for Data Flow Performance Counters</span></span>](performance/performance-counters.md)  
  
  
