---
title: Gerenciador de Conexões de Vários Arquivos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- Multiple Files connection manager
- connection managers [Integration Services], Multiple Files
- connections [Integration Services], files
- multiple file connections
ms.assetid: 10bdc56e-c5cd-4ddb-b2f7-375fe57fe8b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9ebd45aa4f0794d98be6a79125bf1874913d491
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582083"
---
# <a name="multiple-files-connection-manager"></a><span data-ttu-id="d43a6-102">Gerenciador de conexões de vários arquivos</span><span class="sxs-lookup"><span data-stu-id="d43a6-102">Multiple Files Connection Manager</span></span>
  <span data-ttu-id="d43a6-103">Um gerenciador de conexões de Vários Arquivos permite que um pacote faça referência a arquivos e pastas existentes ou crie arquivos e pastas em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d43a6-103">A Multiple Files connection manager enables a package to reference existing files and folders, or to create files and folders at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d43a6-104">As tarefas internas e os componentes de fluxo de dados do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] não usam o gerenciador de conexões de vários arquivos.</span><span class="sxs-lookup"><span data-stu-id="d43a6-104">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="d43a6-105">No entanto você pode usar o gerenciador de conexões na tarefa Script ou no componente Script.</span><span class="sxs-lookup"><span data-stu-id="d43a6-105">However, you can use this connection manager in the Script task or Script component.</span></span> <span data-ttu-id="d43a6-106">Para obter informações sobre como usar gerenciadores de conexões na tarefa Script, consulte [Conectando-se a fontes de dados na tarefa Script](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="d43a6-106">For information about how to use connection managers in the Script task, see [Connecting to Data Sources in the Script Task](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span></span> <span data-ttu-id="d43a6-107">Para obter informações sobre como usar gerenciadores de conexões no componente Script, consulte [conectando-se a fontes de dados no componente Script] (.. /extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="d43a6-107">For information about how to use connection managers in the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span></span>  
  
## <a name="usage-types-of-the-multiple-files-connection-manager"></a><span data-ttu-id="d43a6-108">Tipos de uso do gerenciador de conexões de vários arquivos</span><span class="sxs-lookup"><span data-stu-id="d43a6-108">Usage Types of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="d43a6-109">A propriedade `FileUsageType` do gerenciador de conexões de vários arquivos especifica como a conexão é utilizada.</span><span class="sxs-lookup"><span data-stu-id="d43a6-109">The `FileUsageType` property of the Multiple Files connection manager specifies how the connection is used.</span></span> <span data-ttu-id="d43a6-110">O gerenciador de conexões de vários arquivos pode criar arquivos, pastas e usar arquivos e pastas existentes.</span><span class="sxs-lookup"><span data-stu-id="d43a6-110">The Multiple Files connection manager can create files, create folders, use existing files, and use existing folders.</span></span>  
  
 <span data-ttu-id="d43a6-111">A tabela a seguir lista os valores de `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="d43a6-111">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="d43a6-112">Valor</span><span class="sxs-lookup"><span data-stu-id="d43a6-112">Value</span></span>|<span data-ttu-id="d43a6-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d43a6-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d43a6-114">**0**</span><span class="sxs-lookup"><span data-stu-id="d43a6-114">**0**</span></span>|<span data-ttu-id="d43a6-115">O gerenciador de conexões de vários arquivos utiliza um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="d43a6-115">Multiple Files connection manager uses an existing file.</span></span>|  
|<span data-ttu-id="d43a6-116">**1**</span><span class="sxs-lookup"><span data-stu-id="d43a6-116">**1**</span></span>|<span data-ttu-id="d43a6-117">O gerenciador de conexões de vários arquivos cria um arquivo.</span><span class="sxs-lookup"><span data-stu-id="d43a6-117">Multiple Files connection manager creates a file.</span></span>|  
|<span data-ttu-id="d43a6-118">**2**</span><span class="sxs-lookup"><span data-stu-id="d43a6-118">**2**</span></span>|<span data-ttu-id="d43a6-119">O gerenciador de conexões de vários arquivos utiliza uma pasta existente.</span><span class="sxs-lookup"><span data-stu-id="d43a6-119">Multiple Files connection manager uses an existing folder.</span></span>|  
|<span data-ttu-id="d43a6-120">**3**</span><span class="sxs-lookup"><span data-stu-id="d43a6-120">**3**</span></span>|<span data-ttu-id="d43a6-121">O gerenciador de conexões de vários arquivos cria uma pasta.</span><span class="sxs-lookup"><span data-stu-id="d43a6-121">Multiple Files connection manager creates a folder.</span></span>|  
  
## <a name="configuration-of-the-multiple-files-connection-manager"></a><span data-ttu-id="d43a6-122">Configuração do gerenciador de conexões de vários arquivos</span><span class="sxs-lookup"><span data-stu-id="d43a6-122">Configuration of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="d43a6-123">Quando você adicionar um gerenciador de conexões de vários arquivos a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] criará um gerenciador de conexões que será resolvido como um gerenciador de conexões de vários arquivos no tempo de execução, definirá as propriedades de conexão de vários arquivos e adicionará essa conexão à coleção `Connections` do pacote.</span><span class="sxs-lookup"><span data-stu-id="d43a6-123">When you add a Multiple Files connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a Multiple Files connection at run time, sets the Multiple Files connection properties, and adds the Multiple Files connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="d43a6-124">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `MULTIFILE`.</span><span class="sxs-lookup"><span data-stu-id="d43a6-124">The `ConnectionManagerType` property of the connection manager is set to `MULTIFILE`.</span></span>  
  
 <span data-ttu-id="d43a6-125">Você pode configurar um gerenciador de conexões de vários arquivos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d43a6-125">You can configure a Multiple Files connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="d43a6-126">Especifique o tipo de uso de arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="d43a6-126">Specify the usage type of files and folders.</span></span>  
  
-   <span data-ttu-id="d43a6-127">Especifique as pastas e os arquivos.</span><span class="sxs-lookup"><span data-stu-id="d43a6-127">Specify files and folders.</span></span>  
  
-   <span data-ttu-id="d43a6-128">Se estiver usando vários arquivos ou pastas, especifique a ordem na qual devem ser acessados os arquivos e as pastas.</span><span class="sxs-lookup"><span data-stu-id="d43a6-128">If using multiple files or folders, specify the order in which the files and folders are accessed.</span></span>  
  
 <span data-ttu-id="d43a6-129">Se o gerenciador de conexões de vários arquivos consultar vários arquivos e pastas, os caminhos dos arquivos e pastas serão separados pelo caractere pipe (|).</span><span class="sxs-lookup"><span data-stu-id="d43a6-129">If the Multiple Files connection manager references multiple files and folders, the paths of the files and folders are separated by the pipe (|) character.</span></span> <span data-ttu-id="d43a6-130">A propriedade `ConnectionString` do gerenciador de conexões tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="d43a6-130">The `ConnectionString` property of the connection manager has the following format:</span></span>  
  
 \<*path*>|\<*path*>  
  
 <span data-ttu-id="d43a6-131">Você também pode especificar vários arquivos ou pastas usando caracteres curingas.</span><span class="sxs-lookup"><span data-stu-id="d43a6-131">You can also specify multiple files or folders using wildcard characters.</span></span> <span data-ttu-id="d43a6-132">Por exemplo, para fazer referência a todos os arquivos de texto na unidade C, o valor da `ConnectionString` propriedade pode ser definido como C: \\ \*. txt.</span><span class="sxs-lookup"><span data-stu-id="d43a6-132">For example, to reference all the text files on the C drive, the value of the `ConnectionString` property can be set to C:\\*.txt.</span></span>  
  
 <span data-ttu-id="d43a6-133">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="d43a6-133">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d43a6-134">Para obter mais informações sobre as propriedades que podem ser definidas no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Referência da interface do usuário da caixa de diálogo Adicionar Gerenciador de Conexões de Arquivos](add-file-connection-manager-dialog-box-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d43a6-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add File Connection Manager Dialog Box UI Reference](add-file-connection-manager-dialog-box-ui-reference.md).</span></span>  
  
 <span data-ttu-id="d43a6-135">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="d43a6-135">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
