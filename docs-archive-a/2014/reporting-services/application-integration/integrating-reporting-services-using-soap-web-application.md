---
title: Usando a API SOAP em um aplicativo Web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], Web applications
- impersonation [Reporting Services]
- user impersonation [Reporting Services]
- report servers [Reporting Services], SOAP
- Web applications [Reporting Services]
ms.assetid: e8ca4455-0dc3-4741-8872-3636114938ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e228f01915df633f50b23bf93e892446863c28ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679190"
---
# <a name="using-the-soap-api-in-a-web-application"></a><span data-ttu-id="190bd-102">Usando a API SOAP em um aplicativo Web</span><span class="sxs-lookup"><span data-stu-id="190bd-102">Using the SOAP API in a Web Application</span></span>
  <span data-ttu-id="190bd-103">Você pode acessar a funcionalidade completa do servidor de relatório por meio da API SOAP do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="190bd-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="190bd-104">Por ser um serviço Web, a API SOAP pode ser acessada facilmente para fornecer os recursos de relatórios corporativos para seus aplicativos comerciais personalizados.</span><span class="sxs-lookup"><span data-stu-id="190bd-104">Because it's a Web service, the SOAP API can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="190bd-105">Você acessa o serviço Web do servidor de relatório a partir de um aplicativo Web da mesma forma que acessa a API SOAP de um aplicativo do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="190bd-105">You access the Report Server Web service from a Web application in much the same way that you access the SOAP API from a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="190bd-106">Usando o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , você pode gerar uma classe proxy que expõe as propriedades e os métodos do serviço Web servidor de relatórios e permite que você use uma infraestrutura e ferramentas familiares para criar aplicativos de negócios em [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tecnologia.</span><span class="sxs-lookup"><span data-stu-id="190bd-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Report Server Web service and enables you to use a familiar infrastructure and tools to build business applications on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
 <span data-ttu-id="190bd-107">A funcionalidade de gerenciamento do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é acessada no aplicativo Web tão facilmente como em um aplicativo do Windows.</span><span class="sxs-lookup"><span data-stu-id="190bd-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report management functionality is just as easily accessed from a Web application as from a Windows application.</span></span> <span data-ttu-id="190bd-108">Em um aplicativo Web, você pode adicionar e remover itens do banco de dados do servidor de relatório, definir segurança de item, modificar itens do banco de dados do servidor de relatório, gerenciar programação e entrega e muito mais.</span><span class="sxs-lookup"><span data-stu-id="190bd-108">From a Web application, you can add and remove items from the report server database, set item security, modify report server database items, manage scheduling and delivery, and more.</span></span>  
  
## <a name="enabling-impersonation"></a><span data-ttu-id="190bd-109">Habilitando a representação</span><span class="sxs-lookup"><span data-stu-id="190bd-109">Enabling Impersonation</span></span>  
 <span data-ttu-id="190bd-110">A primeira etapa na configuração do aplicativo Web é habilitar a representação no cliente de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="190bd-110">The first step in configuring your Web application is to enable impersonation from the Web service client.</span></span> <span data-ttu-id="190bd-111">Com representação, os aplicativos do [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] podem ser executados com a identidade do cliente em nome dos quais estão sendo operados.</span><span class="sxs-lookup"><span data-stu-id="190bd-111">With impersonation, [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications can execute with the identity of the client on whose behalf they are operating.</span></span> <span data-ttu-id="190bd-112">O [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] conta com os Serviços de Informações da Internet (IIS) da [!INCLUDE[msCoName](../../includes/msconame-md.md)] para autenticar o usuário e passar um token autenticado para o aplicativo do [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] ou, se não for possível autenticar o usuário, passar um token não autenticado.</span><span class="sxs-lookup"><span data-stu-id="190bd-112">[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] relies on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) to authenticate the user and either pass an authenticated token to the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application or, if unable to authenticate the user, pass an unauthenticated token.</span></span> <span data-ttu-id="190bd-113">Em qualquer um dos casos, o aplicativo [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] representa qualquer token recebido, se a representação estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="190bd-113">In either case, the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application impersonates whichever token is received if impersonation is enabled.</span></span> <span data-ttu-id="190bd-114">Você pode habilitar a representação no cliente, modificando o arquivo Web.config do aplicativo cliente como a seguir:</span><span class="sxs-lookup"><span data-stu-id="190bd-114">You can enable impersonation on the client, by modifying the Web.config file of the client application as follows:</span></span>  
  
