---
title: Definir cores em um gráfico usando uma paleta (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d95efc22-5a32-43d4-9bd2-12753e7fd395
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7db137ed87b0c84e43577dcf2936a6287abd8e36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573746"
---
# <a name="define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs"></a><span data-ttu-id="8703f-102">Definir cores em um gráfico usando uma paleta (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="8703f-102">Define Colors on a Chart Using a Palette (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8703f-103">Você pode alterar a paleta de cores para um gráfico, selecionando uma paleta predefinida ou definindo uma paleta personalizada.</span><span class="sxs-lookup"><span data-stu-id="8703f-103">You can change the color palette for a chart by selecting a pre-defined palette or defining a custom palette.</span></span> <span data-ttu-id="8703f-104">Paletas personalizadas são específicas para relatórios.</span><span class="sxs-lookup"><span data-stu-id="8703f-104">Custom palettes are report-specific.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-colors-on-the-chart-using-a-built-in-color-palette"></a><span data-ttu-id="8703f-105">Para alterar as cores no gráfico usando uma paleta de cores interna</span><span class="sxs-lookup"><span data-stu-id="8703f-105">To change the colors on the chart using a built-in color palette</span></span>  
  
1.  <span data-ttu-id="8703f-106">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="8703f-106">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="8703f-107">Na superfície de design, clique no gráfico.</span><span class="sxs-lookup"><span data-stu-id="8703f-107">On the design surface, click the chart.</span></span> <span data-ttu-id="8703f-108">São exibidas as propriedades do objeto de gráfico no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="8703f-108">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
     <span data-ttu-id="8703f-109">O nome do objeto (**Chart1** por padrão) é exibido na lista suspensa na parte superior do painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="8703f-109">The object name (**Chart1** by default) appears in the drop-down list at the top of the Properties pane.</span></span>  
  
3.  <span data-ttu-id="8703f-110">Na seção **Gráfico** , da propriedade Palette, selecione uma paleta nova na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8703f-110">In the **Chart** section, for the Palette property, select a new palette from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8703f-111">Você não pode alterar as cores nem classificar em uma paleta predefinida.</span><span class="sxs-lookup"><span data-stu-id="8703f-111">You cannot change the colors or order in a pre-defined palette.</span></span>  
  
### <a name="to-define-your-own-colors-on-the-chart-using-a-custom-color-palette"></a><span data-ttu-id="8703f-112">Para definir suas próprias cores no gráfico usando uma paleta de cores personalizada</span><span class="sxs-lookup"><span data-stu-id="8703f-112">To define your own colors on the chart using a custom color palette</span></span>  
  
1.  <span data-ttu-id="8703f-113">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="8703f-113">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="8703f-114">Na superfície de design, clique no gráfico.</span><span class="sxs-lookup"><span data-stu-id="8703f-114">On the design surface, click the chart.</span></span> <span data-ttu-id="8703f-115">São exibidas as propriedades do objeto de gráfico no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="8703f-115">The properties for the chart object are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="8703f-116">Na seção **gráfico** , para a `Palette` propriedade, selecione **personalizado**.</span><span class="sxs-lookup"><span data-stu-id="8703f-116">In the **Chart** section, for the `Palette` property, select **Custom**.</span></span>  
  
4.  <span data-ttu-id="8703f-117">Na propriedade CustomPaletteColors, clique no botão Editar Coleção ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="8703f-117">In the CustomPaletteColors property, click the Edit Collection (**...**) button.</span></span> <span data-ttu-id="8703f-118">O **Editor de Coleção ReportColorExpression** é aberto.</span><span class="sxs-lookup"><span data-stu-id="8703f-118">The **ReportColorExpression Collection Editor** opens.</span></span>  
  
5.  <span data-ttu-id="8703f-119">Clique em **Adicionar** para adicionar uma cor.</span><span class="sxs-lookup"><span data-stu-id="8703f-119">Click **Add** to add a color.</span></span> <span data-ttu-id="8703f-120">Selecione uma cor na lista suspensa ou selecione Expressão e especifique um valor hexadecimal para uma cor específica, como ff6600 para "Laranja".</span><span class="sxs-lookup"><span data-stu-id="8703f-120">Select a color from the drop-down list or select Expression and specify a hex value for a specific color, such as ff6600 for "Orange".</span></span>  
  
     <span data-ttu-id="8703f-121">Para obter mais informações sobre valores hexadecimais, consulte [Tabela de Cores](https://go.microsoft.com/fwlink/?linkid=9258) n MSDN.</span><span class="sxs-lookup"><span data-stu-id="8703f-121">For more information about hex values, see [Color Table](https://go.microsoft.com/fwlink/?linkid=9258) on MSDN.</span></span>  
  
6.  <span data-ttu-id="8703f-122">Clique em **Adicionar** para adicionar mais cores à paleta.</span><span class="sxs-lookup"><span data-stu-id="8703f-122">Click **Add** to add more colors to the palette.</span></span>  
  
7.  <span data-ttu-id="8703f-123">Após concluir, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8703f-123">When you are done, click **OK**.</span></span>  
  
 <span data-ttu-id="8703f-124">Se você estiver usando uma paleta personalizada, poderá alterar a ordem das cores para alterar a cor de séries diferentes no gráfico.</span><span class="sxs-lookup"><span data-stu-id="8703f-124">If you are using a custom palette, you can change the order of the colors to change the color of different series in the chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8703f-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8703f-125">See Also</span></span>  
 <span data-ttu-id="8703f-126">[Formatando as cores da série em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8703f-126">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8703f-127">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8703f-127">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8703f-128">Especificar cores consistentes em gráficos com várias formas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8703f-128">Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;</span></span>](shape-charts-report-builder-and-ssrs.md)  
  
  
