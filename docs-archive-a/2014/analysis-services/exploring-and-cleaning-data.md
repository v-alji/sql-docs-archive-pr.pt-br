---
title: Explorando e limpando dados | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7c888c95-8986-461e-9f11-2395044b9d97
author: minewiskan
ms.author: owend
ms.openlocfilehash: 154c711f735bcbb472e49654139fd16a036a0dd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568867"
---
# <a name="exploring-and-cleaning-data"></a><span data-ttu-id="66cb4-102">Explorando e limpando dados</span><span class="sxs-lookup"><span data-stu-id="66cb4-102">Exploring and Cleaning Data</span></span>
  <span data-ttu-id="66cb4-103">A preparação dos dados é muito mais do que limpeza de dados.</span><span class="sxs-lookup"><span data-stu-id="66cb4-103">Data preparation is much more than data cleansing.</span></span> <span data-ttu-id="66cb4-104">Lembre-se de que o modo como os dados são preparados também afeta como os resultados são interpretados no final.</span><span class="sxs-lookup"><span data-stu-id="66cb4-104">Remember that how data is prepared also affects how results are interpreted in the end.</span></span> <span data-ttu-id="66cb4-105">A preparação dos dados envolve as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="66cb4-105">Data preparation involves these tasks:</span></span>  
  
-   <span data-ttu-id="66cb4-106">Exploração e verificação da distribuição dos dados.</span><span class="sxs-lookup"><span data-stu-id="66cb4-106">Exploring and checking the distribution of data.</span></span>  
  
-   <span data-ttu-id="66cb4-107">Limpeza de registros incorretos e escolha das colunas para a mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="66cb4-107">Cleaning bad records, and choosing columns for data mining.</span></span>  
  
-   <span data-ttu-id="66cb4-108">Tratamento incorreto de nulos.</span><span class="sxs-lookup"><span data-stu-id="66cb4-108">Handling nulls appropriately.</span></span>  
  
-   <span data-ttu-id="66cb4-109">Compartimentalização ou agregação de valores por diferentes partes de tempo.</span><span class="sxs-lookup"><span data-stu-id="66cb4-109">Binning values, or aggregating values by different chunks of time.</span></span>  
  
-   <span data-ttu-id="66cb4-110">Adição de rótulos para aumentar a usabilidade dos resultados.</span><span class="sxs-lookup"><span data-stu-id="66cb4-110">Adding labels to improve the usability of the results.</span></span>  
  
