---
title: Referência de interface do usuário da caixa de diálogo Adicionar Gerenciador de Conexões de Arquivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnection.f1
helpviewer_keywords:
- Add File Connection Manager
ms.assetid: 9370bfb5-5993-4ad8-a9cd-2de53f320f34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 044d8e2eaae9db17d7155cb354f8d009750f44d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684280"
---
# <a name="add-file-connection-manager-dialog-box-ui-reference"></a><span data-ttu-id="f1d15-102">Referência da interface do usuário da caixa de diálogo Adicionar Gerenciador de Conexões de Arquivos</span><span class="sxs-lookup"><span data-stu-id="f1d15-102">Add File Connection Manager Dialog Box UI Reference</span></span>
  <span data-ttu-id="f1d15-103">Use a caixa de diálogo do **Adicionar Gerenciador de Conexões de Arquivos** para definir uma conexão com um grupo de arquivos ou pastas.</span><span class="sxs-lookup"><span data-stu-id="f1d15-103">Use the **Add File Connection Manager** dialog box to define a connection to a group of files or folders.</span></span>  
  
 <span data-ttu-id="f1d15-104">Para obter mais informações sobre o gerenciador de conexões de Vários Arquivos, consulte [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f1d15-104">To learn more about the Multiple Files connection manager, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1d15-105">As tarefas internas e os componentes de fluxo de dados do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] não usam o gerenciador de conexões de vários arquivos.</span><span class="sxs-lookup"><span data-stu-id="f1d15-105">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="f1d15-106">No entanto você pode usar o gerenciador de conexões na tarefa Script ou no componente Script.</span><span class="sxs-lookup"><span data-stu-id="f1d15-106">However, you can use this connection manager in the Script task or Script component.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f1d15-107">Opções</span><span class="sxs-lookup"><span data-stu-id="f1d15-107">Options</span></span>  
 <span data-ttu-id="f1d15-108">**Tipo de uso**</span><span class="sxs-lookup"><span data-stu-id="f1d15-108">**Usage type**</span></span>  
 <span data-ttu-id="f1d15-109">Especifique os tipos de arquivos a serem usados para o gerenciador de conexões de vários arquivos.</span><span class="sxs-lookup"><span data-stu-id="f1d15-109">Specify the type of files to use for the multiple files connection manager.</span></span>  
  
|<span data-ttu-id="f1d15-110">Valor</span><span class="sxs-lookup"><span data-stu-id="f1d15-110">Value</span></span>|<span data-ttu-id="f1d15-111">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f1d15-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f1d15-112">**Criar arquivos**</span><span class="sxs-lookup"><span data-stu-id="f1d15-112">**Create files**</span></span>|<span data-ttu-id="f1d15-113">O gerenciador de conexões criará os arquivos.</span><span class="sxs-lookup"><span data-stu-id="f1d15-113">The connection manager will create the files.</span></span>|  
|<span data-ttu-id="f1d15-114">**Arquivos existentes**</span><span class="sxs-lookup"><span data-stu-id="f1d15-114">**Existing files**</span></span>|<span data-ttu-id="f1d15-115">O gerenciador de conexões utilizará arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="f1d15-115">The connection manager will use existing files.</span></span>|  
|<span data-ttu-id="f1d15-116">**Criar pastas**</span><span class="sxs-lookup"><span data-stu-id="f1d15-116">**Create folders**</span></span>|<span data-ttu-id="f1d15-117">O gerenciador de conexões criará as pastas.</span><span class="sxs-lookup"><span data-stu-id="f1d15-117">The connection manager will create the folders.</span></span>|  
|<span data-ttu-id="f1d15-118">**Pastas existentes**</span><span class="sxs-lookup"><span data-stu-id="f1d15-118">**Existing folders**</span></span>|<span data-ttu-id="f1d15-119">O gerenciador de conexões utilizará pastas existentes.</span><span class="sxs-lookup"><span data-stu-id="f1d15-119">The connection manager will use existing folders.</span></span>|  
  
 <span data-ttu-id="f1d15-120">**Arquivos/Pastas**</span><span class="sxs-lookup"><span data-stu-id="f1d15-120">**Files / Folders**</span></span>  
 <span data-ttu-id="f1d15-121">Exiba os arquivos ou pastas que você adicionou usando os botões descritos abaixo.</span><span class="sxs-lookup"><span data-stu-id="f1d15-121">View the files or folders that you have added by using the buttons described as follows.</span></span>  
  
 <span data-ttu-id="f1d15-122">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="f1d15-122">**Add**</span></span>  
 <span data-ttu-id="f1d15-123">Adicione um arquivo usando a caixa de diálogo **Selecionar Arquivos** ou adicione uma pasta usando a caixa de diálogo **Procurar pasta** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-123">Add a file by using the **Select Files** dialog box, or add a folder by using the **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="f1d15-124">**Editar**</span><span class="sxs-lookup"><span data-stu-id="f1d15-124">**Edit**</span></span>  
 <span data-ttu-id="f1d15-125">Selecione um arquivo ou pasta e substitua-o por um arquivo ou pasta diferente usando a caixa de diálogo **Selecionar arquivos** ou **Procurar pasta** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-125">Select a file or folder, and then replace it with a different file or folder by using the **Select Files** or **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="f1d15-126">**Remover**</span><span class="sxs-lookup"><span data-stu-id="f1d15-126">**Remove**</span></span>  
 <span data-ttu-id="f1d15-127">Selecione um arquivo ou pasta e remova-o da lista usando o botão **Remover** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-127">Select a file or folder, and then remove it from the list by using the **Remove** button.</span></span>  
  
 <span data-ttu-id="f1d15-128">**Botões de seta**</span><span class="sxs-lookup"><span data-stu-id="f1d15-128">**Arrow buttons**</span></span>  
 <span data-ttu-id="f1d15-129">Selecione um arquivo ou pasta e use os botões de seta para movê-los para cima ou para baixo para especificar a sequência de acesso.</span><span class="sxs-lookup"><span data-stu-id="f1d15-129">Select a file or folder, and then use the arrow buttons to move it up or down to specify the sequence of access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d15-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1d15-130">See Also</span></span>  
 [<span data-ttu-id="f1d15-131">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="f1d15-131">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
  
  
