---
title: Inserir ou excluir uma linha (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b9642af3-b3ae-4f78-b0be-8f96b79fc313
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fdec24801d1fae3b95c7d75acb5a3add650d523b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684518"
---
# <a name="insert-or-delete-a-row-report-builder-and-ssrs"></a><span data-ttu-id="b9e74-102">Inserir ou excluir uma linha (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b9e74-102">Insert or Delete a Row (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b9e74-103">Você pode adicionar ou excluir linhas em uma região de dados tablix.</span><span class="sxs-lookup"><span data-stu-id="b9e74-103">You can add or delete rows in a tablix data region.</span></span> <span data-ttu-id="b9e74-104">Essa região pode ser uma tabela, uma matriz ou uma lista.</span><span class="sxs-lookup"><span data-stu-id="b9e74-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="b9e74-105">Os procedimentos a seguir não se aplicam às regiões de dados de gráficos e medidores.</span><span class="sxs-lookup"><span data-stu-id="b9e74-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="b9e74-106">Na região de dados Tablix, você pode adicionar linhas associadas a um grupo (dentro de um grupo) ou que não estão associadas a um grupo (fora de um grupo).</span><span class="sxs-lookup"><span data-stu-id="b9e74-106">In a tablix data region, you can add rows that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="b9e74-107">Uma linha que está dentro de um grupo é repetida uma vez por valor de grupo único.</span><span class="sxs-lookup"><span data-stu-id="b9e74-107">A row that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="b9e74-108">Por exemplo, uma linha dentro de um grupo com base em valor em uma coluna de dados que contém nomes de cores é repetida uma vez por nome de cor distinto.</span><span class="sxs-lookup"><span data-stu-id="b9e74-108">For example, a row inside a group based on the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="b9e74-109">Para grupos aninhados, uma linha pode estar fora do grupo filho, mas dentro do grupo pai.</span><span class="sxs-lookup"><span data-stu-id="b9e74-109">For nested groups, a row can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="b9e74-110">Nesse caso, a linha se repete uma vez para cada valor único no grupo pai.</span><span class="sxs-lookup"><span data-stu-id="b9e74-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-the-row-and-column-handles-appear"></a><span data-ttu-id="b9e74-111">Para selecionar uma região de dados para que os identificadores de linha e coluna sejam exibidos</span><span class="sxs-lookup"><span data-stu-id="b9e74-111">To select a data region so the row and column handles appear</span></span>  
  
-   <span data-ttu-id="b9e74-112">No modo Design, clique no canto superior esquerdo da região de dados Tablix para que os indicadores de linha e coluna sejam exibidos acima ou próximo dele.</span><span class="sxs-lookup"><span data-stu-id="b9e74-112">In Design view, click the upper left corner of the tablix data region so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="b9e74-113">Para obter mais informações sobre áreas de região de dados, consulte [listas &#40;Construtor de relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b9e74-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-row-in-a-selected-data-region"></a><span data-ttu-id="b9e74-114">Para inserir uma linha em uma região de dados selecionada</span><span class="sxs-lookup"><span data-stu-id="b9e74-114">To insert a row in a selected data region</span></span>  
  
-   <span data-ttu-id="b9e74-115">Clique com o botão direito do mouse no identificador de linha no qual você deseja inserir uma linha, clique em **Inserir Linha**e depois em **Acima** ou **Abaixo**.</span><span class="sxs-lookup"><span data-stu-id="b9e74-115">Right-click a row handle where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
     <span data-ttu-id="b9e74-116">\- ou –</span><span class="sxs-lookup"><span data-stu-id="b9e74-116">\- or -</span></span>  
  
-   <span data-ttu-id="b9e74-117">Clique com o botão direito do mouse em uma célula na região de dados na qual você deseja inserir uma linha, clique em **Inserir Linha**e depois em **Acima** ou **Abaixo**.</span><span class="sxs-lookup"><span data-stu-id="b9e74-117">Right-click a cell in the data region where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
### <a name="to-delete-a-row-from-a-selected-data-region"></a><span data-ttu-id="b9e74-118">Para excluir uma linha de uma região de dados selecionada</span><span class="sxs-lookup"><span data-stu-id="b9e74-118">To delete a row from a selected data region</span></span>  
  
-   <span data-ttu-id="b9e74-119">Selecione uma ou mais linhas a serem excluídas, clique com o botão direito do mouse no identificador de uma das linhas selecionadas e clique em **Excluir Linhas**.</span><span class="sxs-lookup"><span data-stu-id="b9e74-119">Select the row or rows that you want to delete, right-click the handle for one of the rows you selected, and then click **Delete Rows**.</span></span>  
  
     <span data-ttu-id="b9e74-120">\- ou –</span><span class="sxs-lookup"><span data-stu-id="b9e74-120">\- or -</span></span>  
  
-   <span data-ttu-id="b9e74-121">Clique com o botão direito do mouse em uma célula na região de dados na qual você deseja excluir uma linha e clique em **Excluir Linhas**.</span><span class="sxs-lookup"><span data-stu-id="b9e74-121">Right-click a cell in the data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
### <a name="to-insert-a-row-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="b9e74-122">Para inserir uma linha em um grupo em uma região de dados selecionada</span><span class="sxs-lookup"><span data-stu-id="b9e74-122">To insert a row in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="b9e74-123">Clique com o botão direito do mouse em uma célula de grupo de linhas na área de grupo de linhas de uma região de dados Tablix na qual deseja inserir uma linha, clique em **Inserir Linha**e depois em **Acima – Fora do Grupo**, **Acima – Dentro do Grupo**, **Abaixo – Dentro do Grupo**ou **Abaixo – Fora do Grupo**.</span><span class="sxs-lookup"><span data-stu-id="b9e74-123">Right-click a row group cell in the row group area of a tablix data region where you want to insert a row, click **Insert Row**, and then click **Above - Outside Group**, **Above - Inside Group**, **Below - Inside Group**, or **Below - Outside Group**.</span></span>  
  
     <span data-ttu-id="b9e74-124">Uma linha é adicionada dentro ou fora do grupo representado pela célula do grupo de linhas na qual você clicou.</span><span class="sxs-lookup"><span data-stu-id="b9e74-124">A row is added either inside or outside the group represented by the row group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-row-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="b9e74-125">Para excluir uma linha de um grupo em uma região de dados selecionada</span><span class="sxs-lookup"><span data-stu-id="b9e74-125">To delete a row from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="b9e74-126">Clique com o botão direito do mouse em uma célula do grupo de linhas na área do grupo de colunas de uma região de dados Tablix na qual você deseja excluir uma linha e clique em **Excluir Linhas**.</span><span class="sxs-lookup"><span data-stu-id="b9e74-126">Right-click a row group cell in the row group area of a tablix data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9e74-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9e74-127">See Also</span></span>  
 <span data-ttu-id="b9e74-128">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b9e74-128">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b9e74-129">[Noções básicas sobre grupos &#40;Construtor de Relatórios e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b9e74-129">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b9e74-130">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b9e74-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b9e74-131">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b9e74-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b9e74-132">[Listas &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b9e74-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b9e74-133">Listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b9e74-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
