---
title: Especificar uma escala logarítmica (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f3092c1c-b128-433d-9a95-983508b2a8d4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cc422a6f95a420445dc604d08a23e8f8e65c95d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569073"
---
# <a name="specify-a-logarithmic-scale-report-builder-and-ssrs"></a><span data-ttu-id="80861-102">Especificar uma escala logarítmica (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="80861-102">Specify a Logarithmic Scale (Report Builder and SSRS)</span></span>
  <span data-ttu-id="80861-103">Se você tiver dados que sejam logaritmicamente proporcionais, é recomendável usar uma escala logarítmica no gráfico.</span><span class="sxs-lookup"><span data-stu-id="80861-103">If you have data that is logarithmically proportional, you may want to consider using a logarithmic scale on the chart.</span></span> <span data-ttu-id="80861-104">Isso ajuda a melhorar a aparência do gráfico tornando seus dados mais gerenciáveis.</span><span class="sxs-lookup"><span data-stu-id="80861-104">This helps improve the appearance of the chart by making your data more manageable.</span></span> <span data-ttu-id="80861-105">A maioria das escalas logarítmicas usa uma base de 10.</span><span class="sxs-lookup"><span data-stu-id="80861-105">Most logarithmic scales use a base of 10.</span></span>  
  
 <span data-ttu-id="80861-106">Esse recurso está disponível somente no eixo de valor.</span><span class="sxs-lookup"><span data-stu-id="80861-106">This feature is only available on the value axis.</span></span> <span data-ttu-id="80861-107">Geralmente, o eixo de valor é o eixo vertical, ou eixo y.</span><span class="sxs-lookup"><span data-stu-id="80861-107">The value axis is usually the vertical, or y-axis.</span></span> <span data-ttu-id="80861-108">No entanto, em gráficos de barras, ele é o eixo horizontal, ou eixo x.</span><span class="sxs-lookup"><span data-stu-id="80861-108">On bar charts, however, it is the horizontal, or x-axis.</span></span>  
  
 <span data-ttu-id="80861-109">Se seu eixo for logarítmico, todas as outras propriedades relacionadas ao eixo serão logaritmicamente escaladas.</span><span class="sxs-lookup"><span data-stu-id="80861-109">If your axis is logarithmic, all other properties relating to the axis will be scaled logarithmically.</span></span> <span data-ttu-id="80861-110">Por exemplo, se você especificar uma escala logarítmica de base 10 em seu eixo, definir um intervalo de eixo de 2 gerará intervalos em magnitudes de 10 para a potência de 2 ou 100.</span><span class="sxs-lookup"><span data-stu-id="80861-110">For example, if you specify a base-10 logarithmic scale on your axis, setting an axis interval of 2 will generate intervals in magnitudes of 10 to the power of 2, or 100.</span></span> <span data-ttu-id="80861-111">Isso significa que os valores do eixo lerão 1, 100, 10.000, em vez do resultado padrão de 1, 10, 100, 1.000, 10.000.</span><span class="sxs-lookup"><span data-stu-id="80861-111">This means your axis values will read 1, 100, 10000, instead of the default result of 1, 10, 100, 1000, 10000.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-logarithmic-scale"></a><span data-ttu-id="80861-112">Para especificar uma escala logarítmica</span><span class="sxs-lookup"><span data-stu-id="80861-112">To specify a logarithmic scale</span></span>  
  
1.  <span data-ttu-id="80861-113">Clique com o botão direito do mouse no eixo y de seu gráfico e clique em **Propriedades VerticalAxis**.</span><span class="sxs-lookup"><span data-stu-id="80861-113">Right-click the y-axis of your chart, and click **VerticalAxis Properties**.</span></span> <span data-ttu-id="80861-114">A caixa de diálogo **Propriedades VerticalAxis** aparece.</span><span class="sxs-lookup"><span data-stu-id="80861-114">The **VerticalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="80861-115">Em **Opções de Eixo**, selecione **Escala Uselogarithmic**.</span><span class="sxs-lookup"><span data-stu-id="80861-115">In **Axis Options**, select **Uselogarithmic scale**.</span></span>  
  
3.  <span data-ttu-id="80861-116">Na caixa de texto **Base de log** , digite um valor positivo para a base logarítmica.</span><span class="sxs-lookup"><span data-stu-id="80861-116">In the **Logbase** text box, type a positive value for the logarithmic base.</span></span> <span data-ttu-id="80861-117">Se nenhum valor for especificado, a base logarítmica assumirá 10 como padrão.</span><span class="sxs-lookup"><span data-stu-id="80861-117">If no value is specified, the logarithmic base defaults to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80861-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="80861-118">See Also</span></span>  
 <span data-ttu-id="80861-119">[Formatando rótulos dos eixos de um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80861-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="80861-120">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80861-120">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="80861-121">[Formatar rótulos de eixo como datas ou moedas &#40;Construtor de Relatórios e SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80861-121">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="80861-122">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="80861-122">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
