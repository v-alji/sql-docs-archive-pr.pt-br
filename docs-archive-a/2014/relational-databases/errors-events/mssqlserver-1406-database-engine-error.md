---
title: MSSQLSERVER_1406 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adaa0084b875f720c477189e0e8e085af124f4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681673"
---
# <a name="mssqlserver_1406"></a><span data-ttu-id="3f4eb-102">MSSQLSERVER_1406</span><span class="sxs-lookup"><span data-stu-id="3f4eb-102">MSSQLSERVER_1406</span></span>
    
## <a name="details"></a><span data-ttu-id="3f4eb-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3f4eb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f4eb-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="3f4eb-104">Product Name</span></span>|<span data-ttu-id="3f4eb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f4eb-105">SQL Server</span></span>|  
|<span data-ttu-id="3f4eb-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3f4eb-106">Event ID</span></span>|<span data-ttu-id="3f4eb-107">1406</span><span class="sxs-lookup"><span data-stu-id="3f4eb-107">1406</span></span>|  
|<span data-ttu-id="3f4eb-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="3f4eb-108">Event Source</span></span>|<span data-ttu-id="3f4eb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3f4eb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3f4eb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3f4eb-110">Component</span></span>|<span data-ttu-id="3f4eb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3f4eb-111">SQLEngine</span></span>|  
|<span data-ttu-id="3f4eb-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="3f4eb-112">Symbolic Name</span></span>|<span data-ttu-id="3f4eb-113">DBM_BADSTATEFORFORCESERVICE</span><span class="sxs-lookup"><span data-stu-id="3f4eb-113">DBM_BADSTATEFORFORCESERVICE</span></span>|  
|<span data-ttu-id="3f4eb-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="3f4eb-114">Message Text</span></span>|<span data-ttu-id="3f4eb-115">Não foi possível forçar o serviço com segurança.</span><span class="sxs-lookup"><span data-stu-id="3f4eb-115">Unable to force service safely.</span></span> <span data-ttu-id="3f4eb-116">Remova o espelhamento de banco de dados e recupere o banco de dados "%.\*ls" para obter acesso.</span><span class="sxs-lookup"><span data-stu-id="3f4eb-116">Remove database mirroring and recover database "%.\*ls" to gain access.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f4eb-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="3f4eb-117">Explanation</span></span>  
 <span data-ttu-id="3f4eb-118">O [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] não pode forçar o serviço porque o estado de espelhamento não pode garantir que o processo forçar serviço funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="3f4eb-118">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot force service because the mirroring state cannot guarantee that the force service process would work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f4eb-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3f4eb-119">User Action</span></span>  
 <span data-ttu-id="3f4eb-120">Remova o espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f4eb-120">Remove database mirroring.</span></span> <span data-ttu-id="3f4eb-121">Depois, você pode recuperar o banco de dados espelho para obter acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="3f4eb-121">You can then recover the mirror database to gain access to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4eb-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3f4eb-122">See Also</span></span>  
 <span data-ttu-id="3f4eb-123">[Forçar o serviço em uma sessão de espelhamento de banco de dados &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="3f4eb-123">[Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 [<span data-ttu-id="3f4eb-124">Removendo o espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3f4eb-124">Removing Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
