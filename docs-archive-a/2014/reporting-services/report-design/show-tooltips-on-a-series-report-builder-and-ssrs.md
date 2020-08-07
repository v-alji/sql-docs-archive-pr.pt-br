---
title: Mostrar ToolTips em uma série (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4c9606ff-e1c3-4cf7-a4e7-bb16f1a9e8ab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9113ec843b3b9255f380b17ee1ab6b360fa1f60d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582292"
---
# <a name="show-tooltips-on-a-series-report-builder-and-ssrs"></a><span data-ttu-id="e8f74-102">Mostrar dicas de ferramenta em uma série (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e8f74-102">Show ToolTips on a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e8f74-103">É possível adicionar uma dica de ferramenta a cada ponto de dados na série de um gráfico para exibir as informações relacionadas ao ponto de dados como, por exemplo, o nome do grupo, o valor do ponto de dados ou a porcentagem do ponto de dados em relação ao total de série quando os usuários passam pelo ponto de dados em um relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="e8f74-103">You can add a ToolTip to each data point on the series of a chart to display information related to the data point, such as the group name, the value of the data point, or the percentage of the data point relative to the series total when users hover over the data point in a rendered report.</span></span>  
  
 <span data-ttu-id="e8f74-104">Você não pode adicionar uma dica de ferramenta a uma série calculada.</span><span class="sxs-lookup"><span data-stu-id="e8f74-104">You cannot add a ToolTip to a calculated series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-tooltip-on-each-data-point"></a><span data-ttu-id="e8f74-105">Para especificar uma dica de ferramenta em cada ponto de dados</span><span class="sxs-lookup"><span data-stu-id="e8f74-105">To specify a ToolTip on each data point</span></span>  
  
1.  <span data-ttu-id="e8f74-106">Clique com o botão direito do mouse em uma série ou em um campo na área **Valores** e clique em **Propriedades da Série**.</span><span class="sxs-lookup"><span data-stu-id="e8f74-106">Right-click on the series or right-click on the field in the **Values** area, and click **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="e8f74-107">Clique em **Dados da Série** e, para a propriedade **ToolTip** digite uma cadeia de caracteres ou expressão.</span><span class="sxs-lookup"><span data-stu-id="e8f74-107">Click **Series Data** and, for the **ToolTip** property, type in a string or expression.</span></span> <span data-ttu-id="e8f74-108">É possível usar qualquer palavra-chave de um gráfico específico para representar outro elemento no gráfico.</span><span class="sxs-lookup"><span data-stu-id="e8f74-108">You can use any chart-specific keyword to represent another element on the chart.</span></span> <span data-ttu-id="e8f74-109">Para obter mais informações, consulte [Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e8f74-109">For more information, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f74-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8f74-110">See Also</span></span>  
 <span data-ttu-id="e8f74-111">[Formatando pontos de dados em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8f74-111">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e8f74-112">[Alterar o texto de um item de legenda &#40;Construtor de Relatórios e SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="e8f74-112">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="e8f74-113">[Formatando as cores da série em um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8f74-113">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e8f74-114">Adicionar uma ação de detalhamento a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e8f74-114">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
