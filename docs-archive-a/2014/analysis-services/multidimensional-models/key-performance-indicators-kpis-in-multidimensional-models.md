---
title: KPIs (indicadores chave de desempenho) em modelos multidimensionais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- viewing Key Performance Indicators
- Key Performance Indicators [Analysis Services]
- KPIs [Analysis Services]
- OLAP objects [Analysis Services], performance indicators
- weights [Analysis Services]
- displaying Key Performance Indicators
- parent KPIs [Analysis Services]
- child KPIs
ms.assetid: 73aee2da-da30-44f1-829c-0a4c078a7768
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44a12747d9e9087dc4f8254cd12fcbf36b876912
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574372"
---
# <a name="key-performance-indicators-kpis-in-multidimensional-models"></a><span data-ttu-id="31712-102">KPIs (indicadores chave de desempenho) em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="31712-102">Key Performance Indicators (KPIs) in Multidimensional Models</span></span>
  <span data-ttu-id="31712-103">Na terminologia empresarial, um KPI (indicador chave de desempenho) é uma medida quantificável para medir o sucesso empresarial.</span><span class="sxs-lookup"><span data-stu-id="31712-103">In business terminology, a Key Performance Indicator (KPI) is a quantifiable measurement for gauging business success.</span></span>  
  
 <span data-ttu-id="31712-104">No [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], um KPI é uma coleção de cálculos associada a um grupo de medidas em um cubo usado para avaliar o sucesso nos negócios.</span><span class="sxs-lookup"><span data-stu-id="31712-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a KPI is a collection of calculations that are associated with a measure group in a cube that are used to evaluate business success.</span></span> <span data-ttu-id="31712-105">Normalmente, esses cálculos são uma combinação de MDX ou membros calculados.</span><span class="sxs-lookup"><span data-stu-id="31712-105">Typically, these calculations are a combination of Multidimensional Expressions (MDX) expressions or calculated members.</span></span> <span data-ttu-id="31712-106">Os KPIs também contêm metadados adicionais que fornecem informações sobre como os aplicativos cliente devem exibir os resultados de cálculos de KPIs.</span><span class="sxs-lookup"><span data-stu-id="31712-106">KPIs also have additional metadata that provides information about how client applications should display the results of the KPI's calculations.</span></span>  
  
 <span data-ttu-id="31712-107">Um KPI processa informações sobre um conjunto de metas, a fórmula real do desempenho registrado em cubos e a medida para mostrar a tendência e o status do desempenho.</span><span class="sxs-lookup"><span data-stu-id="31712-107">A KPI handles information about a goal set, the actual formula of the performance recorded in the cube, and measurement to show the trend and the status of the performance.</span></span> <span data-ttu-id="31712-108">O AMO é usado para definir as fórmulas e outras definições sobre os valores de um KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-108">AMO is used to define the formulas and other definitions about the values of a KPI.</span></span> <span data-ttu-id="31712-109">Uma interface de consulta, como ADOMD.NET, é usada pelo aplicativo cliente para recuperar e expor os valores de KPI ao usuário final.</span><span class="sxs-lookup"><span data-stu-id="31712-109">A query interface, such as ADOMD.NET, is used by the client application to retrieve and expose the KPI values to the end user.</span></span> <span data-ttu-id="31712-110">Para obter mais informações, consulte [Desenvolvendo com ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net).</span><span class="sxs-lookup"><span data-stu-id="31712-110">For more information see [Developing with ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net).</span></span>  
  
 <span data-ttu-id="31712-111">Um simples objeto <xref:Microsoft.AnalysisServices.Kpi> é composto de: informações básicas, a meta, o valor real atingido, o valor de status, o valor de tendência e a pasta na qual o KPI é exibido.</span><span class="sxs-lookup"><span data-stu-id="31712-111">A simple <xref:Microsoft.AnalysisServices.Kpi> object is composed of: basic information, the goal, the actual value achieved, a status value, a trend value, and a folder where the KPI is viewed.</span></span> <span data-ttu-id="31712-112">As informações básicas incluem o nome e a descrição do KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-112">Basic information includes the name and description of the KPI.</span></span> <span data-ttu-id="31712-113">A meta é uma expressão MDX que avalia a um número.</span><span class="sxs-lookup"><span data-stu-id="31712-113">The goal is an MDX expression that evaluates to a number.</span></span> <span data-ttu-id="31712-114">O valor real é uma expressão MDX que avalia a um número.</span><span class="sxs-lookup"><span data-stu-id="31712-114">The actual value is an MDX expression that evaluates to a number.</span></span> <span data-ttu-id="31712-115">O status e valor de tendência são expressões MDX que avaliam a um número.</span><span class="sxs-lookup"><span data-stu-id="31712-115">The status and trend value are MDX expressions that evaluate to a number.</span></span> <span data-ttu-id="31712-116">A pasta é um local sugerido para o KPI para ser apresentado ao cliente.</span><span class="sxs-lookup"><span data-stu-id="31712-116">The folder is a suggested location for the KPI to be presented to the client.</span></span>  
  
 <span data-ttu-id="31712-117">Na terminologia empresarial, um KPI (indicador chave de desempenho) é uma medida quantificável para medir o sucesso empresarial.</span><span class="sxs-lookup"><span data-stu-id="31712-117">In business terminology, a Key Performance Indicator (KPI) is a quantifiable measurement for gauging business success.</span></span> <span data-ttu-id="31712-118">Um KPI é avaliado, frequentemente, ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="31712-118">A KPI is frequently evaluated over time.</span></span> <span data-ttu-id="31712-119">Por exemplo, o departamento de vendas de uma organização pode usar o lucro bruto mensal como um KPI, mas o departamento de recursos humanos da mesma organização pode usar a rotatividade de funcionários trimestral.</span><span class="sxs-lookup"><span data-stu-id="31712-119">For example, the sales department of an organization may use monthly gross profit as a KPI, but the human resources department of the same organization may use quarterly employee turnover.</span></span> <span data-ttu-id="31712-120">Cada um é um exemplo de KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-120">Each is an example of a KPI.</span></span> <span data-ttu-id="31712-121">Os executivos frequentemente usam KPIs agrupados em um scorecard empresarial para obter um resumo histórico rápido e preciso do sucesso da empresa.</span><span class="sxs-lookup"><span data-stu-id="31712-121">Business executives frequently consume KPIs that are grouped together in a business scorecard to obtain a quick and accurate historical summary of business success.</span></span>  
  
 <span data-ttu-id="31712-122">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , um KPI é uma coleção de cálculos, que são associados a um grupo de medidas em um cubo, que são usados para avaliar o sucesso do negócio.</span><span class="sxs-lookup"><span data-stu-id="31712-122">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a KPI is a collection of calculations, which are associated with a measure group in a cube, that are used to evaluate business success.</span></span> <span data-ttu-id="31712-123">Normalmente, esses cálculos são uma combinação de MDX e membros calculados.</span><span class="sxs-lookup"><span data-stu-id="31712-123">Typically, these calculations are a combination of Multidimensional Expressions (MDX) expressions and calculated members.</span></span> <span data-ttu-id="31712-124">Os KPIs também contêm metadados adicionais que fornecem informações sobre como os aplicativos cliente devem exibir os resultados de um cálculo de KPIs.</span><span class="sxs-lookup"><span data-stu-id="31712-124">KPIs also have additional metadata that provides information about how client applications should display the results of a KPI's calculation.</span></span>  
  
 <span data-ttu-id="31712-125">Uma vantagem importante dos KPIs no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] é que eles são KPIs baseados em servidores consumíveis por diferentes aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="31712-125">One key advantage of KPIs in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is that they are server-based KPIs that are consumable by different client applications.</span></span> <span data-ttu-id="31712-126">Um KPI com base em servidor apresenta uma única versão de autenticidade, comparado com as versões separadas de autenticidade dos aplicativos cliente separados.</span><span class="sxs-lookup"><span data-stu-id="31712-126">A server-based KPI presents a single version of the truth, compared to separate versions of the truth from separate client applications.</span></span> <span data-ttu-id="31712-127">Além disso, executando algumas vezes os cálculos complexos no servidor, em vez de em cada computador cliente, poderá trazer benefícios de desempenho.</span><span class="sxs-lookup"><span data-stu-id="31712-127">Moreover, performing the sometimes complex calculations on the server instead of on each client computer may have performance benefits.</span></span>  
  
