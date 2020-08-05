---
title: Adicionar uma média móvel a um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166cf9c1-0750-4866-8381-542e4fbfe65a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bc16d0cb45a3240148f931009a836c231b442b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569100"
---
# <a name="add-a-moving-average-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="18b00-102">Adicionar uma média móvel a um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="18b00-102">Add a Moving Average to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="18b00-103">Uma média móvel é uma média dos dados na série, calculada em um período de tempo definido.</span><span class="sxs-lookup"><span data-stu-id="18b00-103">A moving average is an average of the data in your series, calculated over a defined period of time.</span></span> <span data-ttu-id="18b00-104">A média móvel pode ser mostrada no gráfico para identificar tendências significativas.</span><span class="sxs-lookup"><span data-stu-id="18b00-104">The moving average can be shown on the chart to identify significant trends.</span></span>  
  
 <span data-ttu-id="18b00-105">A fórmula Média Móvel é o indicador de preço mais popular usado em análises técnicas.</span><span class="sxs-lookup"><span data-stu-id="18b00-105">The Moving Average formula is the most popular price indicator used in technical analyses.</span></span> <span data-ttu-id="18b00-106">Muitas outras fórmulas, incluindo desvio médio, mediano e padrão, também podem ser derivadas de uma série no gráfico.</span><span class="sxs-lookup"><span data-stu-id="18b00-106">Many other formulas, including mean, median and standard deviation, can also be derived from a series on the chart.</span></span> <span data-ttu-id="18b00-107">Ao especificar uma média móvel, cada fórmula pode ter um ou mais parâmetros que devem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="18b00-107">When specifying a moving average, each formula may have one or more parameters that must be specified.</span></span>  
  
 <span data-ttu-id="18b00-108">Quando uma fórmula de média móvel é adicionada em Modo de design, a série de linhas adicionada é apenas um espaço reservado visual.</span><span class="sxs-lookup"><span data-stu-id="18b00-108">When a moving average formula is added in Design mode, the line series that is added is only a visual placeholder.</span></span> <span data-ttu-id="18b00-109">O gráfico calcula os pontos de dados de cada fórmula durante o processamento de relatório.</span><span class="sxs-lookup"><span data-stu-id="18b00-109">The chart will calculate the data points of each formula during report processing.</span></span>  
  
 <span data-ttu-id="18b00-110">O suporte interno para linhas de tendência não está disponível no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18b00-110">Built-in support for trend lines is not available in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-calculated-moving-average-to-a-series-on-the-chart"></a><span data-ttu-id="18b00-111">Para adicionar uma média móvel calculada a uma série no gráfico</span><span class="sxs-lookup"><span data-stu-id="18b00-111">To add a calculated moving average to a series on the chart</span></span>  
  
1.  <span data-ttu-id="18b00-112">Clique com o botão direito do mouse na área **Valores** e clique em **Adicionar Série Calculada**.</span><span class="sxs-lookup"><span data-stu-id="18b00-112">Right-click on a field in the **Values** area and click **Add Calculated Series**.</span></span> <span data-ttu-id="18b00-113">A caixa de diálogo **Propriedades da Série Calculada** é exibida.</span><span class="sxs-lookup"><span data-stu-id="18b00-113">The **Calculated Series Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="18b00-114">Selecione a opção **Média Móvel** na lista suspensa **Fórmula** .</span><span class="sxs-lookup"><span data-stu-id="18b00-114">Select the **Moving average** option from the **Formula** drop-down list.</span></span>  
  
3.  <span data-ttu-id="18b00-115">Especifique um valor inteiro para o **Período** que representa o período da média móvel.</span><span class="sxs-lookup"><span data-stu-id="18b00-115">Specify an integer value for the **Period** that represents the period of the moving average.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18b00-116">O período é o número de dias usado para calcular uma média móvel.</span><span class="sxs-lookup"><span data-stu-id="18b00-116">The period is the number of days used to calculate a moving average.</span></span> <span data-ttu-id="18b00-117">Se os valores de data/hora não forem especificados no eixo x, o período será representado pelo número de pontos de dados usados para calcular uma média móvel.</span><span class="sxs-lookup"><span data-stu-id="18b00-117">If date/time values are not specified on the x-axis, the period is represented by the number of data points used to calculate a moving average.</span></span> <span data-ttu-id="18b00-118">Se houver apenas um ponto de dados, a fórmula da média móvel não será calculada.</span><span class="sxs-lookup"><span data-stu-id="18b00-118">If there is only one data point, the moving average formula does not calculate.</span></span> <span data-ttu-id="18b00-119">A média móvel é calculada a partir do segundo ponto.</span><span class="sxs-lookup"><span data-stu-id="18b00-119">The moving average is calculated starting at the second point.</span></span> <span data-ttu-id="18b00-120">Se a opção **Iniciar no primeiro ponto** estiver especificada, o gráfico iniciará a média móvel no primeiro ponto.</span><span class="sxs-lookup"><span data-stu-id="18b00-120">If you specify the **Start from first point** option, the chart will start the moving average at the first point.</span></span> <span data-ttu-id="18b00-121">Se houver apenas um ponto de dados, o ponto na média móvel calculada será idêntico ao primeiro ponto na série original.</span><span class="sxs-lookup"><span data-stu-id="18b00-121">If there is only one data point, the point in the calculated moving average will be identical to the first point in your original series.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b00-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18b00-122">See Also</span></span>  
 <span data-ttu-id="18b00-123">[Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18b00-123">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="18b00-124">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="18b00-124">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="18b00-125">Adicionar pontos vazios ao gráfico &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="18b00-125">Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;</span></span>](add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
  
