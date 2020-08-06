---
title: Filtrar o cubo de origem para uma estrutura de mineração | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slice cubes [Analysis Services]
- mining structures [Analysis Services], filtering source cube
- cubes [Analysis Services], slicing
- filtering data [Analysis Services]
ms.assetid: 05dce7e1-2fe5-4500-bacf-c1a8a76e1424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61409b4803f43d3ff2634daaba65a92bc343db36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570990"
---
# <a name="filter-the-source-cube-for-a-mining-structure"></a><span data-ttu-id="2b0e2-102">Filtrar o cubo de origem para uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="2b0e2-102">Filter the Source Cube for a Mining Structure</span></span>
  <span data-ttu-id="2b0e2-103">Ao criar uma estrutura de mineração baseada em dados em um modelo multidimensional (um cubo OLAP), você pode *dividir* o cubo no qual a estrutura de mineração se baseia.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-103">When you create a mining structure that is based on data in a multidimensional model (an OLAP cube), you can *slice* the cube that the mining structure is based on.</span></span> <span data-ttu-id="2b0e2-104">A divisão permite criar subconjuntos de dados, como um tipo de filtro nos dados que são usados para treinar o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-104">Slicing lets you create subsets of data, as a kind of filter on the data that is used to train the mining model.</span></span>  
  
### <a name="to-slice-a-cube"></a><span data-ttu-id="2b0e2-105">Para fatiar um cubo</span><span class="sxs-lookup"><span data-stu-id="2b0e2-105">To slice a cube</span></span>  
  
1.  <span data-ttu-id="2b0e2-106">No designer de mineração de dados no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , selecione a guia **estrutura de mineração** ou a guia **modelos de mineração** .</span><span class="sxs-lookup"><span data-stu-id="2b0e2-106">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], select the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="2b0e2-107">No menu **modelo de mineração** , selecione **definir fatia de cubo de estrutura de mineração**.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-107">On the **Mining Model** menu, select **Define Mining Structure Cube Slice**.</span></span>  
  
     <span data-ttu-id="2b0e2-108">A caixa de diálogo **cubo de fatia** é aberta.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-108">The **Slice Cube** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="2b0e2-109">Na coluna **dimensão** da caixa de diálogo **cubo de fatia** , selecione a dimensão que você deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-109">In the **Dimension** column of the **Slice Cube** dialog box, select the dimension that you want to filter.</span></span>  
  
4.  <span data-ttu-id="2b0e2-110">Selecione um nível de hierarquia, usando a lista na coluna **hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="2b0e2-110">Select a level of a hierarchy, using the list in the **Hierarchy** column.</span></span>  
  
5.  <span data-ttu-id="2b0e2-111">Selecione um operador da lista na coluna **operador** para usar na criação da condição de filtro.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-111">Select an operator from the list in the **Operator** column, to use in building the filter condition.</span></span>  
  
6.  <span data-ttu-id="2b0e2-112">Clique na caixa na coluna **filtro** .</span><span class="sxs-lookup"><span data-stu-id="2b0e2-112">Click the box in the **Filter** column.</span></span>  
  
     <span data-ttu-id="2b0e2-113">A caixa de diálogo que é aberta contém todos os membros no nível especificado da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-113">A dialog box opens that contains all the members at the specified level of the hierarchy.</span></span>  
  
7.  <span data-ttu-id="2b0e2-114">Selecione o membro ou membros aos quais você pretende aplicar o filtro.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-114">Select the member or members on which you want to filter.</span></span>  
  
8.  <span data-ttu-id="2b0e2-115">Clique em **OK** na caixa de diálogo membro.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-115">Click **OK** in the member dialog box.</span></span>  
  
9. <span data-ttu-id="2b0e2-116">Clique em **OK** na caixa de diálogo **cubo de fatia** .</span><span class="sxs-lookup"><span data-stu-id="2b0e2-116">Click **OK** in the **Slice Cube** dialog box.</span></span>  
  
     <span data-ttu-id="2b0e2-117">O cubo de origem agora é filtrado do modo definido pela fatia de cubo.</span><span class="sxs-lookup"><span data-stu-id="2b0e2-117">The source cube is now filtered as defined by the cube slice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b0e2-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b0e2-118">See Also</span></span>  
 <span data-ttu-id="2b0e2-119">[Tarefas e instruções da estrutura de mineração](data-mining/mining-structure-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="2b0e2-119">[Mining Structure Tasks and How-tos](data-mining/mining-structure-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="2b0e2-120">Criar uma nova estrutura de mineração OLAP</span><span class="sxs-lookup"><span data-stu-id="2b0e2-120">Create a New OLAP Mining Structure</span></span>](data-mining/create-a-new-olap-mining-structure.md)  
  
  
