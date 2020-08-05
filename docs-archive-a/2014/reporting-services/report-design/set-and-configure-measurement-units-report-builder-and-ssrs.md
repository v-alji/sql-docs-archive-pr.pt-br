---
title: Definir e configurar unidades de medida (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a15a96c3-7d2c-433e-a440-4ea051e967a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c01523dad9a96d2d45b96474d36873bac2484343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569089"
---
# <a name="set-and-configure-measurement-units-report-builder-and-ssrs"></a><span data-ttu-id="8bb90-102">Definir e configurar unidades de medida (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="8bb90-102">Set and Configure Measurement Units (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8bb90-103">Indicadores fornecem duas unidades de medida: percentual e numérica.</span><span class="sxs-lookup"><span data-stu-id="8bb90-103">Indicators provide two measurement units: percentage and numeric.</span></span> <span data-ttu-id="8bb90-104">Por padrão, indicadores são configurados para usar percentuais como a unidade de medida.</span><span class="sxs-lookup"><span data-stu-id="8bb90-104">By default, indicators are configured to use percentages as the measurement unit.</span></span> <span data-ttu-id="8bb90-105">Isso significa que os valores de indicador atribuídos a cada ícone no conjunto de indicadores são determinados por um intervalo de percentuais.</span><span class="sxs-lookup"><span data-stu-id="8bb90-105">This means that the indicator values assigned to each icon in the indicator set are determined by a percentage range.</span></span> <span data-ttu-id="8bb90-106">Os intervalos de percentuais são divididos uniformemente pelos ícones no conjunto de indicadores.</span><span class="sxs-lookup"><span data-stu-id="8bb90-106">The percentage ranges are evenly divided across the icons in the indicator set.</span></span> <span data-ttu-id="8bb90-107">Cada ícone representa um estado de indicador.</span><span class="sxs-lookup"><span data-stu-id="8bb90-107">Each icon represents an indicator state.</span></span> <span data-ttu-id="8bb90-108">Você pode alterar os percentuais para cada ícone no conjunto de indicadores especificando percentuais inicial e final diferentes.</span><span class="sxs-lookup"><span data-stu-id="8bb90-108">You can change the percentages for each icon in the indicator set by specifying different start and end percentages.</span></span> <span data-ttu-id="8bb90-109">Os indicadores também detectam automaticamente os valores mínimo e máximo nos dados.</span><span class="sxs-lookup"><span data-stu-id="8bb90-109">Indicators also automatically detect the minimum and maximum values in the data.</span></span>  
  
 <span data-ttu-id="8bb90-110">Você pode alterar a unidade de medida para ser um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="8bb90-110">You can change the measurement unit to be a numeric value.</span></span> <span data-ttu-id="8bb90-111">Nesse caso, você não especifica o mínimo ou o máximo para obter os dados; em vez disso, fornece apenas os valores inicial e final para cada ícone usado pelo indicador.</span><span class="sxs-lookup"><span data-stu-id="8bb90-111">In this case, you do not specify minimum or maximum for the data; instead, you provide only the start and end values for each icon that the indicator uses.</span></span>  
  
 <span data-ttu-id="8bb90-112">Opções como unidades de medida podem ser definidas usando expressões.</span><span class="sxs-lookup"><span data-stu-id="8bb90-112">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="8bb90-113">Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8bb90-113">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-use-the-numeric-state-measurement-unit"></a><span data-ttu-id="8bb90-114">Para usar a unidade de medida em estado numérico</span><span class="sxs-lookup"><span data-stu-id="8bb90-114">To use the numeric state measurement unit</span></span>  
  
1.  <span data-ttu-id="8bb90-115">Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="8bb90-115">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="8bb90-116">Clique em **Valores e Estados** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="8bb90-116">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="8bb90-117">Na lista **Unidade de Medida de Estados** , clique em **Numérico**.</span><span class="sxs-lookup"><span data-stu-id="8bb90-117">In the **States Measurement Unit** list, click **Numeric**.</span></span>  
  
     <span data-ttu-id="8bb90-118">Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define o valor da opção.</span><span class="sxs-lookup"><span data-stu-id="8bb90-118">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="8bb90-119">Para cada ícone no conjunto de indicadores, atualize os valores nas caixas de texto **Início** e **Fim** .</span><span class="sxs-lookup"><span data-stu-id="8bb90-119">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="8bb90-120">Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define os valores das opções **Início** e **Fim** .</span><span class="sxs-lookup"><span data-stu-id="8bb90-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bb90-121">Os valores das caixas de texto **Início** e **Fim** devem ser numéricos.</span><span class="sxs-lookup"><span data-stu-id="8bb90-121">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-percentage-measurement-unit"></a><span data-ttu-id="8bb90-122">Para usar a unidade de medida em percentual</span><span class="sxs-lookup"><span data-stu-id="8bb90-122">To use the percentage measurement unit</span></span>  
  
1.  <span data-ttu-id="8bb90-123">Clique com o botão direito do mouse no indicador que você deseja alterar e clique em **Propriedades do Indicador**.</span><span class="sxs-lookup"><span data-stu-id="8bb90-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="8bb90-124">Clique em **Valores e Estados** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="8bb90-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="8bb90-125">Na lista **Unidade de Medida de Estados** , clique em **Percentual**.</span><span class="sxs-lookup"><span data-stu-id="8bb90-125">In the **States Measurement Unit** list, click **Percentage**.</span></span>  
  
     <span data-ttu-id="8bb90-126">Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define o valor da opção.</span><span class="sxs-lookup"><span data-stu-id="8bb90-126">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="8bb90-127">Opcionalmente, altere as opções **Mínimo** e **Máximo** para usar valores específicos em vez de detectar automaticamente os valores mínimo e máximo dos dados que o indicador usa.</span><span class="sxs-lookup"><span data-stu-id="8bb90-127">Optionally, change the **Minimum** and **Maximum** options to use specific values instead of automatically detecting the minimum and maximum values of the data that the indicator uses.</span></span> <span data-ttu-id="8bb90-128">O valor **Mínimo** deve ser menor do que o valor **Máximo**.</span><span class="sxs-lookup"><span data-stu-id="8bb90-128">The value of **Minimum** must be smaller than the value of **Maximum**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bb90-129">Se você definir explicitamente os valores mínimo e máximo, aquele intervalo de valor será usado pelo indicador independentemente dos valores reais mínimo e máximo nos dados.</span><span class="sxs-lookup"><span data-stu-id="8bb90-129">If you explicitly set minimum and maximum values, that value range is used by the indicator regardless of the actual the minimum and maximum values in the data.</span></span> <span data-ttu-id="8bb90-130">Isto significa que valores menores que o mínimo e maiores que o máximo serão excluídos da avaliação que determina o ícone de indicador que será mostrado no relatório.</span><span class="sxs-lookup"><span data-stu-id="8bb90-130">This means that values lower than the minimum and higher than the maximum are excluded from the evaluation that determine what indictor icon to show in the report.</span></span>  
  
     <span data-ttu-id="8bb90-131">Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define os valores da opção.</span><span class="sxs-lookup"><span data-stu-id="8bb90-131">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the option.</span></span>  
  
5.  <span data-ttu-id="8bb90-132">Para cada ícone no conjunto de indicadores, atualize os valores nas caixas de texto **Início** e **Fim** .</span><span class="sxs-lookup"><span data-stu-id="8bb90-132">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="8bb90-133">Se preferir, clique no botão **Expressão** (*fx*) para editar uma expressão que define os valores das opções **Início** e **Fim** .</span><span class="sxs-lookup"><span data-stu-id="8bb90-133">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bb90-134">Os valores das caixas de texto **Início** e **Fim** devem ser numéricos.</span><span class="sxs-lookup"><span data-stu-id="8bb90-134">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8bb90-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8bb90-135">See Also</span></span>  
 [<span data-ttu-id="8bb90-136">Indicadores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8bb90-136">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
