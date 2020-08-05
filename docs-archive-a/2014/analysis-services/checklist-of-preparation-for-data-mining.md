---
title: Lista de verificação de preparação para mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e056c95-ba06-413e-8dc1-4d411a447c3b
author: minewiskan
ms.author: owend
ms.openlocfilehash: e37b1adb6aebe5d5f8fd23f5289f52425f752a6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571709"
---
# <a name="checklist-of-preparation-for-data-mining"></a><span data-ttu-id="46da5-102">Lista de verificação de preparação para mineração de dados</span><span class="sxs-lookup"><span data-stu-id="46da5-102">Checklist of Preparation for Data Mining</span></span>
  <span data-ttu-id="46da5-103">Embora os suplementos de mineração de dados tornem as experiências com modelos algo fácil e divertido, quando você precisar obter resultados repetíveis e acionáveis, deverá aguardar um tempo suficiente para formular requisitos empresariais básicos e para obter e preparar dados.</span><span class="sxs-lookup"><span data-stu-id="46da5-103">Although the Data Mining Add-ins make it fairly easy and fun to create and experiment with models, when you need to get repeatable, actionable results, you must allow adequate time for formulating basic business requirements, and for obtaining and preparing data.</span></span> <span data-ttu-id="46da5-104">Esta seção fornece uma lista de verificação para ajudá-lo a planejar sua investigação e descreve os problemas comuns.</span><span class="sxs-lookup"><span data-stu-id="46da5-104">This section provides a checklist to help you plan your investigation, and describes common problems.</span></span>  
  
## <a name="checklist-of-data-preparation"></a><span data-ttu-id="46da5-105">Lista de verificação de preparação de dados</span><span class="sxs-lookup"><span data-stu-id="46da5-105">Checklist of Data Preparation</span></span>  
 <span data-ttu-id="46da5-106">**Eu identifiquei uma saída claramente definida.**</span><span class="sxs-lookup"><span data-stu-id="46da5-106">**I have identified a clearly defined output.**</span></span>  
 <span data-ttu-id="46da5-107">Ter um plano para como você usará os resultados.</span><span class="sxs-lookup"><span data-stu-id="46da5-107">Have a plan for how you will use the results.</span></span> <span data-ttu-id="46da5-108">Tipos de modelos diferentes têm saídas diferentes.</span><span class="sxs-lookup"><span data-stu-id="46da5-108">Different types of models have different outputs.</span></span> <span data-ttu-id="46da5-109">Um modelo de série temporal gera valores para uma série no futuro, que são fáceis de entender e utilizar.</span><span class="sxs-lookup"><span data-stu-id="46da5-109">A time series model generates values for a series in the future, which are easily understood and acted on.</span></span> <span data-ttu-id="46da5-110">Outros modelos geram conjuntos complexos que devem ser analisados por especialistas no assunto para produzir um valor maior.</span><span class="sxs-lookup"><span data-stu-id="46da5-110">Other models generate complex sets that must be analyzed by subject matter experts to yield the most value.</span></span>  
  
-   <span data-ttu-id="46da5-111">Qual saída você deseja?</span><span class="sxs-lookup"><span data-stu-id="46da5-111">What output do you want?</span></span>  
  
-   <span data-ttu-id="46da5-112">Você pode definir a saída como uma única coluna ou valor ou outro resultado acionável?</span><span class="sxs-lookup"><span data-stu-id="46da5-112">Can you define the output as a single column or value, or other actionable result?</span></span>  
  
-   <span data-ttu-id="46da5-113">Quais são os critérios para saber que o modelo foi útil?</span><span class="sxs-lookup"><span data-stu-id="46da5-113">What are your criteria for knowing that the model was useful?</span></span>  
  
-   <span data-ttu-id="46da5-114">Como você usará e interpretará esses resultados?</span><span class="sxs-lookup"><span data-stu-id="46da5-114">How will you use and interpret those results?</span></span>  
  