## <a name="common-kpi-terms"></a><span data-ttu-id="31712-128">Termos comuns de KPI</span><span class="sxs-lookup"><span data-stu-id="31712-128">Common KPI Terms</span></span>  
 <span data-ttu-id="31712-129">A tabela a seguir fornece definições para termos de KPI comuns no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31712-129">The following table provides definitions for common KPI terms in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="31712-130">Termo</span><span class="sxs-lookup"><span data-stu-id="31712-130">Term</span></span>|<span data-ttu-id="31712-131">Definição</span><span class="sxs-lookup"><span data-stu-id="31712-131">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="31712-132">Goal</span><span class="sxs-lookup"><span data-stu-id="31712-132">Goal</span></span>|<span data-ttu-id="31712-133">Uma expressão numérica MDX ou um cálculo que retorna o valor alvo do KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-133">An MDX numeric expression or a calculation that returns the target value of the KPI.</span></span>|  
|<span data-ttu-id="31712-134">Valor</span><span class="sxs-lookup"><span data-stu-id="31712-134">Value</span></span>|<span data-ttu-id="31712-135">Uma expressão numérica MDX que retorna o valor real do KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-135">An MDX numeric expression that returns the actual value of the KPI.</span></span>|  
|<span data-ttu-id="31712-136">Status</span><span class="sxs-lookup"><span data-stu-id="31712-136">Status</span></span>|<span data-ttu-id="31712-137">Uma expressão MDX que representa o estado do KPI em um point-in-time.</span><span class="sxs-lookup"><span data-stu-id="31712-137">An MDX expression that represents the state of the KPI at a specified point in time.</span></span><br /><br /> <span data-ttu-id="31712-138">O status da expressão MDX deve retornar um valor normalizado entre -1 e 1.</span><span class="sxs-lookup"><span data-stu-id="31712-138">The status MDX expression should return a normalized value between -1 and 1.</span></span> <span data-ttu-id="31712-139">Valores iguais ou menores que -1 serão interpretados como "ruim" ou "baixo".</span><span class="sxs-lookup"><span data-stu-id="31712-139">Values equal to or less than -1 will be interpreted as "bad" or "low."</span></span> <span data-ttu-id="31712-140">Um valor de zero (0) será interpretado como "aceitável" ou "médio".</span><span class="sxs-lookup"><span data-stu-id="31712-140">A value of zero (0) is interpreted as "acceptable" or "medium."</span></span> <span data-ttu-id="31712-141">Os valores iguais ou maiores que 1 serão interpretados como "bom" ou "alto".</span><span class="sxs-lookup"><span data-stu-id="31712-141">Values equal to or greater than 1 will be interpreted as "good" or "high."</span></span><br /><br /> <span data-ttu-id="31712-142">Um número ilimitado de valores intermediários pode ser opcionalmente retornado e pode ser usado para exibir qualquer número de estados adicionais, caso tenham suporte pelo aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="31712-142">An unlimited number of intermediate values can optionally be returned and can be used to display any number of additional states, if supported by the client application.</span></span>|  
|<span data-ttu-id="31712-143">Tendência</span><span class="sxs-lookup"><span data-stu-id="31712-143">Trend</span></span>|<span data-ttu-id="31712-144">Uma expressão MDX que avalia o valor do KPI ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="31712-144">An MDX expression that evaluates the value of the KPI over time.</span></span> <span data-ttu-id="31712-145">A tendência pode ser qualquer critério com base no tempo e que seja útil em um contexto empresarial específico.</span><span class="sxs-lookup"><span data-stu-id="31712-145">The trend can be any time-based criterion that is useful in a specific business context.</span></span><br /><br /> <span data-ttu-id="31712-146">A expressão MDX de tendência permite que um usuário empresarial determine se o KPI está melhorando ou piorando ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="31712-146">The trend MDX expression enables a business user to determine whether the KPI is improving over time or degrading over time.</span></span>|  
|<span data-ttu-id="31712-147">Indicador de status</span><span class="sxs-lookup"><span data-stu-id="31712-147">Status indicator</span></span>|<span data-ttu-id="31712-148">Um elemento visual que fornece uma indicação rápida do status de um KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-148">A visual element that provides a quick indication of the status for a KPI.</span></span> <span data-ttu-id="31712-149">A exibição do elemento é determinada pelo valor da expressão MDX que avalia o status.</span><span class="sxs-lookup"><span data-stu-id="31712-149">The display of the element is determined by the value of the MDX expression that evaluates status.</span></span>|  
|<span data-ttu-id="31712-150">Indicador de tendência</span><span class="sxs-lookup"><span data-stu-id="31712-150">Trend indicator</span></span>|<span data-ttu-id="31712-151">Um elemento visual que fornece uma indicação rápida da tendência de um KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-151">A visual element that provides a quick indication of the trend for a KPI.</span></span> <span data-ttu-id="31712-152">A exibição do elemento é determinada pelo valor da expressão MDX que avalia a tendência.</span><span class="sxs-lookup"><span data-stu-id="31712-152">The display of the element is determined by the value of the MDX expression that evaluates trend.</span></span>|  
|<span data-ttu-id="31712-153">Pasta de exibição</span><span class="sxs-lookup"><span data-stu-id="31712-153">Display folder</span></span>|<span data-ttu-id="31712-154">A pasta na qual o KPI aparecerá quando um usuário estiver navegando no cubo.</span><span class="sxs-lookup"><span data-stu-id="31712-154">The folder in which the KPI will appear when a user is browsing the cube.</span></span>|  
|<span data-ttu-id="31712-155">KPI Pai</span><span class="sxs-lookup"><span data-stu-id="31712-155">Parent KPI</span></span>|<span data-ttu-id="31712-156">Uma referência a um KPI existente que usa o valor do KPI filho como parte da computação do KPI pai.</span><span class="sxs-lookup"><span data-stu-id="31712-156">A reference to an existing KPI that uses the value of the child KPI as part of computation of the parent KPI.</span></span> <span data-ttu-id="31712-157">Às vezes, um único KPI será uma computação que consiste nos valores de outros KPIs.</span><span class="sxs-lookup"><span data-stu-id="31712-157">Sometimes, a single KPI will be a computation that consists of the values for other KPIs.</span></span> <span data-ttu-id="31712-158">Essa propriedade facilita a exibição correta dos KPIs filhos sob o KPI pai em aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="31712-158">This property facilitates the correct display of the child KPIs underneath the parent KPI in client applications.</span></span>|  
|<span data-ttu-id="31712-159">Membro da hora atual</span><span class="sxs-lookup"><span data-stu-id="31712-159">Current time member</span></span>|<span data-ttu-id="31712-160">Uma expressão MDX que retorna o membro que identifica o contexto temporal do KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-160">An MDX expression that returns the member that identifies the temporal context of the KPI.</span></span>|  
|<span data-ttu-id="31712-161">Peso</span><span class="sxs-lookup"><span data-stu-id="31712-161">Weight</span></span>|<span data-ttu-id="31712-162">Uma expressão numérica MDX que atribui uma importância relativa a um KPI.</span><span class="sxs-lookup"><span data-stu-id="31712-162">An MDX numeric expression that assigns a relative importance to a KPI.</span></span> <span data-ttu-id="31712-163">Se o KPI estiver atribuído a um KPI pai, o peso será usado para ajustar proporcionalmente os resultados do valor do KPI filho ao calcular o valor do KPI pai.</span><span class="sxs-lookup"><span data-stu-id="31712-163">If the KPI is assigned to a parent KPI, the weight is used to proportionally adjust the results of the child KPI value when calculating the value of the parent KPI.</span></span>|  
  
