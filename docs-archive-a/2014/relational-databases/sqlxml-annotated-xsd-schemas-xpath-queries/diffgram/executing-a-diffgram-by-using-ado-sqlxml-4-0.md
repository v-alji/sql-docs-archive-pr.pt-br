---
title: Executando um DiffGram usando ADO (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], SQLOLEDB Provider
- ADO [SQLXML]
- SQLXMLOLEDB Provider, DiffGrams
- data providers [SQLXML], SQLOLEDB Provider
- DiffGrams [SQLXML], ADO
ms.assetid: 741fce82-de83-4923-86eb-30acb5b9a5e6
author: rothja
ms.author: jroth
ms.openlocfilehash: b96db25fd46b1ecbbc15c8acd912743e5560f178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574599"
---
# <a name="executing-a-diffgram-by-using-ado-sqlxml-40"></a><span data-ttu-id="8c491-102">Executando um DiffGram usando o ADO (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="8c491-102">Executing a DiffGram by Using ADO (SQLXML 4.0)</span></span>
  <span data-ttu-id="8c491-103">Este aplicativo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic usa o ADO para estabelecer uma conexão com uma instância do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e então executar um DiffGram.</span><span class="sxs-lookup"><span data-stu-id="8c491-103">This [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application uses ADO to establish a connection to an instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then executes a DiffGram.</span></span> <span data-ttu-id="8c491-104">Nesse aplicativo, o DiffGram e o esquema XSD são armazenados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8c491-104">In this application, the DiffGram and the XSD schema are stored in a file.</span></span> <span data-ttu-id="8c491-105">O aplicativo carrega o DiffGram a partir do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="8c491-105">The application loads the DiffGram from the specified file.</span></span> <span data-ttu-id="8c491-106">Você pode usar qualquer um dos DiffGrams (e o esquema XSD associado) descrito em [exemplos de DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="8c491-106">You can use any of the DiffGrams (and the associated XSD schema) described in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="8c491-107">Este é o processo para o aplicativo de exemplo:</span><span class="sxs-lookup"><span data-stu-id="8c491-107">This is the process for the sample application:</span></span>  
  
-   <span data-ttu-id="8c491-108">O objeto **Conn** (**ADODB. Conexão**) estabelece uma conexão com uma instância em execução do SQL Server em um servidor específico.</span><span class="sxs-lookup"><span data-stu-id="8c491-108">The **conn** object (**ADODB.Connection**) establishes a connection to a running instance of SQL Server on a specific server.</span></span>  
  
-   <span data-ttu-id="8c491-109">O objeto **cmd** (**ADODB. Command**) é executado na conexão estabelecida.</span><span class="sxs-lookup"><span data-stu-id="8c491-109">The **cmd** object (**ADODB.Command**) executes on the established connection.</span></span>  
  
-   <span data-ttu-id="8c491-110">O dialeto do comando é definido como DBGUID_MSSQLXML.</span><span class="sxs-lookup"><span data-stu-id="8c491-110">The command dialect is set to DBGUID_MSSQLXML.</span></span>  
  
-   <span data-ttu-id="8c491-111">O DiffGram é copiado para o fluxo de comando (**strmIn**) de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8c491-111">The DiffGram is copied to the command stream (**strmIn**) from a file.</span></span>  
  
-   <span data-ttu-id="8c491-112">O fluxo de saída do comando é definido como o objeto **StrmOut** (**ADODB. Stream**) para receber todos os dados retornados.</span><span class="sxs-lookup"><span data-stu-id="8c491-112">The command's output stream is set to the **StrmOut** object (**ADODB.Stream**) to receive any returned data.</span></span>  
  
-   <span data-ttu-id="8c491-113">Ao usar o Provedor SQLOLEDB, por padrão, você obterá a funcionalidade do Microsoft SQLXML fornecida por Sqlxmlx.dll.</span><span class="sxs-lookup"><span data-stu-id="8c491-113">When you are using the SQLOLEDB Provider, by default you will get the Microsoft SQLXML functionality provided by Sqlxmlx.dll.</span></span> <span data-ttu-id="8c491-114">Para usar Sqlxml4.dll com o provedor SQLOLEDB, a propriedade **Version do SQLXML** deve ser definida como **SQLXML. 4.0** no objeto de **conexão** do provedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="8c491-114">To use Sqlxml4.dll with the SQLOLEDB Provider, the **SQLXML Version** property must be set to **SQLXML.4.0** on the SQLOLEDB Provider **Connection** object.</span></span>  
  
-   <span data-ttu-id="8c491-115">O comando (DiffGram) é executado.</span><span class="sxs-lookup"><span data-stu-id="8c491-115">The command (DiffGram) is executed.</span></span>  
  
 <span data-ttu-id="8c491-116">O código a seguir é o aplicativo de exemplo.</span><span class="sxs-lookup"><span data-stu-id="8c491-116">The following code is the sample application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c491-117">No código, é necessário fornecer o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="8c491-117">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
Private Sub Command1_Click()  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmOut As New ADODB.Stream  
  Dim strmIn As New ADODB.Stream  
  
  'Open a connection to SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=SqlServerName; database=tempdb; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  strmIn.Open  
  strmIn.Charset = "UTF-8"  
  strmIn.LoadFromFile "C:\SomeFilePath\SampleDiffGram.xml"  
  strmIn.Position = 0  
  Set cmd.CommandStream = strmIn  
  
  strmOut.Open  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Properties("Output Encoding").Value = "UTF-8"  
  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  cmd.Properties("Mapping Schema") = "C:\SomeFilePath\SampleDiffGram.xml"  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Set cmd = Nothing  
  strmOut.Charset = "UTF-8"  
  strmOut.SaveToFile "C:\DropIt.txt", adSaveCreateOverWrite  
  strmOut.Close  
  Set strmOut = Nothing  
  
End Sub  
```  
  
### <a name="to-test-the-diffgram"></a><span data-ttu-id="8c491-118">Para testar o DiffGram</span><span class="sxs-lookup"><span data-stu-id="8c491-118">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="8c491-119">Para uma pasta no seu computador, copie qualquer um dos DiffGrams e o esquema XSD correspondente de um dos exemplos em exemplos de [DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="8c491-119">To a folder on your computer, copy any one of the DiffGrams and the corresponding XSD schema from one of the examples in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="8c491-120">Abra o Visual Basic e crie um projeto EXE padrão.</span><span class="sxs-lookup"><span data-stu-id="8c491-120">Open Visual Basic and create a Standard EXE project.</span></span>  
  
3.  <span data-ttu-id="8c491-121">Adicione estas referências ao projeto:</span><span class="sxs-lookup"><span data-stu-id="8c491-121">Add these references to the project:</span></span>  
  
    ```  
    Microsoft ActiveX Data Objects 2.8 Library  
    ```  
  
4.  <span data-ttu-id="8c491-122">Na caixa de ferramentas, clique em **CommandButton**e desenhe um botão no formulário.</span><span class="sxs-lookup"><span data-stu-id="8c491-122">In the Toolbox, click **CommandButton**, and then draw a button on the form.</span></span>  
  
5.  <span data-ttu-id="8c491-123">Clique duas vezes no botão para editar o código e adicione o código do aplicativo que é fornecido no tópico.</span><span class="sxs-lookup"><span data-stu-id="8c491-123">Double-click the button to edit the code, and add the application code that is provided in the topic.</span></span>  
  
6.  <span data-ttu-id="8c491-124">Edite o código para especificar os nomes do DiffGram e do arquivo XSD.</span><span class="sxs-lookup"><span data-stu-id="8c491-124">Edit the code to specify the DiffGram and XSD file names.</span></span> <span data-ttu-id="8c491-125">Edite também a cadeia de conexão, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="8c491-125">Also edit the connection string as appropriate.</span></span>  
  
7.  <span data-ttu-id="8c491-126">Execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8c491-126">Execute the application.</span></span> <span data-ttu-id="8c491-127">O resultado da execução depende do DiffGram que você está executando.</span><span class="sxs-lookup"><span data-stu-id="8c491-127">The result of the execution depends on what DiffGram you are executing.</span></span>  
  
  
