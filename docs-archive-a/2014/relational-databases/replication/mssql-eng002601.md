---
title: MSSQL_ENG002601 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002601 error
ms.assetid: 657c3ae6-9e4b-4c60-becc-4caf7435c1dc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2e8340fef83749fd6d041af42566b10ed3542c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685062"
---
# <a name="mssql_eng002601"></a><span data-ttu-id="8f60c-102">MSSQL_ENG002601</span><span class="sxs-lookup"><span data-stu-id="8f60c-102">MSSQL_ENG002601</span></span>
    
## <a name="message-details"></a><span data-ttu-id="8f60c-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="8f60c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f60c-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8f60c-104">Product Name</span></span>|<span data-ttu-id="8f60c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f60c-105">SQL Server</span></span>|  
|<span data-ttu-id="8f60c-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8f60c-106">Event ID</span></span>|<span data-ttu-id="8f60c-107">2601</span><span class="sxs-lookup"><span data-stu-id="8f60c-107">2601</span></span>|  
|<span data-ttu-id="8f60c-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8f60c-108">Event Source</span></span>|<span data-ttu-id="8f60c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8f60c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8f60c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8f60c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="8f60c-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8f60c-111">Symbolic Name</span></span>|<span data-ttu-id="8f60c-112">N/D</span><span class="sxs-lookup"><span data-stu-id="8f60c-112">N/A</span></span>|  
|<span data-ttu-id="8f60c-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8f60c-113">Message Text</span></span>|<span data-ttu-id="8f60c-114">Não é possível inserir uma linha de chave duplicada no objeto '%.\*ls' com o índice exclusivo '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="8f60c-114">Cannot insert duplicate key row in object '%.\*ls' with unique index '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8f60c-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="8f60c-115">Explanation</span></span>  
 <span data-ttu-id="8f60c-116">Esse é um erro geral que pode ocorrer independentemente de um banco de dados ser ou não replicado.</span><span class="sxs-lookup"><span data-stu-id="8f60c-116">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="8f60c-117">Nos bancos de dados replicados, esse erro geralmente ocorre porque as chaves primárias não foram gerenciadas corretamente na topologia.</span><span class="sxs-lookup"><span data-stu-id="8f60c-117">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="8f60c-118">Em um ambiente distribuído, é essencial garantir que o mesmo valor não seja inserido em uma coluna de chave primária ou qualquer outra coluna exclusiva em mais de um nó.</span><span class="sxs-lookup"><span data-stu-id="8f60c-118">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="8f60c-119">As causas possíveis podem ser:</span><span class="sxs-lookup"><span data-stu-id="8f60c-119">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="8f60c-120">Inserções e atualizações em uma linha estão acontecendo em mais de um nó.</span><span class="sxs-lookup"><span data-stu-id="8f60c-120">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="8f60c-121">A replicação de mesclagem e as assinaturas atualizáveis para replicação transacional oferecem detecção e resolução de conflitos, mas ainda é melhor inserir ou atualizar uma determinada linha apenas em um nó.</span><span class="sxs-lookup"><span data-stu-id="8f60c-121">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="8f60c-122">O ponto a ponto transacional não oferece detecção e resolução de conflitos. Ele exige que as inserções e as atualizações sejam particionadas.</span><span class="sxs-lookup"><span data-stu-id="8f60c-122">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="8f60c-123">Uma linha foi inserida em um Assinante que deveria ser somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8f60c-123">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="8f60c-124">Assinantes de publicações de instantâneo devem ser tratados como somente leitura, do mesmo modo que Assinantes de publicações transacionais, exceto se forem usadas assinaturas atualizáveis ou replicação transacional ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="8f60c-124">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="8f60c-125">Uma tabela com uma coluna de identidade está sendo usada, mas a coluna não é gerenciada apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="8f60c-125">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
