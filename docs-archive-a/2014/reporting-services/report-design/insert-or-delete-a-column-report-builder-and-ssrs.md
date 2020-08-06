---
title: Inserir ou excluir uma coluna (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9db79e2-7e7d-4359-a706-cb746c94182a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9a6f782dbb6cc1024583926aafe4bab1cfe2d042
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684521"
---
# <a name="insert-or-delete-a-column-report-builder-and-ssrs"></a><span data-ttu-id="1ee85-102">Inserir ou excluir uma coluna (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1ee85-102">Insert or Delete a Column (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1ee85-103">É possível adicionar ou excluir colunas em uma região de dados tablix.</span><span class="sxs-lookup"><span data-stu-id="1ee85-103">You can add or delete columns in a tablix data region.</span></span> <span data-ttu-id="1ee85-104">Essa região pode ser uma tabela, uma matriz ou uma lista.</span><span class="sxs-lookup"><span data-stu-id="1ee85-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="1ee85-105">Os procedimentos a seguir não se aplicam às regiões de dados de gráficos e medidores.</span><span class="sxs-lookup"><span data-stu-id="1ee85-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="1ee85-106">Em uma região de dados tablix, é possível adicionar colunas associadas a um grupo (dentro de um grupo) ou que não estejam associadas a um grupo (fora de um grupo).</span><span class="sxs-lookup"><span data-stu-id="1ee85-106">In a tablix data region, you can add columns that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="1ee85-107">Uma coluna que está dentro de um grupo é repetida uma vez por valor de grupo único.</span><span class="sxs-lookup"><span data-stu-id="1ee85-107">A column that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="1ee85-108">Por exemplo, uma coluna dentro de um grupo com base em valor em uma coluna de dados que contém nomes de cores é repetida uma vez por nome de cor distinto.</span><span class="sxs-lookup"><span data-stu-id="1ee85-108">For example, a column inside a group based the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="1ee85-109">Para grupos aninhados, uma coluna pode estar fora do grupo filho, mas dentro do grupo pai.</span><span class="sxs-lookup"><span data-stu-id="1ee85-109">For nested groups, a column can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="1ee85-110">Nesse caso, a linha se repete uma vez para cada valor único no grupo pai.</span><span class="sxs-lookup"><span data-stu-id="1ee85-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-that-the-row-and-column-handles-appear"></a><span data-ttu-id="1ee85-111">Para selecionar uma região de dados para que os identificadores de linha e coluna sejam exibidos</span><span class="sxs-lookup"><span data-stu-id="1ee85-111">To select a data region so that the row and column handles appear</span></span>  
  
-   <span data-ttu-id="1ee85-112">Na exibição de Design, clique no canto superior esquerdo da região de dados tablix para que os indicadores de coluna e linha sejam exibidos acima e ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="1ee85-112">In Design view, click the upper left corner of the tablix data region, so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="1ee85-113">Para obter mais informações sobre áreas de região de dados, consulte [listas &#40;Construtor de relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1ee85-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-column-in-a-selected-data-region"></a><span data-ttu-id="1ee85-114">Para inserir uma coluna em uma região de dados selecionada</span><span class="sxs-lookup"><span data-stu-id="1ee85-114">To insert a column in a selected data region</span></span>  
  
-   <span data-ttu-id="1ee85-115">Clique com o botão direito do mouse na alça da coluna na qual você deseja inserir uma coluna, clique em **Inserir Coluna**e depois em **Esquerda** ou **Direita**.</span><span class="sxs-lookup"><span data-stu-id="1ee85-115">Right-click a column handle where you want to insert a column, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
     <span data-ttu-id="1ee85-116">-- ou --</span><span class="sxs-lookup"><span data-stu-id="1ee85-116">-- or --</span></span>  
  
-   <span data-ttu-id="1ee85-117">Clique com o botão direito do mouse em uma célula na região de dados na qual você deseja inserir uma linha, clique em **Inserir Coluna**e depois em **Esquerda** ou **Direita**.</span><span class="sxs-lookup"><span data-stu-id="1ee85-117">Right-click a cell in the data region where you want to insert a row, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
### <a name="to-delete-a-column-from-a-selected-data-region"></a><span data-ttu-id="1ee85-118">Para excluir uma coluna de uma região de dados selecionada</span><span class="sxs-lookup"><span data-stu-id="1ee85-118">To delete a column from a selected data region</span></span>  
  
-   <span data-ttu-id="1ee85-119">Selecione uma ou mais colunas que deseja excluir, clique com o botão direito do mouse na alça de uma das colunas selecionadas e clique em **Excluir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="1ee85-119">Select the column or columns that you want to delete, right-click the handle for one of the columns you selected, and then click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="1ee85-120">-- ou --</span><span class="sxs-lookup"><span data-stu-id="1ee85-120">-- or --</span></span>  
  
-   <span data-ttu-id="1ee85-121">Clique com o botão direito do mouse em uma célula na região de dados na qual você deseja excluir uma coluna e clique em **Excluir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="1ee85-121">Right-click a cell in the data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
### <a name="to-insert-a-column-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="1ee85-122">Para inserir uma coluna em um grupo em uma região de dados selecionada</span><span class="sxs-lookup"><span data-stu-id="1ee85-122">To insert a column in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="1ee85-123">Clique com o botão direito do mouse em uma célula do grupo de colunas, na área do grupo de colunas de uma região de dados tablix na qual você deseja inserir uma coluna, clique em **Inserir Coluna**e em **Esquerda – Fora do Grupo**, **Esquerda – Dentro do Grupo**, **Direita – Dentro do Grupo**ou **Direita – Fora do Grupo**.</span><span class="sxs-lookup"><span data-stu-id="1ee85-123">Right-click a column group cell in the column group area of a tablix data region where you want to insert a column, click **Insert Column**, and then click **Left - Outside Group**, **Left - Inside Group**, **Right - Inside Group**, or **Right - Outside Group**.</span></span>  
  
     <span data-ttu-id="1ee85-124">Uma coluna é adicionada dentro ou fora do grupo representado pela célula do grupo de colunas na qual você clicou.</span><span class="sxs-lookup"><span data-stu-id="1ee85-124">A column is added either inside or outside the group represented by the column group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-column-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="1ee85-125">Para excluir uma coluna de um grupo em uma região de dados selecionada</span><span class="sxs-lookup"><span data-stu-id="1ee85-125">To delete a column from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="1ee85-126">Clique com o botão direito do mouse em uma célula do grupo de colunas, na área do grupo de colunas de uma região de dados tablix na qual você deseja excluir uma coluna, e clique em **Excluir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="1ee85-126">Right-click a column group cell in the column group area of a tablix data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee85-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ee85-127">See Also</span></span>  
 <span data-ttu-id="1ee85-128">[Noções básicas sobre grupos &#40;Construtor de Relatórios e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ee85-128">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1ee85-129">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ee85-129">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1ee85-130">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ee85-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1ee85-131">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ee85-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1ee85-132">[Listas &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ee85-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1ee85-133">Listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1ee85-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
