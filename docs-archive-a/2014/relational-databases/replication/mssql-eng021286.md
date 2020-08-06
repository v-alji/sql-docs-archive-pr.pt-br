---
title: MSSQL_ENG021286 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021286 error
ms.assetid: b63620b7-1c6d-46f7-90ea-3a8e99af8de4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 592c788b563046e5949217c94006de2d4755f049
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679866"
---
# <a name="mssql_eng021286"></a><span data-ttu-id="c7220-102">MSSQL_ENG021286</span><span class="sxs-lookup"><span data-stu-id="c7220-102">MSSQL_ENG021286</span></span>
    
## <a name="message-details"></a><span data-ttu-id="c7220-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="c7220-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7220-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c7220-104">Product Name</span></span>|<span data-ttu-id="c7220-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7220-105">SQL Server</span></span>|  
|<span data-ttu-id="c7220-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c7220-106">Event ID</span></span>|<span data-ttu-id="c7220-107">21286</span><span class="sxs-lookup"><span data-stu-id="c7220-107">21286</span></span>|  
|<span data-ttu-id="c7220-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c7220-108">Event Source</span></span>|<span data-ttu-id="c7220-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c7220-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c7220-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c7220-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="c7220-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c7220-111">Symbolic Name</span></span>||  
|<span data-ttu-id="c7220-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c7220-112">Message Text</span></span>|<span data-ttu-id="c7220-113">A tabela de conflitos '%s' não existe.</span><span class="sxs-lookup"><span data-stu-id="c7220-113">Conflict table '%s' does not exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c7220-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="c7220-114">Explanation</span></span>  
 <span data-ttu-id="c7220-115">Esse erro será acionado se a tabela de conflitos de um artigo listado em [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) não existir de fato.</span><span class="sxs-lookup"><span data-stu-id="c7220-115">This error is raised if the conflict table for an article listed in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) does not actually exist.</span></span> <span data-ttu-id="c7220-116">O erro pode ocorrer ao tentar adicionar uma coluna ou descartar uma coluna de uma tabela publicada para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="c7220-116">The error can occur when you attempt to add a column to or drop a column from a table published for merge replication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c7220-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c7220-117">User Action</span></span>  
 <span data-ttu-id="c7220-118">Execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no banco de dados com a tabela de conflitos ausente para verificar se não há problemas de consistência de dados.</span><span class="sxs-lookup"><span data-stu-id="c7220-118">Execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database with the missing conflict table to verify there are no data consistency issues.</span></span>  
  
 <span data-ttu-id="c7220-119">Se a tabela de conflitos estiver ausente em um Assinante, descarte a assinatura e recrie-a.</span><span class="sxs-lookup"><span data-stu-id="c7220-119">If the conflict table is missing on a Subscriber, drop the subscription and recreate it.</span></span> <span data-ttu-id="c7220-120">Se a tabela de conflitos estiver ausente em um Publicador, descarte todas as assinaturas, descarte a publicação e, depois, recrie a publicação e todas as assinaturas.</span><span class="sxs-lookup"><span data-stu-id="c7220-120">If the conflict table is missing on a Publisher, drop all subscriptions, drop the publication, and then recreate the publication and all subscriptions.</span></span> <span data-ttu-id="c7220-121">Para obter mais informações, consulte [Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md) e [Assinar publicações](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="c7220-121">For more information, see [Publish Data and Database Objects](publish/publish-data-and-database-objects.md) and [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7220-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7220-122">See Also</span></span>  
 [<span data-ttu-id="c7220-123">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="c7220-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
