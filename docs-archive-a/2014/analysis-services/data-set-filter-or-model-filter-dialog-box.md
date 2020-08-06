---
title: Caixa de diálogo Filtro de conjunto de dados ou filtro de modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9602174-b7e2-4e16-8ded-dfd8eb9264d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa796cd8cb23894c059deba411b3e1d6676e3b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681275"
---
# <a name="data-set-filter-or-model-filter-dialog-box"></a><span data-ttu-id="51872-102">Caixa de Diálogo Filtro de Conjunto de Dados ou Filtro de Modelo</span><span class="sxs-lookup"><span data-stu-id="51872-102">Data Set Filter or Model Filter Dialog Box</span></span>
  <span data-ttu-id="51872-103">Esta caixa de diálogo o ajuda a construir os filtros que você pode aplicar a um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="51872-103">This dialog box helps you build the filters that you can apply to a data set.</span></span>  <span data-ttu-id="51872-104">O conjunto de dados pode ser um conjunto externo usado para teste ou os dados do caso para um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="51872-104">The data set can be an external data set used for testing, or the case data for a mining model.</span></span> <span data-ttu-id="51872-105">O nome da caixa de diálogo irá mudar dependendo se o filtro for para um conjunto de dados externo ou para um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="51872-105">The name of the dialog box changes depending on whether the filter is for an external data set or for a mining model.</span></span>  
  
 <span data-ttu-id="51872-106">Se você aplica o filtro para um novo conjunto de dados, o modelo de mineração de dados é avaliado usando somente aqueles casos no conjunto de dados que atendam as condições.</span><span class="sxs-lookup"><span data-stu-id="51872-106">If you apply the filter to a new data set, the data mining model is evaluated by using only those cases in the data set that meet the conditions.</span></span> <span data-ttu-id="51872-107">Se você aplica o filtro para o próprio modelo de mineração, o modelo será treinado e testado usando somente os casos, no conjunto de dados de teste existente, que atendam os critérios do filtro.</span><span class="sxs-lookup"><span data-stu-id="51872-107">If you apply the filter to the mining model itself, the model will be trained and tested by using only the cases in the existing test data set that meet the filter criteria.</span></span>  
  
-   <span data-ttu-id="51872-108">A caixa de diálogo **Filtro de Conjunto de Dados** está disponível na guia **Seleção de Entrada** do designer **Gráfico de Precisão de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="51872-108">The **Data Set Filter** dialog box is available from the **Input Selection** tab of the **Mining Accuracy Chart** designer.</span></span>  
  
-   <span data-ttu-id="51872-109">A caixa de diálogo **Filtrar Modelos** está disponível na guia **Modelos de Mineração** do Designer de Data Mining.</span><span class="sxs-lookup"><span data-stu-id="51872-109">The **Model Filter** dialog box is available from the **Mining Models** tab of the Data Miningdesigner.</span></span>  
  
