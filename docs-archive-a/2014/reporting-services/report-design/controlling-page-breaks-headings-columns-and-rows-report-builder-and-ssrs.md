---
title: Controlando quebras de página, cabeçalhos, colunas e linhas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b8fa41f-a727-4f23-8efb-fd9bb0d4cd1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7dae06129ee5dc9962538e8d025dca9966325f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576213"
---
# <a name="controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs"></a><span data-ttu-id="e882b-102">Controlando quebras de páginas, títulos, colunas e linhas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e882b-102">Controlling Page Breaks, Headings, Columns, and Rows (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e882b-103">Uma quebra de página divide um relatório em páginas separadas para exibição e impressão.</span><span class="sxs-lookup"><span data-stu-id="e882b-103">A page break divides a report into separate pages for viewing and printing.</span></span> <span data-ttu-id="e882b-104">As quebras de página determinam como o conteúdo é colocado em uma página de relatório para visualização ideal quando você visualiza um relatório ou exporta-o para outro formato de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e882b-104">Page breaks determine how the content is fitted to a report page for optimal viewing when you preview a report or export it to a different file format.</span></span>  
  
 <span data-ttu-id="e882b-105">A adição de quebras de páginas também melhora o desempenho de relatórios grandes durante seu processamento.</span><span class="sxs-lookup"><span data-stu-id="e882b-105">Adding page breaks also improves the performance of large reports when the are processed.</span></span> <span data-ttu-id="e882b-106">Uma página renderizada é exibida enquanto as páginas restantes são processadas em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e882b-106">A rendered page is displayed while the rest of the pages are rendered in the background.</span></span> <span data-ttu-id="e882b-107">Isso permite que você inicie a exibição das páginas iniciais do relatório enquanto aguarda a disponibilização das restantes.</span><span class="sxs-lookup"><span data-stu-id="e882b-107">This allows you to begin viewing the initial pages of the report while waiting for additional pages to become available.</span></span>  
  
 <span data-ttu-id="e882b-108">É possível adicioná-las a itens de relatório como uma tabela, matriz, lista, gráfico, medidor ou imagem.</span><span class="sxs-lookup"><span data-stu-id="e882b-108">Page breaks can be added to report items such as a table, matrix, list, chart, gauge, or image.</span></span> <span data-ttu-id="e882b-109">Também é possível adicionar quebras de página a grupos em uma tabela, matriz ou lista.</span><span class="sxs-lookup"><span data-stu-id="e882b-109">You can also add page breaks to groups in a table, matrix, or list.</span></span> <span data-ttu-id="e882b-110">As quebras de página podem somente ser adicionadas antes, após e entre os grupos.</span><span class="sxs-lookup"><span data-stu-id="e882b-110">Page breaks can be added before, after, and between groups.</span></span> <span data-ttu-id="e882b-111">As quebras de página entre grupos não são adicionadas ao relatório por padrão.</span><span class="sxs-lookup"><span data-stu-id="e882b-111">Page breaks between groups are not added to the report by default.</span></span>  
  
 <span data-ttu-id="e882b-112">Para obter mais informações, consulte [Exibir cabeçalhos de linhas e colunas em várias páginas &#40;Construtor de Relatórios e SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) e [Manter os cabeçalhos visíveis ao rolar por um relatório &#40;Construtor de Relatórios e SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e882b-112">For more information, see [Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) and [Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e882b-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e882b-113">See Also</span></span>  
 <span data-ttu-id="e882b-114">[Lista &#40;Construtor de Relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e882b-114">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e882b-115">[Controlando a exibição da região de dados Tablix em uma página de relatório &#40;Construtor de Relatórios e SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span><span class="sxs-lookup"><span data-stu-id="e882b-115">[Controlling the Tablix Data Region Display on a Report Page &#40;Report Builder and SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span></span>  
 <span data-ttu-id="e882b-116">[Painel Agrupamento &#40;Construtor de Relatórios&#41;](grouping-pane-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="e882b-116">[Grouping Pane &#40;Report Builder&#41;](grouping-pane-report-builder.md) </span></span>  
 [<span data-ttu-id="e882b-117">Exibir cabeçalhos e rodapés com um grupo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e882b-117">Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;</span></span>](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md)  
  
  
