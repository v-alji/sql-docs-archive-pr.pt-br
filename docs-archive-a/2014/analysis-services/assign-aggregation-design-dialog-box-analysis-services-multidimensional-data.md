---
title: Caixa de diálogo Atribuir Design de agregação (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.copyaggregationdesign.f1
ms.assetid: 50c26cb1-c294-4f17-8b9e-435fdbd4806d
author: minewiskan
ms.author: owend
ms.openlocfilehash: dfc4f7a0847373360a79ddda366ad7aa3f02c5de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571222"
---
# <a name="assign-aggregation-design-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="5daf8-102">Caixa de diálogo Atribuir Design de Agregação (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="5daf8-102">Assign Aggregation Design Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="5daf8-103">Use a caixa de diálogo **Atribuir Design de Agregação** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para atribuir designs de agregação a uma ou mais partições de destino.</span><span class="sxs-lookup"><span data-stu-id="5daf8-103">Use the **Assign Aggregation Design** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to assign aggregation designs to one or more destination partitions.</span></span> <span data-ttu-id="5daf8-104">Você pode exibir a caixa de diálogo **Atribuir Design de Agregação** clicando com o botão direito do mouse em uma partição ou design de agregação no **Pesquisador de Objetos** e selecionando **Atribuir Design de Agregação**.</span><span class="sxs-lookup"><span data-stu-id="5daf8-104">You can display the **Assign Aggregation Design** dialog box by right-clicking a partition or aggregation design in **Object Explorer** and selecting **Assign Aggregation Design**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5daf8-105">Opções</span><span class="sxs-lookup"><span data-stu-id="5daf8-105">Options</span></span>  
  
|<span data-ttu-id="5daf8-106">Termo</span><span class="sxs-lookup"><span data-stu-id="5daf8-106">Term</span></span>|<span data-ttu-id="5daf8-107">Definição</span><span class="sxs-lookup"><span data-stu-id="5daf8-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="5daf8-108">**Designs de agregação**</span><span class="sxs-lookup"><span data-stu-id="5daf8-108">**Aggregation designs**</span></span>|<span data-ttu-id="5daf8-109">Selecione um design de agregação para atribuir a uma ou mais partições de destino.</span><span class="sxs-lookup"><span data-stu-id="5daf8-109">Select an aggregation design to assign to one or more destination partitions.</span></span>|  
|<span data-ttu-id="5daf8-110">**Partições de destino**</span><span class="sxs-lookup"><span data-stu-id="5daf8-110">**Destination partitions**</span></span>|<span data-ttu-id="5daf8-111">Selecione as partições às quais deseja atribuir o design de agregação.</span><span class="sxs-lookup"><span data-stu-id="5daf8-111">Select the partitions to which to assign the aggregation design.</span></span> <span data-ttu-id="5daf8-112">A grade seguinte é usada para especificar partições de destino:</span><span class="sxs-lookup"><span data-stu-id="5daf8-112">The following grid is used to specify destination partitions:</span></span><br /><br /> <span data-ttu-id="5daf8-113">\<check box>: Marque ou desmarque a caixa de seleção no cabeçalho da coluna para incluir ou excluir todas as partições listadas como partições de destino.</span><span class="sxs-lookup"><span data-stu-id="5daf8-113">\<check box>: Select or clear the check box in the column header to include or exclude all listed partitions as destination partitions.</span></span> <span data-ttu-id="5daf8-114">Marque ou desmarque uma caixa de seleção próxima a uma partição para incluir ou excluir essa partição como uma partição de destino.</span><span class="sxs-lookup"><span data-stu-id="5daf8-114">Select or clear a check box next to a partition to include or exclude that partition as a destination partition.</span></span><br /><br /> <span data-ttu-id="5daf8-115">**Partição**: exibe o nome da partição.</span><span class="sxs-lookup"><span data-stu-id="5daf8-115">**Partition**: Displays the name of the partition.</span></span><br /><br /> <span data-ttu-id="5daf8-116">**Origem**: exibe a tabela de origem ou a consulta para a partição.</span><span class="sxs-lookup"><span data-stu-id="5daf8-116">**Source**: Displays the source table or query for the partition.</span></span><br /><br /> <span data-ttu-id="5daf8-117">**Design de agregação**: exibe o nome do design de agregação existente para a partição.</span><span class="sxs-lookup"><span data-stu-id="5daf8-117">**Aggregation Design**: Displays the name of the existing aggregation design for the partition.</span></span>|  
|<span data-ttu-id="5daf8-118">**Ocultar partições com designs de agregação**</span><span class="sxs-lookup"><span data-stu-id="5daf8-118">**Hide partitions with aggregation designs**</span></span>|<span data-ttu-id="5daf8-119">Selecione para mostrar só as partições que não têm designs de agregação atribuídos a elas.</span><span class="sxs-lookup"><span data-stu-id="5daf8-119">Select to show only the partitions that do not have aggregation designs assigned to them.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5daf8-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5daf8-120">See Also</span></span>  
 [<span data-ttu-id="5daf8-121">Agregações e designs de agregação</span><span class="sxs-lookup"><span data-stu-id="5daf8-121">Aggregations and Aggregation Designs</span></span>](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
