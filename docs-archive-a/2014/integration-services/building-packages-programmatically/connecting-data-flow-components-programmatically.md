---
title: Conectar componentes de fluxo de dados programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow task [Integration Services], components
- paths [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 404ecab7-7698-447b-93d6-dd256beb11ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39494fee5314f309b79abfd30303fdd607fd3c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572648"
---
# <a name="connecting-data-flow-components-programmatically"></a><span data-ttu-id="86d62-102">Conectando componentes de fluxo de dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="86d62-102">Connecting Data Flow Components Programmatically</span></span>
  <span data-ttu-id="86d62-103">Depois de adicionar componentes à tarefa de fluxo de dados, conecte-os para criar uma árvore de execução que represente o fluxo de dados das origens às transformações nos destinos.</span><span class="sxs-lookup"><span data-stu-id="86d62-103">After you have added components to the data flow task, you connect them to create an execution tree that represents the flow of data from sources through transformations to destinations.</span></span> <span data-ttu-id="86d62-104">Você usa objetos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> para conectar os componentes no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="86d62-104">You use <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects to connect the components in the data flow.</span></span>  
  
## <a name="creating-a-path"></a><span data-ttu-id="86d62-105">Criando um caminho</span><span class="sxs-lookup"><span data-stu-id="86d62-105">Creating a Path</span></span>  
 <span data-ttu-id="86d62-106">Chame o método New da propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> para criar um caminho novo e adicioná-lo à coleção de caminhos na tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="86d62-106">Call the New method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> interface to create a new path and add it to the collection of paths in the data flow task.</span></span> <span data-ttu-id="86d62-107">Esse método retorna um objeto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> novo, desconectado a ser usado para conectar dois componentes.</span><span class="sxs-lookup"><span data-stu-id="86d62-107">This method returns a new, disconnected <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, which you then use to connect two components.</span></span>  
  
 <span data-ttu-id="86d62-108">Chame o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> para conectar o caminho e notificar os componentes que participam do caminho de que eles foram conectados.</span><span class="sxs-lookup"><span data-stu-id="86d62-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> method to connect the path and to notify the components participating in the path that they have been connected.</span></span> <span data-ttu-id="86d62-109">Esse método aceita um <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> do componente upstream e um <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> do componente downstream como parâmetros.</span><span class="sxs-lookup"><span data-stu-id="86d62-109">This method accepts an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the upstream component and an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> of the downstream component as parameters.</span></span> <span data-ttu-id="86d62-110">Por padrão, a chamada ao método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> do componente cria uma única entrada para componentes que têm entradas e uma única saída para componentes que têm saídas.</span><span class="sxs-lookup"><span data-stu-id="86d62-110">By default, the call to the component's <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method creates a single input for components that have inputs, and a single output for components that have outputs.</span></span> <span data-ttu-id="86d62-111">O exemplo a seguir usa essa saída padrão da origem e a entrada do destino.</span><span class="sxs-lookup"><span data-stu-id="86d62-111">The following example uses this default output of the source and input of the destination.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="86d62-112">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="86d62-112">Next Step</span></span>  
 <span data-ttu-id="86d62-113">Depois de estabelecer um caminho entre dois componentes, a próxima etapa é mapear colunas de entrada no componente downstream, discutida no próximo tópico, [Selecionar colunas de entrada programaticamente](../building-packages-programmatically/selecting-input-columns-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="86d62-113">After you establish a path between two components, the next step is to map input columns in the downstream component, which is discussed in the next topic, [Selecting Input Columns Programmatically](../building-packages-programmatically/selecting-input-columns-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="86d62-114">Amostra</span><span class="sxs-lookup"><span data-stu-id="86d62-114">Sample</span></span>  
 <span data-ttu-id="86d62-115">O exemplo de código a seguir mostra como estabelecer um caminho entre dois componentes.</span><span class="sxs-lookup"><span data-stu-id="86d62-115">The following code sample shows how to establish a path between two components.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Create the source component.    
      IDTSComponentMetaData100 source =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      source.ComponentClassID = "DTSAdapter.OleDbSource";  
      CManagedComponentWrapper srcDesignTime = source.Instantiate();  
      srcDesignTime.ProvideComponentProperties();  
  
      // Create the destination component.  
      IDTSComponentMetaData100 destination =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      destination.ComponentClassID = "DTSAdapter.OleDbDestination";  
      CManagedComponentWrapper destDesignTime = destination.Instantiate();  
      destDesignTime.ProvideComponentProperties();  
  
      // Create the path.  
      IDTSPath100 path = dataFlowTask.PathCollection.New();  
      path.AttachPathAndPropagateNotifications(source.OutputCollection[0],  
        destination.InputCollection[0]);  
    }  
  }  
```  
  
 <span data-ttu-id="86d62-116">}</span><span class="sxs-lookup"><span data-stu-id="86d62-116">}</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Create the source component.    
    Dim source As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    source.ComponentClassID = "DTSAdapter.OleDbSource"  
    Dim srcDesignTime As CManagedComponentWrapper = source.Instantiate()  
    srcDesignTime.ProvideComponentProperties()  
  
    ' Create the destination component.  
    Dim destination As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    destination.ComponentClassID = "DTSAdapter.OleDbDestination"  
    Dim destDesignTime As CManagedComponentWrapper = destination.Instantiate()  
    destDesignTime.ProvideComponentProperties()  
  
    ' Create the path.  
    Dim path As IDTSPath100 = dataFlowTask.PathCollection.New()  
    path.AttachPathAndPropagateNotifications(source.OutputCollection(0), _  
      destination.InputCollection(0))  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="86d62-117">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="86d62-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="86d62-118">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="86d62-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="86d62-119">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="86d62-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="86d62-120">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="86d62-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d62-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86d62-121">See Also</span></span>  
 [<span data-ttu-id="86d62-122">Selecionando colunas de entrada programaticamente</span><span class="sxs-lookup"><span data-stu-id="86d62-122">Selecting Input Columns Programmatically</span></span>](../building-packages-programmatically/selecting-input-columns-programmatically.md)  
  
  
