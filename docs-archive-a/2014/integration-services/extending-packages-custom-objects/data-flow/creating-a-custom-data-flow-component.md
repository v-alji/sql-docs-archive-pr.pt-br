---
title: Criar um componente de fluxo de dados personalizado | Microsoft Docs
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
- design-time component interface [Integration Services]
- custom data flow components [Integration Services], about data flow components
- custom data flow components [Integration Services]
- data flow components [Integration Services]
- data flow components [Integration Services], developing
ms.assetid: 9d96bcf5-eba8-44bd-b113-ed51ad0d0521
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 110d07ff88707ad1a01f299b6f532df99ce58404
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575233"
---
# <a name="creating-a-custom-data-flow-component"></a><span data-ttu-id="48590-102">Criando um componente de fluxo de dados personalizado</span><span class="sxs-lookup"><span data-stu-id="48590-102">Creating a Custom Data Flow Component</span></span>
  <span data-ttu-id="48590-103">No [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], a tarefa de fluxo de dados expõe um modelo de objeto que permite que os desenvolvedores criem componentes de fluxo de dados personalizados, como fontes, transformações e destinos, usando o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] e o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="48590-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the data flow task exposes an object model that lets developers create custom data flow components-sources, transformations, and destinations-by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] and managed code.</span></span>  
  
 <span data-ttu-id="48590-104">Uma tarefa de fluxo de dados consiste em componentes que contêm uma interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> e uma coleção de objetos <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> que definem o movimento dos dados entre os componentes.</span><span class="sxs-lookup"><span data-stu-id="48590-104">A data flow task consists of components that contain an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface and a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects that define the movement of data between components.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48590-105">Quando você cria um provedor personalizado, precisa atualizar o arquivo ProviderDescriptors.xml com os valores de coluna de metadados.</span><span class="sxs-lookup"><span data-stu-id="48590-105">When you create a custom provider, you need to update the ProviderDescriptors.xml file with the metadata column values.</span></span>  
  
## <a name="design-time-and-run-time"></a><span data-ttu-id="48590-106">Tempo de design e tempo de execução</span><span class="sxs-lookup"><span data-stu-id="48590-106">Design Time and Run Time</span></span>  
 <span data-ttu-id="48590-107">Antes da execução, diz-se que a tarefa de fluxo de dados está em um estado de tempo de design, quando sofre alterações incrementais.</span><span class="sxs-lookup"><span data-stu-id="48590-107">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="48590-108">As alterações podem incluir a adição ou remoção de componentes, a adição ou remoção dos objetos do caminho que conectam componentes e as alterações nos metadados dos componentes.</span><span class="sxs-lookup"><span data-stu-id="48590-108">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="48590-109">Quando ocorrem alterações em metadados, o componente pode monitorar e reagir às alterações.</span><span class="sxs-lookup"><span data-stu-id="48590-109">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="48590-110">Por exemplo, um componente pode desabilitar certas alterações ou fazer alterações adicionais em resposta a uma alteração.</span><span class="sxs-lookup"><span data-stu-id="48590-110">For example, a component can disallow certain changes or to make additional changes in response to a change.</span></span> <span data-ttu-id="48590-111">Em tempo de design, o designer interage com um componente através da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> em tempo de design.</span><span class="sxs-lookup"><span data-stu-id="48590-111">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="48590-112">No tempo de execução, a tarefa de fluxo de dados examina a sequência de componentes, prepara um plano de execução e gerencia um pool de threads de trabalho que executa o plano de trabalho.</span><span class="sxs-lookup"><span data-stu-id="48590-112">At execution time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="48590-113">Embora cada thread de trabalho desempenhe algum trabalho interno à tarefa de fluxo de dados, a principal tarefa do thread de trabalho é chamar os métodos do componente através da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="48590-113">Although each worker thread performs some work that is internal to the data flow task, the principal task of the worker thread is to call the methods of the component through the run-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interface.</span></span>  
  
