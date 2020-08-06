---
title: Desenvolver um provedor de logs personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- SSIS packages, log providers
- custom log providers [Integration Services]
- SQL Server Integration Services packages, log providers
- log providers [Integration Services]
- packages [Integration Services], logs
- Integration Services packages, log providers
ms.assetid: 3f715b95-7074-4f5c-8ae2-246998052e78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 88d4f70fa9d50628b831b56f9fa22100648fce51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570171"
---
# <a name="developing-a-custom-log-provider"></a><span data-ttu-id="92d05-102">Desenvolvendo um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="92d05-102">Developing a Custom Log Provider</span></span>
  <span data-ttu-id="92d05-103">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] tem recursos de log extensos que possibilitam capturar eventos que ocorrem durante a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="92d05-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] has extensive logging capabilities that make it possible to capture events that occur during package execution.</span></span> <span data-ttu-id="92d05-104">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] inclui vários provedores de logs que permitem a criação e o armazenamento de logs em formatos como XML, texto, banco de dados ou no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="92d05-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of log providers that enable logs to be created and stored in formats such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="92d05-105">Se os provedores de log e os formatos de saída fornecidos não atenderem totalmente aos seus requisitos, você poderá criar um provedor de log personalizado.</span><span class="sxs-lookup"><span data-stu-id="92d05-105">If the log providers and the output formats that are provided do not entirely meet your requirements, you can create a custom log provider.</span></span>

 <span data-ttu-id="92d05-106">Para criar um provedor de log personalizado, é preciso criar uma classe que herde da classe base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, aplicar o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> à sua nova classe e substituir os métodos e as propriedades importantes da classe base, incluindo a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> e o método <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="92d05-106">To create a custom log provider, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="92d05-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="92d05-107">In This Section</span></span>
 <span data-ttu-id="92d05-108">Esta seção descreve como criar, configurar e codificar um provedor de log personalizado.</span><span class="sxs-lookup"><span data-stu-id="92d05-108">This section describes how to create, configure, and code a custom log provider.</span></span>

 <span data-ttu-id="92d05-109">[Criando um provedor de log personalizado](creating-a-custom-log-provider.md) Descreve como criar as classes para um projeto de provedor de log personalizado.</span><span class="sxs-lookup"><span data-stu-id="92d05-109">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) Describes how to create the classes for a custom log provider project.</span></span>

 <span data-ttu-id="92d05-110">[Codificando um provedor de log personalizado](coding-a-custom-log-provider.md) Descreve como implementar um provedor de log personalizado substituindo os métodos e as propriedades da classe base.</span><span class="sxs-lookup"><span data-stu-id="92d05-110">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) Describes how to implement a custom log provider by overriding the methods and properties of the base class.</span></span>

 <span data-ttu-id="92d05-111">[Desenvolvendo uma interface do usuário para um provedor de log personalizado](developing-a-user-interface-for-a-custom-log-provider.md) Não há suporte para interfaces de usuário personalizadas para provedores de log personalizados no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92d05-111">[Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md) Custom user interfaces for custom log providers are not supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="related-topics"></a><span data-ttu-id="92d05-112">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="92d05-112">Related Topics</span></span>

### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="92d05-113">Informações comuns a todos os objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="92d05-113">Information Common to all Custom Objects</span></span>
 <span data-ttu-id="92d05-114">Para obter informações comuns a todos os tipos de objetos personalizados que você pode criar no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="92d05-114">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="92d05-115">[Desenvolvendo objetos personalizados para Integration Services](../developing-custom-objects-for-integration-services.md) Descreve as etapas básicas na implementação de todos os tipos de objetos personalizados para o [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92d05-115">[Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="92d05-116">[Persistência de objetos personalizados](../persisting-custom-objects.md) Descreve a persistência personalizada e explica quando é necessário.</span><span class="sxs-lookup"><span data-stu-id="92d05-116">[Persisting Custom Objects](../persisting-custom-objects.md) Describes custom persistence and explains when it is necessary.</span></span>

 <span data-ttu-id="92d05-117">[Criando, implantando e depurando objetos personalizados](../building-deploying-and-debugging-custom-objects.md) Descreve as técnicas para criar, assinar, implantar e depurar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="92d05-117">[Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>

### <a name="information-about-other-custom-objects"></a><span data-ttu-id="92d05-118">Informações sobre outros objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="92d05-118">Information about Other Custom Objects</span></span>
 <span data-ttu-id="92d05-119">Para obter informações sobre os outros tipos de objetos personalizados que você pode criar no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="92d05-119">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="92d05-120">[Desenvolvendo uma tarefa personalizada](../task/developing-a-custom-task.md) Discute como programar tarefas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="92d05-120">[Developing a Custom Task](../task/developing-a-custom-task.md) Discusses how to program custom tasks.</span></span>

 <span data-ttu-id="92d05-121">[Desenvolvendo um Gerenciador de conexões personalizado](../connection-manager/developing-a-custom-connection-manager.md) Discute como programar gerenciadores de conexões personalizados.</span><span class="sxs-lookup"><span data-stu-id="92d05-121">[Developing a Custom Connection Manager](../connection-manager/developing-a-custom-connection-manager.md) Discusses how to program custom connection managers.</span></span>

 <span data-ttu-id="92d05-122">[Desenvolvendo um enumerador foreach personalizado](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Discute como programar enumeradores personalizados.</span><span class="sxs-lookup"><span data-stu-id="92d05-122">[Developing a Custom ForEach Enumerator](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Discusses how to program custom enumerators.</span></span>

 <span data-ttu-id="92d05-123">[Desenvolvendo um componente de fluxo de dados personalizado](../data-flow/developing-a-custom-data-flow-component.md) Discute como programar fontes de fluxo de dados personalizadas, transformações e destinos.</span><span class="sxs-lookup"><span data-stu-id="92d05-123">[Developing a Custom Data Flow Component](../data-flow/developing-a-custom-data-flow-component.md) Discusses how to program custom data flow sources, transformations, and destinations.</span></span>

<span data-ttu-id="92d05-124">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="92d05-124">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="92d05-125">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="92d05-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="92d05-126">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="92d05-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="92d05-127">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="92d05-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>


