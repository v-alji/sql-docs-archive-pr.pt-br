---
title: Conceitos dos executáveis do agente de replicação | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- programming interfaces [SQL Server replication]
- programming [SQL Server replication], agents
- replication [SQL Server], agents and profiles
- agents [SQL Server replication], executables
- command prompt [SQL Server replication]
ms.assetid: cba476df-d4ea-44c9-bb86-81488971e328
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73f9fe0d1a98fa1afc813cd113dcced685b4f98a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685573"
---
# <a name="replication-agent-executables-concepts"></a><span data-ttu-id="916ff-102">Conceitos dos executáveis do Replication Agent</span><span class="sxs-lookup"><span data-stu-id="916ff-102">Replication Agent Executables Concepts</span></span>
  <span data-ttu-id="916ff-103">Os agentes de replicação podem ser controlados programaticamente das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="916ff-103">Replication agents can be controlled programmatically in the following ways:</span></span>  
  
-   <span data-ttu-id="916ff-104">Usando as interfaces de programação do agente gerenciado no namespace <xref:Microsoft.SqlServer.Replication>.</span><span class="sxs-lookup"><span data-stu-id="916ff-104">Using the managed agent programming interfaces in the <xref:Microsoft.SqlServer.Replication> Namespace.</span></span>  
  
-   <span data-ttu-id="916ff-105">Invocando arquivos executáveis do agente no prompt de comando usando um conjunto de parâmetros fornecido.</span><span class="sxs-lookup"><span data-stu-id="916ff-105">Invoking agent executable files from the command prompt with a supplied set of parameters.</span></span>  
  
 <span data-ttu-id="916ff-106">Invocar agentes de replicação diretamente do prompt de comando permite que os agentes sejam programaticamente acessados de scripts de linha de comandos existentes em arquivos em lotes.</span><span class="sxs-lookup"><span data-stu-id="916ff-106">Directly invoking replication agents from the command prompt enables agents to be programmatically accessed from command-line scripting in batch files.</span></span> <span data-ttu-id="916ff-107">Quando um agente é invocado do prompt de comando, é executado sob a conta de segurança do Windows [!INCLUDE[msCoName](../../../includes/msconame-md.md)] do usuário que invocou o agente ou que iniciou o arquivo em lotes.</span><span class="sxs-lookup"><span data-stu-id="916ff-107">When an agent is invoked from the command prompt, it runs under the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows security account of the user that invoked the agent or started the batch file.</span></span>  
  
 <span data-ttu-id="916ff-108">As instâncias dos agentes de replicação a seguir podem ser executadas por meio de arquivos executáveis.</span><span class="sxs-lookup"><span data-stu-id="916ff-108">Instances of the following replication agents can be run using executable files.</span></span>  
  
-   [<span data-ttu-id="916ff-109">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="916ff-109">Replication Distribution Agent</span></span>](../agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="916ff-110">Agente do Leitor de Log de Replicação</span><span class="sxs-lookup"><span data-stu-id="916ff-110">Replication Log Reader Agent</span></span>](../agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="916ff-111">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="916ff-111">Replication Merge Agent</span></span>](../agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="916ff-112">Agente de Leitor de Fila de Replicação</span><span class="sxs-lookup"><span data-stu-id="916ff-112">Replication Queue Reader Agent</span></span>](../agents/replication-queue-reader-agent.md)  
  
