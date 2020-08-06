---
title: MSSQLSERVER_17067 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17067 (Database Engine error)
ms.assetid: 32c1f0e8-db70-4836-95b2-8833be9e0ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4ff3de7ed2fbe54a32aaa501979a3acb6b452947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581883"
---
# <a name="mssqlserver_17067"></a><span data-ttu-id="99821-102">MSSQLSERVER_17067</span><span class="sxs-lookup"><span data-stu-id="99821-102">MSSQLSERVER_17067</span></span>
    
## <a name="details"></a><span data-ttu-id="99821-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="99821-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99821-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="99821-104">Product Name</span></span>|<span data-ttu-id="99821-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="99821-105">SQL Server</span></span>|  
|<span data-ttu-id="99821-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="99821-106">Event ID</span></span>|<span data-ttu-id="99821-107">17067</span><span class="sxs-lookup"><span data-stu-id="99821-107">17067</span></span>|  
|<span data-ttu-id="99821-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="99821-108">Event Source</span></span>|<span data-ttu-id="99821-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="99821-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="99821-110">Componente</span><span class="sxs-lookup"><span data-stu-id="99821-110">Component</span></span>|<span data-ttu-id="99821-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="99821-111">SQLEngine</span></span>|  
|<span data-ttu-id="99821-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="99821-112">Symbolic Name</span></span>|<span data-ttu-id="99821-113">SQLASSERT_MESG</span><span class="sxs-lookup"><span data-stu-id="99821-113">SQLASSERT_MESG</span></span>|  
|<span data-ttu-id="99821-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="99821-114">Message Text</span></span>|<span data-ttu-id="99821-115">Asserção do SQL Server: Arquivo: \<%s>, linha = %d %s.</span><span class="sxs-lookup"><span data-stu-id="99821-115">SQL Server Assertion: File: \<%s>, line = %d %s.</span></span> <span data-ttu-id="99821-116">Talvez esse erro esteja relacionado à temporização.</span><span class="sxs-lookup"><span data-stu-id="99821-116">This error may be timing-related.</span></span> <span data-ttu-id="99821-117">Se o erro persistir após a repetição da instrução, use DBCC CHECKDB para verificar a integridade estrutural do banco de dados ou reinicie o servidor para assegurar que as estruturas de dados na memória não estejam corrompidas.</span><span class="sxs-lookup"><span data-stu-id="99821-117">If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="99821-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="99821-118">Explanation</span></span>  
 <span data-ttu-id="99821-119">Talvez o erro seja causado por erros transitórios relacionados à temporização ou por dados corrompidos na memória ou no disco.</span><span class="sxs-lookup"><span data-stu-id="99821-119">This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="99821-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="99821-120">User Action</span></span>  
 <span data-ttu-id="99821-121">Exiba novamente a instrução que causou o disparo da exceção.</span><span class="sxs-lookup"><span data-stu-id="99821-121">Rerun the statement that caused the exception to fire.</span></span> <span data-ttu-id="99821-122">Se o erro foi causado por um evento relacionado à temporização, talvez ele não ocorra novamente.</span><span class="sxs-lookup"><span data-stu-id="99821-122">If the error was caused by a timing-related event, the error may not recur.</span></span> <span data-ttu-id="99821-123">Se o problema persistir, execute DBCC CHECKDB para verificar se há dados corrompidos no disco.</span><span class="sxs-lookup"><span data-stu-id="99821-123">If the problem persists, run DBCC CHECKDB to check for on-disk corruption.</span></span> <span data-ttu-id="99821-124">Reinicie o servidor para garantir que as estruturas de dados na memória não estão corrompidas.</span><span class="sxs-lookup"><span data-stu-id="99821-124">Restart the server to ensure that the in-memory data structures are not corrupted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99821-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="99821-125">See Also</span></span>  
 [<span data-ttu-id="99821-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="99821-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
