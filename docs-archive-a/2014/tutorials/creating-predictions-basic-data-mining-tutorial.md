---
title: Criando previsões (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a8410ed2-bb98-4d51-a9eb-b239be1201c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 456aec6c6b9d0d1a5d0ee1d9949507a37577130c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678378"
---
# <a name="creating-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="72aa7-102">Criando previsões (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="72aa7-102">Creating Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="72aa7-103">Depois de testar a precisão dos seus modelos de mineração e decidir que você está satisfeito com os resultados, você pode gerar previsões usando o Construtor de Consultas de previsão na guia **previsão do modelo de mineração** no designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="72aa7-103">After you have tested the accuracy of your mining models and decided that you are satisfied with the results, you can then generate predictions by using the Prediction Query Builder on the **Mining Model Prediction** tab in the Data Mining Designer.</span></span>  
  
 <span data-ttu-id="72aa7-104">O Construtor de Consultas de Previsão contém três exibições.</span><span class="sxs-lookup"><span data-stu-id="72aa7-104">The Prediction Query Builder has three views.</span></span> <span data-ttu-id="72aa7-105">Com as exibições de **design** e **consulta** , você pode criar e examinar sua consulta.</span><span class="sxs-lookup"><span data-stu-id="72aa7-105">With the **Design** and **Query** views, you can build and examine your query.</span></span> <span data-ttu-id="72aa7-106">Em seguida, você pode executar a consulta e exibir os resultados na exibição de **resultado** .</span><span class="sxs-lookup"><span data-stu-id="72aa7-106">You can then run the query and view the results in the **Result** view.</span></span>  
  
 <span data-ttu-id="72aa7-107">Todas as consultas de previsão usam DMX, que é a abreviação da linguagem Data Mining Extensions.</span><span class="sxs-lookup"><span data-stu-id="72aa7-107">All prediction queries use DMX, which is short for the Data Mining Extensions (DMX) language.</span></span> <span data-ttu-id="72aa7-108">O DMX tem sintaxe semelhante à de T-SQL mas é usado para consultas em objetos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="72aa7-108">DMX has syntax like that of T-SQL but is used for queries against data mining objects.</span></span> <span data-ttu-id="72aa7-109">Embora a sintaxe DMX não seja complicada, o uso de um construtor de consultas como este, ou o do [SQL Server suplementos de mineração de dados para Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), facilita muito a seleção de entradas e a criação de expressões, portanto, é altamente recomendável que você aprenda os conceitos básicos.</span><span class="sxs-lookup"><span data-stu-id="72aa7-109">Although DMX syntax is not complicated, using a query builder like this one, or the one in the [SQL Server Data Mining Add-Ins for Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), makes it much easier to select inputs and build expressions, so we highly recommend that you learn the basics.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="72aa7-110">Criando a consulta</span><span class="sxs-lookup"><span data-stu-id="72aa7-110">Creating the Query</span></span>  
 <span data-ttu-id="72aa7-111">A primeira etapa na criação de uma consulta de previsão é selecionar um modelo de mineração e tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="72aa7-111">The first step in creating a prediction query is to select a mining model and input table.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="72aa7-112">Para selecionar um modelo e uma tabela de entrada</span><span class="sxs-lookup"><span data-stu-id="72aa7-112">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="72aa7-113">Na guia **previsão do modelo de mineração** do designer de mineração de dados, na caixa **modelo de mineração** , clique em **selecionar modelo**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-113">On the **Mining Model Prediction** tab of Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="72aa7-114">Na caixa de diálogo **selecionar modelo de mineração** , navegue pela árvore até a estrutura de **endereçamento direcionada** , expanda a estrutura, selecione `TM_Decision_Tree` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-114">In the **Select Mining Model** dialog box, navigate through the tree to the **Targeted Mailing** structure, expand the structure, select `TM_Decision_Tree`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="72aa7-115">Na caixa **selecionar tabela (s) de entrada** , clique em **selecionar tabela de casos**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-115">In the **Select Input Table(s)** box, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="72aa7-116">Na caixa de diálogo **selecionar tabela** , na lista **fonte de dados** , selecione a exibição da fonte de dados [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72aa7-116">In the **Select Table** dialog box, in the **Data Source** list, select the data source view [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
5.  <span data-ttu-id="72aa7-117">Em **nome da tabela/exibição**, selecione a tabela **ProspectiveBuyer (dbo)** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-117">In **Table/View Name**, select the **ProspectiveBuyer (dbo)** table, and then click **OK**.</span></span>  
  
     <span data-ttu-id="72aa7-118">A `ProspectiveBuyer` tabela é mais parecida com a tabela de casos **vTargetMail** .</span><span class="sxs-lookup"><span data-stu-id="72aa7-118">The `ProspectiveBuyer` table most closely resembles the **vTargetMail** case table.</span></span>  
  
## <a name="mapping-the-columns"></a><span data-ttu-id="72aa7-119">Mapeando as colunas</span><span class="sxs-lookup"><span data-stu-id="72aa7-119">Mapping the Columns</span></span>  
 <span data-ttu-id="72aa7-120">Depois de selecionar a tabela de entrada, o Construtor de Consultas de Previsão cria um mapeamento padrão entre o modelo de mineração e a tabela de entrada, com base nos nomes das colunas.</span><span class="sxs-lookup"><span data-stu-id="72aa7-120">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="72aa7-121">Pelo menos uma coluna da estrutura deve corresponder a uma coluna nos dados externos.</span><span class="sxs-lookup"><span data-stu-id="72aa7-121">At least one column from the structure must match a column in the external data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="72aa7-122">Os dados que você usa para determinar a precisão dos modelos devem conter uma coluna que possa ser mapeada para a coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="72aa7-122">The data that you use to determine the accuracy of the models must contain a column that can be mapped to the predictable column.</span></span> <span data-ttu-id="72aa7-123">Se essa coluna não existir, você poderá criar uma com valores vazios, mas ela precisa ter o mesmo tipo de dados que a coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="72aa7-123">If such a column does not exist, you can create one with empty values, but it must have the same data type as the predictable column.</span></span>  
  
#### <a name="to-map-the-inputs-to-the-model"></a><span data-ttu-id="72aa7-124">Para mapear as entradas para o modelo</span><span class="sxs-lookup"><span data-stu-id="72aa7-124">To map the inputs to the model</span></span>  
  
1.  <span data-ttu-id="72aa7-125">Clique com o botão direito do mouse na janela linhas conectando o **modelo de mineração** à janela **selecionar tabela de entrada** e selecione **Modificar Conexões**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-125">Right-click the lines connecting the **Mining Model** window to the **Select Input Table** window, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="72aa7-126">Observe que nem todas as colunas são mapeadas.</span><span class="sxs-lookup"><span data-stu-id="72aa7-126">Notice that not every column is mapped.</span></span> <span data-ttu-id="72aa7-127">Adicionaremos mapeamentos para várias **colunas da tabela**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-127">We will add mappings for several **Table Columns**.</span></span> <span data-ttu-id="72aa7-128">Também geraremos uma nova coluna de data de aniversário com base na coluna de data atual, visando melhorar a correspondência das colunas.</span><span class="sxs-lookup"><span data-stu-id="72aa7-128">We will also generate a new birth date column based on the current date column, so that the columns match better.</span></span>  
  
2.  <span data-ttu-id="72aa7-129">Em **coluna da tabela**, clique na `Bike Buyer` célula e selecione ProspectiveBuyer. Unknown na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="72aa7-129">Under **Table Column**, click the `Bike Buyer` cell and select ProspectiveBuyer.Unknown from the dropdown.</span></span>  
  
     <span data-ttu-id="72aa7-130">Isso mapeia a coluna previsível, [Comprador de Bicicleta], para uma coluna da tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="72aa7-130">This maps the predictable column, [Bike Buyer], to an input table column.</span></span>  
  
3.  <span data-ttu-id="72aa7-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-131">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="72aa7-132">Em **Gerenciador de soluções**, clique com o botão direito do mouse na exibição da fonte de dados de **endereçamento direcionada** e selecione **Designer de exibição**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-132">In **Solution Explorer**, right-click the **Targeted Mailing** data source view and select **View Designer**.</span></span>  
  
5.  <span data-ttu-id="72aa7-133">Clique com o botão direito do mouse na tabela, ProspectiveBuyer e selecione **novo cálculo nomeado**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-133">Right-click the table, ProspectiveBuyer, and select **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="72aa7-134">Na caixa de diálogo **criar cálculo nomeado** , para **nome da coluna**, digite `calcAge` .</span><span class="sxs-lookup"><span data-stu-id="72aa7-134">In the **Create Named Calculation** dialog box, for **Column name**, type `calcAge`.</span></span>  
  
7.  <span data-ttu-id="72aa7-135">Para **Descrição**, digite **Calculate age com base em DataDeNascimento**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-135">For **Description**, type **Calculate age based on birthdate**.</span></span>  
  
8.  <span data-ttu-id="72aa7-136">Na caixa **expressão** , digite `DATEDIFF(YYYY,[BirthDate],getdate())` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-136">In the **Expression** box, type `DATEDIFF(YYYY,[BirthDate],getdate())` and then click **OK**.</span></span>  
  
     <span data-ttu-id="72aa7-137">Como a tabela de entrada não tem nenhuma coluna de **idade** correspondente à do modelo, você pode usar essa expressão para calcular a idade do cliente da coluna DataDeNascimento na tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="72aa7-137">Because the input table has no **Age** column corresponding to the one in the model, you can use this expression to calculate customer age from the BirthDate column in the input table.</span></span> <span data-ttu-id="72aa7-138">Como a **idade** foi identificada como a coluna mais influente para prever a compra de bicicletas, ela deve existir tanto no modelo quanto na tabela de entrada.</span><span class="sxs-lookup"><span data-stu-id="72aa7-138">Since **Age** was identified as the most influential column for predicting bike buying, it must exist in both the model and in the input table.</span></span>  
  
9. <span data-ttu-id="72aa7-139">No designer de mineração de dados, selecione a guia **previsão do modelo de mineração** e abra novamente a janela **Modificar Conexões** .</span><span class="sxs-lookup"><span data-stu-id="72aa7-139">In Data Mining Designer, select the **Mining Model Prediction** tab and re-open the **Modify Connections** window.</span></span>  
  
10. <span data-ttu-id="72aa7-140">Em **coluna da tabela**, clique na célula **idade** e selecione ProspectiveBuyer. Calc na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="72aa7-140">Under **Table Column**, click the **Age** cell and select ProspectiveBuyer.calcAge from the dropdown.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="72aa7-141">Se você não encontrar a coluna na lista, poderá ter que atualizar a definição da exibição da fonte de dados que é carregada no designer.</span><span class="sxs-lookup"><span data-stu-id="72aa7-141">If you do not see the column in the list, you might have to refresh the definition of the data source view that is loaded in the designer.</span></span> <span data-ttu-id="72aa7-142">Para fazer isso, no menu **arquivo** , selecione **salvar tudo**e, em seguida, feche e abra novamente o projeto no designer.</span><span class="sxs-lookup"><span data-stu-id="72aa7-142">To do this, from the **File** menu, select **Save all**, and then close and re-open the project in the designer.</span></span>  
  
11. <span data-ttu-id="72aa7-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-143">Click **OK**.</span></span>  
  
## <a name="designing-the-prediction-query"></a><span data-ttu-id="72aa7-144">Criando a consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="72aa7-144">Designing the Prediction Query</span></span>  
  
1.  <span data-ttu-id="72aa7-145">O primeiro botão na barra de ferramentas da guia **previsão do modelo de mineração** é alternar para modo de exibição de **design/alternar para exibição de resultado/alternar para o botão de exibição de consulta** .</span><span class="sxs-lookup"><span data-stu-id="72aa7-145">The first button on the toolbar of the **Mining Model Prediction** tab is the **Switch to design view / Switch to result view / Switch to query view** button.</span></span> <span data-ttu-id="72aa7-146">Clique na seta para baixo nesse botão e selecione **design**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-146">Click the down arrow on this button, and select **Design**.</span></span>  
  
2.  <span data-ttu-id="72aa7-147">Na grade da guia **previsão do modelo de mineração** , clique na célula na primeira linha vazia da coluna **origem** e selecione **função de previsão**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-147">In the grid on the **Mining Model Prediction** tab, click the cell in the first empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
3.  <span data-ttu-id="72aa7-148">Na linha **função de previsão** , na coluna **campo** , selecione `PredictProbability` .</span><span class="sxs-lookup"><span data-stu-id="72aa7-148">In the **Prediction Function** row, in the **Field** column, select `PredictProbability`.</span></span>  
  
     <span data-ttu-id="72aa7-149">Na coluna **alias** da mesma linha, digite **probabilidade de resultado**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-149">In the **Alias** column of the same row, type **Probability of result**.</span></span>  
  
4.  <span data-ttu-id="72aa7-150">Na janela **modelo de mineração** acima, selecione e arraste [comprador de bicicleta] para a célula **critérios/argumento** .</span><span class="sxs-lookup"><span data-stu-id="72aa7-150">From the **Mining Model** window above, select and drag [Bike Buyer] into the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="72aa7-151">Quando você permitir, acesse [TM_Decision_Tree]. [Comprador de bicicleta] aparece na célula **critérios/argumento** .</span><span class="sxs-lookup"><span data-stu-id="72aa7-151">When you let go, [TM_Decision_Tree].[Bike Buyer] appears in the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="72aa7-152">Isso especifica a coluna de destino da função `PredictProbability`.</span><span class="sxs-lookup"><span data-stu-id="72aa7-152">This specifies the target column for the `PredictProbability` function.</span></span> <span data-ttu-id="72aa7-153">Para obter mais informações sobre o functions, consulte [Data Mining Extensions &#40;DMX&#41; referência de função](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="72aa7-153">For more information about functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
5.  <span data-ttu-id="72aa7-154">Clique na próxima linha vazia na coluna **origem** e selecione **TM_Decision_Tree** modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="72aa7-154">Click the next empty row in the **Source** column, and then select **TM_Decision_Tree** mining model.</span></span>  
  
6.  <span data-ttu-id="72aa7-155">Na `TM_Decision_Tree` linha, na coluna **campo** , selecione `Bike Buyer` .</span><span class="sxs-lookup"><span data-stu-id="72aa7-155">In the `TM_Decision_Tree` row, in the **Field** column, select `Bike Buyer`.</span></span>  
  
7.  <span data-ttu-id="72aa7-156">Na `TM_Decision_Tree` linha, na coluna **critérios/argumento** , digite `=1` .</span><span class="sxs-lookup"><span data-stu-id="72aa7-156">In the `TM_Decision_Tree` row, in the **Criteria/Argument** column, type `=1`.</span></span>  
  
8.  <span data-ttu-id="72aa7-157">Clique na próxima linha vazia na coluna **origem** e selecione **tabela ProspectiveBuyer**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-157">Click the next empty row in the **Source** column, and then select **ProspectiveBuyer table**.</span></span>  
  
9. <span data-ttu-id="72aa7-158">Na `ProspectiveBuyer` linha, na coluna **campo** , selecione **ProspectiveBuyerKey**.</span><span class="sxs-lookup"><span data-stu-id="72aa7-158">In the `ProspectiveBuyer` row, in the **Field** column, select **ProspectiveBuyerKey**.</span></span>  
  
     <span data-ttu-id="72aa7-159">Essa ação adicionará o identificador exclusivo à consulta de previsão para que você possa identificar a probabilidade de alguém comprar ou não uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="72aa7-159">This adds the unique identifier to the prediction query so that you can identify who is and who is not likely to buy a bicycle.</span></span>  
  
10. <span data-ttu-id="72aa7-160">Adicione mais cinco linhas à grade.</span><span class="sxs-lookup"><span data-stu-id="72aa7-160">Add five more rows to the grid.</span></span> <span data-ttu-id="72aa7-161">Para cada linha, selecione a **tabela ProspectiveBuyer** como a **origem** e, em seguida, adicione as seguintes colunas nas células do **campo** :</span><span class="sxs-lookup"><span data-stu-id="72aa7-161">For each row, select **ProspectiveBuyer table** as the **Source** and then add the following columns in the **Field** cells:</span></span>  
  
    -   <span data-ttu-id="72aa7-162">calcAge</span><span class="sxs-lookup"><span data-stu-id="72aa7-162">calcAge</span></span>  
  
    -   <span data-ttu-id="72aa7-163">LastName</span><span class="sxs-lookup"><span data-stu-id="72aa7-163">LastName</span></span>  
  
    -   <span data-ttu-id="72aa7-164">Nome</span><span class="sxs-lookup"><span data-stu-id="72aa7-164">FirstName</span></span>  
  
    -   <span data-ttu-id="72aa7-165">AddressLine1</span><span class="sxs-lookup"><span data-stu-id="72aa7-165">AddressLine1</span></span>  
  
    -   <span data-ttu-id="72aa7-166">AddressLine2</span><span class="sxs-lookup"><span data-stu-id="72aa7-166">AddressLine2</span></span>  
  
 <span data-ttu-id="72aa7-167">Por fim, execute a consulta e navegue pelos resultados.</span><span class="sxs-lookup"><span data-stu-id="72aa7-167">Finally, run the query and browse the results.</span></span>  
  
 <span data-ttu-id="72aa7-168">O **Construtor de consultas de previsão** também inclui estes controles:</span><span class="sxs-lookup"><span data-stu-id="72aa7-168">The **Prediction Query Builder** also includes these controls:</span></span>  
  
-   <span data-ttu-id="72aa7-169">**Mostrar** caixa de seleção</span><span class="sxs-lookup"><span data-stu-id="72aa7-169">**Show** check box</span></span>  
  
     <span data-ttu-id="72aa7-170">Permite remover as cláusulas de consulta sem precisar excluí-las do designer.</span><span class="sxs-lookup"><span data-stu-id="72aa7-170">Lets you remove clauses from the query without having to delete them from the designer.</span></span> <span data-ttu-id="72aa7-171">Essa opção pode ser útil quando você está trabalhando com consultas complexas e deseja preservar a sintaxe sem precisar copiar e colar a linguagem DMX na janela.</span><span class="sxs-lookup"><span data-stu-id="72aa7-171">This can be useful when you are working with complex queries and want to preserve syntax without having to copy and paste DMX into the window.</span></span>  
  
-   <span data-ttu-id="72aa7-172">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="72aa7-172">**Group**</span></span>  
  
     <span data-ttu-id="72aa7-173">insere um parênteses de abertura (à esquerda) no início da linha selecionada, ou insere um parêntese de fechamento (à direita) no final da linha atual.</span><span class="sxs-lookup"><span data-stu-id="72aa7-173">Inserts an opening (left) parentheses at the beginning of the selected line, or inserts a closing (right) parenthesis at the end of the current line.</span></span>  
  
-   <span data-ttu-id="72aa7-174">**E/OU**</span><span class="sxs-lookup"><span data-stu-id="72aa7-174">**AND/OR**</span></span>  
  
     <span data-ttu-id="72aa7-175">insere o operador `AND` ou o operador `OR` logo após a função ou coluna atual.</span><span class="sxs-lookup"><span data-stu-id="72aa7-175">Inserts the  `AND` operator or the `OR` operator immediately after the current function or column.</span></span>  
  
#### <a name="to-run-the-query-and-view-results"></a><span data-ttu-id="72aa7-176">Para executar a consulta e exibir resultados</span><span class="sxs-lookup"><span data-stu-id="72aa7-176">To run the query and view results</span></span>  
  
1.  <span data-ttu-id="72aa7-177">Na guia **previsão do modelo de mineração** , selecione o botão **resultado** .</span><span class="sxs-lookup"><span data-stu-id="72aa7-177">In the **Mining Model Prediction** tab, select the **Result** button.</span></span>  
  
2.  <span data-ttu-id="72aa7-178">Depois que a consulta for executada e os resultados exibidos, você poderá revisá-los.</span><span class="sxs-lookup"><span data-stu-id="72aa7-178">After the query runs and the results are displayed, you can review the results.</span></span>  
  
     <span data-ttu-id="72aa7-179">A guia **previsão do modelo de mineração** exibe informações de contato para clientes potenciais que provavelmente são compradores de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="72aa7-179">The **Mining Model Prediction** tab displays contact information for potential customers who are likely to be bike buyers.</span></span> <span data-ttu-id="72aa7-180">A **probabilidade de coluna de resultado** indica a probabilidade de a previsão estar correta.</span><span class="sxs-lookup"><span data-stu-id="72aa7-180">The **Probability of result** column indicates the probability of the prediction being correct.</span></span> <span data-ttu-id="72aa7-181">Você poderá usar esses resultados para determinar para quais clientes em potencial a mala direta deverá ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="72aa7-181">You can use these results to determine which potential customers to target for the mailing.</span></span>  
  
3.  <span data-ttu-id="72aa7-182">Neste momento, você pode salvar os resultados.</span><span class="sxs-lookup"><span data-stu-id="72aa7-182">At this point, you can save the results.</span></span> <span data-ttu-id="72aa7-183">Você tem três opções:</span><span class="sxs-lookup"><span data-stu-id="72aa7-183">You have three options:</span></span>  
  
    -   <span data-ttu-id="72aa7-184">Clique com o botão direito do mouse em uma linha de dados nos resultados e selecione **copiar** para salvar apenas esse valor (e o título da coluna) na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="72aa7-184">Right-click a row of data in the results, and select **Copy** to save just that value (and the column heading) to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="72aa7-185">Clique com o botão direito do mouse em qualquer linha nos resultados e selecione **copiar tudo** para copiar todo o conjunto de resultados, incluindo títulos de coluna, para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="72aa7-185">Right-click any row in the results, and select **Copy All** to copy the entire result set, including column headings, to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="72aa7-186">Clique em **salvar resultado da consulta** para salvar os resultados diretamente em um banco de dados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="72aa7-186">Click **Save query result** to save the results directly to a database as follows:</span></span>  
  
        1.  <span data-ttu-id="72aa7-187">Na caixa de diálogo **salvar resultado da consulta de mineração de dados** , selecione uma fonte de dados ou defina uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="72aa7-187">In the **Save Data Mining Query Result** dialog box, select a data source, or define a new data source.</span></span>  
  
        2.  <span data-ttu-id="72aa7-188">Digite um nome para a tabela que conterá os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="72aa7-188">Type a name for the table that will contain the query results.</span></span>  
  
        3.  <span data-ttu-id="72aa7-189">Use a opção, **Adicionar ao DSV**, para criar a tabela e adicioná-la a uma exibição da fonte de dados existente.</span><span class="sxs-lookup"><span data-stu-id="72aa7-189">Use the option, **Add to DSV**, to create the table and add it to an existing data source view.</span></span> <span data-ttu-id="72aa7-190">Isso será útil se você quiser manter todas as tabelas relacionadas para um modelo, como dados de treinamento, dados de origem de previsão e resultados da consulta, na mesma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="72aa7-190">This is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source view.</span></span>  
  
        4.  <span data-ttu-id="72aa7-191">Use a opção **substituir se existir**, para atualizar uma tabela existente com os resultados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="72aa7-191">Use the option, **Overwrite if exists**, to update an existing table with the latest results.</span></span>  
  
             <span data-ttu-id="72aa7-192">Use a opção para substituir a tabela se você adicionou alguma coluna à consulta de previsão, alterou os nomes ou tipos de dados de alguma coluna na consulta de previsão, ou se executou alguma instrução ALTER na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="72aa7-192">You must use the option to overwrite the table if you have added any columns to the prediction query, changed the names or data types of any columns in the prediction query, or if you have run any ALTER statements on the destination table.</span></span>  
  
             <span data-ttu-id="72aa7-193">Além disso, se várias colunas tiverem o mesmo nome (por exemplo, a **expressão**de nome de coluna padrão), você deverá criar um alias para as colunas com nomes duplicados ou um erro será gerado quando o designer tentar salvar os resultados em SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72aa7-193">Also, if multiple columns have the same name (for example, the default column name **Expression**) you must create an alias for the columns with duplicate names, or an error will be raised when the designer tries to save the results to SQL Server.</span></span> <span data-ttu-id="72aa7-194">A razão é que o SQL Server não permite que várias colunas tenham o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="72aa7-194">The reason is that SQL Server does not allow multiple columns to have the same name.</span></span>  
  
             <span data-ttu-id="72aa7-195">Para obter mais informações, consulte [caixa de diálogo Salvar resultado da consulta de mineração de dados &#40;exibição de previsão do modelo de mineração&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span><span class="sxs-lookup"><span data-stu-id="72aa7-195">For more information, see [Save Data Mining Query Result Dialog Box &#40;Mining Model Prediction View&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="72aa7-196">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="72aa7-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="72aa7-197">Usando o detalhamento em dados de estrutura &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="72aa7-197">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="72aa7-198">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72aa7-198">See Also</span></span>  
 [<span data-ttu-id="72aa7-199">Criar uma consulta de previsão usando o construtor de consultas de previsão</span><span class="sxs-lookup"><span data-stu-id="72aa7-199">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
