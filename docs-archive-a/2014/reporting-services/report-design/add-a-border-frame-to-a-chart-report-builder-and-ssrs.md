---
title: Adicionar um quadro de borda a um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ca0c5040-40bb-4cb7-bc2b-5bcbe73858bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c91d3de00caa4eab6ed1894042b2214b7dcf4b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684549"
---
# <a name="add-a-border-frame-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="14139-102">Adicionar uma moldura de borda a um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="14139-102">Add a Border Frame to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="14139-103">Para aumentar o impacto visual de um gráfico, considere a possibilidade de usar uma moldura de borda em volta da parte exterior do gráfico.</span><span class="sxs-lookup"><span data-stu-id="14139-103">To give a chart more visual impact, consider using a border frame around the outside of the chart.</span></span> <span data-ttu-id="14139-104">Para selecionar um quadro de borda, use a caixa de diálogo **Propriedades do Gráfico** ou o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="14139-104">You can select a border frame by using the **Chart Properties** dialog box or by using the Properties pane.</span></span> <span data-ttu-id="14139-105">As molduras de borda de gráficos não podem ser aplicadas a nenhuma outra região de dados.</span><span class="sxs-lookup"><span data-stu-id="14139-105">The chart border frames cannot be applied to any other data region.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-a-border-to-a-chart"></a><span data-ttu-id="14139-106">Para aplicar uma borda a um gráfico</span><span class="sxs-lookup"><span data-stu-id="14139-106">To apply a border to a chart</span></span>  
  
1.  <span data-ttu-id="14139-107">Clique no gráfico com o botão direito do mouse e selecione **Propriedades do Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="14139-107">Right-click anywhere on the chart and select **Chart Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14139-108">Se você não vir as **Propriedades do Gráfico**, aponte para **Gráfico** no menu de atalho e selecione **Propriedades do Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="14139-108">If you do not see the **Chart Properties**, point to **Chart** on the shortcut menu and select **Chart Properties**.</span></span>  
  
2.  <span data-ttu-id="14139-109">Selecione **Borda**e clique no tipo de borda que deseja aplicar ao gráfico.</span><span class="sxs-lookup"><span data-stu-id="14139-109">Select **Border**, and click the type of border to apply to the chart.</span></span>  
  
3.  <span data-ttu-id="14139-110">(Opcional) Selecione um valor ou digite uma expressão que represente o estilo da borda.</span><span class="sxs-lookup"><span data-stu-id="14139-110">(Optional) Select a value or type an expression that represents the style of the border.</span></span>  
  
4.  <span data-ttu-id="14139-111">(Opcional) Especifique a cor da linha que será desenhada em torno do gráfico como borda.</span><span class="sxs-lookup"><span data-stu-id="14139-111">(Optional) Specify the color of the line that will be drawn around the chart as the border.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14139-112">A lista **Cor da linha** contém cores comuns.</span><span class="sxs-lookup"><span data-stu-id="14139-112">The **Line color** list contains common colors.</span></span> <span data-ttu-id="14139-113">Para selecionar opções de uma lista com mais cores, clique em **Mais cores** na lista ou clique no botão de expressão (**fx**), ao lado da lista, para ativar o editor **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="14139-113">If you want to select from a list of more colors, click **More colors** in the list or click the expression (**fx**) button next to the list to bring up the **Expression** editor.</span></span>  
  
5.  <span data-ttu-id="14139-114">(Opcional) Especifique a largura da borda.</span><span class="sxs-lookup"><span data-stu-id="14139-114">(Optional) Specify the width of the border.</span></span> <span data-ttu-id="14139-115">Os valores válidos vão de 0,25 pt a 20 pt.</span><span class="sxs-lookup"><span data-stu-id="14139-115">Valid values are between 0.25pt and 20pt.</span></span> <span data-ttu-id="14139-116">Considere manter o tamanho da borda entre 1 pt e 3 pt para causar um efeito visual melhor.</span><span class="sxs-lookup"><span data-stu-id="14139-116">Consider keeping the size of your border to between 1 and 3pt for the best visual effect.</span></span>  
  
6.  <span data-ttu-id="14139-117">(Opcional) Se a cor do plano de fundo do relatório for diferente de branco, considere definir uma cor de página igual a essa cor.</span><span class="sxs-lookup"><span data-stu-id="14139-117">(Optional) If your report contains a background color other than white, consider defining a page color that is the same color.</span></span> <span data-ttu-id="14139-118">A cor de página é a cor do plano de fundo fora da linha da borda.</span><span class="sxs-lookup"><span data-stu-id="14139-118">The page color is the background color outside of the border line.</span></span>  
  
7.  <span data-ttu-id="14139-119">(Opcional) Se você escolher um tipo de borda, especifique um estilo e uma cor para ela.</span><span class="sxs-lookup"><span data-stu-id="14139-119">(Optional) If you choose a Frame type, specify a style and color for the frame.</span></span> <span data-ttu-id="14139-120">A lista **Cor do preenchimento do quadro** contém cores comuns.</span><span class="sxs-lookup"><span data-stu-id="14139-120">The **Frame fill color** list contains common colors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14139-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="14139-121">See Also</span></span>  
 <span data-ttu-id="14139-122">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14139-122">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="14139-123">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="14139-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="14139-124">Adicionar estilos de bisel, alto-relevo e textura a um gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="14139-124">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
