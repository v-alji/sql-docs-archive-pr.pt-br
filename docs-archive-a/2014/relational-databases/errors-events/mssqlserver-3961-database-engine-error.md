---
title: MSSQLSERVER_3961 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3961 (Database Engine error)
ms.assetid: 3bbc6965-6445-400c-940a-2d85b037513f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f55be9288b3c2e559633d0f67709829466fc8815
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582462"
---
# <a name="mssqlserver_3961"></a><span data-ttu-id="1c9fb-102">MSSQLSERVER_3961</span><span class="sxs-lookup"><span data-stu-id="1c9fb-102">MSSQLSERVER_3961</span></span>
    
## <a name="details"></a><span data-ttu-id="1c9fb-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1c9fb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c9fb-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="1c9fb-104">Product Name</span></span>|<span data-ttu-id="1c9fb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1c9fb-105">SQL Server</span></span>|  
|<span data-ttu-id="1c9fb-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="1c9fb-106">Event ID</span></span>|<span data-ttu-id="1c9fb-107">3961</span><span class="sxs-lookup"><span data-stu-id="1c9fb-107">3961</span></span>|  
|<span data-ttu-id="1c9fb-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="1c9fb-108">Event Source</span></span>|<span data-ttu-id="1c9fb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1c9fb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1c9fb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1c9fb-110">Component</span></span>|<span data-ttu-id="1c9fb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1c9fb-111">SQLEngine</span></span>|  
|<span data-ttu-id="1c9fb-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="1c9fb-112">Symbolic Name</span></span>|<span data-ttu-id="1c9fb-113">XACT_METADATA_INVALID</span><span class="sxs-lookup"><span data-stu-id="1c9fb-113">XACT_METADATA_INVALID</span></span>|  
|<span data-ttu-id="1c9fb-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="1c9fb-114">Message Text</span></span>|<span data-ttu-id="1c9fb-115">Falha na transação de isolamento de instantâneo no banco de dados '%.\*ls' porque o objeto acessado pela instrução foi modificado por uma instrução DDL em outra transação simultânea desde o início dessa transação.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-115">Snapshot isolation transaction failed in database '%.\*ls' because the object accessed by the statement has been modified by a DDL statement in another concurrent transaction since the start of this transaction.</span></span>  <span data-ttu-id="1c9fb-116">Ela não é permitida porque os metadados não têm controle de versão.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-116">It is disallowed because the metadata is not versioned.</span></span> <span data-ttu-id="1c9fb-117">Uma atualização simultânea dos metadados poderá gerar inconsistências se for combinada ao isolamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-117">A concurrent update to metadata can lead to inconsistency if mixed with snapshot isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1c9fb-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="1c9fb-118">Explanation</span></span>  
 <span data-ttu-id="1c9fb-119">Esse erro poderá ocorrer se você estiver consultando metadados do isolamento de instantâneo e houver uma instrução de DDL simultânea que atualiza os metadados que estão sendo acessados no isolamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-119">This error can occur if you are querying metadata under snapshot isolation and there is a concurrent DDL statement that updates the metadata that is being accessed under snapshot isolation.</span></span> <span data-ttu-id="1c9fb-120">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não tem suporte para controle de versão de metadados.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support versioning of metadata.</span></span> <span data-ttu-id="1c9fb-121">Por esse motivo, há restrições nas operações de DDL que podem ser executadas em uma transação explícita sendo executada no isolamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-121">For this reason, there are restrictions on what DDL operations can be performed within an explicit transaction running under snapshot isolation.</span></span> <span data-ttu-id="1c9fb-122">Por definição, uma transação implícita é uma instrução única que permite a imposição de semânticas de isolamento de instantâneo, mesmo com instruções de DDL.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-122">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span> <span data-ttu-id="1c9fb-123">As instruções DDL a seguir não são permitidas sob o isolamento de instantâneo após uma instrução BEGIN TRANSACTION: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME ou qualquer instrução DDL do CLR (common language runtime).</span><span class="sxs-lookup"><span data-stu-id="1c9fb-123">The following DDL statements are not permitted under snapshot isolation after a BEGIN TRANSACTION statement: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME, or any common language runtime (CLR) DDL statement.</span></span> <span data-ttu-id="1c9fb-124">Essas instruções serão permitidas quando você estiver usando o isolamento de instantâneo em transações implícitas.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-124">These statements are permitted when you are using snapshot isolation within implicit transactions.</span></span> <span data-ttu-id="1c9fb-125">Por definição, uma transação implícita é uma instrução única que permite a imposição de semânticas de isolamento de instantâneo, mesmo com instruções de DDL.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-125">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1c9fb-126">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="1c9fb-126">User Action</span></span>  
 <span data-ttu-id="1c9fb-127">Altere o nível de isolamento do instantâneo a um nível de isolamento de não instantâneo como leitura confirmada antes de consultar os metadados.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-127">Change the snapshot isolation level to a non-snapshot isolation level such as read committed before querying metadata.</span></span>  
  
  
