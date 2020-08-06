---
title: 'Lição 8: criar indicadores chave de desempenho | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a6c8ac2b-64ba-456f-b418-7bf0afe145d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3beaab8a34844ecbd633eb5fabbacf37edfede2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680130"
---
# <a name="lesson-8-create-key-performance-indicators"></a><span data-ttu-id="bbad7-102">Lição 8: Criar indicadores chave de desempenho</span><span class="sxs-lookup"><span data-stu-id="bbad7-102">Lesson 8: Create Key Performance Indicators</span></span>
  <span data-ttu-id="bbad7-103">Nesta lição, você criará KPIs (indicadores chave de desempenho).</span><span class="sxs-lookup"><span data-stu-id="bbad7-103">In this lesson, you will create Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="bbad7-104">Os KPIs são usados para medir o desempenho de um valor, definido por uma medida *Base* , em relação a um valor de *Destino* , também definido por uma medida ou um valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="bbad7-104">KPIs are used to gauge performance of a value, defined by a *Base* measure, against a *Target* value, also defined by a measure or by an absolute value.</span></span> <span data-ttu-id="bbad7-105">Em aplicativos cliente de relatório, KPIs podem fornecer aos profissionais de negócios uma maneira rápida e fácil de entender um resumo de sucesso nos negócios ou para identificar tendências.</span><span class="sxs-lookup"><span data-stu-id="bbad7-105">In reporting client applications, KPIs can provide business professionals a quick and easy way to understand a summary of business success or to identify trends.</span></span> <span data-ttu-id="bbad7-106">Para obter mais informações, consulte [KPIs &#40;SSAS Tabular&#41;](tabular-models/kpis-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="bbad7-106">To learn more, see [KPIs &#40;SSAS Tabular&#41;](tabular-models/kpis-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="bbad7-107">Tempo estimado para conclusão desta lição: **15 minutos**</span><span class="sxs-lookup"><span data-stu-id="bbad7-107">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bbad7-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bbad7-108">Prerequisites</span></span>  
 <span data-ttu-id="bbad7-109">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="bbad7-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="bbad7-110">Antes de executar as tarefas desta lição, você deverá ter concluído a lição anterior: [Lição 7: Criar medidas](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="bbad7-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
## <a name="create-key-performance-indicators"></a><span data-ttu-id="bbad7-111">Criar indicadores chave de desempenho</span><span class="sxs-lookup"><span data-stu-id="bbad7-111">Create Key Performance Indicators</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-sales-performance-kpi"></a><span data-ttu-id="bbad7-112">Para criar um KPI de Desempenho de Vendas do Trimestre Atual da Internet</span><span class="sxs-lookup"><span data-stu-id="bbad7-112">To create an Internet Current Quarter Sales Performance KPI</span></span>  
  
1.  <span data-ttu-id="bbad7-113">No designer de modelos, clique na tabela **Vendas pela Internet** (guia).</span><span class="sxs-lookup"><span data-stu-id="bbad7-113">In the model designer, click the **Internet Sales** table (tab).</span></span>  
  
2.  <span data-ttu-id="bbad7-114">Na grade de medida, clique em uma célula vazia.</span><span class="sxs-lookup"><span data-stu-id="bbad7-114">In the measure grid, click an empty cell.</span></span>  
  
3.  <span data-ttu-id="bbad7-115">Na barra de fórmulas acima da tabela, digite a fórmula a seguir:</span><span class="sxs-lookup"><span data-stu-id="bbad7-115">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Sales Performance :=IFERROR([Internet Current Quarter Sales]/[Internet Previous Quarter Sales Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="bbad7-116">Ao concluir a criação da fórmula, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="bbad7-116">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="bbad7-117">Esta medida servirá como medida Base para o KPI.</span><span class="sxs-lookup"><span data-stu-id="bbad7-117">This measure will serve as the Base measure for the KPI.</span></span>  
  
4.  <span data-ttu-id="bbad7-118">Na grade de medida, clique com o botão direito do mouse na medida **Desempenho de Vendas pela Internet do Trimestre Atual** e clique em **Criar KPI**.</span><span class="sxs-lookup"><span data-stu-id="bbad7-118">In the measure grid, right-click the **Internet Current Quarter Sales Performance** measure, and then click **Create KPI**.</span></span>  
  
     <span data-ttu-id="bbad7-119">A caixa de diálogo **Indicador Chave de Desempenho** será aberta.</span><span class="sxs-lookup"><span data-stu-id="bbad7-119">The **Key Performance Indicator** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="bbad7-120">Na caixa de diálogo **Indicador Chave de Desempenho** , em **Definir Valor de Destino**, selecione a opção **Valor Absoluto** .</span><span class="sxs-lookup"><span data-stu-id="bbad7-120">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
6.  <span data-ttu-id="bbad7-121">No campo **valor absoluto** , digite `1.1` e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="bbad7-121">In the **Absolute Value** field, type `1.1`, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="bbad7-122">Em **definir limites de status**, no campo de controle deslizante à esquerda (baixo), digite `1` e, no campo de controle deslizante à direita (alto), digite `1.07` .</span><span class="sxs-lookup"><span data-stu-id="bbad7-122">In **Define Status Thresholds**, in the left (low) slider field, type `1`, and then in the right (high) slider field, type `1.07`.</span></span>  
  
8.  <span data-ttu-id="bbad7-123">Em **Selecionar Estilo de Ícone**, selecione o tipo de ícone losango (vermelho), triângulo (amarelo) e círculo (verde).</span><span class="sxs-lookup"><span data-stu-id="bbad7-123">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="bbad7-124">Observe o campo expansível **Descrições** abaixo dos estilos de ícone disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bbad7-124">Notice the **Descriptions** expandable field below the available icon styles.</span></span> <span data-ttu-id="bbad7-125">Você pode digitar descrições para os vários elementos KPI para torná-los mais identificáveis nos aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="bbad7-125">You can type descriptions for the various KPI elements to make them more identifiable in client applications.</span></span>  
  
9. <span data-ttu-id="bbad7-126">Clique em **OK** para concluir o KPI.</span><span class="sxs-lookup"><span data-stu-id="bbad7-126">Click **OK** to complete the KPI.</span></span>  
  
     <span data-ttu-id="bbad7-127">Na grade de medida, observe o ícone ao lado da medida **Desempenho de Vendas pela Internet do Trimestre Atual** .</span><span class="sxs-lookup"><span data-stu-id="bbad7-127">In the measure grid, notice the icon next to the **Internet Current Quarter Sales Performance** measure.</span></span> <span data-ttu-id="bbad7-128">Esse ícone indica que essa medida serve como um valor Base para um KPI.</span><span class="sxs-lookup"><span data-stu-id="bbad7-128">This icon indicates that this measure serves as a Base value for a KPI.</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-margin-performance-kpi"></a><span data-ttu-id="bbad7-129">Para criar um KPI de Desempenho de Margem do Trimestre Atual da Internet</span><span class="sxs-lookup"><span data-stu-id="bbad7-129">To create an Internet Current Quarter Margin Performance KPI</span></span>  
  
1.  <span data-ttu-id="bbad7-130">Na grade de medida da tabela **Vendas pela Internet** , clique em uma célula vazia.</span><span class="sxs-lookup"><span data-stu-id="bbad7-130">In the measure grid for the **Internet Sales** table, click an empty cell.</span></span>  
  
2.  <span data-ttu-id="bbad7-131">Na barra de fórmulas acima da tabela, digite a fórmula a seguir:</span><span class="sxs-lookup"><span data-stu-id="bbad7-131">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Margin Performance :=IF([Internet Previous Quarter Margin Proportion to QTD]<>0,([Internet Current Quarter Margin]-[Internet Previous Quarter Margin Proportion to QTD])/[Internet Previous Quarter Margin Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="bbad7-132">Ao concluir a criação da fórmula, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="bbad7-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="bbad7-133">Na grade de medida, clique com o botão direito do mouse na medida **Desempenho de Margem da Internet do Trimestre Atual** e clique em **Criar KPI**.</span><span class="sxs-lookup"><span data-stu-id="bbad7-133">In the measure grid, right-click the **Internet Current Quarter Margin Performance** measure, and then click **Create KPI**.</span></span>  
  
4.  <span data-ttu-id="bbad7-134">Na caixa de diálogo **Indicador Chave de Desempenho** , em **Definir Valor de Destino**, selecione a opção **Valor Absoluto** .</span><span class="sxs-lookup"><span data-stu-id="bbad7-134">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
5.  <span data-ttu-id="bbad7-135">No campo **valor absoluto** , digite `1.25` .</span><span class="sxs-lookup"><span data-stu-id="bbad7-135">In the **Absolute Value** field, type `1.25`.</span></span>  
  
6.  <span data-ttu-id="bbad7-136">Em **Definir Limites de Status**, deslize o campo de controle deslizante à esquerda (baixo) até que ele exiba **0.8**e deslize o campo de controle deslizante à direita (alto) até que ele exiba **1.03**.</span><span class="sxs-lookup"><span data-stu-id="bbad7-136">In **Define Status Thresholds**, slide the left (low) slider field until the field displays **0.8**, and then slide the right (high) slider field, until the field displays **1.03**.</span></span>  
  
7.  <span data-ttu-id="bbad7-137">Em **Selecionar Estilo de Ícone**, selecione o tipo de ícone losango (vermelho), triângulo (amarelo), círculo (verde) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbad7-137">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type, and then click **OK**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="bbad7-138">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="bbad7-138">Next Step</span></span>  
 <span data-ttu-id="bbad7-139">Para continuar este tutorial, vá para a próxima lição: [Lição 9: Criar perspectivas](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="bbad7-139">To continue this tutorial, go to the next lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
  
