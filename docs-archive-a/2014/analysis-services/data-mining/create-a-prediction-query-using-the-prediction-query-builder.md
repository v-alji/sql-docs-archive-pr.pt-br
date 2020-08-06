---
title: Criar uma consulta de previsão usando o Construtor de Consultas de previsão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- Mining Model Prediction [Analysis Services], prediction queries
ms.assetid: e02836e5-dd8c-4c97-a078-840ae79d3660
author: minewiskan
ms.author: owend
ms.openlocfilehash: 13f39de4085cb74949e9540570d574c09e72ee27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570338"
---
# <a name="create-a-prediction-query-using-the-prediction-query-builder"></a><span data-ttu-id="a2175-102">Criar uma consulta de previsão usando o construtor de consultas de previsão</span><span class="sxs-lookup"><span data-stu-id="a2175-102">Create a Prediction Query Using the Prediction Query Builder</span></span>
  <span data-ttu-id="a2175-103">Você pode criar consultas de previsão enquanto estiver criando uma solução de mineração de dados no BI Development Studio, ou clicar com o botão direito em um modelo de mineração existente no SQL Server Management Studio e, em seguida, escolher a opção **Criar Consulta de Previsão**.</span><span class="sxs-lookup"><span data-stu-id="a2175-103">You can create prediction queries either while you are building a data mining solution in BI Development Studio, or by right-clicking an existing mining model in SQL Server Management Studio, and then choosing the option, **Build Prediction Query**.</span></span>  
  
 <span data-ttu-id="a2175-104">O **Construtor de Consultas de Previsão** tem os três modos de design a seguir, os quais você pode alternar clicando nos ícones no canto superior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="a2175-104">The **Prediction Query Builder** has the following three design modes, which you can switch among by clicking the icons in the upper-left corner.</span></span>  
  
-   <span data-ttu-id="a2175-105">**Projetar**</span><span class="sxs-lookup"><span data-stu-id="a2175-105">**Design**</span></span>  
  
-   <span data-ttu-id="a2175-106">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="a2175-106">**Query**</span></span>  
  
