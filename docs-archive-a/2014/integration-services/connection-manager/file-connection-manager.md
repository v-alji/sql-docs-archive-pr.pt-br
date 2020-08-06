---
title: Gerenciador de Conexões de Arquivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- files [Integration Services]
- connection managers [Integration Services], File
- connections [Integration Services], files
- File connection manager
ms.assetid: 019078bc-44ee-4975-9169-0f9a89e3f3be
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cebb5438003c6b14c547d14012ff1bc1175a706d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684276"
---
# <a name="file-connection-manager"></a><span data-ttu-id="dcf0f-102">Gerenciador de conexões de arquivos</span><span class="sxs-lookup"><span data-stu-id="dcf0f-102">File Connection Manager</span></span>
  <span data-ttu-id="dcf0f-103">Um gerenciador de conexões de Arquivo permite que um pacote faça referência a um arquivo ou pasta existente ou crie um arquivo ou pasta em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-103">A File connection manager enables a package to reference an existing file or folder, or to create a file or folder at run time.</span></span> <span data-ttu-id="dcf0f-104">Por exemplo, você pode fazer referência a um arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-104">For example, you can reference an Excel file.</span></span> <span data-ttu-id="dcf0f-105">Alguns componentes em [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usam as informações nos arquivos para executar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-105">Certain components in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] use information in files to perform their work.</span></span> <span data-ttu-id="dcf0f-106">Por exemplo, uma tarefa Executar SQL pode fazer referência a um arquivo que contém as instruções SQL que a tarefa executa.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-106">For example, an Execute SQL task can reference a file that contains the SQL statements that the task executes.</span></span> <span data-ttu-id="dcf0f-107">Outros componentes executam operações em arquivos.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-107">Other components perform operations on files.</span></span> <span data-ttu-id="dcf0f-108">Por exemplo, a tarefa Sistema de Arquivos pode fazer referência a um arquivo para copiá-lo para um novo local.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-108">For example, the File System task can reference a file to copy it to a new location.</span></span>  
  
## <a name="usage-types-of-the-file-connection-manager"></a><span data-ttu-id="dcf0f-109">Tipos de uso do gerenciador de conexões de arquivos</span><span class="sxs-lookup"><span data-stu-id="dcf0f-109">Usage Types of the File Connection Manager</span></span>  
 <span data-ttu-id="dcf0f-110">A propriedade `FileUsageType` do gerenciador de conexões de arquivos especifica como a conexão de arquivos é utilizada.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-110">The `FileUsageType` property of the File connection manager specifies how the file connection is used.</span></span> <span data-ttu-id="dcf0f-111">O gerenciador de conexões de arquivos pode criar tanto um arquivo quanto uma pasta e utilizar um arquivo ou uma pasta existente.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-111">The File connection manager can create a file, create a folder, use an existing file, or use an existing folder.</span></span>  
  
 <span data-ttu-id="dcf0f-112">A tabela a seguir lista os valores de `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-112">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="dcf0f-113">Valor</span><span class="sxs-lookup"><span data-stu-id="dcf0f-113">Value</span></span>|<span data-ttu-id="dcf0f-114">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="dcf0f-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="dcf0f-115">O gerenciador de conexões de arquivos utiliza um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-115">File connection manager uses an existing file.</span></span>|  
|`1`|<span data-ttu-id="dcf0f-116">O gerenciador de conexões de arquivos cria um arquivo.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-116">File connection manager creates a file.</span></span>|  
|`2`|<span data-ttu-id="dcf0f-117">O gerenciador de conexões de arquivos utiliza um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-117">File connection manager uses an existing folder.</span></span>|  
|`3`|<span data-ttu-id="dcf0f-118">O gerenciador de conexões de arquivos cria um arquivo.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-118">File connection manager creates a folder.</span></span>|  
  
## <a name="multiple-file-or-folder-connections"></a><span data-ttu-id="dcf0f-119">Várias conexões de arquivo ou pasta</span><span class="sxs-lookup"><span data-stu-id="dcf0f-119">Multiple File or Folder Connections</span></span>  
 <span data-ttu-id="dcf0f-120">O gerenciador de conexões de arquivos pode fazer referência a apenas um arquivo ou a uma pasta.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-120">The File connection manager can reference only one file or folder.</span></span> <span data-ttu-id="dcf0f-121">Para consultar vários arquivos ou pastas, utilize um gerenciador de conexões para vários arquivos em vez de um gerenciador de conexões de arquivos.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-121">To reference multiple files or folders, use a Multiple Files connection manager instead of a File connection manager.</span></span> <span data-ttu-id="dcf0f-122">Para obter mais informações, consulte [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dcf0f-122">For more information, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
## <a name="configuration-of-the-file-connection-manager"></a><span data-ttu-id="dcf0f-123">Configuração do gerenciador de conexões de arquivo</span><span class="sxs-lookup"><span data-stu-id="dcf0f-123">Configuration of the File Connection Manager</span></span>  
 <span data-ttu-id="dcf0f-124">Quando você adicionar um gerenciador de conexões de arquivos a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] criará um gerenciador de conexões que determinará uma conexão de Arquivo no tempo de execução, definirá as propriedades da conexão de Arquivos e irá adicioná-la à coleção `Connections` do pacote.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-124">When you add a File connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a File connection at run time, sets the File connection properties, and adds the File connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="dcf0f-125">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `FILE`.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-125">The `ConnectionManagerType` property of the connection manager is set to `FILE`.</span></span>  
  
 <span data-ttu-id="dcf0f-126">Você pode configurar um gerenciador de conexões de arquivos dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="dcf0f-126">You can configure a File connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="dcf0f-127">Especificando o tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-127">Specify the usage type.</span></span>  
  
-   <span data-ttu-id="dcf0f-128">Especificando um arquivo ou uma pasta.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-128">Specify a file or folder.</span></span>  
  
 <span data-ttu-id="dcf0f-129">Você pode definir a propriedade ConnectionString para o gerenciador de conexões de arquivos especificando uma expressão na janela Propriedades do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcf0f-129">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="dcf0f-130">No entanto, para evitar um erro de validação ao usar uma expressão para especificar o arquivo ou a pasta, no **Editor do Gerenciador de Conexões de Arquivos**, para **Arquivo/Pasta**, adicione um caminho de arquivo ou de pasta.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-130">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="dcf0f-131">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="dcf0f-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="dcf0f-132">Para obter mais informações sobre as propriedades que podem ser definidas no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Editor do Gerenciador de Conexões de Arquivos](../file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="dcf0f-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [File Connection Manager Editor](../file-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="dcf0f-133">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="dcf0f-133">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
