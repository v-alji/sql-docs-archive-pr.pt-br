---
title: Classificar dados em uma tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5fa6ad56-bf68-4aac-a226-52556173b7e2
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9a6636c2c11fc571e8d4c1bcbc25c1e02d815fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678295"
---
# <a name="sort-data-in-a-table-ssas-tabular"></a><span data-ttu-id="c9fc4-102">Classificar dados em uma tabela (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="c9fc4-102">Sort Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="c9fc4-103">É possível classificar dados por texto (de A a Z ou de Z a A) e por números (do menor para o maior ou vice-versa) em uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-103">You can sort data by text (A to Z or Z to A) and numbers (smallest to largest or largest to smallest) in one or more columns.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-text-column"></a><span data-ttu-id="c9fc4-104">Para classificar os dados em uma tabela com base em uma coluna de texto</span><span class="sxs-lookup"><span data-stu-id="c9fc4-104">To sort the data in a table based on a text column</span></span>  
  
1.  <span data-ttu-id="c9fc4-105">No designer de modelo, selecione uma coluna de dados alfanuméricos, um intervalo de células em uma coluna ou verifique se todas as células ativas estão na coluna de uma tabela que contém dados alfanuméricos e clique na seta no cabeçalho da coluna pela qual deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-105">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="c9fc4-106">No menu AutoFiltro, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c9fc4-106">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c9fc4-107">Para classificar em ordem alfanumérica crescente, clique em **Classificar de A a Z**.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-107">To sort in ascending alphanumeric order, click **Sort A to Z**.</span></span>  
  
    -   <span data-ttu-id="c9fc4-108">Para classificar em ordem alfanumérica decrescente, clique em **Classificar de Z a A**.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-108">To sort in descending alphanumeric order, click **Sort Z to A**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9fc4-109">Em alguns casos, podem ser inseridos espaços à esquerda antes dos dados importados de outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-109">In some cases, data imported from another application might have leading spaces inserted before data.</span></span> <span data-ttu-id="c9fc4-110">Você deve remover os espaços à esquerda para classificar os dados corretamente.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-110">You must remove the leading spaces in order to correctly sort the data.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-numeric-column"></a><span data-ttu-id="c9fc4-111">Para classificar os dados em uma tabela com base em uma coluna numérica</span><span class="sxs-lookup"><span data-stu-id="c9fc4-111">To sort the data in a table based on a numeric column</span></span>  
  
1.  <span data-ttu-id="c9fc4-112">No designer de modelo, selecione uma coluna de dados alfanuméricos, um intervalo de células em uma coluna ou verifique se todas as células ativas estão na coluna de uma tabela que contém dados alfanuméricos e clique na seta no cabeçalho da coluna pela qual deseja filtrar.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-112">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="c9fc4-113">No menu AutoFiltro, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c9fc4-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c9fc4-114">Para classificar de números baixos para números altos, clique em **Classificar do Menor ao Maior**.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-114">To sort from low numbers to high numbers, click **Sort Smallest to Largest**.</span></span>  
  
    -   <span data-ttu-id="c9fc4-115">Para classificar de números altos para números baixos, clique em **Classificar do Maior ao Menor**.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-115">To sort from high numbers to low numbers, click **Sort Largest to Smallest**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9fc4-116">Se os resultados não forem os esperados, a coluna poderá conter números armazenados como texto e não como números.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-116">If the results are not what you expected, the column might contain numbers stored as text and not as numbers.</span></span> <span data-ttu-id="c9fc4-117">Por exemplo, os números negativos importados de alguns sistemas de contabilidade ou um número inserido com um ' (apóstrofo) à esquerda são armazenados como texto.</span><span class="sxs-lookup"><span data-stu-id="c9fc4-117">For example, negative numbers imported from some accounting systems, or a number entered with a leading ' (apostrophe), are stored as text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9fc4-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9fc4-118">See Also</span></span>  
 <span data-ttu-id="c9fc4-119">[Filtrar e classificar dados &#40;SSAS de tabela&#41;](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c9fc4-119">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="c9fc4-120">[Perspectivas &#40;SSAS de tabela&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c9fc4-120">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c9fc4-121">Funções &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="c9fc4-121">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
