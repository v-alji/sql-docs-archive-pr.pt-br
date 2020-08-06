---
title: Atualizando células (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- modifying cells
- XMLA, cells
- updating cells
- cells [Analysis Services]
- XML for Analysis, cells
ms.assetid: a1c61496-36ee-4bce-98d9-d13440d349aa
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c3d9a7c27533666c75102d9eac3b8311bfe4af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684402"
---
# <a name="updating-cells-xmla"></a><span data-ttu-id="a3735-102">Atualizando células (XMLA)</span><span class="sxs-lookup"><span data-stu-id="a3735-102">Updating Cells (XMLA)</span></span>
  <span data-ttu-id="a3735-103">Você pode usar o comando [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) para alterar o valor de uma ou mais células em um cubo habilitado para Write-back de cubo.</span><span class="sxs-lookup"><span data-stu-id="a3735-103">You can use the [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) command to change the value of one or more cells in a cube enabled for cube writeback.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="a3735-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] armazena as informações atualizadas em uma tabela de write-back separada para cada partição que contém células a serem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="a3735-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stores the updated information in a separate writeback table for each partition that contains cells to be updated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3735-105">O comando `UpdateCells` não oferece suporte a alocações durante o write-back de cubo.</span><span class="sxs-lookup"><span data-stu-id="a3735-105">The `UpdateCells` command does not support allocations during cube writeback.</span></span> <span data-ttu-id="a3735-106">Para usar write-back alocado, você deve usar o comando de [instrução](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) para enviar uma instrução de atualização MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="a3735-106">To use allocated writeback, you should use the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command to send a Multidimensional Expressions (MDX) UPDATE statement.</span></span> <span data-ttu-id="a3735-107">Para obter mais informações, consulte a [instrução UPDATE CUBE &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-update-cube).</span><span class="sxs-lookup"><span data-stu-id="a3735-107">For more information, see [UPDATE CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-update-cube).</span></span>  
  
## <a name="specifying-cells"></a><span data-ttu-id="a3735-108">Especificando células</span><span class="sxs-lookup"><span data-stu-id="a3735-108">Specifying Cells</span></span>  
 <span data-ttu-id="a3735-109">A propriedade [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) do `UpdateCells` comando contém as células a serem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="a3735-109">The [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property of the `UpdateCells` command contains the cells to be updated.</span></span> <span data-ttu-id="a3735-110">Você identifica cada célula na propriedade `Cell` que usa o número ordinal dessa célula.</span><span class="sxs-lookup"><span data-stu-id="a3735-110">You identify each cell in the `Cell` property using that cell's ordinal number.</span></span> <span data-ttu-id="a3735-111">Conceitualmente, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] numera as células de um cubo como se o cubo fosse uma matriz *p*-dimensional, em que *p* é o número de eixos.</span><span class="sxs-lookup"><span data-stu-id="a3735-111">Conceptually, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] numbers cells in a cube as if the cube were a *p*-dimensional array, where *p* is the number of axes.</span></span> <span data-ttu-id="a3735-112">As células são tratadas em ordem linha-principal.</span><span class="sxs-lookup"><span data-stu-id="a3735-112">Cells are addressed in row-major order.</span></span> <span data-ttu-id="a3735-113">A ilustração a seguir mostra a fórmula para o cálculo do número ordinal de uma célula.</span><span class="sxs-lookup"><span data-stu-id="a3735-113">The following illustration shows the formula for calculating the ordinal number of a cell.</span></span>  
  
 <span data-ttu-id="a3735-114">![Fórmula para calcular a posição ordinal da célula](../../analysis-services/dev-guide/media/cellordinalformula.gif "Fórmula para calcular a posição ordinal da célula")</span><span class="sxs-lookup"><span data-stu-id="a3735-114">![Formula to calculate the cell ordinal position](../../analysis-services/dev-guide/media/cellordinalformula.gif "Formula to calculate the cell ordinal position")</span></span>  
  
 <span data-ttu-id="a3735-115">Depois de saber o número ordinal de uma célula, você pode indicar o valor pretendido da célula na propriedade [Value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) da propriedade [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="a3735-115">Once you know a cell's ordinal number, you can indicate the intended value of the cell in the [Value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) property of the [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3735-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a3735-116">See Also</span></span>  
 <span data-ttu-id="a3735-117">[Atualizar o elemento &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="a3735-117">[Update Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span></span>  
 [<span data-ttu-id="a3735-118">Desenvolvendo com XMLA no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a3735-118">Developing with XMLA in Analysis Services</span></span>](../multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
