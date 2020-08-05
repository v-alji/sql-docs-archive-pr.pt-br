---
title: Adicionar snippets de Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 901c7995-8eb5-4d12-8bb0-de0a922b48f8
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b5886f8f36ae3753fcb7c89dd3aeff9c69eeba5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572471"
---
# <a name="add-transact-sql-snippets"></a><span data-ttu-id="f4f27-102">Adicionar snippets de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f4f27-102">Add Transact-SQL Snippets</span></span>
  <span data-ttu-id="f4f27-103">Você pode adicionar seus próprios snippets de código Transact-SQL ao conjunto de snippets predefinidos incluídos em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4f27-103">You can add your own Transact-SQL code snippets to the set of pre-defined snippets included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="creating-a-transact-sql-snippet-file"></a><span data-ttu-id="f4f27-104">Criando um arquivo de snippet Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f4f27-104">Creating a Transact-SQL Snippet File</span></span>  
 <span data-ttu-id="f4f27-105">A primeira parte da criação de um snippet de código do [!INCLUDE[tsql](../../includes/tsql-md.md)] é criar um arquivo XML com o texto do seu snippet de código.</span><span class="sxs-lookup"><span data-stu-id="f4f27-105">The first part of creating a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is to create an XML file with the text of your code snippet.</span></span> <span data-ttu-id="f4f27-106">O arquivo deve ter uma extensão .snippet e atender as requisitos do [Esquema de trechos de código](https://go.microsoft.com/fwlink/?LinkId=207504).</span><span class="sxs-lookup"><span data-stu-id="f4f27-106">The file must have a .snippet file extension, and meet the requirements of the [Code Snippets Schema](https://go.microsoft.com/fwlink/?LinkId=207504).</span></span> <span data-ttu-id="f4f27-107">Defina a linguagem do snippet como SQL.</span><span class="sxs-lookup"><span data-stu-id="f4f27-107">Set the snippet language to SQL.</span></span>  
  
 <span data-ttu-id="f4f27-108">Você pode usar os snippets predefinidos fornecidos com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como exemplos.</span><span class="sxs-lookup"><span data-stu-id="f4f27-108">You can use the pre-defined snippets that ship with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as examples.</span></span> <span data-ttu-id="f4f27-109">Para encontrar os snippets predefinidos, abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selecione o menu **Ferramentas** e clique em **Gerenciador de Snippets de Código**.</span><span class="sxs-lookup"><span data-stu-id="f4f27-109">To find the pre-defined snippets, open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Tools** menu, and click **Code Snippet Manager**.</span></span> <span data-ttu-id="f4f27-110">Selecione **SQL** na caixa de listagem **Linguagem** ; o caminho para os snippets do [!INCLUDE[tsql](../../includes/tsql-md.md)] será exibido na caixa **Local** .</span><span class="sxs-lookup"><span data-stu-id="f4f27-110">Select **SQL** in the **Language** list box, the path to the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippets is displayed in the **Location** box.</span></span>  
  
## <a name="registering-the-code-snippet"></a><span data-ttu-id="f4f27-111">Registrando o snippet de código</span><span class="sxs-lookup"><span data-stu-id="f4f27-111">Registering the Code Snippet</span></span>  
 <span data-ttu-id="f4f27-112">Após criar o arquivo de snippet, use o Gerenciador de Snippets de Código para registrar o snippet com o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4f27-112">After creating the snippet file, use the Code Snippets Manager to register the snippet with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f4f27-113">Você pode adicionar uma pasta que contém vários snippets ou importar snippets individuais para a pasta **Meus Snippets de Código** .</span><span class="sxs-lookup"><span data-stu-id="f4f27-113">You can either add a folder containing multiple snippets, or import individual snippets to the **My Code Snippets** folder.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f4f27-114">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="f4f27-114">Procedures</span></span>  
  
#### <a name="adding-a-snippet-folder"></a><span data-ttu-id="f4f27-115">Adicionando uma pasta de snippets</span><span class="sxs-lookup"><span data-stu-id="f4f27-115">Adding a Snippet Folder</span></span>  
  
1.  <span data-ttu-id="f4f27-116">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4f27-116">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="f4f27-117">Selecione o menu **Ferramentas** e clique em **Gerenciador de Snippets de Código**.</span><span class="sxs-lookup"><span data-stu-id="f4f27-117">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="f4f27-118">Clique no botão **Adicionar** .</span><span class="sxs-lookup"><span data-stu-id="f4f27-118">Click the **Add** button.</span></span>  
  
4.  <span data-ttu-id="f4f27-119">Navegue até a pasta que contém seus snippets de código e clique no botão **Selecionar Pasta** .</span><span class="sxs-lookup"><span data-stu-id="f4f27-119">Navigate to the folder containing your code snippets, and click the **Select Folder** button.</span></span>  
  
#### <a name="importing-a-snippet"></a><span data-ttu-id="f4f27-120">Importando um snippet</span><span class="sxs-lookup"><span data-stu-id="f4f27-120">Importing a Snippet</span></span>  
  
1.  <span data-ttu-id="f4f27-121">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4f27-121">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="f4f27-122">Selecione o menu **Ferramentas** e clique em **Gerenciador de Snippets de Código**.</span><span class="sxs-lookup"><span data-stu-id="f4f27-122">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="f4f27-123">Clique no botão **Importar**.</span><span class="sxs-lookup"><span data-stu-id="f4f27-123">Click the **Import** button.</span></span>  
  
4.  <span data-ttu-id="f4f27-124">Navegue até a pasta que contém seu trecho, clique no arquivo .snippet e clique em **Abrir** .</span><span class="sxs-lookup"><span data-stu-id="f4f27-124">Navigate to the folder containing your snippet, click on the .snippet file, and click the **Open** button.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f4f27-125">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f4f27-125">Examples</span></span>  
 <span data-ttu-id="f4f27-126">O exemplo a seguir cria um snippet surround-with `TRY-CATCH` e o importa para o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4f27-126">The following example creates a `TRY-CATCH` surround-with snippet and imports it to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="f4f27-127">Cole o código a seguir no bloco de notas e salve como um arquivo chamado TryCatch.snippet.</span><span class="sxs-lookup"><span data-stu-id="f4f27-127">Paste the following code into notepad, then save as a file named TryCatch.snippet.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="https://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
    <_locDefinition xmlns="urn:locstudio">  
        <_locDefault _loc="locNone" />  
        <_locTag _loc="locData">Title</_locTag>  
        <_locTag _loc="locData">Description</_locTag>  
        <_locTag _loc="locData">Author</_locTag>  
        <_locTag _loc="locData">ToolTip</_locTag>  
       <_locTag _loc="locData">Default</_locTag>  
    </_locDefinition>  
    <CodeSnippet Format="1.0.0">  
    <Header>  
    <Title>TryCatch</Title>  
                            <Shortcut></Shortcut>  
    <Description>Example Snippet for Try-Catch.</Description>  
    <Author>SQL Server Books Online Example</Author>  
    <SnippetTypes>  
                                    <SnippetType>SurroundsWith</SnippetType>  
    </SnippetTypes>  
    </Header>  
    <Snippet>  
    <Declarations>  
                                    <Literal>  
                                    <ID>CatchCode</ID>  
                                    <ToolTip>Code to handle the caught error</ToolTip>  
                                    <Default>CatchCode</Default>  
                                    </Literal>  
    </Declarations>  
    <Code Language="SQL"><![CDATA[  
    BEGIN TRY  
  
    $selected$ $end$  
  
    END TRY  
    BEGIN CATCH  
  
    $CatchCode$  
  
    END CATCH;  
    ]]>  
    </Code>  
    </Snippet>  
    </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
2.  <span data-ttu-id="f4f27-128">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4f27-128">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="f4f27-129">Selecione o menu **Ferramentas** e clique em **Gerenciador de Snippets de Código**.</span><span class="sxs-lookup"><span data-stu-id="f4f27-129">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
4.  <span data-ttu-id="f4f27-130">Clique no botão **Importar**.</span><span class="sxs-lookup"><span data-stu-id="f4f27-130">Click the **Import** button.</span></span>  
  
5.  <span data-ttu-id="f4f27-131">Navegue até a pasta que contém TryCatch.snippet, clique no arquivo TryCatch.snippet e clique em **Abrir** .</span><span class="sxs-lookup"><span data-stu-id="f4f27-131">Navigate to the folder containing TryCatch.snippet, click on the TryCatch.snippet file, and click the **Open** button.</span></span> <span data-ttu-id="f4f27-132">Você não deve ter um snippet TryCatch na pasta **Meus Snippets de Código** .</span><span class="sxs-lookup"><span data-stu-id="f4f27-132">You should not have a TryCatch snippet in your **My Code Snippets** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f27-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4f27-133">See Also</span></span>  
 [<span data-ttu-id="f4f27-134">Inserir snippets Transact-SQL com Surround</span><span class="sxs-lookup"><span data-stu-id="f4f27-134">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
