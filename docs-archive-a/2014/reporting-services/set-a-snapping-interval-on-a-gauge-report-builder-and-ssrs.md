---
title: Definir um intervalo de ajuste em um medidor (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0ece7297-6e2f-47fb-835d-b9e9cce53fe2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdc2a621c4406791838d97e93f47cd32fa9d5f94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682090"
---
# <a name="set-a-snapping-interval-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="9bb77-102">Definir um intervalo de ajuste em um medidor (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9bb77-102">Set a Snapping Interval on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9bb77-103">Um intervalo de ajuste define o múltiplo para o qual os valores são arredondados.</span><span class="sxs-lookup"><span data-stu-id="9bb77-103">A snapping interval defines the multiple to which values are rounded.</span></span> <span data-ttu-id="9bb77-104">Por padrão, o medidor apontará para o valor exato do campo especificado no painel de dados.</span><span class="sxs-lookup"><span data-stu-id="9bb77-104">By default, the gauge will point to the exact value of the field you have specified in the data pane.</span></span> <span data-ttu-id="9bb77-105">No entanto, talvez você queira arredondar o valor exato para cima ou para baixo para que o ponteiro se encaixe em um intervalo predefinido.</span><span class="sxs-lookup"><span data-stu-id="9bb77-105">However, you may want to round the exact value up or down so that the pointer will snap to a preset interval.</span></span> <span data-ttu-id="9bb77-106">Por exemplo, se o valor em seu medidor for 34,2 e você especificar um intervalo de ajuste de 5, o ponteiro do medidor apontará para 35.</span><span class="sxs-lookup"><span data-stu-id="9bb77-106">For example, if the value on your gauge is 34.2 and you specify a snapping interval of 5, the gauge pointer will point to 35.</span></span> <span data-ttu-id="9bb77-107">Se o valor em seu medidor for 31,2 e você especificar um intervalo de ajuste de 5, o ponteiro do medidor apontará para 30.</span><span class="sxs-lookup"><span data-stu-id="9bb77-107">If the value on your gauge is 31.2 and you specify a snapping interval of 5, the gauge pointer will point to 30.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-a-snapping-interval-on-a-gauge"></a><span data-ttu-id="9bb77-108">Para definir um intervalo de ajuste em um medidor</span><span class="sxs-lookup"><span data-stu-id="9bb77-108">To set a snapping interval on a gauge</span></span>  
  
1.  <span data-ttu-id="9bb77-109">Clique em qualquer parte dos números do medidor para realçar a escala.</span><span class="sxs-lookup"><span data-stu-id="9bb77-109">Click anywhere on the numbers of the gauge to highlight the scale.</span></span>  
  
2.  <span data-ttu-id="9bb77-110">Abra o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="9bb77-110">Open the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9bb77-111">Se você não vir o painel Propriedades, clique na guia **Exibir** e, em seguida, marque a caixa de seleção **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="9bb77-111">If you do not see the Properties pane, click the **View** tab and then select the **Properties** checkbox.</span></span>  
  
3.  <span data-ttu-id="9bb77-112">Na propriedade **ponteiros** , clique no botão (...).</span><span class="sxs-lookup"><span data-stu-id="9bb77-112">In the **Pointers** property, click the (...) button.</span></span> <span data-ttu-id="9bb77-113">O Editor de Coleção de Ponteiros é aberto.</span><span class="sxs-lookup"><span data-stu-id="9bb77-113">The Pointer Collection Editor opens.</span></span>  
  
4.  <span data-ttu-id="9bb77-114">Defina a propriedade **SnappingEnabled** como `True` .</span><span class="sxs-lookup"><span data-stu-id="9bb77-114">Set the **SnappingEnabled** property to `True`.</span></span>  
  
5.  <span data-ttu-id="9bb77-115">Defina o **SnappingInterval** para um valor que representa o intervalo de ajuste.</span><span class="sxs-lookup"><span data-stu-id="9bb77-115">Set the **SnappingInterval** to a value that represents the snapping interval.</span></span> <span data-ttu-id="9bb77-116">O ponteiro será ajustado para o múltiplo de arredondamento mais próximo do valor especificado.</span><span class="sxs-lookup"><span data-stu-id="9bb77-116">The pointer will be snapped to the nearest round multiple of the value that you have specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb77-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9bb77-117">See Also</span></span>  
 <span data-ttu-id="9bb77-118">[Formatando escalas em um medidor &#40;Construtor de Relatórios e SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9bb77-118">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9bb77-119">[Formatando ponteiros em um medidor &#40;Construtor de Relatórios e SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9bb77-119">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9bb77-120">Medidores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9bb77-120">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
