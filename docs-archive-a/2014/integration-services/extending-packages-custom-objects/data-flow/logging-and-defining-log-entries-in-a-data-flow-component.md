---
title: Registrar em log e definir entradas de log em um componente de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- logs [Integration Services], custom
- custom log entries [Integration Services]
- custom data flow components [Integration Services], logging
- data flow components [Integration Services], logging
ms.assetid: 2190dba9-59b5-480b-b8e9-21d5a54c5917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 14dfec71679bbe455ae8be5face98b776a80b9e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679436"
---
# <a name="logging-and-defining-log-entries-in-a-data-flow-component"></a><span data-ttu-id="238ff-102">Registrando em log e definindo entradas de log em um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="238ff-102">Logging and Defining Log Entries in a Data Flow Component</span></span>
  <span data-ttu-id="238ff-103">Os componentes de fluxo de dados personalizados podem postar mensagens em uma entrada de log existente por meio do método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="238ff-103">Custom data flow components can post messages to an existing log entry by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="238ff-104">Eles também podem apresentar informações ao usuário através do método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> ou de métodos semelhantes da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="238ff-104">They can also present information to the user by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> method or similar methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="238ff-105">Entretanto, essa abordagem leva à sobrecarga pois eventos adicionais são gerados e manipulados, e força o usuário a examinar mensagens informativas detalhadas em busca de mensagens que possam ser do seu interesse.</span><span class="sxs-lookup"><span data-stu-id="238ff-105">However, this approach incurs the overhead of raising and handling additional events, and forces the user to sift through verbose informational messages for the messages that may be of interest to them.</span></span> <span data-ttu-id="238ff-106">Você pode usar uma entrada de log personalizada, conforme descrito a seguir, para fornecer informações de log personalizadas com rótulos distintos a usuários de seu componente.</span><span class="sxs-lookup"><span data-stu-id="238ff-106">You can use a custom log entry as described below to provide distinctly labeled custom log information to users of your component.</span></span>  
  
## <a name="registering-and-using-a-custom-log-entry"></a><span data-ttu-id="238ff-107">Registrando e usando uma entrada de log personalizada</span><span class="sxs-lookup"><span data-stu-id="238ff-107">Registering and Using a Custom Log Entry</span></span>  
  
### <a name="registering-a-custom-log-entry"></a><span data-ttu-id="238ff-108">Registrar uma entrada de log personalizada</span><span class="sxs-lookup"><span data-stu-id="238ff-108">Registering a Custom Log Entry</span></span>  
 <span data-ttu-id="238ff-109">Para registrar uma entrada de log personalizada a ser usada por seu componente, substitua o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="238ff-109">To register a custom log entry for use by your component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="238ff-110">O exemplo a seguir registra uma entrada de log personalizada e fornece um nome e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="238ff-110">The following example registers a custom log entry and provides a name and description.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Runtime;  
...  
private const string MyLogEntryName = "My Custom Component Log Entry";  
private const string MyLogEntryDescription = "Log entry from My Custom Component ";  
...  
    public override void RegisterLogEntries()  
    {  
      this.LogEntryInfos.Add(MyLogEntryName,  
        MyLogEntryDescription,  
        Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT);  
    }  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
...  
Private Const MyLogEntryName As String = "My Custom Component Log Entry"   
Private Const MyLogEntryDescription As String = "Log entry from My Custom Component "  
...  
Public  Overrides Sub RegisterLogEntries()   
  Me.LogEntryInfos.Add(MyLogEntryName, _  
    MyLogEntryDescription, _  
    Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT)   
