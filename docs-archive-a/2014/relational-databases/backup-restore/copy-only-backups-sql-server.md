---
title: Backups somente cópia (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- copy-only backups [SQL Server]
- COPY_ONLY option [BACKUP statement]
- backups [SQL Server], copy-only backups
ms.assetid: f82d6918-a5a7-4af8-868e-4247f5b00c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc74d7b1bba2a0163ac9edefb5d465c54ef6296c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583658"
---
# <a name="copy-only-backups-sql-server"></a><span data-ttu-id="4e42f-102">Backups somente cópia (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e42f-102">Copy-Only Backups (SQL Server)</span></span>
  <span data-ttu-id="4e42f-103">Um *backup somente cópia* é um backup do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que não depende da sequência de backups convencionais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e42f-103">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="4e42f-104">Geralmente, um backup altera o banco de dados e afeta a forma de restauração dos backups posteriores.</span><span class="sxs-lookup"><span data-stu-id="4e42f-104">Usually, taking a backup changes the database and affects how later backups are restored.</span></span> <span data-ttu-id="4e42f-105">Contudo, ocasionalmente, é útil fazer um backup para uma finalidade especial sem afetar o backup global e os procedimentos de restauração do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4e42f-105">However, occasionally, it is useful to take a backup for a special purpose without affecting the overall backup and restore procedures for the database.</span></span> <span data-ttu-id="4e42f-106">Backups de cópia servem para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="4e42f-106">Copy-only backups serve this purpose.</span></span>  
  
 <span data-ttu-id="4e42f-107">Os tipos de backups somente cópia são:</span><span class="sxs-lookup"><span data-stu-id="4e42f-107">The types of copy-only backups are as follows:</span></span>  
  
-   <span data-ttu-id="4e42f-108">Backups completos somente cópia (todos os modelos de recuperação)</span><span class="sxs-lookup"><span data-stu-id="4e42f-108">Copy-only full backups (all recovery models)</span></span>  
  
     <span data-ttu-id="4e42f-109">Um backup somente cópia não pode servir como base diferencial ou backup diferencial e não afeta a base diferencial.</span><span class="sxs-lookup"><span data-stu-id="4e42f-109">A copy-only backup cannot serve as a differential base or differential backup and does not affect the differential base.</span></span>  
  
     <span data-ttu-id="4e42f-110">Restaurar um backup completo somente cópia é o mesmo que restaurar qualquer outro backup completo.</span><span class="sxs-lookup"><span data-stu-id="4e42f-110">Restoring a copy-only full backup is the same as restoring any other full backup.</span></span>  
  
-   <span data-ttu-id="4e42f-111">Backups de log somente cópia (só modelo de recuperação completa e modelo de recuperação bulk-logged)</span><span class="sxs-lookup"><span data-stu-id="4e42f-111">Copy-only log backups (full recovery model and bulk-logged recovery model only)</span></span>  
  
     <span data-ttu-id="4e42f-112">Um backup de log somente cópia preserva o ponto de arquivo de log existente e, portanto, não afeta a sequência de backups de log regulares.</span><span class="sxs-lookup"><span data-stu-id="4e42f-112">A copy-only log backup preserves the existing log archive point and, therefore, does not affect the sequencing of regular log backups.</span></span> <span data-ttu-id="4e42f-113">Backups de log somente cópia em geral são desnecessários.</span><span class="sxs-lookup"><span data-stu-id="4e42f-113">Copy-only log backups are typically unnecessary.</span></span> <span data-ttu-id="4e42f-114">Em vez disso, você pode criar um novo backup de log de rotina (usando WITH NORECOVERY) e usar esse backup com qualquer backup de log anterior necessário para a sequência de restauração.</span><span class="sxs-lookup"><span data-stu-id="4e42f-114">Instead, you can create a new routine log backup (using WITH NORECOVERY) and use that backup together with any previous log backups that are required for the restore sequence.</span></span> <span data-ttu-id="4e42f-115">No entanto, um backup de log somente cópia pode ser útil às vezes para executar uma restauração online.</span><span class="sxs-lookup"><span data-stu-id="4e42f-115">However, a copy-only log backup can sometimes be useful for performing an online restore.</span></span> <span data-ttu-id="4e42f-116">Para um exemplo disso, consulte [Exemplo: Restauração online de um arquivo de leitura/gravação #40;Modelo de recuperação completa&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="4e42f-116">For an example of this, see [Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span></span>  
  
     <span data-ttu-id="4e42f-117">O log de transações nunca é truncado após um backup somente cópia.</span><span class="sxs-lookup"><span data-stu-id="4e42f-117">The transaction log is never truncated after a copy-only backup.</span></span>  
  
 <span data-ttu-id="4e42f-118">Backups somente cópia são registrados na coluna **is_copy_only** da tabela [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4e42f-118">Copy-only backups are recorded in the **is_copy_only** column of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) table.</span></span>  
  
## <a name="to-create-a-copy-only-backup"></a><span data-ttu-id="4e42f-119">Para criar um backup somente cópia</span><span class="sxs-lookup"><span data-stu-id="4e42f-119">To Create a Copy-Only Backup</span></span>  
 <span data-ttu-id="4e42f-120">Você pode criar um backup somente cópia usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e42f-120">You can create a copy-only backup by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4e42f-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e42f-121">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="4e42f-122">Na página **Geral** da caixa de diálogo de **Banco de Dados de Backup**, selecione a opção **Backup somente cópia**.</span><span class="sxs-lookup"><span data-stu-id="4e42f-122">On the **General** page of the **Back Up Database** dialog box, select the **Copy Only Backup** option.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4e42f-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4e42f-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="4e42f-124">A sintaxe [!INCLUDE[tsql](../../../includes/tsql-md.md)] essencial é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="4e42f-124">The essential [!INCLUDE[tsql](../../../includes/tsql-md.md)] syntax is as follows:</span></span>  
  
-   <span data-ttu-id="4e42f-125">Para um backup completo somente cópia:</span><span class="sxs-lookup"><span data-stu-id="4e42f-125">For a copy-only full backup:</span></span>  
  
     <span data-ttu-id="4e42f-126">*Database_name* de banco de dados de backup para \<backup_device*> \*... COM COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="4e42f-126">BACKUP DATABASE *database_name* TO \<backup_device*>\* ... WITH COPY_ONLY ...</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4e42f-127">COPY_ONLY não tem nenhum efeito quando é especificado com a opção DIFFERENTIAL.</span><span class="sxs-lookup"><span data-stu-id="4e42f-127">COPY_ONLY has no effect when specified with the DIFFERENTIAL option.</span></span>  
  
-   <span data-ttu-id="4e42f-128">Para um backup de log somente cópia:</span><span class="sxs-lookup"><span data-stu-id="4e42f-128">For a copy-only log backup:</span></span>  
  
     <span data-ttu-id="4e42f-129">*Database_name* de log de backup para *\<*backup_device*>* ... COM COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="4e42f-129">BACKUP LOG *database_name* TO *\<*backup_device*>* ... WITH COPY_ONLY ...</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4e42f-130">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e42f-130">Using PowerShell</span></span>  
  
<span data-ttu-id="4e42f-131">Use o cmdlet `Backup-SqlDatabase` com o parâmetro `-CopyOnly`.</span><span class="sxs-lookup"><span data-stu-id="4e42f-131">Use the `Backup-SqlDatabase` cmdlet with the `-CopyOnly` parameter.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4e42f-132">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4e42f-132">Related Tasks</span></span>  

### <a name="to-create-a-full-or-log-backup"></a><span data-ttu-id="4e42f-133">Para criar um backup completo ou de log</span><span class="sxs-lookup"><span data-stu-id="4e42f-133">To create a full or log backup</span></span>
  
-   [<span data-ttu-id="4e42f-134">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4e42f-134">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="4e42f-135">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4e42f-135">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
### <a name="to-view-copy-only-backups"></a><span data-ttu-id="4e42f-136">Para exibir backups somente cópia</span><span class="sxs-lookup"><span data-stu-id="4e42f-136">To view copy-only backups</span></span>
  
-   [<span data-ttu-id="4e42f-137">conjunto de backup &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4e42f-137">backupset &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
### <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><span data-ttu-id="4e42f-138">Para configurar e usar o provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e42f-138">To set up and use the SQL Server PowerShell provider</span></span>
  
-   [<span data-ttu-id="4e42f-139">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e42f-139">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  

## <a name="see-also"></a><span data-ttu-id="4e42f-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e42f-140">See Also</span></span>  
 <span data-ttu-id="4e42f-141">[Visão geral do backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4e42f-141">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="4e42f-142">[Modelos de recuperação &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4e42f-142">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="4e42f-143">[Copiar bancos de dados com backup e restauração](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="4e42f-143">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="4e42f-144">Visão geral de restauração e recuperação &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4e42f-144">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
