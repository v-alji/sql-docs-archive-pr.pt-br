---
title: Classificação interativa, mapas do documento e links (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cc6ef408-4a76-408a-9d3f-033481fe21cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35d88e89ed14a205153374d44562e6d3fda92e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684519"
---
# <a name="interactive-sort-document-maps-and-links-report-builder-and-ssrs"></a><span data-ttu-id="f718f-102">Classificação interativa, mapas de documentos e links (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f718f-102">Interactive Sort, Document Maps, and Links (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f718f-103">Em ambientes baseados na Web, você pode adicionar alguns recursos que permitem aos usuários interagir com relatórios.</span><span class="sxs-lookup"><span data-stu-id="f718f-103">In Web-based environments, you can add a number of features that let your users interact with reports.</span></span> <span data-ttu-id="f718f-104">Seus usuários podem alterar a ordem de classificação de valores no relatório, mostrar ou ocultar itens no relatório ou clicar em links que vão para outros relatórios ou páginas da Web.</span><span class="sxs-lookup"><span data-stu-id="f718f-104">Your users can change the sort order of values in your report, show or hide items in the report, or click links that go to other reports or Web pages.</span></span> <span data-ttu-id="f718f-105">Você também pode adicionar um índice ou um mapa do documento.</span><span class="sxs-lookup"><span data-stu-id="f718f-105">You can also add a table of contents or document map.</span></span> <span data-ttu-id="f718f-106">Seus usuários de relatório podem clicar em itens do sumário ou do mapa do documento e ir diretamente para áreas de um relatório.</span><span class="sxs-lookup"><span data-stu-id="f718f-106">Your report users can click items in the table of contents or document map to jump to areas within a report.</span></span>  
  
 <span data-ttu-id="f718f-107">O Construtor de Relatórios e o Designer de Relatórios dão suporte a três tipos de links com as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="f718f-107">Report Builder and Report Designer support three types of links with the following actions:</span></span>  
  
-   <span data-ttu-id="f718f-108">**Links de indicadores** Direciona o usuário para outras áreas dentro do relatório.</span><span class="sxs-lookup"><span data-stu-id="f718f-108">**Bookmark links** Jump to other areas within the report.</span></span>  
  
-   <span data-ttu-id="f718f-109">**Hiperlinks** Direciona o usuário para as URLs que especificam o endereço de páginas da Web ou de relatórios em um servidor de relatório usando o acesso por URL.</span><span class="sxs-lookup"><span data-stu-id="f718f-109">**Hyperlinks** Jump to URLs that specify the address of Web pages or reports on a report server by using URL access.</span></span>  
  
-   <span data-ttu-id="f718f-110">**Links para relatório detalhado** Direciona o usuário para outros relatórios no mesmo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="f718f-110">**Drillthrough report links** Jump to other reports on the same report server.</span></span> <span data-ttu-id="f718f-111">Para obter mais informações, consulte [Relatórios de detalhamento &#40;Construtor de Relatórios e SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f718f-111">For more information, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f718f-112">Links associados a campos de conjuntos de dados podem ser vulneráveis à violação para fins mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="f718f-112">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="f718f-113">Para obter mais informações, consulte [Proteger Relatórios e Recursos](../security/secure-reports-and-resources.md) nos [Manuais Online](https://go.microsoft.com/fwlink/?LinkId=154888) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f718f-113">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="f718f-114">Você também pode permitir que os usuários controlem a exibição do relatório e do conteúdo criando expressões que incluem referências de parâmetros para classificação, filtro e visibilidade.</span><span class="sxs-lookup"><span data-stu-id="f718f-114">You can also let your users control report display and content by designing expressions that include parameter references for sort, filter, and visibility.</span></span> <span data-ttu-id="f718f-115">Para obter mais informações, consulte [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](report-parameters-report-builder-and-report-designer.md), [Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) e [Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span><span class="sxs-lookup"><span data-stu-id="f718f-115">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md), [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md), and [Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="f718f-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f718f-116">In This Section</span></span>  
 [<span data-ttu-id="f718f-117">Classificação interativa &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f718f-117">Interactive Sort &#40;Report Builder and SSRS&#41;</span></span>](interactive-sort-report-builder-and-ssrs.md)  
 <span data-ttu-id="f718f-118">Explica como adicionar botões de classificação interativos a cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="f718f-118">Explains how to add interactive sort buttons to column headers.</span></span>  
  
 [<span data-ttu-id="f718f-119">Criar um mapa de documentos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f718f-119">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
 <span data-ttu-id="f718f-120">Explica como adicionar um índice para oferecer suporte à navegação em um relatório grande.</span><span class="sxs-lookup"><span data-stu-id="f718f-120">Explains how to add a table of contents to support navigation in a large report.</span></span>  
  
 [<span data-ttu-id="f718f-121">Adicionar um indicador a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f718f-121">Add a Bookmark to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-bookmark-to-a-report-report-builder-and-ssrs.md)  
 <span data-ttu-id="f718f-122">Explica como adicionar marcadores para criar links dentro de um relatório.</span><span class="sxs-lookup"><span data-stu-id="f718f-122">Explains how to add bookmarks to create links within a report.</span></span>  
  
 [<span data-ttu-id="f718f-123">Adicionar um hiperlink a uma URL &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f718f-123">Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;</span></span>](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md)  
 <span data-ttu-id="f718f-124">Explica como adicionar um link de seu relatório a uma URL</span><span class="sxs-lookup"><span data-stu-id="f718f-124">Explains how to add a link from your report to a URL</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f718f-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f718f-125">See Also</span></span>  
 [<span data-ttu-id="f718f-126">Detalhamento, busca detalhada, sub-relatórios e regiões de dados aninhadas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f718f-126">Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;</span></span>](drillthrough-drilldown-subreports-and-nested-data-regions.md)  
  
  
