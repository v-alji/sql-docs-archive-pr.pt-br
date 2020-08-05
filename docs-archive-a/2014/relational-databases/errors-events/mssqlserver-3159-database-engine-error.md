---
title: MSSQLSERVER_3159 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3159 (Database Engine error)
ms.assetid: c93c1003-0e3a-40aa-9873-44a0f5b8b57e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b469842b2aab15980c72ea01e46270c55ef29e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574029"
---
# <a name="mssqlserver_3159"></a><span data-ttu-id="363ab-102">MSSQLSERVER_3159</span><span class="sxs-lookup"><span data-stu-id="363ab-102">MSSQLSERVER_3159</span></span>
    
## <a name="details"></a><span data-ttu-id="363ab-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="363ab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="363ab-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="363ab-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="363ab-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="363ab-105">Event ID</span></span>|<span data-ttu-id="363ab-106">3159</span><span class="sxs-lookup"><span data-stu-id="363ab-106">3159</span></span>|  
|<span data-ttu-id="363ab-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="363ab-107">Event Source</span></span>|<span data-ttu-id="363ab-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="363ab-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="363ab-109">Componente</span><span class="sxs-lookup"><span data-stu-id="363ab-109">Component</span></span>|<span data-ttu-id="363ab-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="363ab-110">SQLEngine</span></span>|  
|<span data-ttu-id="363ab-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="363ab-111">Symbolic Name</span></span>|<span data-ttu-id="363ab-112">LDDB_LOGNOTBACKEDUP</span><span class="sxs-lookup"><span data-stu-id="363ab-112">LDDB_LOGNOTBACKEDUP</span></span>|  
|<span data-ttu-id="363ab-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="363ab-113">Message Text</span></span>|<span data-ttu-id="363ab-114">Não foi feito backup da parte final do log do banco de dados "%ls".</span><span class="sxs-lookup"><span data-stu-id="363ab-114">The tail of the log for the database "%ls" has not been backed up.</span></span> <span data-ttu-id="363ab-115">Use BACKUP LOG WITH NORECOVERY para fazer backup do log se ele contiver um trabalho que você não deseja perder.</span><span class="sxs-lookup"><span data-stu-id="363ab-115">Use BACKUP LOG WITH NORECOVERY to back up the log if it contains work that you do not want to lose.</span></span> <span data-ttu-id="363ab-116">Use a cláusula WITH REPLACE ou WITH STOPAT da instrução RESTORE para simplesmente substituir o conteúdo do log.</span><span class="sxs-lookup"><span data-stu-id="363ab-116">Use the WITH REPLACE or WITH STOPAT clause of the RESTORE statement to just overwrite the contents of the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="363ab-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="363ab-117">Explanation</span></span>  
 <span data-ttu-id="363ab-118">Na maioria dos casos, sob os modelos de recuperação bulk-logged ou de operações em massa, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requer que você faça backup do final do log para capturar os registros de log que ainda não sofreram backup.</span><span class="sxs-lookup"><span data-stu-id="363ab-118">In most cases, under the full or bulk-logged recovery models, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires that you back up the tail of the log to capture the log records that have not yet been backed up.</span></span> <span data-ttu-id="363ab-119">Um backup de log realizado no final do log imediatamente antes de uma operação de restauração é chamado de backup de final do log.</span><span class="sxs-lookup"><span data-stu-id="363ab-119">A log backup taken of the tail of the log just before a restore operation is called a tail-log backup.</span></span>  
  
 <span data-ttu-id="363ab-120">Quando você estiver recuperando um banco de dados até o ponto de uma falha, o backup do final do log é o último backup de interesse no plano de recuperação.</span><span class="sxs-lookup"><span data-stu-id="363ab-120">When you are recovering a database to the point of a failure, the tail-log backup is the last backup of interest in the recovery plan.</span></span> <span data-ttu-id="363ab-121">Se você não puder fazer backup da parte final do log, apenas será possível recuperar um banco de dados até o fim do último backup criado antes da falha.</span><span class="sxs-lookup"><span data-stu-id="363ab-121">If you cannot back up the tail of the log, you can recover a database only to the end of the last backup that was created before the failure.</span></span>  
  
 <span data-ttu-id="363ab-122">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] normalmente requer que você faça um backup do final do log antes de começar a restaurar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="363ab-122">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usually requires that you take a tail-log backup before you start to restore a database.</span></span> <span data-ttu-id="363ab-123">O backup da parte final do log impede perda de trabalho e mantém a cadeia de logs intacta.</span><span class="sxs-lookup"><span data-stu-id="363ab-123">The tail-log backup prevents work loss and keeps the log chain intact.</span></span> <span data-ttu-id="363ab-124">Porém, nem todos os cenários de restauração requerem um backup de final do log.</span><span class="sxs-lookup"><span data-stu-id="363ab-124">However, not all restore scenarios require a tail-log backup.</span></span> <span data-ttu-id="363ab-125">Você não precisará ter um backup do final do log se o ponto de recuperação estiver incluído em um backup de log anterior, ou se estiver movendo ou substituindo o banco de dados e não precisar restaurá-lo em um momento determinado após o backup mais recente.</span><span class="sxs-lookup"><span data-stu-id="363ab-125">You do not have to have a tail-log backup if the recovery point is included in an earlier log backup, or if you are moving or replacing (overwriting) the database and do not need to restore it to a point of time after the most recent backup.</span></span> <span data-ttu-id="363ab-126">Além disso, se os arquivos de log estiverem danificados e não for possível criar um backup da parte final do log, você deverá restaurar o banco de dados sem usar um backup da parte final do log.</span><span class="sxs-lookup"><span data-stu-id="363ab-126">Also, if the log files are damaged and a tail-log backup cannot be created, you must restore the database without using a tail-log backup.</span></span> <span data-ttu-id="363ab-127">Todas as transações confirmadas depois do último backup de log são perdidas.</span><span class="sxs-lookup"><span data-stu-id="363ab-127">Any transactions committed after the latest log backup are lost.</span></span> <span data-ttu-id="363ab-128">Para obter mais informações, consulte "Restaurando sem usar um backup de final do log", adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="363ab-128">For more information, see "Restoring Without Using a Tail-Log Backup," later in this topic.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="363ab-129">REPLACE raramente deve ser usado, e só depois de consideração cuidadosa.</span><span class="sxs-lookup"><span data-stu-id="363ab-129">REPLACE should be used rarely, and only after careful consideration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="363ab-130">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="363ab-130">User Action</span></span>  
 <span data-ttu-id="363ab-131">Faça um backup de final do log e tente novamente a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="363ab-131">Take a tail-log backup, and retry the restore operation.</span></span>  
  
 <span data-ttu-id="363ab-132">Se você não puder fazer um backup de final do log, use WITH STOPAT ou WITH REPLACE em suas instruções RESTORE.</span><span class="sxs-lookup"><span data-stu-id="363ab-132">If you cannot back up the tail of the log, use WITH STOPAT or WITH REPLACE in your RESTORE statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="363ab-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="363ab-133">See Also</span></span>  
 <span data-ttu-id="363ab-134">[Restaurar um banco de dados do SQL Server em um ponto específico &#40;Modelo de recuperação completa&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="363ab-134">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="363ab-135">[Faça backup do log de transações quando o banco de dados estiver danificado &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="363ab-135">[Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span></span>  
 <span data-ttu-id="363ab-136">[Fazer backup de um log de transações &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="363ab-136">[Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="363ab-137">Backups da parte final do log &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="363ab-137">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/tail-log-backups-sql-server.md)  
  
  
