---
title: Manter os cabeçalhos visíveis ao rolar por um relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6d9192a4-fd5c-41ad-b9ef-f88f9496afed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d37fcd38a402dc0f88ac002c679c1046d5b0b583
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684514"
---
# <a name="keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs"></a><span data-ttu-id="80a5e-102">Manter os cabeçalhos visíveis ao rolar por um relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="80a5e-102">Keep Headers Visible When Scrolling Through a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="80a5e-103">Para impedir que os rótulos de linha e coluna rolem para fora da exibição depois da renderização de um relatório, você pode congelar os títulos de linha ou coluna.</span><span class="sxs-lookup"><span data-stu-id="80a5e-103">To prevent row and column labels from scrolling out of view after rendering a report, you can freeze the row or column headings.</span></span>  
  
 <span data-ttu-id="80a5e-104">O modo de controlar as linhas e colunas depende se você tem uma tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="80a5e-104">How you control the rows and columns depends on whether you have a table or a matrix.</span></span> <span data-ttu-id="80a5e-105">Se você tiver uma tabela, configure os membros estáticos (linhas e cabeçalhos de coluna) para permanecerem visíveis.</span><span class="sxs-lookup"><span data-stu-id="80a5e-105">If you have a table, you configure static members (row and column headings) to remain visible.</span></span> <span data-ttu-id="80a5e-106">Se você tiver uma matriz, configure as linhas e cabeçalhos de grupos de coluna para permanecerem visíveis.</span><span class="sxs-lookup"><span data-stu-id="80a5e-106">If you have a matrix, you configure row and column group headers to remain visible.</span></span>  
  
 <span data-ttu-id="80a5e-107">Se você exportar o relatório para Excel, o cabeçalho não será congelado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="80a5e-107">If you export the report to Excel, the header will not be frozen automatically.</span></span> <span data-ttu-id="80a5e-108">Você pode congelar o painel no Excel.</span><span class="sxs-lookup"><span data-stu-id="80a5e-108">You can freeze the pane in Excel.</span></span> <span data-ttu-id="80a5e-109">Para obter mais informações, consulte a seção **Cabeçalhos e rodapés de página** de [Exportando para o Microsoft Excel &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="80a5e-109">For more information see the **Page Headers and Footers** section of [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80a5e-110">Mesmo se uma tabela tiver grupos de linhas e de coluna, você não conseguirá manter esses cabeçalhos de grupo visíveis durante a rolagem</span><span class="sxs-lookup"><span data-stu-id="80a5e-110">Even if a table has row and column groups, you cannot keep those group headers visible while scrolling</span></span>  
  
 <span data-ttu-id="80a5e-111">A imagem a seguir mostra uma tabela.</span><span class="sxs-lookup"><span data-stu-id="80a5e-111">The following image shows a table.</span></span>  
  
 <span data-ttu-id="80a5e-112">![Table](../media/table.png "Tabela")</span><span class="sxs-lookup"><span data-stu-id="80a5e-112">![Table](../media/table.png "Table")</span></span>  
  
 <span data-ttu-id="80a5e-113">A imagem a seguir mostra uma matriz.</span><span class="sxs-lookup"><span data-stu-id="80a5e-113">The following image shows a matrix.</span></span>  
  
 <span data-ttu-id="80a5e-114">![Matriz](../media/matrix.png "Matriz")</span><span class="sxs-lookup"><span data-stu-id="80a5e-114">![Matrix](../media/matrix.png "Matrix")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-keep-matrix-group-headers-visible-while-scrolling"></a><span data-ttu-id="80a5e-115">Para manter os cabeçalhos de grupo de matriz visíveis ao rolar</span><span class="sxs-lookup"><span data-stu-id="80a5e-115">To keep matrix group headers visible while scrolling</span></span>  
  
1.  <span data-ttu-id="80a5e-116">Clique com o botão direito do mouse na alça de canto, na linha ou na coluna de uma região de dados tablix e, em seguida, clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="80a5e-116">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="80a5e-117">Na guia **Geral** , em **Cabeçalhos de Linha** ou **Cabeçalhos de Coluna**, selecione **O cabeçalho deve permanecer visível ao rolar**.</span><span class="sxs-lookup"><span data-stu-id="80a5e-117">On the **General** tab, under **Row Headers** or **Column Headers**, select **Header should remain visible while scrolling**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-keep-a-static-tablix-member-row-or-column-visible-while-scrolling"></a><span data-ttu-id="80a5e-118">Para manter um membro tablix estático (linha ou coluna) visível ao rolar</span><span class="sxs-lookup"><span data-stu-id="80a5e-118">To keep a static tablix member (row or column) visible while scrolling</span></span>  
  
1.  <span data-ttu-id="80a5e-119">Na superfície de design, clique em qualquer lugar na tabela para exibir membros estáticos, bem como grupos, no painel de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="80a5e-119">On the design surface, click anywhere in the table to display static members, as well as groups, in the grouping pane.</span></span>  
  
     <span data-ttu-id="80a5e-120">![Painel de agrupamento](../media/grouppane-updated.png "Painel de agrupamento")</span><span class="sxs-lookup"><span data-stu-id="80a5e-120">![Grouping pane](../media/grouppane-updated.png "Grouping pane")</span></span>  
  
     <span data-ttu-id="80a5e-121">O painel Grupos de Linhas exibe os membros hierárquicos estáticos e dinâmicos para a hierarquia de grupos de linhas, e o painel Grupos de colunas mostra uma exibição semelhante para a hierarquia de grupos de coluna.</span><span class="sxs-lookup"><span data-stu-id="80a5e-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy, and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
2.  <span data-ttu-id="80a5e-122">À direita do painel de agrupamento, clique na seta para baixo e, em seguida, clique em **Modo Avançado**.</span><span class="sxs-lookup"><span data-stu-id="80a5e-122">On the right side of the grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span>  
  
3.  <span data-ttu-id="80a5e-123">Clique no membro estático (linha ou coluna) que deverá permanecer visível durante a rolagem.</span><span class="sxs-lookup"><span data-stu-id="80a5e-123">Click the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="80a5e-124">O painel Propriedades exibe as propriedades de **Membro de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="80a5e-124">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="80a5e-125">![Propriedades do membro Tablix](../media/grouppane-tablixmember-updated.png "Propriedades do membro Tablix")</span><span class="sxs-lookup"><span data-stu-id="80a5e-125">![Tablix Member properties](../media/grouppane-tablixmember-updated.png "Tablix Member properties")</span></span>  
  
4.  <span data-ttu-id="80a5e-126">No painel Propriedades, defina **FixedData** como `True` .</span><span class="sxs-lookup"><span data-stu-id="80a5e-126">In the Properties pane, set **FixedData** to `True`.</span></span>  
  
5.  <span data-ttu-id="80a5e-127">Repita essa etapa para todos os membros adjacentes que você deseja manter visíveis durante a rolagem.</span><span class="sxs-lookup"><span data-stu-id="80a5e-127">Repeat this for as many adjacent members as you want to keep visible while scrolling.</span></span>  
  
6.  <span data-ttu-id="80a5e-128">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="80a5e-128">Preview the report.</span></span>  
  
 <span data-ttu-id="80a5e-129">À medida que você pagina para baixo ou pelo relatório, os membros tablix estáticos permanecem na exibição.</span><span class="sxs-lookup"><span data-stu-id="80a5e-129">As you page down or across the report, the static tablix members remain in view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a5e-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="80a5e-130">See Also</span></span>  
 <span data-ttu-id="80a5e-131">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80a5e-131">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="80a5e-132">[Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80a5e-132">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="80a5e-133">[Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80a5e-133">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="80a5e-134">[Exibir cabeçalhos e rodapés com um grupo &#40;Construtor de Relatórios e SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80a5e-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="80a5e-135">[Exibir cabeçalhos de linhas e colunas em várias páginas &#40;Construtor de Relatórios e SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="80a5e-135">[Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="80a5e-136">Painel Agrupamento &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="80a5e-136">Grouping Pane &#40;Report Builder&#41;</span></span>](grouping-pane-report-builder.md)  
  
  
