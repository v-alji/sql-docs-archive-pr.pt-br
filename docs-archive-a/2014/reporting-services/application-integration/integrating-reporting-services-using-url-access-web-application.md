---
title: Usando o acesso à URL em um aplicativo Web | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- links [Reporting Services], URL access
- URL access [Reporting Services], Web applications
- POST requests
- direct addressing [Reporting Services]
- Web applications [Reporting Services]
- hyperlinks [Reporting Services]
ms.assetid: 39e7918c-ad2d-4ca6-b099-2dd4dbdb83dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd31f76658f8160cbb2a576debc335588f77e72c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568355"
---
# <a name="using-url-access-in-a-web-application"></a><span data-ttu-id="2b3e5-102">Usando o acesso à URL em um aplicativo Web</span><span class="sxs-lookup"><span data-stu-id="2b3e5-102">Using URL Access in a Web Application</span></span>
  <span data-ttu-id="2b3e5-103">O acesso à URL no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] foi especificamente criado para permitir o acesso a relatórios individuais pela rede.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-103">URL access in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is specifically designed to enable access to individual reports over a network.</span></span> <span data-ttu-id="2b3e5-104">Esse tipo de acesso é melhor para a integração da exibição de relatórios e da navegação em um aplicativo Web personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-104">This type of access is best for integrating report viewing and navigation into a custom Web application.</span></span> <span data-ttu-id="2b3e5-105">Para usar o acesso à URL em aplicativos Web, você pode:</span><span class="sxs-lookup"><span data-stu-id="2b3e5-105">To use URL access in Web applications, you can:</span></span>  
  
-   <span data-ttu-id="2b3e5-106">Envie uma URL a um servidor de relatório específico a partir de um site ou de portal.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-106">Address a URL to a specific report server from a Web site or portal.</span></span>  
  
-   <span data-ttu-id="2b3e5-107">Use um método POST e passe parâmetros de cadeia de caracteres da consulta para uma URL do servidor de relatório usando campos de formulário.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-107">Use a form POST method and pass query string parameters to a report server URL using form fields.</span></span>  
  
## <a name="url-access-through-direct-addressing"></a><span data-ttu-id="2b3e5-108">Acesso à URL por meio de endereçamento direto</span><span class="sxs-lookup"><span data-stu-id="2b3e5-108">URL Access Through Direct Addressing</span></span>  
 <span data-ttu-id="2b3e5-109">Para acessar um servidor de relatório ou item de banco de dados do servidor de relatório usando uma URL, basta fornecer o endereço da URL em um navegador da Web ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-109">To access a report server or report server database item using a URL, simply provide the URL address from within a Web browser or application.</span></span> <span data-ttu-id="2b3e5-110">Você também pode fornecer parâmetros à URL que podem afetar a aparência do relatório ou do recurso acessado.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-110">You can also supply parameters to the URL that can affect the appearance of the report or resource that is being accessed.</span></span> <span data-ttu-id="2b3e5-111">Uma URL pode ter como destino um servidor de relatório por meio da barra de endereços de um navegador da Web ou uma URL pode ser a origem de um **IFrame** que faz parte de um aplicativo Web maior ou de um portal.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-111">A URL can target a report server through the address bar of a Web browser, or a URL can be the source of an **IFrame** that is part of a larger Web application or portal.</span></span> <span data-ttu-id="2b3e5-112">Você pode incluir hiperlinks para relatórios em várias páginas da Web do seu portal, além de ter como destino um quadro específico para o relatório ou abrir uma nova janela do navegador no processo.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-112">You can include hyperlinks to reports on various Web pages of your portal, as well as target a specific frame for the report or open a new browser window in the process.</span></span>  
  
 <span data-ttu-id="2b3e5-113">No exemplo a seguir, o hiperlink tem como destino um quadro chamado "main", que poderia ser diferente do que inclui o hiperlink.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-113">In the following example, the hyperlink targets a frame named "main", which might be different from the one that includes the hyperlink.</span></span> <span data-ttu-id="2b3e5-114">O hiperlink poderia fazer parte de um portal da Web.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-114">The hyperlink might be part of Web portal.</span></span>  
  
