---
title: Guia Seleção de entrada (exibição de gráfico de precisão de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.columnmapping.f1
ms.assetid: f8b1193c-5c86-4c7e-8e35-158d293184fa
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c5e99e5be275dff6e218d172316c612b5ba0c41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574408"
---
# <a name="input-selection-tab-mining-accuracy-chart-view"></a><span data-ttu-id="c13fd-102">Guia de seleção de entrada (exibição de gráfico de precisão de mineração)</span><span class="sxs-lookup"><span data-stu-id="c13fd-102">Input Selection Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="c13fd-103">Use a guia **Seleção de Entrada** do designer **Gráfico de Precisão de Mineração** para especificar a fonte dos dados que são usados para testar o modelo e criar o gráfico de precisão.</span><span class="sxs-lookup"><span data-stu-id="c13fd-103">Use the **Input Selection** tab of the **Mining Accuracy Chart** designer to specify the source of the data that is used to test the model and build the accuracy chart.</span></span>  
  
 <span data-ttu-id="c13fd-104">\*\*Para obter mais informações: \*\* [Teste e validação &#40;Mineração de dados&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="c13fd-104">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="c13fd-105">Opções</span><span class="sxs-lookup"><span data-stu-id="c13fd-105">Options</span></span>  
 <span data-ttu-id="c13fd-106">**Sincronizar Colunas**  **e Valores de Previsão**</span><span class="sxs-lookup"><span data-stu-id="c13fd-106">**Synchronize Prediction**  **Columns and Values**</span></span>  
 <span data-ttu-id="c13fd-107">Selecione para coordenar os atributos previsíveis na grade de forma que, mesmo que eles tenham um nome diferente, serão derivados da mesma coluna previsível de estrutura de mineração durante o treinamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="c13fd-107">Select to coordinate the predictable attributes in the grid so that, even if they have a different name, they are derived from the same predictable mining structure column during model training.</span></span>  
  
 <span data-ttu-id="c13fd-108">**Observação** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c13fd-108">**Note** This option is selected by default.</span></span> <span data-ttu-id="c13fd-109">Você só deve desmarcar esta caixa para os casos nos quais você sabe que as duas colunas da estrutura de mineração derivam da mesma fonte relacional ou multidimensional subjacente e que estas colunas contêm os mesmos estados ou foram tornadas discretas da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="c13fd-109">You should only clear this box for cases in which you know that two mining structure columns derive from the same underlying relational or multi-dimensional source, and that the columns contain the same states or have been discretized in the same way.</span></span>  
  
 <span data-ttu-id="c13fd-110">**Selecione as colunas previsíveis do modelo de mineração para exibir no gráfico de comparação de precisão**</span><span class="sxs-lookup"><span data-stu-id="c13fd-110">**Select predictable mining model columns to show in the lift chart**</span></span>  
 <span data-ttu-id="c13fd-111">Uma grade que contém colunas para controlar que modelos são incluídos no gráfico de comparação de precisão e como eles são usados neste gráfico.</span><span class="sxs-lookup"><span data-stu-id="c13fd-111">A grid that contains columns to control which models are included in the lift chart and how they are used in the lift chart.</span></span>  
  
|<span data-ttu-id="c13fd-112">Valor</span><span class="sxs-lookup"><span data-stu-id="c13fd-112">Value</span></span>|<span data-ttu-id="c13fd-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="c13fd-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c13fd-114">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="c13fd-114">**Show**</span></span>|<span data-ttu-id="c13fd-115">Selecione no modelo de mineração a caixa próxima ao nome de cada coluna previsível que você deseja exibir no gráfico.</span><span class="sxs-lookup"><span data-stu-id="c13fd-115">Select the box next to the name of each predictable column in the mining model that you want to display in the chart.</span></span><br /><br /> <span data-ttu-id="c13fd-116">Se o gráfico é muito complexo para ser visualizado facilmente, desmarque a caixa próxima de uma ou mais colunas para simplificar o gráfico.</span><span class="sxs-lookup"><span data-stu-id="c13fd-116">If the chart is too complex to view easily, clear the box next to one or more columns to simplify the chart.</span></span><br /><br /> <span data-ttu-id="c13fd-117">Observação: você não pode criar um gráfico de exatidão sem que pelo menos uma coluna seja selecionada.</span><span class="sxs-lookup"><span data-stu-id="c13fd-117">Note: You cannot create an accuracy chart unless at least one column is selected.</span></span>|  
|<span data-ttu-id="c13fd-118">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="c13fd-118">**Mining Model**</span></span>|<span data-ttu-id="c13fd-119">Lista os modelos de mineração que estão contidos na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="c13fd-119">Lists the mining models that are contained in the mining structure.</span></span>|  
|<span data-ttu-id="c13fd-120">**Nome da coluna previsível**</span><span class="sxs-lookup"><span data-stu-id="c13fd-120">**Predictable Column Name**</span></span>|<span data-ttu-id="c13fd-121">Selecione uma coluna previsível que esteja contida nos modelos de mineração que são usados para criar o gráfico de comparação de precisão.</span><span class="sxs-lookup"><span data-stu-id="c13fd-121">Select a predictable column that is contained in the mining models that are used to create the lift chart.</span></span>|  
|<span data-ttu-id="c13fd-122">**Prever valor**</span><span class="sxs-lookup"><span data-stu-id="c13fd-122">**Predict Value**</span></span>|<span data-ttu-id="c13fd-123">Selecione um valor para a coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="c13fd-123">Select a value for the predictable column.</span></span> <span data-ttu-id="c13fd-124">Se você deixar em branco, o gráfico de comparação de precisão prevê o melhor desempenho do modelo para todos os estados da coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="c13fd-124">If you leave this blank, the lift chart predicts how well the model performs for all states of the predictable column.</span></span>|  
  
 <span data-ttu-id="c13fd-125">**Selecione o conjunto de dados a ser usado para o Gráfico de Precisão**</span><span class="sxs-lookup"><span data-stu-id="c13fd-125">**Select data set to be used for Accuracy Chart**</span></span>  
 <span data-ttu-id="c13fd-126">Um grupo de opção que contém três opções para especificar dados de teste de exatidão.</span><span class="sxs-lookup"><span data-stu-id="c13fd-126">An option group that contains three options for specifying accuracy test data.</span></span>  
  
|<span data-ttu-id="c13fd-127">Valor</span><span class="sxs-lookup"><span data-stu-id="c13fd-127">Value</span></span>|<span data-ttu-id="c13fd-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="c13fd-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c13fd-129">**Usar casos de teste do modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="c13fd-129">**Use mining model test cases**</span></span>|<span data-ttu-id="c13fd-130">Use o conjunto de teste que estava criado quando você dividiu a estrutura de mineração e aplique o filtro que esta definido no modelo.</span><span class="sxs-lookup"><span data-stu-id="c13fd-130">Use the testing set that was created when you partitioned the mining structure, and apply the filter that is defined on the model.</span></span> <span data-ttu-id="c13fd-131">Para obter informações sobre filtros de modelo, consulte [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](data-mining/mining-models-analysis-services-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="c13fd-131">For information about model filters, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](data-mining/mining-models-analysis-services-data-mining.md)</span></span>|  
|<span data-ttu-id="c13fd-132">**Usar casos de teste da estrutura de mineração**</span><span class="sxs-lookup"><span data-stu-id="c13fd-132">**Use mining structure test cases**</span></span>|<span data-ttu-id="c13fd-133">Use o conjunto de teste que foi criado quando você dividiu a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="c13fd-133">Use the testing set that was created when you partitioned the mining structure.</span></span>|  
|<span data-ttu-id="c13fd-134">**Especificar um conjunto de dados diferente**</span><span class="sxs-lookup"><span data-stu-id="c13fd-134">**Specify a different data set**</span></span>|<span data-ttu-id="c13fd-135">Especifique uma tabela de uma exibição da fonte de dados existente para usar como conjunto de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="c13fd-135">Specify a table from an existing data source view to use as a test data set.</span></span>|  
  
## <a name="filtering-options"></a><span data-ttu-id="c13fd-136">Opções de filtragem</span><span class="sxs-lookup"><span data-stu-id="c13fd-136">Filtering Options</span></span>  
 <span data-ttu-id="c13fd-137">Se você selecionar a opção **Especificar um conjunto de dados diferente**, poderá definir uma exibição de fonte de dados e criar filtros para aplicar aos dados.</span><span class="sxs-lookup"><span data-stu-id="c13fd-137">If you select the option **Specify a different data set**, you can define a data source view and create filters to apply to that data.</span></span> <span data-ttu-id="c13fd-138">Ao criar um filtro, você está criando uma cláusula WHERE na consulta que retorna os dados de teste da exibição de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c13fd-138">When you create a filter, you are creating a WHERE clause in the query that returns the test data from the data source view.</span></span>  
  
 <span data-ttu-id="c13fd-139">**Observação** Você não pode especificar um filtro no modelo de mineração usando a guia **seleção de entrada** . Para criar um filtro de modelo, clique na guia **modelos de mineração** e edite as propriedades do modelo.</span><span class="sxs-lookup"><span data-stu-id="c13fd-139">**Note** You cannot specify a filter on the mining model by using the **Input Selection** tab. To create a model filter, click the **Mining Models** tab and edit the model properties.</span></span>  
  
 <span data-ttu-id="c13fd-140">Se você não criou um conjunto de controle para teste quando criou a estrutura de mineração, você pode selecionar esta opção e então especificar a exibição de fonte de dados original como um conjunto de teste.</span><span class="sxs-lookup"><span data-stu-id="c13fd-140">If you did not create a holdout set for testing when you created the mining structure, you can select this option and then specify the original data source view as a test set.</span></span> <span data-ttu-id="c13fd-141">Usando esta solução alternativa, você também pode definir filtros no conjunto de dados original.</span><span class="sxs-lookup"><span data-stu-id="c13fd-141">By using  this workaround, you can also set filters on the original data set.</span></span>  
  
 <span data-ttu-id="c13fd-142">**Especificar Mapeamento de Coluna**</span><span class="sxs-lookup"><span data-stu-id="c13fd-142">**Specify Column Mapping**</span></span>  
 <span data-ttu-id="c13fd-143">Abre a caixa de diálogo **Especificar Mapeamento de Coluna** em que você seleciona a fonte de dados, especifica caso e tabelas aninhadas e associa colunas de dados externos às colunas da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="c13fd-143">Opens the **Specify Column Mapping** dialog box, where you select the data source, specify case and nested tables, and map external data columns to the mining structure columns.</span></span>  
  
 <span data-ttu-id="c13fd-144">Para obter mais informações, consulte [Caixa de diálogo Especificar Mapeamento de Coluna &#40;gráfico de precisão de mineração&#41;](specify-column-mapping-dialog-box-mining-accuracy-chart.md).</span><span class="sxs-lookup"><span data-stu-id="c13fd-144">For more information, see [Specify Column Mapping Dialog Box &#40;Mining Accuracy Chart&#41;](specify-column-mapping-dialog-box-mining-accuracy-chart.md).</span></span>  
  
 <span data-ttu-id="c13fd-145">**Expressão de filtro**</span><span class="sxs-lookup"><span data-stu-id="c13fd-145">**Filter Expression**</span></span>  
 <span data-ttu-id="c13fd-146">Exibe a condição do filtro que você construiu usando os editores de filtro.</span><span class="sxs-lookup"><span data-stu-id="c13fd-146">Displays the filter condition that you built by using the filter editors.</span></span>  
  
 <span data-ttu-id="c13fd-147">**Abrir Editor de Filtro**</span><span class="sxs-lookup"><span data-stu-id="c13fd-147">**Open Filter Editor**</span></span>  
 <span data-ttu-id="c13fd-148">Abra a caixa de diálogo **Filtro de Conjunto de Dados** que permite selecionar tabelas externas e definir condições nas colunas de tabela de caso e, a caixa de diálogo **Filtro** que o ajuda a criar condições que se aplicam para determinadas colunas na tabela selecionada ou para colunas em tabelas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="c13fd-148">Opens the **Data Set Filter** dialog box, which lets you select external tables, and set conditions on case table columns, and the **Filter** dialog box, which helps you build conditions that apply to individual columns in the selected table, or to columns in nested tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13fd-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c13fd-149">See Also</span></span>  
 <span data-ttu-id="c13fd-150">[Tarefas de teste e validação e instruções &#40;mineração de dados&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c13fd-150">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 <span data-ttu-id="c13fd-151">[Designer de gráfico de precisão de mineração &#40;mineração de dados&#41;](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c13fd-151">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="c13fd-152">[Aplicar um filtro a um modelo de mineração](data-mining/apply-a-filter-to-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="c13fd-152">[Apply a Filter to a Mining Model](data-mining/apply-a-filter-to-a-mining-model.md) </span></span>  
 [<span data-ttu-id="c13fd-153">Filtros para modelos de mineração &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="c13fd-153">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining/mining-models-analysis-services-data-mining.md)  
  
  