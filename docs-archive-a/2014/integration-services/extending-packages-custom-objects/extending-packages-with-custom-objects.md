---
title: Estendendo pacotes com objetos personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
ms.assetid: 26616eb8-9e80-434d-b22a-ece1b00f449d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0159983f518e51aa082ea23745663e7f09eee1fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678260"
---
# <a name="extending-packages-with-custom-objects"></a><span data-ttu-id="c0a48-102">Estendendo pacotes com objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="c0a48-102">Extending Packages with Custom Objects</span></span>
  <span data-ttu-id="c0a48-103">Se os componentes fornecidos no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] não atenderem às suas necessidades, você poderá ampliar a capacidade do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] com a codificação de suas próprias extensões.</span><span class="sxs-lookup"><span data-stu-id="c0a48-103">If you find that the components provided in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="c0a48-104">Há duas opções distintas para estender seus pacotes: você pode escrever código dentro dos wrappers avançados fornecidos pela tarefa e o componente Script, ou pode criar extensões personalizadas do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a partir do zero com a derivação das classes base fornecidas pelo modelo de objeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0a48-104">You have two discrete options for extending your packages: you can write code within the powerful wrappers provided by the Script task and the Script component, or you can create custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] extensions from scratch by deriving from the base classes provided by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model.</span></span>  
  
 <span data-ttu-id="c0a48-105">Essa seção explora a opção mais avançada – extensão de pacotes com objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="c0a48-105">This section explores the more advanced of the two options - extending packages with custom objects.</span></span>  
  
 <span data-ttu-id="c0a48-106">Quando sua solução personalizada do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] necessita de maior flexibilidade do que a tarefa Script e o componente Script oferecem, ou quando você necessita de um componente que possa ser reutilizado em vários pacotes, o modelo de objeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] possibilita a criação de tarefas personalizadas, componentes de fluxo de dados e outros objetos de pacote em código gerenciado do início ao fim.</span><span class="sxs-lookup"><span data-stu-id="c0a48-106">When your custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solution requires more flexibility than the Script task and the Script component provide, or when you need a component that you can reuse in multiple packages, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model lets you build custom tasks, data flow components, and other package objects in managed code from the ground up.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0a48-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c0a48-107">In This Section</span></span>  
 [<span data-ttu-id="c0a48-108">Desenvolvendo objetos personalizados para o Integration Services</span><span class="sxs-lookup"><span data-stu-id="c0a48-108">Developing Custom Objects for Integration Services</span></span>](developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="c0a48-109">Aborda os objetos personalizados que podem ser criados no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e resume as etapas e configurações essenciais.</span><span class="sxs-lookup"><span data-stu-id="c0a48-109">Discusses the custom objects that can be created for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and summarizes the essential steps and settings.</span></span>  
  
 [<span data-ttu-id="c0a48-110">Persistência de objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="c0a48-110">Persisting Custom Objects</span></span>](persisting-custom-objects.md)  
 <span data-ttu-id="c0a48-111">Discute a persistência padrão de objetos personalizados e o processo de implementação da persistência personalizada.</span><span class="sxs-lookup"><span data-stu-id="c0a48-111">Discusses the default persistence of custom objects, and the process of implementing custom persistence.</span></span>  
  
 [<span data-ttu-id="c0a48-112">Compilando, implantando e depurando objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="c0a48-112">Building, Deploying, and Debugging Custom Objects</span></span>](building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="c0a48-113">Discute as abordagens comuns para criar, implantar e testar os diversos tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="c0a48-113">Discusses the common approaches to building, deploying and testing the various types of custom objects.</span></span>  
  
 [<span data-ttu-id="c0a48-114">Desenvolver uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="c0a48-114">Developing a Custom Task</span></span>](task/developing-a-custom-task.md)  
 <span data-ttu-id="c0a48-115">Descreve o processo de codificação de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="c0a48-115">Describes the process of coding a custom task.</span></span>  
  
 [<span data-ttu-id="c0a48-116">Desenvolver um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="c0a48-116">Developing a Custom Connection Manager</span></span>](connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="c0a48-117">Descreve o processo de codificação de um gerenciador de conexões personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0a48-117">Describes the process of coding a custom connection manager.</span></span>  
  
 [<span data-ttu-id="c0a48-118">Desenvolver um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="c0a48-118">Developing a Custom Log Provider</span></span>](log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="c0a48-119">Descreve o processo de codificação de um provedor de logs personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0a48-119">Describes the process of coding a custom log provider.</span></span>  
  
 [<span data-ttu-id="c0a48-120">Desenvolver um enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="c0a48-120">Developing a Custom ForEach Enumerator</span></span>](foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="c0a48-121">Descreve o processo de codificação de um enumerador personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0a48-121">Describes the process of coding a custom enumerator.</span></span>  
  
 [<span data-ttu-id="c0a48-122">Desenvolver um componente de fluxo de dados personalizado</span><span class="sxs-lookup"><span data-stu-id="c0a48-122">Developing a Custom Data Flow Component</span></span>](data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="c0a48-123">Aborda como programar origens, transformações e destinos de fluxos de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="c0a48-123">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c0a48-124">Referência</span><span class="sxs-lookup"><span data-stu-id="c0a48-124">Reference</span></span>  
 [<span data-ttu-id="c0a48-125">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="c0a48-125">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
 <span data-ttu-id="c0a48-126">Lista os códigos de erro predefinidos do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] com seus nomes simbólicos e descrições.</span><span class="sxs-lookup"><span data-stu-id="c0a48-126">Lists the predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error codes with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c0a48-127">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="c0a48-127">Related Sections</span></span>  
 [<span data-ttu-id="c0a48-128">Estender pacotes com scripts</span><span class="sxs-lookup"><span data-stu-id="c0a48-128">Extending Packages with Scripting</span></span>](../extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="c0a48-129">Discute como estender o fluxo de controle usando a tarefa Script ou estender o fluxo de dados usando o componente Script.</span><span class="sxs-lookup"><span data-stu-id="c0a48-129">Discusses how to extend the control flow by using the Script task, or extend the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="c0a48-130">Compilar Pacotes Programaticamente</span><span class="sxs-lookup"><span data-stu-id="c0a48-130">Building Packages Programmatically</span></span>](../building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="c0a48-131">Descreve como criar, configurar, executar, carregar, salvar e gerenciar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] programaticamente.</span><span class="sxs-lookup"><span data-stu-id="c0a48-131">Describes how to create, configure, run, load, save, and manage [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
<span data-ttu-id="c0a48-132">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c0a48-132">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c0a48-133">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="c0a48-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c0a48-134">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="c0a48-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c0a48-135">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="c0a48-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0a48-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0a48-136">See Also</span></span>  
 <span data-ttu-id="c0a48-137">[Comparando soluções de script e objetos personalizados](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="c0a48-137">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="c0a48-138">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="c0a48-138">SQL Server Integration Services</span></span>](../sql-server-integration-services.md)  
  
  
