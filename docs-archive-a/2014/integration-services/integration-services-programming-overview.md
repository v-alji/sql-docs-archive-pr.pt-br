---
title: Visão geral da programação do Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 11/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services, programming
- architecture [Integration Services]
- assemblies [Integration Services]
- SSIS, programming
- SQL Server Integration Services, programming
- run-time engine [Integration Services]
- packages [Integration Services], programming
- data flow engine [Integration Services]
- languages [Integration Services]
ms.assetid: 262babc6-eea5-4609-bc65-07d64cbcfee9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d9dc548b2987f068f579f053a6b2d205186b416e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574177"
---
# <a name="integration-services-programming-overview"></a><span data-ttu-id="ab366-102">Visão geral da programação do Integration Services</span><span class="sxs-lookup"><span data-stu-id="ab366-102">Integration Services Programming Overview</span></span>
  <span data-ttu-id="ab366-103">O [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tem uma arquitetura que separa a movimentação e a transformação de dados de gerenciamento e fluxos de controle de pacotes.</span><span class="sxs-lookup"><span data-stu-id="ab366-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] has an architecture that separates data movement and transformation from package control flow and management.</span></span> <span data-ttu-id="ab366-104">Há dois mecanismos distintos que definem essa arquitetura e isso pode ser automatizado e estendido na programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab366-104">There are two distinct engines that define this architecture and that can be automated and extended when programming [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="ab366-105">O mecanismo de tempo de execução implementa a infraestrutura de gerenciamento de fluxos de controle e pacotes que permite aos desenvolvedores controlar o fluxo de execução e definir opções para registro de log, manipuladores de eventos e variáveis.</span><span class="sxs-lookup"><span data-stu-id="ab366-105">The run-time engine implements the control flow and package management infrastructure that lets developers control the flow of execution and set options for logging, event handlers, and variables.</span></span> <span data-ttu-id="ab366-106">O mecanismo de fluxo de dados é um mecanismo de desempenho alto, especializado, dedicado exclusivamente a extrair, transformar e carregar dados.</span><span class="sxs-lookup"><span data-stu-id="ab366-106">The data flow engine is a specialized, high performance engine that is exclusively dedicated to extracting, transforming, and loading data.</span></span> <span data-ttu-id="ab366-107">Sua programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] se baseará nesses dois mecanismos.</span><span class="sxs-lookup"><span data-stu-id="ab366-107">When programming [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], you will be programming against these two engines.</span></span>  
  
 <span data-ttu-id="ab366-108">A imagem a seguir descreve a arquitetura do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab366-108">The following image depicts the architecture of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ab366-109">![Arquitetura do Integration Services](media/mw-dts-01.gif "Arquitetura do Integration Services")</span><span class="sxs-lookup"><span data-stu-id="ab366-109">![Integration Services architecture](media/mw-dts-01.gif "Integration Services architecture")</span></span>  
  
## <a name="integration-services-run-time-engine"></a><span data-ttu-id="ab366-110">Mecanismo de tempo de execução do Integration Services</span><span class="sxs-lookup"><span data-stu-id="ab366-110">Integration Services Run-time Engine</span></span>  
 <span data-ttu-id="ab366-111">O mecanismo de tempo de execução do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] controla o gerenciamento e a execução de pacotes, implementando a infraestrutura que habilita a ordem de execução, o registro em log, variáveis e a manipulação de eventos.</span><span class="sxs-lookup"><span data-stu-id="ab366-111">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] run-time engine controls the management and execution of packages, by implementing the infrastructure that enables execution order, logging, variables, and event handling.</span></span> <span data-ttu-id="ab366-112">A programação do mecanismo de tempo de execução do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] permite que os desenvolvedores automatizem a criação, a configuração e a execução de pacotes e criem tarefas personalizadas e outras extensões.</span><span class="sxs-lookup"><span data-stu-id="ab366-112">Programming the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] run-time engine lets developers automate the creation, configuration, and execution of packages and create custom tasks and other extensions.</span></span>  
  
 <span data-ttu-id="ab366-113">Para obter mais informações, consulte [Estender o pacote com a tarefa Script](extending-packages-scripting/task/extending-the-package-with-the-script-task.md), [Desenvolver uma tarefa personalizada](extending-packages-custom-objects/task/developing-a-custom-task.md) e [Compilar pacotes programaticamente](building-packages-programmatically/building-packages-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="ab366-113">For more information, see [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md), [Developing a Custom Task](extending-packages-custom-objects/task/developing-a-custom-task.md), and [Building Packages Programmatically](building-packages-programmatically/building-packages-programmatically.md).</span></span>  
  
## <a name="integration-services-data-flow-engine"></a><span data-ttu-id="ab366-114">Mecanismo de fluxo de dados do Integration Services</span><span class="sxs-lookup"><span data-stu-id="ab366-114">Integration Services Data Flow Engine</span></span>  
 <span data-ttu-id="ab366-115">O mecanismo de fluxo de dados gerencia a tarefa de fluxo de dados, que é especializada, de alto desempenho, dedicada à movimentação e transformação de dados de origens distintas.</span><span class="sxs-lookup"><span data-stu-id="ab366-115">The data flow engine manages the data flow task, which is a specialized, high performance task dedicated to moving and transforming data from disparate sources.</span></span> <span data-ttu-id="ab366-116">Diferente de outras tarefas, a tarefa de fluxo de dados contém objetos adicionais chamados de componentes de fluxo de dados, que podem ser origens, transformações ou destinos.</span><span class="sxs-lookup"><span data-stu-id="ab366-116">Unlike other tasks, the data flow task contains additional objects called data flow components, which can be sources, transformations, or destinations.</span></span> <span data-ttu-id="ab366-117">Esses componentes são as principais partes de movimentação da tarefa.</span><span class="sxs-lookup"><span data-stu-id="ab366-117">These components are the core moving parts of the task.</span></span> <span data-ttu-id="ab366-118">Eles definem a movimentação e a transformação de dados.</span><span class="sxs-lookup"><span data-stu-id="ab366-118">They define the movement and transformation of data.</span></span> <span data-ttu-id="ab366-119">A programação do mecanismo de fluxo de dados permite que desenvolvedores automatizem a criação e a configuração dos componentes em uma tarefa de fluxo de dados e criem componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="ab366-119">Programming the data flow engine lets developers automate the creation and configuration of the components in a data flow task, and create custom components.</span></span>  
  
 <span data-ttu-id="ab366-120">Para obter mais informações, consulte [estendendo o fluxo de dados com o componente Script] (estendendo-Packages-scripting/data-Flow-script-Component/estendendo-The-data-Flow-com-The-script-Component. MD, [desenvolvendo um componente de fluxo de dados personalizado](extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md)e [compilando pacotes programaticamente](building-packages-programmatically/building-packages-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="ab366-120">For more information, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md, [Developing a Custom Data Flow Component](extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), and [Building Packages Programmatically](building-packages-programmatically/building-packages-programmatically.md).</span></span>  
  
## <a name="supported-languages"></a><span data-ttu-id="ab366-121">Idiomas com suporte</span><span class="sxs-lookup"><span data-stu-id="ab366-121">Supported Languages</span></span>  
 <span data-ttu-id="ab366-122">O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] é totalmente compatível com o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab366-122">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fully supports the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="ab366-123">Isso permite que desenvolvedores programem o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ao escolherem idiomas compatíveis com .NET.</span><span class="sxs-lookup"><span data-stu-id="ab366-123">This lets developers program [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in their choice of .NET-compliant languages.</span></span> <span data-ttu-id="ab366-124">Embora o mecanismo de tempo de execução e o mecanismo de fluxo de dados sejam escritos em código nativo, ambos estão disponíveis através de um modelo de objeto totalmente gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ab366-124">Although both the run-time engine and the data flow engine are written in native code, they are both available through a fully managed object model.</span></span>  
  
 <span data-ttu-id="ab366-125">Você pode programar pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], tarefas personalizadas e componentes no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ou em outro editor de código ou de texto.</span><span class="sxs-lookup"><span data-stu-id="ab366-125">You can program [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages, custom tasks, and components in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] or in another code or text editor.</span></span> <span data-ttu-id="ab366-126">O [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] oferece ao desenvolvedor muitas ferramentas e recursos para simplificar e acelerar os ciclos iterativos de codificação, depuração e teste.</span><span class="sxs-lookup"><span data-stu-id="ab366-126">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] offers the developer many tools and features to simplify and accelerate the iterative cycles of coding, debugging, and testing.</span></span> <span data-ttu-id="ab366-127">O [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] também facilita a implantação.</span><span class="sxs-lookup"><span data-stu-id="ab366-127">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] also makes deployment easier.</span></span> <span data-ttu-id="ab366-128">Porém, você não precisa do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] para compilar e criar projetos de código do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab366-128">However, you do not need [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] to compile and build [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] code projects.</span></span> <span data-ttu-id="ab366-129">O SDK do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] inclui os compiladores [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] e [!INCLUDE[csprcs](../includes/csprcs-md.md)] e as ferramentas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="ab366-129">The [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] SDK includes the [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] and [!INCLUDE[csprcs](../includes/csprcs-md.md)] compilers and related tools.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ab366-130">Por padrão, o [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] é instalado com o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mas não com o SDK de [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ab366-130">By default, the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] is installed with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] SDK is not.</span></span> <span data-ttu-id="ab366-131">A menos que o SDK esteja instalado no computador e a documentação do SDK esteja incluída na coleção de manuais online, os links para o conteúdo do SDK desta seção não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="ab366-131">Unless the SDK is installed on the computer and the SDK documentation is included in the Books Online collection, links to SDK content in this section will not work.</span></span> <span data-ttu-id="ab366-132">Depois de instalar o SDK do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], você pode adicionar a documentação do SDK à coleção de Manuais Online e ao sumário seguindo as instruções fornecidas em [Adicionar ou remover a documentação do produto do SQL Server](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="ab366-132">After you have installed the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] SDK, you can add the SDK documentation to the Books Online collection and table of contents by following the instructions in [Add or Remove Product Documentation for SQL Server](../index.yml).</span></span>  
  
 <span data-ttu-id="ab366-133">A tarefa e o componente Script do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] usam o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] VSTA (Tools for Applications) como um ambiente de script inserido.</span><span class="sxs-lookup"><span data-stu-id="ab366-133">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Script task and Script component use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) as an embedded scripting environment.</span></span> <span data-ttu-id="ab366-134">O VSTA dá suporte ao [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic e ao [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="ab366-134">VSTA supports [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic and [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab366-135">As interfaces de programação de aplicativo [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] são incompatíveis com as linguagens de scripts baseadas em COM, como VBScript.</span><span class="sxs-lookup"><span data-stu-id="ab366-135">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] application programming interfaces are incompatible with COM-based scripting languages such as VBScript.</span></span>  
  
## <a name="locating-assemblies"></a><span data-ttu-id="ab366-136">Localizando assemblies</span><span class="sxs-lookup"><span data-stu-id="ab366-136">Locating Assemblies</span></span>  
 <span data-ttu-id="ab366-137">No [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], os assemblies do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] foram atualizados para o .NET 4.0.</span><span class="sxs-lookup"><span data-stu-id="ab366-137">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] assemblies were upgraded to .NET 4.0.</span></span> <span data-ttu-id="ab366-138">Há um cache de assembly global separado para o .NET 4, localizado em *\<drive>* :\Windows\Microsoft.NET\assembly.</span><span class="sxs-lookup"><span data-stu-id="ab366-138">There is a separate global assembly cache for .NET 4, located in *\<drive>*:\Windows\Microsoft.NET\assembly.</span></span> <span data-ttu-id="ab366-139">Você pode localizar todos os assemblies do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nesse caminho, normalmente na pasta GAC_MSIL.</span><span class="sxs-lookup"><span data-stu-id="ab366-139">You can find all of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] assemblies under this path, usually in the GAC_MSIL folder.</span></span>  
  
 <span data-ttu-id="ab366-140">Assim como nas versões anteriores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], os principais arquivos .dll de extensibilidade do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] também ficam em *\<drive>* :\Arquivos de Programas\Microsoft SQL Server\100\SDK\Assemblies.</span><span class="sxs-lookup"><span data-stu-id="ab366-140">As in previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], the core [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] extensibility .dll files are also located at *\<drive>*:\Program Files\Microsoft SQL Server\100\SDK\Assemblies.</span></span>  
  
