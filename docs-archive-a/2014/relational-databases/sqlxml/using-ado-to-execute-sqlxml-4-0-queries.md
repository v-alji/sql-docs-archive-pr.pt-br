---
title: Usando o ADO para executar consultas do SQLXML 4.0
ms.custom: ''
ms.date: 12/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- query testers [SQLXML]
- test scripts
- ADO [SQLXML]
- queries [SQLXML], ADO
- SQLXML, ADO
ms.assetid: 3d54e3bb-7c5f-427e-82f8-1403a54c4f53
author: rothja
ms.author: jroth
ms.openlocfilehash: 169d20b4192e4a5b8e7b32839f2da255fc58d89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679289"
---
# <a name="using-ado-to-execute-sqlxml-40-queries"></a><span data-ttu-id="03c23-102">Usando o ADO para executar consultas do SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="03c23-102">Using ADO to Execute SQLXML 4.0 Queries</span></span>
  <span data-ttu-id="03c23-103">Nas versões anteriores do SQLXML, o suporte à execução de consultas baseadas em HTTP era oferecido por meio de diretórios virtuais IIS SQLXML e do filtro ISAPI SQLXML.</span><span class="sxs-lookup"><span data-stu-id="03c23-103">In previous versions of SQLXML, HTTP-based query execution was supported using SQLXML IIS virtual directories and the SQLXML ISAPI filter.</span></span> <span data-ttu-id="03c23-104">No SQLXML 4.0, esses componentes foram removidos já que uma funcionalidade semelhante é fornecida com os XML Web Services nativos introduzidos no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03c23-104">In SQLXML 4.0, these components have been removed as similar and overlapping functionality is provided with native XML Web services beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="03c23-105">Como alternativa, você pode executar consultas e usar o SQLXML 4.0 com seus aplicativos baseados no COM, aproveitando as extensões SQLXML para ADO (ActiveX Data Objects) que foram introduzidas pela primeira vez no Microsoft Data Access Components (MDAC) 2.6 e versão posterior.</span><span class="sxs-lookup"><span data-stu-id="03c23-105">As an alternative, you can execute queries and use SQLXML 4.0 with your COM-based applications, by leveraging the SQLXML extensions to ActiveX Data Objects (ADO) that were first introduced in Microsoft Data Access Components (MDAC) 2.6 and later.</span></span>  
  
 <span data-ttu-id="03c23-106">Este tópico demonstra o uso do SQLXML e ADO como parte de um aplicativo VBScript (Visual Basic Script Edição), um script com a extensão de arquivo .vbs.</span><span class="sxs-lookup"><span data-stu-id="03c23-106">This topic demonstrates using SQLXML and ADO as part of a Visual Basic Scripting Edition (VBScript) application (a script with the .vbs file extension).</span></span> <span data-ttu-id="03c23-107">Ele fornece procedimentos iniciais de instalação que ajudam a recriar e testar exemplos de consulta na documentação do SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="03c23-107">It provides initial setup procedures to help you recreate and test query samples in the SQLXML 4.0 documentation.</span></span>  
  
## <a name="creating-the-sqlxml-40-test-script"></a><span data-ttu-id="03c23-108">Criando o script de teste SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="03c23-108">Creating the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="03c23-109">Neste procedimento, você cria um arquivo VBScript (.vbs), Sqlxml4test.vbs, que pode ser usado para executar consultas SQLXML, aproveitando as extensões SQLXML ADO no ADO 2.6 e posterior.</span><span class="sxs-lookup"><span data-stu-id="03c23-109">In this procedure, you create a VBScript (.vbs) file, Sqlxml4test.vbs, which can be used to execute SQLXML queries by leveraging the SQLXML ADO extensions in ADO 2.6 and later.</span></span>  
  
#### <a name="to-create-the-sqlxml-40-query-tester-using-ado-vbscript"></a><span data-ttu-id="03c23-110">Para criar o testador de consulta do SQLXML 4.0 usando ADO (VBScript).</span><span class="sxs-lookup"><span data-stu-id="03c23-110">To create the SQLXML 4.0 query tester using ADO (VBScript).</span></span>  
  
