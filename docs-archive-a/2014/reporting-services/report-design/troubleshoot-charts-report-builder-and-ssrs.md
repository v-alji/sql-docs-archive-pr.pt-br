---
title: Solução de problemas de gráficos (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a327ffa-3b69-40d6-8015-cc01cfae9161
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b931b50545ba2b8d7c4c06cc5c48d6415a05470a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681419"
---
# <a name="troubleshoot-charts-report-builder-and-ssrs"></a><span data-ttu-id="f725a-102">Solução de problemas de gráficos (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f725a-102">Troubleshoot Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f725a-103">Esses problemas podem ser úteis durante o trabalho com gráficos.</span><span class="sxs-lookup"><span data-stu-id="f725a-103">These issues can be helpful when working with charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="why-does-my-chart-count-not-sum-the-values-on-the-value-axis"></a><span data-ttu-id="f725a-104">Por que meu gráfico conta, e não soma, os valores no eixo de valores?</span><span class="sxs-lookup"><span data-stu-id="f725a-104">Why does my chart count, not sum, the values on the value axis?</span></span>  
 <span data-ttu-id="f725a-105">A maior parte dos tipos de gráfico exigem valores numéricos ao longo do eixo de valor, que normalmente é o eixo y, para que o gráfico seja desenhado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f725a-105">Most chart types require numeric values along the value axis, which is typically the y-axis, in order to draw correctly.</span></span> <span data-ttu-id="f725a-106">Se o tipo de dados do campo de valor for `String`, o gráfico não poderá exibir um valor numérico, mesmo que haja numerais nos campos.</span><span class="sxs-lookup"><span data-stu-id="f725a-106">If the data type of your value field is `String`, the chart cannot display a numeric value, even if there are numerals in the fields.</span></span> <span data-ttu-id="f725a-107">Em vez disso, o gráfico exibirá uma contagem do número total de linhas que contêm um valor nesse campo.</span><span class="sxs-lookup"><span data-stu-id="f725a-107">Instead, the chart displays a count of the total number of rows that contain a value in that field.</span></span> <span data-ttu-id="f725a-108">Para evitar esse comportamento, verifique se os campos usados para a série de valores têm tipos de dados numéricos, em vez de cadeias de caracteres que contêm números formatados.</span><span class="sxs-lookup"><span data-stu-id="f725a-108">To avoid this behavior, make sure that the fields that you use for value series have numeric data types, as opposed to strings that contain formatted numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f725a-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f725a-109">See Also</span></span>  
 [<span data-ttu-id="f725a-110">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f725a-110">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
