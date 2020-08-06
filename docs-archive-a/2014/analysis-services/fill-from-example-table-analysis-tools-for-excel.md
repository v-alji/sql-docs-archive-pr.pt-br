---
title: Preenchimento de exemplo (ferramentas de análise de tabela para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- fill from example
ms.assetid: dac57d8f-1c65-4878-8ea0-9c680df5e4fb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 69ff9f554c51240eb6f9151718d30677bfb57996
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680713"
---
# <a name="fill-from-example-table-analysis-tools-for-excel"></a><span data-ttu-id="b7825-102">Preencher com Base no Exemplo (Ferramentas de Análise de Tabela para Excel)</span><span class="sxs-lookup"><span data-stu-id="b7825-102">Fill From Example (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="b7825-103">![Botão Preencher com Base no Exemplo em Ferramentas de Análise de Tabela](media/tat-fillex.gif "Botão Preencher com Base no Exemplo em Ferramentas de Análise de Tabela")</span><span class="sxs-lookup"><span data-stu-id="b7825-103">![Fill From Example button in Table Analysis Tools](media/tat-fillex.gif "Fill From Example button in Table Analysis Tools")</span></span>  
  
 <span data-ttu-id="b7825-104">A ferramenta **preencher com exemplo** ajuda a criar novas colunas de dados com base em valores existentes.</span><span class="sxs-lookup"><span data-stu-id="b7825-104">The **Fill From Example** tool helps you build new columns of data based on existing values.</span></span>  
  
 <span data-ttu-id="b7825-105">Por exemplo, suponha que seus dados contenham uma coluna de **valor de compra** , uma coluna de **quantidade de pedidos** e uma coluna de **cliente Premier** com base em alguma fórmula usando as outras colunas.</span><span class="sxs-lookup"><span data-stu-id="b7825-105">For example, suppose your data contains a **Purchase Amount** column, an **Orders Quantity** column, and a **Premier Customer** column that is based on some formula using the other columns.</span></span> <span data-ttu-id="b7825-106">Se a coluna **cliente Premier** contiver muitas linhas em branco, você poderá usar as colunas **quantidade de compra** e quantidade de **pedidos** como as entradas para inferir os valores ausentes.</span><span class="sxs-lookup"><span data-stu-id="b7825-106">If the  **Premier Customer** column contains many blank rows, you could use the **Purchase Amount** and **Orders Quantity** columns as the inputs, to infer the missing values.</span></span> <span data-ttu-id="b7825-107">A ferramenta analisa os padrões existentes nos dados junto com os exemplos inseridos, e faz previsões sobre a categoria a ser atribuída a cada cliente.</span><span class="sxs-lookup"><span data-stu-id="b7825-107">The tool analyzes existing patterns in the data together with the examples you entered, and predicts which category to assign to each customer.</span></span>  
  
 <span data-ttu-id="b7825-108">Caso você não esteja satisfeito com os resultados, forneça mais exemplos para defini-los.</span><span class="sxs-lookup"><span data-stu-id="b7825-108">If you are not satisfied with the results, you can refine the results by providing more examples.</span></span>  
  
## <a name="using-the-fill-from-example-tool"></a><span data-ttu-id="b7825-109">Usando a ferramenta Preencher com Base no Exemplo</span><span class="sxs-lookup"><span data-stu-id="b7825-109">Using the Fill From Example Tool</span></span>  
  
1.  <span data-ttu-id="b7825-110">Na faixa de faixas **analisar** , clique em **preencher com base em exemplo**.</span><span class="sxs-lookup"><span data-stu-id="b7825-110">In the **Analyze** ribbon, click **Fill From Example**.</span></span>  
  
2.  <span data-ttu-id="b7825-111">A ferramenta escolherá automaticamente uma coluna a ser preenchida com base na análise dos dados e você poderá aceitar ou substituir sua sugestão.</span><span class="sxs-lookup"><span data-stu-id="b7825-111">The tool will automatically pick a column to fill based on analysis of the data, and you can either accept or override this suggestion.</span></span>  
  
3.  <span data-ttu-id="b7825-112">Crie uma coluna para os novos dados e digite exemplos dos dados que você deseja prever.</span><span class="sxs-lookup"><span data-stu-id="b7825-112">Create a column for the new data, and type in examples of the data that you want to predict.</span></span> <span data-ttu-id="b7825-113">Verifique se há pelo menos um exemplo de cada valor que você deseja prever.</span><span class="sxs-lookup"><span data-stu-id="b7825-113">Make sure that there is at least one example for every value that you want to predict.</span></span> <span data-ttu-id="b7825-114">Se você estiver preenchendo dados em uma coluna existente, selecione a coluna com os valores ausentes.</span><span class="sxs-lookup"><span data-stu-id="b7825-114">If you are filling in data in an existing column, select the column that has missing values.</span></span>  
  
4.  <span data-ttu-id="b7825-115">Opcionalmente, clique em **escolher colunas a serem usadas na análise**.</span><span class="sxs-lookup"><span data-stu-id="b7825-115">Optionally, click **Choose columns to be used in analysis**.</span></span> <span data-ttu-id="b7825-116">Na caixa de diálogo **seleção de colunas avançadas** , especifique as colunas que são mais prováveis de serem úteis ao preencher os dados ausentes.</span><span class="sxs-lookup"><span data-stu-id="b7825-116">In the **Advanced Columns Selection** dialog box, specify the columns that are most likely to be useful when filling in the missing data.</span></span>  
  
     <span data-ttu-id="b7825-117">Por exemplo, se, com base na sua experiência, você souber que há um efeito causal entre uma coluna e a coluna com valores ausentes, poderá desmarcar outras colunas para obter resultados melhores.</span><span class="sxs-lookup"><span data-stu-id="b7825-117">For example, if you know from experience that there is a causal effect between one column and the column that has missing values, you can deselect other columns to get better results.</span></span>  
  
     <span data-ttu-id="b7825-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7825-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b7825-119">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b7825-119">Click **Run**.</span></span>  
  
     <span data-ttu-id="b7825-120">Quando a análise é concluída, a ferramenta cria uma nova planilha de **padrões** que contém os resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="b7825-120">When analysis is complete, the tool creates a new **Patterns** worksheet that contains the results of analysis.</span></span> <span data-ttu-id="b7825-121">O relatório lista as regras ou os influenciadores principais encontrados e mostra a probabilidade para cada regra.</span><span class="sxs-lookup"><span data-stu-id="b7825-121">The report lists the rules, or key influencers, that were found, and shows the probability for each rule.</span></span>  
  
     <span data-ttu-id="b7825-122">A ferramenta também adicionará automaticamente uma coluna que contém os novos valores à tabela de dados original.</span><span class="sxs-lookup"><span data-stu-id="b7825-122">The tool also automatically adds a column that contains the new values to the original data table.</span></span> <span data-ttu-id="b7825-123">Você pode examinar os valores e compará-los com o original.</span><span class="sxs-lookup"><span data-stu-id="b7825-123">You can review the values and compare them against the original.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="b7825-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7825-124">Requirements</span></span>  
 <span data-ttu-id="b7825-125">Somente é possível trabalhar com dados em colunas.</span><span class="sxs-lookup"><span data-stu-id="b7825-125">You can only work with data in columns.</span></span> <span data-ttu-id="b7825-126">Se a série que você deseja preencher estiver armazenada em uma linha, use a função Colar, Transpor no Excel para alterar esses dados para um formato de coluna.</span><span class="sxs-lookup"><span data-stu-id="b7825-126">If the series that you want to fill is stored in a row, you can use the Paste, Transpose function in Excel to change the data to a columnar format.</span></span>  
  
## <a name="understanding-the-pattern-report"></a><span data-ttu-id="b7825-127">Entendendo o Relatório de Padrão</span><span class="sxs-lookup"><span data-stu-id="b7825-127">Understanding the Pattern Report</span></span>  
 <span data-ttu-id="b7825-128">Quando você executa a ferramenta **preencher com exemplo** , é criado um relatório que fornece mais informações sobre os padrões detectados.</span><span class="sxs-lookup"><span data-stu-id="b7825-128">When you run the **Fill From Example** tool, a report is created that provides more information about the patterns that were detected.</span></span> <span data-ttu-id="b7825-129">Esses padrões são usados para extrapolar novos valores de dados.</span><span class="sxs-lookup"><span data-stu-id="b7825-129">These patterns are used for extrapolating new data values.</span></span>  
  
 <span data-ttu-id="b7825-130">O Relatório de Padrão mostra os influenciadores principais para cada valor previsto.</span><span class="sxs-lookup"><span data-stu-id="b7825-130">The Pattern Report shows the key influencers for each value that was predicted.</span></span> <span data-ttu-id="b7825-131">Cada regra ou influenciador é descrito como uma combinação de uma coluna, o valor nessa coluna e o impacto relativo da regra na previsão.</span><span class="sxs-lookup"><span data-stu-id="b7825-131">Each influencer or rule is described as a combination of a column, the value in that column, and the relative impact of the rule on the prediction.</span></span>  
  
 <span data-ttu-id="b7825-132">Por exemplo, se você estivesse tentando preencher uma planilha que mostrasse a distância de entrega dos pedidos, talvez esperasse logicamente que o destino tivesse um grande impacto no valor dessa distância.</span><span class="sxs-lookup"><span data-stu-id="b7825-132">For example, if you were trying to fill in a worksheet that shows the shipping distance for orders, you might logically expect the destination to have a strong impact on the value for shipping distance.</span></span> <span data-ttu-id="b7825-133">Nesse caso, talvez a o relatório tivesse a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="b7825-133">In this case, the report might contain the following row:</span></span>  
  
|<span data-ttu-id="b7825-134">Column</span><span class="sxs-lookup"><span data-stu-id="b7825-134">Column</span></span>|<span data-ttu-id="b7825-135">Valor</span><span class="sxs-lookup"><span data-stu-id="b7825-135">Value</span></span>|<span data-ttu-id="b7825-136">Favorece</span><span class="sxs-lookup"><span data-stu-id="b7825-136">Favors</span></span>|<span data-ttu-id="b7825-137">Impacto relativo</span><span class="sxs-lookup"><span data-stu-id="b7825-137">Relative Impact</span></span>|  
|------------|-----------|------------|---------------------|  
|<span data-ttu-id="b7825-138">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="b7825-138">StateProvinceCode</span></span>|<span data-ttu-id="b7825-139">AB</span><span class="sxs-lookup"><span data-stu-id="b7825-139">AB</span></span>|<span data-ttu-id="b7825-140">>de 500 quilômetros</span><span class="sxs-lookup"><span data-stu-id="b7825-140">>500 kilometers</span></span>|<span data-ttu-id="b7825-141">80%</span><span class="sxs-lookup"><span data-stu-id="b7825-141">80%</span></span>|  
  
 <span data-ttu-id="b7825-142">Isso significa que o valor AB na coluna **StateProvinceCode** prevê rigidamente uma distância de remessa de >de 500 quilômetros.</span><span class="sxs-lookup"><span data-stu-id="b7825-142">This means that the value AB in the **StateProvinceCode** column strongly predicts a shipping distance of >500 kilometers.</span></span>  
  
 <span data-ttu-id="b7825-143">Em geral, as previsões se baseiam em padrões bem mais complexos do que este exemplo e o relatório pode conter muitas linhas de regras para cada previsão.</span><span class="sxs-lookup"><span data-stu-id="b7825-143">Typically, predictions are based on patterns that are far more complex than this example, and the report may contain many rows of rules for each prediction.</span></span> <span data-ttu-id="b7825-144">Os efeitos de todas as regras são combinados para derivar o valor previsto.</span><span class="sxs-lookup"><span data-stu-id="b7825-144">The effect of all the rules are combined to derive the predicted value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7825-145">O **impacto relativo** é mostrado como uma barra sombreada.</span><span class="sxs-lookup"><span data-stu-id="b7825-145">**Relative Impact** is shown as a shaded bar.</span></span> <span data-ttu-id="b7825-146">Quanto maior a barra, maior a probabilidade de essa regra ser uma previsão do valor preenchido.</span><span class="sxs-lookup"><span data-stu-id="b7825-146">The longer the bar, the greater the probability that this rule is predictive of the filled-in value.</span></span>  
  
 <span data-ttu-id="b7825-147">A ferramenta também adiciona uma nova coluna à tabela de dados original, chamada \<column name> estendida.</span><span class="sxs-lookup"><span data-stu-id="b7825-147">The tool also adds a new column to the original data table, named \<column name> Extended.</span></span>  
  
 <span data-ttu-id="b7825-148">Se a coluna de dados original contiver um valor, ele será copiado na nova coluna.</span><span class="sxs-lookup"><span data-stu-id="b7825-148">If the original data column contained a value, that value is copied into the new column.</span></span> <span data-ttu-id="b7825-149">No entanto, se a coluna contiver uma célula em branco, a nova coluna terá o valor previsto pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="b7825-149">However, if the original column contained a blank cell, the new column contains the value that was predicted by the wizard.</span></span>  
  
## <a name="related-tools-and-information"></a><span data-ttu-id="b7825-150">Ferramentas e informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="b7825-150">Related Tools and Information</span></span>  
 <span data-ttu-id="b7825-151">Você também pode usar o assistente para [explorar dados](explore-data-sql-server-data-mining-add-ins.md) , disponível no cliente de mineração de dados para Excel, para examinar a distribuição de valores em uma coluna do Excel.</span><span class="sxs-lookup"><span data-stu-id="b7825-151">You can also use the [Explore Data](explore-data-sql-server-data-mining-add-ins.md) wizard, available in the Data Mining Client for Excel, to examine the distribution of values in an Excel column.</span></span> <span data-ttu-id="b7825-152">Para obter mais informações, consulte [explorando e limpando dados](exploring-and-cleaning-data.md).</span><span class="sxs-lookup"><span data-stu-id="b7825-152">For more information, see [Exploring and Cleaning Data](exploring-and-cleaning-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7825-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b7825-153">See Also</span></span>  
 [<span data-ttu-id="b7825-154">Ferramentas de Análise de Tabela para Excel</span><span class="sxs-lookup"><span data-stu-id="b7825-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
