---
title: MSSQLSERVER_3456 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3456 (Database Engine error)
ms.assetid: d11b2b2c-3ae4-4023-b82f-05b561bfacce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f13316bdd3147bb0ad63c8d4a2fb18f1fce74006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680968"
---
# <a name="mssqlserver_3456"></a><span data-ttu-id="fb576-102">MSSQLSERVER_3456</span><span class="sxs-lookup"><span data-stu-id="fb576-102">MSSQLSERVER_3456</span></span>
    
## <a name="details"></a><span data-ttu-id="fb576-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fb576-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb576-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="fb576-104">Product Name</span></span>|<span data-ttu-id="fb576-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb576-105">SQL Server</span></span>|  
|<span data-ttu-id="fb576-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="fb576-106">Event ID</span></span>|<span data-ttu-id="fb576-107">3456</span><span class="sxs-lookup"><span data-stu-id="fb576-107">3456</span></span>|  
|<span data-ttu-id="fb576-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="fb576-108">Event Source</span></span>|<span data-ttu-id="fb576-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fb576-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fb576-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fb576-110">Component</span></span>|<span data-ttu-id="fb576-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fb576-111">SQLEngine</span></span>|  
|<span data-ttu-id="fb576-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="fb576-112">Symbolic Name</span></span>|<span data-ttu-id="fb576-113">REC_REDOLSNMISMATCH</span><span class="sxs-lookup"><span data-stu-id="fb576-113">REC_REDOLSNMISMATCH</span></span>|  
|<span data-ttu-id="fb576-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="fb576-114">Message Text</span></span>|<span data-ttu-id="fb576-115">Não foi possível refazer o registro de log %S_LSN, para ID de transação %S_XID, na página %S_PGID, banco de dados '%.\*ls' (ID de banco de dados %d).</span><span class="sxs-lookup"><span data-stu-id="fb576-115">Could not redo log record %S_LSN, for transaction ID %S_XID, on page %S_PGID, database '%.\*ls' (database ID %d).</span></span> <span data-ttu-id="fb576-116">Página: LSN = %S_LSN, type = %ld.</span><span class="sxs-lookup"><span data-stu-id="fb576-116">Page: LSN = %S_LSN, type = %ld.</span></span> <span data-ttu-id="fb576-117">Log: OpCode = %ld, contexto %ld, PrevPageLSN: %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="fb576-117">Log: OpCode = %ld, context %ld, PrevPageLSN: %S_LSN.</span></span> <span data-ttu-id="fb576-118">Restaure de um backup do banco de dados ou repare o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb576-118">Restore from a backup of the database, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fb576-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="fb576-119">Explanation</span></span>  
 <span data-ttu-id="fb576-120">A operação de restauração não pôde refazer o log de transação.</span><span class="sxs-lookup"><span data-stu-id="fb576-120">The restore operation was unable to redo the transaction log.</span></span> <span data-ttu-id="fb576-121">Esse erro colocou o banco de dados no estado SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="fb576-121">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="fb576-122">O grupo de arquivos primário, e possivelmente outros grupos de arquivos, estão sob suspeita e podem estar danificados.</span><span class="sxs-lookup"><span data-stu-id="fb576-122">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="fb576-123">O banco de dados não pode ser recuperado durante a inicialização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e, portanto, não está disponível.</span><span class="sxs-lookup"><span data-stu-id="fb576-123">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="fb576-124">Ação do usuário é necessária para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="fb576-124">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="fb576-125">Observe que, se esse erro ocorrer para **tempdb**, a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será desativada.</span><span class="sxs-lookup"><span data-stu-id="fb576-125">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fb576-126">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="fb576-126">User Action</span></span>  
 <span data-ttu-id="fb576-127">Este erro pode ser causado por uma condição transitória existente no sistema durante uma determinada tentativa de iniciar a instância de servidor ou recuperar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb576-127">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="fb576-128">Este erro também pode ser causado por uma falha permanente que ocorre toda vez que você tenta iniciar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb576-128">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="fb576-129">Para obter informações sobre a causa, examine o Log de Eventos do Windows para procurar um erro anterior que indique a falha específica.</span><span class="sxs-lookup"><span data-stu-id="fb576-129">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="fb576-130">Para obter informações sobre a causa dessa ocorrência do erro 3456, examine o Log de Eventos do Windows para obter um erro anterior que indica a falha específica.</span><span class="sxs-lookup"><span data-stu-id="fb576-130">For information about the cause of this occurrence of error 3456, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="fb576-131">A ação do usuário adequada depende de se as informações no Log de Eventos do Windows indicam se o erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi provocado por uma condição transitória ou por uma falha permanente.</span><span class="sxs-lookup"><span data-stu-id="fb576-131">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="fb576-132">Para obter informações sobre as ações do usuário para solucionar o erro 3456, consulte os Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb576-132">For information about the user actions for troubleshooting error 3456, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb576-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb576-133">See Also</span></span>  
 <span data-ttu-id="fb576-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb576-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="fb576-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fb576-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="fb576-136">[Restaurações completas de banco de dados &#40;Modelo de recuperação simples#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="fb576-136">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="fb576-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="fb576-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="fb576-138">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb576-138">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
