---
title: Formatando intervalos de um medidor (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ffdec8ca-3e95-41cd-850b-9e8c83be4b49
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29574c58eef6f18d685b48dd8d695a5fc42c3e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678619"
---
# <a name="formatting-ranges-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="61213-102">Formatando intervalos de um medidor (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="61213-102">Formatting Ranges on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="61213-103">Um intervalo de medidor é uma zona ou área na escala de medidor que indica uma subseção importante de valores no medidor.</span><span class="sxs-lookup"><span data-stu-id="61213-103">A gauge range is a zone or area on the gauge scale that indicates an important subsection of values on the gauge.</span></span> <span data-ttu-id="61213-104">Usando um intervalo de medidor, é possível indicar visualmente quando o valor de ponteiro entrou em um determinado conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="61213-104">Using a gauge range, you can visually indicate when the pointer value has gone into a certain span of values.</span></span> <span data-ttu-id="61213-105">Intervalos são definidos por um valor inicial e um valor final.</span><span class="sxs-lookup"><span data-stu-id="61213-105">Ranges are defined by a start value and an end value.</span></span>  
  
 <span data-ttu-id="61213-106">Você também pode usar intervalos para definir seções diferentes de um medidor.</span><span class="sxs-lookup"><span data-stu-id="61213-106">You can also use ranges to define different sections of a gauge.</span></span> <span data-ttu-id="61213-107">Por exemplo, em um medidor com valores entre 0 e 10, é possível definir um intervalo vermelho com valor entre 0 e 3, um amarelo com intervalo entre 4 e 7 e um verde com intervalo entre 8 e 10.</span><span class="sxs-lookup"><span data-stu-id="61213-107">For example, on a gauge with values from 0 to 10, you can define a red range that has a value from 0 to 3, a yellow range that has a value from 4 to 7 and a green range that has a value from 8 to 10.</span></span> <span data-ttu-id="61213-108">Caso o valor inicial especificado seja maior que o valor final, os valores são trocados para que o inicial seja o final e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="61213-108">If the start value that you specified is greater than the end value that you specified, the values are swapped so that the start value is the end value and the end value is the start value.</span></span>  
  
 <span data-ttu-id="61213-109">É possível posicionar o intervalo da mesma forma que posiciona ponteiros em uma escala.</span><span class="sxs-lookup"><span data-stu-id="61213-109">You can position the range in the same way that you position pointers on a scale.</span></span> <span data-ttu-id="61213-110">As propriedades **Posição** e **Distância da escala** determinam a posição do intervalo.</span><span class="sxs-lookup"><span data-stu-id="61213-110">The **Position** and **Distance from scale** properties determine the position of the range.</span></span> <span data-ttu-id="61213-111">Para obter mais informações, consulte [Medidores &#40;Construtor de Relatórios e SSRS&#41;](gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="61213-111">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](gauges-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61213-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61213-112">See Also</span></span>  
 <span data-ttu-id="61213-113">[Formatando escalas em um medidor &#40;Construtor de Relatórios e SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61213-113">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="61213-114">[Formatando ponteiros de um medidor &#40;Construtor de Relatórios e SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61213-114">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="61213-115">[Definir mínimo ou máximo em um medidor &#40;Construtor de Relatórios e SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="61213-115">[Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="61213-116">[Tutorial: Adicionando um KPI ao relatório &#40;Construtor de Relatórios&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="61213-116">[Tutorial: Adding a KPI to Your Report &#40;Report Builder&#41;](../tutorial-adding-a-kpi-to-your-report-report-builder.md) </span></span>  
 [<span data-ttu-id="61213-117">Medidores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="61213-117">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
