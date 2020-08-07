---
title: Adicionar estilos de bisel, auto-relevo e textura a um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 737cfc80-b39e-497c-817b-b46693deb58f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 92c5d4af47b7889b9ba5ec421706848f8822075b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582317"
---
# <a name="add-bevel-emboss-and-texture-styles-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="2f63c-102">Adicionar estilos de inclinação, relevo e textura a um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2f63c-102">Add Bevel, Emboss, and Texture Styles to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2f63c-103">Ao usar determinados tipos de gráficos, você pode especificar um efeito de desenho para aumentar o impacto visual do seu gráfico.</span><span class="sxs-lookup"><span data-stu-id="2f63c-103">When using certain chart types, you can specify a drawing effect to increase the visual impact of your chart.</span></span> <span data-ttu-id="2f63c-104">Esses efeitos de desenho só são aplicados à série de seu gráfico.</span><span class="sxs-lookup"><span data-stu-id="2f63c-104">These drawing effects are only applied to the series of your chart.</span></span> <span data-ttu-id="2f63c-105">Eles não têm nenhum efeito sobre qualquer outro elemento do gráfico.</span><span class="sxs-lookup"><span data-stu-id="2f63c-105">They have no effect on any other chart element.</span></span>  
  
 <span data-ttu-id="2f63c-106">Quando você está usando qualquer variante de um gráfico de pizza ou rosca, você pode especificar uma borda suave ou um estilo de desenho côncavo, semelhante aos efeitos de inclinação e relevo que podem ser aplicados a uma imagem.</span><span class="sxs-lookup"><span data-stu-id="2f63c-106">When you are using any variant of a pie or doughnut chart, you can specify a soft edge or concave drawing style, similar to bevel or emboss effects that can be applied to an image.</span></span>  
  
 <span data-ttu-id="2f63c-107">Quando você está usando qualquer variante de um gráfico de colunas ou barras, você pode aplicar estilos de textura, como cilindro, entalhe e claro para escuro às colunas ou barras individuais.</span><span class="sxs-lookup"><span data-stu-id="2f63c-107">When you are using any variant of a bar or column chart, you can apply texture styles, such as cylinder, wedge, and light-to-dark, to the individual bars or columns.</span></span>  
  
 <span data-ttu-id="2f63c-108">Além desses estilos de desenho, você pode adicionar bordas e sombras a muitos elementos de gráfico para dar a ilusão de profundidade.</span><span class="sxs-lookup"><span data-stu-id="2f63c-108">In addition to these drawing styles, you can add borders and shadows to many chart elements to give the illusion of depth.</span></span> <span data-ttu-id="2f63c-109">Para obter mais informações sobre outras maneiras de formatar o gráfico, consulte [Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2f63c-109">For more information on other ways to format the chart, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-bevel-or-emboss-styles-to-a-pie-or-doughnut-chart"></a><span data-ttu-id="2f63c-110">Para adicionar estilos de inclinação ou relevo a um gráfico de pizza ou rosca</span><span class="sxs-lookup"><span data-stu-id="2f63c-110">To add bevel or emboss styles to a pie or doughnut chart</span></span>  
  
1.  <span data-ttu-id="2f63c-111">Na guia **Exibir** , selecione **Propriedades** para abrir o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2f63c-111">On the **View** tab, select **Properties** to open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="2f63c-112">Selecione o gráfico de pizza ou rosca que deseja aprimorar.</span><span class="sxs-lookup"><span data-stu-id="2f63c-112">Select the pie or doughnut chart that you want to enhance.</span></span> <span data-ttu-id="2f63c-113">Selecione o campo de dados no gráfico, não o gráfico inteiro.</span><span class="sxs-lookup"><span data-stu-id="2f63c-113">Select a data field in the chart, not the entire chart.</span></span>  
  
3.  <span data-ttu-id="2f63c-114">No painel Propriedades, expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="2f63c-114">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="2f63c-115">Para PieDrawingStyle, selecione um estilo na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="2f63c-115">For PieDrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f63c-116">Você não pode ter os estilos 3D e bisel ou alto-relevo no mesmo gráfico.</span><span class="sxs-lookup"><span data-stu-id="2f63c-116">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="2f63c-117">Se você habilitou 3D para o gráfico, não verá a propriedade PieDrawingStyle.</span><span class="sxs-lookup"><span data-stu-id="2f63c-117">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="2f63c-118">![Gráfico de pizza com estilo de desenho côncavo](../media/rs-piedrawingeffects-concave.gif "Gráfico de pizza com estilo de desenho côncavo")</span><span class="sxs-lookup"><span data-stu-id="2f63c-118">![Pie chart with concave drawing style](../media/rs-piedrawingeffects-concave.gif "Pie chart with concave drawing style")</span></span>  
  
### <a name="to-add-texture-styles-to-a-bar-or-column-chart"></a><span data-ttu-id="2f63c-119">Para adicionar estilos de textura a um gráfico de barras ou coluna</span><span class="sxs-lookup"><span data-stu-id="2f63c-119">To add texture styles to a bar or column chart</span></span>  
  
1.  <span data-ttu-id="2f63c-120">Selecione o gráfico de barras ou colunas que deseja aprimorar.</span><span class="sxs-lookup"><span data-stu-id="2f63c-120">Select the bar or column chart that you want to enhance.</span></span> <span data-ttu-id="2f63c-121">Selecione o campo de dados no gráfico, não o gráfico inteiro.</span><span class="sxs-lookup"><span data-stu-id="2f63c-121">Select a data field in the chart, not the entire chart.</span></span>  
  
2.  <span data-ttu-id="2f63c-122">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2f63c-122">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="2f63c-123">Expanda o nó **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="2f63c-123">Expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="2f63c-124">Para DrawingStyle, selecione um estilo na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="2f63c-124">For DrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f63c-125">Você não pode ter os estilos 3D e bisel ou alto-relevo no mesmo gráfico.</span><span class="sxs-lookup"><span data-stu-id="2f63c-125">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="2f63c-126">Se você habilitou 3D para o gráfico, não verá a propriedade PieDrawingStyle.</span><span class="sxs-lookup"><span data-stu-id="2f63c-126">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="2f63c-127">![Gráfico de barras com efeito de desenho LightToDark](../media/rs-bardrawingeffects-lighttodark.gif "Gráfico de barras com efeito de desenho LightToDark")</span><span class="sxs-lookup"><span data-stu-id="2f63c-127">![Bar chart with LightToDark drawing effect](../media/rs-bardrawingeffects-lighttodark.gif "Bar chart with LightToDark drawing effect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f63c-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f63c-128">See Also</span></span>  
 <span data-ttu-id="2f63c-129">[Gráficos de barras &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2f63c-129">[Bar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2f63c-130">[Gráficos de colunas &#40;Construtor de Relatórios e SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2f63c-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2f63c-131">[Gráficos de pizza &#40;Construtor de Relatórios e SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2f63c-131">[Pie Charts &#40;Report Builder and SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2f63c-132">Formatar um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2f63c-132">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