-   <span data-ttu-id="46da5-115">Você pode mapear novos dados de entrada para os resultados esperados?</span><span class="sxs-lookup"><span data-stu-id="46da5-115">Can you map new input data to the expected results?</span></span>  
  
 <span data-ttu-id="46da5-116">**Eu sei o significado, os tipos de dados e a distribuição dos dados de entrada.**</span><span class="sxs-lookup"><span data-stu-id="46da5-116">**I know the meaning, data types, and distribution of the input data.**</span></span>  
 <span data-ttu-id="46da5-117">Dedique algum tempo para explorar e entender os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="46da5-117">Take some time to explore and understand your source data.</span></span> <span data-ttu-id="46da5-118">É importante que as pessoas que examinam o modelo entendam o tipo de dados de entrada que foi usado e saibam como interpretar os tipos de dados e a variabilidade, bem como o equilíbrio e a qualidade.</span><span class="sxs-lookup"><span data-stu-id="46da5-118">It is important that people who review the model understand what kind of input data was used and know how to interpret the data types and the variability, as well as the balance and the quality.</span></span>  
  
-   <span data-ttu-id="46da5-119">Qual é a quantidade de dados que você tem?</span><span class="sxs-lookup"><span data-stu-id="46da5-119">How much data do you have?</span></span> <span data-ttu-id="46da5-120">Há dados suficientes para modelar?</span><span class="sxs-lookup"><span data-stu-id="46da5-120">Is there sufficient data for modeling?</span></span>  
  
     <span data-ttu-id="46da5-121">Ele não precisa ser um grande volume-menor e equilibrado pode ser melhor.</span><span class="sxs-lookup"><span data-stu-id="46da5-121">It need not be a huge amount - smaller and balanced can be better.</span></span>  
  
-   <span data-ttu-id="46da5-122">Os dados são de várias origens ou uma única origem?</span><span class="sxs-lookup"><span data-stu-id="46da5-122">Is the data from multiple sources, or a single source?</span></span>  
  
-   <span data-ttu-id="46da5-123">Os dados já foram processados e limpos?</span><span class="sxs-lookup"><span data-stu-id="46da5-123">Is the data already processed and clean?</span></span> <span data-ttu-id="46da5-124">Existem mais dados de entrada disponíveis?</span><span class="sxs-lookup"><span data-stu-id="46da5-124">Is more input data available?</span></span>  
  
-   <span data-ttu-id="46da5-125">Você sabe como ele foi manipulado antes de você ter recebido-como os dados podem ter sido truncados, resumidos ou convertidos?</span><span class="sxs-lookup"><span data-stu-id="46da5-125">Do you know how it was manipulated before you received it - how data might have been truncated, summarized, or converted?</span></span>  
  
-   <span data-ttu-id="46da5-126">Os dados de entrada têm alguns resultados de exemplo que podem ser usados para treinamento?</span><span class="sxs-lookup"><span data-stu-id="46da5-126">Does the input data have some example results that can be used for training?</span></span>  
  
 <span data-ttu-id="46da5-127">**Eu compreendo o nível de integridade de dados que temos e o nível precisamos.**</span><span class="sxs-lookup"><span data-stu-id="46da5-127">**I understand the level of data integrity we have and the level we need.**</span></span>  
 <span data-ttu-id="46da5-128">Dados incorretos podem afetar a qualidade do modelo ou impedir que o modelo seja até mesmo criado.</span><span class="sxs-lookup"><span data-stu-id="46da5-128">Bad data can affect the quality of the model, or prevent the model from being built at all.</span></span> <span data-ttu-id="46da5-129">Você deve ter um bom entendimento da distribuição e do significado dos dados, e como eles chegaram a esse estado.</span><span class="sxs-lookup"><span data-stu-id="46da5-129">You should have a good understanding of both the distribution and meaning of the data, and how it came to this state.</span></span> <span data-ttu-id="46da5-130">Você precisará entender se é possível ou apropriado simplificar os dados através de rótulos, truncando tipos de dados numéricos ou resumindo.</span><span class="sxs-lookup"><span data-stu-id="46da5-130">You'll need to understand if it is possible or appropriate to simplify the data by labeling, truncating numeric data types, or by summarizing.</span></span>  
  
