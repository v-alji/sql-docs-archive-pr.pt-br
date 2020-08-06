---
title: Mover ou excluir um item (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- moving items
- items [Reporting Services], moving
ms.assetid: 980a66c7-a18b-4af7-8954-45726fa517d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a61ad56ea9e20e7fdf38d5acf05529b685ee896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678578"
---
# <a name="move-or-delete-an-item-report-manager"></a><span data-ttu-id="746e0-102">Mover ou excluir um item (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="746e0-102">Move or Delete an Item (Report Manager)</span></span>
  <span data-ttu-id="746e0-103">Relatórios e itens de relatório que você publica em um servidor de relatório são armazenados em pastas.</span><span class="sxs-lookup"><span data-stu-id="746e0-103">Reports and report-related items that you publish to a report server are stored in folders.</span></span> <span data-ttu-id="746e0-104">Você pode mover itens para uma pasta diferente e as referências a esses itens são mantidas automaticamente pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="746e0-104">You can move items to a different folder and references to those items are maintained automatically by the report server.</span></span> <span data-ttu-id="746e0-105">Antes de excluir um item, verifique se outros itens dependem dele.</span><span class="sxs-lookup"><span data-stu-id="746e0-105">Before you delete an item, consider whether other items depend on it.</span></span>  
  
## <a name="move-an-item"></a><span data-ttu-id="746e0-106">Mover um item</span><span class="sxs-lookup"><span data-stu-id="746e0-106">Move an Item</span></span>  
 <span data-ttu-id="746e0-107">Você pode mover itens do servidor de relatório para locais de pasta diferentes na hierarquia de pastas do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="746e0-107">You can move report server items to different folder locations in the report server folder hierarchy.</span></span> <span data-ttu-id="746e0-108">Quando você move um item, todas as propriedades (inclusive configurações de segurança) são movidas com o item para o novo local.</span><span class="sxs-lookup"><span data-stu-id="746e0-108">When you move an item, all properties (including security settings) move with the item to the new location.</span></span> <span data-ttu-id="746e0-109">Ao mover uma pasta, todos os itens na pasta são movidos juntos.</span><span class="sxs-lookup"><span data-stu-id="746e0-109">When you move a folder, all the items in the folder move with it.</span></span>  
  
 <span data-ttu-id="746e0-110">No Gerenciador de Relatórios, os itens que podem ser movidos estão indicados na hierarquia de pasta.</span><span class="sxs-lookup"><span data-stu-id="746e0-110">In Report Manager, the items that you can move are indicated in the folder hierarchy.</span></span> <span data-ttu-id="746e0-111">A tabela a seguir mostra o ícone para cada item móvel.</span><span class="sxs-lookup"><span data-stu-id="746e0-111">The following table shows the icon for each movable item.</span></span>  
  
|<span data-ttu-id="746e0-112">ícone</span><span class="sxs-lookup"><span data-stu-id="746e0-112">Icon</span></span>|<span data-ttu-id="746e0-113">Item móvel</span><span class="sxs-lookup"><span data-stu-id="746e0-113">Moveable item</span></span>|  
|----------|-------------------|  
|<span data-ttu-id="746e0-114">![Report icon](../media/hlp-16doc.gif "Ícone do relatório")</span><span class="sxs-lookup"><span data-stu-id="746e0-114">![Report icon](../media/hlp-16doc.gif "Report icon")</span></span>|<span data-ttu-id="746e0-115">Relatório</span><span class="sxs-lookup"><span data-stu-id="746e0-115">Report</span></span>|  
|<span data-ttu-id="746e0-116">![Ícone do relatório vinculado](../media/hlp-16linked.gif "Ícone do relatório vinculado")</span><span class="sxs-lookup"><span data-stu-id="746e0-116">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>|<span data-ttu-id="746e0-117">Relatório vinculado</span><span class="sxs-lookup"><span data-stu-id="746e0-117">Linked report</span></span>|  
|<span data-ttu-id="746e0-118">![Ícone de pasta](../media/hlp-16folder.gif "Ícone de pasta")</span><span class="sxs-lookup"><span data-stu-id="746e0-118">![Folder icon](../media/hlp-16folder.gif "Folder icon")</span></span>|<span data-ttu-id="746e0-119">Pasta</span><span class="sxs-lookup"><span data-stu-id="746e0-119">Folder</span></span>|  
|<span data-ttu-id="746e0-120">![ícone de recurso genérico](../media/hlp-16file.gif "ícone de recurso genérico")</span><span class="sxs-lookup"><span data-stu-id="746e0-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon")</span></span>|<span data-ttu-id="746e0-121">Recurso genérico</span><span class="sxs-lookup"><span data-stu-id="746e0-121">Generic resource</span></span>|  
|<span data-ttu-id="746e0-122">![Shared data source icon](../media/hlp-16datasource.png "Ícone da fonte de dados compartilhada")</span><span class="sxs-lookup"><span data-stu-id="746e0-122">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>|<span data-ttu-id="746e0-123">Fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="746e0-123">Shared data source</span></span>|  
||<span data-ttu-id="746e0-124">Conjunto de dados compartilhado</span><span class="sxs-lookup"><span data-stu-id="746e0-124">Shared dataset</span></span>|  
  
 <span data-ttu-id="746e0-125">Nem todos os itens com os quais você trabalha podem ser movidos.</span><span class="sxs-lookup"><span data-stu-id="746e0-125">Not all items that you work with can be moved.</span></span> <span data-ttu-id="746e0-126">Não é possível mover itens associados a um relatório, como assinaturas ou histórico de relatório.</span><span class="sxs-lookup"><span data-stu-id="746e0-126">You cannot move items that are associated with a report, such as subscriptions or report history.</span></span> <span data-ttu-id="746e0-127">Esses itens são movidos com os seus relatórios associados.</span><span class="sxs-lookup"><span data-stu-id="746e0-127">Those items move with their associated reports.</span></span> <span data-ttu-id="746e0-128">De maneira semelhante, não é possível mover itens, como agendas compartilhadas, que existem fora da hierarquia de pasta.</span><span class="sxs-lookup"><span data-stu-id="746e0-128">Similarly, you cannot move items, such as shared schedules, that exist outside of the folder hierarchy.</span></span> <span data-ttu-id="746e0-129">Não é possível mover itens sem a devida permissão.</span><span class="sxs-lookup"><span data-stu-id="746e0-129">You cannot move items if you lack permission to do so.</span></span> <span data-ttu-id="746e0-130">A permissão para mover um item é concedida quando as seguintes tarefas são selecionadas na atribuição de função para o item em questão: "Gerenciar relatórios," "Gerenciar modelos", "Gerenciar pastas" e "Gerenciar fontes de dados".</span><span class="sxs-lookup"><span data-stu-id="746e0-130">Permission to move an item is conveyed when the following tasks are selected in your role assignment for the item in question: "Manage reports," "Manage models", "Manage folders," and "Manage data sources."</span></span>  
  
