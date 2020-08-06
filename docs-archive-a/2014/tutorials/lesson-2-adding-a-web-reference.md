---
title: 'Lição 2: adicionando uma referência Web | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2c2b8b8-6b13-45ca-ab3b-1582447b6807
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 02ca614cb042211ac468246c3003efaa5f2e8fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681308"
---
# <a name="lesson-2-adding-a-web-reference"></a><span data-ttu-id="cfc73-102">Lição 2: Adicionando uma referência da Web</span><span class="sxs-lookup"><span data-stu-id="cfc73-102">Lesson 2: Adding a Web Reference</span></span>
  <span data-ttu-id="cfc73-103">Descoberta de serviço Web é o processo pelo qual um cliente localiza um serviço Web e obtém a descrição desse serviço.</span><span class="sxs-lookup"><span data-stu-id="cfc73-103">Web service discovery is the process by which a client locates a Web service and obtains its service description.</span></span> <span data-ttu-id="cfc73-104">O processo de descoberta de serviço Web no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] envolve questionar um site que segue um algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cfc73-104">The process of Web service discovery in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] involves interrogating a Web site following a predetermined algorithm.</span></span> <span data-ttu-id="cfc73-105">O objetivo do processo é localizar a descrição do serviço, que é um documento XML que usa linguagem WSDL.</span><span class="sxs-lookup"><span data-stu-id="cfc73-105">The goal of the process is to locate the service description, which is an XML document that uses the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="cfc73-106">A descrição do serviço descreve quais serviços estão disponíveis e como interagir com eles.</span><span class="sxs-lookup"><span data-stu-id="cfc73-106">The service description describes what services are available and how to interact with those services.</span></span> <span data-ttu-id="cfc73-107">Sem uma descrição de serviço, é impossível interagir programaticamente com um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="cfc73-107">Without a service description, it is impossible to programmatically interact with a Web service.</span></span>  
  
 <span data-ttu-id="cfc73-108">Seu aplicativo deve ter meios para se comunicar com o serviço Web e localizá-lo em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="cfc73-108">Your application must have a means to communicate with the Web service and to locate it at run time.</span></span> <span data-ttu-id="cfc73-109">A adição de uma referência da Web ao projeto para o serviço Web faz isso por meio da geração de uma classe proxy que executa a interface com o serviço Web e fornece uma representação local desse serviço.</span><span class="sxs-lookup"><span data-stu-id="cfc73-109">Adding a Web reference to your project for the Web service does this by generating a proxy class that interfaces with the Web service and provides a local representation of the Web service.</span></span> <span data-ttu-id="cfc73-110">Para obter mais informações, consulte "Como gerar um proxy de serviço Web XML" na documentação do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfc73-110">For more information, see "How to: Generate an XML Web Service Proxy" in your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] documentation.</span></span>  
  
### <a name="to-add-a-web-reference"></a><span data-ttu-id="cfc73-111">Para adicionar uma referência da Web</span><span class="sxs-lookup"><span data-stu-id="cfc73-111">To add a Web reference</span></span>  
  
1.  <span data-ttu-id="cfc73-112">No menu **projeto** , clique em **Adicionar referência de serviço**.</span><span class="sxs-lookup"><span data-stu-id="cfc73-112">On the **Project** menu, click **Add Service Reference**.</span></span>  
  
2.  <span data-ttu-id="cfc73-113">Na caixa de diálogo **Adicionar referência de serviço** , clique em **avançado**.</span><span class="sxs-lookup"><span data-stu-id="cfc73-113">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
3.  <span data-ttu-id="cfc73-114">Na caixa de diálogo **configurações de referência de serviço** , clique em **Adicionar referência Web**.</span><span class="sxs-lookup"><span data-stu-id="cfc73-114">In the **Service Reference Settings** dialog box, click **Add Web Reference**.</span></span>  
  
