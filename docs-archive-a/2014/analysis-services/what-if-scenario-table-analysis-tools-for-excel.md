---
title: Cenário de hipóteses (ferramentas de análise de tabela para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- what if scenario
- scenario analysis
ms.assetid: 4df5a5c5-1983-4009-a7c5-cd340649fd2f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4bb5c5e866c1320c297fb4f2760bca58623f6601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686380"
---
# <a name="what-if-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="a320e-102">Cenário E-Se (Ferramentas de Análise de Tabela para Excel)</span><span class="sxs-lookup"><span data-stu-id="a320e-102">What-If Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="a320e-103">![Botão Cenário E-Se em Ferramentas de Análise de Tabela](media/tat-whatif.gif "Botão Cenário E-Se em Ferramentas de Análise de Tabela")</span><span class="sxs-lookup"><span data-stu-id="a320e-103">![What If Scenario button in Table Analysis tools](media/tat-whatif.gif "What If Scenario button in Table Analysis tools")</span></span>

 <span data-ttu-id="a320e-104">A ferramenta de cenário de **hipóteses** analisa padrões em dados existentes e, em seguida, permite que você avalie o efeito que as alterações em uma coluna teriam no valor de uma coluna diferente.</span><span class="sxs-lookup"><span data-stu-id="a320e-104">The **What-If** scenario tool analyzes patterns in existing data, and then enables you to evaluate the effect that changes in one column would have on the value of a different column.</span></span>

 <span data-ttu-id="a320e-105">Por exemplo, você pode explorar o efeito de aumentar o preço de um item em seu total de vendas.</span><span class="sxs-lookup"><span data-stu-id="a320e-105">For example, you could explore the effect of raising the price of an item on its total sales.</span></span>

 <span data-ttu-id="a320e-106">A ferramenta é flexível em relação ao número de previsões que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="a320e-106">The tool is flexible about the number of predictions you can create.</span></span> <span data-ttu-id="a320e-107">Após a conclusão da análise inicial, é possível prever alterações para todos os dados da tabela ou inserir um valor de teste de cada vez.</span><span class="sxs-lookup"><span data-stu-id="a320e-107">After the initial analysis is complete, you can either predict changes for all the data in the table, or enter test values one at a time.</span></span>

## <a name="using-the-what-if-scenario-tool"></a><span data-ttu-id="a320e-108">Usando a ferramenta de cenário E-Se</span><span class="sxs-lookup"><span data-stu-id="a320e-108">Using the What-If Scenario Tool</span></span>

1.  <span data-ttu-id="a320e-109">Abra uma tabela de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="a320e-109">Open an Excel data table.</span></span>

2.  <span data-ttu-id="a320e-110">Clique em **cenários**e, em seguida, selecione **What-If**.</span><span class="sxs-lookup"><span data-stu-id="a320e-110">Click **Scenarios**, and then select **What-If**.</span></span>

3.  <span data-ttu-id="a320e-111">Na caixa **cenário** , selecione a coluna que contém o valor que você irá alterar e especifique a alteração como um valor específico ou como uma porcentagem de alteração (aumentada ou diminuída) nos valores atuais.</span><span class="sxs-lookup"><span data-stu-id="a320e-111">In the **Scenario** box, select the column that contains the value you will change, and specify the change either as a specific value or as a percentage of change (either increased or decreased) on the current values.</span></span>

4.  <span data-ttu-id="a320e-112">Na caixa **o que acontecerá** , especifique a coluna para a qual você deseja avaliar o efeito.</span><span class="sxs-lookup"><span data-stu-id="a320e-112">In the **What happens to** box, specify the column for which you want to assess the effect.</span></span>

5.  <span data-ttu-id="a320e-113">Opcionalmente, clique em **escolher colunas a serem usadas para análise** para selecionar colunas que provavelmente serão úteis para fazer a previsão.</span><span class="sxs-lookup"><span data-stu-id="a320e-113">Optionally, click **Choose columns to be used for analysis** to select columns that are likely to be useful in making the prediction.</span></span> <span data-ttu-id="a320e-114">Também é possível desmarcar as colunas que provavelmente serão pouco úteis na detecção de padrões, como IDs ou nomes de linhas.</span><span class="sxs-lookup"><span data-stu-id="a320e-114">You can also deselect columns that are likely to be of little use in detecting patterns, such as row IDs or names.</span></span>

6.  <span data-ttu-id="a320e-115">Na caixa **especificar linha ou tabela** , escolha se deseja que o impacto seja avaliado apenas para a linha selecionada no momento ou para o conjunto completo de dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="a320e-115">In the **Specify row or table** box, choose whether you want the impact assessed for the currently selected row only, or for the complete set of data in the table.</span></span>

7.  <span data-ttu-id="a320e-116">Se você selecionar **nessa linha**, a ferramenta exibirá o resultado na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a320e-116">If you select **On this row**, the tool displays the result in the dialog box.</span></span> <span data-ttu-id="a320e-117">Enquanto a caixa de diálogo permanece aberta, você pode modificar as seleções para testar outros cenários.</span><span class="sxs-lookup"><span data-stu-id="a320e-117">While the dialog box remains open, you can modify your selections to test other scenarios.</span></span>

8.  <span data-ttu-id="a320e-118">Se você selecionar **tabela inteira**, a ferramenta exibirá uma mensagem de status na caixa de diálogo e adicionará duas novas colunas à tabela de dados original.</span><span class="sxs-lookup"><span data-stu-id="a320e-118">If you select **Entire table**, the tool displays a status message in the dialog box, and adds two new columns to the original data table.</span></span> <span data-ttu-id="a320e-119">Clique em **fechar** para exibir os resultados completos na planilha.</span><span class="sxs-lookup"><span data-stu-id="a320e-119">Click **Close** to view the complete results in the worksheet.</span></span>

### <a name="requirements"></a><span data-ttu-id="a320e-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a320e-120">Requirements</span></span>
 <span data-ttu-id="a320e-121">Essa ferramenta usa o algoritmo Regressão Logística da Microsoft, que dá suporte para previsão de valores numéricos ou discretos.</span><span class="sxs-lookup"><span data-stu-id="a320e-121">This tool uses the Microsoft Logistic Regression algorithm, which supports prediction of either numeric or discrete values.</span></span> <span data-ttu-id="a320e-122">No entanto, para obter os melhores resultados, sugerimos as seguintes práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="a320e-122">However, to achieve the best results, we suggest the following best practices:</span></span>

-   <span data-ttu-id="a320e-123">Selecione colunas para análise que contenham informações úteis.</span><span class="sxs-lookup"><span data-stu-id="a320e-123">Select columns for analysis that contain useful information.</span></span>

-   <span data-ttu-id="a320e-124">Se você incluir poucas colunas, talvez seja difícil obter um resultado.</span><span class="sxs-lookup"><span data-stu-id="a320e-124">If you include too few columns it may be difficult to obtain a result.</span></span>

-   <span data-ttu-id="a320e-125">Se você usar a opção **para valor** , deverá digitar um valor na caixa ou selecionar um valor na lista.</span><span class="sxs-lookup"><span data-stu-id="a320e-125">If you use the **To value** option, you must type a value in the box or select a value from the list.</span></span>

-   <span data-ttu-id="a320e-126">Se você usar a opção **percentual** , defina a alteração como uma porcentagem de aumento ou diminuição.</span><span class="sxs-lookup"><span data-stu-id="a320e-126">If you use the **Percentage** option, set the change as a percentage increase or decrease.</span></span> <span data-ttu-id="a320e-127">O padrão é 120%, significando um aumento de 20% sobre o valor atual.</span><span class="sxs-lookup"><span data-stu-id="a320e-127">The default is 120%, meaning a 20% increase over the current value.</span></span>

> [!NOTE]
>  <span data-ttu-id="a320e-128">Se você não definir um valor, talvez receba um erro.</span><span class="sxs-lookup"><span data-stu-id="a320e-128">If you do not set a value, you might receive an error.</span></span>

## <a name="understanding-the-results-of-what-if-analysis"></a><span data-ttu-id="a320e-129">Compreendendo os resultados da análise E-Se</span><span class="sxs-lookup"><span data-stu-id="a320e-129">Understanding the Results of What-If Analysis</span></span>
 <span data-ttu-id="a320e-130">Quando você cria um cenário de **hipóteses** , a ferramenta faz três coisas:</span><span class="sxs-lookup"><span data-stu-id="a320e-130">When you create a **What-If** scenario, the tool does three things:</span></span>

-   <span data-ttu-id="a320e-131">Cria uma estrutura de mineração de dados que armazena os fatos principais sobre os dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="a320e-131">Creates a data mining structure that stores key facts about the data in your table.</span></span>

-   <span data-ttu-id="a320e-132">Cria um modelo de mineração de regressão logística com base nos dados.</span><span class="sxs-lookup"><span data-stu-id="a320e-132">Creates a logistic regression mining model based on the data.</span></span>

-   <span data-ttu-id="a320e-133">Cria uma consulta de previsão para cada um dos valores especificados.</span><span class="sxs-lookup"><span data-stu-id="a320e-133">Creates a prediction query for each of the values you specify.</span></span>

 <span data-ttu-id="a320e-134">Você pode gerar todas as previsões de uma vez especificando a **tabela inteira**.</span><span class="sxs-lookup"><span data-stu-id="a320e-134">You can output all the predictions at one time by specifying **Entire table**.</span></span> <span data-ttu-id="a320e-135">A ferramenta cria duas colunas novas na tabela de dados original.</span><span class="sxs-lookup"><span data-stu-id="a320e-135">The tool then creates two new columns in the original data table.</span></span>

 <span data-ttu-id="a320e-136">As colunas adicionadas à tabela contêm dois tipos de informações: o valor previsto atribuído à alteração e sua confiança.</span><span class="sxs-lookup"><span data-stu-id="a320e-136">The columns that are added to the table contain two types of information: the predicted value given the change, and its confidence.</span></span> <span data-ttu-id="a320e-137">Confiança significa a probabilidade de a previsão estar correta.</span><span class="sxs-lookup"><span data-stu-id="a320e-137">Confidence means the probability that the prediction is correct.</span></span>

 <span data-ttu-id="a320e-138">Também é possível inserir um valor de alteração de cada vez na caixa de diálogo e exibir as previsões de modo interativo.</span><span class="sxs-lookup"><span data-stu-id="a320e-138">You can also enter change values one by one in the dialog box, and view the predictions interactively.</span></span> <span data-ttu-id="a320e-139">Isso é o mesmo que criar uma *consulta de Previsão Singleton*.</span><span class="sxs-lookup"><span data-stu-id="a320e-139">This is the same as creating a *singleton prediction query*.</span></span> <span data-ttu-id="a320e-140">Os resultados da consulta de previsão são incluídos na saída com as seguintes informações: o sucesso ou a falha da previsão, o valor previsto e o nível de confiança.</span><span class="sxs-lookup"><span data-stu-id="a320e-140">The results of the prediction query are output with the following information: the success or failure of prediction, the predicted value, and the confidence level.</span></span> <span data-ttu-id="a320e-141">O nível de confiança é mostrado como uma barra que contém uma linha pontilhada.</span><span class="sxs-lookup"><span data-stu-id="a320e-141">The confidence level is shown as a bar that contains a dotted line.</span></span> <span data-ttu-id="a320e-142">Quanto maior a linha pontilhada, maior a confiança no resultado.</span><span class="sxs-lookup"><span data-stu-id="a320e-142">The longer the dotted line, the higher the confidence in the result.</span></span>

 <span data-ttu-id="a320e-143">Por exemplo, se você estiver tentando determinar o efeito de aumentar a idade do cliente na disposição do cliente para comprar e aumentar a idade do cliente para 25, a ferramenta **What-If** consultará o modelo de data mining e retornará o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="a320e-143">For example, if you are trying to determine the effect of increasing the customer's age on the customer's willingness to buy, and increase the customer's age to 25, the **What-If** tool queries the data mining model and returns the following result:</span></span>

 <span data-ttu-id="a320e-144">**Análise E-Se para Compras de Bicicletas encontrou uma solução.**</span><span class="sxs-lookup"><span data-stu-id="a320e-144">**What-If Analysis for Purchases Bicycle has found a solution.**</span></span>

 <span data-ttu-id="a320e-145">**'Compras de Bicicletas' = sim**</span><span class="sxs-lookup"><span data-stu-id="a320e-145">**'Purchases Bicycle' = yes**</span></span>

 <span data-ttu-id="a320e-146">**Confiança: Razoável**</span><span class="sxs-lookup"><span data-stu-id="a320e-146">**Confidence: Fair**</span></span>

 <span data-ttu-id="a320e-147">Como esse resultado se baseia em uma linha existente na tabela de dados, isso significa que, para um determinado cliente, se todos os dados referentes ao cliente permanecerem iguais, mas a idade do cliente aumentar para 25, ele provavelmente comprará uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="a320e-147">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's age was increased to 25, the customer would likely buy a bicycle.</span></span>

 <span data-ttu-id="a320e-148">Incluir na saída as previsões para a tabela de dados original talvez facilite determinar se elas são úteis.</span><span class="sxs-lookup"><span data-stu-id="a320e-148">Outputting the predictions to the original data table might make it easier to determine whether the predictions are useful.</span></span>

## <a name="related-tools"></a><span data-ttu-id="a320e-149">Ferramentas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a320e-149">Related Tools</span></span>
 <span data-ttu-id="a320e-150">O Cliente de Mineração de Dados para Excel, um suplemento separado que fornece mais funções avançadas de mineração de dados, contém assistentes para criação de modelos de mineração de dados que preveem comportamento.</span><span class="sxs-lookup"><span data-stu-id="a320e-150">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="a320e-151">Para obter mais informações, consulte [criando um modelo de mineração de dados](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="a320e-151">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="a320e-152">Para obter mais informações sobre o algoritmo usado pela ferramenta de cenário de **hipóteses** , consulte o tópico "algoritmo de regressão logística da Microsoft" em manuais online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a320e-152">For more information about the algorithm used by the **What-If** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in SQL Server Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="a320e-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a320e-153">See Also</span></span>
 [<span data-ttu-id="a320e-154">Ferramentas de Análise de Tabela para Excel</span><span class="sxs-lookup"><span data-stu-id="a320e-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


