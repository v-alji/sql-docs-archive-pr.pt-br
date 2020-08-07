---
title: Acionar eventos no componente de Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], raising events
ms.assetid: bb389073-e1d0-4794-8d29-c8b293b6a5e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 78eb44239f4e58e43bdd65c41d5fdeb58d053a6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575209"
---
# <a name="raising-events-in-the-script-component"></a><span data-ttu-id="e4927-102">Gerando eventos no componente Script</span><span class="sxs-lookup"><span data-stu-id="e4927-102">Raising Events in the Script Component</span></span>
  <span data-ttu-id="e4927-103">Os eventos fornecem um modo de relatar erros, avisos e outras informações, como o progresso ou status da tarefa, ao pacote que os contém.</span><span class="sxs-lookup"><span data-stu-id="e4927-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="e4927-104">O pacote fornece manipuladores de eventos para gerenciar notificações de eventos.</span><span class="sxs-lookup"><span data-stu-id="e4927-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="e4927-105">O componente Script pode gerar eventos chamando métodos na propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> da classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="e4927-105">The Script component can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class.</span></span> <span data-ttu-id="e4927-106">Para obter mais informações sobre como pacotes [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] manipulam eventos, consulte [Manipuladores de Eventos do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="e4927-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="e4927-107">Os eventos podem ser registrados em qualquer provedor de log que esteja habilitado no pacote.</span><span class="sxs-lookup"><span data-stu-id="e4927-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="e4927-108">Provedores de logs armazenam informações sobre eventos em um repositório de dados.</span><span class="sxs-lookup"><span data-stu-id="e4927-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="e4927-109">O componente Script também pode usar o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> para registrar informações para um provedor de log sem gerar um evento.</span><span class="sxs-lookup"><span data-stu-id="e4927-109">The Script component can also use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="e4927-110">Para obter mais informações sobre como usar o método <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>, consulte a seção seguinte.</span><span class="sxs-lookup"><span data-stu-id="e4927-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method, see the following section.</span></span>  
  
 <span data-ttu-id="e4927-111">Para gerar um evento, a tarefa Script chama um dos métodos seguintes da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> expostos pela propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>:</span><span class="sxs-lookup"><span data-stu-id="e4927-111">To raise an event, the Script task calls one of the following methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface exposed by the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property:</span></span>  
  
|<span data-ttu-id="e4927-112">Evento</span><span class="sxs-lookup"><span data-stu-id="e4927-112">Event</span></span>|<span data-ttu-id="e4927-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e4927-113">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>|<span data-ttu-id="e4927-114">Gera um evento personalizado definido pelo usuário no pacote.</span><span class="sxs-lookup"><span data-stu-id="e4927-114">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>|<span data-ttu-id="e4927-115">Informa o pacote sobre uma condição de erro.</span><span class="sxs-lookup"><span data-stu-id="e4927-115">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>|<span data-ttu-id="e4927-116">Fornece informações ao usuário.</span><span class="sxs-lookup"><span data-stu-id="e4927-116">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireProgress%2A>|<span data-ttu-id="e4927-117">Informa o pacote sobre o progresso do componente.</span><span class="sxs-lookup"><span data-stu-id="e4927-117">Informs the package of the progress of the component.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A>|<span data-ttu-id="e4927-118">Informa o pacote que o componente está em um estado que garante a notificação do usuário, mas não é uma condição de erro.</span><span class="sxs-lookup"><span data-stu-id="e4927-118">Informs the package that the component is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
 <span data-ttu-id="e4927-119">Eis um exemplo simples de geração de um evento de erro:</span><span class="sxs-lookup"><span data-stu-id="e4927-119">Here is a simple example of raising an Error event:</span></span>  
  
 `Dim myMetadata as IDTSComponentMetaData100`  
  
 `myMetaData = Me.ComponentMetaData`  
  
 `myMetaData.FireError(...)`  
  
<span data-ttu-id="e4927-120">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e4927-120">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e4927-121">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="e4927-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e4927-122">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="e4927-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e4927-123">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="e4927-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4927-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e4927-124">See Also</span></span>  
 <span data-ttu-id="e4927-125">[Manipuladores de eventos do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="e4927-125">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="e4927-126">Adicionar um manipulador de eventos a um pacote</span><span class="sxs-lookup"><span data-stu-id="e4927-126">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
