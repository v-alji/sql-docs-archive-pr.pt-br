---
title: Guia do desenvolvedor&#39;s (Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services, programming
- SSIS, programming
- SQL Server Integration Services, programming
- packages [Integration Services], programming
ms.assetid: 60fe148b-a7c4-4289-ae3e-2e949fc1886c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c16ec1a21cf7ebb711f6d3996eb6239ea052c83c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582003"
---
# <a name="developer39s-guide-integration-services"></a><span data-ttu-id="a2604-102">Guia do desenvolvedor&#39;s (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="a2604-102">Developer&#39;s Guide (Integration Services)</span></span>
  <span data-ttu-id="a2604-103">O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] inclui um modelo de objeto totalmente reescrito, que foi aprimorado com vários recursos que tornam a extensão e a programação mais fáceis, flexíveis e eficientes.</span><span class="sxs-lookup"><span data-stu-id="a2604-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes a completely rewritten object model, which has been enhanced with many features that make extending and programming packages easier, more flexible, and more powerful.</span></span> <span data-ttu-id="a2604-104">Desenvolvedores podem estender e programar quase todos os aspectos de pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2604-104">Developers can extend and program almost every aspect of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="a2604-105">Como desenvolvedor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], há duas abordagens fundamentais que você pode adotar na programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a2604-105">As an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] developer, there are two fundamental approaches that you can take to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming:</span></span>  
  
-   <span data-ttu-id="a2604-106">Você pode estender pacotes escrevendo componentes que são disponibilizados dentro do Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] para fornecer funcionalidade personalizada em um pacote.</span><span class="sxs-lookup"><span data-stu-id="a2604-106">You can extend packages by writing components that become available within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to provide custom functionality in a package.</span></span>  
  
-   <span data-ttu-id="a2604-107">Você pode criar, configurar e executar pacotes programaticamente a partir de seus próprios aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a2604-107">You can create, configure, and run packages programmatically from your own applications.</span></span>  
  
 <span data-ttu-id="a2604-108">Se você considerar que os componentes internos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] não atendem aos seus requisitos, você poderá ampliar a capacidade do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] codificando suas próprias extensões.</span><span class="sxs-lookup"><span data-stu-id="a2604-108">If you find that the built-in components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="a2604-109">Nessa abordagem, você tem duas opções distintas:</span><span class="sxs-lookup"><span data-stu-id="a2604-109">In this approach, you have two discrete options:</span></span>  
  
-   <span data-ttu-id="a2604-110">Para uso ad hoc em um único pacote, você pode criar uma tarefa personalizada, escrevendo código na tarefa Script, ou um componente de fluxo de dados personalizado, escrevendo código no componente Script, que pode ser configurado como uma origem, transformação ou destino.</span><span class="sxs-lookup"><span data-stu-id="a2604-110">For ad hoc use in a single package, you can create a custom task by writing code in the Script task, or a custom data flow component by writing code in the Script component, which you can configure as a source, transformation, or destination.</span></span> <span data-ttu-id="a2604-111">Esses wrappers avançados escrevem o código de infraestrutura para você e permitem focar exclusivamente o desenvolvimento da sua funcionalidade personalizada; entretanto, não é fácil reutilizá-los em outros locais.</span><span class="sxs-lookup"><span data-stu-id="a2604-111">These powerful wrappers write the infrastructure code for you and let you focus exclusively on developing your custom functionality; however, they are not easily reusable elsewhere.</span></span>  
  
