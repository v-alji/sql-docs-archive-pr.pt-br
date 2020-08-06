---
title: Especificar uma imagem como um ponteiro em um medidor (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d73b3c3-a068-4868-a2be-0cd261b6e92b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c694cdb90fb668c43eb7e9971bba967bad8dd9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682089"
---
# <a name="specify-an-image-as-a-pointer-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="adada-102">Especificar uma imagem como um ponteiro em um medidor (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="adada-102">Specify an Image as a Pointer on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="adada-103">O medidor contém três estilos internos que podem ser usados para personalizar a aparência do ponteiro.</span><span class="sxs-lookup"><span data-stu-id="adada-103">The gauge contains three built-in styles that can be used to customize the appearance of the pointer.</span></span> <span data-ttu-id="adada-104">Para um medidor radial, os estilos internos são: Agulha, Marcador e Barra.</span><span class="sxs-lookup"><span data-stu-id="adada-104">For a radial gauge, the built in styles are: Needle, Marker and Bar.</span></span> <span data-ttu-id="adada-105">Para um medidor linear, os estilos internos são: Marcador, Barra e Termômetro.</span><span class="sxs-lookup"><span data-stu-id="adada-105">For a linear gauge, the built-in styles are Marker, Bar, and Thermometer.</span></span> <span data-ttu-id="adada-106">Se um único ponteiro for necessário, o usuário poderá criar e especificar uma imagem que pode ser usada como um ponteiro totalmente funcional.</span><span class="sxs-lookup"><span data-stu-id="adada-106">If a unique pointer is required, the user can create and specify an image which can be used as a fully functional pointer.</span></span>  
  
 <span data-ttu-id="adada-107">Quando você está especificando uma imagem para o ponteiro, sua imagem deve ter as seguintes especificações:</span><span class="sxs-lookup"><span data-stu-id="adada-107">When you are specifying an image for the pointer, your image must have the following specifications:</span></span>  
  
-   <span data-ttu-id="adada-108">A origem do ponteiro, ou centro da rotação, deve estar na parte superior da imagem.</span><span class="sxs-lookup"><span data-stu-id="adada-108">The origin of the pointer, or center of rotation, must be at the top of the image.</span></span>  
  
-   <span data-ttu-id="adada-109">A extremidade do ponteiro deve estar apontando para baixo.</span><span class="sxs-lookup"><span data-stu-id="adada-109">The end of the pointer must be pointing down.</span></span>  
  
 <span data-ttu-id="adada-110">Uma vez que o ponteiro é uma forma irregular, você precisará especificar uma cor de transparência para ocultar as partes desnecessárias da imagem.</span><span class="sxs-lookup"><span data-stu-id="adada-110">Since the pointer is an irregular shape, you will need to specify a transparency color to hide the unnecessary portions of the image.</span></span> <span data-ttu-id="adada-111">Considere usar uma cor que normalmente seria mostrada no medidor como a cor de transparência, uma vez que as cores especificadas não serão exibidas no medidor.</span><span class="sxs-lookup"><span data-stu-id="adada-111">Consider using a color that would not normally be shown on the gauge as the transparency color, since the colors specified will not appear on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-an-image-as-a-pointer-on-the-gauge"></a><span data-ttu-id="adada-112">Para especificar uma imagem como um ponteiro no medidor</span><span class="sxs-lookup"><span data-stu-id="adada-112">To specify an image as a pointer on the gauge</span></span>  
  
1.  <span data-ttu-id="adada-113">No modo Design, clique no ponteiro do medidor.</span><span class="sxs-lookup"><span data-stu-id="adada-113">In Design view, click the pointer of the gauge.</span></span>  
  
2.  <span data-ttu-id="adada-114">Adicional Se não existir nenhum ponteiro no medidor, clique com o botão direito do mouse no medidor e selecione **Adicionar ponteiro**.</span><span class="sxs-lookup"><span data-stu-id="adada-114">(Optional) If no pointer exists on the gauge, right-click on the gauge and select **Add Pointer**.</span></span> <span data-ttu-id="adada-115">Um ponteiro é adicionado ao medidor.</span><span class="sxs-lookup"><span data-stu-id="adada-115">A pointer is added to the gauge.</span></span>  
  
3.  <span data-ttu-id="adada-116">Clique na guia **Inserir** na faixa de faixas e clique duas vezes no ícone de imagem.</span><span class="sxs-lookup"><span data-stu-id="adada-116">Click the **Insert** tab on the ribbon and double-click the image icon.</span></span> <span data-ttu-id="adada-117">A caixa de diálogo **Propriedades da Imagem** será aberta.</span><span class="sxs-lookup"><span data-stu-id="adada-117">The **Image Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="adada-118">Adicione uma imagem a seu relatório.</span><span class="sxs-lookup"><span data-stu-id="adada-118">Add an image to your report.</span></span> <span data-ttu-id="adada-119">Para obter mais informações, consulte [Inserir uma imagem em um relatório &#40;Construtor de relatórios e SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="adada-119">For more information, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="adada-120">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="adada-120">Open the Properties pane.</span></span>  
  
6.  <span data-ttu-id="adada-121">Na superfície de design, clique no ponteiro.</span><span class="sxs-lookup"><span data-stu-id="adada-121">On the design surface, click on the pointer.</span></span> <span data-ttu-id="adada-122">As propriedades do ponteiro são exibidas no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="adada-122">The properties for the pointer are displayed in the Properties pane.</span></span>  
  
7.  <span data-ttu-id="adada-123">Expanda o nó PointerImage.</span><span class="sxs-lookup"><span data-stu-id="adada-123">Expand the PointerImage node.</span></span>  
  
8.  <span data-ttu-id="adada-124">Em **origem**, selecione **inserido** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="adada-124">In **Source**, select **Embedded** from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="adada-125">Se sua imagem for armazenada no banco de dados ou na Web, você poderá especificar a opção adequada para essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="adada-125">If your image is stored in the database or on the web, you can specify the appropriate option for this property.</span></span> <span data-ttu-id="adada-126">Para obter mais informações, consulte [caixa de diálogo Propriedades da imagem, &#40;geral Construtor de relatórios e SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="adada-126">For more information, see [Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span></span>  
  
9. <span data-ttu-id="adada-127">Em **valor**, selecione o nome da imagem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="adada-127">In **Value**, select the name of your image from the drop-down list.</span></span>  
  
10. <span data-ttu-id="adada-128">Em **TransparentColor**, escolha um valor de cor que você deseja remover da imagem.</span><span class="sxs-lookup"><span data-stu-id="adada-128">In **TransparentColor**, pick a color value that you want to remove from the image.</span></span> <span data-ttu-id="adada-129">Isso criará uma aparência perfeita do ponteiro no medidor.</span><span class="sxs-lookup"><span data-stu-id="adada-129">This will create a seamless appearance for the pointer in the gauge.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adada-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="adada-130">See Also</span></span>  
 <span data-ttu-id="adada-131">[Formatando ponteiros em um medidor &#40;Construtor de Relatórios e SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="adada-131">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="adada-132">[Adicionar um medidor a um relatório &#40;Construtor de Relatórios e SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="adada-132">[Add a Gauge to a Report &#40;Report Builder and SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="adada-133">[Formatando linhas, cores e imagens &#40;Construtor de Relatórios e SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="adada-133">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="adada-134">Medidores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="adada-134">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
