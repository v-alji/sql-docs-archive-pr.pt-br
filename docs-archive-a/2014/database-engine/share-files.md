---
title: Compartilhar arquivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sharing files
- file sharing [SQL Server]
- version control services [SQL Server], file sharing
ms.assetid: 645f5c0a-e949-4e87-8988-85e4d6128464
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 79909fcdb09e349798edfe285475f8a898c3bf04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685256"
---
# <a name="share-files"></a><span data-ttu-id="5db3d-102">Compartilhar arquivos</span><span class="sxs-lookup"><span data-stu-id="5db3d-102">Share Files</span></span>
  <span data-ttu-id="5db3d-103">Você pode usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para compartilhar itens em projetos de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="5db3d-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to share items across source control projects.</span></span> <span data-ttu-id="5db3d-104">Quando você compartilha um item, as alterações feitas nele são refletidas em todos os projetos em que ele é compartilhado.</span><span class="sxs-lookup"><span data-stu-id="5db3d-104">When you share an item, any changes to the item are reflected in every project to which the item is shared.</span></span>  
  
 <span data-ttu-id="5db3d-105">O compartilhamento de itens oferece as vantagens a seguir para usuários de controle do código-fonte:</span><span class="sxs-lookup"><span data-stu-id="5db3d-105">Item sharing provides the following advantages to source control users:</span></span>  
  
-   <span data-ttu-id="5db3d-106">Torna desnecessário o armazenamento de uma cópia separada do item para cada projeto que usa o item compartilhado, preservando assim espaço em disco no cliente e no servidor de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="5db3d-106">Makes it unnecessary for each project that uses the shared item to store a separate copy of the item, conserving disk space on both the source control client and server.</span></span> <span data-ttu-id="5db3d-107">O provedor de controle do código-fonte armazena o item compartilhado em um local central e todos os projetos em que ele é compartilhado armazenam um ponteiro para aquele local.</span><span class="sxs-lookup"><span data-stu-id="5db3d-107">The source control provider stores the shared item in one central location, and every project to which it is shared stores a pointer to that location.</span></span>  
  
-   <span data-ttu-id="5db3d-108">Evita problemas de compatibilidade de versões.</span><span class="sxs-lookup"><span data-stu-id="5db3d-108">Avoids version incompatibilities.</span></span> <span data-ttu-id="5db3d-109">Como todos os projetos usam a mesma versão de item compartilhado, você evita conflitos resultantes de alteração de cada cópia de um item independente dentro de vários projetos.</span><span class="sxs-lookup"><span data-stu-id="5db3d-109">Because every project to which the item is shared uses the same version of the item, you avoid the conflicts that arise when each copy of an item is changing independently within multiple projects.</span></span>  
  
### <a name="to-share-an-item"></a><span data-ttu-id="5db3d-110">Para compartilhar um item</span><span class="sxs-lookup"><span data-stu-id="5db3d-110">To share an item</span></span>  
  
1.  <span data-ttu-id="5db3d-111">No Gerenciador de Soluções, selecione a pasta ou o projeto em que você deseja colocar os arquivos compartilhados.</span><span class="sxs-lookup"><span data-stu-id="5db3d-111">In Solution Explorer, select either the folder or project in which you want to place the shared files.</span></span>  
  
2.  <span data-ttu-id="5db3d-112">No menu **arquivo** , aponte para **controle do código-fonte**e clique em **compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="5db3d-112">On the **File** menu, point to **Source Control**, and then click **Share**.</span></span>  
  
3.  <span data-ttu-id="5db3d-113">Na caixa de diálogo **compartilhar com** , procure a lista de diretórios do item que você deseja compartilhar e clique nesse item.</span><span class="sxs-lookup"><span data-stu-id="5db3d-113">In the **Share with** dialog box, browse the directory list for the item you want to share, and click that item.</span></span>  
  
4.  <span data-ttu-id="5db3d-114">Clique em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="5db3d-114">Click **Share**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db3d-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5db3d-115">See Also</span></span>  
 [<span data-ttu-id="5db3d-116">Noções básicas de controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="5db3d-116">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
