---
title: Definir mínimo ou máximo em um medidor (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b4c260c0-5a88-4f30-8977-eb5cc78fc146
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 344122dbff647a8c35b838ecce637602f202864b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570442"
---
# <a name="set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="90fce-102">Definir mínimo ou máximo em um medidor (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="90fce-102">Set a Minimum or Maximum on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="90fce-103">Diferente de gráficos, nos quais vários grupos são definidos, o medidor mostra apenas um valor.</span><span class="sxs-lookup"><span data-stu-id="90fce-103">Unlike the chart, where multiple groups are defined, the gauge only shows one value.</span></span> <span data-ttu-id="90fce-104">Como o Construtor de Relatórios e o Designer de Relatórios determinam o contexto ou a significância relativa do valor que você está tentando mostrar no medidor, defina o mínimo e o máximo da escala.</span><span class="sxs-lookup"><span data-stu-id="90fce-104">Since Report Builder and Report Designer determine the context or relative significance of the one value that you are trying to show on the gauge, you must define the minimum and maximum of the scale.</span></span> <span data-ttu-id="90fce-105">Por exemplo, se seus valores de dados tiverem classificações entre 0 e 10, você desejará definir o mínimo como 0 e o máximo como 10.</span><span class="sxs-lookup"><span data-stu-id="90fce-105">For example, if your data values are rankings between 0 and 10, you will want to set the minimum to 0 and maximum to 10.</span></span> <span data-ttu-id="90fce-106">Os números do intervalo são calculados automaticamente com base nos valores especificados para o mínimo e máximo.</span><span class="sxs-lookup"><span data-stu-id="90fce-106">The interval numbers are calculated automatically based on the values specified for the minimum and maximum.</span></span> <span data-ttu-id="90fce-107">Por padrão, o mínimo e o máximo são definidos como 0 e 100, mas esse é um valor arbitrário que você deve alterar.</span><span class="sxs-lookup"><span data-stu-id="90fce-107">By default, the minimum and maximum are set to 0 and 100, but this is an arbitrary value that you should change.</span></span> <span data-ttu-id="90fce-108">O aplicativo não calcula seu valor como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="90fce-108">The application does not calculate your value as a percentage.</span></span>  
  
 <span data-ttu-id="90fce-109">Se o intervalo dos seus valores for grande, por exemplo, de 0 a 10.000, considere usar um multiplicador pra reduzir o número de zeros no medidor.</span><span class="sxs-lookup"><span data-stu-id="90fce-109">If the range of your values is large, for example from 0 to 10000, consider using a multiplier to reduce the number of zeroes on the gauge.</span></span> <span data-ttu-id="90fce-110">O multiplicador só reduzirá a escala dos números do medidor, não o valor em si.</span><span class="sxs-lookup"><span data-stu-id="90fce-110">The multiplier will only reduce the scale of the numbers on the gauge, not the value itself.</span></span>  
  
 <span data-ttu-id="90fce-111">Você pode usar expressões para definir os valores das opções **Mínimo** e **Máximo** .</span><span class="sxs-lookup"><span data-stu-id="90fce-111">You can use expressions to set the values of the **Minimum** and **Maximum** options.</span></span> <span data-ttu-id="90fce-112">Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="90fce-112">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-minimum-and-maximum-on-the-gauge"></a><span data-ttu-id="90fce-113">Para definir o mínimo e o máximo no medidor</span><span class="sxs-lookup"><span data-stu-id="90fce-113">To set the minimum and maximum on the gauge</span></span>  
  
1.  <span data-ttu-id="90fce-114">Clique com o botão direito do mouse na escala e selecione **Propriedades da Escala**.</span><span class="sxs-lookup"><span data-stu-id="90fce-114">Right-click on the scale and select **Scale Properties**.</span></span> <span data-ttu-id="90fce-115">É exibida a caixa de diálogo **Propriedades da Escala** .</span><span class="sxs-lookup"><span data-stu-id="90fce-115">The **Scale Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="90fce-116">Em **Geral**, especifique um valor para **Mínimo**.</span><span class="sxs-lookup"><span data-stu-id="90fce-116">In **General**, specify a value for **Minimum**.</span></span> <span data-ttu-id="90fce-117">Por padrão, esse valor é 0.</span><span class="sxs-lookup"><span data-stu-id="90fce-117">By default, this value is 0.</span></span> <span data-ttu-id="90fce-118">Se preferir, clique no botão **Expressão** (*fx*) para editar a expressão que define o valor da opção.</span><span class="sxs-lookup"><span data-stu-id="90fce-118">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
3.  <span data-ttu-id="90fce-119">Especifique um valor para **Máximo**.</span><span class="sxs-lookup"><span data-stu-id="90fce-119">Specify a value for **Maximum**.</span></span> <span data-ttu-id="90fce-120">Por padrão, esse valor é 100.</span><span class="sxs-lookup"><span data-stu-id="90fce-120">By default, this value is 100.</span></span> <span data-ttu-id="90fce-121">Se preferir, clique no botão **Expressão** (*fx*) para editar a expressão que define o valor da opção.</span><span class="sxs-lookup"><span data-stu-id="90fce-121">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="90fce-122">(Opcional) Se os valores para mínimo e máximo forem grandes, especifique um valor para a opção **Multiplicar rótulos da escala por** .</span><span class="sxs-lookup"><span data-stu-id="90fce-122">(Optional) If the values for your minimum and maximum are large, specify a value for the **Multiply scale labels by** option.</span></span> <span data-ttu-id="90fce-123">Para especificar um multiplicador que reduza sua escala, use um número decimal.</span><span class="sxs-lookup"><span data-stu-id="90fce-123">To specify a multiplier that reduces your scale, use a decimal number.</span></span> <span data-ttu-id="90fce-124">Por exemplo, se você tiver uma escala de 0 a 1.000, poderá especificar um valor de multiplicador de 0,01 para reduzir a escala para ler 0 a 10.</span><span class="sxs-lookup"><span data-stu-id="90fce-124">For example, if you have a scale from 0 to 1000, you can specify a multiplier value of 0.01 to reduce the scale to read 0 to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90fce-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90fce-125">See Also</span></span>  
 <span data-ttu-id="90fce-126">[Formatando escalas em um medidor &#40;Construtor de Relatórios e SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="90fce-126">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="90fce-127">[Formatando ponteiros de um medidor &#40;Construtor de Relatórios e SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="90fce-127">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="90fce-128">Medidores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="90fce-128">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