```  
<!-- Web.config file. -->  
<identity impersonate="true"/>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="190bd-115">A representação é desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="190bd-115">Impersonation is disabled by default.</span></span>  
  
 <span data-ttu-id="190bd-116">Para obter mais informações sobre [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] representação, consulte a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentação do SDK do.</span><span class="sxs-lookup"><span data-stu-id="190bd-116">For more information about [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] impersonation, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="managing-the-report-server-using-soap-api"></a><span data-ttu-id="190bd-117">Gerenciando do servidor de relatório por meio da API SOAP</span><span class="sxs-lookup"><span data-stu-id="190bd-117">Managing the Report Server using SOAP API</span></span>  
 <span data-ttu-id="190bd-118">Você também pode usar seu aplicativo Web para gerenciar um servidor de relatório e seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="190bd-118">You can also use your Web application to manage a report server and its contents.</span></span> <span data-ttu-id="190bd-119">O Gerenciador de Relatórios, incluído com o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], é um exemplo de aplicativo Web criado completamente por meio do [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] e da API SOAP do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="190bd-119">Report Manager, included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], is an example of a Web application that is completely built using [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] and the Reporting Services SOAP API.</span></span> <span data-ttu-id="190bd-120">Você pode adicionar a funcionalidade de gerenciamento de relatório do Gerenciador de Relatórios para seus aplicativos Web personalizados.</span><span class="sxs-lookup"><span data-stu-id="190bd-120">You can add the report management functionality of Report Manager to your custom Web applications.</span></span> <span data-ttu-id="190bd-121">Por exemplo, talvez você queira retornar uma lista de relatórios disponíveis no banco de dados do servidor de relatório e exibi-los em um [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` controle para os usuários escolherem.</span><span class="sxs-lookup"><span data-stu-id="190bd-121">For example, you might want to return a list of available reports in the report server database and display them in a [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` control for your users to choose from.</span></span> <span data-ttu-id="190bd-122">O código a seguir conecta-se ao banco de dados do servidor de relatório e retorna uma lista de itens no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="190bd-122">The following code connects to the report server database and returns a list of items in the report server database.</span></span> <span data-ttu-id="190bd-123">Os relatórios disponíveis são, em seguida, adicionados a um controle Listbox que exibe o caminho de cada relatório.</span><span class="sxs-lookup"><span data-stu-id="190bd-123">The available reports are then added to a Listbox control, which displays the path of each report.</span></span>  
  
```vb  
Private Sub Page_Load(sender As Object, e As System.EventArgs)  
   ' Create a Web service proxy object and set credentials  
   Dim rs As New ReportingService2005()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return a list of catalog items in the report server database  
   Dim items As CatalogItem() = rs.ListChildren("/", True)  
  
   ' For each report, display the path of the report in a Listbox  
   Dim ci As CatalogItem  
   For Each ci In  items  
      If ci.Type = ItemTypeEnum.Report Then  
         catalogListBox.Items.Add(ci.Path)  
      End If  
   Next ci  
End Sub ' Page_Load   
```  
  
```csharp  
private void Page_Load(object sender, System.EventArgs e)  
{  
   // Create a Web service proxy object and set credentials  
   ReportingService2005 rs = new ReportingService2005();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return a list of catalog items in the report server database  
   CatalogItem[] items = rs.ListChildren("/", true);  
  
   // For each report, display the path of the report in a Listbox  
   foreach(CatalogItem ci in items)  
   {  
      if (ci.Type == ItemTypeEnum.Report)  
         catalogListBox.Items.Add(ci.Path);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="190bd-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="190bd-124">See Also</span></span>  
 <span data-ttu-id="190bd-125">[Criando aplicativos usando o serviço Web e o .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="190bd-125">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="190bd-126">[Integrando Reporting Services em aplicativos](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="190bd-126">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="190bd-127">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="190bd-127">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="190bd-128">Usando a API SOAP em um aplicativo do Windows</span><span class="sxs-lookup"><span data-stu-id="190bd-128">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
  
  
