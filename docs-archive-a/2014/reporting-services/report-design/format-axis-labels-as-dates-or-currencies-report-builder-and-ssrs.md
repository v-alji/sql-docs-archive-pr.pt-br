---
title: Formatar rótulos de eixo como datas ou moedas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9a01a74-2f51-4b35-be3a-a6138568f6cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ffe9d903a2271db95d4b1c2ef6201d2b0f3edab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572390"
---
# <a name="format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs"></a><span data-ttu-id="b2b0f-102">Formatar rótulos de eixo como datas ou moedas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b2b0f-102">Format Axis Labels as Dates or Currencies (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b2b0f-103">Quando você mostrar os valores DateTime formatados corretamente em um eixo, um gráfico exibirá automaticamente esses valores como dias.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-103">When you show properly formatted DateTime values on an axis, a chart will automatically display these values as days.</span></span> <span data-ttu-id="b2b0f-104">Para especificar um intervalo de data/hora para o eixo x, como um intervalo de meses ou de horas, você deverá formatar os rótulos dos eixos e definir o tipo de intervalo de eixo para um intervalo de data ou hora válido.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-104">To specify a date/time interval for the x-axis, such as an interval of months or an interval of hours, you must format the axis labels and set the type of axis interval to a valid date or time interval.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b2b0f-105">Nos gráficos de coluna e de dispersão, o eixo horizontal, ou eixo x, é o eixo de categoria.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-105">In column and scatter charts, the horizontal, or x-axis, is the category axis.</span></span> <span data-ttu-id="b2b0f-106">Em gráficos de barras, o eixo vertical, ou eixo y, é o eixo de categoria.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-106">In bar charts, the vertical, or y-axis, is the category axis.</span></span>  
  
 <span data-ttu-id="b2b0f-107">Para formatar os intervalos de tempo corretamente, os valores exibidos no eixo x deverão ser avaliados para um tipo de dados <xref:System.DateTime> .</span><span class="sxs-lookup"><span data-stu-id="b2b0f-107">In order to format time intervals correctly, the values displayed on the x-axis must evaluate to a <xref:System.DateTime> data type.</span></span> <span data-ttu-id="b2b0f-108">Se seu campo tiver um tipo de dados <xref:System.String>, o gráfico não calculará os intervalos como datas ou horas.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-108">If your field has a data type of <xref:System.String>, the chart will not calculate intervals as dates or times.</span></span> <span data-ttu-id="b2b0f-109">Para obter mais informações, consulte [Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b2b0f-109">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="b2b0f-110">Quando um valor numérico for adicionado ao eixo Y, por padrão, o gráfico não formatará o número antes de exibi-lo.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-110">When a numeric value is added to the y-axis, by default, the chart does not format the number before displaying it.</span></span> <span data-ttu-id="b2b0f-111">Se seu campo numérico for um valor de vendas, considere formatar os números como moedas para aumentar a legibilidade do gráfico.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-111">If your numeric field is a sales figure, consider formatting the numbers as currencies to increase the readability of the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-format-x-axis-labels-as-monthly-intervals"></a><span data-ttu-id="b2b0f-112">Para formatar os rótulos do eixo x como intervalos mensais</span><span class="sxs-lookup"><span data-stu-id="b2b0f-112">To format x-axis labels as monthly intervals</span></span>  
  
1.  <span data-ttu-id="b2b0f-113">Clique com o botão direito do mouse no eixo x, ou horizontal, do gráfico e selecione **Propriedades HorizontalAxis**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-113">Right-click the horizontal, or x-axis, of the chart, and select **HorizontalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="b2b0f-114">Na caixa de diálogo **Propriedades HorizontalAxis** , selecione **Número**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-114">In the **HorizontalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="b2b0f-115">Na lista de **Categorias** , selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-115">From the **Category** list, select **Date**.</span></span> <span data-ttu-id="b2b0f-116">Na lista **Tipo** , selecione um formato de data a ser aplicado nos rótulos do eixo x.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-116">From the **Type** list, select a date format to apply to the x-axis labels.</span></span>  
  
4.  <span data-ttu-id="b2b0f-117">Selecione **Opções de Eixo**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-117">Select **Axis Options.**</span></span>  
  
5.  <span data-ttu-id="b2b0f-118">Em **Intervalo**, digite **1**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-118">In **Interval**, type **1**.</span></span> <span data-ttu-id="b2b0f-119">Na propriedade **Interval type** , selecione **Meses**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-119">In **Interval type** property, select **Months**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b2b0f-120">Se você não especificar um tipo de intervalo, o gráfico calculará os intervalos em termos de dias.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-120">If you do not specify an interval type, the chart will calculate intervals in terms of days.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-format-y-axis-labels-using-a-currency-format"></a><span data-ttu-id="b2b0f-121">Para formatar os rótulos do eixo y usando um formato de conversor de moedas</span><span class="sxs-lookup"><span data-stu-id="b2b0f-121">To format y-axis labels using a currency format</span></span>  
  
1.  <span data-ttu-id="b2b0f-122">Clique com o botão direito do mouse no eixo vertical, ou eixo y, do gráfico e selecione **Propriedades VerticalAxis**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-122">Right-click the vertical, or y-axis, of the chart, and select **VerticalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="b2b0f-123">Na caixa de diálogo **Propriedades VerticalAxis** , selecione **Número**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-123">In the **VerticalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="b2b0f-124">Na lista de **Categorias** , selecione **Conversor de Moedas**.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-124">From the **Category** list, select **Currency**.</span></span> <span data-ttu-id="b2b0f-125">Na lista **Símbolo** , selecione um formato de moeda a ser aplicado nos rótulos do eixo Y.</span><span class="sxs-lookup"><span data-stu-id="b2b0f-125">From the **Symbol** list, select a currency format to apply to the y-axis labels.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b2b0f-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2b0f-126">See Also</span></span>  
 <span data-ttu-id="b2b0f-127">[Formatando rótulos dos eixos de um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b2b0f-127">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b2b0f-128">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b2b0f-128">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b2b0f-129">[Especificar uma escala logarítmica &#40;Construtor de Relatórios e SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b2b0f-129">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b2b0f-130">Especificar um intervalo do eixo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b2b0f-130">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