## <a name="parent-kpis"></a><span data-ttu-id="31712-164">KPIs Pai</span><span class="sxs-lookup"><span data-stu-id="31712-164">Parent KPIs</span></span>  
 <span data-ttu-id="31712-165">Uma organização pode rastrear diferentes métricas empresariais em diferentes níveis.</span><span class="sxs-lookup"><span data-stu-id="31712-165">An organization may track different business metrics at different levels.</span></span> <span data-ttu-id="31712-166">Por exemplo, apenas dois ou três KPIs podem ser usados para medir o sucesso de toda a empresa, mas esses KPIs gerais podem ser usados em três ou quatro outros KPIs rastreados pelas unidades de negócios ao longo da empresa.</span><span class="sxs-lookup"><span data-stu-id="31712-166">For example, only two or three KPIs may be used to gauge business success for the whole company, but these company-wide KPIs may be based on three or four other KPIs tracked by the business units throughout the company.</span></span> <span data-ttu-id="31712-167">Além disso, as unidades de negócio em uma empresa podem usar estatísticas diferentes para calcular o mesmo KPI, esses resultados são acumulados para o KPI geral.</span><span class="sxs-lookup"><span data-stu-id="31712-167">Also, business units in a company may use different statistics to calculate the same KPI, the results of which are rolled up to the company-wide KPI.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="31712-168">permite definir uma relação pai-filho entre KPIs.</span><span class="sxs-lookup"><span data-stu-id="31712-168">lets you define a parent-child relationship between KPIs.</span></span> <span data-ttu-id="31712-169">Essa relação pai-filho permite que os resultados do KPI filho seja usada para calcular os resultados do KPI pai.</span><span class="sxs-lookup"><span data-stu-id="31712-169">This parent-child relationship lets the results of the child KPI be used to calculate the results of the parent KPI.</span></span> <span data-ttu-id="31712-170">Os aplicativos cliente também podem usar essa relação para exibir os KPIs pai e filho adequadamente.</span><span class="sxs-lookup"><span data-stu-id="31712-170">Client applications can also use this relationship to appropriately display parent and child KPIs.</span></span>  
  
