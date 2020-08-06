---
title: Exceções (SQL Server suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exceptions [data mining]
- data preparation
- outliers [data mining]
- data cleaning
ms.assetid: e6fa7c62-4005-4792-9211-3b699377a517
author: minewiskan
ms.author: owend
ms.openlocfilehash: 92dddf3338d15e700576a13476ee364696bfd274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686413"
---
# <a name="outliers-sql-server-data-mining-add-ins"></a><span data-ttu-id="24ae0-102">Exceções (Suplementos de Mineração de Dados do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="24ae0-102">Outliers (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="24ae0-103">![Assistente de Exceções na faixa de opções Mineração de Dados](media/dmc-outliers.gif "Assistente de Exceções na faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="24ae0-103">![Outliers wizard in Data Mining ribbon](media/dmc-outliers.gif "Outliers wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="24ae0-104">Uma *exceção* significa um valor de dados que é problemático por qualquer um dos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="24ae0-104">An *outlier* means a data value that is problematic for any one of the following reasons:</span></span>  
  
-   <span data-ttu-id="24ae0-105">O valor está fora do intervalo esperado.</span><span class="sxs-lookup"><span data-stu-id="24ae0-105">Value is outside the expected range.</span></span>  
  
-   <span data-ttu-id="24ae0-106">Os dados talvez tenham sido inseridos incorretamente.</span><span class="sxs-lookup"><span data-stu-id="24ae0-106">Data might have been entered incorrectly.</span></span>  
  
-   <span data-ttu-id="24ae0-107">O valor está faltando.</span><span class="sxs-lookup"><span data-stu-id="24ae0-107">Value is missing.</span></span>  
  
-   <span data-ttu-id="24ae0-108">Os dados consistem em um espaço ou outra cadeia de caracteres nula.</span><span class="sxs-lookup"><span data-stu-id="24ae0-108">Data consists of a space or other null string.</span></span>  
  
-   <span data-ttu-id="24ae0-109">O valor é preciso, mas até agora está fora da distribuição, o que pode afetar significativamente o modelo.</span><span class="sxs-lookup"><span data-stu-id="24ae0-109">Value is accurate, but is so far outside the distribution that it can significantly affect the model.</span></span>  
  
 <span data-ttu-id="24ae0-110">O Cliente de Mineração de Dados para Excel o ajuda a detectar esses dados e atualiza ou elimina os valores.</span><span class="sxs-lookup"><span data-stu-id="24ae0-110">The Data Mining Client for Excel helps you detect this data, and then update the values or suppress them.</span></span> <span data-ttu-id="24ae0-111">Por exemplo, você pode substituir exceções por uma média aritmética ou excluir linhas que contenham valores potencialmente errados.</span><span class="sxs-lookup"><span data-stu-id="24ae0-111">For example, you can replace outliers with an arithmetic mean, or you can delete rows that contain potentially wrong values.</span></span>  
  
## <a name="handling-outliers"></a><span data-ttu-id="24ae0-112">Manipulando exceções</span><span class="sxs-lookup"><span data-stu-id="24ae0-112">Handling Outliers</span></span>  
 <span data-ttu-id="24ae0-113">O assistente para **remover exceções** oferece várias ferramentas para lidar com exceções adequadamente:</span><span class="sxs-lookup"><span data-stu-id="24ae0-113">The **Remove Outliers** wizard gives you several tools to handle outliers appropriately:</span></span>  
  
-   <span data-ttu-id="24ae0-114">Primeiro, você pode explorar os dados para entender melhor a distribuição dos valores e a relação das exceções para outros dados.</span><span class="sxs-lookup"><span data-stu-id="24ae0-114">First, you can explore the data to better understand the distribution of values and the relationship of the outliers to other data.</span></span>  
  
     <span data-ttu-id="24ae0-115">Por exemplo, você pode usar a tarefa **explorar dados** para revisar e corrigir os valores.</span><span class="sxs-lookup"><span data-stu-id="24ae0-115">For example, you can use the **Explore Data** task to review and fix the values.</span></span> <span data-ttu-id="24ae0-116">O assistente para **remover exceções** também exibe um gráfico, uma linha ou um gráfico de barras, para ajudá-lo a entender a distribuição de todos os valores.</span><span class="sxs-lookup"><span data-stu-id="24ae0-116">The **Remove Outliers** wizard also displays a graph, either a line or a bar chart, to help you understand the distribution of all values.</span></span>  
  
-   <span data-ttu-id="24ae0-117">Em seguida, você pode usar o assistente de **exceções** para remover ou alterar exceções.</span><span class="sxs-lookup"><span data-stu-id="24ae0-117">Next, you can use the **Outliers** wizard to remove or change outliers.</span></span> <span data-ttu-id="24ae0-118">O método usado depende se os valores são discretos ou contínuos.</span><span class="sxs-lookup"><span data-stu-id="24ae0-118">The method that you use depends on whether the values are discrete or continuous.</span></span>  
  
     <span data-ttu-id="24ae0-119">O assistente exibe valores discretos em um gráfico de barras, no qual cada barra representa um valor específico, e a altura da barra indica o número de casos de cada valor.</span><span class="sxs-lookup"><span data-stu-id="24ae0-119">The wizard displays discrete values in a bar chart, where each bar represents a specific value, and the height of the bar indicates the number of cases for each value.</span></span> <span data-ttu-id="24ae0-120">Ao deslizar o controle de limite no gráfico, você pode remover barras que representam grupos de valores potencial ou extremamente incorretos.</span><span class="sxs-lookup"><span data-stu-id="24ae0-120">By sliding the threshold control on the chart, you can cut off bars that represent groups of extreme or potentially bad values.</span></span>  
  
-   <span data-ttu-id="24ae0-121">O assistente exibe valores contínuos em um gráfico de barras ou linha.</span><span class="sxs-lookup"><span data-stu-id="24ae0-121">The wizard displays continuous values either on a bar chart or line chart.</span></span> <span data-ttu-id="24ae0-122">No gráfico de linha, o valor é representado no eixo x e a contagem de valores no eixo y.</span><span class="sxs-lookup"><span data-stu-id="24ae0-122">On the line chart, the value is represented on the x-axis and the count of values on the y-axis.</span></span>  
  
     <span data-ttu-id="24ae0-123">Você pode controlar se deseja remover ou manter os valores nas extremidades inferior e superior do gráfico, alterando os valores **mínimo** e **máximo** , ou deslizando as barras.</span><span class="sxs-lookup"><span data-stu-id="24ae0-123">You can control whether to remove or keep values at the low and high ends of the chart by changing the **Minimum** and **Maximum** values, or sliding the bars.</span></span> <span data-ttu-id="24ae0-124">À medida que você altera as configurações de valores mínimo e máximo, os dados que serão suprimidos são mostrados pelo sombreamento no grafo.</span><span class="sxs-lookup"><span data-stu-id="24ae0-124">As you change the minimum and maximum value settings, the data that will be suppressed is shown by shading in the graph.</span></span>  
  
 <span data-ttu-id="24ae0-125">Depois que você tiver selecionado com quais exceções trabalhar, informe ao assistente como manipular as exceções.</span><span class="sxs-lookup"><span data-stu-id="24ae0-125">After you have selected which outliers to work with, you tell the wizard how to handle the outliers.</span></span> <span data-ttu-id="24ae0-126">Você pode excluir as linhas que contêm os valores de exceção ou especificar um valor de substituição, como um valor médio, nulo ou outro de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="24ae0-126">You can either delete the rows that contain the outlier values, or you can specify a replacement value, such as a mean, a null, or another value of your choice.</span></span>  
  
 <span data-ttu-id="24ae0-127">O assistente lhe dá algumas opções para exibir os novos dados.</span><span class="sxs-lookup"><span data-stu-id="24ae0-127">Finally, the wizard gives you some options for displaying the new data.</span></span> <span data-ttu-id="24ae0-128">Você pode substituir os dados originais pelos novos valores, adicionar uma nova coluna à tabela que contém os novos valores ou criar uma nova planilha que contenha os dados atualizados.</span><span class="sxs-lookup"><span data-stu-id="24ae0-128">You can replace the original data with the new values, add a new column to the table that contains the new values, or create a new worksheet that contains the updated data.</span></span>  
  
### <a name="using-the-outlier-wizard"></a><span data-ttu-id="24ae0-129">Usando o Assistente de Exceções</span><span class="sxs-lookup"><span data-stu-id="24ae0-129">Using the Outlier Wizard</span></span>  
  
1.  <span data-ttu-id="24ae0-130">Na faixa de opções **mineração de dados** , clique em **limpar dados**e selecione **exceções**.</span><span class="sxs-lookup"><span data-stu-id="24ae0-130">In the **Data Mining** ribbon, click **Clean Data**, and select **Outliers**.</span></span>  
  
2.  <span data-ttu-id="24ae0-131">Na caixa de diálogo **selecionar dados de origem** , selecione uma tabela de dados do Excel ou um intervalo de células e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="24ae0-131">In the **Select Source Data** dialog box, select an Excel data table, or a range of cells, and click **Next**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="24ae0-132">Você não pode usar o assistente de **exceções** em dados externos, a menos que você o copie para o Excel primeiro.</span><span class="sxs-lookup"><span data-stu-id="24ae0-132">You cannot use the **Outliers** wizard on external data, unless you copy it to Excel first.</span></span>  
  
3.  <span data-ttu-id="24ae0-133">Na caixa de diálogo **Selecionar coluna** , selecione uma **única** coluna.</span><span class="sxs-lookup"><span data-stu-id="24ae0-133">In the **Select Column** dialog box, select a **single** column.</span></span>  
  
     <span data-ttu-id="24ae0-134">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="24ae0-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="24ae0-135">Na caixa de diálogo **especificar limites** , examine a distribuição de dados.</span><span class="sxs-lookup"><span data-stu-id="24ae0-135">In the **Specify Thresholds** dialog box, review the distribution of data.</span></span>  
  
    -   <span data-ttu-id="24ae0-136">Se a coluna contiver valores discretos, o assistente exibirá um histograma contendo a contagem de cada valor discreto.</span><span class="sxs-lookup"><span data-stu-id="24ae0-136">If the column contains discrete values, the wizard displays a histogram containing the count for each discrete value.</span></span>  
  
         <span data-ttu-id="24ae0-137">Supondo que as exceções sejam raras, você pode filtrá-las alterando o valor **mínimo** .</span><span class="sxs-lookup"><span data-stu-id="24ae0-137">Assuming that outliers are rare values, you can filter them out by changing the **Minimum** value.</span></span>  
  
    -   <span data-ttu-id="24ae0-138">Se a coluna contiver dados numéricos, você poderá clicar no botão **Exibir como discreto** ou **Exibir como botão numérico** para alternar entre a exibição dos valores em um gráfico de barras ou em um gráfico de linhas.</span><span class="sxs-lookup"><span data-stu-id="24ae0-138">If the column contains numeric data, you can click the **View as Discrete** button or the **View as Numeric** button to toggle between viewing the values in a bar chart or line chart.</span></span>  
  
5.  <span data-ttu-id="24ae0-139">Na caixa de diálogo **especificar limites** , escolha o intervalo de dados que você deseja manter digitando um valor mínimo e máximo ou arrastando as barras de controle deslizante.</span><span class="sxs-lookup"><span data-stu-id="24ae0-139">In the **Specify Thresholds** dialog box, choose the range of data you want to keep by typing a minimum and maximum value, or by dragging the slider bars.</span></span> <span data-ttu-id="24ae0-140">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="24ae0-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="24ae0-141">Na caixa de diálogo **tratamento** de exceções, especifique se deseja que os valores sejam excluídos ou substituídos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="24ae0-141">In the **Outlier Handling** dialog box, specify whether you want the values to be deleted or replaced, and click **Next**.</span></span>  
  
7.  <span data-ttu-id="24ae0-142">Na caixa de diálogo **Selecionar destino** , especifique onde você deseja que os novos dados sejam salvos.</span><span class="sxs-lookup"><span data-stu-id="24ae0-142">In the **Select Destination** dialog box, specify where you want the new data to be saved.</span></span>  
  
### <a name="related-options"></a><span data-ttu-id="24ae0-143">Opções relacionadas</span><span class="sxs-lookup"><span data-stu-id="24ae0-143">Related Options</span></span>  
 <span data-ttu-id="24ae0-144">O assistente fornece as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="24ae0-144">The wizard provides these options:</span></span>  
  
|<span data-ttu-id="24ae0-145">**Opções**</span><span class="sxs-lookup"><span data-stu-id="24ae0-145">**Options**</span></span>|<span data-ttu-id="24ae0-146">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="24ae0-146">**Comment**</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="24ae0-147">**Selecionar coluna**</span><span class="sxs-lookup"><span data-stu-id="24ae0-147">**Select Column**</span></span>|<span data-ttu-id="24ae0-148">Você pode trabalhar somente com uma coluna por vez.</span><span class="sxs-lookup"><span data-stu-id="24ae0-148">You can work with only one column at a time.</span></span>|  
|<span data-ttu-id="24ae0-149">**Especificar tratamento de limites**</span><span class="sxs-lookup"><span data-stu-id="24ae0-149">**Specify Thresholds Handling**</span></span>|<span data-ttu-id="24ae0-150">Defina um limite usando o **mínimo** para excluir valores que são encontrados em menos linhas do que o valor do limite.</span><span class="sxs-lookup"><span data-stu-id="24ae0-150">Set a threshold using **Minimum** to exclude values that are found in fewer rows than the threshold value.</span></span><br /><br /> <span data-ttu-id="24ae0-151">Inicialmente, o valor no **mínimo** é igual ao valor com menos linhas, e você não pode tornar o mínimo menor que esse valor.</span><span class="sxs-lookup"><span data-stu-id="24ae0-151">Initially the value in **Minimum** is equal to the value with the fewest rows, and you cannot make the minimum lower than that value.</span></span>|  
|<span data-ttu-id="24ae0-152">**Manipulação de Exceções**</span><span class="sxs-lookup"><span data-stu-id="24ae0-152">**Outlier Handling**</span></span>|<span data-ttu-id="24ae0-153">Se você decidir excluir exceções, poderá alterar os dados na planilha atual ou criar uma cópia dos dados em uma nova planilha.</span><span class="sxs-lookup"><span data-stu-id="24ae0-153">If you decide to delete outliers, you can either change the data in the current worksheet, or create a copy of the data in a new worksheet.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24ae0-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="24ae0-154">See Also</span></span>  
 [<span data-ttu-id="24ae0-155">Explorar dados &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="24ae0-155">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
  
