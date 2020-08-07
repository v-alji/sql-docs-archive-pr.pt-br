---
title: Fazer check-out de arquivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- Visual Studio.SourceControl.CheckOutDialog
helpviewer_keywords:
- checking out files
ms.assetid: cc033727-51bb-4b58-a12b-8977ce61ff56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 151f554742bd6c381b27b58155d3f0e40e9eeb0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575368"
---
# <a name="check-out-files"></a><span data-ttu-id="d9cd0-102">Fazer check-out de arquivos</span><span class="sxs-lookup"><span data-stu-id="d9cd0-102">Check Out Files</span></span>
  <span data-ttu-id="d9cd0-103">A menos que você tenha configurado o ambiente do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para permitir a edição de arquivos que tenham feito check-in, faça o check-out de um arquivo antes de modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-103">Unless you have configured the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment to permit checked-in files to be edited, you must check out a file before you can modify it.</span></span> <span data-ttu-id="d9cd0-104">Quando você faz o check-out de um arquivo, uma cópia da versão de arquivo é copiada no disco local e o atributo somente leitura é removido.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-104">When you check out a file, a copy of the file version is copied to your local disk, and the read-only attribute of the file is removed.</span></span>  
  
 <span data-ttu-id="d9cd0-105">Você pode fazer o check-out de arquivos em modo exclusivo ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-105">You can check files out either exclusively or in shared mode.</span></span> <span data-ttu-id="d9cd0-106">Quando você fizer o check-out de um arquivo exclusivamente, nenhum outro usuário poderá fazer o check-out do arquivo até você concluir seu check-out.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-106">When you check out a file exclusively, no other user can check out the file until you check it in.</span></span> <span data-ttu-id="d9cd0-107">Quando você faz o check-out de um arquivo no modo compartilhado, outros usuários podem fazer o check-out e modificar o arquivo; talvez seja necessário mesclar a versão de check-out com as versões criadas por outros usuários.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-107">When you check out a file in shared mode, other users can check out and modify the file, and when you check it in, you may need to merge the version you have checked out with the versions created by other users.</span></span>  
  
 <span data-ttu-id="d9cd0-108">Use o comando **Check-Out** para fazer o check-out de arquivos e projetos com controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-108">Use the **Check Out** command to check out source-controlled projects and files.</span></span> <span data-ttu-id="d9cd0-109">Se você usar esse comando para fazer o check-out de uma solução ou projeto, todos os arquivos na solução ou no projeto também serão submetidos a check-out. No entanto, o check-out de um arquivo de código-fonte individual não resulta no check-out do projeto ou da solução à qual ele pertence.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-109">If you use this command to check out a solution or project, all the files in the solution or project are also checked out. However, checking out an individual source code file does not result in the check out of the project or solution to which it belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9cd0-110">Se o banco de dados do [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe do projeto for configurado para permitir vários check-outs e você quiser fazer o check-out de um arquivo exclusivamente, desmarque a opção **Permitir múltiplos check-outs** na caixa de diálogo **Opções Avançadas de Check-Out** antes de fazer o check-out do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-110">If the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database for your project is configured to allow multiple checkouts, and you want to check out a file exclusively, you must clear the **Allow multiple checkouts** option in the **Advanced Check Out Options** dialog box before checking out the file.</span></span> <span data-ttu-id="d9cd0-111">Você deve reiniciar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para que essa configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-111">You must restart the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for this setting to take effect.</span></span>  
  
### <a name="to-check-out-a-file"></a><span data-ttu-id="d9cd0-112">Para fazer check-out de um arquivo</span><span class="sxs-lookup"><span data-stu-id="d9cd0-112">To check out a file</span></span>  
  
1.  <span data-ttu-id="d9cd0-113">No Gerenciador de Soluções, selecione o projeto ou o arquivo.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-113">In Solution Explorer, select the project or file.</span></span>  
  
2.  <span data-ttu-id="d9cd0-114">No menu **Arquivo** , aponte para **Controle do Código-Fonte**e clique em **Check-Out para Edição**.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-114">On the **File** menu, point to **Source Control**, and then click **Check Out for Edit**.</span></span>  
  
