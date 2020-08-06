---
title: Formatando linhas, cores e imagens (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.textboxproperties.border.f1
- "10502"
- "10094"
- sql12.rtp.rptdesigner.pictureproperties.border.f1
- "10063"
- sql12.rtp.rptdesigner.rectangleproperties.border.f1
- "10055"
- sql12.rtp.rptdesigner.subreportproperties.border.f1
- "10126"
- sql12.rtp.rptdesigner.shared.borderdv.f1
- "10066"
- sql12.rtp.rptdesigner.reportbody.border.f1
ms.assetid: 0f5f0d2a-9537-4152-b441-b40d7f04cf4c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 681ff6b46f692804aef5c7cbbc16e5abe99dbb2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678625"
---
# <a name="formatting-lines-colors-and-images-report-builder-and-ssrs"></a><span data-ttu-id="61659-102">Formatando linhas, cores e imagens (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="61659-102">Formatting Lines, Colors, and Images (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="61659-103">permite formatar linhas, cores, regiões de dados, imagens e outros itens de relatório.</span><span class="sxs-lookup"><span data-stu-id="61659-103">gives you the ability to format lines, colors, data regions, images, and other report items.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="borders-lines-and-gridlines"></a><span data-ttu-id="61659-104">Bordas, linhas e linhas de grade</span><span class="sxs-lookup"><span data-stu-id="61659-104">Borders, Lines and Gridlines</span></span>  
 <span data-ttu-id="61659-105">Bordas, linhas e linhas de grade podem reunir itens visualmente em uma página e ajudar os leitores ao facilitar a leitura do conteúdo do relatório.</span><span class="sxs-lookup"><span data-stu-id="61659-105">Borders, lines, and gridlines can visually tie items together on the page and help your report readers easily read the contents of the report.</span></span> <span data-ttu-id="61659-106">Você pode adicionar rapidamente uma borda em torno de uma caixa de texto, de um grupo de caixas de texto ou de imagem usando estilos de borda predefinidos.</span><span class="sxs-lookup"><span data-stu-id="61659-106">Using the predefined border styles, you can quickly add a border around a text box, a group of text boxes, or an image.</span></span> <span data-ttu-id="61659-107">Além disso, é possível alterar o estilo, a largura e a cor de bordas, linhas e linhas de grade.</span><span class="sxs-lookup"><span data-stu-id="61659-107">In addition, you can change the style, width, and color for the borders, lines, and gridlines.</span></span> <span data-ttu-id="61659-108">As bordas são adicionadas em toda a volta de um item selecionado ou em uma das margens de um item, por exemplo, ao longo da parte inferior de uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="61659-108">Borders are added around the entire item selected or around a border along an edge of the item, for example, a border along the bottom of a text box.</span></span>  
  
 <span data-ttu-id="61659-109">Para formatar bordas e linhas de grade em uma caixa de texto, do layout do relatório ou em torno de uma imagem, use a guia **Borda** da caixa de diálogo **Propriedades** do item de relatório.</span><span class="sxs-lookup"><span data-stu-id="61659-109">To format borders and gridlines in a text box, report layout, or around an image, use the **Border** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="61659-110">Por exemplo, se você quiser adicionar uma borda em torno de uma imagem, clique com o botão direito do mouse na imagem e, na caixa de diálogo **Propriedades da Imagem** , clique em **Borda**.</span><span class="sxs-lookup"><span data-stu-id="61659-110">For example, if you want to add a border around an image, right-click the image and then in the **Image Properties** dialog box, click **Border**.</span></span>  
  
 <span data-ttu-id="61659-111">Além das molduras de borda padrão, é possível aplicar outras molduras.</span><span class="sxs-lookup"><span data-stu-id="61659-111">In addition to the standard border frames, additional border frames can be applied to charts.</span></span> <span data-ttu-id="61659-112">Para obter mais informações, consulte [Adicionar um quadro de borda a um gráfico &#40;Construtor de Relatórios e SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="61659-112">For more information, see [Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="61659-113">Também é possível adicionar uma borda ao próprio relatório.</span><span class="sxs-lookup"><span data-stu-id="61659-113">You can also add a border to the report itself.</span></span> <span data-ttu-id="61659-114">Para obter mais informações, consulte [Adicionar uma borda a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="61659-114">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="applying-background-colors"></a><span data-ttu-id="61659-115">Aplicando cores do plano de fundo</span><span class="sxs-lookup"><span data-stu-id="61659-115">Applying Background Colors</span></span>  
 <span data-ttu-id="61659-116">Uma cor sólida pode ser adicionada ao plano de fundo do relatório inteiro, de uma caixa de texto do relatório ou de uma célula ou de um grupo de células de uma região de dados.</span><span class="sxs-lookup"><span data-stu-id="61659-116">A solid color can be added to the background of the entire report, a text box within the report, or to a cell or group of cells within a data region.</span></span> <span data-ttu-id="61659-117">Por padrão, a cor do plano de fundo é branca; no entanto, é possível selecionar uma cor na guia **Preenchimento** da caixa de diálogo **Propriedades** do item de relatório.</span><span class="sxs-lookup"><span data-stu-id="61659-117">By default, the background color is white; however, you can select a color from the **Fill** tab of the report item's **Properties** dialog box.</span></span> <span data-ttu-id="61659-118">Por exemplo, para alterar a cor da tela de fundo de uma caixa de texto, clique com o botão direito do mouse na caixa de texto e selecione **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="61659-118">For example, if you want to change the background color of a text box, right-click the text box and select **Text Box Properties**.</span></span> <span data-ttu-id="61659-119">Clique em **Preenchimento** e selecione a cor desejada.</span><span class="sxs-lookup"><span data-stu-id="61659-119">Click **Fill** and then select the color you want.</span></span> <span data-ttu-id="61659-120">Nessa caixa de diálogo, é possível selecionar a cor do plano de fundo do item selecionado ou adicionar uma imagem que será exibida no plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="61659-120">In this dialog box, you can select a background color for the selected item or you can add an image that appears in the background.</span></span>  
  
 <span data-ttu-id="61659-121">Se você usar o gráfico, poderá especificar também gradações e estilos de padrão para cores de plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="61659-121">When you use the chart, you can also specify gradients and pattern styles for background colors.</span></span> <span data-ttu-id="61659-122">Para obter mais informações, consulte [Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="61659-122">For more information, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="using-images-as-formatting"></a><span data-ttu-id="61659-123">Usando imagens como formatação</span><span class="sxs-lookup"><span data-stu-id="61659-123">Using Images as Formatting</span></span>  
 <span data-ttu-id="61659-124">Campos que contêm imagens podem ser adicionados a uma região de dados.</span><span class="sxs-lookup"><span data-stu-id="61659-124">Fields that contain images can be added to a data region.</span></span> <span data-ttu-id="61659-125">Se um campo de imagem for usado, as imagens aparecerão no relatório quando ele for executado.</span><span class="sxs-lookup"><span data-stu-id="61659-125">If you use an image field, the images appear in the report with the report is run.</span></span>  
  
 <span data-ttu-id="61659-126">Também é possível adicionar imagens como logotipos ao plano de fundo do relatório ou a um retângulo, caixa de texto, tabela, matriz, ou algumas partes de um gráfico, ou às seções do corpo e da página de um relatório.</span><span class="sxs-lookup"><span data-stu-id="61659-126">You can also add images such as logos to the background of your report or to a rectangle, text box, table, matrix, or some parts of a chart, or to the body and page sections of a report.</span></span> <span data-ttu-id="61659-127">Para obter mais informações, consulte [Imagens &#40;Construtor de Relatórios e SSRS&#41;](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="61659-127">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61659-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61659-128">See Also</span></span>  
 <span data-ttu-id="61659-129">[Formatando texto e espaços reservados &#40;Construtor de Relatórios e SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61659-129">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="61659-130">[Formatando números e datas &#40;Construtor de Relatórios e SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61659-130">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="61659-131">[Formatar o texto em uma caixa de texto &#40;Construtor de Relatórios e SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61659-131">[Format Text in a Text Box &#40;Report Builder and SSRS&#41;](format-text-in-a-text-box-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="61659-132">Caixa de diálogo Preenchimento &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="61659-132">Fill Dialog Box &#40;Report Builder and SSRS&#41;</span></span>](../fill-dialog-box-report-builder-and-ssrs.md)  
  
  
