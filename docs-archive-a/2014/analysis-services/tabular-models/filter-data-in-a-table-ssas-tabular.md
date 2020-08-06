---
title: Filtrar dados em uma tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.customfilterdb.f1
- sql12.asvs.bidtoolset.autofiltermenu.f1
- sql12.asvs.bidtoolset.notallitemsshowing.f1
ms.assetid: 3223059d-f525-4835-bf88-ebc195d9dbdc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f4003457df4068713e75e6bb5c0ab78c15ac03c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679035"
---
# <a name="filter-data-in-a-table-ssas-tabular"></a><span data-ttu-id="f64e0-102">Filtrar dados em uma tabela (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="f64e0-102">Filter Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="f64e0-103">Ao importar dados, é possível aplicar filtros para controlar as linhas que são carregadas em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="f64e0-103">You can apply filters when you import data to control the rows that are loaded into a table.</span></span> <span data-ttu-id="f64e0-104">Depois de importar os dados, não é possível excluir linhas individuais.</span><span class="sxs-lookup"><span data-stu-id="f64e0-104">After you have imported the data, you cannot delete individual rows.</span></span> <span data-ttu-id="f64e0-105">No entanto, você pode aplicar filtros personalizados para controlar a exibição das linhas.</span><span class="sxs-lookup"><span data-stu-id="f64e0-105">However, you can apply custom filters to control the way that rows are displayed.</span></span> <span data-ttu-id="f64e0-106">As linhas que não atenderem aos critérios de filtragem serão ocultadas.</span><span class="sxs-lookup"><span data-stu-id="f64e0-106">Rows that do not meet the filtering criteria are hidden.</span></span> <span data-ttu-id="f64e0-107">Você pode basear um filtro em uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="f64e0-107">You can filter by one or more columns.</span></span> <span data-ttu-id="f64e0-108">Os filtros são aditivos, ou seja, cada filtro adicional se baseia no filtro atual e reduz ainda mais o subconjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="f64e0-108">Filters are additive, which means that each additional filter is based on the current filter and further reduces the subset of data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f64e0-109">A janela de visualização de filtro limita o número de valores diferentes exibidos.</span><span class="sxs-lookup"><span data-stu-id="f64e0-109">The filter preview window limits the number of different values displayed.</span></span> <span data-ttu-id="f64e0-110">Se o limite for excedido, uma mensagem será exibida.</span><span class="sxs-lookup"><span data-stu-id="f64e0-110">If the limit is exceeded, a message is displayed.</span></span>  
  
### <a name="to-filter-data-based-on-column-values"></a><span data-ttu-id="f64e0-111">Para filtrar dados com base em valores de coluna</span><span class="sxs-lookup"><span data-stu-id="f64e0-111">To filter data based on column values</span></span>  
  
1.  <span data-ttu-id="f64e0-112">No designer de modelo, selecione uma tabela e clique na seta no cabeçalho da coluna pela qual deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="f64e0-112">In the model designer, select a table, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="f64e0-113">No menu AutoFiltro, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f64e0-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="f64e0-114">Na lista de valores de coluna, marque ou desmarque um ou mais valores pelos quais filtrar e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f64e0-114">In the list of column values, select or clear one or more values to filter by, and then click **OK**.</span></span>  
  
         <span data-ttu-id="f64e0-115">Se o número de valores for extremamente grande, os itens individuais poderão não ser mostrados na lista.</span><span class="sxs-lookup"><span data-stu-id="f64e0-115">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="f64e0-116">Em vez disso, você verá a mensagem "Itens demais para mostrar".</span><span class="sxs-lookup"><span data-stu-id="f64e0-116">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="f64e0-117">Clique em **filtros de número** ou filtros de **texto** (dependendo do tipo de coluna) e, em seguida, clique nos comandos do operador de comparação (como **igual**a) ou clique em **filtro personalizado**.</span><span class="sxs-lookup"><span data-stu-id="f64e0-117">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as **Equals**), or click **Custom Filter**.</span></span> <span data-ttu-id="f64e0-118">Na caixa de diálogo **Filtro Personalizado** , crie o filtro e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f64e0-118">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
### <a name="to-clear-a-filter-for-a-column"></a><span data-ttu-id="f64e0-119">Para limpar um filtro de uma coluna</span><span class="sxs-lookup"><span data-stu-id="f64e0-119">To clear a filter for a column</span></span>  
  
1.  <span data-ttu-id="f64e0-120">Clique na seta no cabeçalho da coluna da qual você deseja limpar um filtro.</span><span class="sxs-lookup"><span data-stu-id="f64e0-120">Click the arrow in the header of the column for which you want to clear a filter.</span></span>  
  
2.  <span data-ttu-id="f64e0-121">Clique em \*\*Limpar filtro \<Column Name> de \*\*.</span><span class="sxs-lookup"><span data-stu-id="f64e0-121">Click **Clear Filter from \<Column Name>**.</span></span>  
  
### <a name="to-clear-all-filters-for-a-table"></a><span data-ttu-id="f64e0-122">Para desmarcar todos os filtros de uma tabela</span><span class="sxs-lookup"><span data-stu-id="f64e0-122">To clear all filters for a table</span></span>  
  
1.  <span data-ttu-id="f64e0-123">No designer de modelo, selecione a tabela para a qual você deseja limpar filtros.</span><span class="sxs-lookup"><span data-stu-id="f64e0-123">In the model designer, select the table for which you want to clear filters.</span></span>  
  
2.  <span data-ttu-id="f64e0-124">Clique no menu **Coluna** e, em seguida, clique em **Limpar Todos os Filtros**.</span><span class="sxs-lookup"><span data-stu-id="f64e0-124">Click on the **Column** menu, and then click **Clear All Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f64e0-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f64e0-125">See Also</span></span>  
 <span data-ttu-id="f64e0-126">[Filtrar e classificar dados &#40;SSAS de tabela&#41;](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f64e0-126">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="f64e0-127">[Perspectivas &#40;SSAS de tabela&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="f64e0-127">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="f64e0-128">Funções &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="f64e0-128">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
