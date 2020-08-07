---
title: Mesclar células em uma região de dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 43551300-89b2-4f4e-af09-69084324afaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c69ce8182bda3e0b644893e97b69280a003f5732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682121"
---
# <a name="merge-cells-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="a0ce4-102">Mesclar células em uma região de dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a0ce4-102">Merge Cells in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a0ce4-103">Você pode mesclar células em uma região de dados para combinar células, melhorar a aparência da região de dados ou fornecer rótulos que abrangem grupos de colunas e de linhas.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-103">You can merge cells in a data region to combine cells, improve data region appearance, or provide spanning labels for column groups and row groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0ce4-104">As células só podem ser mescladas dentro de cada área de uma região de dados: canto, cabeçalho de coluna, definição de grupo (ou cabeçalhos de linha) e corpo.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-104">Cells can only be merged within each area of a data region: corner, column headers, group definition (or row headers), and body.</span></span> <span data-ttu-id="a0ce4-105">Não é possível mesclar células que cruzam os limites da área.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-105">You cannot merge cells that cross area boundaries.</span></span> <span data-ttu-id="a0ce4-106">Por exemplo, você não pode mesclar uma célula na área do canto da região de dados com uma célula na área do grupo de linhas.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-106">For example, you cannot merge a cell in the data region corner area with a cell in the row group area.</span></span> <span data-ttu-id="a0ce4-107">Para obter mais informações sobre áreas tablix, consulte [listas &#40;Construtor de relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a0ce4-107">For more information about tablix areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-merge-cells-in-a-data-region"></a><span data-ttu-id="a0ce4-108">Para mesclar células em uma região de dados</span><span class="sxs-lookup"><span data-stu-id="a0ce4-108">To merge cells in a data region</span></span>  
  
1.  <span data-ttu-id="a0ce4-109">Na região de dados na superfície de design de relatório, clique na primeira célula a ser mesclada.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-109">In the data region on the report design surface, click the first cell to merge.</span></span> <span data-ttu-id="a0ce4-110">Mantendo o botão esquerdo do mouse pressionado, arraste verticalmente ou horizontalmente para selecionar células adjacentes.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-110">Holding the left mouse button down, drag vertically or horizontally to select adjacent cells.</span></span> <span data-ttu-id="a0ce4-111">As células selecionadas são realçadas.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-111">The selected cells are highlighted.</span></span>  
  
2.  <span data-ttu-id="a0ce4-112">Clique com o botão direito do mouse nas células selecionadas e selecione **Mesclar Células**.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-112">Right-click the selected cells and select **Merge Cells**.</span></span> <span data-ttu-id="a0ce4-113">As células selecionadas são combinadas em uma única célula.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-113">The selected cells are combined into a single cell.</span></span>  
  
3.  <span data-ttu-id="a0ce4-114">Repita as etapas 1 e 2 para mesclar outras células adjacentes em uma região de dados.</span><span class="sxs-lookup"><span data-stu-id="a0ce4-114">Repeat steps 1 and 2 to merge other adjacent cells in a data region.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ce4-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0ce4-115">See Also</span></span>  
 <span data-ttu-id="a0ce4-116">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0ce4-116">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a0ce4-117">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0ce4-117">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a0ce4-118">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0ce4-118">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a0ce4-119">[Lista &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a0ce4-119">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a0ce4-120">Listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ce4-120">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
