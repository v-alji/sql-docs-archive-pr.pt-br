---
title: Guia do desenvolvedor&#39;s (replicação) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- developer's guide [SQL Server replication]
- programming [SQL Server replication]
- replication [SQL Server], development
ms.assetid: 7ee134ae-1cab-4a35-8017-8ac6d8fc64b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d9651aec1f02d19ea3494abf242f75049a4f33f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683501"
---
# <a name="developer39s-guide-replication"></a><span data-ttu-id="e9367-102">Guia do desenvolvedor&#39;s (replicação)</span><span class="sxs-lookup"><span data-stu-id="e9367-102">Developer&#39;s Guide (Replication)</span></span>
  <span data-ttu-id="e9367-103">A capacidade de configurar, manter e monitorar programaticamente uma topologia de replicação permite que você simplifique as tarefas de replicação repetidas e aprimore a experiência do usuário em seus aplicativos baseados em replicação.</span><span class="sxs-lookup"><span data-stu-id="e9367-103">The ability to programmatically configure, maintain, and monitor a replication topology enables you to both simplify repeated replication tasks and improve the user experience for your replication-based applications.</span></span> <span data-ttu-id="e9367-104">Ao programar a replicação, os seus usuários finais poderão obter funcionalidades de replicação personalizadas sem precisar conhecer os procedimentos armazenados de replicação e os executáveis do agente de replicação ou ter de usar a interface do usuário de replicação implementada por [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9367-104">By programming replication, your end-users can be provided with customized replication functionalities without having to be familiar with replication stored procedures and replication agent executables or having to using the replication user interface implemented by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e9367-105">A seguir, cenários nos quais os seus aplicativos poderiam se beneficiar do acesso programático a serviços de replicação:</span><span class="sxs-lookup"><span data-stu-id="e9367-105">The following are scenarios in which your applications might benefit from programmatic access to replication services:</span></span>  
  
-   <span data-ttu-id="e9367-106">Adição de funcionalidades de replicação a um aplicativo de usuário final existente, como a sincronização de uma assinatura pull quando o usuário clica em um botão.</span><span class="sxs-lookup"><span data-stu-id="e9367-106">Adding replication functionalities to an existing end-user application, such as synchronizing a pull subscription when the user clicks a button.</span></span>   
-   <span data-ttu-id="e9367-107">Criação de uma interface do usuário baseada na Web para administração remota da replicação.</span><span class="sxs-lookup"><span data-stu-id="e9367-107">Creating a Web-based user interface for remotely administering replication.</span></span>    
-   <span data-ttu-id="e9367-108">Criação de uma interface do usuário personalizada que exiba somente um subconjunto da funcionalidade de administração, que pode ser usado para administrar remotamente várias topologias de replicação a partir de um único local, ou que combine as funcionalidades de administração e de sincronização.</span><span class="sxs-lookup"><span data-stu-id="e9367-108">Creating a custom user interface that exposes only a subset of administration functionality, can be used to remotely administer multiple replication topologies from a single location, or that combine administration and synchronization functionalities.</span></span>    
-   <span data-ttu-id="e9367-109">Aprimoramento de uma ferramenta de monitoramento existente adicionando a capacidade de monitorar o status de uma publicação, assinatura ou no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e9367-109">Improving an existing monitoring tool by adding the ability to monitor the status of a publication, subscription, or at the Distributor.</span></span>    
-   <span data-ttu-id="e9367-110">Criação de um aplicativo personalizado para administrar ou sincronizar assinaturas de um publicador Oracle.</span><span class="sxs-lookup"><span data-stu-id="e9367-110">Creating a custom application to administer or synchronize subscriptions to an Oracle publisher.</span></span>    
-   <span data-ttu-id="e9367-111">Gravação de regras de negócio personalizadas executadas quando uma assinatura de mesclagem for sincronizada.</span><span class="sxs-lookup"><span data-stu-id="e9367-111">Writing customized business rules that are executed when a merge subscription is synchronized.</span></span>    
-   <span data-ttu-id="e9367-112">Geração de scripts [!INCLUDE[tsql](../../../includes/tsql-md.md)] que podem ser executados de forma repetida na configuração de Assinantes novos.</span><span class="sxs-lookup"><span data-stu-id="e9367-112">Generating [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts that can be run repeated when configuring new Subscribers.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="e9367-113">permite que você controle programaticamente os agentes de replicação e administre e monitore programaticamente uma topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="e9367-113">enables you to programmatically control replication agents and to programmatically administer and monitor a replication topology.</span></span> <span data-ttu-id="e9367-114">Para saber mais sobre como programar a replicação, consulte [Conceitos de programação da replicação](replication-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e9367-114">To learn more about programming replication, see [Replication Programming Concepts](replication-programming-concepts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9367-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e9367-115">In This Section</span></span>  
 [<span data-ttu-id="e9367-116">Conceitos de programação da replicação</span><span class="sxs-lookup"><span data-stu-id="e9367-116">Replication Programming Concepts</span></span>](replication-programming-concepts.md)  
 <span data-ttu-id="e9367-117">Descreve as etapas de planejamento para desenvolver um aplicativo que use a replicação.</span><span class="sxs-lookup"><span data-stu-id="e9367-117">Describes the planning steps to develop an application that uses replication.</span></span>  
  
 [<span data-ttu-id="e9367-118">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="e9367-118">Replication System Stored Procedures Concepts</span></span>](replication-system-stored-procedures-concepts.md)  
 <span data-ttu-id="e9367-119">Descreve como os procedimentos armazenados do sistema podem ser usados para oferecem acesso programático em uma topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="e9367-119">Describes how system stored procedures can be used to proivide programmatic access in a replication topology.</span></span>  
  
 [<span data-ttu-id="e9367-120">Conceitos de objetos de gerenciamento de replicação</span><span class="sxs-lookup"><span data-stu-id="e9367-120">Replication Management Objects Concepts</span></span>](replication-management-objects-concepts.md)  
 <span data-ttu-id="e9367-121">Explica os conceitos da utilização de RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="e9367-121">Explains the concepts for using Replication Management Objects (RMO).</span></span> <span data-ttu-id="e9367-122">Esse é um assembly de código gerenciado que encapsula funcionalidades de replicação para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9367-122">This is a managed code assembly that encapsulates replication functionalities for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="e9367-123">Conceitos dos executáveis do Replication Agent</span><span class="sxs-lookup"><span data-stu-id="e9367-123">Replication Agent Executables Concepts</span></span>](replication-agent-executables-concepts.md)  
 <span data-ttu-id="e9367-124">Descreve o uso dos arquivos executáveis do Replication Agent.</span><span class="sxs-lookup"><span data-stu-id="e9367-124">Describes the use of Replication Agent Executable files.</span></span>  

  
  
