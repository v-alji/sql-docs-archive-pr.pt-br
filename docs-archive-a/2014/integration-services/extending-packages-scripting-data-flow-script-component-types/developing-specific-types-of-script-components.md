---
title: Desenvolver tipos específicos de componentes de Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: dfbbe959-6b4e-4b47-b9dd-bcc31929482d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 114c9ddca90ea02a8e1847444b28b9d5876650a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574779"
---
# <a name="developing-specific-types-of-script-components"></a><span data-ttu-id="5eb94-102">Desenvolvendo tipos específicos de componentes Script</span><span class="sxs-lookup"><span data-stu-id="5eb94-102">Developing Specific Types of Script Components</span></span>
  <span data-ttu-id="5eb94-103">O componente de Script é uma ferramenta configurável que pode ser usada no fluxo de dados de um pacote para atender a quase todos os requisitos não atendidos pelas fontes, transformações e destinos incluídos no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eb94-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="5eb94-104">Esta seção contém exemplos de código do componente Script que demonstram as quatro opções para configurar o componente Script:</span><span class="sxs-lookup"><span data-stu-id="5eb94-104">This section contains Script component code samples that demonstrate the four options for configuring the Script component:</span></span>  
  
-   <span data-ttu-id="5eb94-105">Como uma origem.</span><span class="sxs-lookup"><span data-stu-id="5eb94-105">As a source.</span></span>  
  
-   <span data-ttu-id="5eb94-106">Como uma transformação com saídas síncronas.</span><span class="sxs-lookup"><span data-stu-id="5eb94-106">As a transformation with synchronous outputs.</span></span>  
  
-   <span data-ttu-id="5eb94-107">Como uma transformação com saídas assíncronas.</span><span class="sxs-lookup"><span data-stu-id="5eb94-107">As a transformation with asynchronous outputs.</span></span>  
  
-   <span data-ttu-id="5eb94-108">Como um destino.</span><span class="sxs-lookup"><span data-stu-id="5eb94-108">As a destination.</span></span>  
  
 <span data-ttu-id="5eb94-109">Para obter exemplos adicionais do componente Script, consulte [Exemplos de componentes Script adicionais](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="5eb94-109">For additional examples of the Script component, see [Additional Script Component Examples](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5eb94-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5eb94-110">In This Section</span></span>  
 [<span data-ttu-id="5eb94-111">Criar uma origem com o componente de Script</span><span class="sxs-lookup"><span data-stu-id="5eb94-111">Creating a Source with the Script Component</span></span>](creating-a-source-with-the-script-component.md)  
 <span data-ttu-id="5eb94-112">Explica e demonstra como criar uma origem de fluxo de dados com o componente de Script.</span><span class="sxs-lookup"><span data-stu-id="5eb94-112">Explains and demonstrates how to create a data flow source by using the Script component.</span></span>  
  
 [<span data-ttu-id="5eb94-113">Criar uma transformação síncrona com o componente de Script</span><span class="sxs-lookup"><span data-stu-id="5eb94-113">Creating a Synchronous Transformation with the Script Component</span></span>](creating-a-synchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="5eb94-114">Explica e demonstra como criar uma transformação de fluxo de dados com saídas síncronas usando o componente Script.</span><span class="sxs-lookup"><span data-stu-id="5eb94-114">Explains and demonstrates how to create a data flow transformation with synchronous outputs by using the Script component.</span></span> <span data-ttu-id="5eb94-115">Esse tipo de transformação modifica linhas de dados no local à medida que passam pelo componente.</span><span class="sxs-lookup"><span data-stu-id="5eb94-115">This kind of transformation modifies rows of data in place as they pass through the component.</span></span>  
  
 [<span data-ttu-id="5eb94-116">Criar uma transformação assíncrona com o componente de Script</span><span class="sxs-lookup"><span data-stu-id="5eb94-116">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="5eb94-117">Explica e demonstra como criar uma transformação de fluxo de dados com saídas assíncronas usando o componente Script.</span><span class="sxs-lookup"><span data-stu-id="5eb94-117">Explains and demonstrates how to create a data flow transformation with asynchronous outputs by using the Script component.</span></span> <span data-ttu-id="5eb94-118">Esse tipo de transformação tem que ler todas as linhas de dados antes de adicionar mais informações, como agregações calculadas, aos dados que passam pelo componente.</span><span class="sxs-lookup"><span data-stu-id="5eb94-118">This kind of transformation has to read all rows of data before it can add more information, such as calculated aggregates, to the data that passes through the component.</span></span>  
  
 [<span data-ttu-id="5eb94-119">Criar um destino com o componente de Script</span><span class="sxs-lookup"><span data-stu-id="5eb94-119">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
 <span data-ttu-id="5eb94-120">Explica e demonstra como criar um destino de fluxo de dados com o componente de Script.</span><span class="sxs-lookup"><span data-stu-id="5eb94-120">Explains and demonstrates how to create a data flow destination by using the Script component.</span></span>  
  
<span data-ttu-id="5eb94-121">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5eb94-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5eb94-122">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="5eb94-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5eb94-123">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="5eb94-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5eb94-124">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="5eb94-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb94-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5eb94-125">See Also</span></span>  
 <span data-ttu-id="5eb94-126">[Comparando soluções de script e objetos personalizados](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="5eb94-126">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="5eb94-127">Desenvolvendo tipos específicos de componentes de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="5eb94-127">Developing Specific Types of Data Flow Components</span></span>](../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)  
  
  
