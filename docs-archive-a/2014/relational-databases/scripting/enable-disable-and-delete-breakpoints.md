---
title: Habilitar, desabilitar e excluir pontos de interrupção
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 357b5874-273f-43a9-8e30-83872bdea5dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 17e83c6488b9d9026fb78e5fb8f50e22533fa61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582971"
---
# <a name="enable-disable-and-delete-breakpoints"></a><span data-ttu-id="de4a3-102">Habilitar, desabilitar e excluir pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-102">Enable, Disable, and Delete Breakpoints</span></span>
  <span data-ttu-id="de4a3-103">Para exibir e gerenciar todos os pontos de interrupção abertos, você pode usar a janela **Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="de4a3-103">To view and manage all the open breakpoints, you can use the **Breakpoints** window.</span></span> <span data-ttu-id="de4a3-104">Use a janela para exibir informações de ponto de interrupção e executar ações como excluir, desabilitar ou habilitar pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="de4a3-104">Use the window to view breakpoint information and to take actions such as deleting, disabling, or enabling breakpoints.</span></span>  
  
## <a name="the-breakpoints-window"></a><span data-ttu-id="de4a3-105">Janela Pontos de Interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-105">The Breakpoints Window</span></span>  
 <span data-ttu-id="de4a3-106">A janela **Pontos de Interrupção** lista informações como a linha de código em que o ponto de interrupção é localizado.</span><span class="sxs-lookup"><span data-stu-id="de4a3-106">The **Breakpoints** window lists information such as which line of code the breakpoint is located on.</span></span> <span data-ttu-id="de4a3-107">Na janela **Pontos de Interrupção** , você também pode excluir, desabilitar e habilitar pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="de4a3-107">In the **Breakpoints** window, you can also delete, disable, and enable breakpoints.</span></span> <span data-ttu-id="de4a3-108">Para obter mais informações sobre a janela **Pontos de Interrupção** , consulte [Pontos de Interrupção Window](transact-sql-debugger-breakpoints-window.md).</span><span class="sxs-lookup"><span data-stu-id="de4a3-108">For more information about the **Breakpoints** window, see [Breakpoints Window](transact-sql-debugger-breakpoints-window.md)</span></span>  
  
 <span data-ttu-id="de4a3-109">A desabilitação de um ponto de interrupção impede a pausa da execução, mas deixa a definição no local caso você deseje habilitar o ponto de interrupção mais tarde.</span><span class="sxs-lookup"><span data-stu-id="de4a3-109">Disabling a breakpoint prevents it from pausing execution, but leaves the definition in place in case you want to enable the breakpoint later.</span></span> <span data-ttu-id="de4a3-110">A exclusão de um ponto de interrupção remove isso permanentemente.</span><span class="sxs-lookup"><span data-stu-id="de4a3-110">Deleting a breakpoint removes it permanently.</span></span> <span data-ttu-id="de4a3-111">Você deve alternar um novo ponto de interrupção para pausar execução na instrução.</span><span class="sxs-lookup"><span data-stu-id="de4a3-111">You must toggle a new breakpoint to pause execution on the statement.</span></span>  
  
## <a name="to-open-the-breakpoints-window"></a><span data-ttu-id="de4a3-112">Para abrir a janela Pontos de Interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-112">To Open the Breakpoints Window</span></span>  
 <span data-ttu-id="de4a3-113">**To open the Breakpoints window**</span><span class="sxs-lookup"><span data-stu-id="de4a3-113">**To open the Breakpoints window**</span></span>  
  
 <span data-ttu-id="de4a3-114">Você pode abrir a janela **Pontos de Interrupção** de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="de4a3-114">You can open the **Breakpoints** window in one of the following ways:</span></span>  
  
-   <span data-ttu-id="de4a3-115">No menu **Depurar** , clique em **Janelas**e em **Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="de4a3-115">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
-   <span data-ttu-id="de4a3-116">Na barra de ferramentas **Depurar** , clique no botão **Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="de4a3-116">On the **Debug** toolbar, click the **Breakpoints** button.</span></span>  
  
-   <span data-ttu-id="de4a3-117">Pressione CTRL+ALT+B.</span><span class="sxs-lookup"><span data-stu-id="de4a3-117">Press CTRL+ALT+B.</span></span>  
  
## <a name="to-disable-a-single-breakpoint"></a><span data-ttu-id="de4a3-118">Para desabilitar um único ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-118">To Disable a Single Breakpoint</span></span>  
 <span data-ttu-id="de4a3-119">**To disable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="de4a3-119">**To disable a single breakpoint**</span></span>  
  
 <span data-ttu-id="de4a3-120">Você pode desabilitar um único ponto de interrupção de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="de4a3-120">You can disable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="de4a3-121">Na janela Editor de Consultas, clique com o botão direito do mouse no ponto de interrupção e clique em **Desabilitar Ponto de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="de4a3-121">In the Query Editor window, right-click the breakpoint, and then click **Disable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="de4a3-122">Na janela Pontos de Interrupção, desmarque a caixa de seleção à esquerda do ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="de4a3-122">In the Breakpoints window, clear the check box to the left of the breakpoint.</span></span>  
  
