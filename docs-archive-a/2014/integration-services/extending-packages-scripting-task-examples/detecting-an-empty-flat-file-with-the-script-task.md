---
title: Detectar um arquivo simples vazio com a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- flat files
- Script task [Integration Services], empty flat files
- SSIS Script task, empty flat files
- Script task [Integration Services], examples
ms.assetid: 1b4defb8-886a-483d-8056-d1b91d37bc90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 379b11bd18752ad648fc5f24d11d9ed5bfb63e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574776"
---
# <a name="detecting-an-empty-flat-file-with-the-script-task"></a><span data-ttu-id="3b417-102">Detectando um arquivo simples vazio com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="3b417-102">Detecting an Empty Flat File with the Script Task</span></span>
  <span data-ttu-id="3b417-103">A origem Arquivo Simples não determina se um arquivo simples contém linhas de dados antes de tentar processá-las.</span><span class="sxs-lookup"><span data-stu-id="3b417-103">The Flat File source does not determine whether a flat file contains rows of data before attempting to process it.</span></span> <span data-ttu-id="3b417-104">Talvez você queira aumentar a eficácia de um pacote, especialmente de um pacote que itera em diversos arquivos simples, ignorando os arquivos que não contêm linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="3b417-104">You may want to improve the efficiency of a package, especially of a package that iterates over numerous flat files, by skipping files that do not contain any rows of data.</span></span> <span data-ttu-id="3b417-105">A tarefa Script pode procurar um arquivo simples vazio antes de o pacote começar a processar o fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="3b417-105">The Script task can look for an empty flat file before the package begins to process the data flow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b417-106">Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="3b417-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="3b417-107">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="3b417-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="3b417-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="3b417-108">Description</span></span>  
 <span data-ttu-id="3b417-109">O exemplo a seguir utiliza métodos do namespace `System.IO` para testar o arquivo simples especificado em um gerenciador de conexões de arquivos simples para determinar se o arquivo está vazio, ou se ele contém apenas linhas esperadas que não são de dados, como títulos de colunas ou uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="3b417-109">The following example uses methods from the `System.IO` namespace to test the flat file specified in a Flat File connection manager to determine whether the file is empty, or whether it contains only expected non-data rows such as column headers or an empty line.</span></span> <span data-ttu-id="3b417-110">O script verifica primeiro o tamanho do arquivo; se o tamanho é zero bytes, o arquivo está vazio.</span><span class="sxs-lookup"><span data-stu-id="3b417-110">The script checks the size of the file first; if the size is zero bytes, the file is empty.</span></span> <span data-ttu-id="3b417-111">Quando o tamanho do arquivo é maior que zero, o script lê linhas do arquivo até não encontrar mais linhas ou até o número de linhas exceder o número esperado de linhas que não são de dados.</span><span class="sxs-lookup"><span data-stu-id="3b417-111">If the file size is greater than zero, the script reads lines from the file until there are no more lines, or until the number of lines exceeds the expected number of non-data rows.</span></span> <span data-ttu-id="3b417-112">Quando o número de linhas no arquivo é menor que ou igual ao número esperado de linhas que não são de dados, o arquivo é considerado vazio.</span><span class="sxs-lookup"><span data-stu-id="3b417-112">If the number of lines in the file is less than or equal to the expected number of non-data rows, then the file is considered empty.</span></span> <span data-ttu-id="3b417-113">Os resultados são retornados como um valor booliano em uma variável de usuário, cujo valor pode ser usado para criar ramificação no fluxo de controle do pacote.</span><span class="sxs-lookup"><span data-stu-id="3b417-113">The result is returned as a Boolean value in a user variable, the value of which can be used for branching in the package's control flow.</span></span> <span data-ttu-id="3b417-114">O `FireInformation` método também exibe o resultado na janela de **saída** do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSTA (Tools for Applications).</span><span class="sxs-lookup"><span data-stu-id="3b417-114">The `FireInformation` method also displays the result in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="3b417-115">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="3b417-115">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="3b417-116">Crie e configure um Gerenciador de conexões de arquivo simples chamado `EmptyFlatFileTest` .</span><span class="sxs-lookup"><span data-stu-id="3b417-116">Create and configure a flat file connection manager named `EmptyFlatFileTest`.</span></span>  
  
2.  <span data-ttu-id="3b417-117">Crie uma variável de inteiro nomeada `FFNonDataRows` e defina seu valor como o número de linhas que não são de dados esperadas no arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="3b417-117">Create an integer variable named `FFNonDataRows` and set its value to the number of non-data rows expected in the flat file.</span></span>  
  
3.  <span data-ttu-id="3b417-118">Crie uma variável booliana nomeada `FFIsEmpty`.</span><span class="sxs-lookup"><span data-stu-id="3b417-118">Create a Boolean variable named `FFIsEmpty`.</span></span>  
  
