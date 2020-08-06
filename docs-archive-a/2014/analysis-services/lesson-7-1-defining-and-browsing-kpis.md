---
title: Definindo e navegando por KPIs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 648b9a02-1278-4f11-b940-6f0de6a4042d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44febe6c6c5d432f0cdee43e8eaaa3401c54a2c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680136"
---
# <a name="defining-and-browsing-kpis"></a><span data-ttu-id="46a46-102">Definindo e procurando KPIs</span><span class="sxs-lookup"><span data-stu-id="46a46-102">Defining and Browsing KPIs</span></span>
  <span data-ttu-id="46a46-103">Para definir KPIs (indicadores chave de desempenho), você deve definir primeiramente um nome de KPI e o grupo de medidas ao qual o KPI será associado.</span><span class="sxs-lookup"><span data-stu-id="46a46-103">To define key performance indicators (KPIs), you first define a KPI name and the measure group to which the KPI is associated.</span></span> <span data-ttu-id="46a46-104">Um KPI pode ser associado a todos ou apenas a um único grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="46a46-104">A KPI can be associated with all measure groups or with a single measure group.</span></span> <span data-ttu-id="46a46-105">Depois disso, você define os seguintes elementos do KPI:</span><span class="sxs-lookup"><span data-stu-id="46a46-105">You then define the following elements of the KPI:</span></span>

-   <span data-ttu-id="46a46-106">A expressão de valor</span><span class="sxs-lookup"><span data-stu-id="46a46-106">The value expression</span></span>

     <span data-ttu-id="46a46-107">Uma expressão de valor é uma medida física como Vendas, uma medida calculada como Ganho ou um cálculo, que é definida dentro do KPI usando uma expressão MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="46a46-107">A value expression is a physical measure such as Sales, a calculated measure such as Profit, or a calculation that is defined within the KPI by using a Multidimensional Expressions (MDX) expression.</span></span>

-   <span data-ttu-id="46a46-108">A expressão de meta</span><span class="sxs-lookup"><span data-stu-id="46a46-108">The goal expression</span></span>

     <span data-ttu-id="46a46-109">Uma expressão de meta é um valor, ou uma expressão MDX que resolve um valor, que define o destino da medida determinada pela expressão de valor.</span><span class="sxs-lookup"><span data-stu-id="46a46-109">A goal expression is a value, or an MDX expression that resolves to a value, that defines the target for the measure that the value expression defines.</span></span> <span data-ttu-id="46a46-110">Por exemplo, uma expressão de meta pode ser o valor definido pelos gerentes de negócios de uma empresa para aumentar vendas ou ganhos.</span><span class="sxs-lookup"><span data-stu-id="46a46-110">For example, a goal expression could be the amount by which the business managers of a company want to increase sales or profit.</span></span>

-   <span data-ttu-id="46a46-111">A expressão de status</span><span class="sxs-lookup"><span data-stu-id="46a46-111">The status expression</span></span>

     <span data-ttu-id="46a46-112">Uma expressão de status é uma expressão MDX que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usa para avaliar o status atual da expressão de valor comparada com a expressão de meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-112">A status expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current status of the value expression compared to the goal expression.</span></span> <span data-ttu-id="46a46-113">Uma expressão de meta é um valor normalizado entre -1 e +1, onde -1 significa muito ruim e +1 significa muito bom.</span><span class="sxs-lookup"><span data-stu-id="46a46-113">A goal expression is a normalized value in the range of -1 to +1, where -1 is very bad, and +1 is very good.</span></span> <span data-ttu-id="46a46-114">A expressão de status exibe um gráfico para ajudá-lo a determinar de forma fácil o status da expressão de valor comparada com a expressão de meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-114">The status expression displays a graphic to help you easily determine the status of the value expression compared to the goal expression.</span></span>

