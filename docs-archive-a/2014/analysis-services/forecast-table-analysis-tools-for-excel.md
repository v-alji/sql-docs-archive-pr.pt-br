---
title: Previsão (ferramentas de análise de tabela para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- forecasting
- mining model, time series
- time series [data mining]
ms.assetid: 22bb0b5e-78f5-484e-883d-2b5985a12749
author: minewiskan
ms.author: owend
ms.openlocfilehash: abca22dbcb9ae6426e839f92e391a658f5029e31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570980"
---
# <a name="forecast-table-analysis-tools-for-excel"></a><span data-ttu-id="fc79c-102">Previsão (Ferramentas de Análise de Tabela para Excel)</span><span class="sxs-lookup"><span data-stu-id="fc79c-102">Forecast (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="fc79c-103">![Botão Previsão na faixa de opções Ferramentas de Análise de Tabela](media/tat-forecast.gif "Botão Previsão na faixa de opções Ferramentas de Análise de Tabela")</span><span class="sxs-lookup"><span data-stu-id="fc79c-103">![Forecast button in Table Analysis tools ribbon](media/tat-forecast.gif "Forecast button in Table Analysis tools ribbon")</span></span>  
  
 <span data-ttu-id="fc79c-104">A ferramenta de **previsão** ajuda você a fazer previsões com base em dados em uma tabela de dados do Excel ou em outra fonte de dados e, opcionalmente, exibir as probabilidades associadas a cada valor previsto.</span><span class="sxs-lookup"><span data-stu-id="fc79c-104">The **Forecast** tool helps you make predictions based on data in an Excel data table or other data source, and optionally view the probabilities associated with each predicted value.</span></span> <span data-ttu-id="fc79c-105">Por exemplo, se os dados contiverem uma coluna de data e uma coluna que mostre o total de vendas de cada dia do mês, você poderá prever as vendas dos dias futuros.</span><span class="sxs-lookup"><span data-stu-id="fc79c-105">For example, if your data contains a date column and a column that shows total sales for each day of the month, you could predict the sales for future days.</span></span> <span data-ttu-id="fc79c-106">Também é possível especificar o número de previsões a serem feitas.</span><span class="sxs-lookup"><span data-stu-id="fc79c-106">You can also specify the number of predictions to make.</span></span> <span data-ttu-id="fc79c-107">Por exemplo, você pode prever cinco ou trinta dias.</span><span class="sxs-lookup"><span data-stu-id="fc79c-107">For example, you can predict five days, or thirty.</span></span>  
  
 <span data-ttu-id="fc79c-108">Quando a ferramenta for concluída, ela anexará as novas previsões ao final da tabela da fonte de dados e realçará os novos valores.</span><span class="sxs-lookup"><span data-stu-id="fc79c-108">When the tool completes, it appends the new predictions to the end of the source data table, and highlights the new values.</span></span> <span data-ttu-id="fc79c-109">Novos valores de série temporal não são anexados; isso lhe permite examinar as previsões primeiro.</span><span class="sxs-lookup"><span data-stu-id="fc79c-109">New time series values are not appended; this allows you to review the predictions first.</span></span>  
  
 <span data-ttu-id="fc79c-110">A ferramenta também cria uma nova planilha chamada **relatório de previsão**.</span><span class="sxs-lookup"><span data-stu-id="fc79c-110">The tool also creates a new worksheet named **Forecasting Report**.</span></span> <span data-ttu-id="fc79c-111">Esta planilha reporta se o assistente criou a previsão com êxito.</span><span class="sxs-lookup"><span data-stu-id="fc79c-111">This worksheet reports whether the wizard successfully created a prediction.</span></span> <span data-ttu-id="fc79c-112">A nova planilha também contém um gráfico de linha que mostra as tendências históricas.</span><span class="sxs-lookup"><span data-stu-id="fc79c-112">The new worksheet also contains a line graph that shows the historical trends.</span></span>  
  
 <span data-ttu-id="fc79c-113">Quando você estende a série temporal para incluir as novas previsões, os valores previstos são adicionados ao gráfico de linha.</span><span class="sxs-lookup"><span data-stu-id="fc79c-113">When you extend the time series to include the new predictions, the predicted values are added to the line graph.</span></span> <span data-ttu-id="fc79c-114">Os valores históricos são mostrados como uma linha sólida e as previsões são mostradas como uma linha pontilhada.</span><span class="sxs-lookup"><span data-stu-id="fc79c-114">The historical values are shown as a solid line and the predictions are shown as a dotted line.</span></span>  
  
## <a name="using-the-forecast-tool"></a><span data-ttu-id="fc79c-115">Usando a ferramenta Previsão</span><span class="sxs-lookup"><span data-stu-id="fc79c-115">Using the Forecast Tool</span></span>  
  
1.  <span data-ttu-id="fc79c-116">Abra uma tabela do Excel que contenha dados numéricos previsíveis.</span><span class="sxs-lookup"><span data-stu-id="fc79c-116">Open an Excel table that contains predictable numeric data.</span></span>  
  
2.  <span data-ttu-id="fc79c-117">Clique em **previsão** na guia **analisar** .</span><span class="sxs-lookup"><span data-stu-id="fc79c-117">Click **Forecast** on the **Analyze** tab.</span></span>  
  
3.  <span data-ttu-id="fc79c-118">Especifique as colunas a serem previstas.</span><span class="sxs-lookup"><span data-stu-id="fc79c-118">Specify the columns to forecast.</span></span> <span data-ttu-id="fc79c-119">A ferramenta seleciona automaticamente colunas nos dados que têm um tipo de dados previsível – ou seja, dados numéricos contínuos.</span><span class="sxs-lookup"><span data-stu-id="fc79c-119">The tool automatically selects columns in the data that have a predictable data type-that is, continuous numeric data.</span></span> <span data-ttu-id="fc79c-120">Talvez a ferramenta não selecione algumas colunas que tenham dados numéricos contínuos caso elas contenham muitos valores de zero ou nulos, porque os dados ausentes podem afetar os resultados.</span><span class="sxs-lookup"><span data-stu-id="fc79c-120">The tool might not select some columns that have continuous numeric data if the columns contain many null or zero values, because the missing data might affect the results.</span></span> <span data-ttu-id="fc79c-121">Se isso acontecer, você poderá corrigir os dados usando a ferramenta [rerotular &#40;SQL Server suplementos de mineração de dados&#41;](relabel-sql-server-data-mining-add-ins.md) .</span><span class="sxs-lookup"><span data-stu-id="fc79c-121">If this happens, you can fix the data by using the [Relabel &#40;SQL Server Data Mining Add-ins&#41;](relabel-sql-server-data-mining-add-ins.md) tool.</span></span>  
  
4.  <span data-ttu-id="fc79c-122">Especifique a coluna que contém um identificador de data, tempo ou outra série.</span><span class="sxs-lookup"><span data-stu-id="fc79c-122">Specify the column that contains the date, time, or other series identifier.</span></span> <span data-ttu-id="fc79c-123">Se você selecionar a opção, **\<no time stamp>** a ferramenta criará uma série com base na sequência de linhas nos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="fc79c-123">If you select the option **\<no time stamp>** the tool will create a series based on the sequence of rows in the source data.</span></span>  
  
5.  <span data-ttu-id="fc79c-124">Especifique o número de previsões a serem feitas.</span><span class="sxs-lookup"><span data-stu-id="fc79c-124">Specify the number of predictions to make.</span></span>  
  
6.  <span data-ttu-id="fc79c-125">Se desejar, forneça uma dica ao algoritmo para informar se você espera que os dados sejam repetidos semanalmente, mensalmente ou em outros períodos.</span><span class="sxs-lookup"><span data-stu-id="fc79c-125">Optionally, provide a hint to the algorithm about whether you expect your data to repeat weekly, monthly, or in other periods.</span></span> <span data-ttu-id="fc79c-126">Se os dados não couberem em nenhum dos padrões determinados, ou se você não estiver ciente de quaisquer padrões, selecione **\<detect automatically>** para que a ferramenta Localize os períodos de tempo de repetição.</span><span class="sxs-lookup"><span data-stu-id="fc79c-126">If your data does not fit any of the given patterns, or if you are unaware of any patterns, select **\<detect automatically>** to have the tool find the repeating time periods.</span></span>  
  
7.  <span data-ttu-id="fc79c-127">O assistente adiciona as previsões à tabela de origem e cria um relatório de previsão em uma nova planilha.</span><span class="sxs-lookup"><span data-stu-id="fc79c-127">The wizard adds the predictions to the source table, and creates a forecasting report in a new worksheet.</span></span>  
  
8.  <span data-ttu-id="fc79c-128">Para adicionar os novos valores ao gráfico de previsão, estenda a série temporal para incluir os valores previstos.</span><span class="sxs-lookup"><span data-stu-id="fc79c-128">To add the new values to the prediction graph, extend the time series to include the forecasted values.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="fc79c-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc79c-129">Requirements</span></span>  
 <span data-ttu-id="fc79c-130">As colunas previstas devem conter dados numéricos contínuos, como moeda ou outros números.</span><span class="sxs-lookup"><span data-stu-id="fc79c-130">The columns that you predict must contain continuous numeric data, such as currency or other numbers.</span></span>  
  
 <span data-ttu-id="fc79c-131">Se possível, os dados também devem incluir uma coluna que contenha uma série de horários ou datas.</span><span class="sxs-lookup"><span data-stu-id="fc79c-131">If possible, your data should also include a column that contains a series of times or dates.</span></span> <span data-ttu-id="fc79c-132">Você pode usar uma série numérica (1, 2, 3...) em vez de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="fc79c-132">You can use a numeric series (1,2,3....) instead of date and time data.</span></span> <span data-ttu-id="fc79c-133">No entanto, os valores na coluna da série devem ser exclusivos.</span><span class="sxs-lookup"><span data-stu-id="fc79c-133">However, values in the series column must be unique.</span></span> <span data-ttu-id="fc79c-134">Ocorrerá um erro se a ferramenta de **previsão** encontrar valores duplicados na coluna série.</span><span class="sxs-lookup"><span data-stu-id="fc79c-134">An error occurs if the **Forecast** tool finds duplicate values in the series column.</span></span>  
  
 <span data-ttu-id="fc79c-135">Você não pode prever uma data usando a ferramenta de **previsão** .</span><span class="sxs-lookup"><span data-stu-id="fc79c-135">You cannot predict a date by using the **Forecast** tool.</span></span> <span data-ttu-id="fc79c-136">Embora talvez não ocorra um erro, esse algoritmo não foi projetado para usar datas como valores previsíveis.</span><span class="sxs-lookup"><span data-stu-id="fc79c-136">Although an error might not occur, this algorithm is not designed to use dates as predictable values.</span></span>  
  
### <a name="understanding-time-stamps"></a><span data-ttu-id="fc79c-137">Entendendo carimbos de data/hora</span><span class="sxs-lookup"><span data-stu-id="fc79c-137">Understanding Time Stamps</span></span>  
 <span data-ttu-id="fc79c-138">Você deve identificar uma coluna a ser usada como *carimbo de data/hora*.</span><span class="sxs-lookup"><span data-stu-id="fc79c-138">You must identify a column to use as a *time stamp*.</span></span> <span data-ttu-id="fc79c-139">O carimbo de data/hora serve para duas finalidades.</span><span class="sxs-lookup"><span data-stu-id="fc79c-139">The time stamp serves two purposes.</span></span> <span data-ttu-id="fc79c-140">Primeiro, identifica exclusivamente um valor em uma série temporal.</span><span class="sxs-lookup"><span data-stu-id="fc79c-140">First, it uniquely identifies a value in a time series.</span></span> <span data-ttu-id="fc79c-141">Por exemplo, se você estiver rastreando vendas diariamente, deverá ter apenas um valor de vendas para cada dia.</span><span class="sxs-lookup"><span data-stu-id="fc79c-141">For example, if you are tracking sales on a daily basis, you should have only one sales value for each day.</span></span> <span data-ttu-id="fc79c-142">A data do calendário poderá ser usada como carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="fc79c-142">The calendar date can be used as the time stamp.</span></span> <span data-ttu-id="fc79c-143">Segundo, a coluna de carimbo de data/hora indica a unidade para realização de previsões.</span><span class="sxs-lookup"><span data-stu-id="fc79c-143">Second, the time stamp column indicates the unit for making predictions.</span></span> <span data-ttu-id="fc79c-144">Se você estiver rastreando vendas diárias, suas previsões também serão feitas em unidades de dias.</span><span class="sxs-lookup"><span data-stu-id="fc79c-144">If you are tracking daily sales, your predictions will also be in units of days.</span></span>  
  
 <span data-ttu-id="fc79c-145">Se os dados não incluírem uma coluna de data ou hora, a ferramenta criará automaticamente uma chave de série temporal, denominada _RowIndex.</span><span class="sxs-lookup"><span data-stu-id="fc79c-145">If your data does not include a date or time column, the tool will automatically create a temporary series key, named _RowIndex.</span></span> <span data-ttu-id="fc79c-146">A chave será baseada na ordem das linhas no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="fc79c-146">The key will be based on the order of the rows in the data set.</span></span>  
  
 <span data-ttu-id="fc79c-147">Quando você especificar o número de previsões, digite um número inteiro que indique a contagem de etapas.</span><span class="sxs-lookup"><span data-stu-id="fc79c-147">When you specify the number of predictions, you enter a whole number that indicates the number of steps.</span></span> <span data-ttu-id="fc79c-148">As unidades dessas etapas dependerão das unidades usadas nas séries temporal e de data nos seus dados.</span><span class="sxs-lookup"><span data-stu-id="fc79c-148">The units for these steps depend on the units used in the time and date series in your data.</span></span> <span data-ttu-id="fc79c-149">Se os dados listarem resultados de vendas por mês, a previsão será feita para uma série de meses.</span><span class="sxs-lookup"><span data-stu-id="fc79c-149">If your data lists sales results by the month, the prediction will be for a series of months.</span></span> <span data-ttu-id="fc79c-150">Não será possível alterar as unidades de tempo, a menos que você altere os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="fc79c-150">You cannot change the units of time unless you change the source data.</span></span>  
  
### <a name="understanding-periodicity"></a><span data-ttu-id="fc79c-151">Entendendo a periodicidade</span><span class="sxs-lookup"><span data-stu-id="fc79c-151">Understanding Periodicity</span></span>  
 <span data-ttu-id="fc79c-152">Uma previsão se baseia na repetição de padrões durante um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="fc79c-152">A forecast is based on repeating patterns over a period of time.</span></span> <span data-ttu-id="fc79c-153">Assim, o algoritmo MTS executa cálculos para determinar os períodos de tempo que têm os padrões mais intensos.</span><span class="sxs-lookup"><span data-stu-id="fc79c-153">Therefore, the Microsoft Time Series algorithm performs calculations to determine the time periods that have the strongest patterns.</span></span> <span data-ttu-id="fc79c-154">*Periodicidade* refere-se a esses períodos de tempo.</span><span class="sxs-lookup"><span data-stu-id="fc79c-154">*Periodicity* refers to these time periods.</span></span>  
  
 <span data-ttu-id="fc79c-155">Uma série temporal pode conter vários padrões potenciais.</span><span class="sxs-lookup"><span data-stu-id="fc79c-155">A time series can contain many potential patterns.</span></span> <span data-ttu-id="fc79c-156">Se você tiver certeza de que os dados contêm um certo padrão, talvez possa melhorar a qualidade da previsão fornecendo uma dica ao algoritmo.</span><span class="sxs-lookup"><span data-stu-id="fc79c-156">If you are certain that your data contains a certain pattern, you may be able to improve the quality of prediction by providing a hint to the algorithm.</span></span>  
  
 <span data-ttu-id="fc79c-157">Por exemplo, se você esperar que os dados se repitam semanalmente, selecione Semanalmente para indicar que o algoritmo deve procurar padrões semanais.</span><span class="sxs-lookup"><span data-stu-id="fc79c-157">For example, if you expect that your data repeats on a weekly basis, you can select Weekly to indicate that the algorithm should look for weekly patterns.</span></span> <span data-ttu-id="fc79c-158">No entanto, se nenhum padrão semanal intenso for encontrado, o algoritmo ignorará a dica.</span><span class="sxs-lookup"><span data-stu-id="fc79c-158">However, if no strong weekly patterns are found, the algorithm will ignore the hint.</span></span>  
  
## <a name="understanding-the-forecasting-report"></a><span data-ttu-id="fc79c-159">Compreendendo o relatório de previsão</span><span class="sxs-lookup"><span data-stu-id="fc79c-159">Understanding the Forecasting Report</span></span>  
 <span data-ttu-id="fc79c-160">Neste gráfico, os valores históricos da tabela de dados aparecem como uma linha escura.</span><span class="sxs-lookup"><span data-stu-id="fc79c-160">In this graph, the historical values from your data table appear as a dark line.</span></span> <span data-ttu-id="fc79c-161">Os valores previstos aparecem como linhas pontilhadas.</span><span class="sxs-lookup"><span data-stu-id="fc79c-161">The predicted values appear as dotted lines.</span></span> <span data-ttu-id="fc79c-162">Você pode clicar em um ponto na linha para visualizar o valor previsto.</span><span class="sxs-lookup"><span data-stu-id="fc79c-162">You can click a point on the line to see the forecasted value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc79c-163">Se você não vir rótulos no eixo de tempo para os valores previstos no grafo, abra a planilha que contém os valores previstos e use a função de **série Fill** no Excel para estender a coluna de carimbo de data/hora para incluir os valores previstos.</span><span class="sxs-lookup"><span data-stu-id="fc79c-163">If you do not see labels on the time axis for the predicted values in the graph, open the worksheet that contains the predicted values, and use the **Fill, Series** function in Excel to extend the time stamp column to include the predicted values.</span></span>  
  
 <span data-ttu-id="fc79c-164">Em alguns casos, talvez a previsão não tenha o número necessário de frações de tempo.</span><span class="sxs-lookup"><span data-stu-id="fc79c-164">In some cases, the forecast may not have as many time slices as requested.</span></span> <span data-ttu-id="fc79c-165">Em geral, isso significa que os dados não eram suficientes para permitir ao algoritmo prever tão adiante no futuro.</span><span class="sxs-lookup"><span data-stu-id="fc79c-165">This usually means that data was insufficient to allow the algorithm to forecast that far into the future.</span></span> <span data-ttu-id="fc79c-166">A ferramenta de **previsão** fará apenas previsões que atendam a um limite de probabilidade mínimo.</span><span class="sxs-lookup"><span data-stu-id="fc79c-166">The **Forecast** tool will only make predictions that meet a minimum probability threshold.</span></span>  
  
## <a name="related-tools"></a><span data-ttu-id="fc79c-167">Ferramentas relacionadas</span><span class="sxs-lookup"><span data-stu-id="fc79c-167">Related Tools</span></span>  
 <span data-ttu-id="fc79c-168">O Cliente de Mineração de Dados para Excel, um suplemento separado que fornece funções de mineração de dados mais avançadas, também contém um assistente para previsão.</span><span class="sxs-lookup"><span data-stu-id="fc79c-168">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, also contains a wizard for forecasting.</span></span>  
  
 <span data-ttu-id="fc79c-169">A ferramenta de **previsão** (nas ferramentas de análise de tabela para Excel) e o assistente de **previsão** (no cliente de mineração de dados para Excel) usam o [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Time Series.</span><span class="sxs-lookup"><span data-stu-id="fc79c-169">Both the **Forecast** tool (in the Table Analysis Tools for Excel) and the **Forecast** wizard (in the Data Mining Client for Excel) use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm.</span></span>  
  
-   <span data-ttu-id="fc79c-170">A ferramenta de **previsão** é mais fácil de usar porque configura automaticamente o algoritmo para usar as configurações mais adequadas para seus dados.</span><span class="sxs-lookup"><span data-stu-id="fc79c-170">The **Forecast** tool is easier to use because it automatically configures the algorithm to use the settings that are best for your data.</span></span>  
  
-   <span data-ttu-id="fc79c-171">O assistente de **previsão** no cliente de mineração de dados para Excel fornece a capacidade de personalizar os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="fc79c-171">The **Forecast** wizard in the Data Mining Client for Excel provides you with the ability to customize the parameters.</span></span>  
  
 <span data-ttu-id="fc79c-172">Para obter mais informações sobre o assistente de **previsão** , consulte [assistente de previsão &#40;suplementos de mineração de dados para Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="fc79c-172">For more information about the **Forecast** wizard, see [Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md).</span></span> <span data-ttu-id="fc79c-173">Para obter mais informações sobre o algoritmo usado para previsão, consulte o tópico "Algoritmo MTS" nos Manuais Online do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc79c-173">For more information about the algorithm used for forecasting, see the topic "Microsoft Time Series Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc79c-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fc79c-174">See Also</span></span>  
 [<span data-ttu-id="fc79c-175">Ferramentas de Análise de Tabela para Excel</span><span class="sxs-lookup"><span data-stu-id="fc79c-175">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  