End Sub  
```  
  
 <span data-ttu-id="238ff-111">A enumeração <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> fornece uma dica ao runtime sobre a frequência com que o evento será registrado:</span><span class="sxs-lookup"><span data-stu-id="238ff-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> enumeration provides a hint to the runtime about how frequently the event will be logged:</span></span>  
  
-   <span data-ttu-id="238ff-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: o evento só é registrado às vezes, mas não em toda execução.</span><span class="sxs-lookup"><span data-stu-id="238ff-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: Event is logged only sometimes, not during every execution.</span></span>  
  
-   <span data-ttu-id="238ff-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: o evento é registrado em um número constante de horas em toda execução.</span><span class="sxs-lookup"><span data-stu-id="238ff-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: Event is logged a constant number of times during every execution.</span></span>  
  
-   <span data-ttu-id="238ff-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: o evento é registrado um determinado número de vezes, que é proporcional à quantidade de trabalho concluído.</span><span class="sxs-lookup"><span data-stu-id="238ff-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: Event is logged a number of times proportional to the amount of work completed.</span></span>  
  
 <span data-ttu-id="238ff-115">O exemplo anterior usa o <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> pois o componente espera registrar uma só entrada em cada execução.</span><span class="sxs-lookup"><span data-stu-id="238ff-115">The example above uses <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> because the component expects to log an entry once per execution.</span></span>  
  
 <span data-ttu-id="238ff-116">Depois de registrar a entrada de log personalizada e adicionar uma instância do seu componente personalizado na superfície do designer de fluxo de dados, a caixa de diálogo **Log** do designer exibe uma nova entrada de log com o nome "My Custom Component Log Entry" na lista de entradas de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="238ff-116">After registering the custom log entry and adding an instance of your custom component to the data flow designer surface, the **Logging** dialog box in the designer displays a new log entry with the name "My Custom Component Log Entry" in the list of available log entries.</span></span>  
  
### <a name="logging-to-a-custom-log-entry"></a><span data-ttu-id="238ff-117">Registrando uma entrada de log personalizada</span><span class="sxs-lookup"><span data-stu-id="238ff-117">Logging to a Custom Log Entry</span></span>  
 <span data-ttu-id="238ff-118">Depois do registro da entrada de log personalizada, o componente pode registrar mensagens personalizadas.</span><span class="sxs-lookup"><span data-stu-id="238ff-118">After registering the custom log entry, the component can now log custom messages.</span></span> <span data-ttu-id="238ff-119">O exemplo a seguir escreve uma entrada de log personalizada durante o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> que contém o texto de uma instrução SQL usado pelo componente.</span><span class="sxs-lookup"><span data-stu-id="238ff-119">The example below writes a custom log entry during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method that contains the text of a SQL statement used by the component.</span></span>  
  
```csharp  
public override void PreExecute()  
{  
  DateTime now = DateTime.Now;  
  byte[] additionalData = null;  
  this.ComponentMetaData.PostLogMessage(MyLogEntryName,  
    this.ComponentMetaData.Name,  
    "Command Sent was: " + myCommand.CommandText,  
    now, now, 0, ref additionalData);  
}  
```  
  
```vb  
Public  Overrides Sub PreExecute()   
  Dim now As DateTime = DateTime.Now   
  Dim additionalData As Byte() = Nothing   
  Me.ComponentMetaData.PostLogMessage(MyLogEntryName, _  
    Me.ComponentMetaData.Name, _  
    "Command Sent was: " + myCommand.CommandText, _  
    now, now, 0, additionalData)   
End Sub  
```  
  
 <span data-ttu-id="238ff-120">Agora, quando o usuário executar o pacote, depois de selecionar "My Custom Component Log Entry" na caixa de diálogo **Log**, o log conterá uma entrada claramente rotulada como "User::My Custom Component Log Entry".</span><span class="sxs-lookup"><span data-stu-id="238ff-120">Now when the user executes the package, after selecting the "My Custom Component Log Entry" in the **Logging** dialog box, the log will contain an entry clearly labeled as "User::My Custom Component Log Entry."</span></span> <span data-ttu-id="238ff-121">Essa nova entrada de log contém o texto da instrução SQL, o carimbo de data/hora e quaisquer dados adicionais registrados pelo desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="238ff-121">This new log entry contains the text of the SQL statement, the timestamp, and any additional data logged by the developer.</span></span>  
  
<span data-ttu-id="238ff-122">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="238ff-122">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="238ff-123">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="238ff-123">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="238ff-124">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="238ff-124">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="238ff-125">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="238ff-125">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238ff-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="238ff-126">See Also</span></span>  
 [<span data-ttu-id="238ff-127">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="238ff-127">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