-   <span data-ttu-id="46a46-115">A expressão de tendência</span><span class="sxs-lookup"><span data-stu-id="46a46-115">The trend expression</span></span>

     <span data-ttu-id="46a46-116">Uma expressão de tendência é uma expressão MDX que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usa para avaliar a tendência atual da expressão de valor comparada com a expressão de meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-116">A trend expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current trend of the value expression compared to the goal expression.</span></span> <span data-ttu-id="46a46-117">Uma expressão de tendência ajuda o usuário empresarial a determinar rapidamente se a expressão de valor está melhorando ou piorando com relação à expressão de meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-117">The trend expression helps the business user to quickly determine whether the value expression is becoming better or worse relative to the goal expression.</span></span> <span data-ttu-id="46a46-118">Você pode associar um dos vários gráficos à expressão de tendência para ajudar os usuários empresariais a entender a tendência.</span><span class="sxs-lookup"><span data-stu-id="46a46-118">You can associate one of several graphics with the trend expression to help business users be able to quickly understand the trend.</span></span>

 <span data-ttu-id="46a46-119">Além destes elementos, você define também várias propriedades de um KPI.</span><span class="sxs-lookup"><span data-stu-id="46a46-119">In addition to these elements that you define for a KPI, you also define several properties of a KPI.</span></span> <span data-ttu-id="46a46-120">Essas propriedades incluem uma pasta de exibição, um KPI pai caso o KPI seja computado de outros KPIs, o atual membro de tempo se houver, o peso de um KPI se houver e uma descrição do KPI.</span><span class="sxs-lookup"><span data-stu-id="46a46-120">These properties include a display folder, a parent KPI if the KPI is computed from other KPIs, the current time member if there is one, the weight of the KPI if it has one, and a description of the KPI.</span></span>

