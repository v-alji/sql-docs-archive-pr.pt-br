---
title: Filtrando uma tabela aninhada em um modelo de mineração (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0a3ae0e5-897b-4898-a60d-5455eec3d305
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1e6ce2936a3c6763ea41999b2724c0fe8c79301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684425"
---
# <a name="filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="dd5cf-102">Filtrando uma tabela aninhada em um modelo de mineração (tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="dd5cf-102">Filtering a Nested Table in a Mining Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="dd5cf-103">Após criar e explorar o modelo, você decide que deseja enfatizar um subconjunto dos dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-103">After you have created and explored the model, you decide that you want to focus on a subset of the customer data.</span></span> <span data-ttu-id="dd5cf-104">Por exemplo, talvez você queira analisar apenas as cestas que contêm um determinado item ou os dados demográficos de clientes que não compraram nada em um certo período.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-104">For example, you might want to analyze only the baskets that contain a specific item, or to analyze the demographics of customers who have not purchased anything in a certain period.</span></span>  
  
 <span data-ttu-id="dd5cf-105">O [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fornece a capacidade para filtrar os dados que são usados em um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-105">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides the ability to filter the data that is used in a mining model.</span></span> <span data-ttu-id="dd5cf-106">Esse recurso é útil porque você não precisa configurar uma nova exibição da fonte de dados para usar dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-106">This feature is useful because you do not need to set up a new data source view to use different data.</span></span> <span data-ttu-id="dd5cf-107">No Tutorial de mineração de dados básico, você aprendeu a filtrar dados de uma tabela simples aplicando condições à tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-107">In the Basic Data Mining Tutorial, you learned how to filter data from a flat table by applying conditions to the case table.</span></span> <span data-ttu-id="dd5cf-108">Nesta tarefa, você criará um filtro que se aplica a uma tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-108">In this task, you create a filter that applies to a nested table.</span></span>  
  
## <a name="filters-on-nested-vs-case-tables"></a><span data-ttu-id="dd5cf-109">Filtros em tabelas aninhadas vs. tabelas de casos</span><span class="sxs-lookup"><span data-stu-id="dd5cf-109">Filters on Nested vs. Case Tables</span></span>  
 <span data-ttu-id="dd5cf-110">Se a sua exibição de fonte de dados contiver uma tabela de casos e uma tabela aninhada, como a exibição da fonte de dados usada no modelo de Associação, você poderá filtrar os valores da tabela de casos, a presença ou a ausência de um valor na tabela aninhada ou uma combinação de ambos.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-110">If your data source view contains a case table and a nested table, like the data source view used in the Association model, you can filter on values from the case table, the presence or absence of a value in the nested table, or some combination of both.</span></span>  
  
 <span data-ttu-id="dd5cf-111">Nesta tarefa, primeiro você fará uma cópia do modelo de Associação e depois adicionará os atributos IncomeGroup e Region ao novo modelo relacionado, para que possa filtrar os atributos na tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-111">In this task, you will first make a copy of the Association model and then add the IncomeGroup and Region attributes to the new related model, so that you can filter on those attributes in the case table.</span></span>  
  
#### <a name="to-create-and-modify-a-copy-of-the-association-model"></a><span data-ttu-id="dd5cf-112">Para criar e modificar uma cópia do modelo de Associação</span><span class="sxs-lookup"><span data-stu-id="dd5cf-112">To create and modify a copy of the Association model</span></span>  
  
1.  <span data-ttu-id="dd5cf-113">Na guia **modelos de mineração** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , clique com o botão direito do mouse no `Association` modelo e selecione **novo modelo de mineração**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-113">In the **Mining Models** tab of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click the `Association` model, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="dd5cf-114">Para **nome do modelo**, digite `Association Filtered` .</span><span class="sxs-lookup"><span data-stu-id="dd5cf-114">For **Model Name**, type `Association Filtered`.</span></span> <span data-ttu-id="dd5cf-115">Para **nome do algoritmo**, selecione **regras de associação da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-115">For **Algorithm Name**, select **Microsoft Association Rules**.</span></span> <span data-ttu-id="dd5cf-116">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-116">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="dd5cf-117">Na coluna para o modelo filtrado de associação, clique na linha do Associationgroup e altere o valor de **ignorar** para **entrada**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-117">In the column for the Association Filtered model, click the IncomeGroup row and change the value from **Ignore** to **Input**.</span></span>  
  
 <span data-ttu-id="dd5cf-118">Em seguida, você criará um filtro na tabela de casos no novo modelo de associação.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-118">Next, you will create a filter on the case table in the new association model.</span></span> <span data-ttu-id="dd5cf-119">O filtro passará ao modelo apenas os clientes na região de destino ou com o nível de renda de destino.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-119">The filter will pass to the model only the customers in the target region or with the target income level.</span></span> <span data-ttu-id="dd5cf-120">Depois, você adicionará um segundo conjunto de condições de filtro para especificar se o modelo usa apenas clientes cujas cestas de compras continham pelo menos um item.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-120">Then, you will add a second set of filter conditions to specify that the model uses only customers whose shopping baskets contained at least one item.</span></span>  
  
#### <a name="to-add-a-filter-to-a-mining-model"></a><span data-ttu-id="dd5cf-121">Para adicionar um filtro a um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="dd5cf-121">To add a filter to a mining model</span></span>  
  
1.  <span data-ttu-id="dd5cf-122">Na guia **modelos de mineração** , clique com o botão direito do mouse na associação de modelo filtrada e selecione **definir filtro de modelo**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-122">In the **Mining Models** tab, right-click the model Association Filtered, and select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="dd5cf-123">Na caixa de diálogo **Filtro de Modelos** , clique na linha superior da grade, na caixa de texto **Coluna da Estrutura de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="dd5cf-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
3.  <span data-ttu-id="dd5cf-124">Na caixa de texto **coluna da estrutura de mineração** , selecione invir.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-124">In the **Mining Structure Column** text box, select IncomeGroup.</span></span>  
  
     <span data-ttu-id="dd5cf-125">O ícone no lado esquerdo da caixa de texto é alterado para indicar que o item selecionado é uma coluna.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-125">The icon at the left side of the text box changes to indicate that the selected item is a column.</span></span>  
  
4.  <span data-ttu-id="dd5cf-126">Clique na caixa de texto **operador** e selecione o **=** operador na lista.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-126">Click the **Operator** text box and select the **=** operator from the list.</span></span>  
  
5.  <span data-ttu-id="dd5cf-127">Clique na caixa de texto **valor** e digite `High` na caixa.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-127">Click the **Value** text box, and type `High` in the box.</span></span>  
  
6.  <span data-ttu-id="dd5cf-128">Na grade, clique na linha seguinte.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-128">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="dd5cf-129">Clique na caixa de texto **e/ou** na próxima linha da grade e selecione **ou**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-129">Click the **AND/OR** text box in the next row of the grid and select **OR**.</span></span>  
  
8.  <span data-ttu-id="dd5cf-130">Na caixa de texto **coluna da estrutura de mineração** , selecione invir.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-130">In the **Mining Structure Column** text box, select IncomeGroup.</span></span> <span data-ttu-id="dd5cf-131">Na caixa de texto **valor** , digite `Moderate` .</span><span class="sxs-lookup"><span data-stu-id="dd5cf-131">In the **Value** text box, type `Moderate`.</span></span>  
  
     <span data-ttu-id="dd5cf-132">A condição de filtro que você criou é automaticamente adicionada à caixa de texto **expressão** e deve aparecer da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dd5cf-132">The filter condition that you created is automatically added to the **Expression** text box, and should appears as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate'`  
  
9. <span data-ttu-id="dd5cf-133">Clique na próxima linha da grade, deixando o operador como o padrão **e**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-133">Click the next row in the grid, leaving the operator as the default, **AND**.</span></span>  
  
10. <span data-ttu-id="dd5cf-134">Para **operador**, deixe o valor padrão, **contém**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-134">For **Operator**, leave the default value, **Contains**.</span></span> <span data-ttu-id="dd5cf-135">Clique na caixa de texto **valor** .</span><span class="sxs-lookup"><span data-stu-id="dd5cf-135">Click the **Value** text box.</span></span>  
  
11. <span data-ttu-id="dd5cf-136">Na caixa de diálogo **filtro** , na primeira linha na **coluna estrutura de mineração**, selecione `Model` .</span><span class="sxs-lookup"><span data-stu-id="dd5cf-136">In the **Filter** dialog box, in the first row under **Mining Structure Column**, select `Model`.</span></span>  
  
12. <span data-ttu-id="dd5cf-137">Para **operador**, Select **não é nulo**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-137">For **Operator**, select **IS NOT NULL**.</span></span> <span data-ttu-id="dd5cf-138">Deixe a caixa de texto **valor** em branco.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-138">Leave the **Value** text box blank.</span></span> <span data-ttu-id="dd5cf-139">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-139">Click **OK**.</span></span>  
  
     <span data-ttu-id="dd5cf-140">A condição de filtro na caixa de texto **expressão** da caixa de diálogo **filtro de modelo** é atualizada automaticamente para incluir a nova condição na tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-140">The filter condition in the **Expression** text box of the **Model Filter** dialog box is automatically updated to include the new condition on the nested table.</span></span> <span data-ttu-id="dd5cf-141">A expressão completa é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd5cf-141">The completed expression is as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate' AND EXISTS SELECT * FROM [vAssocSeqLineItems] WHERE [Model] <> NULL).`  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)] ``  
  
#### <a name="to-enable-drillthrough-and-to-process-the-filtered-model"></a><span data-ttu-id="dd5cf-142">Para habilitar a busca detalhada e processar o modelo filtrado</span><span class="sxs-lookup"><span data-stu-id="dd5cf-142">To enable drillthrough and to process the filtered model</span></span>  
  
1.  <span data-ttu-id="dd5cf-143">Na guia **modelos de mineração** , clique com o botão direito do mouse no `Association Filtered` modelo e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-143">In the **Mining Models** tab, right-click the `Association Filtered` model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="dd5cf-144">Altere a propriedade **AllowDrillThrough** para **true**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-144">Change the **AllowDrillThrough** property to **True**.</span></span>  
  
3.  <span data-ttu-id="dd5cf-145">Clique com o botão direito do mouse no `Association Filtered` modelo de mineração e selecione **modelo de processo**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-145">Right-click the `Association Filtered` mining model, and select **Process Model**.</span></span>  
  
4.  <span data-ttu-id="dd5cf-146">Clique em **Sim** na mensagem de erro para implantar o novo modelo no [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-146">Click **Yes** in the error message to deploy the new model to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
5.  <span data-ttu-id="dd5cf-147">Na caixa de diálogo **processar estrutura de mineração** , clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-147">In the **Process Mining Structure** dialog box, click **Run**.</span></span>  
  
6.  <span data-ttu-id="dd5cf-148">Quando o processamento estiver concluído, clique em **fechar** para sair da caixa de diálogo **progresso do processo** e clique em **Fechar** novamente para sair da caixa de diálogo **processar estrutura de mineração** .</span><span class="sxs-lookup"><span data-stu-id="dd5cf-148">When processing is complete click **Close** to exit the **Process Progress** dialog box, and click **Close** again to exit the **Process Mining Structure** dialog box.</span></span>  
  
 <span data-ttu-id="dd5cf-149">Para verificar, use o visualizador da Árvore de Conteúdo Genérico da Microsoft e examine o valor de NODE_SUPPORT em que o modelo filtrado contém menos casos do que o original.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-149">You can verify by using the Microsoft Generic Content Tree viewer and looking at the value for NODE_SUPPORT that the filtered model contains fewer cases than the original model.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd5cf-150">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd5cf-150">Remarks</span></span>  
 <span data-ttu-id="dd5cf-151">O filtro de tabela aninhada que você acabou de criar verifica apenas a presença de pelo menos uma linha na tabela aninhada; no entanto, também é possível criar condições de filtro que verificam a presença de produtos específicos.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-151">The nested table filter that you just created checks only for the presence of at least one row in the nested table; however, you can also create filter conditions that check for the presence of specific products.</span></span>  <span data-ttu-id="dd5cf-152">Por exemplo, você pode criar o seguinte filtro:</span><span class="sxs-lookup"><span data-stu-id="dd5cf-152">For example, you could create the following filter:</span></span>  
  
```  
[IncomeGroup] = 'High' AND  
 EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] = 'Water Bottle' )   
```  
  
 <span data-ttu-id="dd5cf-153">Esta instrução significa que você está restringindo os clientes da tabela de casos a apenas aqueles que compraram uma garrafa de água.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-153">This statement means that you are restricting the customers from the case table to only those who have purchased a water bottle.</span></span> <span data-ttu-id="dd5cf-154">No entanto, como o número de atributos da tabela aninhada é potencialmente ilimitado, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] não fornece a lista dos possíveis valores a serem selecionados.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-154">However, because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="dd5cf-155">Em vez disso, você deve digitar o valor exato.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-155">Instead, you must type the exact value.</span></span>  
  
 <span data-ttu-id="dd5cf-156">Você pode clicar em **Editar consulta** para alterar manualmente a expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-156">You can click **Edit Query** to manually change the filter expression.</span></span> <span data-ttu-id="dd5cf-157">No entanto, se você alterar manualmente qualquer parte da expressão de filtro, a grade será desabilitada e, assim sendo, você deverá trabalhar com a expressão de filtro apenas no modo de edição de texto.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-157">However, if you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="dd5cf-158">Para restaurar o modo de edição da grade, você deve apagar a expressão de filtro e iniciar novamente.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-158">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="dd5cf-159">Você não pode usar o operador LIKE em um filtro de tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="dd5cf-159">You cannot use the LIKE operator in a nested table filter.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dd5cf-160">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="dd5cf-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dd5cf-161">Prevendo associações &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="dd5cf-161">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd5cf-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd5cf-162">See Also</span></span>  
 <span data-ttu-id="dd5cf-163">[Sintaxe de filtro de modelo e exemplos &#40;mineração de dados Analysis Services&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="dd5cf-163">[Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="dd5cf-164">Filtros para modelos de mineração &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="dd5cf-164">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
