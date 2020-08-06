---
title: SQL Server Service Broker | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SSBQUEUEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBREMSVCBINDPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBMSGTYPEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBROUTEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBCONTRACTPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBSERVICEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBPRIORITYPROPERTIES.GENERAL.F1
helpviewer_keywords:
- Broker See Service Broker
- SQL Server Service Broker
- Service Broker
ms.assetid: 8b8b3b57-fd46-44de-9a4e-e3a8e3999c1e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3d3877dd8311e0fe5b65bd4b1e7f9c40fbd84751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684882"
---
# <a name="sql-server-service-broker"></a><span data-ttu-id="c2339-102">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="c2339-102">SQL Server Service Broker</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c2339-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)] dá suporte nativo para aplicativos de mensagens e enfileiramento no [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2339-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)] provides native support for messaging and queuing applications in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="c2339-104">Isso facilita para os desenvolvedores a criação de aplicativos sofisticados que usam os componentes do [!INCLUDE[ssDE](../../includes/ssde-md.md)] para comunicação entre bancos de dados díspares.</span><span class="sxs-lookup"><span data-stu-id="c2339-104">This makes it easier for developers to create sophisticated applications that use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] components to communicate between disparate databases.</span></span> <span data-ttu-id="c2339-105">Os desenvolvedores podem usar o [!INCLUDE[ssSB](../../includes/sssb-md.md)] para criar facilmente aplicativos distribuídos e confiáveis.</span><span class="sxs-lookup"><span data-stu-id="c2339-105">Developers can use [!INCLUDE[ssSB](../../includes/sssb-md.md)] to easily build distributed and reliable applications.</span></span>  
  
 <span data-ttu-id="c2339-106">Os desenvolvedores de aplicativos que usam o [!INCLUDE[ssSB](../../includes/sssb-md.md)] podem distribuir cargas de trabalho de dados por vários bancos de dados sem programação de comunicação complexa e mensagens internas.</span><span class="sxs-lookup"><span data-stu-id="c2339-106">Application developers who use [!INCLUDE[ssSB](../../includes/sssb-md.md)] can distribute data workloads across several databases without programming complex communication and messaging internals.</span></span> <span data-ttu-id="c2339-107">Isso reduz o trabalho de desenvolvimento e teste porque o [!INCLUDE[ssSB](../../includes/sssb-md.md)] controla os caminhos de comunicação no contexto de uma conversa.</span><span class="sxs-lookup"><span data-stu-id="c2339-107">This reduces development and test work because [!INCLUDE[ssSB](../../includes/sssb-md.md)] handles the communication paths in the context of a conversation.</span></span> <span data-ttu-id="c2339-108">Isso também melhora o desempenho.</span><span class="sxs-lookup"><span data-stu-id="c2339-108">It also improves performance.</span></span> <span data-ttu-id="c2339-109">Por exemplo, bancos de dados front-end que oferecem suporte a sites podem gravar informações e enviar tarefas intensivas de processamento para enfileiramento em bancos de dados back-end.</span><span class="sxs-lookup"><span data-stu-id="c2339-109">For example, front-end databases supporting Web sites can record information and send process intensive tasks to queue in back-end databases.</span></span> [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="c2339-110">garante que todas as tarefas sejam gerenciadas no contexto de transações para assegurar a confiabilidade e a consistência técnica.</span><span class="sxs-lookup"><span data-stu-id="c2339-110">ensures that all tasks are managed in the context of transactions to assure reliability and technical consistency.</span></span>  
  
## <a name="where-is-the-documentation-for-service-broker"></a><span data-ttu-id="c2339-111">Onde está a documentação do Service Broker?</span><span class="sxs-lookup"><span data-stu-id="c2339-111">Where is the documentation for Service Broker?</span></span>  
 <span data-ttu-id="c2339-112">A documentação de referência do [!INCLUDE[ssSB](../../includes/sssb-md.md)] está incluída na documentação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2339-112">The reference documentation for [!INCLUDE[ssSB](../../includes/sssb-md.md)] is included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation.</span></span> <span data-ttu-id="c2339-113">Esta documentação de referência inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="c2339-113">This reference documentation includes the following sections:</span></span>  
  
-   <span data-ttu-id="c2339-114">[Instruções DDL &#40;Linguagem de Definição de Dados&#41; &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) para instruções CREATE, ALTER e DROP</span><span class="sxs-lookup"><span data-stu-id="c2339-114">[Data Definition Language &#40;DDL&#41; Statements &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) for CREATE, ALTER, and DROP statements</span></span>  
  
-   [<span data-ttu-id="c2339-115">Exibições de catálogo do Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c2339-115">Service Broker Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/service-broker-catalog-views-transact-sql)  
  
-   [<span data-ttu-id="c2339-116">Exibições de gerenciamento dinâmico relacionadas ao Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c2339-116">Service Broker Related Dynamic Management Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/service-broker-related-dynamic-management-views-transact-sql)  
  
-   [<span data-ttu-id="c2339-117">Utilitário ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="c2339-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](../../tools/ssbdiagnose/ssbdiagnose-utility-service-broker.md)  
  
 <span data-ttu-id="c2339-118">Consulte a [documentação publicada anteriormente](https://go.microsoft.com/fwlink/?LinkId=231312) para saber mais sobre conceitos do [!INCLUDE[ssSB](../../includes/sssb-md.md)] e sobre tarefas de desenvolvimento e gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="c2339-118">See the [previously published documentation](https://go.microsoft.com/fwlink/?LinkId=231312) for [!INCLUDE[ssSB](../../includes/sssb-md.md)] concepts and for development and management tasks.</span></span> <span data-ttu-id="c2339-119">Esta documentação não é reproduzida na documentação do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] devido ao pequeno número de alterações no [!INCLUDE[ssSB](../../includes/sssb-md.md)] no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2339-119">This documentation is not reproduced in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation due to the small number of changes in [!INCLUDE[ssSB](../../includes/sssb-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="whats-new-in-service-broker"></a><span data-ttu-id="c2339-120">Novidades no Service Broker</span><span class="sxs-lookup"><span data-stu-id="c2339-120">What's new in Service Broker</span></span>  
 <span data-ttu-id="c2339-121">Nenhuma alteração significativa foi introduzida no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2339-121">No significant changes are introduced in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  <span data-ttu-id="c2339-122">As alterações a seguir foram introduzidas no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2339-122">The following changes were introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
### <a name="messages-can-be-sent-to-multiple-target-services-multicast"></a><span data-ttu-id="c2339-123">As mensagens podem ser enviadas a vários serviços de destino (multicast)</span><span class="sxs-lookup"><span data-stu-id="c2339-123">Messages can be sent to multiple target services (multicast)</span></span>  
 <span data-ttu-id="c2339-124">A sintaxe da instrução [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) foi estendida para habilitar o multicast, dando suporte a vários identificadores de conversa.</span><span class="sxs-lookup"><span data-stu-id="c2339-124">The syntax of the [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) statement has been extended to enable multicast by supporting multiple conversation handles.</span></span>  
  
### <a name="queues-expose-the-message-enqueued-time"></a><span data-ttu-id="c2339-125">Filas expõem o tempo de enfileiramento da mensagem</span><span class="sxs-lookup"><span data-stu-id="c2339-125">Queues expose the message enqueued time</span></span>  
 <span data-ttu-id="c2339-126">Filas têm uma nova coluna, **message_enqueue_time**, que mostra quanto tempo uma mensagem permaneceu na fila.</span><span class="sxs-lookup"><span data-stu-id="c2339-126">Queues have a new column, **message_enqueue_time**, that shows how long a message has been in the queue.</span></span>  
  
### <a name="poison-message-handling-can-be-disabled"></a><span data-ttu-id="c2339-127">A manipulação de mensagens suspeitas pode estar desabilitada</span><span class="sxs-lookup"><span data-stu-id="c2339-127">Poison message handling can be disabled</span></span>  
 <span data-ttu-id="c2339-128">As instruções [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) e [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) agora tem a capacidade de habilitar ou desabilitar a manipulação de mensagens suspeitas adicionando a cláusula `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span><span class="sxs-lookup"><span data-stu-id="c2339-128">The [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) and [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) statements now have the ability to enable or disable poison message handling by adding the clause, `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span></span> <span data-ttu-id="c2339-129">A exibição de catálogo **sys.service_queues** agora tem a coluna **is_poison_message_handling_enabled** para indicar se a mensagem suspeita está habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="c2339-129">The catalog view **sys.service_queues** now has the column **is_poison_message_handling_enabled** to indicate whether poison message is enabled or disabled.</span></span>  
  
### <a name="alwayson-support-in-service-broker"></a><span data-ttu-id="c2339-130">Suporte AlwaysOn no Service Broker</span><span class="sxs-lookup"><span data-stu-id="c2339-130">AlwaysOn support in Service Broker</span></span>  
 <span data-ttu-id="c2339-131">Para obter mais informações, confira [Service Broker com grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c2339-131">For more information, see [Service Broker with AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span></span>  
  
  
