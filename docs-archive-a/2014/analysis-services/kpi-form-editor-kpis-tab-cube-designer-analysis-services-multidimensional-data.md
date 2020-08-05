---
title: Editor de formulário KPI (guia KPIs, designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpidefinitionpane.f1
ms.assetid: 45c6453a-bbe2-4ca5-836e-c7ef11cfcb65
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c88d6fcec60634f37ddad8b6d0f5cb2124fa1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570953"
---
# <a name="kpi-form-editor-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="9f15b-102">Editor de Formulário KPI (guia KPIs, Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="9f15b-102">KPI Form Editor (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="9f15b-103">Use o painel **Editor de Formulário KPI** na guia **KPIs** do Designer de Cubo para criar ou modificar o KPI (Indicador Chave de Desempenho) selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-103">Use the **KPI Form Editor** pane on the **KPIs** tab in Cube Designer to create or modify the selected Key Performance Indicator (KPI).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f15b-104">Este painel é exibido apenas na exibição de formulário.</span><span class="sxs-lookup"><span data-stu-id="9f15b-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9f15b-105">Opções</span><span class="sxs-lookup"><span data-stu-id="9f15b-105">Options</span></span>  
 <span data-ttu-id="9f15b-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9f15b-106">**Name**</span></span>  
 <span data-ttu-id="9f15b-107">Digite o nome do KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-107">Type the name of the KPI.</span></span>  
  
 <span data-ttu-id="9f15b-108">**Grupo de medidas associado**</span><span class="sxs-lookup"><span data-stu-id="9f15b-108">**Associated measure group**</span></span>  
 <span data-ttu-id="9f15b-109">Selecione o grupo de medidas associado ao KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-109">Select the measure group associated with the KPI.</span></span> <span data-ttu-id="9f15b-110">O aplicativo cliente pode usar essas informações para determinar quais dimensões estão disponíveis quando o usuário procurar esse KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-110">The client application can use this information to determine which dimensions are available when the user browses this KPI.</span></span>  
  
 <span data-ttu-id="9f15b-111">**Expressão de valor**</span><span class="sxs-lookup"><span data-stu-id="9f15b-111">**Value Expression**</span></span>  
 <span data-ttu-id="9f15b-112">Expanda para exibir ou editar a expressão MDX do valor do KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-112">Expand to view or edit the Multidimensional Expressions (MDX) expression for the value of the KPI.</span></span>  
  
 <span data-ttu-id="9f15b-113">Digite a expressão MDX que retorna o valor do KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-113">Type the MDX expression that returns the value of the KPI.</span></span>  
  
 <span data-ttu-id="9f15b-114">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-114">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="9f15b-115">**Expressão de Meta**</span><span class="sxs-lookup"><span data-stu-id="9f15b-115">**Goal Expression**</span></span>  
 <span data-ttu-id="9f15b-116">Expanda para exibir ou editar a expressão MDX do valor de meta do KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-116">Expand to view or edit the MDX expression for the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="9f15b-117">Digite a expressão MDX que retorna o valor de meta do KPI quando o KPI é executado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-117">Type the MDX expression that returns the goal value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="9f15b-118">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-118">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="9f15b-119">**Status**</span><span class="sxs-lookup"><span data-stu-id="9f15b-119">**Status**</span></span>  
 <span data-ttu-id="9f15b-120">Expanda para exibir as opções **Gráfico de Status** e **Expressão de status** .</span><span class="sxs-lookup"><span data-stu-id="9f15b-120">Expand to view the **Status graphic** and **Status expression** options.</span></span>  
  
 <span data-ttu-id="9f15b-121">**Gráfico de Status**</span><span class="sxs-lookup"><span data-stu-id="9f15b-121">**Status graphic**</span></span>  
 <span data-ttu-id="9f15b-122">Selecione o gráfico a ser usado pelo aplicativo cliente para representar o valor de status em formulário gráfico.</span><span class="sxs-lookup"><span data-stu-id="9f15b-122">Select the graphic to be used by the client application to represent the status value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f15b-123">O aplicativo cliente pode oferecer suporte ao gráfico selecionado ou substituí-lo por uma alternativa apropriada.</span><span class="sxs-lookup"><span data-stu-id="9f15b-123">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="9f15b-124">**Expressão de status**</span><span class="sxs-lookup"><span data-stu-id="9f15b-124">**Status expression**</span></span>  
 <span data-ttu-id="9f15b-125">Digite a expressão MDX que retorna o valor de status do KPI quando o KPI é executado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-125">Type the MDX expression that returns the status value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="9f15b-126">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-126">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="9f15b-127">É recomendável que essa expressão retorne um número decimal entre-1 e 1.</span><span class="sxs-lookup"><span data-stu-id="9f15b-127">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="9f15b-128">Um número mais baixo representa uma situação negativa, enquanto um número mais alto representa uma situação positiva.</span><span class="sxs-lookup"><span data-stu-id="9f15b-128">A lower number represents a negative situation, while a higher number represents a positive situation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f15b-129">Os valores abaixo-1 e acima de 1 são possíveis, mas podem não ser interpretados corretamente por aplicativos cliente de terceiros.</span><span class="sxs-lookup"><span data-stu-id="9f15b-129">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="9f15b-130">**Tendência**</span><span class="sxs-lookup"><span data-stu-id="9f15b-130">**Trend**</span></span>  
 <span data-ttu-id="9f15b-131">Expanda para exibir as opções **Gráfico de tendência** e **Expressão de tendência** .</span><span class="sxs-lookup"><span data-stu-id="9f15b-131">Expand to view the **Trend graphic** and **Trend expression** options.</span></span>  
  
 <span data-ttu-id="9f15b-132">**Gráfico de tendência**</span><span class="sxs-lookup"><span data-stu-id="9f15b-132">**Trend graphic**</span></span>  
 <span data-ttu-id="9f15b-133">Selecione o gráfico a ser usado pelo aplicativo cliente para representar o valor de tendência em formulário gráfico.</span><span class="sxs-lookup"><span data-stu-id="9f15b-133">Select the graphic to be used by the client application to represent the trend value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f15b-134">O aplicativo cliente pode oferecer suporte ao gráfico selecionado ou substituí-lo por uma alternativa apropriada.</span><span class="sxs-lookup"><span data-stu-id="9f15b-134">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="9f15b-135">**Expressão de tendência**</span><span class="sxs-lookup"><span data-stu-id="9f15b-135">**Trend expression**</span></span>  
 <span data-ttu-id="9f15b-136">Digite a expressão MDX que retorna o valor de tendência do KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-136">Type the MDX expression that returns the trend value of the KPI.</span></span>  
  
 <span data-ttu-id="9f15b-137">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-137">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="9f15b-138">A base da expressão de tendência pode ser qualquer critério baseado em tempo que faça sentido em um determinado contexto comercial.</span><span class="sxs-lookup"><span data-stu-id="9f15b-138">The trend expression can be based on any time-based criteria that makes sense in a given business context.</span></span> <span data-ttu-id="9f15b-139">É recomendável que essa expressão retorne um número decimal entre-1 e 1.</span><span class="sxs-lookup"><span data-stu-id="9f15b-139">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="9f15b-140">Um número mais baixo representa uma tendência negativa ao longo do tempo, enquanto um número mais alto representa uma tendência positiva.</span><span class="sxs-lookup"><span data-stu-id="9f15b-140">A lower number represents a negative trend over time; a higher number represents a positive trend over time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f15b-141">Os valores abaixo-1 e acima de 1 são possíveis, mas podem não ser interpretados corretamente por aplicativos cliente de terceiros.</span><span class="sxs-lookup"><span data-stu-id="9f15b-141">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="9f15b-142">**Propriedades Adicionais**</span><span class="sxs-lookup"><span data-stu-id="9f15b-142">**Additional Properties**</span></span>  
 <span data-ttu-id="9f15b-143">Expanda para exibir as opções **Pasta de exibição**, **KPI Pai**, **Membro da hora atual**, **Peso**e **Descrição** .</span><span class="sxs-lookup"><span data-stu-id="9f15b-143">Expand to view the **Display folder**, **Parent KPI**, **Current time member**, **Weight**, and **Description** options.</span></span>  
  
 <span data-ttu-id="9f15b-144">**Pasta de exibição**</span><span class="sxs-lookup"><span data-stu-id="9f15b-144">**Display folder**</span></span>  
 <span data-ttu-id="9f15b-145">Digite a categorização do KPI para uso pelo aplicativo cliente para fins de exibição.</span><span class="sxs-lookup"><span data-stu-id="9f15b-145">Type the categorization of the KPI for use by the client application for display purposes.</span></span>  
  
 <span data-ttu-id="9f15b-146">Use uma barra invertida (\\) para separar nomes de pastas em uma pasta de exibição e um ponto e vírgula (;) para separar várias pastas de exibição.</span><span class="sxs-lookup"><span data-stu-id="9f15b-146">Use a backward slash (\\) to separate folder names in a display folder and a semicolon (;) to separate multiple display folders.</span></span> <span data-ttu-id="9f15b-147">Por exemplo, digite `Category\Goal\Scientific;Category\Goal\Metric`.</span><span class="sxs-lookup"><span data-stu-id="9f15b-147">For example, type `Category\Goal\Scientific;Category\Goal\Metric`.</span></span>  
  
 <span data-ttu-id="9f15b-148">**KPI Pai**</span><span class="sxs-lookup"><span data-stu-id="9f15b-148">**Parent KPI**</span></span>  
 <span data-ttu-id="9f15b-149">Selecione um KPI existente sob o qual categorizar o KPI para uso pelo aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="9f15b-149">Select an existing KPI under which to categorize the KPI for use by the client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f15b-150">Se essa opção for definida como um KPI existente, a **Pasta de exibição** será ignorada.</span><span class="sxs-lookup"><span data-stu-id="9f15b-150">If this option is set to an existing KPI, **Display folder** is ignored.</span></span>  
  
 <span data-ttu-id="9f15b-151">**Membro da hora atual**</span><span class="sxs-lookup"><span data-stu-id="9f15b-151">**Current time member**</span></span>  
 <span data-ttu-id="9f15b-152">Digite a expressão MDX que retorna o membro que identifica o contexto temporal do KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-152">Type the MDX expression that returns the member that identifies the temporal context of the KPI.</span></span>  
  
 <span data-ttu-id="9f15b-153">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9f15b-154">A expressão MDX deve retornar o nome exclusivo de um membro dentro de uma dimensão de tempo associada ao grupo de medidas especificado em **Grupo de medidas associado**.</span><span class="sxs-lookup"><span data-stu-id="9f15b-154">The MDX expression must return the unique name of a member within a time dimension associated with the measure group specified in **Associated measure group**.</span></span>  
  
 <span data-ttu-id="9f15b-155">**Weight**</span><span class="sxs-lookup"><span data-stu-id="9f15b-155">**Weight**</span></span>  
 <span data-ttu-id="9f15b-156">Expanda para exibir ou editar a expressão MDX do fator de ponderação do KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-156">Expand to view or edit the MDX expression for the weighting factor of the KPI.</span></span>  
  
 <span data-ttu-id="9f15b-157">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f15b-157">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="9f15b-158">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9f15b-158">**Description**</span></span>  
 <span data-ttu-id="9f15b-159">Digite a descrição opcional do KPI.</span><span class="sxs-lookup"><span data-stu-id="9f15b-159">Type the optional description of the KPI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f15b-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f15b-160">See Also</span></span>  
 [<span data-ttu-id="9f15b-161">KPIs &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="9f15b-161">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
