---
title: Janela Resultados Espaciais
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2d5a477-6496-4d01-adee-7322ebdfadf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e018ec9f016dfc51ed1bb055ba94abf12bc878f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686238"
---
# <a name="spatial-results-window"></a><span data-ttu-id="ea86e-102">Janela Resultados Espaciais</span><span class="sxs-lookup"><span data-stu-id="ea86e-102">Spatial Results Window</span></span>
  <span data-ttu-id="ea86e-103">A janela **Resultados espaciais** fornece ferramentas de mapeamento visuais para exibição de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="ea86e-103">The **Spatial results** window provides visual mapping tools for viewing spatial data.</span></span> <span data-ttu-id="ea86e-104">Para exibir resultados espaciais, os resultados da consulta devem incluir uma coluna espacial com dados de geometria ou de geografia.</span><span class="sxs-lookup"><span data-stu-id="ea86e-104">To view spatial results, your query results must include a spatial column with either geometry or geography data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea86e-105">A janela **Resultados espaciais** estará disponível apenas se os resultados forem retornados para uma grade na janela **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="ea86e-105">The **Spatial results** window is only available if your results are returned to a grid in the **Results** window.</span></span> <span data-ttu-id="ea86e-106">Se você especificar que os resultados são retornados como texto, essa janela não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="ea86e-106">If you specify that your results are returned as text, this window is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea86e-107">Opções</span><span class="sxs-lookup"><span data-stu-id="ea86e-107">Options</span></span>  
 <span data-ttu-id="ea86e-108">**Selecionar coluna espacial**</span><span class="sxs-lookup"><span data-stu-id="ea86e-108">**Select spatial column**</span></span>  
 <span data-ttu-id="ea86e-109">Especifique a coluna espacial que você deseja exibir das colunas espaciais dos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="ea86e-109">Specify the spatial column you want to view from the spatial columns in the query results.</span></span> <span data-ttu-id="ea86e-110">Apenas uma coluna pode ser selecionada por vez.</span><span class="sxs-lookup"><span data-stu-id="ea86e-110">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="ea86e-111">**Selecionar coluna de rótulo**</span><span class="sxs-lookup"><span data-stu-id="ea86e-111">**Select label column**</span></span>  
 <span data-ttu-id="ea86e-112">Especifique a coluna não espacial das colunas retornadas nos resultados da consulta para rotular os dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="ea86e-112">Specify the non-spatial column from the columns returned in the query results to label the spatial data.</span></span> <span data-ttu-id="ea86e-113">Apenas uma coluna pode ser selecionada por vez.</span><span class="sxs-lookup"><span data-stu-id="ea86e-113">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="ea86e-114">Essa opção não estará disponível quando apenas instâncias de ponto forem retornadas em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="ea86e-114">This option is not available when only point instances are returned in a query.</span></span>  
  
 <span data-ttu-id="ea86e-115">**Selecionar projeção**</span><span class="sxs-lookup"><span data-stu-id="ea86e-115">**Select projection**</span></span>  
 <span data-ttu-id="ea86e-116">Exiba dados de geografia em uma de quatro projeções: Cilíndrica equidistante, Mercator, Robinson ou Bonne.</span><span class="sxs-lookup"><span data-stu-id="ea86e-116">Display geography data in one of four projections: Equirectangular, Mercator, Robinson, or Bonne.</span></span>  
  
 <span data-ttu-id="ea86e-117">Essa opção não está disponível para dados de geometria.</span><span class="sxs-lookup"><span data-stu-id="ea86e-117">This option is not available for geometry data.</span></span>  
  
 <span data-ttu-id="ea86e-118">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="ea86e-118">**Zoom**</span></span>  
 <span data-ttu-id="ea86e-119">Ajuste a exibição do mapa em uma escala exponencial.</span><span class="sxs-lookup"><span data-stu-id="ea86e-119">Adjust the map display on an exponential scale.</span></span>  
  
 <span data-ttu-id="ea86e-120">**Mostrar linhas de grade**</span><span class="sxs-lookup"><span data-stu-id="ea86e-120">**Show grid lines**</span></span>  
 <span data-ttu-id="ea86e-121">Ative ou desative as linhas de grade das coordenadas.</span><span class="sxs-lookup"><span data-stu-id="ea86e-121">Toggle coordinate gridlines on or off.</span></span>  
  
 <span data-ttu-id="ea86e-122">Para formas de polígono, o rótulo é exibido apenas quando a forma for grande o suficiente para manter o texto do rótulo.</span><span class="sxs-lookup"><span data-stu-id="ea86e-122">For polygon shapes, the label is displayed only when the shape is large enough to hold the label text.</span></span> <span data-ttu-id="ea86e-123">Para exibir rótulos para formas pequenas, ajuste o zoom.</span><span class="sxs-lookup"><span data-stu-id="ea86e-123">To display labels for small shapes, adjust the zoom.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea86e-124">Instâncias de ponto não podem ser rotuladas.</span><span class="sxs-lookup"><span data-stu-id="ea86e-124">Point instances cannot be labeled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea86e-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea86e-125">See Also</span></span>  
 <span data-ttu-id="ea86e-126">[Exibir dados espaciais no Pesquisador de Objetos](view-spatial-data-in-object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="ea86e-126">[View Spatial Data in Object Explorer](view-spatial-data-in-object-explorer.md) </span></span>  
 <span data-ttu-id="ea86e-127">[Dados espaciais &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ea86e-127">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span></span>  
 <span data-ttu-id="ea86e-128">[Editor de Consultas do Mecanismo de Banco de Dados &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ea86e-128">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="ea86e-129">Editores de consultas e de texto &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ea86e-129">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
