---
title: Detectar categorias (ferramentas de análise de tabela para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- clustering [data mining]
- mining model, decision tree
- category detection
ms.assetid: 3c7e9ebb-d0c9-498e-a9ba-cc13eaa43520
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4874c85d7e4ab65716741e8ae9433406dfb08b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683814"
---
# <a name="detect-categories-table-analysis-tools-for-excel"></a><span data-ttu-id="2d22f-102">Detectar Categorias (Ferramentas de Análise de Tabela para Excel)</span><span class="sxs-lookup"><span data-stu-id="2d22f-102">Detect Categories (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="2d22f-103">![Botão Detectar Categorias na faixa de opções](media/tat-detectcat.gif "Botão Detectar Categorias na faixa de opções")</span><span class="sxs-lookup"><span data-stu-id="2d22f-103">![Detect Categories button in ribbon](media/tat-detectcat.gif "Detect Categories button in ribbon")</span></span>

 <span data-ttu-id="2d22f-104">A ferramenta **detectar categorias** localiza automaticamente linhas em uma tabela que têm características semelhantes.</span><span class="sxs-lookup"><span data-stu-id="2d22f-104">The **Detect Categories** tool automatically finds rows in a table that have similar characteristics.</span></span>

 <span data-ttu-id="2d22f-105">Quando a ferramenta termina, cria um relatório que lista as categorias encontradas, junto com suas características de distinção.</span><span class="sxs-lookup"><span data-stu-id="2d22f-105">When the tool finishes, it creates a report that lists the categories it found, together with their distinguishing characteristics.</span></span> <span data-ttu-id="2d22f-106">Por padrão, ela adiciona uma nova coluna à tabela de dados que contém a categoria proposta para cada linha de dados.</span><span class="sxs-lookup"><span data-stu-id="2d22f-106">By default, it adds a new column to the data table that contains the proposed category for each row of your data.</span></span> <span data-ttu-id="2d22f-107">Assim, você pode examinar as categorias e renomeá-las.</span><span class="sxs-lookup"><span data-stu-id="2d22f-107">You can then review the categories and rename them.</span></span>

## <a name="using-the-detect-categories-tool"></a><span data-ttu-id="2d22f-108">Usando a ferramenta Detectar Categorias</span><span class="sxs-lookup"><span data-stu-id="2d22f-108">Using the Detect Categories Tool</span></span>

1.  <span data-ttu-id="2d22f-109">Abra uma tabela do Excel.</span><span class="sxs-lookup"><span data-stu-id="2d22f-109">Open an Excel table.</span></span>

2.  <span data-ttu-id="2d22f-110">Clique em **detectar categorias**.</span><span class="sxs-lookup"><span data-stu-id="2d22f-110">Click **Detect Categories**.</span></span>

3.  <span data-ttu-id="2d22f-111">Especifique as colunas a serem usadas na análise.</span><span class="sxs-lookup"><span data-stu-id="2d22f-111">Specify the columns to use in analysis.</span></span> <span data-ttu-id="2d22f-112">Você pode desmarcar colunas que tenham valores discretos, como nomes pessoais ou IDs de registro, porque essas colunas talvez não sejam úteis para análise.</span><span class="sxs-lookup"><span data-stu-id="2d22f-112">You can deselect columns that have distinct values, such as personal names or record IDs, because these columns might not be useful for analysis.</span></span>

4.  <span data-ttu-id="2d22f-113">Se desejar, especifique o número máximo de categorias a serem criadas.</span><span class="sxs-lookup"><span data-stu-id="2d22f-113">Optionally, specify the maximum number of categories to create.</span></span> <span data-ttu-id="2d22f-114">Por padrão, a ferramenta cria automaticamente tantas categorias quantas encontra.</span><span class="sxs-lookup"><span data-stu-id="2d22f-114">By default, the tool automatically creates as many categories as it finds.</span></span>

5.  <span data-ttu-id="2d22f-115">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2d22f-115">Click **Run**.</span></span>

6.  <span data-ttu-id="2d22f-116">A ferramenta cria uma nova planilha, denominada Relatório de Categorias, que contém a lista de categorias e suas características.</span><span class="sxs-lookup"><span data-stu-id="2d22f-116">The tool creates a new worksheet, named Categories Report, which contains the list of categories and their characteristics.</span></span>

 <span data-ttu-id="2d22f-117">Para obter mais informações sobre como especificar opções para a ferramenta, consulte [caixa de diálogo detectar categorias (ferramentas de análise de tabela para Excel)](detect-categories-table-analysis-tools-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="2d22f-117">For more information about how to specify options for the tool, see [Detect Categories Dialog Box (Table Analysis Tools for Excel)](detect-categories-table-analysis-tools-for-excel.md).</span></span>

## <a name="understanding-the-categories-report"></a><span data-ttu-id="2d22f-118">Compreendendo o Relatório de Categorias</span><span class="sxs-lookup"><span data-stu-id="2d22f-118">Understanding the Categories Report</span></span>
 <span data-ttu-id="2d22f-119">O **relatório categorias** contém duas tabelas, a **lista de categorias** e as características da **categoria**e um gráfico de perfis de **categoria** .</span><span class="sxs-lookup"><span data-stu-id="2d22f-119">The **Categories Report** contains two tables, **Category List** and **Category Characteristics**, and a **Category Profiles** chart.</span></span>

### <a name="category-list"></a><span data-ttu-id="2d22f-120">Lista de categorias</span><span class="sxs-lookup"><span data-stu-id="2d22f-120">Category List</span></span>
 <span data-ttu-id="2d22f-121">A primeira tabela lista as categorias encontradas.</span><span class="sxs-lookup"><span data-stu-id="2d22f-121">The first table lists the categories that were found.</span></span> <span data-ttu-id="2d22f-122">A coluna **contagem de linhas** indica quantas linhas de dados foram atribuídas a cada categoria.</span><span class="sxs-lookup"><span data-stu-id="2d22f-122">The **Row Count** column indicates how many rows of data were assigned to each category.</span></span>

 <span data-ttu-id="2d22f-123">O modelo cria nomes temporários para cada categoria, mas você pode renomear as categorias como quiser.</span><span class="sxs-lookup"><span data-stu-id="2d22f-123">The model creates temporary names for each category, but you can rename the categories as you like.</span></span> <span data-ttu-id="2d22f-124">Por exemplo, no exemplo a seguir, a primeira categoria foi renomeada como **baixa renda**, pois esse era o atributo superior do cluster.</span><span class="sxs-lookup"><span data-stu-id="2d22f-124">For example, in the following example, the first category has been renamed **Low Income**, because that was the top attribute of the cluster.</span></span>

 <span data-ttu-id="2d22f-125">![relatório criado pela ferramenta Detectar Categorias](media/dm13-tat-detectcat-report1.gif "relatório criado pela ferramenta Detectar Categorias")</span><span class="sxs-lookup"><span data-stu-id="2d22f-125">![report created by Detect Categories tool](media/dm13-tat-detectcat-report1.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="2d22f-126">Assim que você digita o novo rótulo, a alteração é propagada para todos os outros gráficos, bem como para a lista de categorias adicionada à planilha de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="2d22f-126">As soon as you type the new label, the change is propagated to all the other charts as well as to the category list added in the source data worksheet.</span></span>

### <a name="category-characteristics"></a><span data-ttu-id="2d22f-127">Características da Categoria</span><span class="sxs-lookup"><span data-stu-id="2d22f-127">Category Characteristics</span></span>
 <span data-ttu-id="2d22f-128">A segunda tabela, **características da categoria**, mostra detalhes sobre a composição de cada categoria.</span><span class="sxs-lookup"><span data-stu-id="2d22f-128">The second table, **Category Characteristics**, shows details about the makeup of each category.</span></span> <span data-ttu-id="2d22f-129">Clique no botão **Filtrar** na parte superior da coluna **categoria** para ver o foco em uma ou apenas algumas categorias.</span><span class="sxs-lookup"><span data-stu-id="2d22f-129">Click the **Filter** button at the top of the **Category** column to see focus on one or just a few categories.</span></span>

 <span data-ttu-id="2d22f-130">![relatório criado pela ferramenta Detectar Categorias](media/dm13-tat-detectcat-report2.gif "relatório criado pela ferramenta Detectar Categorias")</span><span class="sxs-lookup"><span data-stu-id="2d22f-130">![report created by Detect Categories tool](media/dm13-tat-detectcat-report2.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="2d22f-131">O sombreamento na coluna, **importância relativa**, indica a importância dessa combinação de atributo e valor como um fator de distinção.</span><span class="sxs-lookup"><span data-stu-id="2d22f-131">The shading in the column, **Relative Importance**, indicates how important that combination of attribute and value is as a distinguishing factor.</span></span> <span data-ttu-id="2d22f-132">Quanto maior a barra, maior a probabilidade de que esse atributo represente fortemente essa categoria.</span><span class="sxs-lookup"><span data-stu-id="2d22f-132">The longer the bar, the more likely it is that this attribute is strongly representative of this category.</span></span>

### <a name="categories-profile-chart"></a><span data-ttu-id="2d22f-133">Gráfico Perfil de Categorias</span><span class="sxs-lookup"><span data-stu-id="2d22f-133">Categories Profile Chart</span></span>
 <span data-ttu-id="2d22f-134">O gráfico final na planilha de **relatório categorias** , **perfis de categoria**, é um **gráfico dinâmico** interativo que você pode usar para reorganizar e ocultar campos, filtrar valores e personalizar a aparência do gráfico.</span><span class="sxs-lookup"><span data-stu-id="2d22f-134">The final chart in the **Categories Report** worksheet, **Category Profiles**, is an interactive **Pivot Chart** that you can use to rearrange and hide fields, filter on values, and customize the chart's appearance.</span></span>

 <span data-ttu-id="2d22f-135">O Excel 2013 agora fornece controles de **gráfico** e de **elementos de gráfico** diretamente na superfície de design que facilita a melhoria do design do gráfico.</span><span class="sxs-lookup"><span data-stu-id="2d22f-135">Excel 2013 now provides **Chart Styles** and **Chart Elements** controls right in the design surface that make it easy to improve the chart design.</span></span>

 <span data-ttu-id="2d22f-136">![relatório criado pela ferramenta Detectar Categorias](media/dm13-tat-detectcat-report3.gif "relatório criado pela ferramenta Detectar Categorias")</span><span class="sxs-lookup"><span data-stu-id="2d22f-136">![report created by Detect Categories tool](media/dm13-tat-detectcat-report3.gif "report created by Detect Categories tool")</span></span>

## <a name="requirements"></a><span data-ttu-id="2d22f-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d22f-137">Requirements</span></span>
 <span data-ttu-id="2d22f-138">A ferramenta **detectar categorias** não tem requisitos para a quantidade ou o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="2d22f-138">The **Detect Categories** tool has no requirements for the amount or type of data.</span></span>

> [!NOTE]
>  <span data-ttu-id="2d22f-139">Quando você usa a ferramenta **detectar categorias** , ela cria uma nova coluna, categoria, na tabela de dados original.</span><span class="sxs-lookup"><span data-stu-id="2d22f-139">When you use the **Detect Categories** tool, it creates a new column, Category, in the original data table.</span></span> <span data-ttu-id="2d22f-140">Se você deixar essa coluna na tabela de dados e, em seguida, executar operações subsequentes de mineração de dados, a presença dessa coluna poderá influenciar os resultados.</span><span class="sxs-lookup"><span data-stu-id="2d22f-140">If you leave this column in the data table and then perform subsequent data mining operations, the presence of this column could influence your results.</span></span> <span data-ttu-id="2d22f-141">Para assegurar que isso não afete outras operações, faça uma cópia da tabela de dados sem a coluna Categoria, antes de usar outras ferramentas de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="2d22f-141">To ensure that this does not affect other operations, you should make a copy of the data table without the Category column before using other data mining tools.</span></span>

## <a name="related-tools"></a><span data-ttu-id="2d22f-142">Ferramentas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2d22f-142">Related Tools</span></span>
 <span data-ttu-id="2d22f-143">Quando a ferramenta **detectar categorias** analisa seus dados, ela cria uma estrutura de data mining e um modelo de Data Mining usando o [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de clustering.</span><span class="sxs-lookup"><span data-stu-id="2d22f-143">When the **Detect Categories** tool analyzes your data, it creates a data mining structure and data mining model by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span>

 <span data-ttu-id="2d22f-144">Depois de criar um modelo de Data Mining usando a ferramenta **analisar influenciadores principais** , você pode usar o cliente de mineração de dados para Excel para procurar o modelo e explorar relações com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="2d22f-144">After you have created a data mining model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client for Excel to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="2d22f-145">O Cliente de Mineração de Dados para Excel é um suplemento separado que fornece funções de mineração de dados mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="2d22f-145">The Data Mining Client for Excel is a separate add-in that provides more advanced data mining functionality.</span></span> <span data-ttu-id="2d22f-146">Para obter informações, consulte [procurando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="2d22f-146">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>

 <span data-ttu-id="2d22f-147">Para obter mais informações sobre como usar os recursos de modelagem de dados no cliente de mineração de dados para Excel, consulte [criando um modelo de mineração de dados](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="2d22f-147">For more information about using the data modeling capabilities in the Data Mining Client for Excel, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="2d22f-148">Para obter mais informações sobre o algoritmo usado pela ferramenta **detectar categorias** , consulte o tópico "algoritmo de clustering da Microsoft" nos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] manuais online do.</span><span class="sxs-lookup"><span data-stu-id="2d22f-148">For more information about the algorithm used by the **Detect Categories** tool, see the topic "Microsoft Clustering Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d22f-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d22f-149">See Also</span></span>
 [<span data-ttu-id="2d22f-150">Ferramentas de Análise de Tabela para Excel</span><span class="sxs-lookup"><span data-stu-id="2d22f-150">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


