---
title: Aplicar um filtro a um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filters [data mining]
- filtering input rows [Analysis Services]
- filtering data [Analysis Services]
ms.assetid: 4d0abeb5-e939-46d3-9097-6e0358244300
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9f3147c36e69d9c2249d5bf6d1ba201799c6e27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576064"
---
# <a name="apply-a-filter-to-a-mining-model"></a><span data-ttu-id="0a755-102">Aplicar um filtro a um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="0a755-102">Apply a Filter to a Mining Model</span></span>
  <span data-ttu-id="0a755-103">Se a sua estrutura de mineração tiver uma tabela aninhada, você poderá aplicar um filtro à tabela de casos, à tabela aninhada ou a ambas.</span><span class="sxs-lookup"><span data-stu-id="0a755-103">If your mining structure contains a nested table, you can apply a filter to the case table, the nested table, or both.</span></span>  
  
 <span data-ttu-id="0a755-104">O procedimento a seguir indica como criar os dois tipos de filtros: filtros de caso e filtros nas linhas da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="0a755-104">The following procedure demonstrates how to create both kinds of filters: case filters, and filters on the nested table rows.</span></span>  
  
 <span data-ttu-id="0a755-105">A condição na tabela de casos restringe os clientes àqueles com renda entre 30000 e 40000.</span><span class="sxs-lookup"><span data-stu-id="0a755-105">The condition on the case table restricts customers to those with income between 30000 and 40000.</span></span> <span data-ttu-id="0a755-106">A condição na tabela aninhada restringe os clientes àqueles que não compraram um item específico.</span><span class="sxs-lookup"><span data-stu-id="0a755-106">The condition on the nested table restricts the customers to those who did not purchase a particular item.</span></span>  
  
 <span data-ttu-id="0a755-107">A condição completa do filtro criada neste exemplo é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="0a755-107">The complete filter condition created in this example is as follows:</span></span>  
  
```  
[Income] > '30000'   
AND  [Income] < '40000'   
AND EXISTS (SELECT * FROM [<nested table name>]   
WHERE [Model] <> 'Water Bottle' )   
```  
  
### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="0a755-108">Para criar um filtro de caso em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="0a755-108">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="0a755-109">Em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], no Gerenciador de Soluções, clique na estrutura de mineração que contém o modelo de mineração a filtrar.</span><span class="sxs-lookup"><span data-stu-id="0a755-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="0a755-110">Clique na guia **Modelos de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="0a755-110">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="0a755-111">Selecione o modelo, e clique com o botão direito do mouse para abrir o menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="0a755-111">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="0a755-112">- ou -</span><span class="sxs-lookup"><span data-stu-id="0a755-112">-or-</span></span>  
  
     <span data-ttu-id="0a755-113">Selecione o modelo.</span><span class="sxs-lookup"><span data-stu-id="0a755-113">Select the model.</span></span> <span data-ttu-id="0a755-114">Em seguida, no menu **Modelo de Mineração** , selecione **Definir Filtro de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="0a755-114">Then, on the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="0a755-115">Na caixa de diálogo **Filtro de Modelos** , clique na linha superior da grade, na caixa de texto **Coluna da Estrutura de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="0a755-115">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
5.  <span data-ttu-id="0a755-116">Se a fonte de dados tiver uma tabela simples, a listagem suspensa exibirá somente os nomes das colunas nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="0a755-116">If the data source contains a single flat table, the drop-down list displays only the names of the columns in that table.</span></span>  
  
     <span data-ttu-id="0a755-117">Se a estrutura de mineração tiver várias tabelas, a lista mostrará os nomes das tabelas de origem.</span><span class="sxs-lookup"><span data-stu-id="0a755-117">If the mining structure contains multiple tables, the list shows the names of the source tables.</span></span> <span data-ttu-id="0a755-118">Os nomes de coluna não são exibidos enquanto não for selecionada uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0a755-118">The column names do not display until a table has been selected.</span></span>  
  
     <span data-ttu-id="0a755-119">Se a sua estrutura de mineração tiver uma tabela de casos e uma tabela aninhada, a listagem suspensa indicará as colunas da tabela de casos e o nome da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="0a755-119">If the mining structure contains a case table and a nested table, the drop-down list shows columns from the case table, and the name of the nested table.</span></span>  
  
6.  <span data-ttu-id="0a755-120">Selecione uma coluna na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="0a755-120">Select a column from the drop-down list.</span></span>  
  
     <span data-ttu-id="0a755-121">O ícone no lado esquerdo da caixa de texto muda para indicar que o item selecionado é uma tabela ou uma coluna.</span><span class="sxs-lookup"><span data-stu-id="0a755-121">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
7.  <span data-ttu-id="0a755-122">Clique na caixa de texto **Operador** e selecione um operador na lista.</span><span class="sxs-lookup"><span data-stu-id="0a755-122">Click the **Operator** text box and select an operator from the list.</span></span> <span data-ttu-id="0a755-123">Os operadores válidos são alterados dependendo do tipo de dados da coluna que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="0a755-123">The valid operators change depending on the data type of the column you selected.</span></span>  
  
