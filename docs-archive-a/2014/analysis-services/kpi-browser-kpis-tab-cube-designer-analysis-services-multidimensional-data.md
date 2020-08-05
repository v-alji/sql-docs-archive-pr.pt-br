---
title: Navegador KPI (guia KPIs, designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpibrowserpane.f1
ms.assetid: 2f61bde6-e6ec-4511-8645-c272374014ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 591dfb7c27842e365b78484153dbbde3713b452e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570956"
---
# <a name="kpi-browser-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="98e5a-102">Navegador KPI (guia KPIs, Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="98e5a-102">KPI Browser (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="98e5a-103">Use o painel **Navegador de KPI** na guia **KPIs** do Designer de Cubo para exibir e testar os resultados dos KPIs (indicadores chave de desempenho).</span><span class="sxs-lookup"><span data-stu-id="98e5a-103">Use the **KPI Browser** pane on the **KPIs** tab in Cube Designer to view and test the results of Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="98e5a-104">Os KPIs devem primeiro ser implantados em uma [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instância antes da navegação.</span><span class="sxs-lookup"><span data-stu-id="98e5a-104">KPIs must first be deployed to a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance before browsing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98e5a-105">Esse painel é exibido apenas na exibição do navegador.</span><span class="sxs-lookup"><span data-stu-id="98e5a-105">This pane is displayed only in browser view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="98e5a-106">Opções</span><span class="sxs-lookup"><span data-stu-id="98e5a-106">Options</span></span>  
 <span data-ttu-id="98e5a-107">**Grade de subcubo**</span><span class="sxs-lookup"><span data-stu-id="98e5a-107">**Subcube grid**</span></span>  
 <span data-ttu-id="98e5a-108">Use para definir um subcubo e restringir os resultados dos KPIs a serem exibidos no painel **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="98e5a-108">Use to define a subcube and restrict the results of the KPIs to be displayed in the **Results** pane.</span></span> <span data-ttu-id="98e5a-109">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="98e5a-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="98e5a-110">**Dimensão**</span><span class="sxs-lookup"><span data-stu-id="98e5a-110">**Dimension**</span></span>  
 <span data-ttu-id="98e5a-111">Selecione a dimensão à qual esse filtro se aplica.</span><span class="sxs-lookup"><span data-stu-id="98e5a-111">Select the dimension to which this filter applies.</span></span>  
  
 <span data-ttu-id="98e5a-112">**Hierarquia**</span><span class="sxs-lookup"><span data-stu-id="98e5a-112">**Hierarchy**</span></span>  
 <span data-ttu-id="98e5a-113">Selecione a hierarquia à qual esse filtro se aplica.</span><span class="sxs-lookup"><span data-stu-id="98e5a-113">Select the hierarchy to which this filter applies.</span></span>  
  
 <span data-ttu-id="98e5a-114">**Operador**</span><span class="sxs-lookup"><span data-stu-id="98e5a-114">**Operator**</span></span>  
 <span data-ttu-id="98e5a-115">Selecione o operador que define como a expressão na **Expressão de Filtro** é aplicada à hierarquia selecionada.</span><span class="sxs-lookup"><span data-stu-id="98e5a-115">Select the operator that defines how the expression in **Filter Expression** is applied to the selected hierarchy.</span></span> <span data-ttu-id="98e5a-116">A tabela a seguir descreve os operadores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="98e5a-116">The following table describes the available operators.</span></span>  
  
|<span data-ttu-id="98e5a-117">Valor</span><span class="sxs-lookup"><span data-stu-id="98e5a-117">Value</span></span>|<span data-ttu-id="98e5a-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="98e5a-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98e5a-119">**Igual**</span><span class="sxs-lookup"><span data-stu-id="98e5a-119">**Equal**</span></span>|<span data-ttu-id="98e5a-120">Os resultados são restringidos ao conjunto definido na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-120">The results are restricted to the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98e5a-121">**Diferente de**</span><span class="sxs-lookup"><span data-stu-id="98e5a-121">**Not Equal**</span></span>|<span data-ttu-id="98e5a-122">Os resultados são restringidos aos membros excluídos pelo conjunto definido na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-122">The results are restricted to the members excluded by the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98e5a-123">**No**</span><span class="sxs-lookup"><span data-stu-id="98e5a-123">**In**</span></span>|<span data-ttu-id="98e5a-124">Os resultados são restringidos ao conjunto nomeado escolhido na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-124">The results are restricted to the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98e5a-125">**Não está em**</span><span class="sxs-lookup"><span data-stu-id="98e5a-125">**Not In**</span></span>|<span data-ttu-id="98e5a-126">Os resultados são restringidos aos membros excluídos pelo conjunto nomeado escolhido na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-126">The results are restricted to the members excluded by the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98e5a-127">**Contém**</span><span class="sxs-lookup"><span data-stu-id="98e5a-127">**Contains**</span></span>|<span data-ttu-id="98e5a-128">Os resultados são restringidos aos membros cujos nomes contêm a sequência de caracteres na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-128">The results are restricted to members whose member names contain the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98e5a-129">**Começa com**</span><span class="sxs-lookup"><span data-stu-id="98e5a-129">**Begins With**</span></span>|<span data-ttu-id="98e5a-130">Os resultados são restringidos aos membros cujos nomes começam com a sequência de caracteres na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-130">The results are restricted to members whose member names begin with the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98e5a-131">**Intervalo (Inclusivo)**</span><span class="sxs-lookup"><span data-stu-id="98e5a-131">**Range (Inclusive)**</span></span>|<span data-ttu-id="98e5a-132">Os resultados são restringidos ao intervalo escolhido na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-132">The results are restricted to the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98e5a-133">**Intervalo (Exclusivo)**</span><span class="sxs-lookup"><span data-stu-id="98e5a-133">**Range (Exclusive)**</span></span>|<span data-ttu-id="98e5a-134">Os resultados são restringidos aos membros excluídos pelo intervalo escolhido na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-134">The results are restricted to the members excluded by the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="98e5a-135">**MDX**</span><span class="sxs-lookup"><span data-stu-id="98e5a-135">**MDX**</span></span>|<span data-ttu-id="98e5a-136">Os resultados são restringidos à expressão MDX definida na **Expressão de Filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-136">The results are restricted to the Multidimensional Expressions (MDX) expression set in **Filter Expression**.</span></span>|  
  
 <span data-ttu-id="98e5a-137">**Expressão de filtro**</span><span class="sxs-lookup"><span data-stu-id="98e5a-137">**Filter Expression**</span></span>  
 <span data-ttu-id="98e5a-138">Digite a expressão a ser avaliada pelo **Operador**que restringe os resultados do KPI a serem procurados.</span><span class="sxs-lookup"><span data-stu-id="98e5a-138">Type the expression that is to be evaluated by **Operator**, which restricts the KPI results to be browsed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98e5a-139">Este campo é um elemento de entrada de dados dinâmicos que altera a aparência para refletir os tipos de dados necessários para o operador selecionado.</span><span class="sxs-lookup"><span data-stu-id="98e5a-139">This field is a dynamic data entry element, changing appearance to reflect the types of data necessary for the selected operator.</span></span>  
  
 <span data-ttu-id="98e5a-140">**Grade de resultados**</span><span class="sxs-lookup"><span data-stu-id="98e5a-140">**Results grid**</span></span>  
 <span data-ttu-id="98e5a-141">Exibe o valor avaliado, a meta, o status e a tendência dos KPIs, com base no filtro definido na **Grade de filtro**.</span><span class="sxs-lookup"><span data-stu-id="98e5a-141">Displays the evaluated value, goal, status, and trend for the KPIs, based on the filter defined in **Filter grid**.</span></span> <span data-ttu-id="98e5a-142">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="98e5a-142">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="98e5a-143">**Exibir Estrutura**</span><span class="sxs-lookup"><span data-stu-id="98e5a-143">**Display Structure**</span></span>  
 <span data-ttu-id="98e5a-144">Exibe os KPIs contidos pelo cubo, organizados hierarquicamente de acordo com os valores da **Pasta de exibição** ou **KPI Pai** de cada KPI.</span><span class="sxs-lookup"><span data-stu-id="98e5a-144">Displays the KPIs contained by the cube, hierarchically organized according to the **Display folder** or **Parent KPI** values for each KPI.</span></span>  
  
 <span data-ttu-id="98e5a-145">**Valor**</span><span class="sxs-lookup"><span data-stu-id="98e5a-145">**Value**</span></span>  
 <span data-ttu-id="98e5a-146">Exibe o valor do KPI.</span><span class="sxs-lookup"><span data-stu-id="98e5a-146">Displays the value of the KPI.</span></span>  
  
 <span data-ttu-id="98e5a-147">**Goal**</span><span class="sxs-lookup"><span data-stu-id="98e5a-147">**Goal**</span></span>  
 <span data-ttu-id="98e5a-148">Exibe o valor da meta do KPI.</span><span class="sxs-lookup"><span data-stu-id="98e5a-148">Displays the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="98e5a-149">**Status**</span><span class="sxs-lookup"><span data-stu-id="98e5a-149">**Status**</span></span>  
 <span data-ttu-id="98e5a-150">Exibe o gráfico de status do KPI.</span><span class="sxs-lookup"><span data-stu-id="98e5a-150">Displays the status graphic of the KPI.</span></span>  
  
 <span data-ttu-id="98e5a-151">**Tendência**</span><span class="sxs-lookup"><span data-stu-id="98e5a-151">**Trend**</span></span>  
 <span data-ttu-id="98e5a-152">Exibe o gráfico de tendências do KPI.</span><span class="sxs-lookup"><span data-stu-id="98e5a-152">Displays the trend graphic of the KPI.</span></span>  
  
 <span data-ttu-id="98e5a-153">**Weight**</span><span class="sxs-lookup"><span data-stu-id="98e5a-153">**Weight**</span></span>  
 <span data-ttu-id="98e5a-154">Exibe o fator de peso do KPI.</span><span class="sxs-lookup"><span data-stu-id="98e5a-154">Displays the weight factor of the KPI.</span></span>  
  
 <span data-ttu-id="98e5a-155">**Ndescrição**</span><span class="sxs-lookup"><span data-stu-id="98e5a-155">**(Description)**</span></span>  
 <span data-ttu-id="98e5a-156">Exibirá um ícone de informações se uma descrição for fornecida para um KPI.</span><span class="sxs-lookup"><span data-stu-id="98e5a-156">Displays an information icon if a description is provided for a KPI.</span></span>  
  
 <span data-ttu-id="98e5a-157">Focalize o mouse sobre o ícone de informações para exibir uma Dica de Ferramenta contendo a descrição do KPI.</span><span class="sxs-lookup"><span data-stu-id="98e5a-157">Hover the mouse over the information icon to display a ToolTip containing the description for the KPI.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98e5a-158">Se ocorrer um erro ao calcular um KPI na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , essa opção exibirá informações associadas ao erro.</span><span class="sxs-lookup"><span data-stu-id="98e5a-158">If an error occurs while calculating a KPI on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, this option displays information associated with the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e5a-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98e5a-159">See Also</span></span>  
 [<span data-ttu-id="98e5a-160">KPIs &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="98e5a-160">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
