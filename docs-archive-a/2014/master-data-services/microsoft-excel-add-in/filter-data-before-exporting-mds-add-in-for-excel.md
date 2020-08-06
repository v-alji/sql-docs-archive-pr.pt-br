---
title: Filtrar dados antes do carregamento (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9e30eae0-776b-4a09-aac3-0c0249d92ca5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6d0ccf667f37763326e27dcd8d0cfc005627ebc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680516"
---
# <a name="filter-data-before-loading-mds-add-in-for-excel"></a><span data-ttu-id="6af90-102">Filtrar dados antes de carregar (suplemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="6af90-102">Filter Data before Loading (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="6af90-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , filtre os dados quando desejar limitar o tamanho ou o escopo dos dados que você está carregando no Excel.</span><span class="sxs-lookup"><span data-stu-id="6af90-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], filter data when you want to limit the size or scope of data that you are loading into Excel.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6af90-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6af90-104">Prerequisites</span></span>  
 <span data-ttu-id="6af90-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="6af90-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6af90-106">Você deve ter permissão para acessar a área funcional do **Gerenciador** .</span><span class="sxs-lookup"><span data-stu-id="6af90-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-filter-data-before-loading"></a><span data-ttu-id="6af90-107">Para filtrar dados antes de carregar</span><span class="sxs-lookup"><span data-stu-id="6af90-107">To filter data before loading</span></span>  
  
1.  <span data-ttu-id="6af90-108">Abra o Excel e, na guia **Dados Mestre** , conecte-se a um repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="6af90-108">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="6af90-109">Para obter mais informações, consulte [Conectar-se a um repositório do MDS &#40;Suplemento MDS para Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6af90-109">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="6af90-110">No painel do **Master Data Explorer** , selecione um modelo e uma versão.</span><span class="sxs-lookup"><span data-stu-id="6af90-110">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="6af90-111">A lista de entidades será preenchida.</span><span class="sxs-lookup"><span data-stu-id="6af90-111">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="6af90-112">Se o painel do **Master Data Explorer** não estiver visível, no grupo **Conectar e Carregar** , clique em **Mostrar Explorer**.</span><span class="sxs-lookup"><span data-stu-id="6af90-112">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="6af90-113">Se o painel **Master Data Explorer** estiver desabilitado, isso significará que a planilha existente já contém dados gerenciados pelo MDS.</span><span class="sxs-lookup"><span data-stu-id="6af90-113">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="6af90-114">Para habilitar o painel, abra uma nova planilha.</span><span class="sxs-lookup"><span data-stu-id="6af90-114">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="6af90-115">No painel do **Master Data Explorer** , na lista de entidades, clique na entidade que você deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="6af90-115">In the **Master Data Explorer** pane, in the list of entities, click the entity you want to filter.</span></span>  
  
4.  <span data-ttu-id="6af90-116">Na faixa de opções, no grupo **Conectar e Carregar** , clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="6af90-116">On the ribbon, in the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="6af90-117">Preencha a caixa de diálogo **Filtrar** selecionando os atributos (colunas) a serem exibidos, definindo a ordem das colunas e, se necessário, filtrando os dados para que menos linhas sejam retornadas.</span><span class="sxs-lookup"><span data-stu-id="6af90-117">Complete the **Filter** dialog box by selecting the attributes (columns) to display, setting the order of the columns, and if needed, filtering the data so fewer rows are returned.</span></span> <span data-ttu-id="6af90-118">Abra o painel **Resumo** para saber a quantidade de dados que será retornada.</span><span class="sxs-lookup"><span data-stu-id="6af90-118">View the **Summary** pane for how much data will be returned.</span></span> <span data-ttu-id="6af90-119">Para obter mais informações, consulte [Caixa de diálogo Filtrar &#40;Suplemento MDS para Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6af90-119">For more information, see [Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md).</span></span>  
  
6.  <span data-ttu-id="6af90-120">Clique em **Carregar Dados**.</span><span class="sxs-lookup"><span data-stu-id="6af90-120">Click **Load Data**.</span></span> <span data-ttu-id="6af90-121">A planilha será preenchida com os dados gerenciados no MDS.</span><span class="sxs-lookup"><span data-stu-id="6af90-121">The sheet is populated with MDS-managed data.</span></span>  
  
    > [!NOTE]  
    >  -   <span data-ttu-id="6af90-122">Somente os primeiros um milhão de membros serão carregados no Excel.</span><span class="sxs-lookup"><span data-stu-id="6af90-122">Only the first one million members are loaded into Excel.</span></span>  
    > -   <span data-ttu-id="6af90-123">Em colunas que são listas restritas (atributos baseados em domínio), somente os primeiros 1000 valores são carregados.</span><span class="sxs-lookup"><span data-stu-id="6af90-123">In columns that are constrained lists (domain-based attributes), only the first 1000 values are loaded.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6af90-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6af90-124">Next Steps</span></span>  
 [<span data-ttu-id="6af90-125">Publicar dados do Excel para o MDS &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6af90-125">Publish Data from Excel to MDS &#40;MDS Add-in for Excel&#41;</span></span>](import-data-from-excel-to-master-data-services-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="6af90-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6af90-126">See Also</span></span>  
 <span data-ttu-id="6af90-127">[Carregando dados &#40;Suplemento MDS para Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="6af90-127">[Loading Data &#40;MDS Add-in for Excel&#41;](overview-exporting-data-to-excel-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="6af90-128">[Caixa de diálogo de filtro &#40;Suplemento MDS para Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="6af90-128">[Filter Dialog Box &#40;MDS Add-in for Excel&#41;](filter-dialog-box-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="6af90-129">Reordenar colunas &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="6af90-129">Reorder Columns &#40;MDS Add-in for Excel&#41;</span></span>](reorder-columns-mds-add-in-for-excel.md)  
  
  
