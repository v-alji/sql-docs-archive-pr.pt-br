---
title: Página mover itens (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fc83b8d2-bc79-4b56-8970-34a1cbbcc176
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98ff306caf634a5f0478e2eba03c2313b24be274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684596"
---
# <a name="move-items-page-report-manager"></a><span data-ttu-id="18f1e-102">Página Mover Itens (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="18f1e-102">Move Items Page (Report Manager)</span></span>
  <span data-ttu-id="18f1e-103">Use a página Mover Itens para mover um relatório, pasta ou outro item para um novo local no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="18f1e-103">Use the Move Items page to move a report, folder, or other item to a new location on the report server.</span></span> <span data-ttu-id="18f1e-104">Você pode digitar o caminho do novo local ou usar uma exibição de árvore para procurar um novo local no namespace do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="18f1e-104">You can type the path of the new location or use a tree view to browse to a new location in the report server namespace.</span></span> <span data-ttu-id="18f1e-105">Você só pode mover itens que tem permissão para mover e que estejam armazenados no servidor de relatório atual.</span><span class="sxs-lookup"><span data-stu-id="18f1e-105">You can only move items that you have permission to move and that are stored on the current report server.</span></span>  
  
 <span data-ttu-id="18f1e-106">Quando você move um item referenciado por outro item (por exemplo, uma fonte de dados compartilhada ou um modelo referenciado por muitos relatórios), as informações de caminho desse item são atualizadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="18f1e-106">When you move an item that is referenced by another item (for example, a shared data source or model that is referenced by many reports), the path information for that item is updated automatically.</span></span> <span data-ttu-id="18f1e-107">Mover uma fonte de dados compartilhada não interrompe a conexão da fonte de dados com os relatórios e modelos que ela usa.</span><span class="sxs-lookup"><span data-stu-id="18f1e-107">Moving a shared data source does not disrupt a data source connection to the reports and models that use it.</span></span> <span data-ttu-id="18f1e-108">Se você mover uma fonte de dados compartilhada ou modelo para uma pasta à qual os usuários não têm permissão, eles ainda assim poderão executar qualquer relatório que referencia a fonte de dados ou o modelo, mas o item não estará visível na hierarquia de pasta.</span><span class="sxs-lookup"><span data-stu-id="18f1e-108">If you move a shared data source or model to a folder for which users do not have permission, they will still be able to run any report that references the data source or model, however the item will not be visible to them in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="18f1e-109">Para **Local**, especifique o caminho completo até a pasta, começando com o nome da pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="18f1e-109">For **Location**, specify the full path to folder, beginning with the root folder name.</span></span> <span data-ttu-id="18f1e-110">É possível digitar o nome do caminho ou usar a exibição de árvore para navegar até a pasta desejada.</span><span class="sxs-lookup"><span data-stu-id="18f1e-110">You can type the path name or use the tree view to navigate to the folder you want.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18f1e-111">Nem todos os itens podem ser movidos.</span><span class="sxs-lookup"><span data-stu-id="18f1e-111">Not all items are movable.</span></span> <span data-ttu-id="18f1e-112">Você não pode mover pastas reservadas como Base, Meu Relatórios ou Pastas de Usuários.</span><span class="sxs-lookup"><span data-stu-id="18f1e-112">You cannot move reserved folders such as Home, My Reports, or Users Folders.</span></span> <span data-ttu-id="18f1e-113">Você não pode mover histórico de relatório ou instantâneos para locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="18f1e-113">You cannot move report history or snapshots to different locations.</span></span> <span data-ttu-id="18f1e-114">O histórico e os instantâneos sempre estão localizados no relatório e são acessados por meio do relatório no qual se baseiam.</span><span class="sxs-lookup"><span data-stu-id="18f1e-114">History and snapshots are always located with, and accessed through, the report on which they are based.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="18f1e-115">Navegação</span><span class="sxs-lookup"><span data-stu-id="18f1e-115">Navigation</span></span>  
 <span data-ttu-id="18f1e-116">Use os procedimentos a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="18f1e-116">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-details-view"></a><span data-ttu-id="18f1e-117">Para abrir a página Mover Itens na página Conteúdo em Exibição de Detalhes</span><span class="sxs-lookup"><span data-stu-id="18f1e-117">To open the Move Items page from the Contents page in Details View</span></span>  
  
1.  <span data-ttu-id="18f1e-118">Abra o Gerenciador de Relatórios e navegue até a pasta que contém um item que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="18f1e-118">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="18f1e-119">Você também pode mover itens da Página inicial do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="18f1e-119">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="18f1e-120">Na barra de ferramentas, clique em **Exibição de Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="18f1e-120">In the toolbar, click **Details View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18f1e-121"> Caso você veja apenas **Exibição Lado a Lado**, já estará em **Exibição de Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="18f1e-121">If you see only **Tiles View**, you are already in **Details View**.</span></span>  
  
3.  <span data-ttu-id="18f1e-122">Marque a caixa ao lado de um item e clique em **Mover** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="18f1e-122">Select the box next to an item, and then click **Move** in the toolbar.</span></span> <span data-ttu-id="18f1e-123">Você poderá selecionar mais de uma caixa se desejar mover vários itens para o mesmo local novo.</span><span class="sxs-lookup"><span data-stu-id="18f1e-123">You can select more than one box if you want to move multiple items to the same new location.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-tiles-view"></a><span data-ttu-id="18f1e-124">Para abrir a página Mover Itens na página Conteúdo em Exibição Lado a Lado</span><span class="sxs-lookup"><span data-stu-id="18f1e-124">To open the Move Items page from the Contents page in Tiles View</span></span>  
  
1.  <span data-ttu-id="18f1e-125">Abra o Gerenciador de Relatórios e navegue até a pasta que contém um item que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="18f1e-125">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="18f1e-126">Você também pode mover itens da Página inicial do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="18f1e-126">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="18f1e-127">Na barra de ferramentas, clique em **Exibição Lado a Lado**.</span><span class="sxs-lookup"><span data-stu-id="18f1e-127">In the toolbar, click **Tiles View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18f1e-128"> Caso você veja apenas **Exibição de Detalhes**, já estará em **Exibição Lado a lado**.</span><span class="sxs-lookup"><span data-stu-id="18f1e-128">If you see only **Details View**, you are already in **Tiles View**.</span></span>  
  
3.  <span data-ttu-id="18f1e-129">Focalize um item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="18f1e-129">Hover over an item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="18f1e-130">No menu suspenso, clique em **Mover**.</span><span class="sxs-lookup"><span data-stu-id="18f1e-130">In the drop-down menu, click **Move**.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-general-properties-page-of-an-item"></a><span data-ttu-id="18f1e-131">Para abrir a página Mover Itens na página Propriedades Gerais de um item</span><span class="sxs-lookup"><span data-stu-id="18f1e-131">To open the Move Items page from the General Properties page of an item</span></span>  
  
1.  <span data-ttu-id="18f1e-132">Abra o Gerenciador de Relatórios e navegue até a pasta que contém um item que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="18f1e-132">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="18f1e-133">Você também pode mover itens da Página inicial do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="18f1e-133">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="18f1e-134">Focalize um item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="18f1e-134">Hover over an item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="18f1e-135">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="18f1e-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="18f1e-136">Esse procedimento abre a página Propriedades Gerais de um item.</span><span class="sxs-lookup"><span data-stu-id="18f1e-136">This opens the General properties page for an item.</span></span>  
  
4.  <span data-ttu-id="18f1e-137">Na barra de ferramentas de item, clique **Mover**.</span><span class="sxs-lookup"><span data-stu-id="18f1e-137">In the item toolbar, click **Move**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f1e-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18f1e-138">See Also</span></span>  
 <span data-ttu-id="18f1e-139">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="18f1e-139">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="18f1e-140">[Página Propriedades gerais, pastas &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="18f1e-140">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="18f1e-141">[Página Propriedades gerais, relatórios &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="18f1e-141">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="18f1e-142">[Página Propriedades gerais, recursos &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="18f1e-142">[General Properties Page, Resources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span></span>  
 <span data-ttu-id="18f1e-143">[Página Propriedades gerais, fontes de dados compartilhadas &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="18f1e-143">[General Properties Page, Shared Data Sources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span></span>  
 [<span data-ttu-id="18f1e-144">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="18f1e-144">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