## <a name="to-disable-all-breakpoints"></a><span data-ttu-id="de4a3-123">Para desabilitar todos os pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-123">To Disable All Breakpoints</span></span>  
 <span data-ttu-id="de4a3-124">**To disable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="de4a3-124">**To disable all breakpoints**</span></span>  
  
 <span data-ttu-id="de4a3-125">Você pode desabilitar todos os pontos de interrupção de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="de4a3-125">You can disable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="de4a3-126">No menu **Depurar** , clique em **Desabilitar Todos os Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="de4a3-126">On the **Debug** menu, click **Disable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="de4a3-127">Na barra de ferramentas da janela **Pontos de Interrupção** , clique no botão **Desabilitar Todos os Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="de4a3-127">On the toolbar of the **Breakpoints** window, click the **Disable All Breakpoints** button.</span></span>  
  
## <a name="to-enable-a-single-breakpoint"></a><span data-ttu-id="de4a3-128">Para habilitar um único ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-128">To Enable a Single Breakpoint</span></span>  
 <span data-ttu-id="de4a3-129">**To enable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="de4a3-129">**To enable a single breakpoint**</span></span>  
  
 <span data-ttu-id="de4a3-130">Você pode habilitar um único ponto de interrupção de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="de4a3-130">You can enable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="de4a3-131">Na janela Editor de Consultas, clique com o botão direito do mouse no ponto de interrupção e clique em **Habilitar Ponto de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="de4a3-131">In the Query Editor window, right-click the breakpoint, and then click **Enable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="de4a3-132">Na janela Pontos de Interrupção, clique na caixa à esquerda do ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="de4a3-132">In the Breakpoints window, click the box to the left of the breakpoint.</span></span>  
  
## <a name="to-enable-all-breakpoints"></a><span data-ttu-id="de4a3-133">Para habilitar todos os pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-133">To Enable All Breakpoints</span></span>  
 <span data-ttu-id="de4a3-134">**To enable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="de4a3-134">**To enable all breakpoints**</span></span>  
  
 <span data-ttu-id="de4a3-135">Você pode habilitar todos os pontos de interrupção de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="de4a3-135">You can enable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="de4a3-136">No menu **Depurar** , clique em **Habilitar Todos os Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="de4a3-136">On the **Debug** menu, click **Enable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="de4a3-137">Na barra de ferramentas da janela **Pontos de Interrupção** , clique no botão **Habilitar Todos os Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="de4a3-137">On the toolbar of the **Breakpoints** window, click the **Enable All Breakpoints** button.</span></span>  
  
## <a name="to-delete-a-single-breakpoint"></a><span data-ttu-id="de4a3-138">Para excluir um único ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-138">To Delete a Single Breakpoint</span></span>  
 <span data-ttu-id="de4a3-139">**To delete a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="de4a3-139">**To delete a single breakpoint**</span></span>  
  
 <span data-ttu-id="de4a3-140">Você pode excluir um único ponto de interrupção de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="de4a3-140">You can delete a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="de4a3-141">Na janela Editor de Consultas, clique com o botão direito do mouse no ponto de interrupção e clique em **Excluir Ponto de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="de4a3-141">In the Query Editor window, right-click the breakpoint, and then click **Delete Breakpoint**.</span></span>  
  
-   <span data-ttu-id="de4a3-142">Na janela Pontos de Interrupção, clique com o botão direito do mouse no ponto de interrupção e em **Excluir** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="de4a3-142">In the Breakpoints window, right-click the breakpoint, and then click **Delete** on the shortcut menu.</span></span>  
  
-   <span data-ttu-id="de4a3-143">Na janela Pontos de Interrupção, selecione o ponto de interrupção e pressione DELETE.</span><span class="sxs-lookup"><span data-stu-id="de4a3-143">In the Breakpoints window, select the breakpoint, and then press DELETE.</span></span>  
  
## <a name="to-delete-all-breakpoints"></a><span data-ttu-id="de4a3-144">Para excluir todos os pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-144">To Delete All Breakpoints</span></span>  
 <span data-ttu-id="de4a3-145">**To delete all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="de4a3-145">**To delete all breakpoints**</span></span>  
  
 <span data-ttu-id="de4a3-146">Você pode excluir todos os pontos de interrupção de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="de4a3-146">You can delete all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="de4a3-147">No menu **Depurar** , clique em **Excluir Todos os Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="de4a3-147">On the **Debug** menu, cllick **Delete All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="de4a3-148">Na barra de ferramentas da janela **Pontos de Interrupção** , clique no botão **Excluir Todos os Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="de4a3-148">On the toolbar of the **Breakpoints** window, click the **Delete All Breakpoints** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4a3-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de4a3-149">See Also</span></span>  
 [<span data-ttu-id="de4a3-150">Alternar um ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="de4a3-150">Toggle a Breakpoint</span></span>](../spatial/point.md)  
  
  
