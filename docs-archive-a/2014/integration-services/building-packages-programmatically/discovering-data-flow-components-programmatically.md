---
title: Descobrir componentes de fluxo de dados programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- PipelineComponentInfos collection
- data flow task [Integration Services], components
- discovering data flow components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: ff92a96a-8af6-4532-82cc-c0bbff92401b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a18102f38f1ad06e918efe2ca529185d40deef9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680602"
---
# <a name="discovering-data-flow-components-programmatically"></a><span data-ttu-id="a23af-102">Descobrindo componentes de fluxo de dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="a23af-102">Discovering Data Flow Components Programmatically</span></span>
  <span data-ttu-id="a23af-103">Depois de adicionar uma tarefa de fluxo de dados a um pacote, sua próxima etapa será determinar os componentes de fluxo de dados que estarão disponíveis para uso.</span><span class="sxs-lookup"><span data-stu-id="a23af-103">After you have added a data flow task to a package, your next step may be to determine what data flow components are available for your use.</span></span> <span data-ttu-id="a23af-104">Você pode descobrir programaticamente as fontes de fluxo de dados, as transformações e os destinos instalados e disponíveis no computador local.</span><span class="sxs-lookup"><span data-stu-id="a23af-104">You can programmatically discover the data flow sources, transformations, and destinations that are installed and available on the local computer.</span></span> <span data-ttu-id="a23af-105">Para obter informações sobre como adicionar uma tarefa de fluxo de dados ao pacote, consulte [Adicionar a tarefa de fluxo de dados programaticamente](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="a23af-105">For information about adding a data flow task to the package, see [Adding the Data Flow Task Programmatically](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md).</span></span>  
  
## <a name="discovering-components"></a><span data-ttu-id="a23af-106">Descobrindo componentes</span><span class="sxs-lookup"><span data-stu-id="a23af-106">Discovering Components</span></span>  
 <span data-ttu-id="a23af-107">A classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> fornece a coleção <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A> que contém um objeto <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> para cada componente corretamente instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="a23af-107">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class provides the <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A> collection, which contains a <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> object for each component correctly installed on the local computer.</span></span> <span data-ttu-id="a23af-108">Cada <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> contém informações sobre um componente, como seu nome, sua descrição e seu nome de criação.</span><span class="sxs-lookup"><span data-stu-id="a23af-108">Each <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> contains information about a component such as its name, description, and creation name.</span></span> <span data-ttu-id="a23af-109">É possível usar o valor retornado na propriedade <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> para definir a propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> do <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> quando um componente for adicionado a um pacote.</span><span class="sxs-lookup"><span data-stu-id="a23af-109">You can use the value returned in the <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property to set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> when you add a component to a package.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a23af-110">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a23af-110">Next Step</span></span>  
 <span data-ttu-id="a23af-111">Depois de descobrir quais são os componentes disponíveis, a próxima etapa será adicionar e configurá-los, assunto que será discutido no próximo tópico, [Adicionar a tarefa de fluxo de dados programaticamente](../building-packages-programmatically/adding-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="a23af-111">After discovering available components, the next step is to add and configure the components, which is discussed in the next topic, [Adding Data Flow Components Programmatically](../building-packages-programmatically/adding-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="a23af-112">Amostra</span><span class="sxs-lookup"><span data-stu-id="a23af-112">Sample</span></span>  
 <span data-ttu-id="a23af-113">O exemplo de código a seguir mostra como enumerar a coleção <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos> do objeto <xref:Microsoft.SqlServer.Dts.Runtime.Application> para descobrir programaticamente os componentes de fluxo de dados disponíveis no computador local.</span><span class="sxs-lookup"><span data-stu-id="a23af-113">The following code sample shows how to enumerate the <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object to programmatically discover the data flow components available on the local computer.</span></span> <span data-ttu-id="a23af-114">Esse exemplo precisa de uma referência ao assembly Microsoft.SqlServer.ManagedDTS.</span><span class="sxs-lookup"><span data-stu-id="a23af-114">This sample requires a reference to the Microsoft.SqlServer.ManagedDTS assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Application application = new Application();  
      PipelineComponentInfos componentInfos = application.PipelineComponentInfos;  
  
      foreach (PipelineComponentInfo componentInfo in componentInfos)  
      {  
        Console.WriteLine("Name: " + componentInfo.Name + "\n" +  
          " CreationName: " + componentInfo.CreationName + "\n");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim application As Application = New Application()  
  
    Dim componentInfos As PipelineComponentInfos = application.PipelineComponentInfos  
  
    For Each componentInfo As PipelineComponentInfo In componentInfos  
      Console.WriteLine("Name: " & componentInfo.Name & vbCrLf & _  
        " CreationName: " & componentInfo.CreationName & vbCrLf)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="a23af-115">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a23af-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a23af-116">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="a23af-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a23af-117">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="a23af-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a23af-118">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="a23af-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23af-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a23af-119">See Also</span></span>  
 [<span data-ttu-id="a23af-120">Adicionando componentes de fluxo de dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="a23af-120">Adding Data Flow Components Programmatically</span></span>](../building-packages-programmatically/adding-data-flow-components-programmatically.md)  
  
  