-   <span data-ttu-id="66cb4-111">Conversão dos tipos de dados ou categorização de valores se necessário para análise.</span><span class="sxs-lookup"><span data-stu-id="66cb4-111">Converting data types or categorizing values where necessary for analysis.</span></span>  
  
 <span data-ttu-id="66cb4-112">Se você for novo na modelagem de dados, é recomendável ler o tópico relacionado, [lista de verificação de preparação para mineração de dados](checklist-of-preparation-for-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="66cb4-112">If you are new to data modeling, we recommend that you read the related topic, [Checklist of Preparation for Data Mining](checklist-of-preparation-for-data-mining.md).</span></span>  
  
## <a name="data-preparation-tools"></a><span data-ttu-id="66cb4-113">Ferramentas de preparação de dados</span><span class="sxs-lookup"><span data-stu-id="66cb4-113">Data Preparation Tools</span></span>  
 <span data-ttu-id="66cb4-114">Os Suplementos de Mineração de Dados para Office incluem as seguintes ferramentas para limpeza e preparação dos dados:</span><span class="sxs-lookup"><span data-stu-id="66cb4-114">The Data Mining Add-ins for Office includes the following tools for data cleansing and preparation:</span></span>  
  
### <a name="explore-data"></a><span data-ttu-id="66cb4-115">Explorar Dados</span><span class="sxs-lookup"><span data-stu-id="66cb4-115">Explore Data</span></span>  
 <span data-ttu-id="66cb4-116">Use o assistente para **explorar dados** para estas tarefas de preparação de dados:</span><span class="sxs-lookup"><span data-stu-id="66cb4-116">Use the **Explore Data** wizard for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="66cb4-117">Visualize seus dados e identifique erros que devem ser corrigidos antes da análise.</span><span class="sxs-lookup"><span data-stu-id="66cb4-117">Preview your data and identify errors that must be fixed prior to analysis.</span></span>  
  
-   <span data-ttu-id="66cb4-118">Colete informações estatísticas úteis para entender o equilíbrio dos dados e as tarefas de limpeza necessárias.</span><span class="sxs-lookup"><span data-stu-id="66cb4-118">Gather statistical information that is useful for understanding the balance of data and the required clean-up tasks.</span></span>  
  
-   <span data-ttu-id="66cb4-119">Identifique colunas que sejam úteis para análise e planeje a fase de modelagem de dados.</span><span class="sxs-lookup"><span data-stu-id="66cb4-119">Identify columns that are useful for analysis, and plan the data modeling phase.</span></span>  
  
 <span data-ttu-id="66cb4-120">[Explore os dados &#40;SQL Server suplementos de mineração de dados&#41;](explore-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="66cb4-120">[Explore Data &#40;SQL Server Data Mining Add-ins&#41;](explore-data-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="detect-and-handle-outliers"></a><span data-ttu-id="66cb4-121">Detectar exceções e lidar com elas</span><span class="sxs-lookup"><span data-stu-id="66cb4-121">Detect and Handle Outliers</span></span>  
 <span data-ttu-id="66cb4-122">O assistente de **exceções** grafa a distribuição de valores em seus dados e ajuda você a remover valores extremos.</span><span class="sxs-lookup"><span data-stu-id="66cb4-122">The **Outliers** wizard graphs the distribution of values in your data and helps you remove extreme values.</span></span> <span data-ttu-id="66cb4-123">Use a ferramenta de **exceções** para as seguintes tarefas de preparação de dados:</span><span class="sxs-lookup"><span data-stu-id="66cb4-123">Use the **Outliers** tool for the following data preparation tasks:</span></span>  
  
-   <span data-ttu-id="66cb4-124">Determine se valores individuais são confiáveis, com base em padrões encontrados nos dados.</span><span class="sxs-lookup"><span data-stu-id="66cb4-124">Determine whether individual values are reliable, based on patterns found in the data.</span></span>  
  
-   <span data-ttu-id="66cb4-125">Examine os valores incomuns e tome uma ação ao excluí-los ou substituí-los.</span><span class="sxs-lookup"><span data-stu-id="66cb4-125">Review unusual values and take action by deleting or replacing them.</span></span>  
  
-   <span data-ttu-id="66cb4-126">Faça um escopo de um modelo para um intervalo de valores específicos.</span><span class="sxs-lookup"><span data-stu-id="66cb4-126">Scope a model to a specific range of values.</span></span> <span data-ttu-id="66cb4-127">Por exemplo, se você souber que tem exceções em um armazenamento em particular, poderá eliminar esse valor e obter um modelo que preveja melhor outros armazenamentos.</span><span class="sxs-lookup"><span data-stu-id="66cb4-127">For example, if you know that you have outliers at a particular store, you can eliminate that value and get a model that better predicts other stores.</span></span>  
  
 <span data-ttu-id="66cb4-128">As [exceções &#40;SQL Server suplementos de mineração de dados&#41;](outliers-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="66cb4-128">[Outliers &#40;SQL Server Data Mining Add-ins&#41;](outliers-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="relabel-and-bin-data"></a><span data-ttu-id="66cb4-129">Rotular Novamente e Guardar Dados</span><span class="sxs-lookup"><span data-stu-id="66cb4-129">Relabel and Bin Data</span></span>  
 <span data-ttu-id="66cb4-130">O assistente de **rerotulação** agrupa dados por valores para que você possa alterar os rótulos nos dados.</span><span class="sxs-lookup"><span data-stu-id="66cb4-130">The **Relabel** wizard groups data by values so that you can change the labels on the data.</span></span> <span data-ttu-id="66cb4-131">Use a ferramenta Rotular Novamente para estas tarefas de preparação de dados:</span><span class="sxs-lookup"><span data-stu-id="66cb4-131">Use the Relabel tool for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="66cb4-132">Altere códigos numéricos usados nos resultados da pesquisa para uma descrição textual do significado do código numérico.</span><span class="sxs-lookup"><span data-stu-id="66cb4-132">Change numeric codes used in survey results to a text description of what the numeric code means.</span></span>  
  
     <span data-ttu-id="66cb4-133">Por exemplo, você pode substituir entradas de dados como Sexo = 1 por Sexo = Feminino.</span><span class="sxs-lookup"><span data-stu-id="66cb4-133">For example, you might replace data entries such as Gender = 1 with Gender = Female.</span></span>  
  
-   <span data-ttu-id="66cb4-134">Guarde os dados, criando grupos que representam intervalos de número.</span><span class="sxs-lookup"><span data-stu-id="66cb4-134">Bin data, by creating groups to represents number ranges.</span></span>  
  
     <span data-ttu-id="66cb4-135">Por exemplo, talvez você queira substituir uma coluna de renda de números por rótulos como **receita-moderada** e **renda alta**.</span><span class="sxs-lookup"><span data-stu-id="66cb4-135">For example, you might want to replace an Income column of numbers with labels such as **Income - Moderate** and **Income - High**.</span></span>  
  
-   <span data-ttu-id="66cb4-136">Recolher valores discretos em categorias.</span><span class="sxs-lookup"><span data-stu-id="66cb4-136">Collapse discrete values into categories.</span></span>  
  
     <span data-ttu-id="66cb4-137">Por exemplo, se você tiver muitos produtos individuais para detectar um padrão entre compras, poderá tentar atribuir produtos em categorias mais amplas.</span><span class="sxs-lookup"><span data-stu-id="66cb4-137">For example, if you have too many individual products to detect a pattern among purchases, you could try assigning products into broader categories.</span></span>  
  
 [<span data-ttu-id="66cb4-138">Rerotular &#40;SQL Server os suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="66cb4-138">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
### <a name="cleanse-data"></a><span data-ttu-id="66cb4-139">Limpar dados</span><span class="sxs-lookup"><span data-stu-id="66cb4-139">Cleanse Data</span></span>  
 <span data-ttu-id="66cb4-140">A limpeza de dados inclui uma ampla gama de atividades, a maioria das quais têm suporte pelos suplementos</span><span class="sxs-lookup"><span data-stu-id="66cb4-140">Data cleansing encompasses a wide range of activities, most of which are supported by the add-ins</span></span>  
  
-   <span data-ttu-id="66cb4-141">Identificar nulos e determinar se devem ser alterados para um valor real ou se devem ser tratados como valores `Missing`.</span><span class="sxs-lookup"><span data-stu-id="66cb4-141">Identify nulls and determine whether they should be changed to a real value or handled as `Missing` values.</span></span>  
  
-   <span data-ttu-id="66cb4-142">Detecte valores ausentes e remova-os ou impute um valor adequado, como um valor médio, nulo ou outro.</span><span class="sxs-lookup"><span data-stu-id="66cb4-142">Detect missing values, and then remove them, or impute an appropriate value, such as a mean, null, or other value.</span></span>  
  
 [<span data-ttu-id="66cb4-143">Explorar dados &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="66cb4-143">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="66cb4-144">Rerotular &#40;SQL Server os suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="66cb4-144">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="66cb4-145">Preencher com Base no Exemplo</span><span class="sxs-lookup"><span data-stu-id="66cb4-145">Fill From Example</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
### <a name="sample-data"></a><span data-ttu-id="66cb4-146">Dados de Amostra</span><span class="sxs-lookup"><span data-stu-id="66cb4-146">Sample Data</span></span>  
 <span data-ttu-id="66cb4-147">O assistente de Dados de Amostra fornece dois métodos para criar conjuntos de dados balanceados para modelos de treinamento e teste.</span><span class="sxs-lookup"><span data-stu-id="66cb4-147">The Sample Data wizard provides two methods for creating balanced data sets for training and testing models.</span></span>  
  
-   <span data-ttu-id="66cb4-148">**Amostragem aleatória.**</span><span class="sxs-lookup"><span data-stu-id="66cb4-148">**Random sampling.**</span></span> <span data-ttu-id="66cb4-149">Use esta opção para extrair um conjunto representativo de dados de um conjunto de dados maior, para usar em treinamento ou teste.</span><span class="sxs-lookup"><span data-stu-id="66cb4-149">Use this option to extract a representative set of data from a larger data set, for use in either training or testing.</span></span> <span data-ttu-id="66cb4-150">Os suplementos de mineração de dados usam a *amostragem de sobreratificação* para garantir que um conjunto equilibrado de valores seja obtido para cada variável amostrada.</span><span class="sxs-lookup"><span data-stu-id="66cb4-150">The Data Mining Add-ins use *stratified sampling* to ensure that a balanced set of values is obtained for each variable sampled.</span></span>  
  
-   <span data-ttu-id="66cb4-151">**Sobreamostragem.**</span><span class="sxs-lookup"><span data-stu-id="66cb4-151">**Oversampling.**</span></span> <span data-ttu-id="66cb4-152">Use essa opção quando você tiver menos dados do que desejar para um resultado de destino, e precisar pesar esses dados de maneira mais pesada.</span><span class="sxs-lookup"><span data-stu-id="66cb4-152">Use this option when you have less data than you would like for a target outcome, and need to weight that data more heavily.</span></span> <span data-ttu-id="66cb4-153">Por exemplo, a fraude pode ser relativamente rara, mas você pode sobreamostrar os casos que envolvem fraude para obter dados suficientes para modelagem.</span><span class="sxs-lookup"><span data-stu-id="66cb4-153">For example, fraud might be relatively rare, but you can oversample cases involving fraud to get adequate data for modeling.</span></span>  
  
 <span data-ttu-id="66cb4-154">[Dados de exemplo &#40;SQL Server suplementos de mineração de dados&#41;](sample-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="66cb4-154">[Sample Data &#40;SQL Server Data Mining Add-ins&#41;](sample-data-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66cb4-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66cb4-155">See Also</span></span>  
 <span data-ttu-id="66cb4-156">[Criando um modelo de mineração de dados](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="66cb4-156">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="66cb4-157">[Validando modelos e usando modelos para previsão &#40;suplementos de mineração de dados para Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="66cb4-157">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="66cb4-158">Implantando e dimensionando modelos de mineração &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="66cb4-158">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
