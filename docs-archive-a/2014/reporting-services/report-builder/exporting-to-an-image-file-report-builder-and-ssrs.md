---
title: Exportando para um arquivo de imagem (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 020d8ea2-de07-4212-a2bb-2ed0df2c8db8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dc1c8539b39a99c252ebfcb0275b674f657de6c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573792"
---
# <a name="exporting-to-an-image-file-report-builder-and-ssrs"></a><span data-ttu-id="17c29-102">Exportando para um arquivo de imagem (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="17c29-102">Exporting to an Image File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="17c29-103">A extensão de renderização da Imagem renderiza um relatório para um bitmap ou metarquivo.</span><span class="sxs-lookup"><span data-stu-id="17c29-103">The Image rendering extension renders a report to a bitmap or metafile.</span></span> <span data-ttu-id="17c29-104">Por padrão, a extensão de renderização da Imagem produz um arquivo TIFF do relatório, que pode ser exibido em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="17c29-104">By default, the Image rendering extension produces a TIFF file of the report, which can be viewed in multiple pages.</span></span> <span data-ttu-id="17c29-105">Quando o cliente receber a imagem, ela pode ser exibida em um visualizador de imagem e impressa.</span><span class="sxs-lookup"><span data-stu-id="17c29-105">When the client receives the image, it can be displayed in an image viewer and printed.</span></span> <span data-ttu-id="17c29-106">Este tópico fornece as informações específicas do processador de Imagem e descreve as exceções às regras de renderização.</span><span class="sxs-lookup"><span data-stu-id="17c29-106">This topic provides Image renderer-specific information and describes exceptions to the rendering rules.</span></span>  
  
 <span data-ttu-id="17c29-107">A extensão de renderização de Imagem pode gerar arquivos em qualquer um dos formatos que tenham o suporte do [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG e TIFF.</span><span class="sxs-lookup"><span data-stu-id="17c29-107">The Image rendering extension can generate files in any of the formats supported by [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="17c29-108">Para o formato TIFF, o nome de arquivo do fluxo primário é *NomedoRelatório*.tif.</span><span class="sxs-lookup"><span data-stu-id="17c29-108">For TIFF format, the file name of the primary stream is *ReportName*.tif.</span></span> <span data-ttu-id="17c29-109">Para todos os outros formatos, que renderizam como uma página única por arquivo, o nome do arquivo é *ReportName_Page.ext* .</span><span class="sxs-lookup"><span data-stu-id="17c29-109">For all other formats, which render as a single page per file, the file name is *ReportName_Page.ext* where.</span></span> <span data-ttu-id="17c29-110">*ext* é a extensão do arquivo para o formato selecionado.</span><span class="sxs-lookup"><span data-stu-id="17c29-110">*ext* is the file extension for the chosen format.</span></span> <span data-ttu-id="17c29-111">Para gerar um arquivo em outro formato com suporte da Imagem, especifique qualquer uma das cadeias de caracteres listadas anteriormente na configuração **OutputFormatDeviceInfo** .</span><span class="sxs-lookup"><span data-stu-id="17c29-111">To produce a file in another Image-supported format, specify any of the above listed strings in the **OutputFormatDeviceInfo** setting.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="supported-image-formats"></a><a name="SupportedImageFormats"></a> <span data-ttu-id="17c29-112">Formatos de imagem com suporte</span><span class="sxs-lookup"><span data-stu-id="17c29-112">Supported Image Formats</span></span>  
 <span data-ttu-id="17c29-113">A tabela a seguir mostra a extensão de arquivo e MimeType para cada formato do processador de Imagem.</span><span class="sxs-lookup"><span data-stu-id="17c29-113">The following table shows the file extension and MimeType for each Image renderer format.</span></span>  
  
|<span data-ttu-id="17c29-114">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="17c29-114">**Type**</span></span>|<span data-ttu-id="17c29-115">**Extensão**</span><span class="sxs-lookup"><span data-stu-id="17c29-115">**Extension**</span></span>|<span data-ttu-id="17c29-116">**MIMEType**</span><span class="sxs-lookup"><span data-stu-id="17c29-116">**MIMEType**</span></span>|  
|--------------|-------------------|------------------|  
|<span data-ttu-id="17c29-117">BMP</span><span class="sxs-lookup"><span data-stu-id="17c29-117">BMP</span></span>|<span data-ttu-id="17c29-118">bmp</span><span class="sxs-lookup"><span data-stu-id="17c29-118">bmp</span></span>|<span data-ttu-id="17c29-119">image/bmp</span><span class="sxs-lookup"><span data-stu-id="17c29-119">image/bmp</span></span>|  
|<span data-ttu-id="17c29-120">GIF</span><span class="sxs-lookup"><span data-stu-id="17c29-120">GIF</span></span>|<span data-ttu-id="17c29-121">GIF</span><span class="sxs-lookup"><span data-stu-id="17c29-121">gif</span></span>|<span data-ttu-id="17c29-122">image/gif</span><span class="sxs-lookup"><span data-stu-id="17c29-122">image/gif</span></span>|  
|<span data-ttu-id="17c29-123">JPEG</span><span class="sxs-lookup"><span data-stu-id="17c29-123">JPEG</span></span>|<span data-ttu-id="17c29-124">jpeg</span><span class="sxs-lookup"><span data-stu-id="17c29-124">jpeg</span></span>|<span data-ttu-id="17c29-125">image/jpeg</span><span class="sxs-lookup"><span data-stu-id="17c29-125">image/jpeg</span></span>|  
|<span data-ttu-id="17c29-126">PNG</span><span class="sxs-lookup"><span data-stu-id="17c29-126">PNG</span></span>|<span data-ttu-id="17c29-127">png</span><span class="sxs-lookup"><span data-stu-id="17c29-127">png</span></span>|<span data-ttu-id="17c29-128">image/png</span><span class="sxs-lookup"><span data-stu-id="17c29-128">image/png</span></span>|  
|<span data-ttu-id="17c29-129">TIFF</span><span class="sxs-lookup"><span data-stu-id="17c29-129">TIFF</span></span>|<span data-ttu-id="17c29-130">tif</span><span class="sxs-lookup"><span data-stu-id="17c29-130">tif</span></span>|<span data-ttu-id="17c29-131">imagem/tiff</span><span class="sxs-lookup"><span data-stu-id="17c29-131">image/tiff</span></span>|  
|<span data-ttu-id="17c29-132">EMF</span><span class="sxs-lookup"><span data-stu-id="17c29-132">EMF</span></span>|<span data-ttu-id="17c29-133">EMF</span><span class="sxs-lookup"><span data-stu-id="17c29-133">emf</span></span>|<span data-ttu-id="17c29-134">imagem/emf</span><span class="sxs-lookup"><span data-stu-id="17c29-134">image/emf</span></span>|  
|<span data-ttu-id="17c29-135">EMFPlus</span><span class="sxs-lookup"><span data-stu-id="17c29-135">EMFPlus</span></span>|<span data-ttu-id="17c29-136">EMF</span><span class="sxs-lookup"><span data-stu-id="17c29-136">emf</span></span>|<span data-ttu-id="17c29-137">imagem/emf</span><span class="sxs-lookup"><span data-stu-id="17c29-137">image/emf</span></span>|  
  
  
##  <a name="rendering-multiple-pages"></a><a name="RenderingMultiplePages"></a> <span data-ttu-id="17c29-138">Renderizando várias páginas</span><span class="sxs-lookup"><span data-stu-id="17c29-138">Rendering Multiple Pages</span></span>  
 <span data-ttu-id="17c29-139">TIFF é o único formato que dá suporte a documentos de várias páginas em um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="17c29-139">TIFF is the only format that supports multiple page documents in a single file.</span></span> <span data-ttu-id="17c29-140">Os demais formatos, como JPG ou PNG, emitem uma página por vez e requerem uma chamada separada para a extensão de renderização de cada página.</span><span class="sxs-lookup"><span data-stu-id="17c29-140">Other formats, such as JPG or PNG, output one page at a time and require a separate call to the rendering extension for each page.</span></span>  
  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="17c29-141">Interatividade</span><span class="sxs-lookup"><span data-stu-id="17c29-141">Interactivity</span></span>  
 <span data-ttu-id="17c29-142">A interatividade não tem suporte em formatos de Imagem gerados por esse renderizador.</span><span class="sxs-lookup"><span data-stu-id="17c29-142">Interactivity is not supported in any Image formats generated by this renderer.</span></span> <span data-ttu-id="17c29-143">Os elementos interativos a seguir não são renderizados:</span><span class="sxs-lookup"><span data-stu-id="17c29-143">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="17c29-144">Hiperlinks</span><span class="sxs-lookup"><span data-stu-id="17c29-144">Hyperlinks</span></span>  
  
-   <span data-ttu-id="17c29-145">Mostrar ou ocultar</span><span class="sxs-lookup"><span data-stu-id="17c29-145">Show or Hide</span></span>  
  
-   <span data-ttu-id="17c29-146">Mapa do documento</span><span class="sxs-lookup"><span data-stu-id="17c29-146">Document Map</span></span>  
  
-   <span data-ttu-id="17c29-147">Links de detalhamento ou de clique</span><span class="sxs-lookup"><span data-stu-id="17c29-147">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="17c29-148">Classificação de usuário final</span><span class="sxs-lookup"><span data-stu-id="17c29-148">End user sort</span></span>  
  
-   <span data-ttu-id="17c29-149">Cabeçalhos fixos</span><span class="sxs-lookup"><span data-stu-id="17c29-149">Fixed headers</span></span>  
  
-   <span data-ttu-id="17c29-150">Indicadores</span><span class="sxs-lookup"><span data-stu-id="17c29-150">Bookmarks</span></span>  
  
  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="17c29-151">Configurações de informações do dispositivo</span><span class="sxs-lookup"><span data-stu-id="17c29-151">Device Information Settings</span></span>  
 <span data-ttu-id="17c29-152">Você pode alterar algumas configurações padrão desse renderizador alterando as configurações de informações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="17c29-152">You can change some default settings for this renderer by changing the device information settings.</span></span> <span data-ttu-id="17c29-153">Para obter mais informações, consulte [Image Device Information Settings](../image-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="17c29-153">For more information, see [Image Device Information Settings](../image-device-information-settings.md).</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="17c29-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="17c29-154">See Also</span></span>  
 <span data-ttu-id="17c29-155">[Paginação em Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="17c29-155">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="17c29-156">[Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="17c29-156">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="17c29-157">[Funcionalidade interativa para extensões de renderização de relatório diferentes &#40;Construtor de Relatórios e SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="17c29-157">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="17c29-158">[Renderizando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="17c29-158">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="17c29-159">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="17c29-159">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
