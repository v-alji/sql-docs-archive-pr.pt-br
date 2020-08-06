---
title: Especifique uma versão como a versão mais recente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], latest version
- latest file version specified
- file versions [SQL Server]
ms.assetid: 407dffb1-3ecf-461e-835d-124781f26ee7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: dafe4f757e33a5db63340c3d3cc7c9151871d438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569620"
---
# <a name="specify-a-version-as-the-latest-version"></a><span data-ttu-id="f2cb5-102">Especificar uma versão como a versão mais recente</span><span class="sxs-lookup"><span data-stu-id="f2cb5-102">Specify a Version as the Latest Version</span></span>
  <span data-ttu-id="f2cb5-103">Quando você faz o check-in de um arquivo no controle do código-fonte, essa versão se torna a mais recente; usuários que fazem check-out ou recuperam a versão mais recente recebem cópias locais do item em que foi feito check-in recentemente.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-103">When you check a file into source control, the version you check in becomes the latest version; users who check out or retrieve the latest version receive local copies of the item most recently checked in.</span></span>  
  
 <span data-ttu-id="f2cb5-104">Entretanto, em algumas situações, você pode querer designar uma versão anterior de um item como a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-104">However, in some situations, you may want to designate an earlier version of an item as the latest version.</span></span> <span data-ttu-id="f2cb5-105">Por exemplo, você faz check-out de um arquivo, modifica o arquivo e, por fim, faz check-in do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-105">For example, you check out a file, modify the file, and then check the file in.</span></span> <span data-ttu-id="f2cb5-106">Você decide descartar suas modificações posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-106">You later decide to discard your modifications.</span></span> <span data-ttu-id="f2cb5-107">Como você fez o check-in do item, desfazer o check-out original não é uma opção.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-107">Because you have checked in the item, undoing your original checkout is not an option.</span></span> <span data-ttu-id="f2cb5-108">Nessa situação, você pode designar a versão original de check-out como a versão mais recente do item.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-108">In this situation, you can designate the version you originally checked out as the latest version of the item.</span></span>  
  
 <span data-ttu-id="f2cb5-109">Você pode designar a versão mais recente:</span><span class="sxs-lookup"><span data-stu-id="f2cb5-109">You can designate the latest version by:</span></span>  
  
-   <span data-ttu-id="f2cb5-110">**Fixação de uma versão**.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-110">**Pinning a version**.</span></span> <span data-ttu-id="f2cb5-111">Quando você fixa uma versão de arquivo, as versões mais recentes que a versão fixada não são excluídas.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-111">When you pin a file version, versions that are more recent than the pinned version are not deleted.</span></span> <span data-ttu-id="f2cb5-112">Além disso, você pode desafixar o arquivo fixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-112">In addition, you can unpin a file that you have previously pinned.</span></span> <span data-ttu-id="f2cb5-113">Quando você fizer isso, a versão de check-in mais recente do arquivo se tornará a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-113">When you do this, the most recently checked in version of the file becomes the latest version.</span></span> <span data-ttu-id="f2cb5-114">Entretanto, você não pode fazer check-out de um arquivo fixado.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-114">However, you cannot check out a pinned file.</span></span>  
  
-   <span data-ttu-id="f2cb5-115">**Revertendo para uma versão especificada**.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-115">**Rolling back to a specified version**.</span></span> <span data-ttu-id="f2cb5-116">Quando você reverte uma versão, todas as versões mais recentes do que a revertida serão excluídas do controle de código-fonte.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-116">When you roll back to a version, all versions more recent than the one to which you have rolled back are deleted from source control.</span></span> <span data-ttu-id="f2cb5-117">Depois você pode fazer o check-out da versão mais recente restante.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-117">You can then check out the latest remaining version.</span></span>  
  
### <a name="to-pin-a-version"></a><span data-ttu-id="f2cb5-118">Para fixar uma versão</span><span class="sxs-lookup"><span data-stu-id="f2cb5-118">To pin a version</span></span>  
  
1.  <span data-ttu-id="f2cb5-119">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], abra a solução.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-119">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="f2cb5-120">No Gerenciador de Soluções, selecione o arquivo que você deseja especificar como versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-120">In Solution Explorer, select the file that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="f2cb5-121">No menu **arquivo** , aponte para **controle do código-fonte** e clique em **ViewHistory**.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-121">On the **File** menu, point to **Source Control** and click **ViewHistory**.</span></span>  
  
4.  <span data-ttu-id="f2cb5-122">Na caixa **de diálogo histórico de** \<file> , selecione a versão que você deseja especificar como a mais recente e clique em **fixar**.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-122">In the **History of** \<file> dialog box, select the version that you want to specify as the latest, and click **Pin**.</span></span>  
  
     <span data-ttu-id="f2cb5-123">Um símbolo de alfinete aparece próximo à versão selecionada, indicando que essa é a versão atual do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-123">A pin symbol appears next to the version you have selected, indicating that it is the current file version.</span></span> <span data-ttu-id="f2cb5-124">Se você tiver uma versão diferente carregada no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], será solicitado a recarregar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-124">If you have a different version loaded in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you are prompted to reload the file.</span></span>  
  
### <a name="to-roll-back-to-a-version"></a><span data-ttu-id="f2cb5-125">Para reverter uma versão</span><span class="sxs-lookup"><span data-stu-id="f2cb5-125">To roll back to a version</span></span>  
  
1.  <span data-ttu-id="f2cb5-126">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], abra a solução.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-126">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="f2cb5-127">No Gerenciador de Soluções, selecione o item que você deseja especificar como versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-127">In Solution Explorer, select the item that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="f2cb5-128">No menu **arquivo** , aponte para **controle do código-fonte** e clique em **histórico**.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-128">On the **File** menu, point to **Source Control** and click **History**.</span></span>  
  
4.  <span data-ttu-id="f2cb5-129">Na caixa de diálogo **Opções de histórico** , clique em **OK** para exibir a caixa **de diálogo histórico de arquivo** .</span><span class="sxs-lookup"><span data-stu-id="f2cb5-129">In the **History Options** dialog box, click **OK** to display the **History of File** dialog box.</span></span>  
  
5.  <span data-ttu-id="f2cb5-130">Na caixa **histórico do arquivo** , selecione a versão que você deseja especificar como a versão mais recente e clique em **reverter**.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-130">In the **History of File** box, select the version you want to specify as the latest version, and click **Rollback**.</span></span>  
  
     <span data-ttu-id="f2cb5-131">Uma mensagem é exibida notificando você de que todas as versões subsequentes àquelas selecionadas serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-131">A message appears notifying you that all versions subsequent to the one you have selected will be deleted.</span></span>  
  
6.  <span data-ttu-id="f2cb5-132">Clique em **Sim** para reverter para a versão selecionada.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-132">Click **Yes** to roll back to the selected version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cb5-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f2cb5-133">See Also</span></span>  
 <span data-ttu-id="f2cb5-134">[Gerenciar Check-ins](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="f2cb5-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="f2cb5-135">Fazer check-in de arquivos</span><span class="sxs-lookup"><span data-stu-id="f2cb5-135">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)  
  
  
