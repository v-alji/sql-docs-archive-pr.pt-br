---
title: Localizar impressoras instaladas com a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- System.Drawing.Printing namespace
- printers [Integration Services]
- SSIS Script task, printers
- locating printers
- Printing namespace
- Script task [Integration Services], examples
- finding printers [SQL Server]
- Script task [Integration Services], printers
ms.assetid: 50a55014-e2c3-4ecd-84e1-3e877c55a260
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc4bc06879a55d4d07afca1011cc479dd7e7903a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683623"
---
# <a name="finding-installed-printers-with-the-script-task"></a><span data-ttu-id="31b6f-102">Localizando impressoras instaladas com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="31b6f-102">Finding Installed Printers with the Script Task</span></span>
  <span data-ttu-id="31b6f-103">Os dados que são transformados por pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] costumam ter um relatório impresso como seu destino final.</span><span class="sxs-lookup"><span data-stu-id="31b6f-103">The data that is transformed by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages often has a printed report as its final destination.</span></span> <span data-ttu-id="31b6f-104">O `System.Drawing.Printing` namespace no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fornece classes para trabalhar com impressoras.</span><span class="sxs-lookup"><span data-stu-id="31b6f-104">The `System.Drawing.Printing` namespace in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for working with printers.</span></span>

> [!NOTE]
>  <span data-ttu-id="31b6f-105">Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="31b6f-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="31b6f-106">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="31b6f-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="31b6f-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="31b6f-107">Description</span></span>
 <span data-ttu-id="31b6f-108">O exemplo a seguir localiza impressoras instaladas no servidor que oferece suporte a papel de tamanho válido (conforme usado nos Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="31b6f-108">The following example locates printers installed on the server that support legal size paper (as used in the United States).</span></span> <span data-ttu-id="31b6f-109">O código para verificar tamanhos de papel suportados é encapsulado em uma função particular.</span><span class="sxs-lookup"><span data-stu-id="31b6f-109">The code to check supported paper sizes is encapsulated in a private function.</span></span> <span data-ttu-id="31b6f-110">Para permitir que você rastreie o progresso do script enquanto ele verifica as definições de cada impressora, o script usa o método <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> para gerar uma mensagem informativa para impressoras com tamanho de papel válido e também para gerar um aviso para impressoras sem tamanho de papel válido.</span><span class="sxs-lookup"><span data-stu-id="31b6f-110">To enable you to track the progress of the script as it checks the settings for each printer, the script uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to raise an informational message for printers with legal size paper, and to raise a warning for printers without legal size paper.</span></span> <span data-ttu-id="31b6f-111">Essas mensagens são exibidas na Janela de **Saída** do IDE do [!INCLUDE[msCoName](../../includes/msconame-md.md)] VSTA ([!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications) quando você executa o pacote no designer.</span><span class="sxs-lookup"><span data-stu-id="31b6f-111">These messages appear in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE when you run the package in the designer.</span></span>

#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="31b6f-112">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="31b6f-112">To configure this Script Task example</span></span>

1.  <span data-ttu-id="31b6f-113">Crie a variável nomeada `PrinterList` com o tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="31b6f-113">Create the variable named `PrinterList` with type `Object`.</span></span>

2.  <span data-ttu-id="31b6f-114">Na página **Script** do **Editor da Tarefa Script**, adicione essa variável à propriedade ReadWriteVariables.</span><span class="sxs-lookup"><span data-stu-id="31b6f-114">On the **Script** page of the **Script Task Editor**, add this variable to the ReadWriteVariables property.</span></span>

3.  <span data-ttu-id="31b6f-115">No projeto de script, adicione uma referência ao namespace **System.Drawing**.</span><span class="sxs-lookup"><span data-stu-id="31b6f-115">In the script project, add a reference to the **System.Drawing** namespace.</span></span>

4.  <span data-ttu-id="31b6f-116">Em seu código, use `Imports` instruções para importar o **System. Collections** e os `System.Drawing.Printing` namespaces.</span><span class="sxs-lookup"><span data-stu-id="31b6f-116">In your code, use `Imports` statements to import the **System.Collections** and the `System.Drawing.Printing` namespaces.</span></span>

### <a name="code"></a><span data-ttu-id="31b6f-117">Código</span><span class="sxs-lookup"><span data-stu-id="31b6f-117">Code</span></span>

```vb
Public Sub Main()

    Dim printerName As String
    Dim currentPrinter As New PrinterSettings
    Dim size As PaperSize

    Dim printerList As New ArrayList
    For Each printerName In PrinterSettings.InstalledPrinters
        currentPrinter.PrinterName = printerName
        If PrinterHasLegalPaper(currentPrinter) Then
            printerList.Add(printerName)
            Dts.Events.FireInformation(0, "Example", _
                "Printer " & printerName & " has legal paper.", _
                String.Empty, 0, False)
        Else
            Dts.Events.FireWarning(0, "Example", _
                "Printer " & printerName & " DOES NOT have legal paper.", _
                String.Empty, 0)
        End If
    Next

    Dts.Variables("PrinterList").Value = printerList

    Dts.TaskResult = ScriptResults.Success

End Sub

Private Function PrinterHasLegalPaper( _
    ByVal thisPrinter As PrinterSettings) As Boolean

    Dim size As PaperSize
    Dim hasLegal As Boolean = False

    For Each size In thisPrinter.PaperSizes
        If size.Kind = PaperKind.Legal Then
            hasLegal = True
        End If
    Next

    Return hasLegal

End Function
```

```csharp
public void Main()
        {

            PrinterSettings currentPrinter = new PrinterSettings();
            PaperSize size;
            Boolean Flag = false;

            ArrayList printerList = new ArrayList();
            foreach (string printerName in PrinterSettings.InstalledPrinters)
            {
                currentPrinter.PrinterName = printerName;
                if (PrinterHasLegalPaper(currentPrinter))
                {
                    printerList.Add(printerName);
                    Dts.Events.FireInformation(0, "Example", "Printer " + printerName + " has legal paper.", String.Empty, 0, ref Flag);
                }
                else
                {
                    Dts.Events.FireWarning(0, "Example", "Printer " + printerName + " DOES NOT have legal paper.", String.Empty, 0);
                }
            }

            Dts.Variables["PrinterList"].Value = printerList;

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private bool PrinterHasLegalPaper(PrinterSettings thisPrinter)
        {

            bool hasLegal = false;

            foreach (PaperSize size in thisPrinter.PaperSizes)
            {
                if (size.Kind == PaperKind.Legal)
                {
                    hasLegal = true;
                }
            }

            return hasLegal;

        }
```

<span data-ttu-id="31b6f-118">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="31b6f-118">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="31b6f-119">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="31b6f-119">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="31b6f-120">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="31b6f-120">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="31b6f-121">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="31b6f-121">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="31b6f-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31b6f-122">See Also</span></span>
 [<span data-ttu-id="31b6f-123">Exemplos de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="31b6f-123">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)


