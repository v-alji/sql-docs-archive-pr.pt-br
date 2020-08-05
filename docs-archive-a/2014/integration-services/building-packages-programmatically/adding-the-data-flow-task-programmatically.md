---
title: Adicionar a tarefa de Fluxo de Dados programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- adding Data Flow task
- SSIS data flow
- data flow task [Integration Services], adding
- MainPipe object
ms.assetid: 0ca03712-a82e-4aa7-949b-f869a8936ddf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f7e699cc8e88bafb2a4508fdac8560fa73befe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572652"
---
# <a name="adding-the-data-flow-task-programmatically"></a><span data-ttu-id="9b5e3-102">Adicionando a tarefa Fluxo de Dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="9b5e3-102">Adding the Data Flow Task Programmatically</span></span>
  <span data-ttu-id="9b5e3-103">O [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] inclui uma tarefa chamada Fluxo de Dados, que é representada pelo namespace <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> no modelo de objeto.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-103">[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a task called the Data Flow task, which is represented by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> namespace in the object model.</span></span> <span data-ttu-id="9b5e3-104">A tarefa Fluxo de Dados é uma tarefa especializada, de alto desempenho, dedicada a transformar e mover dados durante a execução de pacotes.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-104">The Data Flow task is a specialized, high-performance task, dedicated to transforming and moving data during package execution.</span></span> <span data-ttu-id="9b5e3-105">Assim como outras tarefas, a tarefa Fluxo de Dados é encapsulada pelo objeto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> e, na perspectiva do mecanismo de tempo de execução, essa é apenas mais uma tarefa do pacote.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-105">Like other tasks, the Data Flow task is wrapped by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object, and from the perspective of the run-time engine, this task is just another task in the package.</span></span> <span data-ttu-id="9b5e3-106">Porém, o fluxo de dados contém objetos adicionais chamados de componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-106">However, the data flow contains additional objects called data flow components.</span></span> <span data-ttu-id="9b5e3-107">Esses são os componentes que fazem com que os dados se movam de uma origem para um destino, às vezes por uma transformação.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-107">These components are the components that make data move from a source to a destination, sometimes through a transformation.</span></span> <span data-ttu-id="9b5e3-108">Os componentes definem a direção do movimento e como os dados são transformados.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-108">The components define both the direction of movement and how data is transformed.</span></span> <span data-ttu-id="9b5e3-109">A configuração da tarefa Fluxo de Dados envolve a adição de componentes à tarefa e, em seguida, a conexão desses componentes para estabelecer o fluxo de dados e conseguir a transformação pretendida.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-109">Configuring the Data Flow task involves adding components to the task, and then connecting them to establish the flow of data and achieve the intended transformation.</span></span>  
  
 <span data-ttu-id="9b5e3-110">Há três tipos de componentes em uma tarefa Fluxo de Dados: **Origens de Fluxo de Dados**, **Transformações de Fluxo de Dados** e **Destinos de Fluxo de Dados**, mostrados nesta ordem dentro da caixa de ferramentas do Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b5e3-110">There are three types of components within a Data Flow task: **Data Flow Sources**, **Data Flow Transformations**, and **Data Flow Destinations**, shown in that order within the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer toolbox.</span></span> <span data-ttu-id="9b5e3-111">Estes tipos também são referenciados simplesmente como origens, transformações ou destinos.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-111">These types are also referred to more simply as sources, transformations, or destinations.</span></span> <span data-ttu-id="9b5e3-112">Como os próprios nomes indicam, há um fluxo de dados de uma origem para uma transformação e, depois, para um destino.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-112">As implied by the names, data flows from a source to a transformation, and then to a destination.</span></span> <span data-ttu-id="9b5e3-113">Esta é uma descrição simplificada do fluxo de dados para ilustrar o conceito, mas a tarefa Fluxo de Dados é flexível e eficiente o bastante para lidar com várias origens e conectar diversas transformações que enviam a saída a vários destinos.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-113">This is a simplistic description of the data flow to illustrate the concept, but the Data Flow task is flexible and powerful enough to handle multiple sources, and to connect together many transformations that send output to multiple destinations.</span></span>  
  
 <span data-ttu-id="9b5e3-114">A tarefa Fluxo de Dados é adicionada a um pacote da mesma forma que são adicionadas outras tarefas.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-114">The Data Flow task is added to a package the same way other tasks are added.</span></span> <span data-ttu-id="9b5e3-115">Após a adição da tarefa, ela é configurada através da adição de componentes à tarefa de fluxo de dados, e da configuração e conexão de componentes na tarefa.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-115">After the task has been added, it is configured by adding components to the data flow task, and configuring and connecting components in the task.</span></span>  
  
## <a name="sample"></a><span data-ttu-id="9b5e3-116">Amostra</span><span class="sxs-lookup"><span data-stu-id="9b5e3-116">Sample</span></span>  
 <span data-ttu-id="9b5e3-117">O exemplo de código a seguir mostra como adicionar uma tarefa Fluxo de Dados a um pacote.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-117">The following code sample shows how to add a Data Flow task to a package.</span></span> <span data-ttu-id="9b5e3-118">Este exemplo exige uma referência aos assemblies Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap e Microsoft.SqlServer.ManagedDTS.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-118">This example requires a reference to the assemblies Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap, and Microsoft.SqlServer.ManagedDTS.</span></span>  
  
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
      Package p = new Package();  
      Executable e = p.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;   
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim e As Executable = p.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As TaskHost = CType(e, TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="9b5e3-119">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="9b5e3-119">External Resources</span></span>  
 <span data-ttu-id="9b5e3-120">Entrada no blog, [EzAPI – Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) (EzAPI – atualizado para o SQL Server 2012) em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-120">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="9b5e3-121">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9b5e3-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9b5e3-122">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="9b5e3-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9b5e3-123">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="9b5e3-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9b5e3-124">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="9b5e3-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5e3-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b5e3-125">See Also</span></span>  
 [<span data-ttu-id="9b5e3-126">Descobrindo componentes de fluxo de dados programaticamente</span><span class="sxs-lookup"><span data-stu-id="9b5e3-126">Discovering Data Flow Components Programmatically</span></span>](../building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
  
  