> [!NOTE]
>  <span data-ttu-id="46a46-121">Para obter mais exemplos de KPIs, consulte os exemplos de KPI na guia Modelos do painel Ferramentas de Cálculo ou nos exemplos do data warehouse de exemplo do **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="46a46-121">For more examples of KPIs, see the KPI examples on the Templates tab in the Calculation Tools pane or in the examples in the **Adventure Works DW 2012** sample data warehouse.</span></span> <span data-ttu-id="46a46-122">Para obter mais informações sobre como instalar esse banco de dados, consulte [Instalar dados de exemplo e projetos para o tutorial de modelagem multidimensional do Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="46a46-122">For more information about how to install this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

 <span data-ttu-id="46a46-123">Na tarefa desta lição, você definirá KPIs no projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e depois navegará pelo cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usados esses KPIs.</span><span class="sxs-lookup"><span data-stu-id="46a46-123">In the task in this lesson, you define  KPIs in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, and you then browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube by using these KPIs.</span></span> <span data-ttu-id="46a46-124">Você definirá os seguintes KPIs:</span><span class="sxs-lookup"><span data-stu-id="46a46-124">You will define the following KPIs:</span></span>

-   <span data-ttu-id="46a46-125">Receita do revendedor</span><span class="sxs-lookup"><span data-stu-id="46a46-125">Reseller Revenue</span></span>

     <span data-ttu-id="46a46-126">Este KPI é usado para mensurar como estão as vendas atual do revendedor quando comparadas às cotas de vendas para vendas de revendedores, se as vendas estão próximas da meta e qual a tendência para alcançar a meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-126">This KPI is used to measure how actual reseller sales compare to sales quotas for reseller sales, how close the sales are to the goal, and what the trend is toward reaching the goal.</span></span>

-   <span data-ttu-id="46a46-127">Margem de lucro bruto do produto</span><span class="sxs-lookup"><span data-stu-id="46a46-127">Product Gross Profit Margin</span></span>

     <span data-ttu-id="46a46-128">Este KPI é usado para determinar se a margem de lucro bruto de cada categoria de produto está próxima da meta especificada para cada categoria e também a tendência para alcançar a meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-128">This KPI is used to determine how close the gross profit margin is for each product category to a specified goal for each product category, and also to determine the trend toward reaching this goal.</span></span>

## <a name="defining-the-reseller-revenue-kpi"></a><span data-ttu-id="46a46-129">Definindo o KPI Receita do revendedor</span><span class="sxs-lookup"><span data-stu-id="46a46-129">Defining the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="46a46-130">Abra o Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique na guia **KPIs** .</span><span class="sxs-lookup"><span data-stu-id="46a46-130">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **KPIs** tab.</span></span>

     <span data-ttu-id="46a46-131">A guia **KPIs** inclui vários painéis.</span><span class="sxs-lookup"><span data-stu-id="46a46-131">The **KPIs** tab includes several panes.</span></span> <span data-ttu-id="46a46-132">No lado esquerdo da guia estão os painéis **Organizador de KPI** e **Ferramentas de Cálculo** .</span><span class="sxs-lookup"><span data-stu-id="46a46-132">On the left side of the tab are the **KPI Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="46a46-133">O painel de exibição, localizado na parte central da guia, contém os detalhes do KPI selecionado no painel **Organizador de KPI** .</span><span class="sxs-lookup"><span data-stu-id="46a46-133">The display pane in the middle of the tab contains the details of the KPI that is selected in the **KPI Organizer** pane.</span></span>

     <span data-ttu-id="46a46-134">A imagem a seguir mostra a guia **KPIs** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="46a46-134">The following image shows the **KPIs** tab of Cube Designer.</span></span>

     <span data-ttu-id="46a46-135">![Guia KPIs do Designer de Cubo](../../2014/tutorials/media/l7-kpi-1.gif "Guia KPIs do Designer de Cubo")</span><span class="sxs-lookup"><span data-stu-id="46a46-135">![KPIs tab of Cube Designer](../../2014/tutorials/media/l7-kpi-1.gif "KPIs tab of Cube Designer")</span></span>

2.  <span data-ttu-id="46a46-136">Na barra de ferramentas da guia **KPIs** , clique no botão **Novo KPI** .</span><span class="sxs-lookup"><span data-stu-id="46a46-136">On the toolbar of the **KPIs** tab, click the **New KPI** button.</span></span>

     <span data-ttu-id="46a46-137">Um modelo de KPI em branco aparece no painel de exibição, como mostra a imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="46a46-137">A blank KPI template appears in the display pane, as shown in the following image.</span></span>

     <span data-ttu-id="46a46-138">![Modelo de KPI em branco no painel de exibição](../../2014/tutorials/media/l7-kpi-2.gif "Modelo de KPI em branco no painel de exibição")</span><span class="sxs-lookup"><span data-stu-id="46a46-138">![Blank KPI template in display pane](../../2014/tutorials/media/l7-kpi-2.gif "Blank KPI template in display pane")</span></span>

3.  <span data-ttu-id="46a46-139">Na caixa **nome** , digite e, em `Reseller Revenue` seguida, selecione **vendas do revendedor** na lista **grupo de medidas associado** .</span><span class="sxs-lookup"><span data-stu-id="46a46-139">In the **Name** box, type `Reseller Revenue`, and then select **Reseller Sales** in the **Associated measure group** list.</span></span>

4.  <span data-ttu-id="46a46-140">Na guia **Metadados** do painel **Ferramentas de Cálculo** , expanda **Medidas**e **Vendas do Revendedor**e arraste a medida **Vendas do Revendedor-Valor de Vendas** até a caixa **Expressão de Valor** .</span><span class="sxs-lookup"><span data-stu-id="46a46-140">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Reseller Sales**, and then drag the **Reseller Sales-Sales Amount** measure to the **Value Expression** box.</span></span>

5.  <span data-ttu-id="46a46-141">Na guia **Metadados** do painel **Ferramentas de Cálculo** , expanda **Medidas**e **Cotas de Vendas**e arraste a medida **Cota do Valor de Vendas** até a caixa **Expressão de Meta** .</span><span class="sxs-lookup"><span data-stu-id="46a46-141">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Sales Quotas**, and then drag the **Sales Amount Quota** measure to the **Goal Expression** box.</span></span>

6.  <span data-ttu-id="46a46-142">Verifique se a opção **Medidor** está selecionada na lista **Indicador de status** . Depois, digite a seguinte expressão MDX na caixa **Expressão de status** :</span><span class="sxs-lookup"><span data-stu-id="46a46-142">Verify that **Gauge** is selected in the **Status indicator** list, and then type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
     When 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.95
       Then 1
     When
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")<.95
       And 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.85
       Then 0
      Else-1
    End
    ```

     <span data-ttu-id="46a46-143">Essa expressão MDX fornece a base para avaliar o progresso para atingir a meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-143">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span> <span data-ttu-id="46a46-144">Nessa expressão, se as vendas atuais do revendedor são superiores a 85% da meta, um valor 0 é usado para popular o gráfico escolhido.</span><span class="sxs-lookup"><span data-stu-id="46a46-144">In this MDX expression, if actual reseller sales are more than 85 percent of the goal, a value of 0 is used to populate the chosen graphic.</span></span> <span data-ttu-id="46a46-145">Como um medidor foi o gráfico escolhido, o ponteiro desse medidor ficará no meio, entre vazio e cheio.</span><span class="sxs-lookup"><span data-stu-id="46a46-145">Because a gauge is the chosen graphic, the pointer in the gauge will be half-way between empty and full.</span></span> <span data-ttu-id="46a46-146">Se as vendas atuais do revendedor forem superiores a 90%, o ponteiro do medidor ficará em ¾ entre vazio e cheio.</span><span class="sxs-lookup"><span data-stu-id="46a46-146">If actual reseller sales are more the 90 percent, the pointer on the gauge will be three-fourths of the way between empty and full.</span></span>

7.  <span data-ttu-id="46a46-147">Verifique se a opção **Seta padrão** está selecionada na lista **Indicador de tendência** . Depois, digite a seguinte expressão na caixa **Expressão de tendência** :</span><span class="sxs-lookup"><span data-stu-id="46a46-147">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following expression in the **Trend expression** box:</span></span>

    ```
    Case
     When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
     When  (
      KpiValue("Reseller Revenue") - 
       (KpiValue("Reseller Revenue"), 
        ParallelPeriod
         ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
          /
          (KpiValue ("Reseller Revenue"),
           ParallelPeriod
            ([Date].[Calendar Date].[Calendar Year],1,
             [Date].[Calendar Date].CurrentMember)))
           >=.02
      Then 1
       When(
        KpiValue("Reseller Revenue") - 
         (KpiValue ( "Reseller Revenue" ),
          ParallelPeriod
           ([Date].[Calendar Date].[Calendar Year],1,
            [Date].[Calendar Date].CurrentMember))
           /
            (KpiValue("Reseller Revenue"),
             ParallelPeriod
              ([Date].[Calendar Date].[Calendar Year],1,
                [Date].[Calendar Date].CurrentMember)))
            <=.02
      Then -1
       Else 0
    End
    ```

     <span data-ttu-id="46a46-148">Essa expressão MDX fornece a base para avaliar a tendência para atingir a meta definida.</span><span class="sxs-lookup"><span data-stu-id="46a46-148">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-reseller-revenue-kpi"></a><span data-ttu-id="46a46-149">Navegando no cubo usando o KPI Receita do revendedor</span><span class="sxs-lookup"><span data-stu-id="46a46-149">Browsing the Cube by Using the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="46a46-150">No menu **Compilar** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique em **Implantar Tutorial do Analysis Service**.</span><span class="sxs-lookup"><span data-stu-id="46a46-150">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="46a46-151">Quando a implantação for concluída com êxito, na barra de ferramentas da guia **KPIs** , clique no botão **Exibição de Navegador** e em **Reconectar**.</span><span class="sxs-lookup"><span data-stu-id="46a46-151">When deployment has successfully completed, on the toolbar of the **KPIs** tab, click the **Browser View** button, and then click **Reconnect**.</span></span>

     <span data-ttu-id="46a46-152">Os medidores de status e tendência são exibidos no painel **Navegador KPI** para vendas do revendedor com base nos valores para cada membro padrão de cada dimensão, juntamente com o valor do valor e da meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-152">The status and trend gauges are displayed in the **KPI Browser** pane for reseller sales based on the values for the default member of each dimension, together with the value for the value and the goal.</span></span> <span data-ttu-id="46a46-153">O membro padrão de cada dimensão é o membro Todos do nível Todos, pois você não definiu nenhum outro membro de nenhuma dimensão como membro padrão.</span><span class="sxs-lookup"><span data-stu-id="46a46-153">The default member of each dimension is the All member of the All level, because you have not defined any other member of any dimension as the default member.</span></span>

3.  <span data-ttu-id="46a46-154">No painel de filtros, selecione **Região de Vendas** na lista **Dimensão** , **Regiões de Vendas** na lista **Hierarquia** , **Igual** na lista **Operador** , marque a caixa de seleção **América do Norte** na lista **Expressão de Filtro** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="46a46-154">In the filter pane, select **Sales Territory** in the **Dimension** list, select **Sales Territories** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **North America** check box in the **Filter Expression** list, and then click **OK**.</span></span>

4.  <span data-ttu-id="46a46-155">Na próxima linha do painel **Filtro** , selecione **Data** na lista **Dimensão** , selecione **Data do Calendário** na lista **Hierarquia** , selecione **Igual** na lista **Operador** , marque a caixa de seleção **Q3 CY 2007** na lista **Filtrar Expressão** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="46a46-155">In the next row in the **Filter** pane, select **Date** in the **Dimension** list, select **Calendar Date** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **Q3 CY 2007** check box in the **Filter Expression** list, and then click **OK**.</span></span>

5.  <span data-ttu-id="46a46-156">Clique em qualquer lugar no painel **Navegador KPI** para atualizar os valores do **KPI Receita do Revendedor**.</span><span class="sxs-lookup"><span data-stu-id="46a46-156">Click anywhere in the **KPI Browser** pane to update the values for the **Reseller Revenue KPI**.</span></span>

     <span data-ttu-id="46a46-157">Observe que as seções **Valor**, **Meta**e **Status** do KPI refletem os valores do novo período</span><span class="sxs-lookup"><span data-stu-id="46a46-157">Notice that the **Value**, **Goal**, and **Status** sections of the KPI reflect the values for the new time period</span></span>

## <a name="defining-the-product-gross-profit-margin-kpi"></a><span data-ttu-id="46a46-158">Definindo o KPI Margem de lucro bruto do produto</span><span class="sxs-lookup"><span data-stu-id="46a46-158">Defining the Product Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="46a46-159">Clique no botão **Exibição de Formulário** na barra de ferramentas da guia **KPIs** e clique no botão **Novo KPI** .</span><span class="sxs-lookup"><span data-stu-id="46a46-159">Click the **Form View** button on the toolbar of the **KPIs** tab, and then click the **New KPI** button.</span></span>

2.  <span data-ttu-id="46a46-160">Na caixa **nome** , digite `Product Gross Profit Margin` e, em seguida, verifique se **\<All>** aparece na lista **grupo de medidas associado** .</span><span class="sxs-lookup"><span data-stu-id="46a46-160">In the **Name** box, type `Product Gross Profit Margin`, and then verify that **\<All>** appears in the **Associated measure group** list.</span></span>

3.  <span data-ttu-id="46a46-161">Na guia **Metadados** no painel **Ferramentas de Cálculo** , arraste a medida **MLB Total** até a caixa **Expressão de Valor** .</span><span class="sxs-lookup"><span data-stu-id="46a46-161">In the **Metadata** tab in the **Calculation Tools** pane, drag the **Total GPM** measure to the **Value Expression** box.</span></span>

4.  <span data-ttu-id="46a46-162">Na caixa **Expressão de Meta** , digite a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="46a46-162">In the **Goal Expression** box, type the following expression:</span></span>

    ```
    Case
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Accessories]
        Then .40                 
        When [Product].[Category].CurrentMember 
          Is [Product].[Category].[Bikes]
        Then .12                
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Clothing]
        Then .20
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Components]
        Then .10
        Else .12            
    End
    ```

5.  <span data-ttu-id="46a46-163">Na lista **Indicador de status** , selecione **Cilindro**.</span><span class="sxs-lookup"><span data-stu-id="46a46-163">In the **Status indicator** list, select **Cylinder**.</span></span>

6.  <span data-ttu-id="46a46-164">Digite a seguinte expressão MDX na caixa **Expressão de status** :</span><span class="sxs-lookup"><span data-stu-id="46a46-164">Type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .90
        Then 1
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) <  .90
             And 
             KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .80
        Then 0
        Else -1
    End
    ```

     <span data-ttu-id="46a46-165">Essa expressão MDX fornece a base para avaliar o progresso para atingir a meta.</span><span class="sxs-lookup"><span data-stu-id="46a46-165">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span>

