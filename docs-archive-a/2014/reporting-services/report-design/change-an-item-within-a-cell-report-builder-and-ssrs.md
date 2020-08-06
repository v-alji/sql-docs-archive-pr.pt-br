---
title: Alterar um item em uma célula (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91a54778-8929-41f9-bb4c-826cec636be4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 80ef171713e6505867e00e343ce17b70cab9045a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686064"
---
# <a name="change-an-item-within-a-cell-report-builder-and-ssrs"></a><span data-ttu-id="71481-102">Alterar um item de uma célula (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="71481-102">Change an Item Within a Cell (Report Builder and SSRS)</span></span>
  <span data-ttu-id="71481-103">Somente um item não contêiner, como uma caixa de texto, linha ou imagem, pode ser substituído por um novo item de relatório.</span><span class="sxs-lookup"><span data-stu-id="71481-103">Only a non-container item, such as a text box, line, or image, can be replaced by a new report item.</span></span> <span data-ttu-id="71481-104">Por exemplo, é possível arrastar uma tabela para uma caixa de texto a fim de substituí-la pela tabela.</span><span class="sxs-lookup"><span data-stu-id="71481-104">For example, you can drag a table into a text box to replace the text box with a table.</span></span>  
  
 <span data-ttu-id="71481-105">Se a célula contiver um item de contêiner, como um retângulo, lista, tabela ou matriz, o novo item será adicionado a ele em vez de substituí-lo.</span><span class="sxs-lookup"><span data-stu-id="71481-105">If the cell contains a container item such as a rectangle, list, table, or matrix, the new item is added to the containing item instead of replacing it.</span></span> <span data-ttu-id="71481-106">Para substituir um item por um novo item, exclua o contêiner.</span><span class="sxs-lookup"><span data-stu-id="71481-106">To replace a container item with a new item, delete the container.</span></span> <span data-ttu-id="71481-107">A exclusão do contêiner substitui o mesmo por uma caixa de texto, que você pode então substituir por outro item.</span><span class="sxs-lookup"><span data-stu-id="71481-107">Deleting the container item replaces it with a text box, which you can then replace with another item.</span></span>  
  
 <span data-ttu-id="71481-108">Por padrão, todas as células de uma tabela, matriz ou região de dados da lista contêm uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="71481-108">By default, all cells in a table, matrix, or list data region contain a text box.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-an-item-within-a-cell"></a><span data-ttu-id="71481-109">Para alterar um item de uma célula</span><span class="sxs-lookup"><span data-stu-id="71481-109">To change an item within a cell</span></span>  
  
-   <span data-ttu-id="71481-110">Na guia **Inserir** , no grupo **Regiões de Dados** ou **Itens de Relatório** , clique no item que você deseja adicionar ao relatório e, em seguida, clique no relatório.</span><span class="sxs-lookup"><span data-stu-id="71481-110">On the **Insert** tab, in the **Data Regions** or **Report Items** group, click the item that you want to add to the report, and then click the report.</span></span> <span data-ttu-id="71481-111">O item será adicionado ao relatório.</span><span class="sxs-lookup"><span data-stu-id="71481-111">The item is added to the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71481-112">A caixa de diálogo **Propriedades da Imagem** é aberta quando você arrasta um item de relatório de imagem para uma célula, na qual é possível definir propriedades, como a origem da imagem, antes de adicionar a imagem à célula.</span><span class="sxs-lookup"><span data-stu-id="71481-112">The **Image Properties** dialog box opens when you drag an image report item to a cell, where you can set properties such as the source of the image before the image is added to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71481-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71481-113">See Also</span></span>  
 <span data-ttu-id="71481-114">[Imagens, caixas de texto, retângulos e linhas &#40;Construtor de Relatórios e SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="71481-114">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="71481-115">Listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="71481-115">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
