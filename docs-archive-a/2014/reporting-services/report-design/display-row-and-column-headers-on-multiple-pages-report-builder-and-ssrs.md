---
title: Exibir cabeçalhos de linhas e colunas em várias páginas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2422b1e2-822f-4379-9d7f-9afebb350e3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e3b38aa0faab267a0cd71feafe600829237b55c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683427"
---
# <a name="display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs"></a><span data-ttu-id="e0002-102">Exibir cabeçalhos de linhas e colunas em várias páginas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e0002-102">Display Row and Column Headers on Multiple Pages (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e0002-103">Você pode controlar se é preciso repetir cabeçalhos de linha e coluna em todas as páginas de uma região de dados tablix com várias páginas.</span><span class="sxs-lookup"><span data-stu-id="e0002-103">You can control whether to repeat row and column headers on every page for a tablix data region that spans multiple pages.</span></span> <span data-ttu-id="e0002-104">Uma região de dados tablix pode ser uma tabela, uma matriz ou uma lista.</span><span class="sxs-lookup"><span data-stu-id="e0002-104">A tablix data region can be a table, matrix, or list.</span></span>  
  
 <span data-ttu-id="e0002-105">O modo como você controla as linhas e as colunas dependerá se a região de dados de tablix tem cabeçalhos de grupo.</span><span class="sxs-lookup"><span data-stu-id="e0002-105">How you control the rows and columns depends on whether the tablix data region has group headers.</span></span> <span data-ttu-id="e0002-106">Quando você clicar em uma região de dados de tablix que tem cabeçalhos de grupo, uma linha pontilhada mostrará as áreas de tablix, como mostrado na figura seguinte:</span><span class="sxs-lookup"><span data-stu-id="e0002-106">When you click in a tablix data region that has group headers, a dotted line shows the tablix areas, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="e0002-107">![Áreas da região de dados Tablix](../media/rs-tablixareas.gif "Áreas da região de dados Tablix")</span><span class="sxs-lookup"><span data-stu-id="e0002-107">![Tablix data region areas](../media/rs-tablixareas.gif "Tablix data region areas")</span></span>  
  
 <span data-ttu-id="e0002-108">Cabeçalhos de grupos de linhas e colunas são criados automaticamente quando você adiciona grupos usando o assistente de Nova Tabela ou de Novo Gráfico, adicionando campos ao painel Agrupamento ou usando menus de contexto.</span><span class="sxs-lookup"><span data-stu-id="e0002-108">Row and column group headers are created automatically when you add groups by using the New Table or Matrix wizard or the New Chart wizard, by adding fields to the Grouping pane, or by using context menus.</span></span> <span data-ttu-id="e0002-109">Se a região de dados de tablix tiver apenas uma área de corpo de tablix e nenhum cabeçalho de grupo, as linhas e as colunas serão os membros do tablix.</span><span class="sxs-lookup"><span data-stu-id="e0002-109">If the tablix data region has only a tablix body area and no group headers, the rows and columns are tablix members.</span></span>  
  
 <span data-ttu-id="e0002-110">Para membros estáticos, você pode exibir as linhas adjacentes superiores ou as colunas adjacentes em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="e0002-110">For static members, you can display the top adjacent rows or the side adjacent columns on multiple pages.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-row-headers-on-multiple-pages"></a><span data-ttu-id="e0002-111">Para exibir cabeçalhos de linha em várias páginas</span><span class="sxs-lookup"><span data-stu-id="e0002-111">To display row headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="e0002-112">Clique com o botão direito do mouse na alça de canto, na linha ou na coluna de uma região de dados tablix e, em seguida, clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="e0002-112">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="e0002-113">Em **Cabeçalhos de Linha**, selecione **Repetir linhas de cabeçalho em cada página**.</span><span class="sxs-lookup"><span data-stu-id="e0002-113">In **Row Headers**, select **Repeat header rows on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-column-headers-on-multiple-pages"></a><span data-ttu-id="e0002-114">Para exibir cabeçalhos de coluna em várias páginas</span><span class="sxs-lookup"><span data-stu-id="e0002-114">To display column headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="e0002-115">Clique com o botão direito do mouse na alça de canto, na linha ou na coluna de uma região de dados tablix e, em seguida, clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="e0002-115">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="e0002-116">Em **Cabeçalhos de Colunas**, selecione **Repetir colunas de cabeçalho em cada página**.</span><span class="sxs-lookup"><span data-stu-id="e0002-116">In **Column Headers**, select **Repeat header columns on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-a-static-tablix-member-row-or-column-on-multiple-pages"></a><span data-ttu-id="e0002-117">Para exibir um membro de tablix estático (linha ou coluna) em várias páginas</span><span class="sxs-lookup"><span data-stu-id="e0002-117">To display a static tablix member (row or column) on multiple pages</span></span>  
  