-   <span data-ttu-id="8f60c-126">Na replicação de mesclagem, esse erro também pode ocorrer durante uma inserção em uma tabela do sistema **MSmerge_contents**; o erro gerado é semelhante a: Não foi possível inserir uma linha de chave duplicada no objeto 'MSmerge_contents' com índice exclusivo 'ucl1SycContents'.</span><span class="sxs-lookup"><span data-stu-id="8f60c-126">In merge replication, this error can also occur during an insert into the system table **MSmerge_contents**; the error raised is similar to: Cannot insert duplicate key row in object 'MSmerge_contents' with unique index 'ucl1SycContents.'</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f60c-127">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8f60c-127">User Action</span></span>  
 <span data-ttu-id="8f60c-128">A ação necessária depende do motivo que levou à ocorrência do erro:</span><span class="sxs-lookup"><span data-stu-id="8f60c-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="8f60c-129">Inserções e atualizações em uma linha estão acontecendo em mais de um nó.</span><span class="sxs-lookup"><span data-stu-id="8f60c-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="8f60c-130">Independentemente do tipo de replicação usado, recomendamos o particionamento das atualizações e inserções sempre que possível para reduzir o processamento necessário para a detecção e a resolução de conflitos.</span><span class="sxs-lookup"><span data-stu-id="8f60c-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="8f60c-131">Para a replicação transacional ponto a ponto, é necessário o particionamento de inserções e atualizações.</span><span class="sxs-lookup"><span data-stu-id="8f60c-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="8f60c-132">Para obter mais informações, consulte [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="8f60c-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="8f60c-133">Uma linha foi inserida em um Assinante que deveria ser somente leitura.</span><span class="sxs-lookup"><span data-stu-id="8f60c-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="8f60c-134">Não insira ou atualize linhas no Assinante, exceto se estiver usando a replicação de mesclagem, a replicação transacional com assinaturas atualizáveis ou a replicação transacional ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="8f60c-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="8f60c-135">Uma tabela com uma coluna de identidade está sendo usada, mas a coluna não é gerenciada apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="8f60c-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="8f60c-136">Para replicação de mesclagem e replicação transacional com assinaturas atualizáveis, as colunas de identidade devem ser gerenciadas automaticamente por replicação.</span><span class="sxs-lookup"><span data-stu-id="8f60c-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="8f60c-137">Para replicação transacional ponto a ponto, elas devem ser gerenciadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="8f60c-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="8f60c-138">Para obter mais informações, consulte [Replicar colunas de identidade](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="8f60c-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
-   <span data-ttu-id="8f60c-139">O erro ocorre durante uma inserção na tabela do sistema **MSmerge_contents**.</span><span class="sxs-lookup"><span data-stu-id="8f60c-139">The error occurs during an insert into the system table **MSmerge_contents**.</span></span>  
  
     <span data-ttu-id="8f60c-140">O erro pode ocorrer devido a um valor incorreto para a propriedade de filtro de junção **join_unique_key**.</span><span class="sxs-lookup"><span data-stu-id="8f60c-140">This error can occur because of an incorrect value for the join filter property **join_unique_key**.</span></span> <span data-ttu-id="8f60c-141">Essa propriedade só deverá ser definida como TRUE se a coluna associada na tabela pai for exclusiva.</span><span class="sxs-lookup"><span data-stu-id="8f60c-141">This property should be set to TRUE only if the joined column in the parent table is unique.</span></span> <span data-ttu-id="8f60c-142">Se a propriedade for definida como TRUE, mas a coluna não for exclusiva, esse erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="8f60c-142">If the property is set to TRUE, but the column is not unique, this error is raised.</span></span> <span data-ttu-id="8f60c-143">Para obter mais informações sobre como definir essa propriedade, consulte [Definir e modificar um filtro de junção entre artigos de mesclagem](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="8f60c-143">For more information on setting this property, see [Define and Modify a Join Filter Between Merge Articles](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f60c-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f60c-144">See Also</span></span>  
 [<span data-ttu-id="8f60c-145">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="8f60c-145">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