8.  <span data-ttu-id="0a755-124">Clique na caixa de texto **Valor** e digite um valor na caixa.</span><span class="sxs-lookup"><span data-stu-id="0a755-124">Click the **Value** text box, and type a value in the box.</span></span>  
  
     <span data-ttu-id="0a755-125">Por exemplo, selecione `Income` como a coluna, selecione o operador maior que (>) e, em seguida, digite `30000` .</span><span class="sxs-lookup"><span data-stu-id="0a755-125">For example, select `Income` as the column, select the greater than operator (>), and then type `30000`.</span></span>  
  
9. <span data-ttu-id="0a755-126">Na grade, clique na linha seguinte.</span><span class="sxs-lookup"><span data-stu-id="0a755-126">Click the next row in the grid.</span></span>  
  
     <span data-ttu-id="0a755-127">A condição do filtro que você criou é automaticamente adicionada à caixa de texto Expressão.</span><span class="sxs-lookup"><span data-stu-id="0a755-127">The filter condition that you created is automatically added to the Expression text box.</span></span> <span data-ttu-id="0a755-128">Por exemplo, `[Income] > '30000'`</span><span class="sxs-lookup"><span data-stu-id="0a755-128">For example, `[Income] > '30000'`</span></span>  
  
10. <span data-ttu-id="0a755-129">Clique na caixa de texto **AND/OR** na linha seguinte da grade para adicionar uma condição.</span><span class="sxs-lookup"><span data-stu-id="0a755-129">Click the **AND/OR** text box in the next row of the grid to add a condition.</span></span>  
  
     <span data-ttu-id="0a755-130">Por exemplo, para criar uma condição BETWEEN, selecione `AND` na lista suspensa de operandos lógicos.</span><span class="sxs-lookup"><span data-stu-id="0a755-130">For example, to create a BETWEEN condition, select `AND` from the drop-down list of logical operands.</span></span>  
  
11. <span data-ttu-id="0a755-131">Selecione um operador e digite um valor conforme descrito nas etapas 7 e 8.</span><span class="sxs-lookup"><span data-stu-id="0a755-131">Select an operator and type a value as described in Steps 7 and 8.</span></span>  
  
     <span data-ttu-id="0a755-132">Por exemplo, selecione `Income` como a coluna novamente, selecione o operador menor que (<) e, em seguida, digite `40000` .</span><span class="sxs-lookup"><span data-stu-id="0a755-132">For example, select `Income` as the column again, select the less than operator (<), and then type `40000`.</span></span>  
  
12. <span data-ttu-id="0a755-133">Na grade, clique na linha seguinte.</span><span class="sxs-lookup"><span data-stu-id="0a755-133">Click the next row in the grid.</span></span>  
  
13. <span data-ttu-id="0a755-134">A condição de filtro na caixa de texto Expressão é atualizada automaticamente para incluir a nova condição.</span><span class="sxs-lookup"><span data-stu-id="0a755-134">The filter condition in the Expression text box is automatically updated to include the new condition.</span></span> <span data-ttu-id="0a755-135">A expressão completa é a seguinte: `[Income] > '30000'AND [Income] < '40000'`</span><span class="sxs-lookup"><span data-stu-id="0a755-135">The completed expression is as follows: `[Income] > '30000'AND [Income] < '40000'`</span></span>  
  
### <a name="to-add-a-filter-on-the-nested-table-in-a-mining-model"></a><span data-ttu-id="0a755-136">Para adicionar um filtro na tabela aninhada em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="0a755-136">To add a filter on the nested table in a mining model</span></span>  
  
1.  <span data-ttu-id="0a755-137">Na caixa de diálogo \*\* \<name> filtro de modelo\*\* , clique em uma linha vazia na grade na **coluna estrutura de mineração**.</span><span class="sxs-lookup"><span data-stu-id="0a755-137">In the **\<name>Model Filter** Dialog box, click an empty row in the grid under **Mining Structure Column**.</span></span>  
  
2.  <span data-ttu-id="0a755-138">Selecione o nome da tabela aninhada na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="0a755-138">Select the name of the nested table from the drop-down list.</span></span>  
  
     <span data-ttu-id="0a755-139">O ícone no lado esquerdo da caixa de texto muda para indicar que o item selecionado é o nome de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0a755-139">The icon at the left side of the text box changes to indicate that the selected item is the name of a table.</span></span>  
  
3.  <span data-ttu-id="0a755-140">Clique na caixa de texto **Operador** e selecione **Contém** ou **Não Contém**.</span><span class="sxs-lookup"><span data-stu-id="0a755-140">Click the **Operator** text box and select **Contains** or **Not Contain**.</span></span>  
  
     <span data-ttu-id="0a755-141">Essas são as únicas condições disponíveis para a tabela aninhada na caixa de diálogo **Filtro de Modelos** , pois você está restringindo a tabela de casos a apenas aqueles que têm um determinado valor na tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="0a755-141">These are the only conditions available for the nested table in the **Model Filter** dialog box, because you are restricting the case table to only those cases that contain a certain value in the nested table.</span></span> <span data-ttu-id="0a755-142">Você definirá o valor da condição na tabela aninhada na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="0a755-142">You will set the value for the condition on the nested table in the next step.</span></span>  
  
