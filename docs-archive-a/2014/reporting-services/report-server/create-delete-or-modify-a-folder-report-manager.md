---
title: Criar, excluir ou modificar uma pasta (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing folders
- modifying folders
- deleting folders
- folders [Reporting Services], creating
- folders [Reporting Services], deleting
- folders [Reporting Services], modifying
ms.assetid: d62159a8-ec67-4e28-a9f1-05a9250065bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bd7d5ceebdb7b3a48ded66ed108bddda25d8a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575589"
---
# <a name="create-delete-or-modify-a-folder-report-manager"></a><span data-ttu-id="60292-102">Criar, excluir ou modificar uma pasta (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="60292-102">Create, Delete, or Modify a Folder (Report Manager)</span></span>
  <span data-ttu-id="60292-103">É possível criar pastas para organizar e administrar os itens publicados em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="60292-103">You can create folders to organize and manage the items you publish to a report server.</span></span> <span data-ttu-id="60292-104">Criar pastas pode ajudar os usuários a localizar relatórios de seu interesse.</span><span class="sxs-lookup"><span data-stu-id="60292-104">Creating folders can help users find reports of interest to them.</span></span> <span data-ttu-id="60292-105">Para gerenciadores de conteúdo, pastas fornecem uma estrutura para a aplicação de permissões.</span><span class="sxs-lookup"><span data-stu-id="60292-105">For content managers, folders provide a framework for applying permissions.</span></span> <span data-ttu-id="60292-106">É possível criar atribuições de função em pastas específicas para restringir o acesso a relatórios em desenvolvimento ou que não devem ser distribuídos amplamente.</span><span class="sxs-lookup"><span data-stu-id="60292-106">You can create role assignments on specific folders to restrict access to reports that are in development or that should not be widely distributed.</span></span>  
  
### <a name="to-create-a-folder"></a><span data-ttu-id="60292-107">Para criar uma pasta</span><span class="sxs-lookup"><span data-stu-id="60292-107">To create a folder</span></span>  
  
1.  <span data-ttu-id="60292-108">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="60292-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="60292-109">No Gerenciador de Relatórios, selecione a pasta Base e clique em **Nova Pasta**.</span><span class="sxs-lookup"><span data-stu-id="60292-109">In Report Manager, select the Home folder and click **New Folder**.</span></span> <span data-ttu-id="60292-110">Ou, para criar uma pasta na pasta já existente, navegue até essa pasta na página **Conteúdo** e clique na pasta para abri-la.</span><span class="sxs-lookup"><span data-stu-id="60292-110">Or, to create a folder under an existing folder, navigate to that folder in the **Contents** page and click the folder to open it.</span></span> <span data-ttu-id="60292-111">Clique em **Nova Pasta**.</span><span class="sxs-lookup"><span data-stu-id="60292-111">Then click **New Folder**.</span></span>  
  
     <span data-ttu-id="60292-112">A página **Nova Pasta** será aberta.</span><span class="sxs-lookup"><span data-stu-id="60292-112">The **New Folder** page opens.</span></span>  
  
3.  <span data-ttu-id="60292-113">Digite um nome de pasta.</span><span class="sxs-lookup"><span data-stu-id="60292-113">Type a folder name.</span></span> <span data-ttu-id="60292-114">Um nome de pasta pode incluir espaços, mas não pode incluir caracteres reservados usados para codificação de URL: ; ?</span><span class="sxs-lookup"><span data-stu-id="60292-114">A folder name can include spaces, but cannot include reserved characters that are used for URL encoding: ; ?</span></span> <span data-ttu-id="60292-115">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="60292-115">: \@ & = + , $ / \* \< > |.</span></span> <span data-ttu-id="60292-116">Não é possível digitar uma série de nomes de pasta para criar várias pastas de uma vez.</span><span class="sxs-lookup"><span data-stu-id="60292-116">You cannot type a series of folder names to create several folders at once.</span></span>  
  
4.  <span data-ttu-id="60292-117">Como opção, digite uma descrição.</span><span class="sxs-lookup"><span data-stu-id="60292-117">Optionally type a description.</span></span>  
  
5.  <span data-ttu-id="60292-118">Selecione **Ocultar na exibição de lista** se não deseja exibir a pasta na exibição padrão da página **Conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="60292-118">Select **Hide in list view** if you do not want to display the folder in the default view of the **Contents** page.</span></span> <span data-ttu-id="60292-119">A pasta só será visível a usuários quando eles clicarem em **Mostrar Detalhes** na página **Conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="60292-119">The folder will be visible to users only when they click **Show Details** on the **Contents** page.</span></span>  
  
6.  <span data-ttu-id="60292-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="60292-120">Click **OK**.</span></span>  
  
### <a name="to-delete-a-folder"></a><span data-ttu-id="60292-121">Para excluir uma pasta</span><span class="sxs-lookup"><span data-stu-id="60292-121">To delete a folder</span></span>  
  
1.  <span data-ttu-id="60292-122">No Gerenciador de Relatórios, navegue até a página **Conteúdo** e localize o item que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="60292-122">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="60292-123">Focalize o item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="60292-123">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="60292-124">No menu suspenso, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="60292-124">In the drop-down menu, click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-modify-or-delete-a-folder"></a><span data-ttu-id="60292-125">Para modificar ou excluir uma pasta</span><span class="sxs-lookup"><span data-stu-id="60292-125">To modify or delete a folder</span></span>  
  
1.  <span data-ttu-id="60292-126">No Gerenciador de Relatórios, navegue até a página **Conteúdo** e localize o item que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="60292-126">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="60292-127">Focalize o item e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="60292-127">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="60292-128">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="60292-128">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="60292-129">A página Propriedades Gerais será aberta.</span><span class="sxs-lookup"><span data-stu-id="60292-129">The General Properties page opens.</span></span>  
  
4.  <span data-ttu-id="60292-130">Para alterar o local da pasta, clique em **Mover**.</span><span class="sxs-lookup"><span data-stu-id="60292-130">To change the folder location, click **Move**.</span></span> <span data-ttu-id="60292-131">Digite o local da pasta de destino ou escolha a pasta de destino da árvore e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="60292-131">Type the location of the destination folder, or choose the destination folder from the tree, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="60292-132">Ou modifique as propriedades de pasta das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="60292-132">Or, modify folder properties in the following ways:</span></span>  
  
    -   <span data-ttu-id="60292-133">Para modificar o texto de exibição sobre a pasta, digite um nome ou descrição.</span><span class="sxs-lookup"><span data-stu-id="60292-133">To modify display text about the folder, type a name or description.</span></span>  
  
    -   <span data-ttu-id="60292-134">Para exibir a pasta na exibição padrão na página **Conteúdo** , desmarque **Ocultar na exibição de lista**.</span><span class="sxs-lookup"><span data-stu-id="60292-134">To display the folder in the default view on the **Contents** page, clear **Hide in list view**.</span></span>  
  
6.  <span data-ttu-id="60292-135">Ou, para remover a pasta e seu conteúdo, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="60292-135">Or, to remove the folder and its contents, click **Delete**.</span></span>  
  
7.  <span data-ttu-id="60292-136">Clique em **Aplicar** para salvar os detalhes.</span><span class="sxs-lookup"><span data-stu-id="60292-136">Click **Apply** to save changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60292-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60292-137">See Also</span></span>  
 <span data-ttu-id="60292-138">[&#40;Report Manager de página nova pasta&#41;](../new-folder-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="60292-138">[New Folder Page &#40;Report Manager&#41;](../new-folder-page-report-manager.md) </span></span>  
 <span data-ttu-id="60292-139">[Página de conteúdo &#40;Report Manager&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="60292-139">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="60292-140">Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="60292-140">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
