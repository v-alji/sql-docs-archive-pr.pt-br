---
title: Implementando a interface IRenderingExtension | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IRenderingExtension interface
- rendering extensions [Reporting Services], IRenderingExtension interface
ms.assetid: 74b2f2b7-6796-42da-ab7d-b05891ad4001
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f57c4aa41ccfed165b69581cbf3917e4dfbb4960
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574534"
---
# <a name="implementing-the-irenderingextension-interface"></a><span data-ttu-id="5f3f0-102">Implementando a interface IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="5f3f0-102">Implementing the IRenderingExtension Interface</span></span>
  <span data-ttu-id="5f3f0-103">A extensão de renderização obtém os resultados de uma definição de relatório combinada com os dados reais e renderiza os dados resultantes para um formato que seja utilizável.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-103">The rendering extension takes the results from a report definition that is combined with the actual data and renders the resulting data to a format that is useable.</span></span> <span data-ttu-id="5f3f0-104">A transformação dos dados combinados e a formatação são feitas usando uma classe CLR (Common Language Runtime) que implementa <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-104">The transformation of the combined data and formatting is done by using a common language runtime (CLR) class that implements <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension>.</span></span> <span data-ttu-id="5f3f0-105">Isto transforma o modelo de objeto em um formato de saída que é consumível por um visualizador, impressora ou outro destino de saída.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-105">This transforms the object model into an output format that is consumable by a viewer, printer, or other output target.</span></span>  
  
 <span data-ttu-id="5f3f0-106">O <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> tem três métodos que devem ser codificados:</span><span class="sxs-lookup"><span data-stu-id="5f3f0-106">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension> has three methods that must be coded:</span></span>  
  
-   <span data-ttu-id="5f3f0-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> - renderiza o relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-107"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> - renders the report.</span></span>  
  
-   <span data-ttu-id="5f3f0-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> - renderiza um fluxo específico de um relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-108"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> - renders a specific stream from the report.</span></span>  
  
-   <span data-ttu-id="5f3f0-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>- obtém informações adicionais, como ícones, isso é obrigatório para o relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-109"><xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> - gets additional information, such as icons, that are required for the report.</span></span>  
  
 <span data-ttu-id="5f3f0-110">As seções a seguir discutem esses métodos em mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-110">The following sections discuss these methods in more detail.</span></span>  
  
## <a name="render-method"></a><span data-ttu-id="5f3f0-111">Método Render</span><span class="sxs-lookup"><span data-stu-id="5f3f0-111">Render Method</span></span>  
 <span data-ttu-id="5f3f0-112">O método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> contém argumentos que representam os seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="5f3f0-112">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> method contains arguments that represent the following objects:</span></span>  
  
-   <span data-ttu-id="5f3f0-113">O *relatório* que você deseja renderizar.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-113">The *report* that you want to render.</span></span> <span data-ttu-id="5f3f0-114">Esse objeto contém propriedades, dados e informações de layout para o relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-114">This object contains properties, data, and layout information for the report.</span></span> <span data-ttu-id="5f3f0-115">O relatório é a raiz do árvore de modelo de objeto de relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-115">The report is the root of the report object model tree.</span></span>  
  
-   <span data-ttu-id="5f3f0-116">O *ServerParameters*, que contém o objeto de dicionário de cadeia de caracteres, com os parâmetros para o servidor de relatório, se houver.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-116">The *ServerParameters* that contain the string dictionary object, with the parameters for the report server, if any.</span></span>  
  
-   <span data-ttu-id="5f3f0-117">O parâmetro *deviceInfo*, que contém as configurações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-117">The *deviceInfo* parameter that contain the device settings.</span></span> <span data-ttu-id="5f3f0-118">Para obter mais informações, consulte [Passando configurações de informações de dispositivos para extensões de renderização](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="5f3f0-118">For more information, see [Passing Device Information Settings to Rendering Extensions](../../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
-   <span data-ttu-id="5f3f0-119">O parâmetro *clientCapabilities*, que contém um objeto de dicionário <xref:System.Collections.Specialized.NameValueCollection> que contém informações sobre o cliente para o qual você está renderizando.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-119">The *clientCapabilities* parameter that contains a <xref:System.Collections.Specialized.NameValueCollection> dictionary object that has information about the client to which you are rendering.</span></span>  
  
-   <span data-ttu-id="5f3f0-120">O *RenderProperties*, que contém informações sobre o resultado da renderização.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-120">The *RenderProperties* that contains information about the rendering result.</span></span>  
  
-   <span data-ttu-id="5f3f0-121">*createAndRegisterStream* é uma função de delegado a ser chamada para a obtenção de um fluxo no qual será feita a renderização.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-121">The *createAndRegisterStream* is a delegate function to be called to get a stream to render into.</span></span>  
  
