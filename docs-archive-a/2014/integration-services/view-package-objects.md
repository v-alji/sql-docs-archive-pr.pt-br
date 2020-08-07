---
title: Exibir objetos de pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, properties
- properties [Integration Services]
- Package Explorer window [Integration Services]
- packages [Integration Services], properties
- explorer view [Integration Services]
- SSIS packages, properties
- viewing package objects
- SQL Server Integration Services packages, properties
ms.assetid: a85c0245-0a68-4eb0-83b1-9b11df80bd10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffe46be35db26186f715b18ba6114732d130e02e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575902"
---
# <a name="view-package-objects"></a><span data-ttu-id="1a6b6-102">Exibir objetos do pacote</span><span class="sxs-lookup"><span data-stu-id="1a6b6-102">View Package Objects</span></span>
  <span data-ttu-id="1a6b6-103">No Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] , a guia **Explorador de Pacotes** fornece uma exibição de explorer do pacote.</span><span class="sxs-lookup"><span data-stu-id="1a6b6-103">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the **Package Explorer** tab provides an explorer view of the package.</span></span> <span data-ttu-id="1a6b6-104">A exibição reflete a hierarquia de contêiner da arquitetura [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a6b6-104">The view reflects the container hierarchy of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] architecture.</span></span> <span data-ttu-id="1a6b6-105">O contêiner de pacote está no topo da hierarquia e você expande o pacote para exibir as conexões, executáveis, manipuladores de eventos, provedores de log, restrições de precedência e variáveis no pacote.</span><span class="sxs-lookup"><span data-stu-id="1a6b6-105">The package container is at the top of the hierarchy, and you expand the package to view the connections, executables, event handlers, log providers, precedence constraints, and variables in the package.</span></span>

 <span data-ttu-id="1a6b6-106">Os executáveis, que são contêineres e tarefas do pacote, podem incluir manipuladores de eventos, restrições de precedência e variáveis.</span><span class="sxs-lookup"><span data-stu-id="1a6b6-106">The executables, which are the containers and tasks in the package, can include event handlers, precedence constraints, and variables.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="1a6b6-107">dá suporte a uma hierarquia de contêineres aninhada, e os contêineres Loop For, Loop Foreach e Sequência podem incluir outros executáveis.</span><span class="sxs-lookup"><span data-stu-id="1a6b6-107">supports a nested hierarchy of containers, and the For Loop, Foreach Loop, and Sequence containers can include other executables.</span></span>

 <span data-ttu-id="1a6b6-108">Se um pacote incluir um fluxo de dados, o **Explorador de Pacotes** listará a tarefa de Fluxo de Dados e incluirá uma pasta **Componentes** que lista os componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="1a6b6-108">If a package includes a data flow, the **Package Explorer** lists the Data Flow task and includes a **Components** folder that lists the data flow components.</span></span>

 <span data-ttu-id="1a6b6-109">Na guia **Explorador de Pacotes** , você pode excluir objetos em um pacote e acessar a janela **Propriedades** para exibir as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="1a6b6-109">From the **Package Explorer** tab, you can delete objects in a package and access the **Properties** window to view object properties.</span></span>

 <span data-ttu-id="1a6b6-110">O diagrama a seguir mostra uma exibição de árvore de um pacote simples.</span><span class="sxs-lookup"><span data-stu-id="1a6b6-110">The following diagram shows a tree view of a simple package.</span></span>

 <span data-ttu-id="1a6b6-111">![Captura de tela da guia Explorador de Pacotes](media/packageexplorer.gif "Captura de tela da guia Explorador de Pacotes")</span><span class="sxs-lookup"><span data-stu-id="1a6b6-111">![Screenshot of the Package Explorer tab](media/packageexplorer.gif "Screenshot of the Package Explorer tab")</span></span>

### <a name="to-view-package-content"></a><span data-ttu-id="1a6b6-112">Para exibir o conteúdo do pacote</span><span class="sxs-lookup"><span data-stu-id="1a6b6-112">To view package content</span></span>

-   [<span data-ttu-id="1a6b6-113">Exibir objetos de pacote no Explorador de Pacotes</span><span class="sxs-lookup"><span data-stu-id="1a6b6-113">View Package Objects in Package Explorer</span></span>](../../2014/integration-services/view-package-objects-in-package-explorer.md)

## <a name="see-also"></a><span data-ttu-id="1a6b6-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a6b6-114">See Also</span></span>
 <span data-ttu-id="1a6b6-115">[Integration Services tarefas](control-flow/integration-services-tasks.md) [Integration Services](control-flow/integration-services-containers.md) [restrições de precedência](control-flow/precedence-constraints.md) de contêineres [Integration Services &#40;as variáveis do SSIS&#41;](integration-services-ssis-variables.md) [Integration Services &#40;SSIS&#41; manipuladores de eventos](integration-services-ssis-event-handlers.md) [Integration Services &#40;SSIS&#41; log](performance/integration-services-ssis-logging.md)</span><span class="sxs-lookup"><span data-stu-id="1a6b6-115">[Integration Services Tasks](control-flow/integration-services-tasks.md) [Integration Services Containers](control-flow/integration-services-containers.md) [Precedence Constraints](control-flow/precedence-constraints.md) [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) [Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md)</span></span>


