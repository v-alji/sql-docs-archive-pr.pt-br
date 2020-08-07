---
title: Modificando dados (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01df67471753922e3e7db39c56a9ed50aae900dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574928"
---
# <a name="modifying-data-mdx"></a><span data-ttu-id="e7a98-102">Modificando dados (MDX)</span><span class="sxs-lookup"><span data-stu-id="e7a98-102">Modifying Data (MDX)</span></span>
  <span data-ttu-id="e7a98-103">Além de usar a linguagem MDX para recuperar e manipular dados de dimensões e cubos, você pode usá-la para atualizar ou executar *write-back* de dados de dimensão e de cubo.</span><span class="sxs-lookup"><span data-stu-id="e7a98-103">Besides using Multidimensional Expressions (MDX) to retrieve and handle data from dimensions and cubes, you can use MDX to update or *writeback* dimension and cube data.</span></span> <span data-ttu-id="e7a98-104">Essas atualizações podem ser temporárias, como na análise teórica (ou"what if"), ou permanentes, como quando alterações devem ser feitas com base na análise dos dados.</span><span class="sxs-lookup"><span data-stu-id="e7a98-104">These updates can be temporary, as with speculative, or "what if", analysis, or permanent, as when changes must occur based upon data analysis.</span></span>  
  
 <span data-ttu-id="e7a98-105">As atualizações de dados podem ocorrer no nível de dimensão ou de cubo:</span><span class="sxs-lookup"><span data-stu-id="e7a98-105">Updates to data can occur at the dimension or cube level:</span></span>  
  
 <span data-ttu-id="e7a98-106">**Write-backs de dimensão**</span><span class="sxs-lookup"><span data-stu-id="e7a98-106">**Dimension writebacks**</span></span>  
 <span data-ttu-id="e7a98-107">Use a [Instrução ALTER CUBE (MDX)](/sql/mdx/mdx-data-definition-alter-cube) para alterar os dados de uma dimensão habilitada para gravação e a [Instrução REFRESH CUBE (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) para refletir a exclusão, criação e atualização de valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="e7a98-107">You use the [ALTER CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-alter-cube) statement to change a write-enabled dimension's data and the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to reflect the deletion, creation, and updating of attribute values.</span></span> <span data-ttu-id="e7a98-108">Você também pode usar a instrução ALTER CUBE para executar operações complexas, como excluir uma subárvore inteira de uma hierarquia e promover os filhos de um membro excluído.</span><span class="sxs-lookup"><span data-stu-id="e7a98-108">You can also use the ALTER CUBE statement to perform complex operations, such as deleting a whole sub-tree in a hierarchy and promoting the children of a deleted member.</span></span>  
  
 <span data-ttu-id="e7a98-109">**Write-backs de cubo**</span><span class="sxs-lookup"><span data-stu-id="e7a98-109">**Cube writebacks**</span></span>  
 <span data-ttu-id="e7a98-110">Use a instrução [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) para fazer atualizações em um cubo habilitado para gravação.</span><span class="sxs-lookup"><span data-stu-id="e7a98-110">You use the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement to make updates to a write-enabled cube.</span></span> <span data-ttu-id="e7a98-111">A instrução UPDATE CUBE permite atualizar uma tupla com um valor específico.</span><span class="sxs-lookup"><span data-stu-id="e7a98-111">The UPDATE CUBE statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="e7a98-112">Use a [Instrução REFRESH CUBE (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) para atualizar dados de uma sessão de cliente com dados atualizados do servidor.</span><span class="sxs-lookup"><span data-stu-id="e7a98-112">You use the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to refresh data in a client session with updated data from the server.</span></span>  
  
 <span data-ttu-id="e7a98-113">Para obter mais informações, consulte [Usando write-backs de cubo &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span><span class="sxs-lookup"><span data-stu-id="e7a98-113">For more information, see [Using Cube Writebacks &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a98-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7a98-114">See Also</span></span>  
 [<span data-ttu-id="e7a98-115">Conceitos básicos de consulta MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e7a98-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
