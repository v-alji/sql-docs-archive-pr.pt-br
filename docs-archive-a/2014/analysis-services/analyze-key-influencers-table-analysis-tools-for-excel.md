---
title: Analisar os influenciadores principais (ferramentas de análise de tabela para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- key influencers
- factor analysis
ms.assetid: 54d7b4ce-7b79-407a-985c-aa655ad19280
author: minewiskan
ms.author: owend
ms.openlocfilehash: f60eb5144059b0976d52eec2329f27553132146c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571187"
---
# <a name="analyze-key-influencers-table-analysis-tools-for-excel"></a><span data-ttu-id="0f387-102">Analisar os Influenciadores Principais (Ferramentas de Análise de Tabela para Excel)</span><span class="sxs-lookup"><span data-stu-id="0f387-102">Analyze Key Influencers (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="0f387-103">![Botão Analisar os Influenciadores Principais na faixa de opções](media/tat-aki.gif "Botão Analisar os Influenciadores Principais na faixa de opções")</span><span class="sxs-lookup"><span data-stu-id="0f387-103">![Analyze Key Influencers button in ribbon](media/tat-aki.gif "Analyze Key Influencers button in ribbon")</span></span>  
  
 <span data-ttu-id="0f387-104">Com a ferramenta **analisar influenciadores principais** , você escolhe uma coluna que contém um resultado de destino e o algoritmo determina quais fatores tinham a influência mais forte sobre o resultado.</span><span class="sxs-lookup"><span data-stu-id="0f387-104">With the **Analyze Key Influencers** tool, you choose a column that contains a target outcome, and the algorithm determines which factors had the strongest influence on the outcome.</span></span>  
  
 <span data-ttu-id="0f387-105">A ferramenta cria novas tabelas de dados que reportam os fatores associados a cada resultado e exibe graficamente a probabilidade de relação.</span><span class="sxs-lookup"><span data-stu-id="0f387-105">The tool creates new data tables that report the factors associated with each outcome and graphically displays the probability of the relationship.</span></span> <span data-ttu-id="0f387-106">Você pode filtrar as tabelas por fatores e resultados diferentes para explorar os resultados com mais profundidade.</span><span class="sxs-lookup"><span data-stu-id="0f387-106">You can filter the tables by different factors and outcomes to explore the results in more depth.</span></span>  
  
 <span data-ttu-id="0f387-107">Você também pode selecionar um par de resultados possíveis e compará-los.</span><span class="sxs-lookup"><span data-stu-id="0f387-107">You can also select a pair of possible outcomes and compare them.</span></span> <span data-ttu-id="0f387-108">Por exemplo, você pode comparar grupos diferentes de consumidores para determinar possíveis fatores de tomada de decisão.</span><span class="sxs-lookup"><span data-stu-id="0f387-108">For example, you might compare different groups of consumers to determine possible decision-making factors.</span></span>  
  
## <a name="using-the-analyze-key-influencers-tool"></a><span data-ttu-id="0f387-109">Usando a ferramenta Analisar os Influenciadores Principais</span><span class="sxs-lookup"><span data-stu-id="0f387-109">Using the Analyze Key Influencers Tool</span></span>  
  
1.  <span data-ttu-id="0f387-110">Abra uma tabela de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="0f387-110">Open an Excel data table.</span></span>  
  
2.  <span data-ttu-id="0f387-111">Em **ferramentas de tabela**, na faixa de quadro **analisar** , clique em **analisar influenciadores-chave.**</span><span class="sxs-lookup"><span data-stu-id="0f387-111">In **Table Tools**, on the **Analyze** ribbon, click **Analyze Key Influencers.**</span></span>  
  
3.  <span data-ttu-id="0f387-112">Selecione a coluna única que é o destino da análise.</span><span class="sxs-lookup"><span data-stu-id="0f387-112">Select the single column that is the target of analysis.</span></span>  
  
4.  <span data-ttu-id="0f387-113">Opcionalmente, clique em **escolher colunas a serem usadas para análise**.</span><span class="sxs-lookup"><span data-stu-id="0f387-113">Optionally, click **Choose columns to be used for analysis**.</span></span> <span data-ttu-id="0f387-114">Na caixa de diálogo **seleção de colunas avançadas** , escolha as colunas que têm mais probabilidade de conter dados relevantes.</span><span class="sxs-lookup"><span data-stu-id="0f387-114">In the **Advanced Columns Selection** dialog box, choose the columns that are most likely to contain relevant data.</span></span> <span data-ttu-id="0f387-115">Para melhorar o desempenho e a precisão, desmarque colunas como ID ou nome que não são importantes para análise de padrão.</span><span class="sxs-lookup"><span data-stu-id="0f387-115">To improve performance and accuracy, deselect columns such as ID or name that are unimportant for pattern analysis.</span></span> <span data-ttu-id="0f387-116">Clique em **OK** para fechar a caixa de diálogo **seleção de colunas avançadas** .</span><span class="sxs-lookup"><span data-stu-id="0f387-116">Click **OK** to close the **Advanced Columns Selection** dialog box.</span></span>  
  
5.  <span data-ttu-id="0f387-117">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0f387-117">Click **Run**.</span></span>  
  
     <span data-ttu-id="0f387-118">A ferramenta **analisar influenciadores principais** conduz uma análise dos dados para determinar as configurações ideais e define todos os parâmetros automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0f387-118">The **Analyze Key Influencers** tool conducts an analysis of the data to determine the optimum settings, and sets all parameters automatically.</span></span>  
  
6.  <span data-ttu-id="0f387-119">Se nenhum padrão for detectado, o assistente criará uma nova planilha contendo uma descrição do problema.</span><span class="sxs-lookup"><span data-stu-id="0f387-119">If no patterns were detected, the wizard creates a new worksheet that contains a description of the problem.</span></span>  
  
7.  <span data-ttu-id="0f387-120">Se forem detectados padrões, o assistente criará um relatório em uma nova planilha mostrando esses padrões.</span><span class="sxs-lookup"><span data-stu-id="0f387-120">If patterns are detected, the wizard creates a report on a new worksheet that shows the patterns.</span></span> <span data-ttu-id="0f387-121">O relatório é nomeado \*\*como influenciadores- \<column> chave para \*\*.</span><span class="sxs-lookup"><span data-stu-id="0f387-121">The report is named **Key Influencers for \<column>**.</span></span> <span data-ttu-id="0f387-122">Você pode personalizar o relatório conforme descrito no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="0f387-122">You can customize the report as described in the following procedure.</span></span>  
  
#### <a name="create-a-custom-report"></a><span data-ttu-id="0f387-123">Criar um relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="0f387-123">Create a custom report</span></span>  
  
1.  <span data-ttu-id="0f387-124">Na caixa de diálogo **discriminação baseada em influenciadores de chave** , escolha os dois valores que você deseja comparar selecionando-os nas listas suspensas **valor 1** e **valor 2** .</span><span class="sxs-lookup"><span data-stu-id="0f387-124">In the **Discrimination based on key influencers** dialog box, choose the two values that you want to compare by selecting them from the **Value 1** and **Value 2** dropdown lists.</span></span> <span data-ttu-id="0f387-125">Por exemplo, você pode comparar compradores a não compradores.</span><span class="sxs-lookup"><span data-stu-id="0f387-125">For example, you might compare buyers to non-buyers.</span></span>  
  
2.  <span data-ttu-id="0f387-126">Clique em **Adicionar relatório**.</span><span class="sxs-lookup"><span data-stu-id="0f387-126">Click **Add Report**.</span></span>  
  
     <span data-ttu-id="0f387-127">O assistente cria uma nova planilha e adiciona uma tabela para cada par de comparações de fatores chave.</span><span class="sxs-lookup"><span data-stu-id="0f387-127">The wizard creates a new worksheet and adds a table for each pair of key factor comparisons.</span></span>  
  
3.  <span data-ttu-id="0f387-128">Quando terminar de fazer comparações, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="0f387-128">When you are done making comparisons, click **Close**.</span></span>  
  
## <a name="understanding-the-key-influencers-report"></a><span data-ttu-id="0f387-129">Compreendendo o relatório Influenciadores Principais</span><span class="sxs-lookup"><span data-stu-id="0f387-129">Understanding the Key Influencers Report</span></span>  
 <span data-ttu-id="0f387-130">Após a criação do modelo de dados, a ferramenta **analisar influenciadores principais** cria relatórios que ajudam você a explorar e comparar os influenciadores principais.</span><span class="sxs-lookup"><span data-stu-id="0f387-130">After the data model has been created, the **Analyze Key Influencers** tool creates reports that help you explore and compare key influencers.</span></span>  
  
-   <span data-ttu-id="0f387-131">O relatório no lado esquerdo é gerado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0f387-131">The report on the left side is the one generated by default.</span></span> <span data-ttu-id="0f387-132">Ele mostra os preditores mais fortes da coluna de resultado (a variável dependente).</span><span class="sxs-lookup"><span data-stu-id="0f387-132">It shows the strongest predictors of the outcome column (the dependent variable).</span></span>  
  
-   <span data-ttu-id="0f387-133">O relatório no lado direito é opcional, que você pode criar comparando dois valores de resultado específicos.</span><span class="sxs-lookup"><span data-stu-id="0f387-133">The report on the right side is optional, which you can create by comparing two specific outcome values.</span></span> <span data-ttu-id="0f387-134">Esse relatório compara compradores e não compradores.</span><span class="sxs-lookup"><span data-stu-id="0f387-134">This report compares buyers and non-buyers.</span></span>  
  
-   <span data-ttu-id="0f387-135">Observe que uma nova planilha será adicionada para cada relatório que você cria.</span><span class="sxs-lookup"><span data-stu-id="0f387-135">Note that a new worksheet is added for each report that you create.</span></span> <span data-ttu-id="0f387-136">Você pode mover as tabelas depois que elas forem criadas; nós as colocamos lado a lado para comparação.</span><span class="sxs-lookup"><span data-stu-id="0f387-136">You can move the tables after they are created; we placed them side by side for comparison.</span></span>  
  
 <span data-ttu-id="0f387-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span><span class="sxs-lookup"><span data-stu-id="0f387-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span></span>  
  
 <span data-ttu-id="0f387-138">**Impacto relativo**</span><span class="sxs-lookup"><span data-stu-id="0f387-138">**Relative Impact**</span></span>  
 <span data-ttu-id="0f387-139">A barra sombreada no primeiro relatório indica a intensidade da associação desse atributo com o resultado.</span><span class="sxs-lookup"><span data-stu-id="0f387-139">The shaded bar in the first report indicates the strength of the association of this attribute with the outcome.</span></span>  
  
 <span data-ttu-id="0f387-140">O comprimento da barra indica a probabilidade de o fator colaborar para o resultado; portanto, quanto maior a barra sombreada, mais intensa a associação.</span><span class="sxs-lookup"><span data-stu-id="0f387-140">The length of the bar indicates the probability that the factor contributes to the outcome; therefore, the longer the shaded bar, the stronger the association.</span></span>  
  
 <span data-ttu-id="0f387-141">**Favorece**</span><span class="sxs-lookup"><span data-stu-id="0f387-141">**Favors**</span></span>  
 <span data-ttu-id="0f387-142">No segundo relatório, os valores de destino que você compara são listados em duas colunas, com os fatores relacionados listados em ordem decrescente de confiança.</span><span class="sxs-lookup"><span data-stu-id="0f387-142">In the second report, the target values that you compare are listed in two columns, with the related factors listed in order of descending confidence.</span></span>  
  
-   <span data-ttu-id="0f387-143">A barra **azul** mostra atributos que contribuem para o resultado, "não" (= não adquiriu).</span><span class="sxs-lookup"><span data-stu-id="0f387-143">The **blue** bar shows attributes contributing to the outcome, "No" (=did not purchase).</span></span>  
  
-   <span data-ttu-id="0f387-144">A barra **vermelha** mostra atributos que contribuem para o resultado "Sim" (= comprou uma bicicleta).</span><span class="sxs-lookup"><span data-stu-id="0f387-144">The **red** bar shows attributes contributing to the outcome, "Yes" (=purchased a bike).</span></span>  
  
 <span data-ttu-id="0f387-145">As cores na barra de matização são arbitrárias.</span><span class="sxs-lookup"><span data-stu-id="0f387-145">The colors in the shading bar are arbitrary.</span></span> <span data-ttu-id="0f387-146">Você pode alterar estas cores definindo as opções para design de tabela no Excel.</span><span class="sxs-lookup"><span data-stu-id="0f387-146">You can change these colors by setting the options for table design in Excel.</span></span>  
  
 <span data-ttu-id="0f387-147">Em um relatório que compara dois valores, o segundo relatório classificará os influenciadores principais pelo grau de impacto nos valores de destino.</span><span class="sxs-lookup"><span data-stu-id="0f387-147">In a report that contrasts two values, the second report ranks the key influencers by the amount of impact on the target values.</span></span>  
  
 <span data-ttu-id="0f387-148">Como todos os gráficos são baseados nas tabelas do Excel, você pode filtrar e classificar para enfatizar fatores ou resultados específicos.</span><span class="sxs-lookup"><span data-stu-id="0f387-148">Because all the charts are based on Excel tables, you can filter and sort to focus on specific factors or outcomes.</span></span>  
  
## <a name="more-about-the-analyze-key-influencers-tool"></a><span data-ttu-id="0f387-149">Mais informações sobre a ferramenta Analisar os Influenciadores Principais</span><span class="sxs-lookup"><span data-stu-id="0f387-149">More About the Analyze Key Influencers Tool</span></span>  
 <span data-ttu-id="0f387-150">Quando a ferramenta **analisar influenciadores principais** analisa seus dados, ela faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f387-150">When the **Analyze Key Influencers** tool analyzes your data, it does the following:</span></span>  
  
-   <span data-ttu-id="0f387-151">Cria uma estrutura de dados que armazena as principais informações sobre a distribuição dos dados.</span><span class="sxs-lookup"><span data-stu-id="0f387-151">Creates a data structure that stores key information about the distribution of your data.</span></span>  
  
-   <span data-ttu-id="0f387-152">Cria um modelo usando o algoritmo Naïve Bayes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0f387-152">Creates a model using the Microsoft Naïve Bayes algorithm.</span></span>  
  
-   <span data-ttu-id="0f387-153">Cria previsões que correlacionam cada coluna de dados com o resultado especificado.</span><span class="sxs-lookup"><span data-stu-id="0f387-153">Creates predictions that correlates each column of data with the specified outcome.</span></span>  
  
-   <span data-ttu-id="0f387-154">Usa a pontuação de confiança para cada uma das previsões para identificar os fatores que são mais influentes na geração do resultado desejado.</span><span class="sxs-lookup"><span data-stu-id="0f387-154">Uses the confidence score for each of the predictions to identify the factors that are the most influential in producing the targeted outcome.</span></span>  
  
-   <span data-ttu-id="0f387-155">Cria um relatório que descreve os influenciadores principais, ordenados por pontuações de confiança.</span><span class="sxs-lookup"><span data-stu-id="0f387-155">Creates a report describing the key influencers, ordered by confidence scores.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="0f387-156">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f387-156">Requirements</span></span>  
 <span data-ttu-id="0f387-157">Se a coluna de destino contiver valores numéricos contínuos, a ferramenta segmentará automaticamente os valores numéricos em grupos.</span><span class="sxs-lookup"><span data-stu-id="0f387-157">If the target column contains continuous numeric values, the tool automatically segments the numeric values into groups.</span></span> <span data-ttu-id="0f387-158">Esses agrupamentos representam clusters de casos com características semelhantes.</span><span class="sxs-lookup"><span data-stu-id="0f387-158">These groupings represent clusters of cases that have similar characteristics.</span></span> <span data-ttu-id="0f387-159">No entanto, talvez os valores numéricos não sejam divididos em grupos amigáveis com o usuário.</span><span class="sxs-lookup"><span data-stu-id="0f387-159">However, numeric values might not be divided into user-friendly groups.</span></span> <span data-ttu-id="0f387-160">Por exemplo, o relatório pode conter um agrupamento como " \< 12,85701", enquanto os usuários de relatório normalmente gostam de ver agrupamentos que usam números inteiros, como 10-19, 20-29 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="0f387-160">For example, the report might contain a grouping such as "\<12.85701", whereas report users typically like to see groupings that use whole numbers, such as 10-19, 20-29, and so on.</span></span>  
  
 <span data-ttu-id="0f387-161">Se você quiser agrupar dados numéricos de um modo diferente, será necessário segmentar os dados da maneira desejada antes de criar a análise.</span><span class="sxs-lookup"><span data-stu-id="0f387-161">If you want to group numeric data in a different way, you must segment the data the way you want before creating the analysis.</span></span> <span data-ttu-id="0f387-162">Por exemplo, você pode usar a ferramenta de [rerotulação](relabel-sql-server-data-mining-add-ins.md) no cliente de mineração de dados para Excel para criar um novo rótulo de agrupamento em uma coluna separada e, em seguida, usar apenas essa nova coluna na análise.</span><span class="sxs-lookup"><span data-stu-id="0f387-162">For example, you can use the [Relabel](relabel-sql-server-data-mining-add-ins.md) tool in the Data Mining Client for Excel to create a new grouping label in a separate column, and then use only that new column in analysis.</span></span>  
  
### <a name="related-tools"></a><span data-ttu-id="0f387-163">Ferramentas relacionadas</span><span class="sxs-lookup"><span data-stu-id="0f387-163">Related Tools</span></span>  
 <span data-ttu-id="0f387-164">A faixa de informações de **mineração de dados** fornece ferramentas mais avançadas, incluindo a capacidade de personalizar modelos de Data Mining</span><span class="sxs-lookup"><span data-stu-id="0f387-164">The **Data Mining** ribbon provides more advanced tools, including the ability to customize data mining models</span></span>  
  
 <span data-ttu-id="0f387-165">Se você salvar seu modelo usando a ferramenta **analisar influenciadores principais** , poderá usar o cliente de mineração de dados para procurar o modelo e explorar relações com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="0f387-165">If you save your model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="0f387-166">Para obter informações, consulte [procurando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="0f387-166">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span> <span data-ttu-id="0f387-167">Também é possível usar o Microsoft Office Visio para criar gráficos e diagramas que exibem as relações como cluster ou redes de dependências.</span><span class="sxs-lookup"><span data-stu-id="0f387-167">You can also use Microsoft Office Visio to create charts and diagrams that display the relationships as cluster or as dependency networks.</span></span> <span data-ttu-id="0f387-168">Para obter mais informações, consulte [solução de problemas de diagramas de mineração de dados do Visio &#40;SQL Server suplementos de mineração de dados&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="0f387-168">For more information, see [Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f387-169">Os modelos criados quando você usa as Ferramentas de Análise de Tabela são excluídas quando você fecha a planilha ou encerra a conexão com o servidor do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f387-169">The models that are created when you use the Table Analysis Tools are deleted when you close your worksheet or terminate the connection with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span> <span data-ttu-id="0f387-170">Portanto, você pode procurar os modelos contanto que a conexão permaneça aberta.</span><span class="sxs-lookup"><span data-stu-id="0f387-170">Therefore, you can only browse the models as long as the connection remains open.</span></span> <span data-ttu-id="0f387-171">Você não pode renderizar os modelos no Visio se fechar a conexão ou a planilha.</span><span class="sxs-lookup"><span data-stu-id="0f387-171">You cannot render the models in Visio if you close the connection or close the worksheet.</span></span>  
  
 <span data-ttu-id="0f387-172">Para obter mais informações sobre o algoritmo usado pela ferramenta **analisar influenciadores de chave** , consulte "algoritmo Bayes do Microsoft ingênua" em manuais online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f387-172">For more information about the algorithm used by the **Analyze Key Influencers** tool, see "Microsoft Naïve Bayes Algorithm" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f387-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f387-173">See Also</span></span>  
 <span data-ttu-id="0f387-174">[Ferramentas de análise de tabela para Excel](table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="0f387-174">[Table Analysis Tools for Excel](table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="0f387-175">Criar um modelo de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="0f387-175">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
