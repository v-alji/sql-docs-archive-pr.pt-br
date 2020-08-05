---
title: Controlando a exibição da região de dados Tablix em uma página de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f81c48cc-f038-4f57-988d-e9a3cbb46424
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3a3f01dc722d94f72b8bf348415e7dd7fa85132
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572447"
---
# <a name="controlling-the-tablix-data-region-display-on-a-report-page-report-builder-and-ssrs"></a><span data-ttu-id="f4ea7-102">Controlando a exibição da região de dados Tablix em uma página do relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f4ea7-102">Controlling the Tablix Data Region Display on a Report Page (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f4ea7-103">Este tópico descreve as propriedades de uma região de dados Tablix que pode ser modificada para alterar a forma como uma região de dados Tablix é exibida quando visualizada em um relatório.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-103">This topic describes properties for a tablix data region that you can modify to change the way a tablix data region appears when you view it in a report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="controlling-the-appearance-of-data"></a><span data-ttu-id="f4ea7-104">Controlando a aparência dos dados</span><span class="sxs-lookup"><span data-stu-id="f4ea7-104">Controlling the Appearance of Data</span></span>  
 <span data-ttu-id="f4ea7-105">Os seguintes recursos ajudam a controlar a aparência de uma região de dados Tablix:</span><span class="sxs-lookup"><span data-stu-id="f4ea7-105">The following features help control the appearance of a tablix data region:</span></span>  
  
