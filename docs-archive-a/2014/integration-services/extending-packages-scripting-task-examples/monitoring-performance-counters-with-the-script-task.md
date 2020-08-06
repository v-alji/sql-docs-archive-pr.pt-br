---
title: Monitorar contadores de desempenho com a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- performance counters [Integration Services]
- SSIS Script task, performance counters
- custom performance counters [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], performance counters
- counters [Integration Services]
ms.assetid: 86609bf1-cae6-435e-a58d-41bdfc521e94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 143e11ff966eb11961aa15073a503522c4b9c86b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683611"
---
# <a name="monitoring-performance-counters-with-the-script-task"></a><span data-ttu-id="6a389-102">Monitorando contadores de desempenho com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="6a389-102">Monitoring Performance Counters with the Script Task</span></span>
  <span data-ttu-id="6a389-103">Talvez administradores precisem monitorar o desempenho de pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que executam transformações complexas em grandes volumes de dados.</span><span class="sxs-lookup"><span data-stu-id="6a389-103">Administrators may need to monitor the performance of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that perform complex transformations on large amounts of data.</span></span> <span data-ttu-id="6a389-104">O namespace **System.Diagnostics** do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fornece classes para usar contadores de desempenho existentes e para criar contadores de desempenho próprios.</span><span class="sxs-lookup"><span data-stu-id="6a389-104">The **System.Diagnostics** namespace of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for using existing performance counters and for creating your own performance counters.</span></span>  
  
 <span data-ttu-id="6a389-105">Os contadores de desempenho armazenam informações de desempenho do aplicativo que podem ser usadas para analisar o desempenho do software com tempo.</span><span class="sxs-lookup"><span data-stu-id="6a389-105">Performance counters store application performance information that you can use to analyze the performance of software over time.</span></span> <span data-ttu-id="6a389-106">Contadores de desempenho podem ser monitorados local ou remotamente através da ferramenta **Monitor de Desempenho**.</span><span class="sxs-lookup"><span data-stu-id="6a389-106">Performance counters can be monitored locally or remotely by using the **Performance Monitor** tool.</span></span> <span data-ttu-id="6a389-107">Você pode armazenar os valores de contadores de desempenho em variáveis para posteriormente criar ramificações do fluxo de controle no pacote.</span><span class="sxs-lookup"><span data-stu-id="6a389-107">You can store the values of performance counters in variables for later control flow branching in the package.</span></span>  
  
 <span data-ttu-id="6a389-108">Como alternativa ao uso de contadores de desempenho, você pode gerar o evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> através da propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> do objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="6a389-108">As an alternative to using performance counters, you can raise the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="6a389-109">O evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> retorna o progresso incremental e informações completas sobre percentual ao runtime [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a389-109">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event returns both incremental progress and percentage complete information to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a389-110">Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="6a389-110">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="6a389-111">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="6a389-111">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="6a389-112">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="6a389-112">Description</span></span>  
 <span data-ttu-id="6a389-113">O exemplo a seguir cria um contador de desempenho personalizado e incrementa o contador.</span><span class="sxs-lookup"><span data-stu-id="6a389-113">The following example creates a custom performance counter and increments the counter.</span></span> <span data-ttu-id="6a389-114">Primeiro, o exemplo determina se o contador de desempenho já existe.</span><span class="sxs-lookup"><span data-stu-id="6a389-114">First, the example determines whether the performance counter already exists.</span></span> <span data-ttu-id="6a389-115">Se o contador de desempenho não tiver sido criado, o script chamará o método `Create` do objeto `PerformanceCounterCategory` para criá-lo.</span><span class="sxs-lookup"><span data-stu-id="6a389-115">If the performance counter has not been created, the script calls the `Create` method of the `PerformanceCounterCategory` object to create it.</span></span> <span data-ttu-id="6a389-116">Depois que o contador de desempenho for criado, o script irá incrementá-lo.</span><span class="sxs-lookup"><span data-stu-id="6a389-116">After the performance counter has been created, the script increments the counter.</span></span> <span data-ttu-id="6a389-117">Finalmente, o exemplo adota a prática ideal de chamar o método `Close` no contador de desempenho quando ele não é mais necessário.</span><span class="sxs-lookup"><span data-stu-id="6a389-117">Finally, the example follows the best practice of calling the `Close` method on the performance counter when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a389-118">É necessário ter direitos administrativos para criar uma nova categoria de contador de desempenho e um contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="6a389-118">Creating a new performance counter category and performance counter requires administrative rights.</span></span> <span data-ttu-id="6a389-119">Além disso, a nova categoria e o contador permanecem no computador depois da sua criação.</span><span class="sxs-lookup"><span data-stu-id="6a389-119">Also, the new category and counter persist on the computer after creation.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="6a389-120">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="6a389-120">To configure this Script Task example</span></span>  
  
-   <span data-ttu-id="6a389-121">Use uma `Imports` instrução em seu código para importar o namespace **System. Diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="6a389-121">Use an `Imports` statement in your code to import the **System.Diagnostics** namespace.</span></span>  
  
### <a name="example-code"></a><span data-ttu-id="6a389-122">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="6a389-122">Example Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myCounter As PerformanceCounter  
  
    Try  
        'Create the performance counter if it does not already exist.  
        If Not _  
        PerformanceCounterCategory.Exists("TaskExample") Then  
            PerformanceCounterCategory.Create("TaskExample", _  
                "Task Performance Counter Example", "Iterations", _  
                "Number of times this task has been called.")  
        End If  
  
        'Initialize the performance counter.  
        myCounter = New PerformanceCounter("TaskExample", _  
            "Iterations", String.Empty, False)  
  
        'Increment the performance counter.  
        myCounter.Increment()  
  
         myCounter.Close()  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Task Performance Counter Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
  
public class ScriptMain  
{  
  
public void Main()  
        {  
  
            PerformanceCounter myCounter;  
  
            try  
            {  
                //Create the performance counter if it does not already exist.  
                if (!PerformanceCounterCategory.Exists("TaskExample"))  
                {  
                    PerformanceCounterCategory.Create("TaskExample", "Task Performance Counter Example", "Iterations", "Number of times this task has been called.");  
                }  
  
                //Initialize the performance counter.  
                myCounter = new PerformanceCounter("TaskExample", "Iterations", String.Empty, false);  
  
                //Increment the performance counter.  
                myCounter.Increment();  
  
                myCounter.Close();  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Task Performance Counter Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
```  
  
<span data-ttu-id="6a389-123">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6a389-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6a389-124">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="6a389-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6a389-125">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="6a389-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6a389-126">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="6a389-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