-   <span data-ttu-id="46da5-131">Rótulos de dados: estão claros e corretos?</span><span class="sxs-lookup"><span data-stu-id="46da5-131">Data labels: are they clear and correct?</span></span>  
  
-   <span data-ttu-id="46da5-132">Tipos de dados: são apropriados e foram modificados?</span><span class="sxs-lookup"><span data-stu-id="46da5-132">Data types: are they appropriate, and have they been changed?</span></span>  
  
-   <span data-ttu-id="46da5-133">Você classificou, limpou ou descartou os dados errados?</span><span class="sxs-lookup"><span data-stu-id="46da5-133">Have you sorted, cleaned up, or discarded wrong data?</span></span>  
  
     <span data-ttu-id="46da5-134">Você verificou se não há nenhuma duplicata?</span><span class="sxs-lookup"><span data-stu-id="46da5-134">Have you verified there are no duplicates?</span></span>  
  
-   <span data-ttu-id="46da5-135">Como você administrará valores ausentes?</span><span class="sxs-lookup"><span data-stu-id="46da5-135">How will you handle missing values?</span></span> <span data-ttu-id="46da5-136">Os valores ausentes têm um significado?</span><span class="sxs-lookup"><span data-stu-id="46da5-136">Do missing values have a meaning?</span></span>  
  
-   <span data-ttu-id="46da5-137">Você verificou as fontes para ver se algum erro pode ter sido introduzido no processo de importação?</span><span class="sxs-lookup"><span data-stu-id="46da5-137">Have you verified the sources to see if any errors might have been introduced in the import process?</span></span>  
  
     <span data-ttu-id="46da5-138">Onde a entrada está armazenada?</span><span class="sxs-lookup"><span data-stu-id="46da5-138">Where is the input stored?</span></span> <span data-ttu-id="46da5-139">Quanto tempo ele permanece disponível?</span><span class="sxs-lookup"><span data-stu-id="46da5-139">How long does it stay available?</span></span>  
  
     <span data-ttu-id="46da5-140">Há um dicionário de dados?</span><span class="sxs-lookup"><span data-stu-id="46da5-140">Is there a data dictionary?</span></span> <span data-ttu-id="46da5-141">Você pode criar um?</span><span class="sxs-lookup"><span data-stu-id="46da5-141">Can you create one?</span></span>  
  
-   <span data-ttu-id="46da5-142">Se você combinou conjuntos de dados, verificou se há várias colunas que representam os mesmos dados?</span><span class="sxs-lookup"><span data-stu-id="46da5-142">If you combined data sets, did you check for multiple columns representing the same data?</span></span>  
  
 <span data-ttu-id="46da5-143">**Eu sei onde os dados de origem são armazenados, de onde eles vieram e como eles são processados. O processo pode ser facilmente repetido, se necessário.**</span><span class="sxs-lookup"><span data-stu-id="46da5-143">**I know where source data is stored, where it came from, and how it is processed. The process can be easily repeated if needed.**</span></span>  
 <span data-ttu-id="46da5-144">Conjuntos de dados únicos são bons para experimentos, mas se você quiser mover o modelo para produção, convém pensar com antecedência como o processo de limpeza pode ser aplicado aos dados operacionais.</span><span class="sxs-lookup"><span data-stu-id="46da5-144">One-off data sets are fine for experiments, but if you ever want to move the model into production, you'll want to think in advance about how the cleaning process can be applied to operational data.</span></span> <span data-ttu-id="46da5-145">Além disso, se você tiver dados operacionais, precisará saber como ele pode ter sido alterado antes de tê-lo-você precisará saber como ele foi arredondado, ou resumido, certamente.</span><span class="sxs-lookup"><span data-stu-id="46da5-145">Also, if you have operational data, you need to know how it might have been altered before you got it-you'll need to know how it was rounded, or summarized, certainly.</span></span>  
  