-   <span data-ttu-id="f4ea7-106">**Formatando dados.**</span><span class="sxs-lookup"><span data-stu-id="f4ea7-106">**Formatting data.**</span></span> <span data-ttu-id="f4ea7-107">Para formatar dados em uma tabela, matriz ou lista, defina as propriedades de formato da caixa de texto na célula.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-107">To format data in a table, matrix, or list, set the format properties of the text box in the cell.</span></span> <span data-ttu-id="f4ea7-108">É possível definir propriedades para várias células ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-108">You can set properties for multiple cells at the same time.</span></span> <span data-ttu-id="f4ea7-109">Para formatar dados em um gráfico, defina as propriedades de formatação na série.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-109">To format data in a chart, set formatting properties on the series.</span></span> <span data-ttu-id="f4ea7-110">Para obter mais informações, consulte [Formatando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) e [Formatando um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-110">For more information, see [Formatting Report Items &#40;Report Builder and SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) and [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f4ea7-111">**Gravando expressões**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-111">**Writing expressions**.</span></span> <span data-ttu-id="f4ea7-112">Para obter mais informações, consulte [Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) e [Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-112">For more information, see [Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md), and [Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f4ea7-113">**Controlando a ordem de classificação**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-113">**Controlling sort order**.</span></span> <span data-ttu-id="f4ea7-114">Para controlar a ordem de classificação, você deve definir expressões de classificação na região de dados.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-114">To control the sort order, you must define sort expressions on the data region.</span></span> <span data-ttu-id="f4ea7-115">Para controlar a ordem de classificação das linhas e das colunas associadas a um grupo, você deve definir expressões de classificação no grupo, inclusive os grupos detalhados.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-115">To control sort order for rows and columns that are associated with a group, you must define sort expressions on the group, including the details groups.</span></span> <span data-ttu-id="f4ea7-116">Também é possível adicionar botões de classificação interativos para permitir que o usuário classifique uma região de dados Tablix ou seus grupos.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-116">You can also add interactive sort buttons to enable the user to sort a tablix data region or its groups.</span></span> <span data-ttu-id="f4ea7-117">Para obter mais informações, consulte [Classificar dados em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-117">For more information, see [Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f4ea7-118">**Exibindo uma mensagem quando não há dados**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-118">**Displaying a message when there is no data**.</span></span> <span data-ttu-id="f4ea7-119">Quando não há dados de um conjunto de dados de relatório em tempo de execução, é possível escrever uma mensagem própria a ser exibida em lugar da região de dados.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-119">When no data exists for a report dataset at run time, you can write your own message to display in place of the data region.</span></span> <span data-ttu-id="f4ea7-120">Para obter mais informações, consulte [Definir uma mensagem Nenhum Dado para uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](../report-data/set-a-no-data-message-for-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-120">For more information, see [Set a No Data Message for a Data Region &#40;Report Builder and SSRS&#41;](../report-data/set-a-no-data-message-for-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f4ea7-121">**Ocultando dados condicionalmente**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-121">**Conditionally hiding data**.</span></span> <span data-ttu-id="f4ea7-122">Para controlar condicionalmente se deseja mostrar ou ocultar uma região de dados ou partes de uma região de dados, você pode definir a Propriedade Hidden como `True` or como uma expressão.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-122">To conditionally control whether to show or hide a data region or parts of a data region, you can set the Hidden property to `True` or to an expression.</span></span> <span data-ttu-id="f4ea7-123">Entre as expressões podem estar referências a parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-123">Expressions can include references to report parameters.</span></span> <span data-ttu-id="f4ea7-124">Também é possível especificar um item de alternância, para que usuário possa optar por exibir dados detalhados.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-124">You can also specify a toggle item, so that user can decide to display detail data.</span></span> <span data-ttu-id="f4ea7-125">Para obter mais informações, consulte [Ação de análise detalhada &#40;Construtor de Relatórios e SSRS&#41;](drilldown-action-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-125">For more information, see [Drilldown Action &#40;Report Builder and SSRS&#41;](drilldown-action-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f4ea7-126">**Mesclando células.**</span><span class="sxs-lookup"><span data-stu-id="f4ea7-126">**Merging cells.**</span></span> <span data-ttu-id="f4ea7-127">Várias células contíguas em uma tabela podem ser integradas em uma única célula.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-127">Multiple contiguous cells within a table can be combined into a single cell.</span></span> <span data-ttu-id="f4ea7-128">Isso é conhecido como abrangência de coluna ou mesclagem de célula.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-128">This is known as a column span or a cell merge.</span></span> <span data-ttu-id="f4ea7-129">As células só podem ser combinadas horizontal ou verticalmente.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-129">Cells can only be combined horizontally or vertically.</span></span> <span data-ttu-id="f4ea7-130">Quando você mescla células, apenas os dados na primeira célula são preservados.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-130">When you merge cells, only the data in the first cell is preserved.</span></span> <span data-ttu-id="f4ea7-131">Os dados das demais células são removidos.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-131">Data in other cells is removed.</span></span> <span data-ttu-id="f4ea7-132">As células mescladas podem ser divididas nas colunas originais.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-132">Merged cells can be split into their original columns.</span></span> <span data-ttu-id="f4ea7-133">Para obter mais informações, consulte [Mesclar células em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](merge-cells-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-133">For more information, see [Merge Cells in a Data Region &#40;Report Builder and SSRS&#41;](merge-cells-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
## <a name="controlling-tablix-data-region-position-and-expansion-on-a-page"></a><span data-ttu-id="f4ea7-134">Controlando a posição da região de dados Tablix e a expansão em uma página</span><span class="sxs-lookup"><span data-stu-id="f4ea7-134">Controlling Tablix Data Region Position and Expansion on a Page</span></span>  
 <span data-ttu-id="f4ea7-135">Os seguintes recursos ajudam a controlar a forma como uma região de dados Tablix é exibida em um relatório renderizado:</span><span class="sxs-lookup"><span data-stu-id="f4ea7-135">The following features help control the way a tablix data region displays in a rendered report:</span></span>  
  
-   <span data-ttu-id="f4ea7-136">**Controlando a posição de uma região de dados Tablix em relação a outros itens de relatório**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-136">**Controlling the position of a tablix data region in relation to other report items**.</span></span> <span data-ttu-id="f4ea7-137">Uma região de dados Tablix pode ser posicionada acima, próxima a, ou abaixo dos demais itens de relatório na superfície de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-137">A tablix data region can be positioned above, next to, or below other report items on the report design surface.</span></span> <span data-ttu-id="f4ea7-138">Em tempo de execução, o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] expande a região de dados Tablix conforme necessário para os dados recuperados do conjunto de dados vinculado, movendo itens de relatório semelhantes além do necessário.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-138">At run time, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] expands the tablix data region as needed for the data retrieved for the linked dataset, moving peer report items aside as needed.</span></span> <span data-ttu-id="f4ea7-139">Para ancorar um Tablix próximo a outro item de relatório, você deve criar os itens de relatório semelhantes e ajustar as posições relativas.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-139">To anchor a tablix next to another report item, you must make the report items peers and adjust their relative positions.</span></span> <span data-ttu-id="f4ea7-140">Para obter mais informações, consulte [Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-140">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f4ea7-141">**Alterando a direção de expansão**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-141">**Changing the Expansion Direction**.</span></span> <span data-ttu-id="f4ea7-142">Para controlar se uma região de dados tablix se expande na página LTR (da esquerda para direita) ou RTL (da direita para esquerda), use a propriedade Direction, que pode ser acessada na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-142">To control whether a tablix data region expands across the page from left-to-right (LTR) or from right-to-left (RTL), use the Direction property, which can be accessed through the Properties window.</span></span> <span data-ttu-id="f4ea7-143">Para obter mais informações, consulte [Renderizando regiões de dados &#40;Construtor de Relatórios e SSRS&#41;](rendering-data-regions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-143">For more information, see [Rendering Data Regions &#40;Report Builder and SSRS&#41;](rendering-data-regions-report-builder-and-ssrs.md).</span></span>  
  
## <a name="controlling-how-a-tablix-data-region-renders-on-a-page"></a><span data-ttu-id="f4ea7-144">Controlando a forma de renderização de uma região de dados Tablix em uma página</span><span class="sxs-lookup"><span data-stu-id="f4ea7-144">Controlling How a Tablix Data Region Renders on a Page</span></span>  
 <span data-ttu-id="f4ea7-145">A lista a seguir descreve modos que podem ajudar a controlar como uma região de dados Tablix aparece em um relatório:</span><span class="sxs-lookup"><span data-stu-id="f4ea7-145">The following list describes ways that you can help control how a tablix data region appears in a report:</span></span>  
  
-   <span data-ttu-id="f4ea7-146">**Controlando a paginação**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-146">**Controlling paging**.</span></span> <span data-ttu-id="f4ea7-147">Para controlar a quantidade de dados exibidos em todas as páginas de relatório, é possível definir quebras de página em regiões de dados.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-147">To control the amount of data that displays on each report page, you can set page breaks on data regions.</span></span> <span data-ttu-id="f4ea7-148">Você também pode definir quebras de página em grupos.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-148">You can also set page breaks on groups.</span></span> <span data-ttu-id="f4ea7-149">As quebras de página podem afetar o desempenho da renderização sob demanda reduzindo a quantidade de dados que precisam ser processados em cada página.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-149">Page breaks can affect the on-demand rendering performance by reducing the amount of data that needs to be processed on each page.</span></span> <span data-ttu-id="f4ea7-150">Para obter mais informações, consulte [Paginação no Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) e [Adicionar uma quebra de página &#40;Construtor de Relatórios e SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-150">For more information, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) and [Add a Page Break &#40;Report Builder and SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f4ea7-151">**Exibindo dados em qualquer lado dos cabeçalhos de linha**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-151">**Displaying data on either side of row headers**.</span></span> <span data-ttu-id="f4ea7-152">Você não está limitado a exibir cabeçalhos de linha no lado de uma região de dados Tablix.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-152">You are not limited to displaying row headers on the side of a tablix data region.</span></span> <span data-ttu-id="f4ea7-153">É possível mover os cabeçalhos de linha entre colunas, para que as colunas de dados sejam exibidas antes dos cabeçalhos de linha.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-153">You can move the row headers between columns, so that columns of data appear before the row headers.</span></span> <span data-ttu-id="f4ea7-154">Para fazer isso, modifique a propriedade GroupsBeforeRowHeaders para a matriz.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-154">To do this, modify the GroupsBeforeRowHeaders property for the matrix.</span></span> <span data-ttu-id="f4ea7-155">É possível acessar essa propriedade usando a janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-155">You can access this property through the Properties window.</span></span> <span data-ttu-id="f4ea7-156">O valor dessa propriedade é um inteiro. Por exemplo, um valor igual a 2 exibirá duas instâncias de grupos dos dados de coluna da região de dados antes da exibição da coluna que contém os cabeçalhos de linha.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-156">The value for this property is an integer; for example, a value of 2 will display two groups instances of data region column data before displaying the column containing the row headers.</span></span>  
  
## <a name="controlling-how-tablix-row-and-column-groups-render"></a><span data-ttu-id="f4ea7-157">Controlando como os grupos de linhas e de colunas Tablix são processados</span><span class="sxs-lookup"><span data-stu-id="f4ea7-157">Controlling How Tablix Row and Column Groups Render</span></span>  
 <span data-ttu-id="f4ea7-158">A renderização dos grupos de regiões de dados Tablix depende da estrutura de grupo.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-158">To control how a tablix data region groups render depends on the group structure.</span></span> <span data-ttu-id="f4ea7-159">Uma região de dados Tablix pode ter quatro áreas, como mostra a figura a seguir:</span><span class="sxs-lookup"><span data-stu-id="f4ea7-159">A tablix data region can have four areas, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="f4ea7-160">![Áreas de região de dados Tablix](../media/rs-tablixareas.gif "Áreas da região de dados Tablix")</span><span class="sxs-lookup"><span data-stu-id="f4ea7-160">![Tablix data region areas](../media/rs-tablixareas.gif "Tablix data region areas")</span></span>  
  
 <span data-ttu-id="f4ea7-161">A área do grupo de linhas e a área do grupo de colunas contêm cabeçalhos de grupo.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-161">The row group area and column group area contain group headers.</span></span> <span data-ttu-id="f4ea7-162">Quando uma região de dados Tablix tem cabeçalhos de grupo, você pode controlar a repetição de linhas e colunas definindo as propriedades na página **Geral** da caixa de diálogo **Propriedades do Tablix** .</span><span class="sxs-lookup"><span data-stu-id="f4ea7-162">When a tablix data region has group headers, you control how rows and columns repeat by setting properties on the **General** page of the **Tablix Properties** dialog Box.</span></span>  
  
 <span data-ttu-id="f4ea7-163">Se uma região de dados Tablix tiver apenas uma área de corpo Tablix, não haverá nenhum cabeçalho de grupo.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-163">If a tablix data region has only a tablix body area, there are no group headers.</span></span> <span data-ttu-id="f4ea7-164">Só existem membros de tablix estáticos e dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-164">There are only static and dynamic tablix members.</span></span> <span data-ttu-id="f4ea7-165">Um membro estático é exibido uma vez em relação a um grupo de linhas ou colunas Tablix.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-165">A static member displays once in relation to a tablix row or column group.</span></span> <span data-ttu-id="f4ea7-166">Um membro dinâmico ocorre uma vez para cada valor de grupo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-166">A dynamic member repeats once for every unique group value.</span></span> <span data-ttu-id="f4ea7-167">Por exemplo, em uma região de dados Tablix que exibe um pedido de vendas, os nomes de coluna podem ser exibidos no pedido de vendas em um membro de linha estático.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-167">For example, in a tablix data region that displays a sales order, the column names in the sales order can be displayed on a static row member.</span></span> <span data-ttu-id="f4ea7-168">Cada linha do pedido de vendas é exibido em um membro de linha dinâmico.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-168">Each line in the sales order is displayed on a dynamic row member.</span></span>  
  
 <span data-ttu-id="f4ea7-169">Você pode ajudar a controlar como um membro Tablix é processado definindo propriedades no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-169">You can help control how a tablix member renders by setting properties in the Properties pane.</span></span> <span data-ttu-id="f4ea7-170">Para obter mais informações, consulte “Modo avançado” em [Painel Agrupamento &#40;Construtor de Relatórios&#41;](grouping-pane-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-170">For more information, see "Advanced mode" in [Grouping Pane &#40;Report Builder&#41;](grouping-pane-report-builder.md).</span></span>  
  
 <span data-ttu-id="f4ea7-171">A lista a seguir descreve modos que podem ajudar a controlar como uma região de dados Tablix aparece em um relatório:</span><span class="sxs-lookup"><span data-stu-id="f4ea7-171">The following list describes ways that you can help control how a tablix data region appears in a report:</span></span>  
  
-   <span data-ttu-id="f4ea7-172">**Repetindo cabeçalhos de linha e coluna em várias páginas**.É possível exibir cabeçalhos de linha e coluna em todas as páginas abrangidas em uma região de dados tablix.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-172">**Repeating row and column headers on multiple pages**.You can display row and column headers on each page that a tablix data region spans.</span></span> <span data-ttu-id="f4ea7-173">Para obter informações, consulte [Exibir cabeçalhos de linhas e colunas em várias páginas &#40;Construtor de Relatórios e SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-173">For more information, see [Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="f4ea7-174">**Mantendo cabeçalhos de linha e coluna na exibição durante a rolagem**.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-174">**Keeping row and column headers in view when scrolling**.</span></span> <span data-ttu-id="f4ea7-175">É possível controlar se você deve manter os cabeçalhos de linha e coluna na exibição ao rolar um relatório usando um navegador.</span><span class="sxs-lookup"><span data-stu-id="f4ea7-175">You can control whether to keep the row and column headers in view when you scroll a report using a browser.</span></span> <span data-ttu-id="f4ea7-176">Para obter informações, consulte [Manter os cabeçalhos visíveis ao rolar por um relatório &#40;Construtor de Relatórios e SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-176">For more information, see [Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f4ea7-177">Para obter mais informações sobre como a exportação de um relatório de formatos diferentes afeta a maneira como uma região de dados Tablix é renderizada em uma página, consulte [Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f4ea7-177">For more information about how exporting a report to different formats affects the way a tablix data region renders on a page, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ea7-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4ea7-178">See Also</span></span>  
 <span data-ttu-id="f4ea7-179">[Vinculando várias regiões de dados ao mesmo conjunto &#40;Construtor de Relatórios e SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4ea7-179">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4ea7-180">[Regiões de dados aninhadas &#40;Construtor de Relatórios e SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4ea7-180">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4ea7-181">[Escopo de expressão para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md) </span><span class="sxs-lookup"><span data-stu-id="f4ea7-181">[Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md) </span></span>  
 <span data-ttu-id="f4ea7-182">[Controlando quebras de página, cabeçalhos, colunas e linhas &#40;Construtor de Relatórios e SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4ea7-182">[Controlling Page Breaks, Headings, Columns, and Rows &#40;Report Builder and SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4ea7-183">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4ea7-183">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4ea7-184">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4ea7-184">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4ea7-185">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4ea7-185">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f4ea7-186">[Lista &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f4ea7-186">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f4ea7-187">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f4ea7-187">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  