---
title: Usando a API SOAP em um aplicativo do Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- Windows applications [Reporting Services]
- Windows Forms [Reporting Services]
- SOAP [Reporting Services], Windows applications
ms.assetid: e4804792-20cd-4df2-9257-fb958ff447b4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 115ce02da69a8adb2c7a3de4175e528f281eb2b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568360"
---
# <a name="using-the-soap-api-in-a-windows-application"></a><span data-ttu-id="fef37-102">Usando a API SOAP em um aplicativo do Windows</span><span class="sxs-lookup"><span data-stu-id="fef37-102">Using the SOAP API in a Windows Application</span></span>
  <span data-ttu-id="fef37-103">Você pode acessar a funcionalidade completa do servidor de relatório por meio da API SOAP do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fef37-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="fef37-104">A API SOAP é um serviço Web e, sendo assim, pode ser acessada facilmente para fornecer os recursos de relatórios corporativos para seus aplicativos comerciais personalizados.</span><span class="sxs-lookup"><span data-stu-id="fef37-104">The SOAP API is a Web service and, as such, can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="fef37-105">Você pode acessar o serviço Web em um aplicativo do Windows simplesmente gravando o código que faz chamadas para o serviço.</span><span class="sxs-lookup"><span data-stu-id="fef37-105">You can access the Web service in a Windows application simply by writing code that makes calls to the service.</span></span> <span data-ttu-id="fef37-106">Usando o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , você pode gerar uma classe de proxy que expõe as propriedades e os métodos do serviço Web e permite que você use uma infraestrutura e ferramentas familiares para criar aplicativos de negócios baseados em [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tecnologia.</span><span class="sxs-lookup"><span data-stu-id="fef37-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Web service and enables you to use a familiar infrastructure and tools to build business applications built on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
## <a name="integrating-report-management-functionality-using-windows-forms"></a><span data-ttu-id="fef37-107">Integrando a funcionalidade de gerenciamento de relatórios com o Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fef37-107">Integrating Report Management Functionality Using Windows Forms</span></span>  
 <span data-ttu-id="fef37-108">Diferentemente do acesso de URL, a API SOAP expõe o conjunto completo de funções de gerenciamento disponíveis por meio do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="fef37-108">Unlike URL access, the SOAP API exposes the complete set of management functions that are available through the report server.</span></span> <span data-ttu-id="fef37-109">Isto significa que a funcionalidade administrativa inteira do Gerenciador de Relatórios está disponível para os desenvolvedores por meio de SOAP.</span><span class="sxs-lookup"><span data-stu-id="fef37-109">This means that the entire administrative functionality of Report Manager is available to developers through SOAP.</span></span> <span data-ttu-id="fef37-110">Dessa forma, você pode desenvolver um gerenciamento completo e a ferramenta de administração usando o Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fef37-110">As such, you can develop a complete management and administration tool using Windows Forms.</span></span> <span data-ttu-id="fef37-111">Por exemplo, no aplicativo do Windows, você pode habilitar os usuários para recuperar o conteúdo do namespace do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="fef37-111">For example, in your Windows application, you might want to enable your users to retrieve the contents of the report server namespace.</span></span> <span data-ttu-id="fef37-112">Para isso, você pode usar o método <xref:ReportService2010.ReportingService2010.ListChildren%2A> do serviço Web para listar todos os itens no banco de dados do servidor de relatório e, em seguida, usar um controle Listview, Treeview ou Combobox para exibir esses itens para os usuários.</span><span class="sxs-lookup"><span data-stu-id="fef37-112">To do this, you could use the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method to list all the items in the report server database and then use a Listview, Treeview, or Combobox control to display those items to your users.</span></span> <span data-ttu-id="fef37-113">O código de serviço Web a seguir pode ser usado para recuperar a lista atual de relatórios disponíveis em uma pasta Meus Relatórios do usuário quando o usuário clica em um botão do formulário:</span><span class="sxs-lookup"><span data-stu-id="fef37-113">The following Web service code might be used to retrieve the current list of available reports in a user's My Reports folder when a user clicks a button on a form:</span></span>  
  
```vb  
' Button click event that retrieves a list of reports from  
' the My Reports folder and displays them in a combo box  
Private Sub listReportsButton_Click(sender As Object, e As System.EventArgs)  
   ' Create a new Web service object and set credentials  
   ' to Windows Authentication  
   Dim rs As New ReportingService2010()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return the list of items in My Reports  
   Dim items As CatalogItem() = rs.ListChildren("/Adventureworks 2008 Sample Reports", False)  
  
   Dim ci As CatalogItem  
   For Each ci In  items  
      ' If the item is a report, add it to   
      ' a combo box  
      If ci.TypeName = "Report" Then  
         catalogComboBox.Items.Add(ci.Name)  
      End If  
   Next ci  
End Sub 'listReportsButton_Click  
```  
  
```csharp  
// Button click event that retrieves a list of reports from  
// the My Reports folder and displays them in a combo box  
private void listReportsButton_Click(object sender, System.EventArgs e)  
{  
   // Create a new Web service object and set credentials  
   // to Windows Authentication  
   ReportingService2010 rs = new ReportingService2010();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return the list of items in My Reports  
   CatalogItem[] items = rs.ListChildren("/Adventureworks 2008 Sample Reports", false);  
  
   foreach (CatalogItem ci in items)  
   {  
      // If the item is a report, add it to   
      // a combo box  
      if (ci.TypeName == "Report")  
         catalogComboBox.Items.Add(ci.Name);  
   }  
}  
```  
  
 <span data-ttu-id="fef37-114">A partir daí, você poderá habilitar os usuários para selecionar o relatório na caixa Combinação e visualizá-lo no formulário usando um controle do navegador da Web ou um controle de imagem.</span><span class="sxs-lookup"><span data-stu-id="fef37-114">From there, you might enable users to select the report from the Combo box and preview the report on the form either using a Web browser control or an image control.</span></span>  
  
## <a name="enabling-report-viewing-and-navigation-using-windows-forms"></a><span data-ttu-id="fef37-115">Habilitando a exibição e navegação do relatório por meio do Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fef37-115">Enabling Report Viewing and Navigation Using Windows Forms</span></span>  
 <span data-ttu-id="fef37-116">Há dois métodos disponíveis para integrar relatórios nos aplicativos do Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fef37-116">There are two methods available for integrating reports into your Windows Forms applications.</span></span>  
  
 <span data-ttu-id="fef37-117">Você pode usar a API SOAP para renderizar relatórios em qualquer um dos formatos de renderização suportados usando o método <xref:ReportExecution2005.ReportExecutionService.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="fef37-117">You can use the SOAP API to render reports to any of the supported rendering formats using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="fef37-118">Há pequenas desvantagens em habilitar a exibição e navegação de relatório por meio de SOAP:</span><span class="sxs-lookup"><span data-stu-id="fef37-118">There are slight disadvantages to enabling report viewing and navigation through SOAP:</span></span>  
  
-   <span data-ttu-id="fef37-119">Você não pode se beneficiar da funcionalidade interna da barra de ferramentas do relatório que é incluída com o Visualizador de HTML por meio do acesso de URL.</span><span class="sxs-lookup"><span data-stu-id="fef37-119">You cannot take advantage of the built-in functionality of the report toolbar that is included with the HTML Viewer through URL access.</span></span>  
  
-   <span data-ttu-id="fef37-120">Se você renderizar para HTML, deverá renderizar separadamente quaisquer imagem ou recursos como fluxos adicionais que usam o método <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="fef37-120">If you render to HTML, you must separately render any images or resources as additional streams using the <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A> method.</span></span>  
  
-   <span data-ttu-id="fef37-121">Há uma pequena vantagem de desempenho na renderização de relatórios com o acesso de URL em relação à API SOAP.</span><span class="sxs-lookup"><span data-stu-id="fef37-121">There is a slight performance advantage to rendering reports using URL access over using the SOAP API.</span></span>  
  
 <span data-ttu-id="fef37-122">Porém, o método <xref:ReportExecution2005.ReportExecutionService.Render%2A> da API SOAP pode ser usado para renderizar relatórios e salvá-los em vários formatos de saída programaticamente.</span><span class="sxs-lookup"><span data-stu-id="fef37-122">However, the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method of the SOAP API can be used to render reports and save them to various output formats programmatically.</span></span> <span data-ttu-id="fef37-123">Essa é uma vantagem em relação ao acesso de URL que requer interação de usuário.</span><span class="sxs-lookup"><span data-stu-id="fef37-123">This is an advantage over URL access, which requires user interaction.</span></span> <span data-ttu-id="fef37-124">Quando você renderizar um relatório que usa o método <xref:ReportExecution2005.ReportExecutionService.Render%2A> de SOAP API, será possível renderizar em qualquer um dos formatos de saída suportados.</span><span class="sxs-lookup"><span data-stu-id="fef37-124">When you render a report using the SOAP API <xref:ReportExecution2005.ReportExecutionService.Render%2A> method, you can render to any of the supported output formats.</span></span>  
  
 <span data-ttu-id="fef37-125">Você também pode usar os controles ReportViewer livremente distribuíveis que estão incluídos no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fef37-125">You can also use the freely distributable ReportViewer controls that are included with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span> <span data-ttu-id="fef37-126">Os controles ReportViewer facilitam a inserção da funcionalidade [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em aplicativos personalizados.</span><span class="sxs-lookup"><span data-stu-id="fef37-126">The ReportViewer controls make it easy to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] functionality into custom applications.</span></span> <span data-ttu-id="fef37-127">Os controles ReportViewer são destinados a desenvolvedores que desejam fornecer relatórios com design prévio, totalmente criados como parte de um conjunto de recursos do aplicativo (por exemplo, um aplicativo de gerenciamento de site da Web pode incluir relatórios que mostrem a análise de fluxo de acesso a sites da Web da empresa).</span><span class="sxs-lookup"><span data-stu-id="fef37-127">The ReportViewer controls are intended for developers who want to provide predesigned, fully authored reports as part of an application feature set (for example, a Web site management application might include reports that show click-stream analysis on company Web sites).</span></span> <span data-ttu-id="fef37-128">A inserção de controles em um aplicativo fornece uma alternativa otimizada para incluir os componentes de servidor do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em sua implantação de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fef37-128">Embedding the controls in an application provides a streamlined alternative to including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server components in your application deployment.</span></span> <span data-ttu-id="fef37-129">Os controles fornecem a funcionalidade de relatório, mas sem a criação de relatório adicional, publicação ou distribuição e suporte de entrega que você localiza no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fef37-129">The controls provide report functionality, but without the additional report authoring, publication, or distribution and delivery support that you find in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fef37-130">Há duas versões de controles ReportViewer, uma para aplicativos cliente sofisticados do Windows e um para aplicativos [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fef37-130">There are two versions of the ReportViewer controls, one for rich Windows client applications and one for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications.</span></span> <span data-ttu-id="fef37-131">Os controles dão suporte ao processamento local e aos modos de processamento remotos.</span><span class="sxs-lookup"><span data-stu-id="fef37-131">The controls support both local processing and remote processing modes.</span></span> <span data-ttu-id="fef37-132">No modo de processamento local, o aplicativo fornece a definição de relatório e conjuntos de dados, e dispara o processamento do relatório.</span><span class="sxs-lookup"><span data-stu-id="fef37-132">In local processing mode, your application provides the report definition and datasets and triggers report processing.</span></span> <span data-ttu-id="fef37-133">No modo de processamento remoto, a recuperação de dados e o processando de relatório ocorre no servidor de relatório e o controle é usado para exibição e navegação no relatório.</span><span class="sxs-lookup"><span data-stu-id="fef37-133">In remote processing mode, data retrieval and report processing happen on the report server and the control is used for display and report navigation.</span></span> <span data-ttu-id="fef37-134">Esse modelo permite que você crie aplicativos sofisticados que podem ser escalados da área de trabalho à empresa.</span><span class="sxs-lookup"><span data-stu-id="fef37-134">This model allows you to build rich applications that can be scaled from desktop to the enterprise.</span></span>  
  
 <span data-ttu-id="fef37-135">Os controles ReportViewer são documentados na Ajuda online do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fef37-135">ReportViewer controls are documented in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] online Help.</span></span> <span data-ttu-id="fef37-136">Para obter mais informações, consulte a documentação do produto do [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fef37-136">For more information, see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] product documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef37-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fef37-137">See Also</span></span>  
 <span data-ttu-id="fef37-138">[Criando aplicativos usando o serviço Web e o .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="fef37-138">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="fef37-139">[Integrando Reporting Services em aplicativos](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fef37-139">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="fef37-140">Usando a API SOAP em um aplicativo Web</span><span class="sxs-lookup"><span data-stu-id="fef37-140">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
  
  
