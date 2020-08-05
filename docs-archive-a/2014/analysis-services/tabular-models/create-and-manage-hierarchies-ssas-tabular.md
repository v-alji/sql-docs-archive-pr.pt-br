---
title: Criar e gerenciar hierarquias (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8dd30cd0-a831-4d25-b577-648d7f3c7fa6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0bab3e09aadb4e0c857b9c1da3111e03e90f777e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572216"
---
# <a name="create-and-manage-hierarchies-ssas-tabular"></a><span data-ttu-id="401db-102">Criar e Gerenciar hierarquias (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="401db-102">Create and Manage Hierarchies (SSAS Tabular)</span></span>
  <span data-ttu-id="401db-103">As hierarquias podem ser criadas e gerenciadas no designer modelo em Exibição de Diagrama.</span><span class="sxs-lookup"><span data-stu-id="401db-103">Hierarchies can be created and managed in the model designer, in Diagram View.</span></span> <span data-ttu-id="401db-104">Par exibir o designer de modelos na Exibição de Diagrama no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique no menu **Model** , aponte para **Exibição de Modelo**e clique em **Exibição de Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="401db-104">To view the model designer in Diagram View, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
 <span data-ttu-id="401db-105">Este tópico inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="401db-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="401db-106">Criar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-106">Create a Hierarchy</span></span>](#bkmk_create)  
  
-   [<span data-ttu-id="401db-107">Editar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-107">Edit a Hierarchy</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="401db-108">Excluir uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-108">Delete a Hierarchy</span></span>](#bkmk_delete)  
  
##  <a name="create-a-hierarchy"></a><a name="bkmk_create"></a> <span data-ttu-id="401db-109">Criar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-109">Create a Hierarchy</span></span>  
 <span data-ttu-id="401db-110">Você pode criar uma hierarquia usando as colunas e o menu de contexto de tabela.</span><span class="sxs-lookup"><span data-stu-id="401db-110">You can create a hierarchy by using the columns and table context menu.</span></span> <span data-ttu-id="401db-111">Quando você criar uma hierarquia, um novo nível pai é exibido com as colunas selecionadas como níveis filho.</span><span class="sxs-lookup"><span data-stu-id="401db-111">When you create a hierarchy, a new parent level displays with selected columns as child levels.</span></span>  
  
#### <a name="to-create-a-hierarchy-from-the-context-menu"></a><span data-ttu-id="401db-112">Para criar uma hierarquia no menu de contexto</span><span class="sxs-lookup"><span data-stu-id="401db-112">To create a hierarchy from the context menu</span></span>  
  
1.  <span data-ttu-id="401db-113">No designer modelo (Exibição de Diagrama), em uma janela de tabela, clique com o botão direito do mouse em uma coluna e clique em **Criar Hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="401db-113">In the model designer (Diagram View), in a table window, right-click on a column, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="401db-114">Para selecionar várias colunas, clique em cada coluna, clique com o botão direito do mouse para abrir o menu de contexto e clique em **Criar Hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="401db-114">To select multiple columns, click each column, then right-click to open the context menu, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="401db-115">Um nível de hierarquia pai é criado na parte inferior da janela da tabela e as colunas selecionadas são copiadas sob a hierarquia como níveis filho.</span><span class="sxs-lookup"><span data-stu-id="401db-115">A parent hierarchy level is created at the bottom of the table window and the selected columns are copied under the hierarchy as child levels.</span></span>  
  
2.  <span data-ttu-id="401db-116">Digite um nome para a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-116">Type a name for the hierarchy.</span></span>  
  
 <span data-ttu-id="401db-117">Você pode arrastar colunas adicionais para o nível pai da hierarquia, que copia as colunas.</span><span class="sxs-lookup"><span data-stu-id="401db-117">You can drag additional columns into your hierarchy's parent level, which copies the columns.</span></span> <span data-ttu-id="401db-118">Remova o nível filho para colocá-lo onde você desejar que ele seja exibido na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-118">Drop the child level to place it where you want it to appear in the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="401db-119">O comando Criar Hierarquia estará desabilitado no menu de contexto se você fizer multisseleção de uma medida junto com uma ou mais colunas, ou se você selecionar colunas de várias tabelas.</span><span class="sxs-lookup"><span data-stu-id="401db-119">The Create Hierarchy command is disabled in the context menu if you multi-select a measure along with one or more columns or you select columns from multiple tables.</span></span>  
  
##  <a name="edit-a-hierarchy"></a><a name="bkmk_edit"></a><span data-ttu-id="401db-120">Editar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-120">Edit a Hierarchy</span></span>  
 <span data-ttu-id="401db-121">Você pode renomear uma hierarquia, renomear um nível filho, alterar a ordem dos níveis filho, adicionar colunas adicionais como níveis filho, remover um nível filho de uma hierarquia, mostrar o nome de origem de um nível filho (o nome da coluna) e ocultar um nível filho se tiver o mesmo nome como o nível pai da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-121">You can rename a hierarchy, rename a child level, change the order of the child levels, add additional columns as child levels, remove a child level from a hierarchy, show the source name of a child level (the column name), and hide a child level if it has the same name as the hierarchy parent level.</span></span>  
  
#### <a name="to-change-the-name-of-a-hierarchy-or-child-level"></a><span data-ttu-id="401db-122">Para alterar o nome de uma hierarquia ou nível filho</span><span class="sxs-lookup"><span data-stu-id="401db-122">To change the name of a hierarchy or child level</span></span>  
  
1.  <span data-ttu-id="401db-123">Clique com o botão direito do mouse no nível pai ou nível filho da hierarquia e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="401db-123">Right-click the hierarchy parent level or a child level, and the click **Rename**.</span></span>  
  
2.  <span data-ttu-id="401db-124">Digite um novo nome ou edite o nome existente.</span><span class="sxs-lookup"><span data-stu-id="401db-124">Type a new name or edit the existing name.</span></span>  
  
#### <a name="to-change-the-order-of-a-child-level-in-a-hierarchy"></a><span data-ttu-id="401db-125">Para alterar a ordem de um nível filho em uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-125">To change the order of a child level in a hierarchy</span></span>  
  
-   <span data-ttu-id="401db-126">Clique e arraste um nível filho para uma nova posição na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-126">Click and drag a child level into a new position in the hierarchy.</span></span>  
  
-   <span data-ttu-id="401db-127">Ou clique com o botão direito em um nível filho da hierarquia e clique em Mover para Cima para mover o nível na lista ou clique em Mover para Baixo para mover para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="401db-127">Or, right-click a child level of the hierarchy, and then click Move Up to move the level up in the list, or click Move Down to move the level down in the list.</span></span>  
  
-   <span data-ttu-id="401db-128">Ou clique em um nível filho para selecioná-lo e pressione Alt + Seta para Cima para mover o nível para cima, ou pressione Alt + Seta para Baixo para mover o nível para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="401db-128">Or, click a child level to select it, and then press Alt + Up Arrow to move the level up, or press Alt+Down Arrow to move the level down in the list.</span></span>  
  
#### <a name="to-add-another-child-level-to-a-hierarchy"></a><span data-ttu-id="401db-129">Para adicionar outro nível filho a uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-129">To add another child level to a hierarchy</span></span>  
  
-   <span data-ttu-id="401db-130">Clique e arraste uma coluna para o nível pai ou um local específico da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-130">Click and drag a column onto the parent level or into a specific location of the hierarchy.</span></span> <span data-ttu-id="401db-131">A coluna é copiada como um nível filho da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-131">The column is copied as a child level of the hierarchy.</span></span>  
  
-   <span data-ttu-id="401db-132">Ou clique com o botão direito do mouse em uma coluna, aponte para **Adicionar à Hierarquia**e clique na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-132">Or, right-click a column, point to **Add to Hierarchy**, and then click the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="401db-133">Você pode adicionar uma coluna oculta (uma coluna que é oculta de relatórios) como um nível filho à hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-133">You can add a hidden column (a column that is hidden from reports) as a child level to the hierarchy.</span></span> <span data-ttu-id="401db-134">O nível filho não está oculto.</span><span class="sxs-lookup"><span data-stu-id="401db-134">The child level is not hidden.</span></span>  
  
#### <a name="to-remove-a-child-level-from-a-hierarchy"></a><span data-ttu-id="401db-135">Para remover um nível filho de uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-135">To remove a child level from a hierarchy</span></span>  
  
-   <span data-ttu-id="401db-136">Clique com o botão direito do mouse no nível filho e clique em **Remover da Hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="401db-136">Right-click a child level, and then click **Remove from Hierarchy**.</span></span>  
  
-   <span data-ttu-id="401db-137">Ou clique no nível filho e pressione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="401db-137">Or, click a child level, and then press **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="401db-138">Se você renomear um nível filho da hierarquia, ele não mais terá o mesmo nome que a coluna da qual foi copiado.</span><span class="sxs-lookup"><span data-stu-id="401db-138">If you rename a hierarchy child level, it no longer shares the same name as the column that it is copied from.</span></span> <span data-ttu-id="401db-139">Use o comando **Mostrar Nome de Origem** para ver de qual coluna ela foi copiada.</span><span class="sxs-lookup"><span data-stu-id="401db-139">Use the **Show Source Name** command to see which column it was copied from.</span></span>  
  
#### <a name="to-show-a-source-name"></a><span data-ttu-id="401db-140">Para mostrar um nome de origem</span><span class="sxs-lookup"><span data-stu-id="401db-140">To show a source name</span></span>  
  
-   <span data-ttu-id="401db-141">Clique com o botão direito do mouse no nível filho da hierarquia e clique em **Show Source Name (Mostrar Nome de Origem)**.</span><span class="sxs-lookup"><span data-stu-id="401db-141">Right-click a hierarchy child level, and then click **Show Source Name**.</span></span> <span data-ttu-id="401db-142">O nome da coluna da qual ela foi copiada é exibido.</span><span class="sxs-lookup"><span data-stu-id="401db-142">The name of the column that it was copied from appears.</span></span>  
  
##  <a name="delete-a-hierarchy"></a><a name="bkmk_delete"></a><span data-ttu-id="401db-143">Excluir uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="401db-143">Delete a Hierarchy</span></span>  
  
#### <a name="to-delete-a-hierarchy-and-remove-its-child-levels"></a><span data-ttu-id="401db-144">Para excluir uma hierarquia e remover seus níveis filho</span><span class="sxs-lookup"><span data-stu-id="401db-144">To delete a hierarchy and remove its child levels</span></span>  
  
-   <span data-ttu-id="401db-145">Clique com o botão direito no nível pai da hierarquia e clique em Excluir Hierarquia.</span><span class="sxs-lookup"><span data-stu-id="401db-145">Right-click the parent hierarchy level, and then click Delete Hierarchy.</span></span>  
  
-   <span data-ttu-id="401db-146">Ou clique no nível pai da hierarquia e pressione Excluir.</span><span class="sxs-lookup"><span data-stu-id="401db-146">Or, click the parent hierarchy level, and then press Delete.</span></span> <span data-ttu-id="401db-147">Isto também remove todos os níveis filho.</span><span class="sxs-lookup"><span data-stu-id="401db-147">This also removes all the child levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401db-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="401db-148">See Also</span></span>  
 <span data-ttu-id="401db-149">[Designer de modelo de tabela &#40;SSAS de tabela&#41;](../tabular-model-designer-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="401db-149">[Tabular Model Designer &#40;SSAS Tabular&#41;](../tabular-model-designer-ssas-tabular.md) </span></span>  
 <span data-ttu-id="401db-150">[Hierarquias &#40;SSAS de tabela&#41;](hierarchies-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="401db-150">[Hierarchies &#40;SSAS Tabular&#41;](hierarchies-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="401db-151">Medidas &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="401db-151">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