4.  <span data-ttu-id="3b417-119">Adicione a variável `FFNonDataRows` à propriedade **ReadOnlyVariables** da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="3b417-119">Add the `FFNonDataRows` variable to the Script task's **ReadOnlyVariables** property.</span></span>  
  
5.  <span data-ttu-id="3b417-120">Adicione a variável `FFIsEmpty` à propriedade **ReadWriteVariables** da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="3b417-120">Add the `FFIsEmpty` variable to the Script task's **ReadWriteVariables** property.</span></span>  
  
6.  <span data-ttu-id="3b417-121">No seu código, importe o namespace `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="3b417-121">In your code, import the `System.IO` namespace.</span></span>  
  
 <span data-ttu-id="3b417-122">Se você estiver iterando em arquivos com um enumerador de arquivo Foreach, em vez de utilizar um único gerenciador de conexões de arquivos simples, modifique o código de exemplo a seguir para obter o nome e o caminho do arquivo a partir da variável em que o valor enumerado é armazenado, e não do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="3b417-122">If you are iterating over files with a Foreach File enumerator, instead of using a single Flat File connection manager, you will need to modify the sample code below to obtain the file name and path from the variable in which the enumerated value is stored instead of from the connection manager.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3b417-123">Código</span><span class="sxs-lookup"><span data-stu-id="3b417-123">Code</span></span>  
  
```vb  
Public Sub Main()  
  
  Dim nonDataRows As Integer = _  
      DirectCast(Dts.Variables("FFNonDataRows").Value, Integer)  
  Dim ffConnection As String = _  
      DirectCast(Dts.Connections("EmptyFlatFileTest").AcquireConnection(Nothing), _  
      String)  
  Dim flatFileInfo As New FileInfo(ffConnection)  
  ' If file size is 0 bytes, flat file does not contain data.  
  Dim fileSize As Long = flatFileInfo.Length  
  If fileSize > 0 Then  
    Dim lineCount As Integer = 0  
    Dim line As String  
    Dim fsFlatFile As New StreamReader(ffConnection)  
    Do Until fsFlatFile.EndOfStream  
      line = fsFlatFile.ReadLine  
      lineCount += 1  
      ' If line count > expected number of non-data rows,  
      '  flat file contains data (default value).  
      If lineCount > nonDataRows Then  
        Exit Do  
      End If  
      ' If line count <= expected number of non-data rows,  
      '  flat file does not contain data.  
      If lineCount <= nonDataRows Then  
        Dts.Variables("FFIsEmpty").Value = True  
      End If  
    Loop  
  Else  
    Dts.Variables("FFIsEmpty").Value = True  
  End If  
  
  Dim fireAgain As Boolean = False  
  Dts.Events.FireInformation(0, "Script Task", _  
      String.Format("{0}: {1}", ffConnection, _  
      Dts.Variables("FFIsEmpty").Value.ToString), _  
      String.Empty, 0, fireAgain)  
  
  Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
public void Main()  
        {  
  
            int nonDataRows = (int)(Dts.Variables["FFNonDataRows"].Value);  
            string ffConnection = (string)(Dts.Connections["EmptyFlatFileTest"].AcquireConnection(null) as String);  
            FileInfo flatFileInfo = new FileInfo(ffConnection);  
            // If file size is 0 bytes, flat file does not contain data.  
            long fileSize = flatFileInfo.Length;  
            if (fileSize > 0)  
            {  
  
                int lineCount = 0;  
                string line;  
                StreamReader fsFlatFile = new StreamReader(ffConnection);  
                while (!(fsFlatFile.EndOfStream))  
                {  
                    Console.WriteLine (fsFlatFile.ReadLine());  
                    lineCount += 1;  
                    // If line count > expected number of non-data rows,  
                    //  flat file contains data (default value).  
                    if (lineCount > nonDataRows)  
                    {  
                        break;  
                    }  
                    // If line count <= expected number of non-data rows,  
                    //  flat file does not contain data.  
                    if (lineCount <= nonDataRows)  
                    {  
                        Dts.Variables["FFIsEmpty"].Value = true;  
                    }  
                }  
            }  
            else  
            {  
                Dts.Variables["FFIsEmpty"].Value = true;  
            }  
  
            bool fireAgain = false;  
            Dts.Events.FireInformation(0, "Script Task", String.Format("{0}: {1}", ffConnection, Dts.Variables["FFIsEmpty"].Value), String.Empty, 0, ref fireAgain);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
```  
  
<span data-ttu-id="3b417-124">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3b417-124">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3b417-125">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="3b417-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3b417-126">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="3b417-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3b417-127">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="3b417-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b417-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b417-128">See Also</span></span>  
 [<span data-ttu-id="3b417-129">Exemplos de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="3b417-129">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)  
  
  