4.  <span data-ttu-id="0a755-143">Clique na caixa **valor** e, em seguida, clique no botão **(...)** para criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="0a755-143">Click the **Value** box, and then click the **(...)** button to build an expression.</span></span>  
  
     <span data-ttu-id="0a755-144">A caixa de diálogo \*\* \<name> Filtrar\*\* é aberta.</span><span class="sxs-lookup"><span data-stu-id="0a755-144">The **\<name>Filter** dialog box opens.</span></span> <span data-ttu-id="0a755-145">Essa caixa de diálogo só pode definir condições na tabela atual, que neste caso é a tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="0a755-145">This dialog box can set conditions only on the current table, which in this case is the nested table.</span></span>  
  
5.  <span data-ttu-id="0a755-146">Clique na caixa **Coluna da Estrutura de Mineração** e selecione o nome de coluna nas listas suspensas das colunas da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="0a755-146">Click the **Mining Structure Column** box and select a column name from the dropdown lists of nested table columns.</span></span>  
  
6.  <span data-ttu-id="0a755-147">Clique em **Operador** e selecione um operador na lista de operadores válidos para a coluna.</span><span class="sxs-lookup"><span data-stu-id="0a755-147">Click **Operator** and select an operator from the list of valid operators for the column.</span></span>  
  
7.  <span data-ttu-id="0a755-148">Clique em **Valor** e digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0a755-148">Click **Value** and type a value.</span></span>  
  
     <span data-ttu-id="0a755-149">Por exemplo, para **coluna da estrutura de mineração,** selecione `Model` .</span><span class="sxs-lookup"><span data-stu-id="0a755-149">For example, for **Mining Structure Column,** select `Model`.</span></span> <span data-ttu-id="0a755-150">Para **operador**, selecione `<>` e digite o valor `Water Bottle` .</span><span class="sxs-lookup"><span data-stu-id="0a755-150">For **Operator**, select `<>`, and type the value `Water Bottle`.</span></span> <span data-ttu-id="0a755-151">Essa condição cria a seguinte expressão de filtro:</span><span class="sxs-lookup"><span data-stu-id="0a755-151">This condition creates the following filter expression:</span></span>  
  
```  
EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] <> 'Water Bottle' )   
```  
  
> [!NOTE]  
>  <span data-ttu-id="0a755-152">Como o número de atributos da tabela aninhada é potencialmente ilimitado, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não fornece a lista dos possíveis valores a serem selecionados.</span><span class="sxs-lookup"><span data-stu-id="0a755-152">Because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="0a755-153">Você deve digitar o valor exato.</span><span class="sxs-lookup"><span data-stu-id="0a755-153">You must type the exact value.</span></span> <span data-ttu-id="0a755-154">Você não pode usar um operador LIKE em uma tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="0a755-154">Also, you cannot use a LIKE operator in a nested table.</span></span>  
  
1.  <span data-ttu-id="0a755-155">Adicione mais condições conforme necessário, combinando as condições selecionando `AND` ou `OR` na caixa **e/ou** no lado esquerdo da grade de **condições** .</span><span class="sxs-lookup"><span data-stu-id="0a755-155">Add more conditions as necessary, combining the conditions by selecting `AND` or `OR` in the **AND/OR** box at the left side of the **Conditions** grid.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="0a755-156">Na caixa de diálogo **Filtro de Modelos** , examine as condições que você criou usando a caixa de diálogo **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="0a755-156">In the **Model Filter** dialog box, review the conditions that you created by using the **Filter** dialog box.</span></span> <span data-ttu-id="0a755-157">As condições para a tabela aninhada são acrescentadas às condições da tabela de casos, e o conjunto completo das condições de filtro é exibido na caixa de texto **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="0a755-157">The conditions for the nested table are appended to the conditions for the case table, and the complete set of filter conditions is displayed in the **Expression** text box.</span></span>  
  
3.  <span data-ttu-id="0a755-158">Se desejar, clique em **Editar Consulta** para alterar manualmente a expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="0a755-158">Optionally, click **Edit Query** to manually change the filter expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a755-159">Se você alterar manualmente qualquer parte da expressão de filtro, a grade será desabilitada e, assim sendo, você deverá trabalhar com a expressão de filtro apenas no modo de edição de texto.</span><span class="sxs-lookup"><span data-stu-id="0a755-159">If you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="0a755-160">Para restaurar o modo de edição da grade, você deve apagar a expressão de filtro e iniciar novamente.</span><span class="sxs-lookup"><span data-stu-id="0a755-160">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="0a755-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a755-161">See Also</span></span>  
 <span data-ttu-id="0a755-162">[Filtros para modelos de mineração &#40;mineração de dados Analysis Services&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="0a755-162">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="0a755-163">[Tarefas e instruções do modelo de mineração](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="0a755-163">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="0a755-164">Excluir um filtro de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="0a755-164">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