## <a name="weights"></a><span data-ttu-id="31712-171">Pesos</span><span class="sxs-lookup"><span data-stu-id="31712-171">Weights</span></span>  
 <span data-ttu-id="31712-172">Os pesos também podem ser atribuídos à KPIs filho.</span><span class="sxs-lookup"><span data-stu-id="31712-172">Weights can also be assigned to child KPIs.</span></span> <span data-ttu-id="31712-173">Os pesos permitem que o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ajuste proporcionalmente os resultados do KPI filho ao calcular o valor do KPI pai.</span><span class="sxs-lookup"><span data-stu-id="31712-173">Weights enable [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to proportionally adjust the results of the child KPI when calculating the value of the parent KPI.</span></span>  
  
## <a name="retrieving-and-displaying-kpis"></a><span data-ttu-id="31712-174">Recuperando e exibindo KPIs</span><span class="sxs-lookup"><span data-stu-id="31712-174">Retrieving and Displaying KPIs</span></span>  
 <span data-ttu-id="31712-175">A exibição dos KPIs depende da implementação do aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="31712-175">The display of KPIs depends on the implementation of the client application.</span></span> <span data-ttu-id="31712-176">Por exemplo, selecionar **Exibição de Navegador** na barra de ferramentas na guia **KPIs** do Designer de Cubo, demonstra uma possível implementação do cliente, com gráficos usados para exibir os indicadores de status e tendência, exibir pastas usadas para agrupar KPIs e KPIs filho exibidos sob KPIs pai.</span><span class="sxs-lookup"><span data-stu-id="31712-176">For example, selecting **Browser View** on the toolbar on the **KPIs** tab of Cube Designer demonstrates one possible client implementation, with graphics used to display status and trend indicators, display folders used to group KPIs, and child KPIs displayed under parent KPIs.</span></span>  
  
 <span data-ttu-id="31712-177">Você pode usar as funções MDX para recuperar as seções individuais do KPI, como o valor ou meta, para usar em expressões MDX, instruções e scripts.</span><span class="sxs-lookup"><span data-stu-id="31712-177">You can use MDX functions to retrieve individual sections of the KPI, such as the value or goal, for use in MDX expressions, statements, and scripts.</span></span>  
  
  