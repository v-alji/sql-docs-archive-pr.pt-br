---
title: Desfazer check-outs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourcControl.UndoCheckDialog
helpviewer_keywords:
- checking out files
- checkout source controls [SQL Server]
- undoing checkouts
ms.assetid: a6596b20-3aa5-4dc4-a4c5-3649f1f5a20e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ff6e6041b59caa75bf7f8530d915db48e0379338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569603"
---
# <a name="undo-checkouts"></a><span data-ttu-id="e27fd-102">Desfazer check-outs</span><span class="sxs-lookup"><span data-stu-id="e27fd-102">Undo Checkouts</span></span>
  <span data-ttu-id="e27fd-103">Você pode usar o comando **Desfazer check-out** para cancelar um check-out existente.</span><span class="sxs-lookup"><span data-stu-id="e27fd-103">You can use the **Undo Checkout** command to cancel an existing checkout.</span></span> <span data-ttu-id="e27fd-104">Isso é particularmente útil quando você tiver modificado e salvado um arquivo, e depois precisar reverter as alterações.</span><span class="sxs-lookup"><span data-stu-id="e27fd-104">This is particularly useful when you have modified and saved a file, and then later need to roll back your changes.</span></span>  
  
 <span data-ttu-id="e27fd-105">Dependendo das opções definidas na caixa de diálogo **Opções Avançadas de Desfazer Check-Out** , o ambiente do Studio deixa a cópia de trabalho do item no disco local ou a substitui pela versão com controle do código-fonte mais recente.</span><span class="sxs-lookup"><span data-stu-id="e27fd-105">Depending on the options you set in the **Undo Checkout Advanced Options** dialog box, the Studio environment either leaves the working copy of the item on your local disk or replaces it with the latest source-controlled version.</span></span> <span data-ttu-id="e27fd-106">Se alguém tiver modificado o item fora do contexto do sistema de controle do código-fonte, a versão recuperada talvez não seja a mais recente.</span><span class="sxs-lookup"><span data-stu-id="e27fd-106">If someone has modified the item outside the context of the source control system, the retrieved version may not be the latest one.</span></span>  
  
### <a name="to-undo-a-checkout"></a><span data-ttu-id="e27fd-107">Para desfazer um check-out</span><span class="sxs-lookup"><span data-stu-id="e27fd-107">To undo a checkout</span></span>  
  
1.  <span data-ttu-id="e27fd-108">No Gerenciador de Soluções, selecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="e27fd-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="e27fd-109">No menu **Arquivo** , aponte para **Controle do Código-Fonte**e clique em **Desfazer Check-out**.</span><span class="sxs-lookup"><span data-stu-id="e27fd-109">On the **File** menu, point to **Source Control**, and then click **Undo Checkout**.</span></span>  
  
3.  <span data-ttu-id="e27fd-110">Na caixa de diálogo **Desfazer Check-out** , selecione as opções apropriadas e clique no botão **Desfazer Check-out** .</span><span class="sxs-lookup"><span data-stu-id="e27fd-110">In the **Undo Checkout** dialog box, select the appropriate options, and then click the **Undo Checkout** button.</span></span>  
  
     <span data-ttu-id="e27fd-111">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="e27fd-111">**Columns**</span></span>  
     <span data-ttu-id="e27fd-112">Identifique as colunas a serem exibidas e a ordem em que elas são exibidas.</span><span class="sxs-lookup"><span data-stu-id="e27fd-112">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="e27fd-113">**Exibição Simples**</span><span class="sxs-lookup"><span data-stu-id="e27fd-113">**Flat View**</span></span>  
     <span data-ttu-id="e27fd-114">Exiba os itens como listas simples com sua conexão de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="e27fd-114">Display the items as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="e27fd-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e27fd-115">**Name**</span></span>  
     <span data-ttu-id="e27fd-116">Exibe os nomes dos itens para os quais desfazer o check-out.</span><span class="sxs-lookup"><span data-stu-id="e27fd-116">Displays the names of the items for which to undo the checkout.</span></span> <span data-ttu-id="e27fd-117">Os itens aparecem com as caixas de seleção próximas a eles selecionadas.</span><span class="sxs-lookup"><span data-stu-id="e27fd-117">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="e27fd-118">Se você não quiser desfazer a saída de um item, desmarque sua caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="e27fd-118">If you do not want to undo the checkout of an item, clear its check box.</span></span>  
  
     <span data-ttu-id="e27fd-119">**Opções**</span><span class="sxs-lookup"><span data-stu-id="e27fd-119">**Options**</span></span>  
     <span data-ttu-id="e27fd-120">Exibe opções de desfazer check-out específicas de plug-ins de controle do código-fonte quando é clicada a seta à direita do botão.</span><span class="sxs-lookup"><span data-stu-id="e27fd-120">Displays source control plug-in-specific undo checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="e27fd-121">**Sort**</span><span class="sxs-lookup"><span data-stu-id="e27fd-121">**Sort**</span></span>  
     <span data-ttu-id="e27fd-122">Classifica a ordem das colunas exibidas.</span><span class="sxs-lookup"><span data-stu-id="e27fd-122">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="e27fd-123">**Exibição de árvore**</span><span class="sxs-lookup"><span data-stu-id="e27fd-123">**Tree View**</span></span>  
     <span data-ttu-id="e27fd-124">Exibe a pasta e hierarquia de item para itens que você está revertendo o check-out.</span><span class="sxs-lookup"><span data-stu-id="e27fd-124">Display the folder and item hierarchy for items on which you are reversing the checkout.</span></span>  
  
     <span data-ttu-id="e27fd-125">**Desfazer check-out**</span><span class="sxs-lookup"><span data-stu-id="e27fd-125">**Undo Checkout**</span></span>  
     <span data-ttu-id="e27fd-126">Reverte o check-out, descartando qualquer alteração no arquivo onde foi feito o check-out.</span><span class="sxs-lookup"><span data-stu-id="e27fd-126">Revert the checkout, discarding any changes to the checked-out file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e27fd-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e27fd-127">See Also</span></span>  
 <span data-ttu-id="e27fd-128">[Fazer check-out de arquivos](../../2014/database-engine/check-out-files.md) </span><span class="sxs-lookup"><span data-stu-id="e27fd-128">[Check Out Files](../../2014/database-engine/check-out-files.md) </span></span>  
 [<span data-ttu-id="e27fd-129">Gerenciar check-outs</span><span class="sxs-lookup"><span data-stu-id="e27fd-129">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