4.  <span data-ttu-id="cfc73-115">Na caixa **URL** da caixa de diálogo **Adicionar referência Web** , digite a URL para obter a descrição de serviço do serviço Web servidor de relatórios, como http://localhost/reportserver/reportservice2010.asmx .</span><span class="sxs-lookup"><span data-stu-id="cfc73-115">In the **URL** box of the **Add Web Reference** dialog box, type the URL to obtain the service description of the Report Server Web service, such as http://localhost/reportserver/reportservice2010.asmx.</span></span> <span data-ttu-id="cfc73-116">Em seguida, clique no botão **ir** para recuperar informações sobre o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="cfc73-116">Then click the **Go** button to retrieve information about the Web service.</span></span>  
  
     <span data-ttu-id="cfc73-117">\- ou –</span><span class="sxs-lookup"><span data-stu-id="cfc73-117">\- or -</span></span>  
  
     <span data-ttu-id="cfc73-118">Se o serviço Web servidor de relatórios existir no computador local, clique no link **Serviços Web no computador local** no painel navegador.</span><span class="sxs-lookup"><span data-stu-id="cfc73-118">If the Report Server Web service exists on the local machine, click the **Web services on the local machine** link in the browser pane.</span></span> <span data-ttu-id="cfc73-119">Em seguida, clique no link do serviço Web ReportService2010 na lista fornecida.</span><span class="sxs-lookup"><span data-stu-id="cfc73-119">Then click the link for the ReportService2010 Web service from the list provided.</span></span>  
  
5.  <span data-ttu-id="cfc73-120">Na caixa **nome da referência Web** , renomeie a referência Web para ReportService2010, que é o namespace que você usará para essa referência Web.</span><span class="sxs-lookup"><span data-stu-id="cfc73-120">In the **Web reference name** box, rename the Web reference to ReportService2010, which is the namespace you will use for this Web reference.</span></span>  
  
6.  <span data-ttu-id="cfc73-121">Clique em **Adicionar referência** para adicionar uma referência Web para o serviço Web de destino.</span><span class="sxs-lookup"><span data-stu-id="cfc73-121">Click **Add Reference** to add a Web reference for the target Web service.</span></span>  
  
     <span data-ttu-id="cfc73-122">O [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] baixa a descrição do serviço e gera uma classe proxy para executar a interface entre o aplicativo e o serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="cfc73-122">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] downloads the service description and generates a proxy class to interface between your application and the Report Server Web service.</span></span> <span data-ttu-id="cfc73-123">Você também precisará adicionar uma referência ao namespace <xref:System.Web.Services> para que a referência da Web funcione.</span><span class="sxs-lookup"><span data-stu-id="cfc73-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
7.  <span data-ttu-id="cfc73-124">No menu Projeto, clique em **Adicionar Referência**.</span><span class="sxs-lookup"><span data-stu-id="cfc73-124">On the Project menu, click **Add Reference**.</span></span>  
  
8.  <span data-ttu-id="cfc73-125">Na caixa de diálogo **Adicionar referência** , na guia **.net** , selecione **System. Web. Services**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfc73-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
 <span data-ttu-id="cfc73-126">Para obter mais informações, consulte [Acessando a API SOAP](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="cfc73-126">For more information, see [Accessing the SOAP API](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc73-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cfc73-127">See Also</span></span>  
 <span data-ttu-id="cfc73-128">[Serviço Web Servidor de Relatórios](../reporting-services/report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cfc73-128">[Report Server Web Service](../reporting-services/report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="cfc73-129">[Lição 3: acessando o serviço Web](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cfc73-129">[Lesson 3: Accessing the Web Service](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span></span>  
 [<span data-ttu-id="cfc73-130">Acessando o serviço Web servidor de relatórios usando Visual Basic ou o tutorial&#35; &#40;do SSRS do Visual C&#41;</span><span class="sxs-lookup"><span data-stu-id="cfc73-130">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
