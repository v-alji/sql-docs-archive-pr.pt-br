---
title: Desenvolver tipos específicos de componentes de fluxo de dados | Microsoft Docs
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
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 348e219a-b8ff-425e-b9c6-811880101c54
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e168c866e03bfa5fd1f32127e4bfd6e58a2e8d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683621"
---
# <a name="developing-specific-types-of-data-flow-components"></a><span data-ttu-id="a8100-102">Desenvolvendo tipos específicos de componentes de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="a8100-102">Developing Specific Types of Data Flow Components</span></span>
  <span data-ttu-id="a8100-103">Esta seção aborda as especificações do desenvolvimento de componentes de origem, componentes de transformação com saídas síncronas, componentes de transformação com saídas assíncronas e componentes de destino.</span><span class="sxs-lookup"><span data-stu-id="a8100-103">This section covers the specifics of developing source components, transformation components with synchronous outputs, transformation components with asynchronous outputs, and destination components.</span></span>  
  
 <span data-ttu-id="a8100-104">Para obter informações sobre desenvolvimento de componentes em geral, consulte [Desenvolver um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a8100-104">For information about component development in general, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8100-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a8100-105">In This Section</span></span>  
 [<span data-ttu-id="a8100-106">Desenvolvendo um componente de origem personalizado</span><span class="sxs-lookup"><span data-stu-id="a8100-106">Developing a Custom Source Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)  
 <span data-ttu-id="a8100-107">Contém informações sobre o desenvolvimento de um componente que acessa dados de uma fonte de dados externa e fornece-os a componentes downstream no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a8100-107">Contains information on developing a component that accesses data from an external data source and supplies it to downstream components in the data flow.</span></span>  
  
 [<span data-ttu-id="a8100-108">Desenvolvendo um componente de transformação personalizado com saídas síncronas</span><span class="sxs-lookup"><span data-stu-id="a8100-108">Developing a Custom Transformation Component with Synchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md)  
 <span data-ttu-id="a8100-109">Contém informações sobre o desenvolvimento de um componente de transformação cujas saídas são síncronas para suas entradas.</span><span class="sxs-lookup"><span data-stu-id="a8100-109">Contains information on developing a transformation component whose outputs are synchronous to its inputs.</span></span> <span data-ttu-id="a8100-110">Esses componentes não adicionam dados ao fluxo de dados, mas processam dados percorridos.</span><span class="sxs-lookup"><span data-stu-id="a8100-110">These components do not add data to the data flow, but process data as it passes through.</span></span>  
  
 [<span data-ttu-id="a8100-111">Desenvolvendo um componente de transformação personalizado com saídas assíncronas</span><span class="sxs-lookup"><span data-stu-id="a8100-111">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)  
 <span data-ttu-id="a8100-112">Contém informações sobre o desenvolvimento de um componente de transformação cujas saídas não são síncronas para suas entradas.</span><span class="sxs-lookup"><span data-stu-id="a8100-112">Contains information on developing a transformation component whose outputs are not synchronous to its inputs.</span></span> <span data-ttu-id="a8100-113">Esses componentes recebem dados de componentes upstream, mas também adicionam dados ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a8100-113">These components receive data from upstream components, but also add data to the dataflow.</span></span>  
  
 [<span data-ttu-id="a8100-114">Desenvolvendo um componente de destino personalizado</span><span class="sxs-lookup"><span data-stu-id="a8100-114">Developing a Custom Destination Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)  
 <span data-ttu-id="a8100-115">Contém informações sobre o desenvolvimento de um componente que recebe linhas de componentes upstream no fluxo de dados e grava-as em uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="a8100-115">Contains information on developing a component that receives rows from upstream components in the data flow and writes them to an external data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a8100-116">Referência</span><span class="sxs-lookup"><span data-stu-id="a8100-116">Reference</span></span>  
 <xref:Microsoft.SqlServer.Dts.Pipeline>  
 <span data-ttu-id="a8100-117">Contém as classes e interfaces usadas para criar componentes de fluxo de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="a8100-117">Contains the classes and interfaces used to create custom data flow components.</span></span>  
  
 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>  
 <span data-ttu-id="a8100-118">Contém as classes não gerenciadas e as interfaces da tarefa de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a8100-118">Contains the unmanaged classes and interfaces of the data flow task.</span></span> <span data-ttu-id="a8100-119">O desenvolvedor usa esses elementos e o namespace <xref:Microsoft.SqlServer.Dts.Pipeline> gerenciado quando cria um fluxo de dados programaticamente ou cria componentes de fluxo de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="a8100-119">The developer uses these, and the managed <xref:Microsoft.SqlServer.Dts.Pipeline> namespace, when building a data flow programmatically or creating custom data flow components.</span></span>  
  
<span data-ttu-id="a8100-120">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a8100-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a8100-121">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="a8100-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a8100-122">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="a8100-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a8100-123">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="a8100-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8100-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8100-124">See Also</span></span>  
 <span data-ttu-id="a8100-125">[Comparando soluções de script e objetos personalizados](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="a8100-125">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="a8100-126">Desenvolver tipos específicos de componentes de Script</span><span class="sxs-lookup"><span data-stu-id="a8100-126">Developing Specific Types of Script Components</span></span>](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md)  
  
  