#### <a name="to-move-an-item-from-within-the-contents-page"></a><span data-ttu-id="746e0-131">Para mover um item de dentro da página Conteúdo</span><span class="sxs-lookup"><span data-stu-id="746e0-131">To move an item from within the Contents page</span></span>  
  
1.  <span data-ttu-id="746e0-132">Inicie o [Report Manager &#40;o modo nativo do SSRS&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="746e0-132">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="746e0-133">No Gerenciador de Relatórios, navegue até a página **Conteúdo** e localize o item que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="746e0-133">In Report Manager, navigate to the **Contents** page, and locate the item that you want to move.</span></span>  
  
3.  <span data-ttu-id="746e0-134">Focalize o item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="746e0-134">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="746e0-135">No menu suspenso, clique em **Mover**.</span><span class="sxs-lookup"><span data-stu-id="746e0-135">In the drop-down menu, click **Move**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="746e0-136">Para **Localização**, especifique a pasta para a qual você deseja mover o item.</span><span class="sxs-lookup"><span data-stu-id="746e0-136">For **Location**, specify the folder you want to move the item to.</span></span> <span data-ttu-id="746e0-137">É possível digitar o nome de pasta totalmente qualificado ou usar o controle de árvore para navegar até a pasta.</span><span class="sxs-lookup"><span data-stu-id="746e0-137">You can type the fully qualified folder name or use the tree control to navigate to the folder.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="746e0-138">Como alternativa, navegue até o objeto que você deseja mover, clique em **Propriedades**e clique em **Mover** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="746e0-138">Alternatively, you can navigate to the object you want to move, click **Properties**, and then click **Move** at the top of the page.</span></span>  
  
## <a name="delete-an-item"></a><span data-ttu-id="746e0-139">Excluir um item</span><span class="sxs-lookup"><span data-stu-id="746e0-139">Delete an item</span></span>  
 <span data-ttu-id="746e0-140">Antes de excluir um item, determine se ele é usado por outros itens.</span><span class="sxs-lookup"><span data-stu-id="746e0-140">Before you delete an item, determine if it is used by other items.</span></span> <span data-ttu-id="746e0-141">Por exemplo, se você excluir uma fonte de dados compartilhada, relatórios e modelos que usam essa fonte de dados não serão mais executados.</span><span class="sxs-lookup"><span data-stu-id="746e0-141">For example, if you delete a shared data source, reports and models that use that data source will no longer run.</span></span> <span data-ttu-id="746e0-142">Se um relatório for excluído, as assinaturas e o histórico de relatórios associados também são excluídos.</span><span class="sxs-lookup"><span data-stu-id="746e0-142">If you delete a report, subscriptions and report history associated with that report are also deleted.</span></span> <span data-ttu-id="746e0-143">Para localizar itens dependentes de um item, consulte [página de itens dependentes &#40;Report Manager&#41;].. /dependent-items-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="746e0-143">To find dependent items for an item, see [Dependent Items Page &#40;Report Manager&#41;]../dependent-items-page-report-manager.md).</span></span>  
  
#### <a name="to-delete-a-report-or-item"></a><span data-ttu-id="746e0-144">Para excluir um relatório ou item</span><span class="sxs-lookup"><span data-stu-id="746e0-144">To delete a report or item</span></span>  
  
1.  <span data-ttu-id="746e0-145">Inicie o [Report Manager &#40;o modo nativo do SSRS&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="746e0-145">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="746e0-146">No Gerenciador de Relatórios, navegue até a página **Conteúdo** e localize o item que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="746e0-146">In Report Manager, navigate to the **Contents** page, and locate the item that you want to delete.</span></span>  
  
3.  <span data-ttu-id="746e0-147">Focalize o item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="746e0-147">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="746e0-148">No menu suspenso, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="746e0-148">In the drop-down menu, click **Delete**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="746e0-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="746e0-149">See Also</span></span>  
 <span data-ttu-id="746e0-150">[Página de conteúdo &#40;Report Manager&#41;].. /contents-page-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="746e0-150">[Contents Page &#40;Report Manager&#41;]../contents-page-report-manager.md)</span></span>   
 [<span data-ttu-id="746e0-151">Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="746e0-151">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