## <a name="creating-a-component"></a><span data-ttu-id="48590-114">Criando um componente</span><span class="sxs-lookup"><span data-stu-id="48590-114">Creating a Component</span></span>  
 <span data-ttu-id="48590-115">Para criar um componente de fluxo de dados, você deve derivar uma classe da classe base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>, aplicar a classe <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> e substituir os métodos apropriados da classe base.</span><span class="sxs-lookup"><span data-stu-id="48590-115">To create a data flow component, you derive a class from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class, apply the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> class, and then override the appropriate methods of the base class.</span></span> <span data-ttu-id="48590-116">O <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implementa as interfaces <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> e expõe os métodos para você substituir em seu componente.</span><span class="sxs-lookup"><span data-stu-id="48590-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interfaces, and exposes their methods for you to override in your component.</span></span>  
  
 <span data-ttu-id="48590-117">Dependendo dos objetos usados pelo seu componente, seu projeto precisará de referências a alguns ou todos os assemblies seguintes:</span><span class="sxs-lookup"><span data-stu-id="48590-117">Depending on the objects used by your component, your project will require references to some or all of the following assemblies:</span></span>  
  
|<span data-ttu-id="48590-118">Recurso</span><span class="sxs-lookup"><span data-stu-id="48590-118">Feature</span></span>|<span data-ttu-id="48590-119">Assembly para referência</span><span class="sxs-lookup"><span data-stu-id="48590-119">Assembly to reference</span></span>|<span data-ttu-id="48590-120">Namespace para importar</span><span class="sxs-lookup"><span data-stu-id="48590-120">Namespace to import</span></span>|  
|-------------|---------------------------|-------------------------|  
|<span data-ttu-id="48590-121">Fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="48590-121">Data flow</span></span>|<span data-ttu-id="48590-122">Microsoft.SqlServer.PipelineHost</span><span class="sxs-lookup"><span data-stu-id="48590-122">Microsoft.SqlServer.PipelineHost</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline>|  
|<span data-ttu-id="48590-123">Wrapper de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="48590-123">Data flow wrapper</span></span>|<span data-ttu-id="48590-124">Microsoft.SqlServer.DTSPipelineWrap</span><span class="sxs-lookup"><span data-stu-id="48590-124">Microsoft.SqlServer.DTSPipelineWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>|  
|<span data-ttu-id="48590-125">Runtime</span><span class="sxs-lookup"><span data-stu-id="48590-125">Runtime</span></span>|<span data-ttu-id="48590-126">Microsoft.SQLServer.ManagedDTS</span><span class="sxs-lookup"><span data-stu-id="48590-126">Microsoft.SQLServer.ManagedDTS</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime>|  
|<span data-ttu-id="48590-127">Wrapper de runtime</span><span class="sxs-lookup"><span data-stu-id="48590-127">Runtime wrapper</span></span>|<span data-ttu-id="48590-128">Microsoft.SqlServer.DTSRuntimeWrap</span><span class="sxs-lookup"><span data-stu-id="48590-128">Microsoft.SqlServer.DTSRuntimeWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Wrapper>|  
  
 <span data-ttu-id="48590-129">O exemplo de código a seguir mostra um componente simples que deriva da classe base e aplica o <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="48590-129">The following code example shows a simple component that derives from the base class, and applies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="48590-130">Você precisa adicionar uma referência ao assembly DTSPipelineWrap.</span><span class="sxs-lookup"><span data-stu-id="48590-130">You need to add a reference to the DTSPipelineWrap assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SampleComponent", ComponentType = ComponentType.Transform )]  
    public class BasicComponent: PipelineComponent  
    {  
        // TODO: Override the base class methods.  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(DisplayName:="SampleComponent", ComponentType:=ComponentType.Transform)> _  
Public Class BasicComponent  
  
    Inherits PipelineComponent  
  
    ' TODO: Override the base class methods.  
  
End Class  
```  
  
<span data-ttu-id="48590-131">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="48590-131">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="48590-132">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="48590-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="48590-133">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="48590-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="48590-134">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="48590-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48590-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48590-135">See Also</span></span>  
 [<span data-ttu-id="48590-136">Desenvolvendo uma interface do usuário para um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="48590-136">Developing a User Interface for a Data Flow Component</span></span>](developing-a-user-interface-for-a-data-flow-component.md)  
  
  
