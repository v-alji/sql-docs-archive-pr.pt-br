---
title: Editor do Gerenciador de conexões de arquivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnectionmanager.f1
helpviewer_keywords:
- File Connection Manager Editor
ms.assetid: 051c48e5-3d86-49af-b554-ff62e3de3622
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f3261b836d4800787fc078b05b15e469d3c200d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582005"
---
# <a name="file-connection-manager-editor"></a><span data-ttu-id="6afdf-102">Editor do Gerenciador de Conexões de Arquivos</span><span class="sxs-lookup"><span data-stu-id="6afdf-102">File Connection Manager Editor</span></span>
  <span data-ttu-id="6afdf-103">Use a caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos** para especificar as propriedades usadas para conectar a um arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="6afdf-103">Use the **File Connection Manager Editor** dialog box to specify the properties used to connect to a file or a folder.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6afdf-104">Você pode definir a propriedade ConnectionString para o gerenciador de conexões de arquivos especificando uma expressão na janela Propriedades do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6afdf-104">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6afdf-105">No entanto, para evitar um erro de validação ao usar uma expressão para especificar o arquivo ou a pasta, no **Editor do Gerenciador de Conexões de Arquivos**, para **Arquivo/Pasta**, adicione um caminho de arquivo ou de pasta.</span><span class="sxs-lookup"><span data-stu-id="6afdf-105">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="6afdf-106">Para obter mais informações sobre o gerenciador de conexões de Arquivos, consulte [File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6afdf-106">To learn more about the File connection manager, see [File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6afdf-107">Opções</span><span class="sxs-lookup"><span data-stu-id="6afdf-107">Options</span></span>  
 <span data-ttu-id="6afdf-108">**Tipo de Uso**</span><span class="sxs-lookup"><span data-stu-id="6afdf-108">**Usage Type**</span></span>  
 <span data-ttu-id="6afdf-109">Especifique se o **Gerenciador de Conexões de Arquivos** conecta a um arquivo ou pasta existente ou crie um novo arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="6afdf-109">Specify whether the **File Connection Manager** connects to an existing file or folder or creates a new file or folder.</span></span>  
  
|<span data-ttu-id="6afdf-110">Valor</span><span class="sxs-lookup"><span data-stu-id="6afdf-110">Value</span></span>|<span data-ttu-id="6afdf-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="6afdf-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6afdf-112">Criar arquivo</span><span class="sxs-lookup"><span data-stu-id="6afdf-112">Create file</span></span>|<span data-ttu-id="6afdf-113">Crie um novo arquivo em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="6afdf-113">Create a new file at run time.</span></span>|  
|<span data-ttu-id="6afdf-114">Arquivo existente</span><span class="sxs-lookup"><span data-stu-id="6afdf-114">Existing file</span></span>|<span data-ttu-id="6afdf-115">Use um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="6afdf-115">Use an existing file.</span></span>|  
|<span data-ttu-id="6afdf-116">Criar pasta</span><span class="sxs-lookup"><span data-stu-id="6afdf-116">Create folder</span></span>|<span data-ttu-id="6afdf-117">Crie uma nova pasta em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="6afdf-117">Create a new folder at run time.</span></span>|  
|<span data-ttu-id="6afdf-118">Pasta existente</span><span class="sxs-lookup"><span data-stu-id="6afdf-118">Existing folder</span></span>|<span data-ttu-id="6afdf-119">Use uma pasta existente.</span><span class="sxs-lookup"><span data-stu-id="6afdf-119">Use an existing folder.</span></span>|  
  
 <span data-ttu-id="6afdf-120">**Arquivo / Pasta**</span><span class="sxs-lookup"><span data-stu-id="6afdf-120">**File / Folder**</span></span>  
 <span data-ttu-id="6afdf-121">Se **Arquivo**, especifique o arquivo a usar.</span><span class="sxs-lookup"><span data-stu-id="6afdf-121">If **File**, specify the file to use.</span></span>  
  
 <span data-ttu-id="6afdf-122">Se **Pasta**, especifique a pasta a usar.</span><span class="sxs-lookup"><span data-stu-id="6afdf-122">If **Folder**, specify the folder to use.</span></span>  
  
 <span data-ttu-id="6afdf-123">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="6afdf-123">**Browse**</span></span>  
 <span data-ttu-id="6afdf-124">Selecione o arquivo ou pasta usando a caixa de diálogo **Selecionar Arquivo** ou **Procurar Pasta** .</span><span class="sxs-lookup"><span data-stu-id="6afdf-124">Select the file or folder by using the **Select File** or **Browse for Folder** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6afdf-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6afdf-125">See Also</span></span>  
 [<span data-ttu-id="6afdf-126">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="6afdf-126">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