-   <span data-ttu-id="46da5-146">Você deseja ser capaz de repetir a experiência?</span><span class="sxs-lookup"><span data-stu-id="46da5-146">Do you want to be able to repeat the experiment?</span></span>  
  
-   <span data-ttu-id="46da5-147">Quais ferramentas você usará para preparar dados em um formato que dá suporte à análise de dados?</span><span class="sxs-lookup"><span data-stu-id="46da5-147">What tools will you use to prepare data in a format that supports data analysis?</span></span> <span data-ttu-id="46da5-148">Isso pode ser automatizado ou precisa que alguém examine e limpe no Excel?</span><span class="sxs-lookup"><span data-stu-id="46da5-148">Can it be automated or do you need someone to review and clean up in Excel?</span></span>  
  
-   <span data-ttu-id="46da5-149">Se você estiver fornecendo dados de outro sistema, poderá capturar e rastrear os filtros que foram aplicados?</span><span class="sxs-lookup"><span data-stu-id="46da5-149">If you are sourcing data from another system, will you be able to capture and track filters that were applied?</span></span>  
  
-   <span data-ttu-id="46da5-150">Sua estrutura de processamento de dados também pode aplicar algoritmos de aprendizagem de máquina, executar testes e visualizar os resultados?</span><span class="sxs-lookup"><span data-stu-id="46da5-150">Can your data processing framework also apply machine learning algorithms, perform tests, and visualize results?</span></span>  
  
 <span data-ttu-id="46da5-151">**Nós concordamos com a granularidade desejada das previsões e nossos dados foram modificados para produzir essas unidades.**</span><span class="sxs-lookup"><span data-stu-id="46da5-151">**We have agreed on the desired granularity of predictions and our data has been modified to output those units.**</span></span>  
 <span data-ttu-id="46da5-152">Decida sobre a granularidade dos resultados desejados antes de preparar dados. Por exemplo, você deseja as previsões de vendas por dia ou por trimestre?</span><span class="sxs-lookup"><span data-stu-id="46da5-152">Decide on the granularity of the results you want before preparing data, For example, do you want sales predictions by the day, or for each quarter?</span></span> <span data-ttu-id="46da5-153">Você deverá considerar estruturas de dados diferentes para os mesmos dados, para tratar níveis diferentes de resumo.</span><span class="sxs-lookup"><span data-stu-id="46da5-153">You might consider setting up different data structures for the same data, to handle different levels of summary.</span></span>  
  
-   <span data-ttu-id="46da5-154">Qual é a unidade de medida ou unidade de tempo atual?</span><span class="sxs-lookup"><span data-stu-id="46da5-154">What is the current unit of measure or unit of time?</span></span>  
  
     <span data-ttu-id="46da5-155">Qual unidade você deseja usar nos resultados?</span><span class="sxs-lookup"><span data-stu-id="46da5-155">What unit do you want to use in the results?</span></span>  
  
-   <span data-ttu-id="46da5-156">É possível definir uma unidade básica (por exemplo, dia/hora/min/chamada de instrução) para todos os dados de entrada?</span><span class="sxs-lookup"><span data-stu-id="46da5-156">Is it possible to define a basic unit (e.g. day/ hour / min / instruction call) for all input data?</span></span>  
  
     <span data-ttu-id="46da5-157">Você deseja fazer rollup para unidades maiores?</span><span class="sxs-lookup"><span data-stu-id="46da5-157">Do you want to rollup to higher units?</span></span>  
  