-   <span data-ttu-id="a2604-112">Para permitir o uso em vários pacotes, você pode criar extensões personalizadas do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tais como gerenciadores de conexões, tarefas, enumeradores, provedores de log e componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a2604-112">For use in multiple packages, you can create custom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] extensions such as connection managers, tasks, enumerators, log providers, and data flow components.</span></span> <span data-ttu-id="a2604-113">O modelo de objeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gerenciado contém classes base que fornecem um ponto de partida e facilitam ainda mais o desenvolvimento de extensões personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a2604-113">The managed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model contains base classes that provide a starting point and make developing custom extensions easier than ever.</span></span>  
  
 <span data-ttu-id="a2604-114">Se desejar criar pacotes dinamicamente, ou gerenciar e executar pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fora do ambiente de desenvolvimento, você poderá manipular pacotes programaticamente.</span><span class="sxs-lookup"><span data-stu-id="a2604-114">If you want to create packages dynamically, or to manage and run [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages outside the development environment, you can manipulate packages programmatically.</span></span> <span data-ttu-id="a2604-115">Você pode carregar, modificar e executar pacotes existentes, ou criar e executar pacotes inteiramente novos programaticamente.</span><span class="sxs-lookup"><span data-stu-id="a2604-115">You can load, modify, and run existing packages, or you can create and run entirely new packages programmatically.</span></span> <span data-ttu-id="a2604-116">Nessa abordagem, você tem uma série de opções:</span><span class="sxs-lookup"><span data-stu-id="a2604-116">In this approach, you have a continuous range of options:</span></span>  
  
-   <span data-ttu-id="a2604-117">Carregar e executar um pacote existente sem modificação.</span><span class="sxs-lookup"><span data-stu-id="a2604-117">Load and run an existing package without modification.</span></span>  
  
-   <span data-ttu-id="a2604-118">Carregue um pacote existente, reconfigure-o (por exemplo, especifique outra fonte de dados) e execute-o.</span><span class="sxs-lookup"><span data-stu-id="a2604-118">Load an existing package, reconfigure it (for example, specify a different data source), and run it.</span></span>  
  
-   <span data-ttu-id="a2604-119">Crie um pacote novo, adicione e configure componentes, fazendo alterações em cada objeto e em cada propriedade, salve-o e, depois, execute-o.</span><span class="sxs-lookup"><span data-stu-id="a2604-119">Create a new package, add and configure components, making changes object by object and property by property, save it, and then run it.</span></span>  
  
 <span data-ttu-id="a2604-120">Essas abordagens da programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] são descritas nessa seção e demonstradas através de exemplos.</span><span class="sxs-lookup"><span data-stu-id="a2604-120">These approaches to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming are described in this section and demonstrated with examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2604-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a2604-121">In This Section</span></span>  
 [<span data-ttu-id="a2604-122">Visão geral da programação do Integration Services</span><span class="sxs-lookup"><span data-stu-id="a2604-122">Integration Services Programming Overview</span></span>](integration-services-programming-overview.md)  
 <span data-ttu-id="a2604-123">Descreve as funções de fluxo de controle e fluxo de dados no desenvolvimento do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2604-123">Describes the roles of control flow and data flow in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] development.</span></span>  
  
 [<span data-ttu-id="a2604-124">Compreendendo as transformações síncronas e assíncronas</span><span class="sxs-lookup"><span data-stu-id="a2604-124">Understanding Synchronous and Asynchronous Transformations</span></span>](understanding-synchronous-and-asynchronous-transformations.md)  
 <span data-ttu-id="a2604-125">Descreve a diferença importante entre saídas síncronas e assíncronas e os componentes que usam essas saídas no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="a2604-125">Describes the important distinction between synchronous and asynchronous outputs and the components that use them in the data flow.</span></span>  
  
 [<span data-ttu-id="a2604-126">Trabalhando programaticamente com gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="a2604-126">Working with Connection Managers Programmatically</span></span>](working-with-connection-managers-programmatically.md)  
 <span data-ttu-id="a2604-127">Lista os gerenciadores de conexões que você pode usar a partir do código gerenciado e os valores que os gerenciadores de conexões retornam quando o código chama o método `AcquireConnection`.</span><span class="sxs-lookup"><span data-stu-id="a2604-127">Lists the connection managers that you can use from managed code, and the values that the connection managers return when the code calls the `AcquireConnection` method.</span></span>  
  
 [<span data-ttu-id="a2604-128">Estender pacotes com scripts</span><span class="sxs-lookup"><span data-stu-id="a2604-128">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="a2604-129">Descreve como estender o fluxo de controle por meio da tarefa Script ou o fluxo de dados por meio do componente Script.</span><span class="sxs-lookup"><span data-stu-id="a2604-129">Describes how to extend the control flow by using the Script task, or the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="a2604-130">Estendendo pacotes com objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="a2604-130">Extending Packages with Custom Objects</span></span>](extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 <span data-ttu-id="a2604-131">Descreve como criar e programar tarefas personalizadas, componentes de fluxo de dados e outros objetos de pacote para uso em vários pacotes.</span><span class="sxs-lookup"><span data-stu-id="a2604-131">Describes how to create and program custom tasks, data flow components, and other package objects for use in multiple packages.</span></span>  
  
 [<span data-ttu-id="a2604-132">Compilar Pacotes Programaticamente</span><span class="sxs-lookup"><span data-stu-id="a2604-132">Building Packages Programmatically</span></span>](building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="a2604-133">Descreve como criar, configurar e salvar pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programaticamente.</span><span class="sxs-lookup"><span data-stu-id="a2604-133">Describes how to create, configure, and save [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
 [<span data-ttu-id="a2604-134">Executar e gerenciar pacotes programaticamente</span><span class="sxs-lookup"><span data-stu-id="a2604-134">Running and Managing Packages Programmatically</span></span>](run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 <span data-ttu-id="a2604-135">Descreve como enumerar, executar e gerenciar pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programaticamente.</span><span class="sxs-lookup"><span data-stu-id="a2604-135">Describes how to enumerate, run, and manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a2604-136">Referência</span><span class="sxs-lookup"><span data-stu-id="a2604-136">Reference</span></span>  
 [<span data-ttu-id="a2604-137">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="a2604-137">Integration Services Error and Message Reference</span></span>](integration-services-error-and-message-reference.md)  
 <span data-ttu-id="a2604-138">Lista os códigos de erro predefinidos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] acompanhados de seus nomes simbólicos e descrições.</span><span class="sxs-lookup"><span data-stu-id="a2604-138">Lists the predefined [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error codes, together with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a2604-139">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="a2604-139">Related Sections</span></span>  
 [<span data-ttu-id="a2604-140">Ferramentas de solução de problemas para desenvolvimento de pacotes</span><span class="sxs-lookup"><span data-stu-id="a2604-140">Troubleshooting Tools for Package Development</span></span>](troubleshooting/troubleshooting-tools-for-package-development.md)  
 <span data-ttu-id="a2604-141">Descreve os recursos e as ferramentas que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fornece para solucionar problemas de pacotes durante o desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="a2604-141">Describes the features and tools that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides for troubleshooting packages during development.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="a2604-142">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="a2604-142">External Resources</span></span>  
  
-   <span data-ttu-id="a2604-143">Exemplos do CodePlex, [Exemplos de Produtos do Integration Services](https://go.microsoft.com/fwlink/?LinkID=131204), em www.codeplex.com/MSFTISProdSamples</span><span class="sxs-lookup"><span data-stu-id="a2604-143">CodePlex samples, [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204), on www.codeplex.com/MSFTISProdSamples</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2604-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2604-144">See Also</span></span>  
 [<span data-ttu-id="a2604-145">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="a2604-145">SQL Server Integration Services</span></span>](sql-server-integration-services.md)  
  
  
