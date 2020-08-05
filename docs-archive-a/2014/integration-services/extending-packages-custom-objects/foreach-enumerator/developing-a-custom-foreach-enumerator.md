---
title: Desenvolver um enumerador ForEach personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services]
- custom foreach enumerators [Integration Services], about custom foreach enumerators
- foreach enumerators [Integration Services]
ms.assetid: bffe26e0-1b9a-47ad-bae6-6b708cb4cf4f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3d61f98266320f63d7ee56262b7c85dfb64d39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574213"
---
# <a name="developing-a-custom-foreach-enumerator"></a><span data-ttu-id="bb595-102">Desenvolvendo um enumerador de ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="bb595-102">Developing a Custom ForEach Enumerator</span></span>
  <span data-ttu-id="bb595-103">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] usa enumeradores foreach para iterar sobre os itens de uma coleção e executar as mesmas tarefas para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="bb595-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses foreach enumerators to iterate over the items in a collection and perform the same tasks for each element.</span></span> <span data-ttu-id="bb595-104">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] inclui vários enumeradores foreach que dão suporte às coleções mais usadas, como todos os arquivos de uma pasta, todas as tabelas de um banco de dados ou todos os elementos de uma lista armazenada em uma variável de pacote.</span><span class="sxs-lookup"><span data-stu-id="bb595-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of foreach enumerators that support the most commonly used collections, such as all the files in a folder, all the tables in a database, or all the elements of a list stored in a package variable.</span></span> <span data-ttu-id="bb595-105">Se os enumeradores de foreach e as coleções fornecidos não satisfizerem seus requisitos completamente, você poderá criar um enumerador de foreach personalizado.</span><span class="sxs-lookup"><span data-stu-id="bb595-105">If the foreach enumerators and collections that are provided do not entirely meet your requirements, you can create a custom foreach enumerator.</span></span>  
  
 <span data-ttu-id="bb595-106">Para criar um enumerador de foreach personalizado, é preciso criar uma classe que herde da classe base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, aplicar o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> em sua nova classe e substituir os métodos e propriedades importantes da classe base, incluindo o método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="bb595-106">To create a custom foreach enumerator, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb595-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bb595-107">In This Section</span></span>  
 <span data-ttu-id="bb595-108">Esta seção descreve como criar, configurar e codificar um enumerador foreach personalizado e sua interface de usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="bb595-108">This section describes how to create, configure, and code a custom foreach enumerator and its custom user interface.</span></span>  
  
 [<span data-ttu-id="bb595-109">Criar um enumerador Foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="bb595-109">Creating a Custom Foreach Enumerator</span></span>](creating-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="bb595-110">Descreve como criar as classes para um projeto de enumerador foreach personalizado.</span><span class="sxs-lookup"><span data-stu-id="bb595-110">Describes how to create the classes for a custom foreach enumerator project.</span></span>  
  
 [<span data-ttu-id="bb595-111">Codificar um enumerador Foreach personalizado</span><span class="sxs-lookup"><span data-stu-id="bb595-111">Coding a Custom Foreach Enumerator</span></span>](coding-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="bb595-112">Descreve como implementar um enumerador de foreach personalizado anulando os métodos e propriedades da classe base.</span><span class="sxs-lookup"><span data-stu-id="bb595-112">Describes how to implement a custom foreach enumerator by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="bb595-113">Desenvolver uma interface do usuário para um enumerador ForEach personalizado</span><span class="sxs-lookup"><span data-stu-id="bb595-113">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="bb595-114">Descreve como implementar a classe de interface do usuário e o formulário usado para configurar o enumerador foreach personalizado.</span><span class="sxs-lookup"><span data-stu-id="bb595-114">Describes how to implement the user interface class and the form that is used to configure the custom foreach enumerator.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="bb595-115">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="bb595-115">Related Topics</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="bb595-116">Informações comuns a todos os objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="bb595-116">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="bb595-117">Para obter informações comuns a todos os tipos de objetos personalizados que você pode criar no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="bb595-117">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="bb595-118">Desenvolvendo objetos personalizados para o Integration Services</span><span class="sxs-lookup"><span data-stu-id="bb595-118">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="bb595-119">Descreve as etapas básicas para implementar todos os tipos de objetos personalizados para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb595-119">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="bb595-120">Persistência de objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="bb595-120">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="bb595-121">Descreve a persistência personalizada e explica quando ela é necessária.</span><span class="sxs-lookup"><span data-stu-id="bb595-121">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="bb595-122">Compilando, implantando e depurando objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="bb595-122">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="bb595-123">Descreve as técnicas para compilar, assinar, implantar e depurar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bb595-123">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="bb595-124">Informações sobre outros objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="bb595-124">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="bb595-125">Para obter informações sobre os outros tipos de objetos personalizados que você pode criar no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="bb595-125">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="bb595-126">Desenvolver uma tarefa personalizada</span><span class="sxs-lookup"><span data-stu-id="bb595-126">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="bb595-127">Aborda como programar tarefas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="bb595-127">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="bb595-128">Desenvolver um gerenciador de conexões personalizado</span><span class="sxs-lookup"><span data-stu-id="bb595-128">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="bb595-129">Aborda como programar gerenciadores de conexões personalizados.</span><span class="sxs-lookup"><span data-stu-id="bb595-129">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="bb595-130">Desenvolver um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="bb595-130">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="bb595-131">Aborda como programar provedores de log personalizados.</span><span class="sxs-lookup"><span data-stu-id="bb595-131">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="bb595-132">Desenvolver um componente de fluxo de dados personalizado</span><span class="sxs-lookup"><span data-stu-id="bb595-132">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="bb595-133">Aborda como programar origens, transformações e destinos de fluxos de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="bb595-133">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="bb595-134">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="bb595-134">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bb595-135">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="bb595-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bb595-136">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="bb595-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bb595-137">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="bb595-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