1.  <span data-ttu-id="03c23-111">Copie o código VBScript abaixo e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="03c23-111">Copy the VBScript code below, and paste it into a text file.</span></span> <span data-ttu-id="03c23-112">Salve o arquivo como Sqlxml4test.vbs.</span><span class="sxs-lookup"><span data-stu-id="03c23-112">Save the file as Sqlxml4test.vbs.</span></span>  
  
    ```vb
    WScript.Echo "Query process may take a few seconds to complete. Please be patient."  
  
    ' Note that for SQL Server Native Client to be used as the data provider,  
    ' it needs to be installed on the client computer first. Also, SQLXML extensions   
    ' for ADO are used and available in MDAC 2.6 or later.  
  
    'Set script variables.  
    inputFile = "@@FILE_NAME@@"  
    strServer = "@@SERVER_NAME@@"  
    strDatabase = "@@DATABASE_NAME@@"  
    dbGuid = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
    ' Establish ADO connection to SQL Server and   
    ' create an instance of the ADO Command object.  
    Set conn = CreateObject("ADODB.Connection")  
    Set cmd = CreateObject("ADODB.Command")  
    conn.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Server=" & strServer & _  
              ";Database=" & strDatabase & ";Integrated Security=SSPI"  
    Set cmd.ActiveConnection = conn  
  
    ' Create the input stream as an instance of the ADO Stream object.  
    Set inStream = CreateObject("ADODB.Stream")  
    inStream.Open  
    inStream.Charset = "utf-8"  
    inStream.LoadFromFile inputFile  
  
    ' Set ADO Command instance to use input stream.  
    Set cmd.CommandStream = inStream  
  
    ' Set the command dialect.  
    cmd.Dialect = dbGuid  
  
    ' Set a second ADO Stream instance for use as a results stream.   
    Set outStream = CreateObject("ADODB.Stream")  
    outStream.Open  
  
    ' Set dynamic properties used by the SQLXML ADO command instance.   
    cmd.Properties("XML Root").Value = "ROOT"  
    cmd.Properties("Output Encoding").Value = "UTF-8"  
  
    ' Connect the results stream to the command instance and execute the command.  
    cmd.Properties("Output Stream").Value = outStream  
    cmd.Execute , , 1024  
  
    ' Echo cropped/partial results to console.  
    WScript.Echo Left(outStream.ReadText, 1023)  
  
    inStream.Close  
    outStream.Close  
    ```  
  
2.  <span data-ttu-id="03c23-113">Atualize os valores de script a seguir para o exemplo que você está tentando testar e seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="03c23-113">Update the following script values for the sample you are trying to test and your test environment.</span></span>  
  
    -   <span data-ttu-id="03c23-114">Localize "`@@FILE_NAME@@`" e substitua-o pelo nome do seu arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="03c23-114">Find "`@@FILE_NAME@@`" and replace it with the name of your template file.</span></span>  
  
    -   <span data-ttu-id="03c23-115">Localize "`@@SERVER_NAME@@`" e substitua-o pelo nome da sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (por exemplo, "`(local)`" se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver sendo executado localmente).</span><span class="sxs-lookup"><span data-stu-id="03c23-115">Find "`@@SERVER_NAME@@`" and replace it with the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (for example, "`(local)`" if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running locally).</span></span>  
  
    -   <span data-ttu-id="03c23-116">Localize "`@@DATABASE_NAME@@`" e substitua-o pelo nome do banco de dados (por exemplo, "`AdventureWorks2012`" ou "`tempdb`").</span><span class="sxs-lookup"><span data-stu-id="03c23-116">Find "`@@DATABASE_NAME@@`" and replace it with the name of the database (for example, either "`AdventureWorks2012`" or "`tempdb`").</span></span>  
  
     <span data-ttu-id="03c23-117">Atualize qualquer outro valor se mencionado nas instruções específicas do exemplo que você está tentando recriar localmente em seu computador.</span><span class="sxs-lookup"><span data-stu-id="03c23-117">Update any other values if mentioned in the specific instructions for the example you are attempting to recreate locally on your computer.</span></span>  
  
3.  <span data-ttu-id="03c23-118">Salve o arquivo e feche-o.</span><span class="sxs-lookup"><span data-stu-id="03c23-118">Save the file and close it.</span></span>  
  
4.  <span data-ttu-id="03c23-119">Verifique se você criou outros arquivos, como modelos ou esquemas XML que são parte do exemplo que você está tentando recriar localmente em seu computador.</span><span class="sxs-lookup"><span data-stu-id="03c23-119">Verify that you have created any additional files, such as XML templates or schemas that are part of the sample you are attempting to recreate locally on your computer.</span></span> <span data-ttu-id="03c23-120">Esses arquivos deveriam estar localizados no mesmo diretório onde você salvou o arquivo de script de teste (Sqlxml4test.vbs).</span><span class="sxs-lookup"><span data-stu-id="03c23-120">These files should be located in the same directory where you have saved the test script file (Sqlxml4test.vbs).</span></span>  
  
