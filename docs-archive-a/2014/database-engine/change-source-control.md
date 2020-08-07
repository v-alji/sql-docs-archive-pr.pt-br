---
title: Alterar controle do código-fonte | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- IDD_SCC_CONNECTION_DIALOG
helpviewer_keywords:
- Change Source Control dialog box
ms.assetid: e6a5d83c-5809-4c56-907a-73d0c7ccdd7a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 55831529243608e8c71972a31009e5672fb0234f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575370"
---
# <a name="change-source-control"></a><span data-ttu-id="3260e-102">Alterar Controle do Código-Fonte</span><span class="sxs-lookup"><span data-stu-id="3260e-102">Change Source Control</span></span>
  <span data-ttu-id="3260e-103">Cria e gerencia as conexões e associações que vinculam uma solução ou projeto salvo localmente com uma pasta do banco de dados de controle do código fonte.</span><span class="sxs-lookup"><span data-stu-id="3260e-103">Creates and manages the connections and bindings that link a locally saved solution or project to a source control database folder.</span></span>  
  
## <a name="dialog-box-access"></a><span data-ttu-id="3260e-104">Acesso à caixa de diálogo</span><span class="sxs-lookup"><span data-stu-id="3260e-104">Dialog Box Access</span></span>  
 <span data-ttu-id="3260e-105">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], selecione um item no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="3260e-105">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], select an item in Solution Explorer.</span></span> <span data-ttu-id="3260e-106">No menu **Arquivo** , clique em **Controle do Código Fonte**e em **Alterar Controle do Código Fonte**.</span><span class="sxs-lookup"><span data-stu-id="3260e-106">On the **File** menu, click **Source Control**, and then **Change Source Control**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3260e-107">Esta caixa de diálogo também está disponível clicando com o botão direito do mouse no item no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="3260e-107">This dialog box is also available by right-clicking the item in Solution Explorer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3260e-108">Opções</span><span class="sxs-lookup"><span data-stu-id="3260e-108">Options</span></span>  
 <span data-ttu-id="3260e-109">**Associa**</span><span class="sxs-lookup"><span data-stu-id="3260e-109">**Bind**</span></span>  
 <span data-ttu-id="3260e-110">Associe itens selecionados com um local de servidor de controle do código fonte especificado.</span><span class="sxs-lookup"><span data-stu-id="3260e-110">Associate selected items with a specified source control server location.</span></span> <span data-ttu-id="3260e-111">Por exemplo, você pode usar esse botão para associar à última pasta de servidor de controle do código fonte conhecida e ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3260e-111">For example, you can use this button to bind to the last known source control server folder and database.</span></span> <span data-ttu-id="3260e-112">Se uma pasta de servidor ou banco de dados recente não puder ser localizada, você será solicitado a especificar outra.</span><span class="sxs-lookup"><span data-stu-id="3260e-112">If a recent server folder or database cannot be found, you are prompted to specify another.</span></span>  
  
 <span data-ttu-id="3260e-113">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="3260e-113">**Browse**</span></span>  
 <span data-ttu-id="3260e-114">Navegue até um novo local de servidor de controle do código fonte para o item especificado.</span><span class="sxs-lookup"><span data-stu-id="3260e-114">Navigate to a new source control server location for the specified item.</span></span>  
  
 <span data-ttu-id="3260e-115">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="3260e-115">**Columns**</span></span>  
 <span data-ttu-id="3260e-116">Identifique colunas a serem exibidas e a ordem na qual elas são exibidas.</span><span class="sxs-lookup"><span data-stu-id="3260e-116">Identify columns to display and the order in which they are displayed.</span></span>  
  
 <span data-ttu-id="3260e-117">**Connect**</span><span class="sxs-lookup"><span data-stu-id="3260e-117">**Connect**</span></span>  
 <span data-ttu-id="3260e-118">Crie uma conexão entre itens selecionados e o servidor de controle do código fonte.</span><span class="sxs-lookup"><span data-stu-id="3260e-118">Create a connection between selected items and the source control server.</span></span>  
  
 <span data-ttu-id="3260e-119">**Conectado**</span><span class="sxs-lookup"><span data-stu-id="3260e-119">**Connected**</span></span>  
 <span data-ttu-id="3260e-120">Exibe o status da conexão de uma solução ou projeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="3260e-120">Displays the connection status of a selected solution or project.</span></span>  
  
 <span data-ttu-id="3260e-121">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="3260e-121">**Disconnect**</span></span>  
 <span data-ttu-id="3260e-122">Desconecte a cópia local de uma solução ou projeto em seu computador a partir de sua cópia mestre no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3260e-122">Disconnect the local copy of a solution or project on your computer from its master copy in the database.</span></span> <span data-ttu-id="3260e-123">Use esse comando antes de desconectar seu computador do servidor de controle do código fonte, por exemplo, ao trabalhar offline no seu laptop.</span><span class="sxs-lookup"><span data-stu-id="3260e-123">Use this command before disconnecting your computer from the source control server, for example, when working offline on your laptop.</span></span>  
  
 <span data-ttu-id="3260e-124">**OK**</span><span class="sxs-lookup"><span data-stu-id="3260e-124">**OK**</span></span>  
 <span data-ttu-id="3260e-125">Aceite as alterações feitas na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3260e-125">Accept changes made in the dialog box.</span></span>  
  
 <span data-ttu-id="3260e-126">**Provedor**</span><span class="sxs-lookup"><span data-stu-id="3260e-126">**Provider**</span></span>  
 <span data-ttu-id="3260e-127">Exibe o nome de seu plug-in de controle do código fonte.</span><span class="sxs-lookup"><span data-stu-id="3260e-127">Displays the name of your source control plug-in.</span></span>  
  
 <span data-ttu-id="3260e-128">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="3260e-128">**Refresh**</span></span>  
 <span data-ttu-id="3260e-129">Atualize as informações de conexão de todos os projetos listados nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3260e-129">Refreshes the connection information for all projects listed in this dialog box.</span></span>  
  
 <span data-ttu-id="3260e-130">**Associação de Servidores**</span><span class="sxs-lookup"><span data-stu-id="3260e-130">**Server Binding**</span></span>  
 <span data-ttu-id="3260e-131">Indica a associação do item com um servidor de controle do código fonte.</span><span class="sxs-lookup"><span data-stu-id="3260e-131">Indicates the item's binding to a source control server.</span></span>  
  
 <span data-ttu-id="3260e-132">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="3260e-132">**Server Name**</span></span>  
 <span data-ttu-id="3260e-133">Exibe o nome do servidor de controle do código fonte ao qual a solução ou projeto correspondente está associado.</span><span class="sxs-lookup"><span data-stu-id="3260e-133">Displays the name of the source control server to which the corresponding solution or project is bound.</span></span>  
  
 <span data-ttu-id="3260e-134">**Solução/Projeto**</span><span class="sxs-lookup"><span data-stu-id="3260e-134">**Solution/Project**</span></span>  
 <span data-ttu-id="3260e-135">Exibe o nome de cada solução e projeto na seleção atual.</span><span class="sxs-lookup"><span data-stu-id="3260e-135">Displays the name of each solution and project in the current selection.</span></span>  
  
 <span data-ttu-id="3260e-136">**Sort**</span><span class="sxs-lookup"><span data-stu-id="3260e-136">**Sort**</span></span>  
 <span data-ttu-id="3260e-137">Classifique a ordem de colunas exibidas.</span><span class="sxs-lookup"><span data-stu-id="3260e-137">Sort the order of displayed columns.</span></span>  
  
 <span data-ttu-id="3260e-138">**Status**</span><span class="sxs-lookup"><span data-stu-id="3260e-138">**Status**</span></span>  
 <span data-ttu-id="3260e-139">Identifica o status da associação e da conexão de um item.</span><span class="sxs-lookup"><span data-stu-id="3260e-139">Identifies the binding and connection status of an item.</span></span> <span data-ttu-id="3260e-140">Possíveis opções são:</span><span class="sxs-lookup"><span data-stu-id="3260e-140">Possible options are:</span></span>  
  
