---
title: Adicionar um grupo de detalhes (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ef8efba-6d48-4aeb-a3b9-a02ba5a44614
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 24b1f6af1aaf336a69a0068636ced60c364e556d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573775"
---
# <a name="add-a-details-group-report-builder-and-ssrs"></a><span data-ttu-id="0d5aa-102">Adicionar um grupo de detalhes (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="0d5aa-102">Add a Details Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0d5aa-103">Os dados de detalhes de um conjunto de dados de relatório são especificados como um grupo sem expressão de grupo.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-103">The detail data from a report dataset is specified as a group with no group expression.</span></span> <span data-ttu-id="0d5aa-104">Adicione um grupo de detalhes a uma região de dados tablix existente quando desejar exibir os dados de detalhes para uma matriz. Adicione dados de detalhes novamente que você excluiu de uma tabela ou lista ou para adicionar grupos de detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-104">Add a detail group to an existing tablix data region when you want to display the detail data for a matrix, add back detail data that you have deleted from a table or list, or to add additional detail groups.</span></span> <span data-ttu-id="0d5aa-105">Para obter mais informações sobre grupos, consulte [Noções básicas sobre grupos &#40;Construtor de Relatórios e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0d5aa-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="0d5aa-106">Para adicionar um grupo de detalhes a uma região de dados tablix</span><span class="sxs-lookup"><span data-stu-id="0d5aa-106">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="0d5aa-107">Na superfície de design, clique em qualquer lugar em uma região de dados tablix para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-107">On the design surface, click anywhere in a tablix data region to select it.</span></span> <span data-ttu-id="0d5aa-108">O painel Agrupamento exibe os grupos de linhas e colunas dessa região de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-108">The Grouping pane displays the row and column groups for the selected data region.</span></span>  
  
2.  <span data-ttu-id="0d5aa-109">No painel Agrupamento, clique com o botão direito do mouse em um grupo que seja o grupo filho mais interno.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-109">In the Grouping pane, right-click a group that is an innermost child group.</span></span> <span data-ttu-id="0d5aa-110">Clique em **Adicionar Grupo**e em **Grupo Filho**.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-110">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="0d5aa-111">A caixa de diálogo **Grupo Tablix** é aberta.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-111">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="0d5aa-112">Em **Expressão de Grupo**, deixe a expressão em branco.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-112">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="0d5aa-113">Um grupo de detalhes não tem nenhuma expressão.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-113">A details group has no expression.</span></span>  
  
4.  <span data-ttu-id="0d5aa-114">Selecione **Mostrar dados de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-114">Select **Show detail data**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="0d5aa-115">Um novo grupo de detalhes é adicionado como um grupo filho ao painel Agrupamento e o identificador da linha do grupo selecionado na etapa 1 exibe o ícone do grupo de detalhes.</span><span class="sxs-lookup"><span data-stu-id="0d5aa-115">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="0d5aa-116">Para obter mais informações sobre identificadores, consulte [Células, linhas e colunas da região de dados Tablix &#40;Construtor de Relatórios&#41; e SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0d5aa-116">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5aa-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d5aa-117">See Also</span></span>  
 <span data-ttu-id="0d5aa-118">[Adicionar ou excluir um grupo em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d5aa-118">[Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d5aa-119">[Noções básicas sobre grupos &#40;Construtor de Relatórios e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d5aa-119">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d5aa-120">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d5aa-120">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d5aa-121">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d5aa-121">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d5aa-122">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d5aa-122">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d5aa-123">[Lista &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d5aa-123">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0d5aa-124">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0d5aa-124">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