5.  <span data-ttu-id="03c23-121">Siga as instruções da próxima seção sobre como usar o script de teste SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="03c23-121">Follow the instructions in the next section for how to use the SQLXML 4.0 test script.</span></span>  
  
## <a name="using-the-sqlxml-40-test-script"></a><span data-ttu-id="03c23-122">Usando o script de teste SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="03c23-122">Using the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="03c23-123">O procedimento a seguir descreve como usar os arquivos Sqlxml4test.vbs para testar as consultas de exemplo fornecidas nesta documentação.</span><span class="sxs-lookup"><span data-stu-id="03c23-123">The following procedure describes how to use the Sqlxml4test.vbs files to test the example queries provided in this documentation.</span></span>  
  
#### <a name="to-use-the-sqlxml-40-query-tester"></a><span data-ttu-id="03c23-124">Para usar o testador de consulta do SQLXML 4.0 </span><span class="sxs-lookup"><span data-stu-id="03c23-124">To use the SQLXML 4.0 query tester</span></span>  
  
1.  <span data-ttu-id="03c23-125">Verifique se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client está instalado, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="03c23-125">Verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed, as follows:</span></span>  
  
    1.  <span data-ttu-id="03c23-126">No menu **Iniciar** , aponte para **configurações**e clique em painel de **controle**.</span><span class="sxs-lookup"><span data-stu-id="03c23-126">From the **Start** menu, point to **Settings**, and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="03c23-127">No painel de controle, abra **Adicionar ou remover programas**</span><span class="sxs-lookup"><span data-stu-id="03c23-127">In Control Panel, open **Add or Remove Programs**</span></span>  
  
    3.  <span data-ttu-id="03c23-128">Na lista de programas atualmente instalados, verifique se **Microsoft SQL Server cliente nativo** aparece na lista.</span><span class="sxs-lookup"><span data-stu-id="03c23-128">In the list of currently installed programs, verify that **Microsoft SQL Server Native Client** appears in the list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="03c23-129">Se você precisar instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, consulte [instalando SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="03c23-129">If you need to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Installing SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
2.  <span data-ttu-id="03c23-130">Verifique se a versão do MDAC instalada no computador cliente é a 2.6 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="03c23-130">Verify that the version of MDAC installed for the client computer is 2.6 or later.</span></span> <span data-ttu-id="03c23-131">Se precisar verificar as informações de versão do MDAC, você poderá usar a ferramenta Verificador de componentes do MDAC, que é fornecida como download gratuito no site da Microsoft [https://www.microsoft.com/](https://www.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="03c23-131">If you need to verify MDAC version information, you can use the MDAC Component Checker tool, which is provided as free download from the Microsoft Web site [https://www.microsoft.com/](https://www.microsoft.com/).</span></span> <span data-ttu-id="03c23-132">Para obter mais informações, pesquise "verificador de componentes do MDAC" no site da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03c23-132">For more information, search on "MDAC Component Checker" on the Microsoft Web site.</span></span>  
  
3.  <span data-ttu-id="03c23-133">Execute o script.</span><span class="sxs-lookup"><span data-stu-id="03c23-133">Execute the script.</span></span>  
  
     <span data-ttu-id="03c23-134">Você pode executar o arquivo VBScript na linha de comando usando Cscript.exe ou clicando duas vezes no arquivo Sqlxml4test.vbs para chamar o Windows Script Host (WScript.exe).</span><span class="sxs-lookup"><span data-stu-id="03c23-134">You can execute the VBScript file either at the command line using Cscript.exe or by double-clicking Sqlxml4test.vbs file to invoke the Windows Script Host (WScript.exe).</span></span>  
  
     <span data-ttu-id="03c23-135">Durante sua execução, o script deverá exibir uma mensagem de alerta informando que poderá levar alguns minutos para ser executado antes de retornar e exibir os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="03c23-135">When executed, the script should display a message to alert you that the script might take a few moments to execute before returning and displaying query results as script output.</span></span> <span data-ttu-id="03c23-136">Quando o resultado for exibido, compare seu conteúdo com o dos resultados esperados para o exemplo.</span><span class="sxs-lookup"><span data-stu-id="03c23-136">When the output appears, compare its contents to the expected results for the sample.</span></span>  
  
  