-   <span data-ttu-id="a2175-107">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="a2175-107">**Result**</span></span>  
  
 <span data-ttu-id="a2175-108">O modo de**design** permite criar uma consulta de previsão escolhendo dados de entrada, mapeando os dados para o modelo e adicionando funções de previsão em instruções que você cria usando a grade.</span><span class="sxs-lookup"><span data-stu-id="a2175-108">**Design** mode lets you build a prediction query by choosing input data, mapping the data to the model, and then adding prediction functions into statements you build by using the grid.</span></span> <span data-ttu-id="a2175-109">A grade de design contém estes blocos de construção:</span><span class="sxs-lookup"><span data-stu-id="a2175-109">The design grid contains these building blocks:</span></span>  
  
 <span data-ttu-id="a2175-110">**Origem**</span><span class="sxs-lookup"><span data-stu-id="a2175-110">**Source**</span></span>  
 <span data-ttu-id="a2175-111">Escolha a origem da nova coluna.</span><span class="sxs-lookup"><span data-stu-id="a2175-111">Choose the source of the new column.</span></span> <span data-ttu-id="a2175-112">Você pode usar colunas do modelo de mineração, tabelas de entrada incluídas na exibição da fonte de dados, uma função de previsão ou uma expressão personalizada.</span><span class="sxs-lookup"><span data-stu-id="a2175-112">You can use columns from the mining model, input tables included in the data source view, a prediction function, or a customized expression.</span></span>  
  
 <span data-ttu-id="a2175-113">**Campo**</span><span class="sxs-lookup"><span data-stu-id="a2175-113">**Field**</span></span>  
 <span data-ttu-id="a2175-114">Determina a coluna ou função específica associada à seleção na coluna **Origem** .</span><span class="sxs-lookup"><span data-stu-id="a2175-114">Determines the specific column or function that is associated with the selection in the **Source** column.</span></span>  
  
 <span data-ttu-id="a2175-115">**Receber**</span><span class="sxs-lookup"><span data-stu-id="a2175-115">**Alias**</span></span>  
 <span data-ttu-id="a2175-116">Determina como a coluna será nomeada no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="a2175-116">Determines how the column is to be named in the result set.</span></span>  
  
 <span data-ttu-id="a2175-117">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="a2175-117">**Show**</span></span>  
 <span data-ttu-id="a2175-118">Determina se a seleção na coluna **Origem** é exibida nos resultados.</span><span class="sxs-lookup"><span data-stu-id="a2175-118">Determines whether the selection in the **Source** column is displayed in the results.</span></span>  
  
 <span data-ttu-id="a2175-119">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="a2175-119">**Group**</span></span>  
 <span data-ttu-id="a2175-120">Trabalha com a coluna **E/Ou** para agrupar expressões usando parênteses.</span><span class="sxs-lookup"><span data-stu-id="a2175-120">Works with the **And/Or** column to group expressions together by using parentheses.</span></span> <span data-ttu-id="a2175-121">Por exemplo, (expr1 ou expr2) e expr3.</span><span class="sxs-lookup"><span data-stu-id="a2175-121">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="a2175-122">**E/ou**</span><span class="sxs-lookup"><span data-stu-id="a2175-122">**And/Or**</span></span>  
 <span data-ttu-id="a2175-123">Cria lógica na consulta.</span><span class="sxs-lookup"><span data-stu-id="a2175-123">Creates logic in the query.</span></span> <span data-ttu-id="a2175-124">Por exemplo, (expr1 ou expr2) e expr3.</span><span class="sxs-lookup"><span data-stu-id="a2175-124">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="a2175-125">**Critérios/Argumento**</span><span class="sxs-lookup"><span data-stu-id="a2175-125">**Criteria/Argument**</span></span>  
 <span data-ttu-id="a2175-126">Especifica uma condição ou expressão de usuário que se aplica à coluna.</span><span class="sxs-lookup"><span data-stu-id="a2175-126">Specifies a condition or user expression that applies to the column.</span></span> <span data-ttu-id="a2175-127">Você pode arrastar colunas das tabelas para a célula.</span><span class="sxs-lookup"><span data-stu-id="a2175-127">You can drag columns from the tables to the cell.</span></span>  
  
 <span data-ttu-id="a2175-128">O modo de**Consulta** fornece um editor de texto que dá a você acesso direto à linguagem DMX (extensões DMX), junto com uma exibição dos dados de entrada e das colunas de modelo.</span><span class="sxs-lookup"><span data-stu-id="a2175-128">**Query** mode provides a text editor that gives you direct access to the Data Mining Extensions (DMX) language, along with a view of the input data and model columns.</span></span> <span data-ttu-id="a2175-129">Quando você seleciona o modo **Consulta** , a grade usada para definir a consulta é substituída por um editor de texto básico.</span><span class="sxs-lookup"><span data-stu-id="a2175-129">When you select **Query** mode, the grid that you used to define the query is replaced by a basic text editor.</span></span> <span data-ttu-id="a2175-130">Você pode usar este editor para copiar e salvar consultas que você compôs ou colar em consultas DMX existentes e da Área de transferência e executá-las.</span><span class="sxs-lookup"><span data-stu-id="a2175-130">You can use this editor to copy and save queries you have composed, or to paste in existing DMX queries and from the Clipboard and run them.</span></span>  
  
 <span data-ttu-id="a2175-131">A exibição de**Resultado** executa a consulta atual e exibe os resultados em uma grade.</span><span class="sxs-lookup"><span data-stu-id="a2175-131">**Result** view runs the current query and displays the results in a grid.</span></span> <span data-ttu-id="a2175-132">Se os dados subjacentes forem alterados e você desejar executar novamente a consulta, clique no botão Executar na barra de status</span><span class="sxs-lookup"><span data-stu-id="a2175-132">If the underlying data has changed and you want to rerun the query, click the Play button in the status bar</span></span>  
  
 <span data-ttu-id="a2175-133">Você pode criar uma consulta de mineração de dados usando uma combinação das ferramentas visuais e do editor de texto.</span><span class="sxs-lookup"><span data-stu-id="a2175-133">You can design a data mining query by using a combination of the visual tools and the text editor.</span></span> <span data-ttu-id="a2175-134">Se você digita alterações na consulta no editor de texto e volta ao modo de exibição de **Design** , todas as alterações são perdidas, e a consulta é revertida para a consulta original criada pelo Construtor de Consulta de Previsão. Este tópico orienta o uso do construtor de consultas gráficas.</span><span class="sxs-lookup"><span data-stu-id="a2175-134">If you type changes to the query in the text editor and switch back to the **Design** view, all the changes are lost, and the query reverts to the original query created by Prediction Query Builder This topic walks you through use of the graphical query builder.</span></span>  
  
