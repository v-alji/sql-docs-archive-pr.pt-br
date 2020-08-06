---
title: Imagens (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fcc2db5c-5c26-4607-ae2b-f65c80360536
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f0840a10cc1082ba8dc7912862f7cf34c64972d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679708"
---
# <a name="images-report-builder-and-ssrs"></a><span data-ttu-id="bc02e-102">Imagens (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bc02e-102">Images (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bc02e-103">Uma imagem é um item de relatório que contém uma referência a uma imagem inserida em um relatório, armazenada em um banco de dados, no servidor de relatório ou em qualquer outro lugar na Web.</span><span class="sxs-lookup"><span data-stu-id="bc02e-103">An image is a report item that contains a reference to an image that is embedded in the report, stored in a database, stored on the report server, or stored elsewhere on the Web.</span></span> <span data-ttu-id="bc02e-104">Uma imagem pode ser uma imagem que é repetida com linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="bc02e-104">An image can be a picture that is repeated with rows of data.</span></span> <span data-ttu-id="bc02e-105">Você também pode usar uma imagem como plano de fundo para determinados itens de relatórios.</span><span class="sxs-lookup"><span data-stu-id="bc02e-105">You can also use an image as a background for certain report items.</span></span>  
  
 <span data-ttu-id="bc02e-106">Convém armazenar logotipos em um servidor pois você pode usar o mesmo logotipo em muitos relatórios.</span><span class="sxs-lookup"><span data-stu-id="bc02e-106">Storing logos on a server is a good idea because you can use the same logo in many reports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="comparing-external-embedded-and-data-bound-images"></a><a name="ComparingImages"></a> <span data-ttu-id="bc02e-107">Comparando imagens externas, inseridas e vinculadas a dados</span><span class="sxs-lookup"><span data-stu-id="bc02e-107">Comparing External, Embedded, and Data-Bound Images</span></span>  
 <span data-ttu-id="bc02e-108">Quando você usar uma imagem com base em servidor ou outra imagem externa em um relatório, o item de imagem conterá um caminho que aponta para uma imagem no servidor de relatório ou onde quer que esteja na Web.</span><span class="sxs-lookup"><span data-stu-id="bc02e-108">When you use a server-based or other external image in a report, the image item contains a path that points to an image on the report server or wherever it exists on the Web.</span></span> <span data-ttu-id="bc02e-109">No entanto, quando você usar uma imagem inserida, seus dados serão armazenados na definição de relatório e não existirão como um arquivo separado.</span><span class="sxs-lookup"><span data-stu-id="bc02e-109">When you use an embedded image, however, the image data is stored within the report definition and does not exist as a separate file.</span></span>  
  
 <span data-ttu-id="bc02e-110">As imagens com base no servidor funcionam bem para logotipos e imagens estáticas compartilhadas entre vários relatórios ou páginas da Web.</span><span class="sxs-lookup"><span data-stu-id="bc02e-110">Server-based images work well for logos and static pictures that are shared among several reports or Web pages.</span></span> <span data-ttu-id="bc02e-111">As imagens inseridas garantem que as imagens estejam sempre disponíveis para o relatório, mas elas não podem ser compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="bc02e-111">Embedded images ensure that the images are always available to the report, but they cannot be shared.</span></span> <span data-ttu-id="bc02e-112">As definições do relatório com imagens externas são menores que as definições com imagens inseridas.</span><span class="sxs-lookup"><span data-stu-id="bc02e-112">Report definitions with external images are smaller than definitions with embedded images.</span></span>  
  
 <span data-ttu-id="bc02e-113">As imagens vinculadas a dados também podem ser exibidas de dados binários armazenados em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc02e-113">Data-bound images can also be displayed from binary data stored in a database.</span></span> <span data-ttu-id="bc02e-114">Por exemplo, as imagens exibidas ao lado dos nomes de produtos em uma lista de produtos são imagens de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc02e-114">For example, the pictures that appear alongside product names in a product list are database images.</span></span> <span data-ttu-id="bc02e-115">Na imagem a seguir, as imagens de bicicletas são armazenadas em um banco de dados e recuperadas no relatório para ilustrar cada produto.</span><span class="sxs-lookup"><span data-stu-id="bc02e-115">In the following picture, the images of bicycles are stored in a database and retrieved in the report to illustrate each product.</span></span>  
  
 <span data-ttu-id="bc02e-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span><span class="sxs-lookup"><span data-stu-id="bc02e-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span></span>  
  

  
##  <a name="images-as-report-parts"></a><a name="ImagesReportParts"></a> <span data-ttu-id="bc02e-117">Imagens como partes do relatório</span><span class="sxs-lookup"><span data-stu-id="bc02e-117">Images as Report Parts</span></span>  
 <span data-ttu-id="bc02e-118">Você pode salvar imagens separadamente de um relatório como partes de relatório.</span><span class="sxs-lookup"><span data-stu-id="bc02e-118">You can save images separately from a report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 
  
##  <a name="embedding-images"></a><a name="EmbedImages"></a> <span data-ttu-id="bc02e-119">Inserindo imagens</span><span class="sxs-lookup"><span data-stu-id="bc02e-119">Embedding Images</span></span>  
 <span data-ttu-id="bc02e-120">Você pode inserir imagens em um relatório para que todos os dados de imagens sejam armazenados na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="bc02e-120">You can embed images in a report so that all image data is stored within the report definition.</span></span> <span data-ttu-id="bc02e-121">Quando você insere uma imagem, ela tem codificação MIME e é armazenada como texto na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="bc02e-121">When you embed an image, the image is MIME-encoded and stored as text in the report definition.</span></span> <span data-ttu-id="bc02e-122">Usar uma imagem inserida garante que ela esteja sempre disponível para o relatório, mas também aumenta o tamanho da definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="bc02e-122">Using an embedded image ensures that the image is always available to the report, but it also increases the size of the report definition.</span></span>  
  
 <span data-ttu-id="bc02e-123">Para obter mais informações sobre como inserir uma imagem, consulte [Inserir uma imagem em um relatório &#40;Construtor de Relatórios e SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc02e-123">For more information about embedding an image, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="external-images"></a><a name="ExternalImages"></a> <span data-ttu-id="bc02e-124">Imagens externas</span><span class="sxs-lookup"><span data-stu-id="bc02e-124">External Images</span></span>  
 <span data-ttu-id="bc02e-125">Você pode incluir imagens armazenadas em um relatório, especificando uma URL para a imagem.</span><span class="sxs-lookup"><span data-stu-id="bc02e-125">You can include stored images in a report by specifying a URL to the image.</span></span> <span data-ttu-id="bc02e-126">Quando você usar uma imagem externa em um relatório, a origem será definida como `External` e o valor da imagem será seu endereço de URL ou o caminho para a imagem.</span><span class="sxs-lookup"><span data-stu-id="bc02e-126">When you use an external image in a report, the image source is set to `External` and the value for the image is the URL address or path to the image.</span></span>  
  
 <span data-ttu-id="bc02e-127">Para obter mais informações, consulte [Especificando caminhos para itens externos &#40;Construtor de Relatórios e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc02e-127">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="bc02e-128">Quando o relatório for executado no Construtor de Relatórios ou no Designer de Relatórios, a visualização usará as credenciais do usuário para exibir a imagem.</span><span class="sxs-lookup"><span data-stu-id="bc02e-128">When the report is run in Report Builder or Report Designer, preview uses the credentials of the user to display the image.</span></span> <span data-ttu-id="bc02e-129">Quando o relatório for executado no servidor de relatório, a imagem no relatório talvez não seja exibida se as credenciais do servidor não forem suficientes para acessá-la.</span><span class="sxs-lookup"><span data-stu-id="bc02e-129">When the report is run on the report server, the image in the report may not be displayed if the server credentials are not sufficient to access the image.</span></span> <span data-ttu-id="bc02e-130">Nesse caso, contate o administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="bc02e-130">In that case, contact your system administrator.</span></span>  
  
 <span data-ttu-id="bc02e-131">Para obter mais informações sobre como adicionar uma imagem externa a um relatório, consulte [Adicionar uma imagem externa &#40;Construtor de Relatórios e SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc02e-131">For more information about adding an external image to a report, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="background-images"></a><a name="BackgroundImages"></a> <span data-ttu-id="bc02e-132">Imagens de plano de fundo</span><span class="sxs-lookup"><span data-stu-id="bc02e-132">Background Images</span></span>  
 <span data-ttu-id="bc02e-133">Você pode usar uma imagem como uma imagem de plano de fundo no corpo do relatório ou em um retângulo, caixa de texto, lista, matriz ou tabela.</span><span class="sxs-lookup"><span data-stu-id="bc02e-133">You can use an image as a background image in the body of the report or in a rectangle, text box, list, matrix, or table.</span></span> <span data-ttu-id="bc02e-134">Uma imagem de plano de fundo e uma imagem têm propriedades semelhantes.</span><span class="sxs-lookup"><span data-stu-id="bc02e-134">A background image and an image have similar properties.</span></span> <span data-ttu-id="bc02e-135">Também é possível especificar como a imagem será repetida para preencher o plano de fundo do item.</span><span class="sxs-lookup"><span data-stu-id="bc02e-135">You can also specify how the image is repeated to fill the background of the item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc02e-136">Algumas extensões de renderização, como a extensão de renderização HTML, renderizam a imagem de plano de fundo do corpo do relatório no corpo, no cabeçalho da página e no rodapé da página.</span><span class="sxs-lookup"><span data-stu-id="bc02e-136">Some rendering extensions, like the HTML rendering extension, render the background image for the report body in the body, the page header, and the page footer.</span></span> <span data-ttu-id="bc02e-137">Você pode definir uma imagem de plano de fundo separada para o cabeçalho e rodapé da página, mas, se nenhuma imagem for definida, o relatório usará a imagem de plano de fundo do corpo.</span><span class="sxs-lookup"><span data-stu-id="bc02e-137">You can define a separate background image for the page header and footer, but if no image is defined, the report uses the background image of the body.</span></span> <span data-ttu-id="bc02e-138">Outras extensões de renderização, como a extensão de renderização de Imagem, não renderizam a imagem de plano de fundo do corpo no cabeçalho e rodapé da página.</span><span class="sxs-lookup"><span data-stu-id="bc02e-138">Other rendering extensions, like the Image rendering extension, do not render the body background image in the page header and footer.</span></span>  
  
 <span data-ttu-id="bc02e-139">Para obter mais informações sobre como adicionar uma imagem de tela de fundo, consulte [Adicionar uma imagem de tela de fundo &#40;Construtor de Relatórios e SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc02e-139">For more information about adding a background image, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="data-bound-images"></a><a name="DataboundImages"></a> <span data-ttu-id="bc02e-140">Imagens vinculadas a dados</span><span class="sxs-lookup"><span data-stu-id="bc02e-140">Data-bound Images</span></span>  
 <span data-ttu-id="bc02e-141">Você pode adicionar imagens armazenadas em um banco de dados ao seu relatório.</span><span class="sxs-lookup"><span data-stu-id="bc02e-141">You can add images that are stored in a database to your report.</span></span> <span data-ttu-id="bc02e-142">Use o mesmo item de relatório de imagem como aquele usado para imagens estáticas, mas com um conjunto de propriedades que indica que a imagem está armazenada em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc02e-142">You use the same image report item as the one used for static images, but with a set of properties that indicate that the image is stored in a database.</span></span> <span data-ttu-id="bc02e-143">Para ver instruções sobre como trabalhar com imagens vinculadas a dados, consulte [Adicionar uma imagem vinculada a dados &#40;Construtor de Relatórios e SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc02e-143">To view instructions about working with data-bound images, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a> <span data-ttu-id="bc02e-144">Tópicos de instruções</span><span class="sxs-lookup"><span data-stu-id="bc02e-144">How-to Topics</span></span>  
 [<span data-ttu-id="bc02e-145">Adicionar uma imagem externa &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc02e-145">Add an External Image &#40;Report Builder and SSRS&#41;</span></span>](add-an-external-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="bc02e-146">Inserir uma imagem em um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc02e-146">Embed an Image in a Report &#40;Report Builder and SSRS&#41;</span></span>](embed-an-image-in-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="bc02e-147">Adicionar uma imagem de tela de fundo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc02e-147">Add a Background Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-background-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="bc02e-148">Adicionar uma imagem vinculada a dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc02e-148">Add a Data-Bound Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-data-bound-image-report-builder-and-ssrs.md)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="bc02e-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc02e-149">See Also</span></span>  
 <span data-ttu-id="bc02e-150">[Exportando para um arquivo de imagem &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc02e-150">[Exporting to an Image File &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bc02e-151">Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc02e-151">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