1.  <span data-ttu-id="e0002-118">Na superfície de design, clique no manipulador de linha ou coluna da região de dados de tablix para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="e0002-118">On the design surface, click the row or column handle of the tablix data region to select it.</span></span> <span data-ttu-id="e0002-119">O painel Agrupamento exibe os grupos de linhas e colunas.</span><span class="sxs-lookup"><span data-stu-id="e0002-119">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="e0002-120">À direita lado do painel Agrupamento, clique na seta para baixo e, em seguida, clique em **Modo Avançado**.</span><span class="sxs-lookup"><span data-stu-id="e0002-120">On the right side of the Grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span> <span data-ttu-id="e0002-121">O painel Grupos de Linhas exibe os membros hierárquicos estáticos e dinâmicos para a hierarquia de grupos de linhas e o painel Grupos de colunas mostra uma exibição semelhante para a hierarquia de grupos de coluna.</span><span class="sxs-lookup"><span data-stu-id="e0002-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
3.  <span data-ttu-id="e0002-122">Clique no membro estático que corresponde àquele (linha ou coluna) que deverá permanecer visível durante a rolagem.</span><span class="sxs-lookup"><span data-stu-id="e0002-122">Click the static member that corresponds to the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="e0002-123">O painel Propriedades exibe as propriedades de **Membro de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="e0002-123">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="e0002-124">Se você não vir o painel Propriedades, clique na guia **Exibir** na parte superior da janela do Construtor de Relatórios e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e0002-124">If you don't see the Properties pane, click the **View** tab at the top of the Report Builder window and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="e0002-125">No painel Propriedades, defina **RepeatOnNewPage** como True.</span><span class="sxs-lookup"><span data-stu-id="e0002-125">In the Properties pane, set **RepeatOnNewPage** to True.</span></span>  
  
5.  <span data-ttu-id="e0002-126">Defina **KeepWithGroup** como After.</span><span class="sxs-lookup"><span data-stu-id="e0002-126">Set **KeepWithGroup** to After.</span></span>  
  
6.  <span data-ttu-id="e0002-127">Repita essa etapa para todos os membros adjacentes desejados.</span><span class="sxs-lookup"><span data-stu-id="e0002-127">Repeat this for as many adjacent members as you want to repeat.</span></span>  
  
7.  <span data-ttu-id="e0002-128">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="e0002-128">Preview the report.</span></span>  
  
 <span data-ttu-id="e0002-129">À medida que você exibe cada página do relatório que a região de dados do tablix abrange, os membros de tablix se repetem em cada página.</span><span class="sxs-lookup"><span data-stu-id="e0002-129">As you view each page of the report that the tablix data region spans, the static tablix members repeat on each page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0002-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e0002-130">See Also</span></span>  
 <span data-ttu-id="e0002-131">[Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e0002-131">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e0002-132">[Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e0002-132">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e0002-133">[Controlando quebras de páginas, títulos, colunas e linhas &#40;Construtor de Relatórios e SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e0002-133">[Controlling Page Breaks, Headings, Columns, and Rows &#40;Report Builder and SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e0002-134">[Exibir cabeçalhos e rodapés com um grupo &#40;Construtor de Relatórios e SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e0002-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e0002-135">Manter os cabeçalhos visíveis ao rolar por um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e0002-135">Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;</span></span>](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)  
  
  
