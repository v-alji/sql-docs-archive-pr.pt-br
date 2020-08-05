---
title: Adicionar uma quebra de página (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3846cd48-2787-47e9-b13b-7fc45a205f68
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 55d6be3ae47827c5a8ff4a5b36e3ff2ce80e1034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569099"
---
# <a name="add-a-page-break-report-builder-and-ssrs"></a><span data-ttu-id="4708d-102">Adicionar uma quebra de página (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="4708d-102">Add a Page Break (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4708d-103">É possível adicionar uma quebra de página a retângulos, regiões de dados ou grupos dentro das regiões de dados para controlar a quantidade de informações em cada página.</span><span class="sxs-lookup"><span data-stu-id="4708d-103">You can add a page break to rectangles, data regions, or groups within data regions to control the amount of information on each page.</span></span> <span data-ttu-id="4708d-104">A adição de quebras de página pode melhorar o desempenho de relatórios publicados porque apenas os itens em cada página precisam ser processados conforme o relatório é exibido.</span><span class="sxs-lookup"><span data-stu-id="4708d-104">Adding page breaks can improve the performance of published reports because only the items on each page have to be processed as you view the report.</span></span> <span data-ttu-id="4708d-105">Quando todo o relatório ocupa uma única página, todos os itens devem ser processados antes de o relatório ser exibido.</span><span class="sxs-lookup"><span data-stu-id="4708d-105">When the whole report is a single page, all items must be processed before you can view the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-break-to-a-data-region"></a><span data-ttu-id="4708d-106">Para adicionar uma quebra de página a uma região de dados</span><span class="sxs-lookup"><span data-stu-id="4708d-106">To add a page break to a data region</span></span>  
  
1.  <span data-ttu-id="4708d-107">Na superfície de design, clique com o botão direito do mouse na alça de canto da região de dados e clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="4708d-107">On the design surface, right-click the corner handle of the data region and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="4708d-108">Na guia **Geral** , em **Opções de quebra de página**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4708d-108">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="4708d-109">**Adicionar uma quebra de página antes**.</span><span class="sxs-lookup"><span data-stu-id="4708d-109">**Add a page break before**.</span></span> <span data-ttu-id="4708d-110">Selecione essa opção para adicionar uma quebra de página antes da tabela.</span><span class="sxs-lookup"><span data-stu-id="4708d-110">Select this option when you want to add a page break before the table.</span></span>  
  
    -   <span data-ttu-id="4708d-111">**Adicionar uma quebra de página após**.</span><span class="sxs-lookup"><span data-stu-id="4708d-111">**Add a page break after**.</span></span> <span data-ttu-id="4708d-112">Selecione essa opção para adicionar uma quebra de página após a tabela.</span><span class="sxs-lookup"><span data-stu-id="4708d-112">Select this option when you want to add a page break after the table.</span></span>  
  
    -   <span data-ttu-id="4708d-113">**Ajustar a tabela em uma página, se possível**.</span><span class="sxs-lookup"><span data-stu-id="4708d-113">**Fit table on one page if possible**.</span></span> <span data-ttu-id="4708d-114">Selecione essa opção para que os dados permaneçam em uma única página.</span><span class="sxs-lookup"><span data-stu-id="4708d-114">Select this option when you want the data to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-rectangle"></a><span data-ttu-id="4708d-115">Para adicionar uma quebra de página a um retângulo</span><span class="sxs-lookup"><span data-stu-id="4708d-115">To add a page break to a rectangle</span></span>  
  
1.  <span data-ttu-id="4708d-116">Na superfície de design, clique com o botão direito do mouse no retângulo em que quer adicionar uma quebra de página e clique em **Propriedades do Retângulo**.</span><span class="sxs-lookup"><span data-stu-id="4708d-116">On the design surface, right-click the rectangle where you want to add a page break, and then click **Rectangle Properties**.</span></span>  
  
2.  <span data-ttu-id="4708d-117">Na guia **Geral** , em **Opções de quebra de página**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4708d-117">On the **General** tab, under **Page break options**, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="4708d-118">**Adicionar uma quebra de página antes**.</span><span class="sxs-lookup"><span data-stu-id="4708d-118">**Add a page break before**.</span></span> <span data-ttu-id="4708d-119">Selecione essa opção para adicionar uma quebra de página antes do retângulo.</span><span class="sxs-lookup"><span data-stu-id="4708d-119">Select this option when you want to add a page break before the rectangle.</span></span>  
  
    -   <span data-ttu-id="4708d-120">**Adicionar uma quebra de página após**.</span><span class="sxs-lookup"><span data-stu-id="4708d-120">**Add a page break after**.</span></span> <span data-ttu-id="4708d-121">Selecione essa opção para adicionar uma quebra de página após o retângulo.</span><span class="sxs-lookup"><span data-stu-id="4708d-121">Select this option when you want to add a page break after the rectangle.</span></span>  
  
    -   <span data-ttu-id="4708d-122">**Omitir borda na quebra de página**.</span><span class="sxs-lookup"><span data-stu-id="4708d-122">**Omit border on page break**.</span></span> <span data-ttu-id="4708d-123">Selecione essa opção quando não desejar uma borda na quebra de página.</span><span class="sxs-lookup"><span data-stu-id="4708d-123">Select this option when you do not want a border on the page break.</span></span>  
  
    -   <span data-ttu-id="4708d-124">**Manter o conteúdo em uma única página, se possível**.</span><span class="sxs-lookup"><span data-stu-id="4708d-124">**Keep contents together on a single page, if possible**.</span></span> <span data-ttu-id="4708d-125">Selecione essa opção quando desejar que o conteúdo dentro do retângulo permaneça em uma única página.</span><span class="sxs-lookup"><span data-stu-id="4708d-125">Select this option when you want contents inside the rectangle to stay on one page.</span></span>  
  
### <a name="to-add-a-page-break-to-a-row-group-in-a-table-matrix-or-list"></a><span data-ttu-id="4708d-126">Para adicionar uma quebra de página a um grupo de linhas de uma tabela, matriz ou lista</span><span class="sxs-lookup"><span data-stu-id="4708d-126">To add a page break to a row group in a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="4708d-127">No painel Agrupamento, clique com o botão direito do mouse no grupo de linhas e clique em **Propriedades do Grupo**.</span><span class="sxs-lookup"><span data-stu-id="4708d-127">In the Grouping pane, right-click a row group, and then click **Group Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4708d-128">Quebras de página em grupos de colunas são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="4708d-128">Page breaks are ignored on column groups.</span></span>  
  
2.  <span data-ttu-id="4708d-129">Na guia **Quebras de Página** , selecione **Entre cada instância de um grupo** para adicionar uma quebra de página entre cada instância de um grupo na tabela.</span><span class="sxs-lookup"><span data-stu-id="4708d-129">On the **Page Breaks** tab, select **Between each instance of a group** to add a page break between each instance of a group in the table.</span></span>  
  
3.  <span data-ttu-id="4708d-130">Opcionalmente, selecione **Também no início de um grupo** ou **Também no fim de um grupo** para especificar que uma quebra de página seja adicionada quando um grupo for iniciado ou finalizado na tabela.</span><span class="sxs-lookup"><span data-stu-id="4708d-130">Optionally, select **Also at the start of a group** or **Also at the end of a group** to specify that a page break be added when a group starts or ends in the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4708d-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4708d-131">See Also</span></span>  
 <span data-ttu-id="4708d-132">[Paginação no Reporting Services &#40;Construtor de Relatórios e SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4708d-132">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4708d-133">[Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4708d-133">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4708d-134">Cabeçalhos e rodapés de página &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4708d-134">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