### <a name="deviceinfo-parameter"></a><span data-ttu-id="5f3f0-122">Parâmetro deviceInfo</span><span class="sxs-lookup"><span data-stu-id="5f3f0-122">deviceInfo Parameter</span></span>  
 <span data-ttu-id="5f3f0-123">O parâmetro *deviceInfo* contém parâmetros de renderização e não parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-123">The *deviceInfo* parameter contains rendering parameters, not report parameters.</span></span> <span data-ttu-id="5f3f0-124">Esses parâmetros de renderização são passados para a extensão de renderização.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-124">These rendering parameters are passed to the rendering extension.</span></span> <span data-ttu-id="5f3f0-125">Os valores *deviceInfo* são convertidos em um objeto <xref:System.Collections.Specialized.NameValueCollection> pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-125">The *deviceInfo* values are converted into a <xref:System.Collections.Specialized.NameValueCollection> object by the report server.</span></span> <span data-ttu-id="5f3f0-126">Os itens do parâmetro *deviceInfo* são tratados como valores que não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-126">Items in the *deviceInfo* parameter are treated as case-insensitive values.</span></span> <span data-ttu-id="5f3f0-127">Se a solicitação de renderização aconteceu como resultado de acesso à URL, os parâmetros da URL no formato `rc:key=value` são convertidos em pares de chave/valor no objeto de dicionário *deviceInfo*.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-127">If the render request came as a result of URL access, the URL parameters in the form `rc:key=value` are converted to key/value pairs in the *deviceInfo* dictionary object.</span></span> <span data-ttu-id="5f3f0-128">O código de detecção do navegador também fornece os seguintes itens no dicionário *clientCapabilities*: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type e AcceptLanguage.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-128">The browser detection code also provides the following items in the *clientCapabilities* dictionary: EcmaScriptVersion, JavaScript, MajorVersion, MinorVersion, Win32, Type, and AcceptLanguage.</span></span> <span data-ttu-id="5f3f0-129">Qualquer par de nome/valor no parâmetro *deviceInfo* que não é compreendido pela extensão de renderização é ignorado.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-129">Any name/value pair in the *deviceInfo* parameter that is not understood by the rendering extension is ignored.</span></span> <span data-ttu-id="5f3f0-130">O exemplo de código a seguir mostra um método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> de exemplo que recupera ícones:</span><span class="sxs-lookup"><span data-stu-id="5f3f0-130">The following code sample shows a sample <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method that retrieves icons:</span></span>  
  
```csharp  
public void GetRenderingResource (CreateStream createStreamCallback, NameValueCollection deviceInfo)  
{  
    string[] iconTagValues = deviceInfo.GetValues("Icon");  
    if ((iconTagValues != null) && (iconTagValues.Length > 0) )  
    {  
        // Create a stream to output to.  
        Stream outputStream = createStreamCallback(m_iconResourceName, "gif", null, "image/gif", false);  
        // Get the GIF image for one of the buttons on the toolbar  
        Image requiredImage = (Image) m_resourcemanager.GetObject(m_iconResourceName  
        // Write the image to the output stream  
        requiredImage.Save(outputStream, requiredImage.RawFormat);  
    }  
    return;  
}  
```  
  
## <a name="renderstream-method"></a><span data-ttu-id="5f3f0-131">Método RenderStream</span><span class="sxs-lookup"><span data-stu-id="5f3f0-131">RenderStream Method</span></span>  
 <span data-ttu-id="5f3f0-132">O método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> processa um fluxo específico do relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-132">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.RenderStream%2A> method renders a particular stream from the report.</span></span> <span data-ttu-id="5f3f0-133">Todos os fluxos são criados durante a chamada <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> inicial, mas os fluxos não são retornados ao cliente inicialmente.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-133">All streams are created during the initial <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.Render%2A> call, but the streams are not returned to the client initially.</span></span> <span data-ttu-id="5f3f0-134">Esse método é usado para fluxos secundários, como imagens em renderização HTML, ou páginas adicionais de uma extensão de renderização de várias páginas, como Imagem/EMF.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-134">This method is used for secondary streams, such as images in HTML rendering, or additional pages of a multi-page rendering extension, such as Image/EMF.</span></span>  
  
## <a name="getrenderingresource-method"></a><span data-ttu-id="5f3f0-135">Método GetRenderingResource</span><span class="sxs-lookup"><span data-stu-id="5f3f0-135">GetRenderingResource Method</span></span>  
 <span data-ttu-id="5f3f0-136">O método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> recupera as informações sem executar toda renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-136">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method retrieves the information without executing an entire rendering of the report.</span></span> <span data-ttu-id="5f3f0-137">Existem ocasiões em que o relatório necessita de informações que não exigem que o próprio relatório seja renderizado.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-137">There are times when the report requires information that does not require the report itself to be rendered.</span></span> <span data-ttu-id="5f3f0-138">Por exemplo, se você precisar do ícone associado à extensão de renderização, use o parâmetro *DeviceInfo* que contém a única marca **\<Icon>** .</span><span class="sxs-lookup"><span data-stu-id="5f3f0-138">For example, if you need the icon associated with the rendering extension, use the *deviceInfo* parameter containing the single tag **\<Icon>**.</span></span> <span data-ttu-id="5f3f0-139">Nesses casos, você pode usar o método <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f3f0-139">In these cases, you can use the <xref:Microsoft.ReportingServices.OnDemandReportRendering.IRenderingExtension.GetRenderingResource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3f0-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5f3f0-140">See Also</span></span>  
 <span data-ttu-id="5f3f0-141">[Implementando uma extensão de renderização](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="5f3f0-141">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 [<span data-ttu-id="5f3f0-142">Visão geral das extensões de renderização</span><span class="sxs-lookup"><span data-stu-id="5f3f0-142">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
  
  