-   <span data-ttu-id="51872-110">A grade **Condições** contém colunas nas quais você pode especificar uma tabela ou nome de coluna, um operador e valores de destino.</span><span class="sxs-lookup"><span data-stu-id="51872-110">The **Conditions** grid contains columns where you can specify a table or column name, an operator, and target values.</span></span> <span data-ttu-id="51872-111">Usando esta grade você está essencialmente criando uma cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="51872-111">By using this grid you are essentially creating a WHERE clause.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="51872-112">Para testar a precisão em um subconjunto dos dados originais de treinamento, é possível adicionar a exibição de fonte de dados que foi utilizada para definir o conjunto de treinamento como dados externos de teste e então adicionar as condições na grade **Filtro de Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="51872-112">To test accuracy on a subset of the original training data, you can add the data source view that was used to define the training set as the external testing data, and then add conditions in the **Data Set Filter** grid.</span></span>  
  
 <span data-ttu-id="51872-113">\*\*Para obter mais informações: \*\* [Teste e validação &#40;Mineração de dados&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="51872-113">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="51872-114">Opções</span><span class="sxs-lookup"><span data-stu-id="51872-114">Options</span></span>  
 <span data-ttu-id="51872-115">**Condições**</span><span class="sxs-lookup"><span data-stu-id="51872-115">**Conditions**</span></span>  
 <span data-ttu-id="51872-116">Exibe nomes de tabela, seguidos por nomes de coluna com condições.</span><span class="sxs-lookup"><span data-stu-id="51872-116">Displays table names, followed by column names with conditions.</span></span>  
  
|<span data-ttu-id="51872-117">Valor</span><span class="sxs-lookup"><span data-stu-id="51872-117">Value</span></span>|<span data-ttu-id="51872-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="51872-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51872-119">**E/ou**</span><span class="sxs-lookup"><span data-stu-id="51872-119">**And/Or**</span></span>|<span data-ttu-id="51872-120">Escolha um operador para unir múltiplas condições.</span><span class="sxs-lookup"><span data-stu-id="51872-120">Choose an operator to join multiple conditions.</span></span>|  
|<span data-ttu-id="51872-121">**Coluna de Estrutura de Mineração**</span><span class="sxs-lookup"><span data-stu-id="51872-121">**Mining Structure Column**</span></span>|<span data-ttu-id="51872-122">Clique para selecionar uma fonte de dados e em seguida clique em linhas sucessivas na grade para adicionar colunas da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="51872-122">Click to select a data source, and then click successive lines in the grid to add columns from the data source.</span></span><br /><br /> <span data-ttu-id="51872-123">A primeira linha na grade especifica a exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="51872-123">The first line in the grid specifies the data source view.</span></span> <span data-ttu-id="51872-124">Após você selecionar uma exibição de fonte de dados, a **Coluna de Estrutura de Mineração** exibirá um ícone de tabela e o campo **Valor** vai mostrar as combinações de todos os critérios que você definiu para esta fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="51872-124">After you select a data source view, **Mining Structure Column** displays a table icon, and the **Value** field displays the combination of all criteria that you have defined for this data source.</span></span><br /><br /> <span data-ttu-id="51872-125">Após você ter selecionado uma fonte de dados, a caixa **Coluna de Estrutura de Mineração** apresentará um lista suspensa com as colunas individuais da fonte.</span><span class="sxs-lookup"><span data-stu-id="51872-125">After you have selected a data source, the **Mining Structure Column** box provides a dropdown list of individual columns in the data source.</span></span>|  
|<span data-ttu-id="51872-126">**Operador**</span><span class="sxs-lookup"><span data-stu-id="51872-126">**Operator**</span></span>|<span data-ttu-id="51872-127">Selecione um operador da lista.</span><span class="sxs-lookup"><span data-stu-id="51872-127">Select an operator from the list.</span></span>|  
|<span data-ttu-id="51872-128">**Valor**</span><span class="sxs-lookup"><span data-stu-id="51872-128">**Value**</span></span>|<span data-ttu-id="51872-129">Para tabelas, o campo **Valor** exibe a combinação de todos os filtros aplicados à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="51872-129">For tables, the **Value** field shows the combination of all filters applied to the data source.</span></span> <span data-ttu-id="51872-130">Você também pode clicar no botão compilar **(...)** à direita da caixa de texto para abrir a caixa de diálogo **Filtrar** e criar uma condição.</span><span class="sxs-lookup"><span data-stu-id="51872-130">You can also click the build **(...)** button at the right of the text box to open the **Filter** dialog box and build a condition.</span></span>|  
  
 <span data-ttu-id="51872-131">**Expression**</span><span class="sxs-lookup"><span data-stu-id="51872-131">**Expression**</span></span>  
 <span data-ttu-id="51872-132">Exibe o conjunto de critérios que você criou usando a grade.</span><span class="sxs-lookup"><span data-stu-id="51872-132">Displays the set of criteria that you built by using the grid.</span></span>  
  
 <span data-ttu-id="51872-133">**Editar Consulta**</span><span class="sxs-lookup"><span data-stu-id="51872-133">**Edit Query**</span></span>  
 <span data-ttu-id="51872-134">Altera o modo de edição de filtro de forma que você pode digitar uma expressão de filtro diretamente na caixa de texto **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="51872-134">Changes the filter editing mode so that you can type a filter expression directly in the **Expression** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51872-135">Depois de fazer alterações manuais na expressão de filtro, você não poderá retornar ao modo de edição de grade, mesmo depois de salvar a expressão na caixa **expressão de filtro** na guia Seleção de **entrada** . Se você quiser criar uma expressão usando a grade, deverá excluir a expressão de filtro existente e começar novamente.</span><span class="sxs-lookup"><span data-stu-id="51872-135">After you have made manual changes to the filter expression, you cannot return to grid edit mode, even after you have saved the expression in the **Filter Expression** box on the **Input Selection** tab. If you want to build an expression by using the grid, you must delete the existing filter expression and start over.</span></span>  
  
 <span data-ttu-id="51872-136">**Reverter Edições de Consulta**</span><span class="sxs-lookup"><span data-stu-id="51872-136">**Revert Query Edits**</span></span>  
 <span data-ttu-id="51872-137">Restaura a grade a seu estado anterior e cancela qualquer alteração que você fez à expressão do filtro.</span><span class="sxs-lookup"><span data-stu-id="51872-137">Restores the grid to its previous state and cancels any changes that you made to the filter expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51872-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51872-138">See Also</span></span>  
 <span data-ttu-id="51872-139">[Tarefas de teste e validação e instruções &#40;mineração de dados&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="51872-139">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="51872-140">Designer de gráfico de precisão de mineração &#40;mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="51872-140">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
