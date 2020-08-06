---
title: MSSQL_REPL020011 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL020011 error
ms.assetid: f72072d7-bbb6-48ad-ac88-afa74aeb4d58
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646f25740ebb007f8d04a89690d3b712781efcc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683486"
---
# <a name="mssql_repl020011"></a><span data-ttu-id="6764d-102">MSSQL_REPL020011</span><span class="sxs-lookup"><span data-stu-id="6764d-102">MSSQL_REPL020011</span></span>
    
## <a name="message-details"></a><span data-ttu-id="6764d-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="6764d-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6764d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="6764d-104">Product Name</span></span>|<span data-ttu-id="6764d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6764d-105">SQL Server</span></span>|  
|<span data-ttu-id="6764d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="6764d-106">Event ID</span></span>|<span data-ttu-id="6764d-107">20011</span><span class="sxs-lookup"><span data-stu-id="6764d-107">20011</span></span>|  
|<span data-ttu-id="6764d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="6764d-108">Event Source</span></span>|<span data-ttu-id="6764d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6764d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6764d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6764d-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="6764d-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="6764d-111">Symbolic Name</span></span>||  
|<span data-ttu-id="6764d-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="6764d-112">Message Text</span></span>|<span data-ttu-id="6764d-113">O processo não pôde executar '%1' em '%2'.</span><span class="sxs-lookup"><span data-stu-id="6764d-113">The process could not execute '%1' on '%2'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6764d-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="6764d-114">Explanation</span></span>  
 <span data-ttu-id="6764d-115">Esse erro pode ser acionado em várias circunstâncias durante o processamento da replicação transacional, como quando o Agente de Leitor de Log executa **sp_replcmds** (O processo não pôde executar 'sp_replcmds' em \<ServerName>) ou **sp_repldone** (O processo não pôde executar 'sp_repldone' em \<ServerName>).</span><span class="sxs-lookup"><span data-stu-id="6764d-115">This error can be raised in a number of circumstances during transactional replication processing, such as when the Log Reader Agent executes **sp_replcmds** (The process could not execute 'sp_replcmds' on \<ServerName>) or **sp_repldone** (The process could not execute 'sp_repldone' on \<ServerName>).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6764d-116">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="6764d-116">User Action</span></span>  
 <span data-ttu-id="6764d-117">Se o erro for gerado em um banco de dados que você acabou de restaurar de um backup, certifique-se de ter seguido as etapas descritas na documentação de backup e restauração, inclusive executando **sp_replrestart** , se apropriado.</span><span class="sxs-lookup"><span data-stu-id="6764d-117">If this error is raised in a database that you have just restored from a backup, ensure you have followed the steps outlined in the backup and restore documentation, including executing **sp_replrestart** if appropriate.</span></span> <span data-ttu-id="6764d-118">Para obter mais informações, consulte [Estratégias para fazer backup e restaurar o instantâneo e a replicação transacional](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="6764d-118">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="6764d-119">Esse erro é um erro de processamento interno e, se for gerado em circunstâncias diferentes de uma restauração, geralmente indica que a replicação deve ser removida e reconfigurada.</span><span class="sxs-lookup"><span data-stu-id="6764d-119">This error is an internal processing error and if it is raised in circumstances other than a restore, it typically indicates that replication must be removed and reconfigured.</span></span> <span data-ttu-id="6764d-120">Se você não puder remover a replicação, entre em contato com o atendimento ao cliente para assistência técnica.</span><span class="sxs-lookup"><span data-stu-id="6764d-120">If you cannot remove replication, contact customer support for assistance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6764d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6764d-121">See Also</span></span>  
 <span data-ttu-id="6764d-122">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="6764d-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="6764d-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6764d-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span></span>  
 [<span data-ttu-id="6764d-124">sp_repldone &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6764d-124">sp_repldone &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-repldone-transact-sql)  
  
  
