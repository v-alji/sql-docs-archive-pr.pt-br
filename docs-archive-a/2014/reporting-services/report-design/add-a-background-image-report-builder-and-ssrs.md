---
title: Adicionar uma imagem de tela de fundo (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c777fefb-8695-44a7-b5cd-a18c587583f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7bc15e1b063a73c463cdb1e7e99075af2a3dce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684550"
---
# <a name="add-a-background-image-report-builder-and-ssrs"></a><span data-ttu-id="01ada-102">Adicionar uma imagem de plano de fundo (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="01ada-102">Add a Background Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="01ada-103">Você pode adicionar uma imagem de plano de fundo a um item de relatório tais como um retângulo, uma caixa de texto, uma lista, uma matriz, uma tabela, algumas partes de um gráfico, ou uma seção de relatório como cabeçalho de página, rodapé de página ou corpo de relatório.</span><span class="sxs-lookup"><span data-stu-id="01ada-103">You can add a background image to a report item such as a rectangle, text box, list, matrix, table, and some parts of a chart, or a report section such as the page header, page footer, or report body.</span></span> <span data-ttu-id="01ada-104">Você pode definir uma imagem de tela de fundo para qualquer item selecionado na superfície de design do relatório que exiba **BackgroundImage** no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="01ada-104">You can define a background image for any selected item on the report design surface that displays **BackgroundImage** in the Properties pane.</span></span> <span data-ttu-id="01ada-105">Assim como outras imagens, a imagem de plano de fundo pode ser uma URL para uma imagem no servidor de relatório, uma imagem de um campo de conjunto de dados ou uma imagem inserida na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="01ada-105">Like other images, the background image can be a URL to an image on the report server, an image from a dataset field, or an image embedded in the report definition.</span></span> <span data-ttu-id="01ada-106">Para usar uma imagem inserida no relatório, primeiro adicione a imagem à definição de relatório antes de adicioná-la à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="01ada-106">To use an image embedded in the report, you must first add the image to the report definition before you can add the image to the design surface.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-the-report-definition"></a><span data-ttu-id="01ada-107">Para inserir uma imagem na definição de relatório</span><span class="sxs-lookup"><span data-stu-id="01ada-107">To embed an image in the report definition</span></span>  
  
1.  <span data-ttu-id="01ada-108">No painel de dados do relatório, clique com o botão direito do mouse no nó **Imagens** e clique em **Adicionar Imagem**.</span><span class="sxs-lookup"><span data-stu-id="01ada-108">In the Report Data pane, right-click the **Images** node, and then click **Add Image**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="01ada-109">Se o painel de dados do relatório não estiver visível, clique em **Dados do Relatório** na guia **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="01ada-109">If the Report Data pane is not visible, on the **View** tab, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="01ada-110">Navegue até a imagem a ser inserida em sua definição de relatório e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="01ada-110">Navigate to the image you want to embed in your report definition, and then click **OK**.</span></span>  
  
### <a name="to-add-a-background-image"></a><span data-ttu-id="01ada-111">Para adicionar uma imagem de plano de fundo</span><span class="sxs-lookup"><span data-stu-id="01ada-111">To add a background image</span></span>  
  
1.  <span data-ttu-id="01ada-112">No modo Design de Relatório, selecione o item de relatório ao qual você deseja adicionar uma imagem de plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="01ada-112">In report design view, select the report item to which you want to add a background image.</span></span>  
  
2.  <span data-ttu-id="01ada-113">Se o painel Propriedades não estiver visível, na guia **Exibir** , selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="01ada-113">If the Properties pane is not visible, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="01ada-114">No painel Propriedades, expanda **BackgroundImage**e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="01ada-114">In the Properties pane, expand **BackgroundImage**, and then do the following:</span></span>  
  
    -   <span data-ttu-id="01ada-115">Para uma imagem inserida:</span><span class="sxs-lookup"><span data-stu-id="01ada-115">For an embedded image:</span></span>  
  
         <span data-ttu-id="01ada-116">Defina **Origem** como **Inserida**.</span><span class="sxs-lookup"><span data-stu-id="01ada-116">Set **Source** to **Embedded**.</span></span>  
  
         <span data-ttu-id="01ada-117">Defina **Valor** como o nome de uma imagem que é inserida no relatório.</span><span class="sxs-lookup"><span data-stu-id="01ada-117">Set **Value** to the name of an image that is embedded in the report.</span></span>  
  
    -   <span data-ttu-id="01ada-118">Para uma imagem externa:</span><span class="sxs-lookup"><span data-stu-id="01ada-118">For an external image:</span></span>  
  
         <span data-ttu-id="01ada-119">Defina **Origem** como **Externa**.</span><span class="sxs-lookup"><span data-stu-id="01ada-119">Set **Source** to **External**.</span></span>  
  
         <span data-ttu-id="01ada-120">Defina **Valor** como um caminho válido para uma imagem.</span><span class="sxs-lookup"><span data-stu-id="01ada-120">Set **Value** to a valid path to an image.</span></span> <span data-ttu-id="01ada-121">Ele pode estar em um servidor de relatório em modo nativo ou em modo Integrado do SharePoint, ou ele pode estar em qualquer outro site.</span><span class="sxs-lookup"><span data-stu-id="01ada-121">This can be on a report server in native mode or SharePoint integrated mode, or it can be on any other Web site.</span></span> <span data-ttu-id="01ada-122">Para obter mais informações, consulte [Adicionar uma imagem externa &#40;Construtor de Relatórios e SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="01ada-122">For more information, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
    -   <span data-ttu-id="01ada-123">Para uma imagem contida em um campo do banco de dados ao qual o item de relatório está conectado:</span><span class="sxs-lookup"><span data-stu-id="01ada-123">For an image is that is contained in a field in the database to which the report item is connected:</span></span>  
  
         <span data-ttu-id="01ada-124">Defina **Origem** como **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="01ada-124">Set **Source** to **Database**.</span></span>  
  
         <span data-ttu-id="01ada-125">Defina **Valor** como o nome de um campo no conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="01ada-125">Set **Value** to the name of a field in the report dataset.</span></span> <span data-ttu-id="01ada-126">Para obter mais informações, consulte [Adicionar uma imagem com limite de dados &#40;Construtor de Relatórios e SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="01ada-126">For more information, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  
         <span data-ttu-id="01ada-127">Para **MIMEType** ou formato de arquivo, selecione o tipo MIME adequado para a imagem; por exemplo, .bmp.</span><span class="sxs-lookup"><span data-stu-id="01ada-127">For **MIMEType**, or file format, select the appropriate MIME type for the image-for example, .bmp.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="01ada-128">MIMEType só poderá ser aplicado se a propriedade **Source** estiver definida como **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="01ada-128">MIMEType applies only if the **Source** property is set to **Database**.</span></span> <span data-ttu-id="01ada-129">Se a propriedade **Source** estiver definida como **Externa** ou **Inserida**, o valor **MIMEType** será ignorado.</span><span class="sxs-lookup"><span data-stu-id="01ada-129">If the **Source** property is set to **External** or **Embedded**, the value of **MIMEType** is ignored.</span></span>  
  
    -   <span data-ttu-id="01ada-130">Para **BackgroundRepeat**, selecione uma expressão, **Default**, **Repeat**, **RepeatX**ou **RepeatY**ou **Clip**.</span><span class="sxs-lookup"><span data-stu-id="01ada-130">For **BackgroundRepeat**, select an expression, **Default**, **Repeat**, **RepeatX**, or **RepeatY**, or **Clip**.</span></span>  
  
         <span data-ttu-id="01ada-131">Para as imagens de tela de fundo em um gráfico, **BackgroundRepeat** poderá ser definido como **Default**, **Repeat**, **Fit**e **Clip**, mas não **RepeatX** ou **RepeatY**.</span><span class="sxs-lookup"><span data-stu-id="01ada-131">For background images in a chart, **BackgroundRepeat** can be set to **Default**, **Repeat**, **Fit**, and **Clip**, but not **RepeatX** or **RepeatY**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ada-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="01ada-132">See Also</span></span>  
 <span data-ttu-id="01ada-133">[Imagens &#40;Construtor de Relatórios e SSRS&#41;](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="01ada-133">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="01ada-134">Caixa de diálogo Propriedades da Imagem, Geral &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="01ada-134">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