-   [<span data-ttu-id="916ff-113">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="916ff-113">Replication Snapshot Agent</span></span>](../agents/replication-snapshot-agent.md)  
  
 <span data-ttu-id="916ff-114">Ao invocar agentes de replicação, você pode usar perfis de desempenho para transmitir automaticamente um conjunto definido de parâmetros para o executável do agente.</span><span class="sxs-lookup"><span data-stu-id="916ff-114">When invoking replication agents, you can use performance profiles to automatically pass a defined set of parameters to the agent executable.</span></span> <span data-ttu-id="916ff-115">Para saber mais, confira [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="916ff-115">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="916ff-116">Exemplos</span><span class="sxs-lookup"><span data-stu-id="916ff-116">Examples</span></span>  
 <span data-ttu-id="916ff-117">Os exemplos a seguir mostram como invocar os agentes de replicação no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="916ff-117">The following examples show how to invoke replication agents from the command prompt.</span></span> <span data-ttu-id="916ff-118">Os agentes de replicação também podem ser invocados usando RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="916ff-118">Replication agents can also be invoked using Replication Management Objects (RMO).</span></span> <span data-ttu-id="916ff-119">Para obter mais informações, consulte [Sincronizar assinaturas &#40;replicação&#41;](../synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="916ff-119">For more information, see [Synchronize Subscriptions &#40;Replication&#41;](../synchronize-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="916ff-120">As quebras de linha destes exemplos foram adicionadas para melhorar a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="916ff-120">Line breaks in these examples were added to improve readability.</span></span> <span data-ttu-id="916ff-121">Em um arquivo em lotes, devem ser feitos comandos em uma única linha.</span><span class="sxs-lookup"><span data-stu-id="916ff-121">In a batch file, commands must be made in a single line.</span></span>  
  
### <a name="running-the-snapshot-agent"></a><span data-ttu-id="916ff-122">Executando o Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="916ff-122">Running the Snapshot Agent</span></span>  
 <span data-ttu-id="916ff-123">Esse arquivo em lotes de exemplo invoca o Snapshot Agent no prompt de comando para gerar um instantâneo para a publicação **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="916ff-123">This example batch file invokes the Snapshot Agent from the command prompt to generate a snapshot for the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare variables  
SET Publisher=%InstanceName%;  
SET PublicationDB=AdventureWorks2012;   
SET Publication=AdvWorksSalesOrdersMerge;   
  
REM --Start the Snapshot Agent to generate the snapshot for AdvWorksSalesOrdersMerge.  
"C:\Program Files\Microsoft SQL Server\120\COM\SNAPSHOT.EXE" -Publication %Publication%   
-Publisher %Publisher% -Distributor %Publisher% -PublisherDB %PublicationDB%   
-ReplicationType 2 -OutputVerboseLevel 1 -DistributorSecurityMode 1 ;  
  
```  
  
### <a name="running-the-distribution-agent"></a><span data-ttu-id="916ff-124">Executando o Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="916ff-124">Running the Distribution Agent</span></span>  
 <span data-ttu-id="916ff-125">Esse arquivo em lotes de exemplo invoca o Agente de Distribuição no prompt de comando para replicar as alterações de forma contínua da publicação **AdvWorksProductTran** para um assinante push.</span><span class="sxs-lookup"><span data-stu-id="916ff-125">This example batch file invokes the Distribution Agent from the command prompt to continuously replicate changes from the **AdvWorksProductTran** publication to a push subscriber.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksProductsTran;  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4 ;  
  
```  
  
### <a name="running-the-merge-agent"></a><span data-ttu-id="916ff-126">Executando o Merge Agent</span><span class="sxs-lookup"><span data-stu-id="916ff-126">Running the Merge Agent</span></span>  
 <span data-ttu-id="916ff-127">Esse arquivo em lotes de exemplo invoca o Agente de Mesclagem no prompt de comando para sincronizar uma assinatura pull com a publicação **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="916ff-127">This example batch file invokes the Merge Agent from the command prompt to synchronize a pull subscription to the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksSalesOrdersMerge;  
  
REM --Start the Merge Agent with concurrent upload and download processes.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE" -Publication %Publication%    
-Publisher %Publisher%  -Subscriber  %Subscriber%  -Distributor %Publisher%    
-PublisherDB %PublicationDB%  -SubscriberDB %SubscriptionDB% -PublisherSecurityMode 1    
-OutputVerboseLevel 2  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1    
-Validate 3  -ParallelUploadDownload 1 ;  
  
```  
  
  
