---
title: Obter uma lista para o loop ForEach com a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], Foreach loops
- Script task [Integration Services], examples
- SSIS Script task, Foreach loops
ms.assetid: 694f0462-d0c5-4191-b64e-821b1bdef055
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 039860da121efaa52115bb515b158ea10373e459
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679432"
---
# <a name="gathering-a-list-for-the-foreach-loop-with-the-script-task"></a><span data-ttu-id="87d88-102">Obtendo uma lista para o loop ForEach com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="87d88-102">Gathering a List for the ForEach Loop with the Script Task</span></span>
  <span data-ttu-id="87d88-103">O Enumerador Foreach De Variável enumera os itens em uma lista que é passada para ele em uma variável e executa as mesmas tarefas em cada item.</span><span class="sxs-lookup"><span data-stu-id="87d88-103">The Foreach from Variable Enumerator enumerates over the items in a list that is passed to it in a variable and performs the same tasks on each item.</span></span> <span data-ttu-id="87d88-104">Você pode usar o código personalizado em uma tarefa Script para preencher uma lista com esse propósito.</span><span class="sxs-lookup"><span data-stu-id="87d88-104">You can use custom code in a Script task to populate a list for this purpose.</span></span> <span data-ttu-id="87d88-105">Para obter mais informações sobre o enumerador, consulte [Contêiner do Loop Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="87d88-105">For more information about the enumerator, see [Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87d88-106">Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="87d88-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="87d88-107">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="87d88-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="87d88-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="87d88-108">Description</span></span>  
 <span data-ttu-id="87d88-109">O exemplo a seguir usa métodos do namespace `System.IO` para reunir uma lista de pastas de trabalho do Excel no computador, que são anteriores ou posteriores a um número de dias especificado pelo usuário em uma variável.</span><span class="sxs-lookup"><span data-stu-id="87d88-109">The following example uses methods from the `System.IO` namespace to gather a list of Excel workbooks on the computer that are either newer or older than a number of days specified by the user in a variable.</span></span> <span data-ttu-id="87d88-110">Ele busca diretórios na Unidade C recursivamente para arquivos com a extensão .xls e verifica a data da última modificação em cada arquivo para determinar se o arquivo pertence a essa lista.</span><span class="sxs-lookup"><span data-stu-id="87d88-110">It searches directories on Drive C recursively for files that have the .xls extension and examines the date on which each file was last modified to determine whether the file belongs in the list.</span></span> <span data-ttu-id="87d88-111">Ele adiciona arquivos de qualificação a um `ArrayList` e salva o `ArrayList` em uma variável para uso posterior em um contêiner do Loop de Foreach.</span><span class="sxs-lookup"><span data-stu-id="87d88-111">It adds qualifying files to an `ArrayList` and saves the `ArrayList` to a variable for later use in a Foreach Loop container.</span></span> <span data-ttu-id="87d88-112">O contêiner do Loop de Foreach é configurado para usar o Foreach de enumerador de Variável.</span><span class="sxs-lookup"><span data-stu-id="87d88-112">The Foreach Loop container is configured to use the Foreach from Variable enumerator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87d88-113">A variável que você usa com o Foreach de Enumerador de Variável deve ser do tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="87d88-113">The variable that you use with the Foreach from Variable Enumerator must be of type `Object`.</span></span> <span data-ttu-id="87d88-114">O objeto que você coloca na variável deve implementar uma das seguintes interfaces: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource`ou `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span><span class="sxs-lookup"><span data-stu-id="87d88-114">The object that you place in the variable must implement one of the following interfaces: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource`, or `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span></span> <span data-ttu-id="87d88-115">Um `Array` ou `ArrayList` costuma ser usado.</span><span class="sxs-lookup"><span data-stu-id="87d88-115">An `Array` or `ArrayList` is commonly used.</span></span> <span data-ttu-id="87d88-116">O `ArrayList` requer uma referência e uma instrução `Imports` para o namespace `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="87d88-116">The `ArrayList` requires a reference and an `Imports` statement for the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="87d88-117">Você pode testar essa tarefa usando diferentes valores positivos e negativos para a variável do pacote `FileAge`.</span><span class="sxs-lookup"><span data-stu-id="87d88-117">You can experiment with this task by using different positive and negative values for the `FileAge` package variable.</span></span> <span data-ttu-id="87d88-118">Por exemplo, você pode digitar 5 para procurar arquivos criados nos últimos cinco dias, ou digitar -3 para procurar arquivos criados há mais de três dias.</span><span class="sxs-lookup"><span data-stu-id="87d88-118">For example, you can enter 5 to search for files created in the last five days, or enter -3 to search for files that were created more than three days ago.</span></span> <span data-ttu-id="87d88-119">Essa tarefa pode levar um ou dois minutos em uma unidade com várias pastas a serem pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="87d88-119">This task may take a minute or two on a drive with many folders to search.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="87d88-120">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="87d88-120">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="87d88-121">Crie uma variável do pacote nomeada `FileAge` do tipo inteiro e digite um valor inteiro positivo ou negativo.</span><span class="sxs-lookup"><span data-stu-id="87d88-121">Create a package variable named `FileAge` of type integer and enter a positive or negative integer value.</span></span> <span data-ttu-id="87d88-122">Quando o valor é positivo, o código busca arquivos posteriores ao número especificado de dias; quando ele é negativo, o código busca arquivos anteriores ao número especificado de dias.</span><span class="sxs-lookup"><span data-stu-id="87d88-122">When the value is positive, the code searches for files newer than the specified number of days; when negative, for files older than the specified number of days.</span></span>  
  
2.  <span data-ttu-id="87d88-123">Crie uma variável de pacote nomeada `FileList` do tipo `Object` para receber a lista de arquivos reunidos pela tarefa Script para uso posterior pelo Enumerador Foreach De Variável.</span><span class="sxs-lookup"><span data-stu-id="87d88-123">Create a package variable named `FileList` of type `Object` to receive the list of files gathered by the Script task for later use by the Foreach from Variable Enumerator.</span></span>  
  
3.  <span data-ttu-id="87d88-124">Adicione a variável `FileAge` à propriedade `ReadOnlyVariables` da tarefa Script e adicione a variável `FileList` à propriedade `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="87d88-124">Add the `FileAge` variable to the Script task's `ReadOnlyVariables` property, and add the `FileList` variable to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="87d88-125">No seu código, importe os namespaces `System.Collections` e `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="87d88-125">In your code, import the `System.Collections` and the `System.IO` namespaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="87d88-126">Código</span><span class="sxs-lookup"><span data-stu-id="87d88-126">Code</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Math  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Collections  
Imports System.IO  
  
Public Class ScriptMain  
  
  Private Const FILE_AGE As Integer = -50  
  
  Private Const FILE_ROOT As String = "C:\"  
  Private Const FILE_FILTER As String = "*.xls"  
  
  Private isCheckForNewer As Boolean = True  
  Dim fileAgeLimit As Integer  
  Private listForEnumerator As ArrayList  
  
  Public Sub Main()  
  
    fileAgeLimit = DirectCast(Dts.Variables("FileAge").Value, Integer)  
  
    ' If value provided is positive, we want files NEWER THAN n days.  
    '  If negative, we want files OLDER THAN n days.  
    If fileAgeLimit < 0 Then  
      isCheckForNewer = False  
    End If  
    ' Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit)  
  
    listForEnumerator = New ArrayList  
  
    GetFilesInFolder(FILE_ROOT)  
  
    ' Return the list of files to the variable  
    '  for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: " & listForEnumerator.Count.ToString, "Results", Windows.Forms.MessageBoxButtons.OK, Windows.Forms.MessageBoxIcon.Information)  
    Dts.Variables("FileList").Value = listForEnumerator  
  
    Dts.TaskResult = ScriptResults.Success  
  
  End Sub  
  
  Private Sub GetFilesInFolder(ByVal folderPath As String)  
  
    Dim localFiles() As String  
    Dim localFile As String  
    Dim fileChangeDate As Date  
    Dim fileAge As TimeSpan  
    Dim fileAgeInDays As Integer  
    Dim childFolder As String  
  
    Try  
      localFiles = Directory.GetFiles(folderPath, FILE_FILTER)  
      For Each localFile In localFiles  
        fileChangeDate = File.GetLastWriteTime(localFile)  
        fileAge = DateTime.Now.Subtract(fileChangeDate)  
        fileAgeInDays = fileAge.Days  
        CheckAgeOfFile(localFile, fileAgeInDays)  
      Next  
  
      If Directory.GetDirectories(folderPath).Length > 0 Then  
        For Each childFolder In Directory.GetDirectories(folderPath)  
          GetFilesInFolder(childFolder)  
        Next  
      End If  
  
    Catch  
      ' Ignore exceptions on special folders such as System Volume Information.  
    End Try  
  
  End Sub  
  
  Private Sub CheckAgeOfFile(ByVal localFile As String, ByVal fileAgeInDays As Integer)  
  
    If isCheckForNewer Then  
      If fileAgeInDays <= fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    Else  
      If fileAgeInDays > fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    End If  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Math;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Collections;  
using System.IO;  
  
public partial class ScriptMain : Microsoft.SqlServer.Dts.Tasks.ScriptTask.VSTARTScriptObjectModelBase  
    {  
  
        private const int FILE_AGE = -50;  
  
        private const string FILE_ROOT = "C:\\";  
        private const string FILE_FILTER = "*.xls";  
  
        private bool isCheckForNewer = true;  
        int fileAgeLimit;  
        private ArrayList listForEnumerator;  
  
        public void Main()  
  {  
  
    fileAgeLimit = (int)(Dts.Variables["FileAge"].Value);  
  
    // If value provided is positive, we want files NEWER THAN n days.  
    // If negative, we want files OLDER THAN n days.  
    if (fileAgeLimit<0)  
    {  
      isCheckForNewer = false;  
    }  
    // Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit);  
  
    ArrayList listForEnumerator = new ArrayList();  
  
    GetFilesInFolder(FILE_ROOT);  
  
    // Return the list of files to the variable  
    // for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: "+ listForEnumerator.Count, "Results",   
MessageBoxButtons.OK, MessageBoxIcon.Information);  
    Dts.Variables["FileList"].Value = listForEnumerator;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  
  }  
  
        private void GetFilesInFolder(string folderPath)  
        {  
  
            string[] localFiles;  
            DateTime fileChangeDate;  
            TimeSpan fileAge;  
            int fileAgeInDays;  
  
            try  
            {  
                localFiles = Directory.GetFiles(folderPath, FILE_FILTER);  
                foreach (string localFile in localFiles)  
                {  
                    fileChangeDate = File.GetLastWriteTime(localFile);  
                    fileAge = DateTime.Now.Subtract(fileChangeDate);  
                    fileAgeInDays = fileAge.Days;  
                    CheckAgeOfFile(localFile, fileAgeInDays);  
                }  
  
                if (Directory.GetDirectories(folderPath).Length > 0)  
                {  
                    foreach (string childFolder in Directory.GetDirectories(folderPath))  
                    {  
                        GetFilesInFolder(childFolder);  
                    }  
                }  
  
            }  
            catch  
            {  
                // Ignore exceptions on special folders, such as System Volume Information.  
            }  
  
        }  
  
        private void CheckAgeOfFile(string localFile, int fileAgeInDays)  
        {  
  
            if (isCheckForNewer)  
            {  
                if (fileAgeInDays <= fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
            else  
            {  
                if (fileAgeInDays > fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
  
        }  
  
    }  
```  
  
<span data-ttu-id="87d88-127">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="87d88-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="87d88-128">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="87d88-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="87d88-129">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="87d88-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="87d88-130">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="87d88-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d88-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="87d88-131">See Also</span></span>  
 <span data-ttu-id="87d88-132">[Contêiner Loop Foreach](../control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="87d88-132">[Foreach Loop Container](../control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="87d88-133">Configurar um contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="87d88-133">Configure a Foreach Loop Container</span></span>](../configure-a-foreach-loop-container.md)  
  
  