|<span data-ttu-id="3260e-141">**Opção**</span><span class="sxs-lookup"><span data-stu-id="3260e-141">**Option**</span></span>|<span data-ttu-id="3260e-142">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3260e-142">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="3260e-143">Válido</span><span class="sxs-lookup"><span data-stu-id="3260e-143">Valid</span></span>|<span data-ttu-id="3260e-144">O item está corretamente associado e conectado com a pasta de servidor à qual pertence.</span><span class="sxs-lookup"><span data-stu-id="3260e-144">The item is correctly bound and connected to the server folder to which it belongs.</span></span>|  
|<span data-ttu-id="3260e-145">Inválido</span><span class="sxs-lookup"><span data-stu-id="3260e-145">Invalid</span></span>|<span data-ttu-id="3260e-146">O item está incorretamente associado com a pasta à qual pertence ou desconectado dela.</span><span class="sxs-lookup"><span data-stu-id="3260e-146">The item is incorrectly bound to or disconnected from the folder to which it belongs.</span></span> <span data-ttu-id="3260e-147">Use o comando **Adicionar ao Controle do Código Fonte** em vez de **Associar** neste item.</span><span class="sxs-lookup"><span data-stu-id="3260e-147">Use the **Add to Source Control** command instead of **Bind** for this item.</span></span>|  
|<span data-ttu-id="3260e-148">Unknown (desconhecido)</span><span class="sxs-lookup"><span data-stu-id="3260e-148">Unknown</span></span>|<span data-ttu-id="3260e-149">O status do item sob controle do código fonte ainda não foi determinado.</span><span class="sxs-lookup"><span data-stu-id="3260e-149">The status of the item under source control has not yet been determined.</span></span>|  
|<span data-ttu-id="3260e-150">Não Controlado</span><span class="sxs-lookup"><span data-stu-id="3260e-150">Not Controlled</span></span>|<span data-ttu-id="3260e-151">O item não foi colocado sob controle do código fonte.</span><span class="sxs-lookup"><span data-stu-id="3260e-151">The item has not been placed under source control.</span></span>|  
  
 <span data-ttu-id="3260e-152">**Desassociar**</span><span class="sxs-lookup"><span data-stu-id="3260e-152">**Unbind**</span></span>  
 <span data-ttu-id="3260e-153">Exiba a caixa de diálogo **Controle do Código Fonte** para permitir que você remova itens selecionados do controle do código fonte e desassocie permanentemente os itens de suas pastas atuais.</span><span class="sxs-lookup"><span data-stu-id="3260e-153">Display the **Source Control** dialog box to allow you to remove selected items from source control and permanently disassociate the items from their present folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3260e-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3260e-154">See Also</span></span>  
 [<span data-ttu-id="3260e-155">Controle do código-fonte do Gerenciador de Soluções</span><span class="sxs-lookup"><span data-stu-id="3260e-155">Solution Explorer Source Control</span></span>](../../2014/database-engine/solution-explorer-source-control.md)  
  
  
