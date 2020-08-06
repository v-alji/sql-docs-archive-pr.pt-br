---
title: Exibir dados espaciais no Pesquisador de Objetos
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 59cca562-e3f5-4257-b868-adcbcc0142cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 881adf69ee83ee4b7536afae0b190fbec90f132c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574625"
---
# <a name="view-spatial-data-in-object-explorer"></a><span data-ttu-id="7d896-102">Exibir dados espaciais no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="7d896-102">View Spatial Data in Object Explorer</span></span>
  <span data-ttu-id="7d896-103">A janela **Resultados espaciais** no Editor de Consultas fornece ferramentas de mapeamento visuais para exibir resultados de dados espaciais além dos dados exibidos em formato de grade na janela **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="7d896-103">The **Spatial results** window in Query Editor provides visual mapping tools for viewing spatial data results in addition to the data displayed in grid format in the **Results** window.</span></span> <span data-ttu-id="7d896-104">Para exibir dados espaciais na janela **Resultados Espaciais** , os resultados da consulta devem conter pelo menos uma coluna de dados espaciais com dados de geometria ou de geografia.</span><span class="sxs-lookup"><span data-stu-id="7d896-104">To display spatial data in the **Spatial Results** window, your query results must contain at least one spatial data column with either geometry or geography data.</span></span>  
  
### <a name="to-view-spatial-data-in-the-spatial-results-window"></a><span data-ttu-id="7d896-105">Para exibir dados espaciais na janela Resultados espaciais</span><span class="sxs-lookup"><span data-stu-id="7d896-105">To view spatial data in the Spatial results window</span></span>  
  
1.  <span data-ttu-id="7d896-106">No Editor de Consultas, clique na guia **Resultados espaciais** .</span><span class="sxs-lookup"><span data-stu-id="7d896-106">In Query Editor, click the **Spatial results** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d896-107">Essa janela não estará disponível se os resultados da consulta não contiverem dados espaciais ou se você especificar que os resultados são retornados como texto.</span><span class="sxs-lookup"><span data-stu-id="7d896-107">This window is not available if your query results do not contain spatial data or if you specify that your results are returned as text.</span></span>  
  
2.  <span data-ttu-id="7d896-108">Selecione a coluna que você deseja exibir na lista **Selecionar coluna espacial** .</span><span class="sxs-lookup"><span data-stu-id="7d896-108">Select the column you want to view from the **Select spatial column** list.</span></span> <span data-ttu-id="7d896-109">Se houver apenas uma coluna espacial na tabela, essa coluna será a opção padrão na lista.</span><span class="sxs-lookup"><span data-stu-id="7d896-109">If there is only one spatial column in your table, this column is the default option in the list.</span></span>  
  
3.  <span data-ttu-id="7d896-110">Selecione a coluna não espacial que você deseja usar como rótulos de dados na lista **Selecionar colunas de rótulos** .</span><span class="sxs-lookup"><span data-stu-id="7d896-110">Select the non-spatial column you want to use as data labels from the **Select label columns** list.</span></span>  
  
4.  <span data-ttu-id="7d896-111">Selecione a projeção desejada para obter dados de geografia na lista **Selecionar projeção** .</span><span class="sxs-lookup"><span data-stu-id="7d896-111">Select the projection you want for geography data from the **Select projection** list.</span></span> <span data-ttu-id="7d896-112">A projeção padrão é Cilíndrica equidistante. Outras projeções disponíveis são Mercator, Robinson ou Bonne.</span><span class="sxs-lookup"><span data-stu-id="7d896-112">The default projection is Equirectangular; other projections available are Mercator, Robinson, or Bonne.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d896-113">**Selecionar projeção** não estará disponível se a coluna espacial contiver dados geométricos.</span><span class="sxs-lookup"><span data-stu-id="7d896-113">**Select projection** is not available if your spatial column contains geometry data.</span></span>  
  
5.  <span data-ttu-id="7d896-114">Ajuste o controle deslizante **Zoom** para aumentar o tamanho visual dos elementos mapeados.</span><span class="sxs-lookup"><span data-stu-id="7d896-114">Adjust the **Zoom** slider to increase the visual size of mapped elements.</span></span> <span data-ttu-id="7d896-115">Para formas de polígono, o rótulo é visível apenas quando a forma for grande o suficiente para manter o texto do rótulo.</span><span class="sxs-lookup"><span data-stu-id="7d896-115">For polygon shapes, the label is visible only when the shape is large enough to hold the label text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d896-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d896-116">See Also</span></span>  
 <span data-ttu-id="7d896-117">[Janela Resultados Espaciais](spatial-results-window.md) </span><span class="sxs-lookup"><span data-stu-id="7d896-117">[Spatial Results Window](spatial-results-window.md) </span></span>  
 <span data-ttu-id="7d896-118">[Editor de Consultas do Mecanismo de Banco de Dados &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7d896-118">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="7d896-119">Editores de consultas e de texto &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7d896-119">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
