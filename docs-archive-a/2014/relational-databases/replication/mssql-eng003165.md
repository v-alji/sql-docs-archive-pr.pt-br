---
title: MSSQL_ENG003165 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003165 error
ms.assetid: 707d33dd-644e-4cc9-ac51-dddd49031530
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1702588ba6ac1beeb33b87a7afc7fc330271559
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568483"
---
# <a name="mssql_eng003165"></a><span data-ttu-id="f9886-102">MSSQL_ENG003165</span><span class="sxs-lookup"><span data-stu-id="f9886-102">MSSQL_ENG003165</span></span>
    
## <a name="message-details"></a><span data-ttu-id="f9886-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="f9886-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f9886-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="f9886-104">Product Name</span></span>|<span data-ttu-id="f9886-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9886-105">SQL Server</span></span>|  
|<span data-ttu-id="f9886-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="f9886-106">Event ID</span></span>|<span data-ttu-id="f9886-107">3165</span><span class="sxs-lookup"><span data-stu-id="f9886-107">3165</span></span>|  
|<span data-ttu-id="f9886-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="f9886-108">Event Source</span></span>|<span data-ttu-id="f9886-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f9886-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f9886-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f9886-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="f9886-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="f9886-111">Symbolic Name</span></span>||  
|<span data-ttu-id="f9886-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="f9886-112">Message Text</span></span>|<span data-ttu-id="f9886-113">O banco de dados '%ls' foi restaurado; entretanto, houve um erro durante a restauração/remoção da replicação.</span><span class="sxs-lookup"><span data-stu-id="f9886-113">Database '%ls' was restored; however, an error was encountered while replication was being restored/removed.</span></span> <span data-ttu-id="f9886-114">O banco de dados foi deixado offline.</span><span class="sxs-lookup"><span data-stu-id="f9886-114">The database has been left offline.</span></span> <span data-ttu-id="f9886-115">Consulte o tópico MSSQL_ENG003165 dos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9886-115">See the topic MSSQL_ENG003165 in SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f9886-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="f9886-116">Explanation</span></span>  
 <span data-ttu-id="f9886-117">O erro será gerado se ocorrer um problema durante a restauração de um backup de um banco de dados replicado:</span><span class="sxs-lookup"><span data-stu-id="f9886-117">This error is raised if a problem occurs restoring a backup of a replicated database:</span></span>  
  
-   <span data-ttu-id="f9886-118">Se o backup estiver sendo restaurado para o mesmo banco de dados e servidor nos quais foi obtido, o erro indica que não foi possível restaurar as configurações de replicação corretamente.</span><span class="sxs-lookup"><span data-stu-id="f9886-118">If the backup is being restored to the same database and server on which it was taken, the error indicates that replication settings could not be restored properly.</span></span>  
  
-   <span data-ttu-id="f9886-119">Se o backup estiver sendo restaurado para um banco de dados ou servidor diferente, o erro indica que não foi possível remover as configurações de replicação corretamente (por padrão, as configurações de replicação são removidas se o banco de dados ou servidor for diferente).</span><span class="sxs-lookup"><span data-stu-id="f9886-119">If the backup is being restored to a different database or server, the error indicates that replication settings could not be removed properly (by default, replication settings are removed if the database or server is different).</span></span>  
  
 <span data-ttu-id="f9886-120">É provável que o erro seja resultado de uma não correspondência entre o estado de um banco de dados restaurado e um ou mais bancos de dados do sistema com metadados de replicação: banco de dados **msdb**, **mestre**ou de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f9886-120">The error is probably the result of a mismatch between the state of the restored database and one or more system databases that contain replication metadata: **msdb**, **master**, or the distribution database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f9886-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f9886-121">User Action</span></span>  
 <span data-ttu-id="f9886-122">Para resolver o problema:</span><span class="sxs-lookup"><span data-stu-id="f9886-122">To resolve this issue:</span></span>  
  
1.  <span data-ttu-id="f9886-123">Execute ALTER DATABASE para que o banco de dados fique online; por exemplo: `ALTER DATABASE AdventureWorks SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="f9886-123">Execute ALTER DATABASE to bring the database online; for example: `ALTER DATABASE AdventureWorks SET ONLINE`.</span></span> <span data-ttu-id="f9886-124">Para obter mais informações, veja [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f9886-124">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span> <span data-ttu-id="f9886-125">Se desejar preservar as configurações de replicação, vá para a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="f9886-125">If you want to preserve replication settings, go to step 2.</span></span> <span data-ttu-id="f9886-126">Caso contrário, vá para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="f9886-126">If not, go to step 3.</span></span>  
  
2.  <span data-ttu-id="f9886-127">Execute [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f9886-127">Execute [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span></span> <span data-ttu-id="f9886-128">Se esse procedimento armazenado for executado com êxito, a restauração será concluída.</span><span class="sxs-lookup"><span data-stu-id="f9886-128">If this stored procedure executes successfully, the restore is complete.</span></span> <span data-ttu-id="f9886-129">Se não for executado com êxito, vá para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="f9886-129">If it does not execute successfully, go to step 3.</span></span>  
  
3.  <span data-ttu-id="f9886-130">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para remover todas as configurações de replicação.</span><span class="sxs-lookup"><span data-stu-id="f9886-130">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove all replication settings.</span></span>  
  
     <span data-ttu-id="f9886-131">Se necessário, reconfigure a replicação.</span><span class="sxs-lookup"><span data-stu-id="f9886-131">Reconfigure replication if necessary.</span></span> <span data-ttu-id="f9886-132">Se a topologia de replicação tiver sido inserida no script conforme recomendado, você deverá usar scripts para reconfigurar a topologia.</span><span class="sxs-lookup"><span data-stu-id="f9886-132">If you have scripted the replication topology as recommended, use scripts to reconfigure the topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9886-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f9886-133">See Also</span></span>  
 <span data-ttu-id="f9886-134">[Fazer backup e restaurar bancos de dados do SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f9886-134">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="f9886-135">[Fazer backup e restaurar bancos de dados replicados](administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f9886-135">[Back Up and Restore Replicated Databases](administration/back-up-and-restore-replicated-databases.md) </span></span>  
 [<span data-ttu-id="f9886-136">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="f9886-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
