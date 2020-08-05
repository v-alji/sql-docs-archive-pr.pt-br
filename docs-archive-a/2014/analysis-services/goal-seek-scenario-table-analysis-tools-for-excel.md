---
title: Cenário de busca de meta (ferramentas de análise de tabela para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- scenario analysis
- goal seek scenario
ms.assetid: efe50306-cf7c-46b3-9cc4-e7f0b6968b0c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b3b4df4f78a2d3652b1dac3c566e66507b523ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572264"
---
# <a name="goal-seek-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="d433d-102">Cenário de Metas a Atingir (Ferramentas de Análise de Tabela para Excel)</span><span class="sxs-lookup"><span data-stu-id="d433d-102">Goal Seek Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="d433d-103">![Botão Meta a Atingir em Ferramentas de Análise de Tabela](media/tat-goalseek.gif "Botão Meta a Atingir em Ferramentas de Análise de Tabela")</span><span class="sxs-lookup"><span data-stu-id="d433d-103">![Goal Seek button in Table Analysis tools](media/tat-goalseek.gif "Goal Seek button in Table Analysis tools")</span></span>  
  
 <span data-ttu-id="d433d-104">A ferramenta de cenário de **busca de meta** é complementar à ferramenta de cenário de [What If](what-if-scenario-table-analysis-tools-for-excel.md) .</span><span class="sxs-lookup"><span data-stu-id="d433d-104">The **Goal Seek** scenario tool is complementary to the [What If](what-if-scenario-table-analysis-tools-for-excel.md) scenario tool.</span></span> <span data-ttu-id="d433d-105">A ferramenta **What-If** indica o impacto de fazer uma alteração, enquanto a ferramenta **meta Seek** informa os fatores subjacentes que devem ser alterados para obter um resultado desejado.</span><span class="sxs-lookup"><span data-stu-id="d433d-105">The **What-If** tool tells you the impact of making a change, whereas the **Goal Seek** tool tells you the underlying factors that must change to achieve a desired result.</span></span>  
  
 <span data-ttu-id="d433d-106">Por exemplo, digamos que seu objetivo seja aumentar a satisfação do cliente.</span><span class="sxs-lookup"><span data-stu-id="d433d-106">For example, let's say your goal is to increase customer satisfaction.</span></span> <span data-ttu-id="d433d-107">Você pode usar a análise de **meta Seek** para determinar quais fatores são mais prováveis de aumentar a satisfação do cliente e decidir se essas alterações são econômicas.</span><span class="sxs-lookup"><span data-stu-id="d433d-107">You can use **Goal Seek** analysis to determine which factors would be most likely to increase customer satisfaction, and decide whether those changes are cost-effective.</span></span>  
  
 <span data-ttu-id="d433d-108">Quando a ferramenta conclui sua análise, ela cria duas colunas novas na tabela de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="d433d-108">When the tool finishes its analysis, it creates two new columns in the source data table.</span></span> <span data-ttu-id="d433d-109">Essas colunas mostram a *probabilidade* de que o resultado de destino possa ser obtido e a alteração recomendada, se houver.</span><span class="sxs-lookup"><span data-stu-id="d433d-109">These columns show the *likelihood* that the targeted outcome can be achieved, and the recommended change, if any.</span></span>  
  
 <span data-ttu-id="d433d-110">A ferramenta pode analisar um conjunto de dados e fazer previsões para todo o conjunto ou você pode criar a análise e testar os cenários um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="d433d-110">The tool can analyze a set of data and make predictions for the entire set, or you can create the analysis and then test scenarios one at a time.</span></span>  
  
## <a name="using-the-goal-seek-scenario-tool"></a><span data-ttu-id="d433d-111">Usando a ferramenta de cenário Meta a Atingir</span><span class="sxs-lookup"><span data-stu-id="d433d-111">Using the Goal Seek Scenario Tool</span></span>  
  
1.  <span data-ttu-id="d433d-112">Abra uma tabela do Excel.</span><span class="sxs-lookup"><span data-stu-id="d433d-112">Open an Excel table.</span></span>  
  
2.  <span data-ttu-id="d433d-113">Clique em **cenários**e selecione **meta buscar**.</span><span class="sxs-lookup"><span data-stu-id="d433d-113">Click **Scenarios**, and select **Goal Seek**.</span></span>  
  
3.  <span data-ttu-id="d433d-114">Na caixa de diálogo **análise de cenário: meta de busca** , selecione a coluna que contém o valor de destino da lista.</span><span class="sxs-lookup"><span data-stu-id="d433d-114">In the **Scenario Analysis: Goal Seek** dialog box, select the column that contains the target value from the list.</span></span>  
  
4.  <span data-ttu-id="d433d-115">Especifique o valor que você deseja atingir.</span><span class="sxs-lookup"><span data-stu-id="d433d-115">Specify the value that you want to achieve.</span></span>  
  
     <span data-ttu-id="d433d-116">Se a meta da coluna contiver valores numéricos contínuos, também será possível especificar uma diminuição ou um aumento desejado no valor.</span><span class="sxs-lookup"><span data-stu-id="d433d-116">If the column goal contains continuous numeric values, you can also specify a desired increase or decrease in the value.</span></span> <span data-ttu-id="d433d-117">Por exemplo, você pode escolher **vendas** como a coluna e especificar que o destino é um aumento de 120%.</span><span class="sxs-lookup"><span data-stu-id="d433d-117">For example, you might choose **Sales** as the column and specify that the target is an increase of 120%.</span></span>  
  
     <span data-ttu-id="d433d-118">Ou, você pode especificar a meta como um intervalo de valores, digitando um limite inferior e um limite superior.</span><span class="sxs-lookup"><span data-stu-id="d433d-118">Or, you can specify the goal as a range of values, by typing a lower and upper limit.</span></span>  
  
5.  <span data-ttu-id="d433d-119">Especifique a coluna que contém os valores que serão alterados.</span><span class="sxs-lookup"><span data-stu-id="d433d-119">Specify the column that contains the values you will change.</span></span> <span data-ttu-id="d433d-120">Em outras palavras, escolha a coluna que será manipulada para produzir o resultado desejado.</span><span class="sxs-lookup"><span data-stu-id="d433d-120">In other words, pick the column that will be manipulated to produce the desired result.</span></span>  
  
6.  <span data-ttu-id="d433d-121">Opcionalmente, clique em **escolher colunas a serem usadas para análise**e selecione as colunas que contêm informações úteis.</span><span class="sxs-lookup"><span data-stu-id="d433d-121">Optionally, click **Choose columns to be used for analysis**, and select columns that contain useful information.</span></span> <span data-ttu-id="d433d-122">Desmarque as colunas que não colaborarão para a análise.</span><span class="sxs-lookup"><span data-stu-id="d433d-122">Deselect columns that will not contribute to the analysis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d433d-123">Não desmarque colunas que você usará para a meta ou a alteração.</span><span class="sxs-lookup"><span data-stu-id="d433d-123">Do not deselect columns that you will use for either the goal or the change.</span></span> <span data-ttu-id="d433d-124">Essas colunas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="d433d-124">These columns are required.</span></span>  
  
7.  <span data-ttu-id="d433d-125">Especifique se você deseja fazer previsões para toda a tabela ou apenas para a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d433d-125">Specify whether you want to make predictions for the entire table, or for only the selected row.</span></span>  
  
8.  <span data-ttu-id="d433d-126">Se você selecionou a opção de **tabela inteira** , a ferramenta adicionará as previsões à tabela de origem em duas novas colunas.</span><span class="sxs-lookup"><span data-stu-id="d433d-126">If you selected the **Entire table** option, the tool adds the predictions to the source table in two new columns.</span></span>  
  
9. <span data-ttu-id="d433d-127">Se você selecionou a opção **nessa linha**, os resultados da análise serão gerados para a caixa de diálogo para revisão.</span><span class="sxs-lookup"><span data-stu-id="d433d-127">If you selected the option **On this row**, the results of analysis are output to the dialog box for review.</span></span> <span data-ttu-id="d433d-128">A caixa de diálogo permanece aberta para que você possa continuar experimentando valores e metas diferentes.</span><span class="sxs-lookup"><span data-stu-id="d433d-128">The dialog box stays open so that you can continue trying out different values and goals.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="d433d-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d433d-129">Requirements</span></span>  
 <span data-ttu-id="d433d-130">Essa ferramenta usa o algoritmo Regressão Logística da Microsoft, que pode processar valores numéricos ou discretos.</span><span class="sxs-lookup"><span data-stu-id="d433d-130">This tool uses the Microsoft Logistic Regression algorithm, which can process either numeric or discrete values.</span></span>  
  
 <span data-ttu-id="d433d-131">Você pode executar a previsão várias vezes e selecionar colunas diferentes depois, mas cada combinação de meta e alteração deve ser calculada separadamente.</span><span class="sxs-lookup"><span data-stu-id="d433d-131">You can run the prediction multiple times, and select different columns later, but each combination of a goal and a change must be calculated separately.</span></span>  
  
 <span data-ttu-id="d433d-132">Você poderá obter resultados melhores se selecionar colunas para análise que contenham informações úteis.</span><span class="sxs-lookup"><span data-stu-id="d433d-132">You can achieve better results if you select columns for analysis that contain useful information.</span></span> <span data-ttu-id="d433d-133">No entanto, se você incluir poucas colunas, talvez seja difícil obter um resultado.</span><span class="sxs-lookup"><span data-stu-id="d433d-133">However, if you include too few columns, it might be difficult to obtain a result.</span></span>  
  
 <span data-ttu-id="d433d-134">Quando você criar uma previsão de cada vez, não se esqueça de selecionar uma linha que ainda não contenha o resultado desejado ou talvez receba um erro.</span><span class="sxs-lookup"><span data-stu-id="d433d-134">When you create predictions one at a time, be sure to select a row that does not already contain the desired result, or you may get an error.</span></span> <span data-ttu-id="d433d-135">Em outras palavras, se a finalidade da meta a atingir for determinar fatores que incentivem compras de bicicletas, inclua apenas clientes que não compraram uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="d433d-135">In other words, if the purpose of goal seeking is to determine factors that encourage bike purchases, you should only include customers who did not purchase a bike.</span></span>  
  
## <a name="understanding-the-results-of-goal-seek-analysis"></a><span data-ttu-id="d433d-136">Compreendendo os resultados da análise Meta a Atingir</span><span class="sxs-lookup"><span data-stu-id="d433d-136">Understanding the Results of Goal Seek Analysis</span></span>  
 <span data-ttu-id="d433d-137">Quando você cria um cenário Meta a Atingir, a ferramenta executa três ações:</span><span class="sxs-lookup"><span data-stu-id="d433d-137">When you create a goal seeking scenario, the tool does three things:</span></span>  
  
-   <span data-ttu-id="d433d-138">Cria uma estrutura de mineração de dados que armazena os fatos principais sobre os dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="d433d-138">Creates a data mining structure that stores key facts about the data in your table.</span></span>  
  
-   <span data-ttu-id="d433d-139">Cria um modelo de mineração de regressão logística com base nos dados.</span><span class="sxs-lookup"><span data-stu-id="d433d-139">Creates a logistic regression mining model based on the data.</span></span>  
  
-   <span data-ttu-id="d433d-140">Cria uma previsão para cada valor especificado.</span><span class="sxs-lookup"><span data-stu-id="d433d-140">Creates a prediction for each value that you specify.</span></span>  
  
 <span data-ttu-id="d433d-141">Se você testar os cenários de meta a atingir um de cada vez, poderá exibir os resultados interativamente.</span><span class="sxs-lookup"><span data-stu-id="d433d-141">If you test goal-seeking scenarios one at a time, you can view the results interactively.</span></span> <span data-ttu-id="d433d-142">Isso é o mesmo que criar uma *consulta de Previsão Singleton*.</span><span class="sxs-lookup"><span data-stu-id="d433d-142">This is the same as creating a *singleton prediction query*.</span></span>  
  
 <span data-ttu-id="d433d-143">A ferramenta relata no painel de **resultados** da caixa de diálogo se foi bem-sucedida ao encontrar um cenário que atinja a meta desejada.</span><span class="sxs-lookup"><span data-stu-id="d433d-143">The tool reports in the **Results** pane of the dialog box whether it was successful in finding a scenario that achieves the desired goal.</span></span> <span data-ttu-id="d433d-144">Caso uma solução bem-sucedida tenha sido encontrada, a ferramenta também gerará uma recomendação informando sobre a alteração necessária.</span><span class="sxs-lookup"><span data-stu-id="d433d-144">If a successful solution was found, the tool also generates a recommendation that tells you the required change.</span></span> <span data-ttu-id="d433d-145">Por exemplo, a ferramenta de **busca de meta** pode informar que a distância de comutação deve ser inferior a 5 milhas.</span><span class="sxs-lookup"><span data-stu-id="d433d-145">For example, the **Goal Seek** tool might tell you that the commuting distance should be less than 5 miles.</span></span>  
  
 <span data-ttu-id="d433d-146">Resultados do exemplo:</span><span class="sxs-lookup"><span data-stu-id="d433d-146">Example results:</span></span>  
  
 <span data-ttu-id="d433d-147">**A opção Meta a Atingir de Interesse na Compra encontrou uma solução.**</span><span class="sxs-lookup"><span data-stu-id="d433d-147">**Goal Seeking for Interest in Buying has found a solution.**</span></span>  
  
 <span data-ttu-id="d433d-148">**A correspondência mais próxima obtida com a alteração de 'Commute distance' para '2-5 miles'.**</span><span class="sxs-lookup"><span data-stu-id="d433d-148">**Closest match obtained by changing 'Commute distance' to '2-5 miles'.**</span></span>  
  
 <span data-ttu-id="d433d-149">Como esse resultado se baseia em uma linha existente na tabela de dados, isso significa que, para um determinado cliente, se todos os dados referentes ao cliente permanecerem iguais, mas a distância do trabalho do cliente for reduzida para 2-5 miles, ele provavelmente ficará um pouco mais inclinado a comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="d433d-149">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's commute was reduced to 2-5 miles, the customer would be somewhat more likely buy a bicycle.</span></span>  
  
 <span data-ttu-id="d433d-150">Se você criar previsões de meta-busca para todas as linhas na tabela do Excel especificando a **tabela inteira**, a ferramenta criará duas novas colunas na tabela de dados original.</span><span class="sxs-lookup"><span data-stu-id="d433d-150">If you create goal-seeking predictions for all the rows in the Excel table by specifying **Entire table**, thetool creates two new columns in the original data table.</span></span> <span data-ttu-id="d433d-151">A primeira coluna adicionada à tabela contém uma marca de seleção em um círculo verde, para indicar que a meta pode ser alcançada, ou um X em um círculo vermelho, para indicar que não é possível fazer nenhuma alteração para permitir a meta.</span><span class="sxs-lookup"><span data-stu-id="d433d-151">The first column that is added to the table contains either a check mark in a green circle, to indicate that the goal can be met, or an X mark in a red circle, to indicate that no changes can be made that will enable the goal.</span></span>  
  
 <span data-ttu-id="d433d-152">A segunda coluna contém a alteração recomendada.</span><span class="sxs-lookup"><span data-stu-id="d433d-152">The second column contains the recommended change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d433d-153">O nível de confiança da recomendação e seu êxito são predeterminados pelo algoritmo e não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="d433d-153">The confidence level for the recommendation and its success are predetermined by the algorithm and cannot be changed.</span></span>  
  
## <a name="related-tools"></a><span data-ttu-id="d433d-154">Ferramentas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d433d-154">Related Tools</span></span>  
 <span data-ttu-id="d433d-155">O Cliente de Mineração de Dados para Excel, um suplemento separado que fornece mais funções avançadas de mineração de dados, contém assistentes para criação de modelos de mineração de dados que preveem comportamento.</span><span class="sxs-lookup"><span data-stu-id="d433d-155">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="d433d-156">Para obter mais informações, consulte [criando um modelo de mineração de dados](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="d433d-156">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
 <span data-ttu-id="d433d-157">Para obter mais informações sobre o algoritmo usado pela ferramenta de cenário de **busca de meta** , consulte o tópico "algoritmo de regressão logística da Microsoft" nos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] manuais online do.</span><span class="sxs-lookup"><span data-stu-id="d433d-157">For more information about the algorithm used by the **Goal Seek** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d433d-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d433d-158">See Also</span></span>  
 [<span data-ttu-id="d433d-159">Ferramentas de Análise de Tabela para Excel</span><span class="sxs-lookup"><span data-stu-id="d433d-159">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
