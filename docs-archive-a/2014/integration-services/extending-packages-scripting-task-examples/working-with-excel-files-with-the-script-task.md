---
title: Trabalhando com arquivos do Excel com a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Excel files
- Script task [Integration Services], examples
- Excel [Integration Services]
ms.assetid: b8fa110a-2c9c-4f5a-8fe1-305555640e44
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68a764452de548cd46e74d2a7f2f588a050a21c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574210"
---
# <a name="working-with-excel-files-with-the-script-task"></a><span data-ttu-id="8bd39-102">Trabalhando com arquivos do Excel com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="8bd39-102">Working with Excel Files with the Script Task</span></span>
  <span data-ttu-id="8bd39-103">O [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fornece o gerenciador de conexões do Excel, a origem do Excel e o destino do Excel para trabalhar com dados armazenados em planilhas no formato de arquivo do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="8bd39-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides the Excel connection manager, Excel source, and Excel destination for working with data stored in spreadsheets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel file format.</span></span> <span data-ttu-id="8bd39-104">As técnicas descritas neste tópico utilizam a tarefa Script para obter informações sobre bancos de dados (arquivos de pasta de trabalho) e tabelas (planilhas e intervalos nomeados) do Excel disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8bd39-104">The techniques described in this topic use the Script task to obtain information about available Excel databases (workbook files) and tables (worksheets and named ranges).</span></span> <span data-ttu-id="8bd39-105">Esses exemplos podem ser facilmente modificados para funcionar com quaisquer das outras fontes de dados com base em arquivo suportadas pelo Provedor OLE DB [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet.</span><span class="sxs-lookup"><span data-stu-id="8bd39-105">These samples can easily be modified to work with any of the other file-based data sources supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB Provider.</span></span>  
  
 [<span data-ttu-id="8bd39-106">Configurando um pacote para testar os exemplos</span><span class="sxs-lookup"><span data-stu-id="8bd39-106">Configuring a Package to Test the Samples</span></span>](#configuring)  
  
 [<span data-ttu-id="8bd39-107">Exemplo 1: verificar se existe um arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="8bd39-107">Example1: Check Whether an Excel File Exists</span></span>](#example1)  
  
 [<span data-ttu-id="8bd39-108">Exemplo 2: verificar se existe uma tabela do Excel</span><span class="sxs-lookup"><span data-stu-id="8bd39-108">Example 2: Check Whether an Excel Table Exists</span></span>](#example2)  
  
 [<span data-ttu-id="8bd39-109">Exemplo 3: obter uma lista de arquivos do Excel em uma pasta</span><span class="sxs-lookup"><span data-stu-id="8bd39-109">Example 3: Get a List of Excel Files in a Folder</span></span>](#example3)  
  
 [<span data-ttu-id="8bd39-110">Exemplo 4: obter uma lista de tabelas em um arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="8bd39-110">Example 4: Get a List of Tables in an Excel File</span></span>](#example4)  
  
 [<span data-ttu-id="8bd39-111">Exibindo os resultados das amostras</span><span class="sxs-lookup"><span data-stu-id="8bd39-111">Displaying the Results of the Samples</span></span>](#testing)  
  
> [!NOTE]  
>  <span data-ttu-id="8bd39-112">Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="8bd39-112">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="8bd39-113">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="8bd39-113">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="configuring-a-package-to-test-the-samples"></a><a name="configuring"></a> <span data-ttu-id="8bd39-114">Configurando um pacote para testar as amostras</span><span class="sxs-lookup"><span data-stu-id="8bd39-114">Configuring a Package to Test the Samples</span></span>  
 <span data-ttu-id="8bd39-115">Você pode configurar um único pacote para testar todos os exemplos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="8bd39-115">You can configure a single package to test all the samples in this topic.</span></span> <span data-ttu-id="8bd39-116">Os exemplos usam muitas das mesmas variáveis de pacote e as mesmas classes [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bd39-116">The samples use many of the same package variables and the same [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes.</span></span>  
  
#### <a name="to-configure-a-package-for-use-with-the-examples-in-this-topic"></a><span data-ttu-id="8bd39-117">Para configurar um pacote para uso com os exemplos neste tópico</span><span class="sxs-lookup"><span data-stu-id="8bd39-117">To configure a package for use with the examples in this topic</span></span>  
  
1.  <span data-ttu-id="8bd39-118">Crie um projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] novo em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e abra o pacote padrão para editar.</span><span class="sxs-lookup"><span data-stu-id="8bd39-118">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open the default package for editing.</span></span>  
  
2.  <span data-ttu-id="8bd39-119">**Variáveis**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-119">**Variables**.</span></span> <span data-ttu-id="8bd39-120">Abra a janela **Variáveis** e defina as seguintes variáveis:</span><span class="sxs-lookup"><span data-stu-id="8bd39-120">Open the **Variables** window and define the following variables:</span></span>  
  
    -   <span data-ttu-id="8bd39-121">`ExcelFile`, de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-121">`ExcelFile`, of type `String`.</span></span> <span data-ttu-id="8bd39-122">Digite o caminho completo e o nome do arquivo em uma pasta de trabalho do Excel existente.</span><span class="sxs-lookup"><span data-stu-id="8bd39-122">Enter the complete path and filename to an existing Excel workbook.</span></span>  
  
    -   <span data-ttu-id="8bd39-123">`ExcelTable`, de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-123">`ExcelTable`, of type `String`.</span></span> <span data-ttu-id="8bd39-124">Digite o nome de uma planilha existente ou intervalo nomeado na pasta de trabalho nomeada no valor da variável `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-124">Enter the name of an existing worksheet or named range in the workbook named in the value of the `ExcelFile` variable.</span></span> <span data-ttu-id="8bd39-125">Esse valor diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8bd39-125">This value is case-sensitive.</span></span>  
  
    -   <span data-ttu-id="8bd39-126">`ExcelFileExists`, de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-126">`ExcelFileExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="8bd39-127">`ExcelTableExists`, de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-127">`ExcelTableExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="8bd39-128">`ExcelFolder`, de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-128">`ExcelFolder`, of type `String`.</span></span> <span data-ttu-id="8bd39-129">Digite o caminho completo de uma pasta que contenha pelo menos uma pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="8bd39-129">Enter the complete path of a folder that contains at least one Excel workbook.</span></span>  
  
    -   <span data-ttu-id="8bd39-130">`ExcelFiles`, de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-130">`ExcelFiles`, of type `Object`.</span></span>  
  
    -   <span data-ttu-id="8bd39-131">`ExcelTables`, de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-131">`ExcelTables`, of type `Object`.</span></span>  
  
3.  <span data-ttu-id="8bd39-132">**Instruções Imports**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-132">**Imports statements**.</span></span> <span data-ttu-id="8bd39-133">A maioria dos exemplos de código requer que você importe um ou ambos namespaces [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] seguintes no topo de seu arquivo de script:</span><span class="sxs-lookup"><span data-stu-id="8bd39-133">Most of the code samples require you to import one or both of the following [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces at the top of your script file:</span></span>  
  
    -   <span data-ttu-id="8bd39-134">`System.IO`, para operações do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8bd39-134">`System.IO`, for file system operations.</span></span>  
  
    -   <span data-ttu-id="8bd39-135">`System.Data.OleDb`, para abrir arquivos do Excel como fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="8bd39-135">`System.Data.OleDb`, to open Excel files as data sources.</span></span>  
  
4.  <span data-ttu-id="8bd39-136">**Referências**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-136">**References**.</span></span> <span data-ttu-id="8bd39-137">Os exemplos de código que leem informações de esquema de arquivos do Excel requerem uma referência no projeto de script para o namespace `System.Xml`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-137">The code samples that read schema information from Excel files require an additional reference in the script project to the `System.Xml` namespace.</span></span>  
  
5.  <span data-ttu-id="8bd39-138">Defina a linguagem de scripts padrão para o componente Script usando a opção **Linguagem de scripts** na página **Geral** da caixa de diálogo **Opções**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-138">Set the default scripting language for the Script component by using the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="8bd39-139">Para obter mais informações, consulte [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="8bd39-139">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>  
  
##  <a name="example-1-description-check-whether-an-excel-file-exists"></a><a name="example1"></a> <span data-ttu-id="8bd39-140">Descrição do exemplo 1: verificar se existe um arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="8bd39-140">Example 1 Description: Check Whether an Excel File Exists</span></span>  
 <span data-ttu-id="8bd39-141">Esse exemplo determina se o arquivo da pasta de trabalho do Excel especificado na variável `ExcelFile` existe, e define o valor booliano da variável `ExcelFileExists` para o resultado.</span><span class="sxs-lookup"><span data-stu-id="8bd39-141">This example determines whether the Excel workbook file specified in the `ExcelFile` variable exists, and then sets the Boolean value of the `ExcelFileExists` variable to the result.</span></span> <span data-ttu-id="8bd39-142">Você pode usar esse valor booliano para ramificar no fluxo de trabalho do pacote.</span><span class="sxs-lookup"><span data-stu-id="8bd39-142">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="8bd39-143">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="8bd39-143">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="8bd39-144">Adicione uma nova tarefa Script ao pacote e altere seu nome para `ExcelFileExists` .</span><span class="sxs-lookup"><span data-stu-id="8bd39-144">Add a new Script task to the package and change its name to `ExcelFileExists`.</span></span>  
  
2.  <span data-ttu-id="8bd39-145">No **Editor da Tarefa Script**, na guia **Script**, clique em **ReadOnlyVariables** e insira o valor da propriedade usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd39-145">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="8bd39-146">Digite `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-146">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="8bd39-147">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-147">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-148">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione a `ExcelFile` variável.</span><span class="sxs-lookup"><span data-stu-id="8bd39-148">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFile` variable.</span></span>  
  
3.  <span data-ttu-id="8bd39-149">Clique em **ReadWriteVariables** e insira o valor da propriedade usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd39-149">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="8bd39-150">Digite `ExcelFileExists`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-150">Type `ExcelFileExists`.</span></span>  
  
         <span data-ttu-id="8bd39-151">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-151">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-152">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione a `ExcelFileExists` variável.</span><span class="sxs-lookup"><span data-stu-id="8bd39-152">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFileExists` variable.</span></span>  
  
4.  <span data-ttu-id="8bd39-153">Clique em **Editar Script** para abrir o editor de scripts.</span><span class="sxs-lookup"><span data-stu-id="8bd39-153">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="8bd39-154">Adicione uma instrução `Imports` para o namespace `System.IO` no topo do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="8bd39-154">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="8bd39-155">Adicione o código seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bd39-155">Add the following code.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="8bd39-156">Código do exemplo 1</span><span class="sxs-lookup"><span data-stu-id="8bd39-156">Example 1 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    If File.Exists(fileToTest) Then  
      Dts.Variables("ExcelFileExists").Value = True  
    Else  
      Dts.Variables("ExcelFileExists").Value = False  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    string fileToTest;  
  
    fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
    if (File.Exists(fileToTest))  
    {  
      Dts.Variables["ExcelFileExists"].Value = true;  
    }  
    else  
    {  
      Dts.Variables["ExcelFileExists"].Value = false;  
    }  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
##  <a name="example-2-description-check-whether-an-excel-table-exists"></a><a name="example2"></a> <span data-ttu-id="8bd39-157">Descrição do exemplo 2: verificar se existe uma tabela do Excel</span><span class="sxs-lookup"><span data-stu-id="8bd39-157">Example 2 Description: Check Whether an Excel Table Exists</span></span>  
 <span data-ttu-id="8bd39-158">Esse exemplo determina se a planilha ou intervalo nomeado do Excel especificado na variável `ExcelTable` existe no arquivo da pasta de trabalho do Excel especificado na variável `ExcelFile`, e define o valor booliano da variável `ExcelTableExists` para o resultado.</span><span class="sxs-lookup"><span data-stu-id="8bd39-158">This example determines whether the Excel worksheet or named range specified in the `ExcelTable` variable exists in the Excel workbook file specified in the `ExcelFile` variable, and then sets the Boolean value of the `ExcelTableExists` variable to the result.</span></span> <span data-ttu-id="8bd39-159">Você pode usar esse valor booliano para ramificar no fluxo de trabalho do pacote.</span><span class="sxs-lookup"><span data-stu-id="8bd39-159">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="8bd39-160">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="8bd39-160">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="8bd39-161">Adicione uma nova tarefa Script ao pacote e altere seu nome para `ExcelTableExists` .</span><span class="sxs-lookup"><span data-stu-id="8bd39-161">Add a new Script task to the package and change its name to `ExcelTableExists`.</span></span>  
  
2.  <span data-ttu-id="8bd39-162">No **Editor da Tarefa Script**, na guia **Script**, clique em **ReadOnlyVariables** e insira o valor da propriedade usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd39-162">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="8bd39-163">Tipo `ExcelTable` e `ExcelFile` separado por vírgulas`.`</span><span class="sxs-lookup"><span data-stu-id="8bd39-163">Type `ExcelTable` and `ExcelFile` separated by commas`.`</span></span>  
  
         <span data-ttu-id="8bd39-164">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-164">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-165">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione as `ExcelTable` `ExcelFile` variáveis e.</span><span class="sxs-lookup"><span data-stu-id="8bd39-165">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTable` and `ExcelFile` variables.</span></span>  
  
3.  <span data-ttu-id="8bd39-166">Clique em **ReadWriteVariables** e insira o valor da propriedade usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd39-166">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="8bd39-167">Digite `ExcelTableExists`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-167">Type `ExcelTableExists`.</span></span>  
  
         <span data-ttu-id="8bd39-168">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-168">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-169">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione a `ExcelTableExists` variável.</span><span class="sxs-lookup"><span data-stu-id="8bd39-169">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTableExists` variable.</span></span>  
  
4.  <span data-ttu-id="8bd39-170">Clique em **Editar Script** para abrir o editor de scripts.</span><span class="sxs-lookup"><span data-stu-id="8bd39-170">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="8bd39-171">Adicione uma referência ao assembly `System.Xml` no projeto de script.</span><span class="sxs-lookup"><span data-stu-id="8bd39-171">Add a reference to the `System.Xml` assembly in the script project.</span></span>  
  
6.  <span data-ttu-id="8bd39-172">Adicione instruções `Imports` para os namespaces `System.IO` e `System.Data.OleDb` no topo do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="8bd39-172">Add `Imports` statements for the `System.IO` and `System.Data.OleDb` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="8bd39-173">Adicione o código seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bd39-173">Add the following code.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="8bd39-174">Código do exemplo 2</span><span class="sxs-lookup"><span data-stu-id="8bd39-174">Example 2 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
    Dim tableToTest As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim excelTables As DataTable  
    Dim excelTable As DataRow  
    Dim currentTable As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    tableToTest = Dts.Variables("ExcelTable").Value.ToString  
  
    Dts.Variables("ExcelTableExists").Value = False  
    If File.Exists(fileToTest) Then  
      connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & fileToTest & _  
        ";Extended Properties=Excel 8.0"  
      excelConnection = New OleDbConnection(connectionString)  
      excelConnection.Open()  
      excelTables = excelConnection.GetSchema("Tables")  
      For Each excelTable In excelTables.Rows  
        currentTable = excelTable.Item("TABLE_NAME").ToString  
        If currentTable = tableToTest Then  
          Dts.Variables("ExcelTableExists").Value = True  
        End If  
      Next  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
    public void Main()  
        {  
            string fileToTest;  
            string tableToTest;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable excelTables;  
            string currentTable;  
  
            fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
            tableToTest = Dts.Variables["ExcelTable"].Value.ToString();  
  
            Dts.Variables["ExcelTableExists"].Value = false;  
            if (File.Exists(fileToTest))  
            {  
                connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + fileToTest + ";Extended Properties=Excel 8.0";  
                excelConnection = new OleDbConnection(connectionString);  
                excelConnection.Open();  
                excelTables = excelConnection.GetSchema("Tables");  
                foreach (DataRow excelTable in excelTables.Rows)  
                {  
                    currentTable = excelTable["TABLE_NAME"].ToString();  
                    if (currentTable == tableToTest)  
                    {  
                        Dts.Variables["ExcelTableExists"].Value = true;  
                    }  
                }  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
}  
```  
  
##  <a name="example-3-description-get-a-list-of-excel-files-in-a-folder"></a><a name="example3"></a> <span data-ttu-id="8bd39-175">Descrição do exemplo 3: obter uma lista de arquivos do Excel em uma pasta</span><span class="sxs-lookup"><span data-stu-id="8bd39-175">Example 3 Description: Get a List of Excel Files in a Folder</span></span>  
 <span data-ttu-id="8bd39-176">Esse exemplo preenche uma matriz com a lista de arquivos do Excel encontrada na pasta especificada no valor da variável `ExcelFolder`, e copia a matriz para a variável `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-176">This example fills an array with the list of Excel files found in the folder specified in the value of the `ExcelFolder` variable, and then copies the array into the `ExcelFiles` variable.</span></span> <span data-ttu-id="8bd39-177">Você pode usar o Enumerador Foreach de Variável para repetir nos arquivos da matriz.</span><span class="sxs-lookup"><span data-stu-id="8bd39-177">You can use the Foreach from Variable enumerator to iterate over the files in the array.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="8bd39-178">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="8bd39-178">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="8bd39-179">Adicione uma nova tarefa Script ao pacote e altere seu nome para **GetExcelFiles**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-179">Add a new Script task to the package and change its name to **GetExcelFiles**.</span></span>  
  
2.  <span data-ttu-id="8bd39-180">Abra o **Editor da Tarefa Script**, na guia **Script**, clique em **ReadOnlyVariables** e insira o valor da propriedade usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd39-180">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="8bd39-181">Digite `ExcelFolder`</span><span class="sxs-lookup"><span data-stu-id="8bd39-181">Type `ExcelFolder`</span></span>  
  
         <span data-ttu-id="8bd39-182">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-182">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-183">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione a variável ExcelFolder.</span><span class="sxs-lookup"><span data-stu-id="8bd39-183">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFolder variable.</span></span>  
  
3.  <span data-ttu-id="8bd39-184">Clique em **ReadWriteVariables** e insira o valor da propriedade usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd39-184">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="8bd39-185">Digite `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-185">Type `ExcelFiles`.</span></span>  
  
         <span data-ttu-id="8bd39-186">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-186">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-187">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione a variável ExcelFiles.</span><span class="sxs-lookup"><span data-stu-id="8bd39-187">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFiles variable.</span></span>  
  
4.  <span data-ttu-id="8bd39-188">Clique em **Editar Script** para abrir o editor de scripts.</span><span class="sxs-lookup"><span data-stu-id="8bd39-188">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="8bd39-189">Adicione uma instrução `Imports` para o namespace `System.IO` no topo do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="8bd39-189">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="8bd39-190">Adicione o código seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bd39-190">Add the following code.</span></span>  
  
### <a name="example-3-code"></a><span data-ttu-id="8bd39-191">Código do exemplo 3</span><span class="sxs-lookup"><span data-stu-id="8bd39-191">Example 3 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const FILE_PATTERN As String = "*.xls"  
  
    Dim excelFolder As String  
    Dim excelFiles As String()  
  
    excelFolder = Dts.Variables("ExcelFolder").Value.ToString  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN)  
  
    Dts.Variables("ExcelFiles").Value = excelFiles  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    const string FILE_PATTERN = "*.xls";  
  
    string excelFolder;  
    string[] excelFiles;  
  
    excelFolder = Dts.Variables["ExcelFolder"].Value.ToString();  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN);  
  
    Dts.Variables["ExcelFiles"].Value = excelFiles;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="8bd39-192">Solução alternada</span><span class="sxs-lookup"><span data-stu-id="8bd39-192">Alternate Solution</span></span>  
 <span data-ttu-id="8bd39-193">Em vez de usar uma tarefa Script para reunir uma lista de arquivos do Excel em uma matriz, você também pode usar o Enumerador de Arquivo Foreach para repetir em todos os arquivos do Excel em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="8bd39-193">Instead of using a Script task to gather a list of Excel files into an array, you can also use the ForEach File enumerator to iterate over all the Excel files in a folder.</span></span> <span data-ttu-id="8bd39-194">Para obter mais informações, consulte [Executar um loop por meio de arquivos e tabelas do Excel usando um contêiner do Loop Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8bd39-194">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="example-4-description-get-a-list-of-tables-in-an-excel-file"></a><a name="example4"></a> <span data-ttu-id="8bd39-195">Descrição do exemplo 4: obter uma lista de tabelas em um arquivo do Excel</span><span class="sxs-lookup"><span data-stu-id="8bd39-195">Example 4 Description: Get a List of Tables in an Excel File</span></span>  
 <span data-ttu-id="8bd39-196">Esse exemplo preenche uma matriz com a lista de planilhas e intervalos nomeados encontrados no arquivo da pasta de trabalho especificado pelo valor da variável `ExcelFile`, e copia a matriz para a variável `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-196">This example fills an array with the list of worksheets and named ranges found in the Excel workbook file specified by the value of the `ExcelFile` variable, and then copies the array into the `ExcelTables` variable.</span></span> <span data-ttu-id="8bd39-197">Você pode usar o Enumerador Foreach de Variável para repetir nas tabelas da matriz.</span><span class="sxs-lookup"><span data-stu-id="8bd39-197">You can use the Foreach from Variable Enumerator to iterate over the tables in the array.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8bd39-198">A lista de tabelas em uma pasta de trabalho do Excel inclui planilhas (que têm o sufixo $) e intervalos nomeados.</span><span class="sxs-lookup"><span data-stu-id="8bd39-198">The list of tables in an Excel workbook includes both worksheets (which have the $ suffix) and named ranges.</span></span> <span data-ttu-id="8bd39-199">Se você tiver que filtrar a lista para apenas planilhas ou apenas intervalos nomeados, talvez seja necessário acrescentar um código adicional para esse propósito.</span><span class="sxs-lookup"><span data-stu-id="8bd39-199">If you have to filter the list for only worksheets or only named ranges, you may have to add additional code for this purpose.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="8bd39-200">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="8bd39-200">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="8bd39-201">Adicione uma nova tarefa Script ao pacote e altere seu nome para **GetExcelTables**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-201">Add a new Script task to the package and change its name to **GetExcelTables**.</span></span>  
  
2.  <span data-ttu-id="8bd39-202">Abra o **Editor da Tarefa Script**, na guia **Script**, clique em **ReadOnlyVariables** e insira o valor da propriedade usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd39-202">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="8bd39-203">Digite `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-203">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="8bd39-204">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-204">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-205">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione a variável ExcelFile.</span><span class="sxs-lookup"><span data-stu-id="8bd39-205">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFile variable.</span></span>  
  
3.  <span data-ttu-id="8bd39-206">Clique em **ReadWriteVariables** e insira o valor da propriedade usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bd39-206">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="8bd39-207">Digite `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="8bd39-207">Type `ExcelTables`.</span></span>  
  
         <span data-ttu-id="8bd39-208">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-208">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-209">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione o ExcelTablesvariable.</span><span class="sxs-lookup"><span data-stu-id="8bd39-209">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelTablesvariable.</span></span>  
  
4.  <span data-ttu-id="8bd39-210">Clique em **Editar Script** para abrir o editor de scripts.</span><span class="sxs-lookup"><span data-stu-id="8bd39-210">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="8bd39-211">Acrescente uma referência ao namespace `System.Xml` no projeto de script.</span><span class="sxs-lookup"><span data-stu-id="8bd39-211">Add a reference to the `System.Xml` namespace in the script project.</span></span>  
  
6.  <span data-ttu-id="8bd39-212">Adicione uma instrução `Imports` para o namespace `System.Data.OleDb` no topo do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="8bd39-212">Add an `Imports` statement for the `System.Data.OleDb` namespace at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="8bd39-213">Adicione o código seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bd39-213">Add the following code.</span></span>  
  
### <a name="example-4-code"></a><span data-ttu-id="8bd39-214">Exemplo 4 Código</span><span class="sxs-lookup"><span data-stu-id="8bd39-214">Example 4 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim excelFile As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim tablesInFile As DataTable  
    Dim tableCount As Integer = 0  
    Dim tableInFile As DataRow  
    Dim currentTable As String  
    Dim tableIndex As Integer = 0  
  
    Dim excelTables As String()  
  
    excelFile = Dts.Variables("ExcelFile").Value.ToString  
    connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & excelFile & _  
        ";Extended Properties=Excel 8.0"  
    excelConnection = New OleDbConnection(connectionString)  
    excelConnection.Open()  
    tablesInFile = excelConnection.GetSchema("Tables")  
    tableCount = tablesInFile.Rows.Count  
    ReDim excelTables(tableCount - 1)  
    For Each tableInFile In tablesInFile.Rows  
      currentTable = tableInFile.Item("TABLE_NAME").ToString  
      excelTables(tableIndex) = currentTable  
      tableIndex += 1  
    Next  
  
    Dts.Variables("ExcelTables").Value = excelTables  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            string excelFile;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable tablesInFile;  
            int tableCount = 0;  
            string currentTable;  
            int tableIndex = 0;  
  
            string[] excelTables = new string[5];  
  
            excelFile = Dts.Variables["ExcelFile"].Value.ToString();  
            connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + excelFile + ";Extended Properties=Excel 8.0";  
            excelConnection = new OleDbConnection(connectionString);  
            excelConnection.Open();  
            tablesInFile = excelConnection.GetSchema("Tables");  
            tableCount = tablesInFile.Rows.Count;  
  
            foreach (DataRow tableInFile in tablesInFile.Rows)  
            {  
                currentTable = tableInFile["TABLE_NAME"].ToString();  
                excelTables[tableIndex] = currentTable;  
                tableIndex += 1;  
            }  
  
            Dts.Variables["ExcelTables"].Value = excelTables;  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="8bd39-215">Solução alternada</span><span class="sxs-lookup"><span data-stu-id="8bd39-215">Alternate Solution</span></span>  
 <span data-ttu-id="8bd39-216">Em vez de usar uma tarefa Script para reunir uma lista de tabelas do Excel em uma matriz, você também pode usar o Enumerador de Conjunto de Linhas de Esquema ADO.NET Foreach para repetir em todos as tabelas (planinhas e intervalos nomeados) em um arquivo de pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="8bd39-216">Instead of using a Script task to gather a list of Excel tables into an array, you can also use the ForEach ADO.NET Schema Rowset Enumerator to iterate over all the tables (that is, worksheets and named ranges) in an Excel workbook file.</span></span> <span data-ttu-id="8bd39-217">Para obter mais informações, consulte [Executar um loop por meio de arquivos e tabelas do Excel usando um contêiner do Loop Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8bd39-217">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="displaying-the-results-of-the-samples"></a><a name="testing"></a> <span data-ttu-id="8bd39-218">Exibindo os resultados das amostras</span><span class="sxs-lookup"><span data-stu-id="8bd39-218">Displaying the Results of the Samples</span></span>  
 <span data-ttu-id="8bd39-219">Se você configurou cada um dos exemplos deste tópico no mesmo pacote, você pode conectar todas as tarefas Script a uma tarefa Script adicional que exibe a saída de todos os exemplos.</span><span class="sxs-lookup"><span data-stu-id="8bd39-219">If you have configured each of the examples in this topic in the same package, you can connect all the Script tasks to an additional Script task that displays the output of all the examples.</span></span>  
  
#### <a name="to-configure-a-script-task-to-display-the-output-of-the-examples-in-this-topic"></a><span data-ttu-id="8bd39-220">Para configurar uma tarefa Script para exibir a saída dos exemplos neste tópico</span><span class="sxs-lookup"><span data-stu-id="8bd39-220">To configure a Script task to display the output of the examples in this topic</span></span>  
  
1.  <span data-ttu-id="8bd39-221">Adicione uma nova tarefa Script ao pacote e altere seu nome para **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-221">Add a new Script task to the package and change its name to **DisplayResults**.</span></span>  
  
2.  <span data-ttu-id="8bd39-222">Conecte cada uma das quatro tarefas Script de exemplo uma a outra, de forma que cada tarefa seja executada depois que a anterior for concluída com êxito e conecte a quarta tarefa de exemplo à tarefa **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-222">Connect each of the four example Script tasks to one another, so that each task runs after the preceding task completes successfully, and connect the fourth example task to the **DisplayResults** task.</span></span>  
  
3.  <span data-ttu-id="8bd39-223">Abra a tarefa **DisplayResults** no **Editor da Tarefa Script**.</span><span class="sxs-lookup"><span data-stu-id="8bd39-223">Open the **DisplayResults** task in the **Script Task Editor**.</span></span>  
  
4.  <span data-ttu-id="8bd39-224">Na guia **Script**, clique em **ReadOnlyVariables** e use um dos seguintes métodos para adicionar todas as sete variáveis listadas em [Configurando um pacote para testar as amostras](#configuring):</span><span class="sxs-lookup"><span data-stu-id="8bd39-224">On the **Script** tab, click **ReadOnlyVariables** and use one of the following methods to add all seven variables listed in [Configuring a Package to Test the Samples](#configuring):</span></span>  
  
    -   <span data-ttu-id="8bd39-225">Digite o nome de cada variável separado por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="8bd39-225">Type the name of each variable separated by commas.</span></span>  
  
         <span data-ttu-id="8bd39-226">- ou -</span><span class="sxs-lookup"><span data-stu-id="8bd39-226">-or-</span></span>  
  
    -   <span data-ttu-id="8bd39-227">Clique no botão de reticências (**...**) ao lado do campo de propriedade e, na caixa de diálogo **Selecionar variáveis** , selecione as variáveis.</span><span class="sxs-lookup"><span data-stu-id="8bd39-227">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, selecting the variables.</span></span>  
  
5.  <span data-ttu-id="8bd39-228">Clique em **Editar Script** para abrir o editor de scripts.</span><span class="sxs-lookup"><span data-stu-id="8bd39-228">Click **Edit Script** to open the script editor.</span></span>  
  
6.  <span data-ttu-id="8bd39-229">Adicione instruções `Imports` para os namespaces `Microsoft.VisualBasic` e `System.Windows.Forms` no topo do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="8bd39-229">Add `Imports` statements for the `Microsoft.VisualBasic` and `System.Windows.Forms` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="8bd39-230">Adicione o código seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bd39-230">Add the following code.</span></span>  
  
8.  <span data-ttu-id="8bd39-231">Execute o pacote e examine os resultados exibidos em uma caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="8bd39-231">Run the package and examine the results displayed in a message box.</span></span>  
  
### <a name="code-to-display-the-results"></a><span data-ttu-id="8bd39-232">Codifique para exibir o resultados</span><span class="sxs-lookup"><span data-stu-id="8bd39-232">Code to Display the Results</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const EOL As String = ControlChars.CrLf  
  
    Dim results As String  
    Dim filesInFolder As String()  
    Dim fileInFolder As String  
    Dim tablesInFile As String()  
    Dim tableInFile As String  
  
    results = _  
      "Final values of variables:" & EOL & _  
      "ExcelFile: " & Dts.Variables("ExcelFile").Value.ToString & EOL & _  
      "ExcelFileExists: " & Dts.Variables("ExcelFileExists").Value.ToString & EOL & _  
      "ExcelTable: " & Dts.Variables("ExcelTable").Value.ToString & EOL & _  
      "ExcelTableExists: " & Dts.Variables("ExcelTableExists").Value.ToString & EOL & _  
      "ExcelFolder: " & Dts.Variables("ExcelFolder").Value.ToString & EOL & _  
      EOL  
  
    results &= "Excel files in folder: " & EOL  
    filesInFolder = DirectCast(Dts.Variables("ExcelFiles").Value, String())  
    For Each fileInFolder In filesInFolder  
      results &= " " & fileInFolder & EOL  
    Next  
    results &= EOL  
  
    results &= "Excel tables in file: " & EOL  
    tablesInFile = DirectCast(Dts.Variables("ExcelTables").Value, String())  
    For Each tableInFile In tablesInFile  
      results &= " " & tableInFile & EOL  
    Next  
  
    MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information)  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            const string EOL = "\r";  
  
            string results;  
            string[] filesInFolder;  
            //string fileInFolder;  
            string[] tablesInFile;  
            //string tableInFile;  
  
            results = "Final values of variables:" + EOL + "ExcelFile: " + Dts.Variables["ExcelFile"].Value.ToString() + EOL + "ExcelFileExists: " + Dts.Variables["ExcelFileExists"].Value.ToString() + EOL + "ExcelTable: " + Dts.Variables["ExcelTable"].Value.ToString() + EOL + "ExcelTableExists: " + Dts.Variables["ExcelTableExists"].Value.ToString() + EOL + "ExcelFolder: " + Dts.Variables["ExcelFolder"].Value.ToString() + EOL + EOL;  
  
            results += "Excel files in folder: " + EOL;  
            filesInFolder = (string[])(Dts.Variables["ExcelFiles"].Value);  
            foreach (string fileInFolder in filesInFolder)  
            {  
                results += " " + fileInFolder + EOL;  
            }  
            results += EOL;  
  
            results += "Excel tables in file: " + EOL;  
            tablesInFile = (string[])(Dts.Variables["ExcelTables"].Value);  
            foreach (string tableInFile in tablesInFile)  
            {  
                results += " " + tableInFile + EOL;  
            }  
  
            MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
<span data-ttu-id="8bd39-233">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8bd39-233">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8bd39-234">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="8bd39-234">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8bd39-235">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="8bd39-235">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8bd39-236">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="8bd39-236">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd39-237">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8bd39-237">See Also</span></span>  
 <span data-ttu-id="8bd39-238">[Gerenciador de conexões do Excel](../connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="8bd39-238">[Excel Connection Manager](../connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="8bd39-239">Loop através de arquivos e tabelas do Excel por meio de um contêiner do Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="8bd39-239">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
  