### <a name="to-create-a-prediction-query"></a><span data-ttu-id="a2175-135">Para criar uma consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="a2175-135">To create a prediction query</span></span>  
  
1.  <span data-ttu-id="a2175-136">Clique na guia **Previsão do Modelo de Mineração** do Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="a2175-136">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="a2175-137">Clique em **Selecionar Modelo** na tabela **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="a2175-137">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="a2175-138">A caixa de diálogo **Selecionar Modelo de Mineração** é aberta e mostra todas as estruturas de mineração existentes no projeto atual.</span><span class="sxs-lookup"><span data-stu-id="a2175-138">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
3.  <span data-ttu-id="a2175-139">Selecione o modelo no qual você deseja criar uma previsão e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2175-139">Select the model on which you want to create a prediction, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a2175-140">Na tabela **Selecionar Tabela(s) de Entrada** , clique em **Selecionar Tabela de Casos**.</span><span class="sxs-lookup"><span data-stu-id="a2175-140">On the **Select Input Table(s)** table, click **Select Case Table**.</span></span>  
  
     <span data-ttu-id="a2175-141">A caixa de diálogo **Selecionar Tabela** é aberta.</span><span class="sxs-lookup"><span data-stu-id="a2175-141">The **Select Table** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="a2175-142">Na lista **Fonte de Dados** , selecione a fonte de dados que contém os dados com os quais você deseja criar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="a2175-142">In the **Data Source** list, select the data source that contains the data on which to create a prediction.</span></span>  
  
6.  <span data-ttu-id="a2175-143">Na caixa **Nome da Tabela/Exibição** , selecione a tabela que contém os dados nos quais você deseja criar uma previsão e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2175-143">In the **Table/View Name** box, select the table that contains the data on which to create a prediction, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a2175-144">Depois de selecionar a tabela de entrada, o Construtor de Consultas de Previsão cria um mapeamento padrão entre o modelo de mineração e a tabela de entrada, com base nos nomes das colunas.</span><span class="sxs-lookup"><span data-stu-id="a2175-144">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="a2175-145">Para excluir um mapeamento, clique para selecionar a linha que vincula a coluna da tabela **Modelo de Mineração** à coluna mapeada da tabela **Selecionar Tabela(s) de Entrada** e, em seguida, pressione a tecla DELETE.</span><span class="sxs-lookup"><span data-stu-id="a2175-145">To delete a mapping, click to select the line that links the column in the **Mining Model** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span> <span data-ttu-id="a2175-146">Você também pode criar mapeamentos manualmente clicando em uma coluna da tabela **Selecionar Tabela(s) de Entrada** e arrastando-a para a coluna correspondente da tabela **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="a2175-146">You can also manually create mappings by clicking a column in the **Select Input Table(s)** table and dragging it onto the corresponding column in the **Mining Model** table.</span></span>  
  
7.  <span data-ttu-id="a2175-147">Adicione qualquer combinação destes três tipos de informação à grade Construtor de Consultas de Previsão:</span><span class="sxs-lookup"><span data-stu-id="a2175-147">Add any combination of the following three types of information to the Prediction Query Builder grid:</span></span>  
  
    -   <span data-ttu-id="a2175-148">Colunas previsíveis na caixa **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="a2175-148">Predictable columns from the **Mining Model** box.</span></span>  
  
    -   <span data-ttu-id="a2175-149">Qualquer combinação de colunas de entrada na caixa **Selecionar Tabela(s) de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="a2175-149">Any combination of input columns from the **Select Input Table(s)** box.</span></span>  
  
    -   <span data-ttu-id="a2175-150">Funções de previsão</span><span class="sxs-lookup"><span data-stu-id="a2175-150">Prediction functions</span></span>  
  
8.  <span data-ttu-id="a2175-151">Execute a consulta clicando no primeiro botão da barra de ferramentas da guia **Previsão do Modelo de Mineração** e selecione **Resultado**.</span><span class="sxs-lookup"><span data-stu-id="a2175-151">Run the query by clicking the first button on the toolbar of the **Mining Model Prediction** tab, and then selecting **Result**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2175-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2175-152">See Also</span></span>  
 <span data-ttu-id="a2175-153">[Criar uma consulta singleton no designer de mineração de dados](create-a-singleton-query-in-the-data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a2175-153">[Create a Singleton Query in the Data Mining Designer](create-a-singleton-query-in-the-data-mining-designer.md) </span></span>  
 [<span data-ttu-id="a2175-154">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="a2175-154">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
