---
title: Painel de design (exibição de previsão do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.design.f1
ms.assetid: 17f24c8d-43cd-4f4d-83b3-a41ee8fbe8e8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 32ac73a2d6fde38d15d1f45a8439293695749ea4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681254"
---
# <a name="design-pane-mining-model-prediction-view"></a><span data-ttu-id="d413b-102">Painel Design (Exibição da Previsão do Modelo de Mineração)</span><span class="sxs-lookup"><span data-stu-id="d413b-102">Design Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="d413b-103">O painel **Design** contém o Construtor de Consulta de Previsão, que você pode utilizar para criar previsões de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="d413b-103">The **Design** pane contains the Prediction Query Builder, which you can use to build data mining predictions.</span></span> <span data-ttu-id="d413b-104">É possível projetar consultas de previsão que usam tabelas de dados de entrada de uma exibição da fonte de dados, gerar previsões em massa ou criar consultas de previsão singleton, que permitem fornecer valores individuais.</span><span class="sxs-lookup"><span data-stu-id="d413b-104">You can design prediction queries that use tables of input data from a data source view, to generate bulk predictions, or you can create singleton prediction queries, which let you provide individual values.</span></span>  
  
 <span data-ttu-id="d413b-105">Para executar a consulta e exibir os resultados, alterne para a exibição de resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="d413b-105">To run the query and view the results, switch to query result view.</span></span>  
  
 <span data-ttu-id="d413b-106">A visualização da **Consulta** mostra a consulta de DMX (extensões DMX) criada pelo Construtor de Consultas de Previsão.</span><span class="sxs-lookup"><span data-stu-id="d413b-106">The **Query** view displays the Data Mining Extensions (DMX) query that Prediction Query Builder creates.</span></span> <span data-ttu-id="d413b-107">Se você estiver familiarizado com DMX, poderá personalizar esta consulta.</span><span class="sxs-lookup"><span data-stu-id="d413b-107">If you are familiar with DMX, you can customize this query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d413b-108">Se você fizer alguma alteração manual na consulta, suas alterações serão perdidas ao voltar para a exibição Design.</span><span class="sxs-lookup"><span data-stu-id="d413b-108">If you make any manual changes to the query, your changes will be lost when you switch back to Design view.</span></span> <span data-ttu-id="d413b-109">Se desejar salvar a consulta DMX, copie-a na área de transferência do Windows e cole-a em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d413b-109">If you want to save the DMX query, you can copy the query to the Windows Clipboard and then paste it to a text file.</span></span>  
  
 <span data-ttu-id="d413b-110">**Para obter mais informações:** [Consulta de mineração de dados](data-mining/data-mining-queries.md)</span><span class="sxs-lookup"><span data-stu-id="d413b-110">**For More Information:** [Data Mining Queries](data-mining/data-mining-queries.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="d413b-111">Opções</span><span class="sxs-lookup"><span data-stu-id="d413b-111">Options</span></span>  
 <span data-ttu-id="d413b-112">**Alternar para a exibição de resultado da consulta**</span><span class="sxs-lookup"><span data-stu-id="d413b-112">**Switch to query result view**</span></span>  
 <span data-ttu-id="d413b-113">Clique para mudar entre os painéis **Design**, **Consulta**e **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="d413b-113">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="d413b-114">A consulta é executada ao alternar para o painel **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="d413b-114">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="d413b-115">**Salvar o resultado da consulta**</span><span class="sxs-lookup"><span data-stu-id="d413b-115">**Save the query result**</span></span>  
 <span data-ttu-id="d413b-116">Abre a caixa de diálogo **Salvar Resultado da Consulta de Mineração de Dados** .</span><span class="sxs-lookup"><span data-stu-id="d413b-116">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="d413b-117">**Consulta singleton**</span><span class="sxs-lookup"><span data-stu-id="d413b-117">**Singleton query**</span></span>  
 <span data-ttu-id="d413b-118">Permite a criação de uma consulta singleton, na qual você pode fornecer valores diretamente para a consulta em vez de fornecer uma tabela como fonte de dados conhecidos.</span><span class="sxs-lookup"><span data-stu-id="d413b-118">Enables creating a singleton query, in which you can provide values directly for the query instead of providing a table as the source of the known data.</span></span> <span data-ttu-id="d413b-119">A tabela **Selecionar Tabela(s) de Entrada** será substituída por uma tabela **Entrada de Consultas Singleton** .</span><span class="sxs-lookup"><span data-stu-id="d413b-119">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span>  
  
 <span data-ttu-id="d413b-120">**Atualizar resultados de consulta**</span><span class="sxs-lookup"><span data-stu-id="d413b-120">**Refresh query results**</span></span>  
 <span data-ttu-id="d413b-121">Processa novamente a consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="d413b-121">Reprocesses the prediction query.</span></span> <span data-ttu-id="d413b-122">Isso está habilitado apenas no painel **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="d413b-122">This is enabled only in the **Result** pane.</span></span>  
  
 <span data-ttu-id="d413b-123">**Modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="d413b-123">**Mining Model**</span></span>  
 <span data-ttu-id="d413b-124">Exibe o modelo de mineração selecionado no qual você deseja basear as previsões.</span><span class="sxs-lookup"><span data-stu-id="d413b-124">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="d413b-125">**Selecionar Modelo**</span><span class="sxs-lookup"><span data-stu-id="d413b-125">**Select Model**</span></span>  
 <span data-ttu-id="d413b-126">Abre a caixa de diálogo **Selecionar Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="d413b-126">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="d413b-127">**Selecionar Tabela(s) de Entrada**</span><span class="sxs-lookup"><span data-stu-id="d413b-127">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="d413b-128">Exibe as tabelas de entrada selecionadas que contêm dados conhecidos nos quais as previsões serão fundamentadas.</span><span class="sxs-lookup"><span data-stu-id="d413b-128">Displays the selected input tables that contain known data on which to base the predictions.</span></span>  
  
 <span data-ttu-id="d413b-129">**Excluir tabela**</span><span class="sxs-lookup"><span data-stu-id="d413b-129">**Delete Table**</span></span>  
 <span data-ttu-id="d413b-130">Exclui a tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="d413b-130">Deletes the selected table.</span></span> <span data-ttu-id="d413b-131">Esse botão será desabilitado se uma tabela não tiver sido selecionada ou não existir.</span><span class="sxs-lookup"><span data-stu-id="d413b-131">This button is disabled if a table has not been selected or does not exist.</span></span>  
  
 <span data-ttu-id="d413b-132">**Selecionar Tabela de Casos**</span><span class="sxs-lookup"><span data-stu-id="d413b-132">**Select Case Table**</span></span>  
 <span data-ttu-id="d413b-133">Abre a caixa de diálogo **Selecionar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="d413b-133">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="d413b-134">Esse botão só será exibido se uma tabela da caixa não tiver sido selecionada.</span><span class="sxs-lookup"><span data-stu-id="d413b-134">This button appears only if a case table has not been selected.</span></span>  
  
 <span data-ttu-id="d413b-135">**Selecionar Tabela Aninhada**</span><span class="sxs-lookup"><span data-stu-id="d413b-135">**Select Nested Table**</span></span>  
 <span data-ttu-id="d413b-136">Abre a caixa de diálogo **Selecionar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="d413b-136">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="d413b-137">Esse botão só será exibido se uma tabela do casos tiver sido selecionada.</span><span class="sxs-lookup"><span data-stu-id="d413b-137">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="d413b-138">Se a estrutura de mineração associada não contiver uma tabela aninhada, esse botão será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="d413b-138">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="d413b-139">**Modificar Junção**</span><span class="sxs-lookup"><span data-stu-id="d413b-139">**Modify Join**</span></span>  
 <span data-ttu-id="d413b-140">Abre a caixa de diálogo **Especificar Junção Aninhada** .</span><span class="sxs-lookup"><span data-stu-id="d413b-140">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="d413b-141">Esse botão só será ativado se a tabela aninhada for selecionada.</span><span class="sxs-lookup"><span data-stu-id="d413b-141">This button is active only if the nested table is selected.</span></span>  
  
 <span data-ttu-id="d413b-142">**Entrada de Consultas Singleton**</span><span class="sxs-lookup"><span data-stu-id="d413b-142">**Singleton Query input**</span></span>  
 <span data-ttu-id="d413b-143">Habilitado quando você seleciona o botão **Consulta Singleton** .</span><span class="sxs-lookup"><span data-stu-id="d413b-143">Enabled when you select the **Singleton query** button.</span></span> <span data-ttu-id="d413b-144">Contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="d413b-144">Contains the following columns:</span></span>  
  
|<span data-ttu-id="d413b-145">Valor</span><span class="sxs-lookup"><span data-stu-id="d413b-145">Value</span></span>|<span data-ttu-id="d413b-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="d413b-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d413b-147">**Coluna do Modelo de Mineração**</span><span class="sxs-lookup"><span data-stu-id="d413b-147">**Mining Model Column**</span></span>|<span data-ttu-id="d413b-148">Lista as colunas de modelo de mineração contidas no modelo de mineração que for selecionado na tabela **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="d413b-148">Lists the mining model columns contained within the mining model that is selected in the **Mining Model** table.</span></span>|  
|<span data-ttu-id="d413b-149">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d413b-149">**Value**</span></span>|<span data-ttu-id="d413b-150">Selecione um valor da lista que contém cada estado possível da coluna de modelos de mineração selecionada.</span><span class="sxs-lookup"><span data-stu-id="d413b-150">Select a value from the list that contains each possible state of the selected mining model column.</span></span><br /><br /> <span data-ttu-id="d413b-151">Se a coluna for uma coluna de tabela aninhada, clicar na célula de valor abrirá a caixa de diálogo **Entrada de Tabela Aninhada** .</span><span class="sxs-lookup"><span data-stu-id="d413b-151">If the column is a nested table column, clicking the value cell opens the **Nested Table Input** dialog box.</span></span>|  
  
 <span data-ttu-id="d413b-152">**Origem**</span><span class="sxs-lookup"><span data-stu-id="d413b-152">**Source**</span></span>  
 <span data-ttu-id="d413b-153">Selecione a origem que contém o campo que você utilizará para a coluna.</span><span class="sxs-lookup"><span data-stu-id="d413b-153">Select the source that contains the field that you will use for the column.</span></span> <span data-ttu-id="d413b-154">Você pode usar o modelo de mineração selecionado na tabela **Modelo de Mineração** , a tabela ou as tabelas selecionadas na tabela **Selecionar Tabela(s) de Entrada** , uma função de previsão ou uma expressão personalizada.</span><span class="sxs-lookup"><span data-stu-id="d413b-154">You can either use the mining model that is selected in the **Mining Model** table, the input table or tables that are selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="d413b-155">As colunas podem ser arrastadas das tabelas que contêm o modelo de mineração e as tabelas de entrada até a célula.</span><span class="sxs-lookup"><span data-stu-id="d413b-155">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
 <span data-ttu-id="d413b-156">**Campo**</span><span class="sxs-lookup"><span data-stu-id="d413b-156">**Field**</span></span>  
 <span data-ttu-id="d413b-157">Selecione uma coluna na lista de colunas derivada da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="d413b-157">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="d413b-158">Se você selecionou a opção **Função de Previsão** em **Origem**, ela conterá a função de previsão disponível para o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="d413b-158">If you selected **Prediction Function** in **Source**, this contains the prediction function available for the selected mining model.</span></span>  
  
 <span data-ttu-id="d413b-159">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="d413b-159">**Group**</span></span>  
 <span data-ttu-id="d413b-160">Use com a coluna **E/ou** para agrupar expressões.</span><span class="sxs-lookup"><span data-stu-id="d413b-160">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="d413b-161">Por exemplo, `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="d413b-161">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="d413b-162">**E/ou**</span><span class="sxs-lookup"><span data-stu-id="d413b-162">**And/Or**</span></span>  
 <span data-ttu-id="d413b-163">Use para criar uma consulta lógica.</span><span class="sxs-lookup"><span data-stu-id="d413b-163">Use to create a logical query.</span></span> <span data-ttu-id="d413b-164">Por exemplo, `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="d413b-164">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="d413b-165">**Critérios/Argumento**</span><span class="sxs-lookup"><span data-stu-id="d413b-165">**Criteria/Argument**</span></span>  
 <span data-ttu-id="d413b-166">Especifique uma condição ou expressão de usuário que se aplica à coluna.</span><span class="sxs-lookup"><span data-stu-id="d413b-166">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="d413b-167">As colunas podem ser arrastadas das tabelas que contêm o modelo de mineração e as tabelas de entrada até a célula.</span><span class="sxs-lookup"><span data-stu-id="d413b-167">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d413b-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d413b-168">See Also</span></span>  
 <span data-ttu-id="d413b-169">[Referência de instrução&#41; &#40;DMX de extensões de mineração de dados](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="d413b-169">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 <span data-ttu-id="d413b-170">[Interfaces de consulta de mineração de dados](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d413b-170">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="d413b-171">Construtor de Consultas de previsão &#40;Mineração de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="d413b-171">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