7.  <span data-ttu-id="46a46-166">Verifique se **Seta padrão** está selecionada na lista **Indicador de tendência** . Depois, digite a seguinte expressão MDX na caixa **Expressão de tendência** :</span><span class="sxs-lookup"><span data-stu-id="46a46-166">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following MDX expression in the **Trend expression** box:</span></span>

    ```
    Case
    When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
       When VBA!Abs
        (
          KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            ) /
            (
              KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            )  
          ) <=.02
      Then 0
      When KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[ Calendar Date].[ Calendar Year],
               1,
               [Date].[ Calendar Date].CurrentMember
             )
           ) /
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[Calendar Date].[Calendar Year],
               1,
               [Date].[Calendar Date].CurrentMember
             )
           )  >.02
      Then 1
      Else -1
    End
    ```

     <span data-ttu-id="46a46-167">Essa expressão MDX fornece a base para avaliar a tendência para atingir a meta definida.</span><span class="sxs-lookup"><span data-stu-id="46a46-167">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-total-gross-profit-margin-kpi"></a><span data-ttu-id="46a46-168">Navegando no cubo usando o KPI Margem de lucro bruto total</span><span class="sxs-lookup"><span data-stu-id="46a46-168">Browsing the Cube by Using the Total Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="46a46-169">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Service**.</span><span class="sxs-lookup"><span data-stu-id="46a46-169">On the **Build** menu, click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="46a46-170">Quando a implantação for concluída com êxito, clique no botão **Reconectar** na barra de ferramentas da guia **KPIs** e clique em **Exibição de Navegador**.</span><span class="sxs-lookup"><span data-stu-id="46a46-170">When deployment has successfully completed, click **Reconnect** on the toolbar of the **KPIs** tab, and then click **Browser View**.</span></span>

     <span data-ttu-id="46a46-171">O `Product Gross Profit Margin` KPI é exibido e exibe o valor do KPI para **Q3 CY 2007** e o **América do Norte** território Sales.</span><span class="sxs-lookup"><span data-stu-id="46a46-171">The `Product Gross Profit Margin` KPI appears and displays the KPI value for **Q3 CY 2007** and the **North America** sales territory.</span></span>

3.  <span data-ttu-id="46a46-172">No painel **Filtro** , selecione **Produto** na lista **Dimensão** , **Categoria** na lista **Hierarquia** , **Igual** na lista **Operador** , **Bicicletas** na lista **Expressão de Filtro** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="46a46-172">In the **Filter** pane, select **Product** in the **Dimension** list, select **Category** in the **Hierarchy** list, select **Equal** in the **Operator** list, and then select **Bikes** in the **Filter Expression** list, and then click **OK**.</span></span>

     <span data-ttu-id="46a46-173">A margem de lucro bruto para a venda de bicicletas dos revendedores na América do Norte no período Q3 CY 2007 é exibida.</span><span class="sxs-lookup"><span data-stu-id="46a46-173">The gross profit margin for the sale of Bikes by resellers in North America in Q3 CY 2007 appears.</span></span>

## <a name="next-lesson"></a><span data-ttu-id="46a46-174">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="46a46-174">Next Lesson</span></span>
 [<span data-ttu-id="46a46-175">Lição 8: Como definir ações</span><span class="sxs-lookup"><span data-stu-id="46a46-175">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)