```  
<a href="http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main" target="main" >  
   Click here for the Territory Sales Drilldown sample report  
</a>  
```  
  
 <span data-ttu-id="2b3e5-115">No exemplo anterior, a configuração de informações de dispositivo **LinkTarget** é passada com um valor “main” na cadeia de consulta da URL.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-115">In the previous example, the device information setting **LinkTarget** is passed with a value of "main" in the query string of the URL.</span></span> <span data-ttu-id="2b3e5-116">Isso garante que qualquer hiperlink de detalhamento do relatório também terá como destino o quadro chamado "main".</span><span class="sxs-lookup"><span data-stu-id="2b3e5-116">This ensures that any drillthrough hyperlinks in the report also target the frame named "main".</span></span>  
  
 <span data-ttu-id="2b3e5-117">Para obter mais informações sobre as configurações de informações de dispositivo, consulte [Passando as configurações de informações de dispositivo para extensões de renderização](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="2b3e5-117">For more information about device information settings, see [Passing Device Information Settings to Rendering Extensions](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="2b3e5-118">Observe que muitos servidores e navegadores limitam o número de caracteres permitidos em uma URL.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-118">Note that many servers and browsers limit the number of characters allowed in a URL.</span></span> <span data-ttu-id="2b3e5-119">Em alguns casos, é imposto um limite de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-119">In some cases, a 256-character limit is imposed.</span></span> <span data-ttu-id="2b3e5-120">Para contornar essa limitação, você poderá usar solicitações POST usando submissão de formulário.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-120">To get around this limitation, you can use POST requests using form submission.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b3e5-121">O Internet Explorer tem um comprimento máximo de URL de 2.083 caracteres.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-121">Internet Explorer has a maximum URL length of 2,083 characters.</span></span> <span data-ttu-id="2b3e5-122">Esse limite se aplica às URLs de solicitação POST e GET.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-122">This limit applies to both POST and GET request URLs.</span></span> <span data-ttu-id="2b3e5-123">No entanto, POST não está limitado pelo tamanho da URL para o envio de pares de nome/valor como parte de um formulário, já que eles são transferidos no cabeçalho e não na URL.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-123">POST, however, is not limited by the size of the URL for submitting name/value pairs as part of a form, because they are transferred in the header and not the URL.</span></span>  
  
## <a name="url-access-through-a-form-post-method"></a><span data-ttu-id="2b3e5-124">Acesso à URL por meio de um método POST de formulário</span><span class="sxs-lookup"><span data-stu-id="2b3e5-124">URL Access Through a Form POST Method</span></span>  
 <span data-ttu-id="2b3e5-125">Quando um usuário solicita dados de um servidor de relatório usando acesso à URL, a solicitação HTTP usa o método GET.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-125">When a user requests data from a report server using URL access, the HTTP request uses the GET method.</span></span> <span data-ttu-id="2b3e5-126">Isso é equivalente a uma submissão de formulário onde METHOD= "GET".</span><span class="sxs-lookup"><span data-stu-id="2b3e5-126">This is equivalent to a form submission where METHOD="GET".</span></span> <span data-ttu-id="2b3e5-127">Solicitações de URL ou submissões de formulário que usam METHOD= "GET" estão limitados pelo número máximo de caracteres que um servidor ou navegador da Web pode processar.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-127">URL requests or form submissions that use METHOD="GET" are limited by the maximum number of characters that a server or Web browser can process.</span></span>  
  
 <span data-ttu-id="2b3e5-128">Com as solicitações POST (METHOD= "POST" e campos de entrada), os pares de nome/valor são transferidos no cabeçalho e não na URL.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-128">With POST requests (METHOD="POST" and input fields), the name/value pairs are transferred in the header and not the URL.</span></span> <span data-ttu-id="2b3e5-129">Dessa forma, os pares de nome/valor da cadeia de caracteres de consulta não fazem parte da URL, permitindo que você forneça listas de parâmetros mais longas e mais complexas.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-129">Therefore, the name/value pairs of the query string are not part of the URL, thus enabling you to provide much longer and more complex parameter lists.</span></span>  
  
 <span data-ttu-id="2b3e5-130">Usando o acesso direto, um usuário pode ver a URL para o servidor de relatório e poderá ser capaz de modificar a cadeia de caracteres de consulta ou observar os parâmetros de solicitação URL e do servidor de relatório para uso posterior.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-130">Using direct access, a user can see the URL for the report server, and may be able to modify the  query string or note the particular URL request and report server parameters for later use.</span></span>  
  
 <span data-ttu-id="2b3e5-131">O HTML de exemplo a seguir demonstra a utilização de um formulário que pode ser usado para ter como destino um servidor de relatório com uma URL específica e passar parâmetros de cadeia de caracteres de consulta como parte dos campos de entrada do formulário.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-131">The following sample HTML demonstrates the use of a form that you can use to target a report server with a specific URL and pass query string parameters as part of the form's input fields.</span></span>  
  
```  
<FORM id="frmRender" action="http://server/reportserver?/SampleReports/  
   Territory Sales Drilldown" method="post" target="_self">  
   <INPUT type="hidden" name="rs:Command" value="Render">   
   <INPUT type="hidden" name="rc:LinkTarget" value="main">  
   <INPUT type="hidden" name="rs:Format" value="HTML4.0">  
   <INPUT type="submit" value="Button">  
</FORM>  
```  
  
 <span data-ttu-id="2b3e5-132">No exemplo anterior, se um usuário clicar no botão do formulário, o servidor de relatório retornará um relatório renderizado em HTML destinado ao quadro atual.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-132">In the previous example, if a user clicks the button on the form, the report server returns an HTML-rendered report targeted at the current frame.</span></span> <span data-ttu-id="2b3e5-133">Uma cadeia de caracteres de acesso à URL comparável poderia ficar assim:</span><span class="sxs-lookup"><span data-stu-id="2b3e5-133">A comparable URL access string might look like the following:</span></span>  
  
```  
http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main&rs:Format=HTML4.0  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b3e5-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b3e5-134">See Also</span></span>  
 <span data-ttu-id="2b3e5-135">[Integrando Reporting Services em aplicativos](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="2b3e5-135">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="2b3e5-136">[Integrando Reporting Services usando o acesso à URL](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="2b3e5-136">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="2b3e5-137">[Usando o acesso à URL em um aplicativo do Windows](integrating-reporting-services-using-url-access-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="2b3e5-137">[Using URL Access in a Windows Application](integrating-reporting-services-using-url-access-windows-application.md) </span></span>  
 [<span data-ttu-id="2b3e5-138">Acesso à URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2b3e5-138">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
