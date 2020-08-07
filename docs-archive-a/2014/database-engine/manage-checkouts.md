---
title: Gerenciar Check-outs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- source controls [SQL Server Management Studio], checkouts
- checkouts [SQL Server Management Studio]
- checking out files
ms.assetid: ddd4adba-d432-4005-9cb2-bb9ee3163d8e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfa25cdc27e707d4be705e66b215130c9d70ce1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583764"
---
# <a name="manage-checkouts"></a><span data-ttu-id="7f1d1-102">Gerenciar check-outs</span><span class="sxs-lookup"><span data-stu-id="7f1d1-102">Manage Checkouts</span></span>
  <span data-ttu-id="7f1d1-103">Depois que um arquivo é adicionado ao controle do código-fonte, faça check-out do arquivo antes de você fazer modificações nele.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-103">After a file has been added to source control, you must check out the file before you can modify it.</span></span> <span data-ttu-id="7f1d1-104">Ao fazer o check-out de um arquivo com controle do código-fonte, o provedor de controle do código-fonte cria uma cópia da versão mais recente em seu disco local e remove o atributo somente leitura do arquivo.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-104">When you check a file out of source control, the source control provider creates a copy of the latest version on your local disk and removes the read-only attribute of the file.</span></span> <span data-ttu-id="7f1d1-105">Em algumas circunstâncias, você pode precisar editar um arquivo sem fazer check-out do mesmo.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-105">In some circumstances you might need to edit a file without checking out the file.</span></span> <span data-ttu-id="7f1d1-106">Para obter mais informações sobre como editar um arquivo sem fazer check-out do arquivo, consulte [Editar arquivos com check-in](../../2014/database-engine/edit-checked-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="7f1d1-106">For more information about editing a file without checking the file out, see [Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md).</span></span>  
  
 <span data-ttu-id="7f1d1-107">Você pode usar o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para fazer check-out de arquivos manualmente ou automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-107">You can use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out files manually or automatically.</span></span> <span data-ttu-id="7f1d1-108">Você faz check-out dos arquivos manualmente abrindo a solução que contém os arquivos no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] ambiente e, em seguida, clicando no comando **check-out** .</span><span class="sxs-lookup"><span data-stu-id="7f1d1-108">You check out files manually by opening the solution that contains the files in the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment, and then clicking the **Check Out** command.</span></span> <span data-ttu-id="7f1d1-109">Você também pode fazer check-out dos arquivos automaticamente se configurar o ambiente do [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-109">You can check out files automatically if you configure the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to do so.</span></span>  
  
 <span data-ttu-id="7f1d1-110">Dependendo das opções definidas pelo administrador do provedor de controle de código-fonte, você também pode fazer check-out dos arquivos em modo exclusivo ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-110">Depending on the options that your administrator sets on your source control provider, you can also check out files in exclusive or shared mode.</span></span> <span data-ttu-id="7f1d1-111">Quando você fizer o check-out de um arquivo exclusivamente, somente você poderá modificá-lo, nenhum outro usuário poderá fazer o check-out do arquivo até você terminar.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-111">When you check out a file exclusively, only you can modify it, and no other user can check out the file until you check it in.</span></span> <span data-ttu-id="7f1d1-112">Quando você fizer o check-out em um arquivo no modo compartilhado, qualquer número de usuários poderá fazer check-out do mesmo arquivo.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-112">When you check out a file in shared mode, any number of users can check out the same file.</span></span> <span data-ttu-id="7f1d1-113">Cada vez que um usuário faz check-in de um arquivo, o provedor de controle do código-fonte tenta mesclar o arquivo com a versão mais recente disponível no servidor.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-113">As each user checks in the file, the source control provider attempts to merge the file with the latest server version of the file.</span></span> <span data-ttu-id="7f1d1-114">Caso haja conflito entre a versão de check-in e a mais recente, o provedor de controle do código-fonte solicitará que o usuário resolva os conflitos.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-114">If conflicts arise between the version that is being checked in and the latest version, the source control provider prompts the user to resolve the conflicts.</span></span>  
  
 <span data-ttu-id="7f1d1-115">A tabela a seguir descreve os tópicos dessa seção.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-115">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="7f1d1-116">Tópico</span><span class="sxs-lookup"><span data-stu-id="7f1d1-116">Topic</span></span>|<span data-ttu-id="7f1d1-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="7f1d1-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7f1d1-118">Fazer check-out de arquivos</span><span class="sxs-lookup"><span data-stu-id="7f1d1-118">Check Out Files</span></span>](../../2014/database-engine/check-out-files.md)|<span data-ttu-id="7f1d1-119">Fornece instruções sobre como fazer check-out de um arquivo para que você possa modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-119">Provides instructions on how to check out a file so you can modify it.</span></span>|  
|[<span data-ttu-id="7f1d1-120">Desfazer check-outs</span><span class="sxs-lookup"><span data-stu-id="7f1d1-120">Undo Checkouts</span></span>](../../2014/database-engine/undo-checkouts.md)|<span data-ttu-id="7f1d1-121">Explica como cancelar um check-out existente.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-121">Explains how to cancel an existing checkout.</span></span>|  
|[<span data-ttu-id="7f1d1-122">Fazer check-out automático de arquivos na edição</span><span class="sxs-lookup"><span data-stu-id="7f1d1-122">Automatically Check Out Files Upon Edit</span></span>](../../2014/database-engine/automatically-check-out-files-upon-edit.md)|<span data-ttu-id="7f1d1-123">Explica como configurar o controle do código-fonte para fazer check-out de um arquivo quando você começa a editá-lo.</span><span class="sxs-lookup"><span data-stu-id="7f1d1-123">Explains how to configure source control to check out a file when you start to edit it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f1d1-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f1d1-124">See Also</span></span>  
 <span data-ttu-id="7f1d1-125">[Gerenciar Check-ins](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="7f1d1-125">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="7f1d1-126">Editar arquivos com check-in</span><span class="sxs-lookup"><span data-stu-id="7f1d1-126">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)  
  
  
