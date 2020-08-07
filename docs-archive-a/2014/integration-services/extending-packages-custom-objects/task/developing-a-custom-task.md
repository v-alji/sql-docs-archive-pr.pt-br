---
title: Desenvolver uma tarefa personalizada | Microsoft Docs
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
- custom tasks [Integration Services], about custom tasks
- Task class
- custom tasks [Integration Services]
- SSIS custom tasks
- SSIS custom tasks, about custom tasks
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- tasks [Integration Services], custom
- TaskHost object
ms.assetid: dcbd8615-fa6d-4ddb-b8a5-0b19dddd6239
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d9d3446acff7ced73ab47014bec51708dba225b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575961"
---
# <a name="developing-a-custom-task"></a><span data-ttu-id="b6256-102">Desenvolvendo uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="b6256-102">Developing a Custom Task</span></span>
  <span data-ttu-id="b6256-103">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] usa tarefas para executar unidades de trabalho como suporte à extração, transformação e carregamento de dados.</span><span class="sxs-lookup"><span data-stu-id="b6256-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses tasks to perform units of work in support of the extraction, transformation, and loading of data.</span></span> <span data-ttu-id="b6256-104">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] inclui várias tarefas que executam as ações usadas mais frequentemente, da execução de uma instrução SQL ao download de um arquivo de um site de FTP.</span><span class="sxs-lookup"><span data-stu-id="b6256-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of tasks that perform the most frequently used actions, from executing an SQL statement to downloading a file from an FTP site.</span></span> <span data-ttu-id="b6256-105">Se as tarefas incluídas e as ações suportadas não satisfizerem seus requisitos completamente, você poderá criar uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="b6256-105">If the included tasks and supported actions do not completely meet your requirements, you can create a custom task.</span></span>  
  
 <span data-ttu-id="b6256-106">Para criar uma tarefa personalizada, é preciso criar uma classe que herde da classe base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), aplicar o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> em sua nova classe e substituir os métodos e as propriedades importantes da classe base, incluindo o método <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6256-106">To create a custom task, you have to create a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6256-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b6256-107">In This Section</span></span>  
 <span data-ttu-id="b6256-108">Esta seção descreve como criar, configurar e codificar uma tarefa personalizada e sua interface de usuário personalizada opcional.</span><span class="sxs-lookup"><span data-stu-id="b6256-108">This section describes how to create, configure, and code a custom task and its optional custom user interface.</span></span>  
  
 [<span data-ttu-id="b6256-109">Criar uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="b6256-109">Creating a Custom Task</span></span>](creating-a-custom-task.md)  
 <span data-ttu-id="b6256-110">Descreve a primeira etapa, que é criar a tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="b6256-110">Describes the first step, which is creating the custom task.</span></span>  
  
 [<span data-ttu-id="b6256-111">Codificar uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="b6256-111">Coding a Custom Task</span></span>](coding-a-custom-task.md)  
 <span data-ttu-id="b6256-112">Descreve como codificar os métodos principais de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="b6256-112">Describes how to code the principal methods of a custom task.</span></span>  
  
 [<span data-ttu-id="b6256-113">Conectar-se a fontes de dados em uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="b6256-113">Connecting to Data Sources in a Custom Task</span></span>](connecting-to-data-sources-in-a-custom-task.md)  
 <span data-ttu-id="b6256-114">Descreve como conectar uma tarefa personalizada a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b6256-114">Describes how to connect a custom task to a data source.</span></span>  
  
 [<span data-ttu-id="b6256-115">Gerar e definir eventos em uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="b6256-115">Raising and Defining Events in a Custom Task</span></span>](raising-and-defining-events-in-a-custom-task.md)  
 <span data-ttu-id="b6256-116">Descreve como gerar eventos e definir eventos personalizados da tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="b6256-116">Describes how to raise events and define custom events from the custom task.</span></span>  
  
 [<span data-ttu-id="b6256-117">Adicionar suporte para depuração em uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="b6256-117">Adding Support for Debugging in a Custom Task</span></span>](adding-support-for-debugging-in-a-custom-task.md)  
 <span data-ttu-id="b6256-118">Descreve como criar destinos de ponto de interrupção na tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="b6256-118">Describes how to create breakpoint targets in the custom task.</span></span>  
  
 [<span data-ttu-id="b6256-119">Desenvolver uma interface do usuário para uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="b6256-119">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
 <span data-ttu-id="b6256-120">Descreve como criar uma interface de usuário que seja exibida no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer para configurar propriedades na tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="b6256-120">Describes how to create a user interface that shows in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to configure properties on the custom task.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b6256-121">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="b6256-121">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="b6256-122">Informações comuns a todos os objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="b6256-122">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="b6256-123">Para obter informações comuns a todos os tipos de objetos personalizados que você pode criar no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="b6256-123">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="b6256-124">Desenvolvendo objetos personalizados para o Integration Services</span><span class="sxs-lookup"><span data-stu-id="b6256-124">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="b6256-125">Descreve as etapas básicas para implementar todos os tipos de objetos personalizados no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6256-125">Describes the basic steps in implementing all kinds of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="b6256-126">Persistência de objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="b6256-126">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="b6256-127">Descreve a persistência personalizada e explica quando ela é necessária.</span><span class="sxs-lookup"><span data-stu-id="b6256-127">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="b6256-128">Compilando, implantando e depurando objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="b6256-128">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="b6256-129">Descreve as técnicas para compilar, assinar, implantar e depurar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b6256-129">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="b6256-130">Informações sobre outros objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="b6256-130">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="b6256-131">Para obter informações sobre os outros tipos de objetos personalizados que você pode criar no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="b6256-131">For information about the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="b6256-132">Desenvolver um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="b6256-132">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="b6256-133">Aborda como programar gerenciadores de conexões personalizados.</span><span class="sxs-lookup"><span data-stu-id="b6256-133">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="b6256-134">Desenvolver um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="b6256-134">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="b6256-135">Aborda como programar provedores de log personalizados.</span><span class="sxs-lookup"><span data-stu-id="b6256-135">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="b6256-136">Desenvolver um enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="b6256-136">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="b6256-137">Aborda como programar enumeradores personalizados.</span><span class="sxs-lookup"><span data-stu-id="b6256-137">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="b6256-138">Desenvolver um componente de fluxo de dados personalizado</span><span class="sxs-lookup"><span data-stu-id="b6256-138">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="b6256-139">Aborda como programar origens, transformações e destinos de fluxos de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="b6256-139">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="b6256-140">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b6256-140">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b6256-141">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="b6256-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b6256-142">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="b6256-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b6256-143">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="b6256-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6256-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6256-144">See Also</span></span>  
 <span data-ttu-id="b6256-145">[Estender o pacote com a tarefa Script](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span><span class="sxs-lookup"><span data-stu-id="b6256-145">[Extending the Package with the Script Task](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span></span>  
 [<span data-ttu-id="b6256-146">Comparar soluções de script e objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="b6256-146">Comparing Scripting Solutions and Custom Objects</span></span>](../../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)  
  
  
