---
title: MSSQL_REPL027056 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027056 error
ms.assetid: 92d62f3c-b8ae-482e-a348-2e9a8ee9786e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fb130321ec54c39559d52e493cc8f3424172fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683485"
---
# <a name="mssql_repl027056"></a><span data-ttu-id="493fb-102">MSSQL_REPL027056</span><span class="sxs-lookup"><span data-stu-id="493fb-102">MSSQL_REPL027056</span></span>
    
## <a name="message-details"></a><span data-ttu-id="493fb-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="493fb-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="493fb-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="493fb-104">Product Name</span></span>|<span data-ttu-id="493fb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="493fb-105">SQL Server</span></span>|  
|<span data-ttu-id="493fb-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="493fb-106">Event ID</span></span>|<span data-ttu-id="493fb-107">27056</span><span class="sxs-lookup"><span data-stu-id="493fb-107">27056</span></span>|  
|<span data-ttu-id="493fb-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="493fb-108">Event Source</span></span>|<span data-ttu-id="493fb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="493fb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="493fb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="493fb-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="493fb-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="493fb-111">Symbolic Name</span></span>||  
|<span data-ttu-id="493fb-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="493fb-112">Message Text</span></span>|<span data-ttu-id="493fb-113">O processo de mesclagem não pôde alterar o histórico de geração no '%1'.</span><span class="sxs-lookup"><span data-stu-id="493fb-113">The merge process was unable to change generation history at the '%1'.</span></span> <span data-ttu-id="493fb-114">Ao solucionar o problema, reinicie a sincronização com o log de histórico detalhado e especifique um arquivo de saída no qual será realizada a gravação.</span><span class="sxs-lookup"><span data-stu-id="493fb-114">When troubleshooting, restart the synchronization with verbose history logging and specify an output file to which to write.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="493fb-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="493fb-115">Explanation</span></span>  
 <span data-ttu-id="493fb-116">Geralmente, esse erro é gerado como resultado da contenção em tabelas do sistema de replicação de mesclagem que cresceram exageradamente.</span><span class="sxs-lookup"><span data-stu-id="493fb-116">This error is typically raised as a result of contention in merge replication system tables that have grown excessively large.</span></span> <span data-ttu-id="493fb-117">As tabelas grandes do sistema são normalmente causadas por um longo período de retenção de publicação, pois os metadados devem ser armazenados nessas tabelas até que o período de retenção seja atingido.</span><span class="sxs-lookup"><span data-stu-id="493fb-117">Large system tables are typically caused by a long publication retention period, because metadata must be stored in these tables until the retention period is reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="493fb-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="493fb-118">User Action</span></span>  
 <span data-ttu-id="493fb-119">**Para resolver o problema:**</span><span class="sxs-lookup"><span data-stu-id="493fb-119">**To resolve the issue:**</span></span>  
  
1.  <span data-ttu-id="493fb-120">Diminua o valor dos parâmetros -**DownloadGenerationsPerBatch** e **- UploadGenerationsPerBatch** para o Merge Agent permitir que o processamento continue enquanto você aborda o problema subjacente que está causando o erro.</span><span class="sxs-lookup"><span data-stu-id="493fb-120">Decrease the value of the -**DownloadGenerationsPerBatch** and **-UploadGenerationsPerBatch** parameters for the Merge Agent to allow processing to continue while you address the underlying issue causing the error.</span></span> <span data-ttu-id="493fb-121">Os parâmetros de agente podem ser especificados em perfis de agente e na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="493fb-121">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="493fb-122">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="493fb-122">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="493fb-123">Trabalhar com perfis do Agente de Replicação</span><span class="sxs-lookup"><span data-stu-id="493fb-123">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="493fb-124">Exibir e modificar parâmetros do prompt de comando de agentes de replicação &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="493fb-124">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="493fb-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="493fb-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
2.  <span data-ttu-id="493fb-126">Especifique a menor definição possível para o período de retenção de publicação.</span><span class="sxs-lookup"><span data-stu-id="493fb-126">Specify the lowest setting possible for the publication retention period.</span></span> <span data-ttu-id="493fb-127">Para obter mais informações, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="493fb-127">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
3.  <span data-ttu-id="493fb-128">Como parte da manutenção da replicação de mesclagem, verifique esporadicamente o crescimento das tabelas do sistema associadas à replicação de mesclagem: **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**e **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="493fb-128">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="493fb-129">Periodicamente, indexe novamente essas tabelas.</span><span class="sxs-lookup"><span data-stu-id="493fb-129">Periodically re-index these tables.</span></span> <span data-ttu-id="493fb-130">Para obter mais informações, veja [Reorganizar e recriar índices](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="493fb-130">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="493fb-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="493fb-131">See Also</span></span>  
 [<span data-ttu-id="493fb-132">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="493fb-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