## <a name="commonly-used-assemblies"></a><span data-ttu-id="ab366-141">Assemblies comumente usados</span><span class="sxs-lookup"><span data-stu-id="ab366-141">Commonly Used Assemblies</span></span>  
 <span data-ttu-id="ab366-142">A tabela a seguir lista os assemblies usados com frequência durante a programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] através do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab366-142">The following table lists the assemblies that are frequently used when programming [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] using the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span></span>  
  
|<span data-ttu-id="ab366-143">Assembly</span><span class="sxs-lookup"><span data-stu-id="ab366-143">Assembly</span></span>|<span data-ttu-id="ab366-144">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ab366-144">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ab366-145">Microsoft.SqlServer.ManagedDTS.dll</span><span class="sxs-lookup"><span data-stu-id="ab366-145">Microsoft.SqlServer.ManagedDTS.dll</span></span>|<span data-ttu-id="ab366-146">Contém o mecanismo de tempo de execução gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ab366-146">Contains the managed run-time engine.</span></span>|  
|<span data-ttu-id="ab366-147">Microsoft.SqlServer.RuntimeWrapper.dll</span><span class="sxs-lookup"><span data-stu-id="ab366-147">Microsoft.SqlServer.RuntimeWrapper.dll</span></span>|<span data-ttu-id="ab366-148">Contém o assembly de interoperabilidade primária (PIA), ou wrapper, para o mecanismo de tempo de execução nativo.</span><span class="sxs-lookup"><span data-stu-id="ab366-148">Contains the primary interop assembly (PIA), or wrapper, for the native run-time engine.</span></span>|  
|<span data-ttu-id="ab366-149">Microsoft.SqlServer.PipelineHost.dll</span><span class="sxs-lookup"><span data-stu-id="ab366-149">Microsoft.SqlServer.PipelineHost.dll</span></span>|<span data-ttu-id="ab366-150">Contém o mecanismo de fluxo de dados gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ab366-150">Contains the managed data flow engine.</span></span>|  
|<span data-ttu-id="ab366-151">Microsoft.SqlServer.PipelineWrapper.dll</span><span class="sxs-lookup"><span data-stu-id="ab366-151">Microsoft.SqlServer.PipelineWrapper.dll</span></span>|<span data-ttu-id="ab366-152">Contém o assembly de interoperabilidade primária (PIA), ou wrapper, para o mecanismo de fluxo de dados nativo.</span><span class="sxs-lookup"><span data-stu-id="ab366-152">Contains the primary interop assembly (PIA), or wrapper, for the native data flow engine.</span></span>|  

<span data-ttu-id="ab366-153">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ab366-153">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ab366-154">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="ab366-154">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ab366-155">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="ab366-155">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ab366-156">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="ab366-156">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  