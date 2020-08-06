---
title: MSSQL_ENG002627 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002627 error
ms.assetid: 7f4136ac-3784-4a41-a98c-8a02308e4883
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cf481635d6a24570792c9da04fe71ebea885ce5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685547"
---
# <a name="mssql_eng002627"></a><span data-ttu-id="98298-102">MSSQL_ENG002627</span><span class="sxs-lookup"><span data-stu-id="98298-102">MSSQL_ENG002627</span></span>
    
## <a name="message-details"></a><span data-ttu-id="98298-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="98298-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98298-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="98298-104">Product Name</span></span>|<span data-ttu-id="98298-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="98298-105">SQL Server</span></span>|  
|<span data-ttu-id="98298-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="98298-106">Event ID</span></span>|<span data-ttu-id="98298-107">2627</span><span class="sxs-lookup"><span data-stu-id="98298-107">2627</span></span>|  
|<span data-ttu-id="98298-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="98298-108">Event Source</span></span>|<span data-ttu-id="98298-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="98298-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="98298-110">Componente</span><span class="sxs-lookup"><span data-stu-id="98298-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="98298-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="98298-111">Symbolic Name</span></span>|<span data-ttu-id="98298-112">N/D</span><span class="sxs-lookup"><span data-stu-id="98298-112">N/A</span></span>|  
|<span data-ttu-id="98298-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="98298-113">Message Text</span></span>|<span data-ttu-id="98298-114">Violação da restrição %ls '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="98298-114">Violation of %ls constraint '%.\*ls'.</span></span> <span data-ttu-id="98298-115">Não é possível inserir uma chave duplicada no objeto '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="98298-115">Cannot insert duplicate key in object '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="98298-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="98298-116">Explanation</span></span>  
 <span data-ttu-id="98298-117">Esse é um erro geral que pode ocorrer independentemente de um banco de dados ser ou não replicado.</span><span class="sxs-lookup"><span data-stu-id="98298-117">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="98298-118">Nos bancos de dados replicados, esse erro geralmente ocorre porque as chaves primárias não foram gerenciadas corretamente na topologia.</span><span class="sxs-lookup"><span data-stu-id="98298-118">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="98298-119">Em um ambiente distribuído, é essencial garantir que o mesmo valor não seja inserido em uma coluna de chave primária ou qualquer outra coluna exclusiva em mais de um nó.</span><span class="sxs-lookup"><span data-stu-id="98298-119">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="98298-120">As causas possíveis podem ser:</span><span class="sxs-lookup"><span data-stu-id="98298-120">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="98298-121">Inserções e atualizações em uma linha estão acontecendo em mais de um nó.</span><span class="sxs-lookup"><span data-stu-id="98298-121">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="98298-122">A replicação de mesclagem e as assinaturas atualizáveis para replicação transacional oferecem detecção e resolução de conflitos, mas ainda é melhor inserir ou atualizar uma determinada linha apenas em um nó.</span><span class="sxs-lookup"><span data-stu-id="98298-122">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="98298-123">O ponto a ponto transacional não oferece detecção e resolução de conflitos. Ele exige que as inserções e as atualizações sejam particionadas.</span><span class="sxs-lookup"><span data-stu-id="98298-123">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="98298-124">Uma linha foi inserida em um Assinante que deveria ser somente leitura.</span><span class="sxs-lookup"><span data-stu-id="98298-124">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="98298-125">Assinantes de publicações de instantâneo devem ser tratados como somente leitura, do mesmo modo que Assinantes de publicações transacionais, exceto se forem usadas assinaturas atualizáveis ou replicação transacional ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="98298-125">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="98298-126">Uma tabela com uma coluna de identidade está sendo usada, mas a coluna não é gerenciada apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="98298-126">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98298-127">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="98298-127">User Action</span></span>  
 <span data-ttu-id="98298-128">A ação necessária depende do motivo que levou à ocorrência do erro:</span><span class="sxs-lookup"><span data-stu-id="98298-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="98298-129">Inserções e atualizações em uma linha estão acontecendo em mais de um nó.</span><span class="sxs-lookup"><span data-stu-id="98298-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="98298-130">Independentemente do tipo de replicação usado, recomendamos o particionamento das atualizações e inserções sempre que possível para reduzir o processamento necessário para a detecção e a resolução de conflitos.</span><span class="sxs-lookup"><span data-stu-id="98298-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="98298-131">Para a replicação transacional ponto a ponto, é necessário o particionamento de inserções e atualizações.</span><span class="sxs-lookup"><span data-stu-id="98298-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="98298-132">Para obter mais informações, consulte [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="98298-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="98298-133">Uma linha foi inserida em um Assinante que deveria ser somente leitura.</span><span class="sxs-lookup"><span data-stu-id="98298-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="98298-134">Não insira ou atualize linhas no Assinante, exceto se estiver usando a replicação de mesclagem, a replicação transacional com assinaturas atualizáveis ou a replicação transacional ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="98298-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="98298-135">Uma tabela com uma coluna de identidade está sendo usada, mas a coluna não é gerenciada apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="98298-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="98298-136">Para replicação de mesclagem e replicação transacional com assinaturas atualizáveis, as colunas de identidade devem ser gerenciadas automaticamente por replicação.</span><span class="sxs-lookup"><span data-stu-id="98298-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="98298-137">Para replicação transacional ponto a ponto, elas devem ser gerenciadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="98298-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="98298-138">Para obter mais informações, consulte [Replicar colunas de identidade](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="98298-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98298-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98298-139">See Also</span></span>  
 <span data-ttu-id="98298-140">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="98298-140">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="98298-141">[Replicação de mesclagem](merge/merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="98298-141">[Merge Replication](merge/merge-replication.md) </span></span>  
 <span data-ttu-id="98298-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="98298-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="98298-143">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="98298-143">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
