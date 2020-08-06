---
title: Desenvolver um gerenciador de conexões personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], connections
- custom connection managers [Integration Services], about custom connection managers
- connection managers [Integration Services], custom
- Integration Services packages, connection managers
- SSIS packages, connection managers
- SQL Server Integration Services packages, connection managers
- custom connection managers [Integration Services]
ms.assetid: bda0b29e-57f5-4879-b04d-1396dc56daa8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19c5a9066db6542742537a41a7f567d1b4b1d23d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685848"
---
# <a name="developing-a-custom-connection-manager"></a><span data-ttu-id="e4965-102">Desenvolvendo um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="e4965-102">Developing a Custom Connection Manager</span></span>
  <span data-ttu-id="e4965-103">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] usa gerenciadores de conexões para encapsular as informações necessárias para conexão a uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="e4965-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses connection managers to encapsulate the information needed to connect to an external data source.</span></span> <span data-ttu-id="e4965-104">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] inclui vários gerenciadores de conexões que dão suporte a conexões às fontes de dados usadas mais comumente, de bancos de dados corporativos a arquivos de texto e planilhas do Excel.</span><span class="sxs-lookup"><span data-stu-id="e4965-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of connection managers that support connections to the most commonly used data sources, from enterprise databases to text files and Excel worksheets.</span></span> <span data-ttu-id="e4965-105">Se os gerenciadores de conexões e as fontes de dados externas suportadas pelo [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] não satisfizerem totalmente os seus requisitos, você pode criar um gerenciador de conexões personalizado.</span><span class="sxs-lookup"><span data-stu-id="e4965-105">If the connection managers and external data sources supported by [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] do not entirely meet your requirements, you can create a custom connection manager.</span></span>  
  
 <span data-ttu-id="e4965-106">Para criar um gerenciador de conexões personalizado, é preciso criar uma classe que herde da classe base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, aplicar o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> a sua nova classe e substituir os métodos e as propriedades importantes da classe base, incluindo a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> e o método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4965-106">To create a custom connection manager, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e4965-107">A maioria das tarefas, fontes e destinos incluídos no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] funcionam somente com tipos específicos de gerenciadores de conexões internos.</span><span class="sxs-lookup"><span data-stu-id="e4965-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="e4965-108">Antes de desenvolver um gerenciador de conexões personalizado para ser usado com tarefas e componentes internos, verifique se esses componentes restringem a lista de gerenciadores de conexões disponíveis para os de tipo específico.</span><span class="sxs-lookup"><span data-stu-id="e4965-108">Before developing a custom connection manager for use with built-in tasks and components, check whether those components restrict the list of available connection managers to those of a specific type.</span></span> <span data-ttu-id="e4965-109">Se sua solução precisar de um gerenciador de conexões personalizado, é possível que você também tenha que desenvolver uma tarefa personalizada ou uma origem ou destino personalizado, para uso com o gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="e4965-109">If your solution requires a custom connection manager, you might also have to develop a custom task, or a custom source or destination, for use with the connection manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4965-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e4965-110">In This Section</span></span>  
 <span data-ttu-id="e4965-111">Esta seção descreve como criar, configurar e codificar um gerenciador de conexões personalizado e sua interface de usuário personalizada opcional.</span><span class="sxs-lookup"><span data-stu-id="e4965-111">This section describes how to create, configure, and code a custom connection manager and its optional custom user interface.</span></span> <span data-ttu-id="e4965-112">Os snippets de códigos mostrados nesta seção foram retirados do exemplo de Gerenciador de Conexões Personalizado do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4965-112">The code snippets shown in this section are drawn from the Sql Server Custom Connection Manager Sample.</span></span>  
  
 [<span data-ttu-id="e4965-113">Criar um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="e4965-113">Creating a Custom Connection Manager</span></span>](creating-a-custom-connection-manager.md)  
 <span data-ttu-id="e4965-114">Descreve como criar as classes para um projeto de gerenciador de conexões personalizado.</span><span class="sxs-lookup"><span data-stu-id="e4965-114">Describes how to create the classes for a custom connection manager project.</span></span>  
  
 [<span data-ttu-id="e4965-115">Codificar um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="e4965-115">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
 <span data-ttu-id="e4965-116">Descreve como implementar um gerenciador de conexões personalizado anulando os métodos e propriedades da classe base.</span><span class="sxs-lookup"><span data-stu-id="e4965-116">Describes how to implement a custom connection manager by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="e4965-117">Desenvolver uma interface do usuário para um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="e4965-117">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
 <span data-ttu-id="e4965-118">Descreve como implementar a classe de interface de usuário e o formulário usado para configurar o gerenciador de conexões personalizado.</span><span class="sxs-lookup"><span data-stu-id="e4965-118">Describes how to implement the user interface class and the form that is used to configure the custom connection manager.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e4965-119">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="e4965-119">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="e4965-120">Informações comuns a todos os objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="e4965-120">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="e4965-121">Para obter informações comuns a todos os tipos de objetos personalizados que você pode criar no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e4965-121">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="e4965-122">Desenvolvendo objetos personalizados para o Integration Services</span><span class="sxs-lookup"><span data-stu-id="e4965-122">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="e4965-123">Descreve as etapas básicas para implementar todos os tipos de objetos personalizados para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4965-123">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="e4965-124">Persistência de objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="e4965-124">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="e4965-125">Descreve a persistência personalizada e explica quando ela é necessária.</span><span class="sxs-lookup"><span data-stu-id="e4965-125">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="e4965-126">Compilando, implantando e depurando objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="e4965-126">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="e4965-127">Descreve as técnicas para compilar, assinar, implantar e depurar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="e4965-127">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="e4965-128">Informações sobre outros objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="e4965-128">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="e4965-129">Para obter informações sobre os outros tipos de objetos personalizados que você pode criar no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e4965-129">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="e4965-130">Desenvolver uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="e4965-130">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="e4965-131">Aborda como programar tarefas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e4965-131">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="e4965-132">Desenvolver um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="e4965-132">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="e4965-133">Aborda como programar provedores de log personalizados.</span><span class="sxs-lookup"><span data-stu-id="e4965-133">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="e4965-134">Desenvolver um enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="e4965-134">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="e4965-135">Aborda como programar enumeradores personalizados.</span><span class="sxs-lookup"><span data-stu-id="e4965-135">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="e4965-136">Desenvolver um componente de fluxo de dados personalizado</span><span class="sxs-lookup"><span data-stu-id="e4965-136">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="e4965-137">Aborda como programar origens, transformações e destinos de fluxos de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="e4965-137">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="e4965-138">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e4965-138">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e4965-139">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="e4965-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e4965-140">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="e4965-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e4965-141">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="e4965-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
