---
title: Ação de busca detalhada (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10249"
- "10186"
- sql12.rtp.rptdesigner.calculatedseriesproperties.visibility.f1
- sql12.rtp.rptdesigner.seriesproperties.visibility.f1
- sql12.rtp.rptdesigner.chartareaproperties.visibility.f1
- "10092"
- sql12.rtp.rptdesigner.textboxproperties.visibility.f1
- sql12.rtp.rptdesigner.charttitleproperties.visibility.f1
- "10167"
- sql12.rtp.rptdesigner.rectangleproperties.visibility.f1
- "10174"
- sql12.rtp.rptdesigner.majorgridlineproperties.visibility.f1
- "10155"
- "10123"
- sql12.rtp.rptdesigner.subreportproperties.visibility.f1
- "10425"
- sql12.rtp.rptdesigner.minorgridlineproperties.visibility.f1
- "10217"
- sql12.rtp.rptdesigner.axisproperties.visibility.f1
- sql12.rtp.rptdesigner.serieslabelproperties.visibility.f1
- "10161"
- sql12.rtp.rptdesigner.chartproperties.visibility.f1
- sql12.rtp.rptdesigner.legendproperties.visibility.f1
- sql12.rtp.rptdesigner.pictureproperties.visibility.f1
- "10215"
- "10258"
- "10144"
- "10062"
- "10053"
ms.assetid: 1f8d1ef2-0daf-40c6-9ba7-3b391249bcd4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fe3d55dc70a606df759c049b7b147820f0e3110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582303"
---
# <a name="drilldown-action-report-builder-and-ssrs"></a><span data-ttu-id="7827f-102">Ação de análise detalhada (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="7827f-102">Drilldown Action (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7827f-103">Ao fornecer ícones de sinal de adição ou de subtração em uma caixa de texto, você permitirá que os usuários ocultem ou exibam itens interativamente.</span><span class="sxs-lookup"><span data-stu-id="7827f-103">B providing plus and minus icons on a text box, you can enable users to hide and display items interactively.</span></span> <span data-ttu-id="7827f-104">Isso se chama *busca detalhada* .</span><span class="sxs-lookup"><span data-stu-id="7827f-104">This is called a *drilldown* action.</span></span> <span data-ttu-id="7827f-105">Para uma tabela ou matriz, você pode mostrar ou ocultar linhas e colunas estáticas ou linhas e colunas que estão associadas a grupos.</span><span class="sxs-lookup"><span data-stu-id="7827f-105">For a table or matrix, you can show or hide static rows and columns, or rows and columns that are associated with groups.</span></span>  
  
 <span data-ttu-id="7827f-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span><span class="sxs-lookup"><span data-stu-id="7827f-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span></span>  
  
 <span data-ttu-id="7827f-107">Nesta ilustração, o usuário clica nos sinais de adição (+) no relatório para mostrar dados detalhados.</span><span class="sxs-lookup"><span data-stu-id="7827f-107">In this illustration, the user clicks the plus signs (+) in the report to show detail data.</span></span>  
  
 <span data-ttu-id="7827f-108">Por exemplo, você pode ocultar inicialmente todas as linhas, exceto a linha de resumo do grupo externo de uma tabela com grupos de linhas.</span><span class="sxs-lookup"><span data-stu-id="7827f-108">For example, you can initially hide all the rows except the outer group summary row for a table with row groups.</span></span> <span data-ttu-id="7827f-109">Para cada grupo interno (inclusive os grupo de detalhes), adicione um ícone de expandir/recolher à célula de agrupamento do grupo contentor.</span><span class="sxs-lookup"><span data-stu-id="7827f-109">For each inner group (including the details group), add an expand/collapse icon to the grouping cell of the containing group.</span></span> <span data-ttu-id="7827f-110">Quando o relatório for renderizado, o usuário poderá clicar na caixa de texto para expandir e recolher os dados de detalhes.</span><span class="sxs-lookup"><span data-stu-id="7827f-110">When the report is rendered, the user can click the text box to expand and collapse the detail data.</span></span> <span data-ttu-id="7827f-111">Para obter mais informações, consulte [Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7827f-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="7827f-112">Para permitir que os usuários expandam ou recolham um item, defina as propriedades de visibilidade do item.</span><span class="sxs-lookup"><span data-stu-id="7827f-112">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7827f-113">Quando você cria um relatório com uma ação de busca detalhada, as informações de visibilidade devem ser definidas no grupo, na coluna ou na linha que você deseja ocultar, não apenas uma única caixa de texto na linha ou coluna.</span><span class="sxs-lookup"><span data-stu-id="7827f-113">When you create a report with a drilldown action, the visibility information must be set on the group, column, or row that you want to hide, not just a single text box in the row or column.</span></span> <span data-ttu-id="7827f-114">Além disso, a caixa de texto que você usa para alternância deve estar em um escopo de contenção que controle o item que você deseja mostrar ou ocultar.</span><span class="sxs-lookup"><span data-stu-id="7827f-114">In addition, the text box that you use for the toggle must be in a containing scope that controls the item that you want to show or hide.</span></span>  
>   
>  <span data-ttu-id="7827f-115">Por exemplo, para ocultar uma linha associada a um grupo aninhado, a caixa de texto deve estar em uma linha associada ao grupo pai ou superior na hierarquia de contenção.</span><span class="sxs-lookup"><span data-stu-id="7827f-115">For example, to hide a row associated with a nested group, the text box must be in a row associated with the parent group or higher in the containment hierarchy.</span></span>  
>   
>  <span data-ttu-id="7827f-116">Para obter informações sobre como definir informações de visibilidade no grupo, na coluna ou na linha, consulte [Adicionar uma ação de expandir/recolher a um item &#40;Construtor de Relatórios e SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="7827f-116">For information on setting visibility information on the group, column or row, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="7827f-117">Para obter mais informações sobre como ocultar itens de relatório, consulte [Ocultar um item &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7827f-117">For more information about hiding report items, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="comparing-drilldown-and-drillthrough-reports"></a><span data-ttu-id="7827f-118">Comparando relatórios de busca detalhada com relatórios detalhados</span><span class="sxs-lookup"><span data-stu-id="7827f-118">Comparing Drilldown and Drillthrough Reports</span></span>  
 <span data-ttu-id="7827f-119">Em um relatório de busca detalhada, um usuário clica em um botão de adição ou subtração para expandir ou recolher uma seção de um relatório para mostrar dados detalhados no local.</span><span class="sxs-lookup"><span data-stu-id="7827f-119">In a drilldown report, a user clicks a plus or minus button to expand or collapse a section of a report to show detail data in place.</span></span> <span data-ttu-id="7827f-120">Em um relatório detalhado, o usuário clica em um link para um valor resumido e isso abre um relatório relacionado separado para mostrar dados de detalhes.</span><span class="sxs-lookup"><span data-stu-id="7827f-120">In a drillthrough report, the user clicks a link for a summary value, and this opens a separate, related report to show detail data.</span></span> <span data-ttu-id="7827f-121">Os dados de detalhes só são recuperados quando o relatório de detalhes é executado.</span><span class="sxs-lookup"><span data-stu-id="7827f-121">The detail data is only retrieved when the detail report runs.</span></span> <span data-ttu-id="7827f-122">Normalmente, os relatórios detalhados exigem menos recursos do que os relatórios de busca detalhada.</span><span class="sxs-lookup"><span data-stu-id="7827f-122">Drillthrough reports typically require fewer resources than drilldown reports.</span></span> <span data-ttu-id="7827f-123">Para obter mais informações, consulte [Detalhamento, busca detalhada, sub-relatórios e regiões de dados aninhadas &#40;Construtor de Relatórios e SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span><span class="sxs-lookup"><span data-stu-id="7827f-123">For more information, see [Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span></span>  
  
## <a name="rendering-extension-support-for-hidden-report-items"></a><span data-ttu-id="7827f-124">Suporte à extensão de renderização para itens de relatório ocultos</span><span class="sxs-lookup"><span data-stu-id="7827f-124">Rendering Extension Support for Hidden Report Items</span></span>  
 <span data-ttu-id="7827f-125">Só há suporte para a alternância de mostrar e ocultar itens de relatório por extensões de renderização que dão suporte à interatividade de usuário, como a extensão de renderização HTML usada quando você executa um relatório no Construtor de Relatórios e no Gerenciador de Relatórios, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="7827f-125">The show-and-hide toggle on report items is supported only by rendering extensions that support user interactivity, such as the HTML rendering extension that is used when you run a report in Report Builder and in Report Manager, for example.</span></span> <span data-ttu-id="7827f-126">Outras extensões de renderização exibem itens ocultos.</span><span class="sxs-lookup"><span data-stu-id="7827f-126">Other rendering extensions display hidden items.</span></span> <span data-ttu-id="7827f-127">A lista a seguir descreve suporte para itens de relatório com visibilidade condicional:</span><span class="sxs-lookup"><span data-stu-id="7827f-127">The following list describes support for report items with conditional visibility:</span></span>  
  
-   <span data-ttu-id="7827f-128">Em HTML, se os itens estiverem ocultos, eles não serão visíveis no código-fonte HTML.</span><span class="sxs-lookup"><span data-stu-id="7827f-128">In HTML, if items are hidden, they are not visible in the HTML source.</span></span>  
  
-   <span data-ttu-id="7827f-129">A extensão de renderização XML exibe todos os itens do relatório, quer eles estejam ocultos ou não.</span><span class="sxs-lookup"><span data-stu-id="7827f-129">The XML rendering extension displays all report items, regardless of whether they are hidden.</span></span>  
  
-   <span data-ttu-id="7827f-130">A extensão de renderização do Excel exibe e expande linhas e colunas ocultas de uma tabela, matriz ou lista.</span><span class="sxs-lookup"><span data-stu-id="7827f-130">The Excel rendering extension displays and expands hidden rows and columns for a table, matrix, or list.</span></span> <span data-ttu-id="7827f-131">Todas as linhas e colunas são visíveis.</span><span class="sxs-lookup"><span data-stu-id="7827f-131">All rows and columns are visible.</span></span>  
  
 <span data-ttu-id="7827f-132">Para obter mais informações, consulte [Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7827f-132">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7827f-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7827f-133">See Also</span></span>  
 <span data-ttu-id="7827f-134">[Detalhamento, busca detalhada, sub-relatórios e regiões de dados aninhadas &#40;Construtor de Relatórios e SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span><span class="sxs-lookup"><span data-stu-id="7827f-134">[Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span></span>  
 <span data-ttu-id="7827f-135">[Classificação interativa, mapas de documentos e links &#40;Construtor de Relatórios e SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7827f-135">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7827f-136">Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7827f-136">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