-   <span data-ttu-id="46da5-158">As categorias são rotuladas consistentemente?</span><span class="sxs-lookup"><span data-stu-id="46da5-158">Are categories labeled consistently?</span></span> <span data-ttu-id="46da5-159">É fácil adicionar ou remover categorias?</span><span class="sxs-lookup"><span data-stu-id="46da5-159">Is it easy to add or remove categories?</span></span>  
  
 <span data-ttu-id="46da5-160">**Nosso design de avaliação é repetível e reprodutível.**</span><span class="sxs-lookup"><span data-stu-id="46da5-160">**Our experimental design is repeatable and reproducible.**</span></span>  
 <span data-ttu-id="46da5-161">Considere estratégias para analisar e validar seus resultados e planeje capturar um instantâneo dos dados, para garantir você possa rastrear os efeitos para os dados.</span><span class="sxs-lookup"><span data-stu-id="46da5-161">Consider strategies for analyzing and validating your results and plan to capture a data snapshot, to make sure you can trace back effects to data.</span></span> <span data-ttu-id="46da5-162">Se uma semente aleatória é usada, os resultados poderão variar um pouco.</span><span class="sxs-lookup"><span data-stu-id="46da5-162">If a random seed is used, the results can differ subtly.</span></span> <span data-ttu-id="46da5-163">Isso pode dificultar a comparação e a validação de modelos.</span><span class="sxs-lookup"><span data-stu-id="46da5-163">This can make it difficult to compare and validate models.</span></span>  
  
-   <span data-ttu-id="46da5-164">Se você fizer muitas alterações personalizadas nos dados, o que acontecerá na próxima vez que quiser criar o modelo?</span><span class="sxs-lookup"><span data-stu-id="46da5-164">If you make a lot of custom changes to the data, what happens the next time you want to build the model?</span></span>  
  
-   <span data-ttu-id="46da5-165">Já foi definido um procedimento manual ou um processo aprovado que você deverá usar para processar a entrada e obter os resultados desejados?</span><span class="sxs-lookup"><span data-stu-id="46da5-165">Has a manual procedure or approved process already been defined that you should use to process input and get the desired outputs?</span></span>  
  
-   <span data-ttu-id="46da5-166">Você decidiu usar uma semente para o modelo?</span><span class="sxs-lookup"><span data-stu-id="46da5-166">Have you decided to use a seed for the model?</span></span>  
  
 <span data-ttu-id="46da5-167">**Temos o conhecimento do domínio para validar os resultados ou temos acesso aos especialistas de assunto que podem aconselhar.**</span><span class="sxs-lookup"><span data-stu-id="46da5-167">**We have the domain knowledge to validate the results, or have access to subject matter experts who can advise.**</span></span>  
 <span data-ttu-id="46da5-168">Reserve um tempo para validar as variáveis, o modelo e os resultados.</span><span class="sxs-lookup"><span data-stu-id="46da5-168">Take time to validate the variables, the model, and the results.</span></span> <span data-ttu-id="46da5-169">Obtenha a ajuda de especialistas para avaliar as interações e os resultados.</span><span class="sxs-lookup"><span data-stu-id="46da5-169">Get the help of experts to assess interactions and results.</span></span> <span data-ttu-id="46da5-170">No entanto, não deixe as suposições anularem evidências.</span><span class="sxs-lookup"><span data-stu-id="46da5-170">However, don't let assumptions overrule evidence.</span></span> <span data-ttu-id="46da5-171">Esteja aberto a novas e inesperadas descobertas.</span><span class="sxs-lookup"><span data-stu-id="46da5-171">Be open to new and unexpected findings.</span></span>  
  
-   <span data-ttu-id="46da5-172">O conhecimento de domínio está disponível para ajudar a filtrar dados e reduzir o ruído de entrada?</span><span class="sxs-lookup"><span data-stu-id="46da5-172">Is domain knowledge available to help in filtering data and reducing input noise?</span></span>  
  
-   <span data-ttu-id="46da5-173">Os especialistas de domínio podem ajudar a entender e interpretar os resultados e sugerir melhorias?</span><span class="sxs-lookup"><span data-stu-id="46da5-173">Can domain experts help understand interpret the results and suggest improvements?</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46da5-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46da5-174">See Also</span></span>  
 [<span data-ttu-id="46da5-175">Escolhendo os dados para a mineração de dados</span><span class="sxs-lookup"><span data-stu-id="46da5-175">Choosing Data for Data Mining</span></span>](choosing-data-for-data-mining.md)  
  
  
