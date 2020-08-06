---
title: MSSQLSERVER_3314 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3314 (Database Engine error)
ms.assetid: f3a5ca6a-b502-4cab-b3b1-4bc753763fa9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3b891b438f71d70f5dd62174eae2c5a07d29a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581853"
---
# <a name="mssqlserver_3314"></a><span data-ttu-id="1c32a-102">MSSQLSERVER_3314</span><span class="sxs-lookup"><span data-stu-id="1c32a-102">MSSQLSERVER_3314</span></span>
    
## <a name="details"></a><span data-ttu-id="1c32a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1c32a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c32a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="1c32a-104">Product Name</span></span>|<span data-ttu-id="1c32a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1c32a-105">SQL Server</span></span>|  
|<span data-ttu-id="1c32a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="1c32a-106">Event ID</span></span>|<span data-ttu-id="1c32a-107">3314</span><span class="sxs-lookup"><span data-stu-id="1c32a-107">3314</span></span>|  
|<span data-ttu-id="1c32a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="1c32a-108">Event Source</span></span>|<span data-ttu-id="1c32a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1c32a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1c32a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1c32a-110">Component</span></span>|<span data-ttu-id="1c32a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1c32a-111">SQLEngine</span></span>|  
|<span data-ttu-id="1c32a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="1c32a-112">Symbolic Name</span></span>|<span data-ttu-id="1c32a-113">ERR_LOG_RID2</span><span class="sxs-lookup"><span data-stu-id="1c32a-113">ERR_LOG_RID2</span></span>|  
|<span data-ttu-id="1c32a-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="1c32a-114">Message Text</span></span>|<span data-ttu-id="1c32a-115">Ocorreu um erro na ID do registro de log %S_LSN ao desfazer uma operação registrada no banco de dados '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="1c32a-115">During undoing of a logged operation in database '%.\*ls', an error occurred at log record ID %S_LSN.</span></span> <span data-ttu-id="1c32a-116">Em geral, a falha específica é registrada anteriormente como um erro no serviço Log de Eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="1c32a-116">Typically, the specific failure is logged previously as an error in the Windows Event Log service.</span></span> <span data-ttu-id="1c32a-117">Repare ou restaure o banco de dados usando um backup.</span><span class="sxs-lookup"><span data-stu-id="1c32a-117">Restore the database or file from a backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1c32a-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="1c32a-118">Explanation</span></span>  
 <span data-ttu-id="1c32a-119">Trata-se de um erro de rollup ao desfazer a recuperação.</span><span class="sxs-lookup"><span data-stu-id="1c32a-119">This is a rollup error for undo recovery.</span></span> <span data-ttu-id="1c32a-120">Esse erro colocou o banco de dados no estado SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="1c32a-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="1c32a-121">O grupo de arquivos primário, e possivelmente outros grupos de arquivos, estão sob suspeita e podem estar danificados.</span><span class="sxs-lookup"><span data-stu-id="1c32a-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="1c32a-122">O banco de dados não pode ser recuperado durante a inicialização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e, portanto, não está disponível.</span><span class="sxs-lookup"><span data-stu-id="1c32a-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="1c32a-123">Ação do usuário é necessária para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="1c32a-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="1c32a-124">Observe que, se esse erro ocorrer para **tempdb**, a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será desativada.</span><span class="sxs-lookup"><span data-stu-id="1c32a-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1c32a-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="1c32a-125">User Action</span></span>  
 <span data-ttu-id="1c32a-126">Este erro pode ser causado por uma condição transitória existente no sistema durante uma determinada tentativa de iniciar a instância de servidor ou recuperar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1c32a-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="1c32a-127">Este erro também pode ser causado por uma falha permanente que ocorre toda vez que você tenta iniciar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1c32a-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="1c32a-128">Para obter informações sobre a causa, examine o Log de Eventos do Windows para procurar um erro anterior que indique a falha específica.</span><span class="sxs-lookup"><span data-stu-id="1c32a-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="1c32a-129">Para obter informações sobre a causa dessa ocorrência do erro 3314, examine o Log de Eventos do Windows para procurar um erro anterior que indique a falha específica.</span><span class="sxs-lookup"><span data-stu-id="1c32a-129">For information about the cause of this occurrence of error 3314, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="1c32a-130">A ação do usuário adequada depende de se as informações no Log de Eventos do Windows indicam se o erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi provocado por uma condição transitória ou por uma falha permanente.</span><span class="sxs-lookup"><span data-stu-id="1c32a-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="1c32a-131">Para obter informações sobre as ações do usuário para solucionar o erro 3314, consulte os Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c32a-131">For information about the user actions for troubleshooting error 3314, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c32a-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1c32a-132">See Also</span></span>  
 <span data-ttu-id="1c32a-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c32a-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="1c32a-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c32a-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="1c32a-135">[Restaurações completas de banco de dados &#40;Modelo de recuperação simples#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="1c32a-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="1c32a-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="1c32a-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="1c32a-137">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1c32a-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
