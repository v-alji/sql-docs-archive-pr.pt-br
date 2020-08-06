---
title: Alterar um tipo de gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fff24978-e3bd-4fac-8cd7-d6aa81f3cc25
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb466bed475b27206bf6837a60d0867f5fb745be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678639"
---
# <a name="change-a-chart-type-report-builder-and-ssrs"></a><span data-ttu-id="d4c8f-102">Alterar um tipo de gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="d4c8f-102">Change a Chart Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d4c8f-103">Quando você insere um gráfico pela primeira vez em um relatório, a caixa de diálogo **Selecionar tipo de gráfico** é exibida.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-103">When you first insert a chart into a report, the **Select Chart Type** dialog appears.</span></span> <span data-ttu-id="d4c8f-104">Se você cancelar essa caixa de diálogo, um tipo de gráfico Coluna será adicionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-104">If you cancel this dialog, a Column chart type is added by default.</span></span>  
  
 <span data-ttu-id="d4c8f-105">A qualquer momento durante a criação do relatório, é possível alterar o tipo de gráfico para aquele mais adequado ao relatório.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-105">At any point when designing the report, you can change the chart type to something more suitable to the report.</span></span> <span data-ttu-id="d4c8f-106">É importante escolher o tipo de gráfico correto para o tipo de dados para que ele seja interpretado corretamente.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-106">It is important to select the correct chart type for your data so that it can be interpreted correctly.</span></span> <span data-ttu-id="d4c8f-107">Você deve entender as características de cada tipo de gráfico para determinar qual deles é o mais adequado para seus dados.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-107">You should understand each chart type's characteristics to determine what chart type is best suited for your data.</span></span> <span data-ttu-id="d4c8f-108">Para obter mais informações, consulte [Tipos de gráficos &#40;Construtor de Relatórios e SSRS&#41;](chart-types-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d4c8f-108">For more information, see [Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="d4c8f-109">Se houver várias séries exibidas em um gráfico, talvez você deseje alterar o tipo de gráfico de uma série individual.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-109">When multiple series are displayed on a chart, you may want to change the chart type of an individual series.</span></span> <span data-ttu-id="d4c8f-110">Só será possível alterar o tipo de gráfico de uma série se o tipo de gráfico for Área, Coluna, Linha ou Dispersão.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-110">You can only change the chart type of an individual series if the chart type is Area, Column, Line, or Scatter.</span></span> <span data-ttu-id="d4c8f-111">Para todos os outros tipos de gráfico, todas as séries do gráfico serão alteradas para o tipo de gráfico selecionado.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-111">For all other chart types, all series in your chart will be changed to the selected chart type.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-chart-type"></a><span data-ttu-id="d4c8f-112">Para alterar o tipo de gráfico</span><span class="sxs-lookup"><span data-stu-id="d4c8f-112">To change the chart type</span></span>  
  
1.  <span data-ttu-id="d4c8f-113">No modo de exibição de Design, clique com o botão direito do mouse no gráfico e clique em **Alterar Tipo de Gráfico**.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-113">In Design view, right-click the chart and then click **Change Chart Type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d4c8f-114">Se houver várias séries exibidas em um gráfico, clique com o botão direito do mouse na série que você deseja alterar e não no gráfico.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-114">When there are multiple series on a chart, you must right-click on the series, not the chart, which you want to change.</span></span>  
  
2.  <span data-ttu-id="d4c8f-115">Na caixa de diálogo **Tipo SelectChart** , selecione um tipo de gráfico na lista.</span><span class="sxs-lookup"><span data-stu-id="d4c8f-115">In the **SelectChart Type** dialog box, select a chart type from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c8f-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4c8f-116">See Also</span></span>  
 <span data-ttu-id="d4c8f-117">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d4c8f-117">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d4c8f-118">[Medidores &#40;Construtor de Relatórios e SSRS&#41;](gauges-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d4c8f-118">[Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d4c8f-119">Adicionar um gráfico a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d4c8f-119">Add a Chart to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-chart-to-a-report-report-builder-and-ssrs.md)  
  
  