3.  <span data-ttu-id="d9cd0-115">Se a caixa de diálogo **check-out para editar** for exibida, selecione os itens desejados e clique em **fazer check-out**. Se você tiver configurado o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] ambiente para não exibir a caixa de diálogo **check-out** , os itens selecionados em Gerenciador de soluções e quaisquer filhos que eles possam ter terão check-out imediatamente.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-115">If the **Check Out for Edit** dialog box is displayed, select the items you want, and click **Check Out**. If you have configured the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment not to display the **Check Out** dialog box, the items selected in Solution Explorer and any children they might have are checked out immediately.</span></span>  
  
     <span data-ttu-id="d9cd0-116">**Fazer Check-out**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-116">**Check Out**</span></span>  
     <span data-ttu-id="d9cd0-117">Faça check-out de todos os itens selecionados.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-117">Check out all the selected items.</span></span>  
  
     <span data-ttu-id="d9cd0-118">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-118">**Columns**</span></span>  
     <span data-ttu-id="d9cd0-119">Identifique as colunas a serem exibidas e a ordem em que elas são exibidas.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-119">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="d9cd0-120">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-120">**Comments**</span></span>  
     <span data-ttu-id="d9cd0-121">Especifique um comentário a ser associado com a operação de check-out.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-121">Specify a comment to associate with the checkout operation.</span></span>  
  
     <span data-ttu-id="d9cd0-122">**Não mostrar a caixa de diálogo Check-out ao fazer check-out dos itens**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-122">**Don't Show Check Out dialog box when checking out items**</span></span>  
     <span data-ttu-id="d9cd0-123">Suprima a caixa de diálogo durante operações de check-out.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-123">Suppress the dialog box during checkout operations.</span></span>  
  
     <span data-ttu-id="d9cd0-124">**Exibição Simples**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-124">**Flat View**</span></span>  
     <span data-ttu-id="d9cd0-125">Exiba os itens de check-out como listas simples em suas conexões de controle do código fonte.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-125">Display the items you are checking out as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="d9cd0-126">**Editar**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-126">**Edit**</span></span>  
     <span data-ttu-id="d9cd0-127">Modificar um item sem verificá-lo. O botão **Editar** será exibido somente se você tiver [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configurado o para dar suporte à edição de arquivos com check-in.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-127">Modify an item without checking it out. The **Edit** button appears only if you have [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configured to support the editing of checked-in files.</span></span>  
  
     <span data-ttu-id="d9cd0-128">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-128">**Name**</span></span>  
     <span data-ttu-id="d9cd0-129">Exibe os nomes dos itens disponíveis para check-out.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-129">Displays the names of the items available for checkout.</span></span> <span data-ttu-id="d9cd0-130">Os itens selecionados são exibidos com caixas de seleção ao lado.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-130">Items that are selected appear with check boxes next to them.</span></span> <span data-ttu-id="d9cd0-131">Se não quiser fazer check-out de um item em particular, desmarque sua caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-131">If you do not want to check out a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="d9cd0-132">**Opções**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-132">**Options**</span></span>  
     <span data-ttu-id="d9cd0-133">Exibe opções de check-out específico de plug-ins de controle do código fonte quando a seta à direita do botão é clicada.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-133">Displays source control plug-in-specific checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="d9cd0-134">**Sort**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-134">**Sort**</span></span>  
     <span data-ttu-id="d9cd0-135">Classifique a ordem das colunas exibidas.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-135">Sort the order of the displayed columns.</span></span>  
  
     <span data-ttu-id="d9cd0-136">**Exibição de árvore**</span><span class="sxs-lookup"><span data-stu-id="d9cd0-136">**Tree View**</span></span>  
     <span data-ttu-id="d9cd0-137">Exiba a hierarquia de pastas e arquivos do item de check-out.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-137">Display the folder and file hierarchy for the item you are checking out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9cd0-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9cd0-138">See Also</span></span>  
 <span data-ttu-id="d9cd0-139">[Editar arquivos com check-in](../../2014/database-engine/edit-checked-in-files.md) </span><span class="sxs-lookup"><span data-stu-id="d9cd0-139">[Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md) </span></span>  
 <span data-ttu-id="d9cd0-140">[Fazer check-out automático de arquivos após editar](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span><span class="sxs-lookup"><span data-stu-id="d9cd0-140">[Automatically Check Out Files Upon Edit](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span></span>  
 <span data-ttu-id="d9cd0-141">[Desfazer check-outs](../../2014/database-engine/undo-checkouts.md) </span><span class="sxs-lookup"><span data-stu-id="d9cd0-141">[Undo Checkouts](../../2014/database-engine/undo-checkouts.md) </span></span>  
 [<span data-ttu-id="d9cd0-142">Gerenciar check-outs</span><span class="sxs-lookup"><span data-stu-id="d9cd0-142">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
