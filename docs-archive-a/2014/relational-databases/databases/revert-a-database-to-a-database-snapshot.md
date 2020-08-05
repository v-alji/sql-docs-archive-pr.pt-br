---
title: Reverter um banco de dados para um instantâneo do banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], reverting to
- reverting databases
ms.assetid: 8f74dd31-c9ca-4537-8760-0c7648f0787d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1c78da3d7c559309c0563760e7062f01cf784648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573096"
---
# <a name="revert-a-database-to-a-database-snapshot"></a><span data-ttu-id="afdce-102">Reverter um banco de dados a um instantâneo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="afdce-102">Revert a Database to a Database Snapshot</span></span>
  <span data-ttu-id="afdce-103">Se os dados em um banco de dados online forem danificados, em alguns casos, reverter o banco de dados para um instantâneo do banco de dados que preceda o dano pode ser uma alternativa apropriada para restaurar o banco de dados de um backup.</span><span class="sxs-lookup"><span data-stu-id="afdce-103">If data in an online database becomes damaged, in some cases, reverting the database to a database snapshot that predates the damage might be an appropriate alternative to restoring the database from a backup.</span></span> <span data-ttu-id="afdce-104">Por exemplo, reverter um banco de dados pode ser útil para reverter um erro sério recente de usuário, como uma tabela descartada.</span><span class="sxs-lookup"><span data-stu-id="afdce-104">For example, reverting a database might be useful for reverse a recent serious user error, such as a dropped table.</span></span> <span data-ttu-id="afdce-105">Porém, todas as mudanças feitas depois que o instantâneo foi criado serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="afdce-105">However, all changes made after the snapshot was created are lost.</span></span>  
  
-   <span data-ttu-id="afdce-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="afdce-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="afdce-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="afdce-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="afdce-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="afdce-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="afdce-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="afdce-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="afdce-110">**Para reverter um banco de dados para um instantâneo do banco de dados usando:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="afdce-110">**To Revert a Database to a Database Snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="afdce-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="afdce-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="afdce-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="afdce-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="afdce-113">Não há suporte para a reversão nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="afdce-113">Reverting is unsupported under the following conditions:</span></span>  
  
-   <span data-ttu-id="afdce-114">O banco de dados deve ter somente um instantâneo do banco de dados no momento, para o qual você planeja reverter.</span><span class="sxs-lookup"><span data-stu-id="afdce-114">The database must currently have only one database snapshot, to which you plan to revert.</span></span>  
  
-   <span data-ttu-id="afdce-115">Grupos de arquivos somente leitura ou compactados existem no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-115">Any read-only or compressed filegroups exist in the database.</span></span>  
  
-   <span data-ttu-id="afdce-116">Há algum arquivo offline agora, mas que estava online quando o instantâneo foi criado.</span><span class="sxs-lookup"><span data-stu-id="afdce-116">Any files are now offline but were online when the snapshot was created.</span></span>  
  
 <span data-ttu-id="afdce-117">Antes de reverter um banco de dados, considere as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="afdce-117">Before reverting a database, consider the following limitations:</span></span>  
  
-   <span data-ttu-id="afdce-118">Reverter não é destinado à recuperação de mídia.</span><span class="sxs-lookup"><span data-stu-id="afdce-118">Reverting is not intended for media recovery.</span></span> <span data-ttu-id="afdce-119">.</span><span class="sxs-lookup"><span data-stu-id="afdce-119">.</span></span> <span data-ttu-id="afdce-120">Um instantâneo do banco de dados é uma cópia incompleta dos arquivos de banco de dados. Assim, se o banco de dados ou o instantâneo do banco de dados estiver corrompido, reverter de um instantâneo será praticamente impossível.</span><span class="sxs-lookup"><span data-stu-id="afdce-120">A database snapshot is an incomplete copy of the database files, so if either the database or the database snapshot is corrupted, reverting from a snapshot is likely to be impossible.</span></span> <span data-ttu-id="afdce-121">Além disso, mesmo quando isso é possível, é improvável que a reversão corrija o problema no caso de corrupção.</span><span class="sxs-lookup"><span data-stu-id="afdce-121">Furthermore, even when it is possible, reverting in the event of corruption is unlikely to correct the problem.</span></span> <span data-ttu-id="afdce-122">Portanto, é essencial fazer backups e testar regularmente seu plano de restauração para proteger um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-122">Therefore, taking regular backups and testing your restore plan are essential to protect a database.</span></span> <span data-ttu-id="afdce-123">Para obter mais informações, consulte [Fazer backup e restaurar bancos de dados do SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-123">For more information, see [Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="afdce-124">Se você precisa ser capaz de restaurar o banco de dados de origem para o momento determinado em que o instantâneo do banco de dados foi criado, use um modelo de recuperação completo e implemente uma política de backup que permita fazer isso.</span><span class="sxs-lookup"><span data-stu-id="afdce-124">If you need to be able to restore the source database to the point in time at which you created a database snapshot, use the full recovery model and implement a backup policy that enables you to do that.</span></span>  
  
-   <span data-ttu-id="afdce-125">O banco de dados de origem original é substituído pelo banco de dados revertido. Assim, as atualizações feitas no banco de dados desde a criação do instantâneo são perdidas.</span><span class="sxs-lookup"><span data-stu-id="afdce-125">The original source database is overwritten by the reverted database, so any updates to the database since the snapshot's creation are lost.</span></span>  
  
-   <span data-ttu-id="afdce-126">A operação de reversão também substitui o arquivo de log antigo e recria o log.</span><span class="sxs-lookup"><span data-stu-id="afdce-126">The revert operation also overwrites the old log file and rebuilds the log.</span></span> <span data-ttu-id="afdce-127">Consequentemente, você não pode fazer roll forward do banco de dados revertido para o ponto do erro do usuário.</span><span class="sxs-lookup"><span data-stu-id="afdce-127">Consequently, you cannot roll the reverted database forward to the point of user error.</span></span> <span data-ttu-id="afdce-128">Portanto, recomendamos que você faça backup do log antes de reverter um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-128">Therefore, we recommend that you back up the log before reverting a database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="afdce-129">Embora você não possa restaurar o registro original para roll-forward do banco de dados, a informações no arquivo de log original pode ser útil para reconstruir os dados perdidos.</span><span class="sxs-lookup"><span data-stu-id="afdce-129">Although you cannot restore the original log to roll forward the database, the information in the original log file can be useful for reconstructing lost data.</span></span>  
  
-   <span data-ttu-id="afdce-130">A reversão quebra a cadeia de backup de log.</span><span class="sxs-lookup"><span data-stu-id="afdce-130">Reverting breaks the log backup chain.</span></span> <span data-ttu-id="afdce-131">Então, antes de fazer o backup de log do banco de dados revertido, você deve primeiro fazer um backup do banco de dados completo ou um backup de arquivo.</span><span class="sxs-lookup"><span data-stu-id="afdce-131">Therefore, before you can take log backups of the reverted database, you must first take a full database backup or file backup.</span></span> <span data-ttu-id="afdce-132">Recomendamos um backup de banco de dados completo.</span><span class="sxs-lookup"><span data-stu-id="afdce-132">We recommend a full database backup.</span></span>  
  
-   <span data-ttu-id="afdce-133">Durante uma operação de reversão, o instantâneo e o banco de dados de origem ficam indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="afdce-133">During a revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="afdce-134">O instantâneo e o banco de dados de origem são ambos marcados como “Em restauração”.</span><span class="sxs-lookup"><span data-stu-id="afdce-134">The source database and snapshot are both marked "In restore."</span></span> <span data-ttu-id="afdce-135">Se ocorrer um erro durante a operação de reversão, quando o banco de dados for novamente inicializado, a operação de reversão tentará terminar a reversão.</span><span class="sxs-lookup"><span data-stu-id="afdce-135">If an error occurs during the revert operation, when the database starts up again, the revert operation will try to finish reverting.</span></span>  
  
-   <span data-ttu-id="afdce-136">Os metadados de um banco de dados revertido são iguais aos metadados na hora do instantâneo.</span><span class="sxs-lookup"><span data-stu-id="afdce-136">The metadata of a reverted database is the same as the metadata at the time of the snapshot.</span></span>  
  
-   <span data-ttu-id="afdce-137">A reversão cancela todos os catálogos de texto completo.</span><span class="sxs-lookup"><span data-stu-id="afdce-137">Reverting drops all the full-text catalogs.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="afdce-138">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="afdce-138">Prerequisites</span></span>  
 <span data-ttu-id="afdce-139">Verifique se o banco de dados de origem e o instantâneo do banco de dados atendem aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="afdce-139">Ensure that the source database and database snapshot meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="afdce-140">Verifique se o banco de dados não foi corrompido.</span><span class="sxs-lookup"><span data-stu-id="afdce-140">Verify that the database has not become corrupted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="afdce-141">Se o banco de dados tiver sido corrompido, você precisará restaurá-lo de backups.</span><span class="sxs-lookup"><span data-stu-id="afdce-141">If the database has been corrupted, you will need to restore it from backups.</span></span> <span data-ttu-id="afdce-142">Para obter mais informações, veja [Restaurações completas de banco de dados &#40;Modelo de recuperação simples#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) ou [Restaurações completas de banco de dados &#40;Modelo de recuperação completa#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-142">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](../backup-restore/complete-database-restores-full-recovery-model.md).</span></span>  
  
-   <span data-ttu-id="afdce-143">Identifique um instantâneo recente que foi criado antes do erro.</span><span class="sxs-lookup"><span data-stu-id="afdce-143">Identify a recent snapshot that was created before the error.</span></span> <span data-ttu-id="afdce-144">Para obter mais informações, veja [Exibir um instantâneo de banco de dados &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-144">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
-   <span data-ttu-id="afdce-145">Descarte todos os outros instantâneos que existem no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-145">Drop any other snapshots that currently exist on the database.</span></span> <span data-ttu-id="afdce-146">Para obter mais informações, veja [Remover um instantâneo do banco de dados &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-146">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="afdce-147">Segurança</span><span class="sxs-lookup"><span data-stu-id="afdce-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="afdce-148">Permissões</span><span class="sxs-lookup"><span data-stu-id="afdce-148">Permissions</span></span>  
 <span data-ttu-id="afdce-149">Qualquer usuário que tenha permissões RESTORE DATABASE no banco de dados de origem pode revertê-lo ao estado em que estava quando o instantâneo de banco de dados foi criado.</span><span class="sxs-lookup"><span data-stu-id="afdce-149">Any user who has RESTORE DATABASE permissions on the source database can revert it to its state when a database snapshot was created.</span></span>  
  
##  <a name="how-to-revert-a-database-to-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="afdce-150">Como reverter o banco de dados para um instantâneo do banco de dados (usando Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="afdce-150">How to Revert a Database to a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="afdce-151">**Para reverter um banco de dados a um instantâneo do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="afdce-151">**To revert a database to a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afdce-152">Para obter um exemplo deste procedimento, consulte [Exemplos (Transact-SQL)](#TsqlExample), posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="afdce-152">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="afdce-153">Identifique o instantâneo do banco de dados para o qual você quer reverter o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-153">Identify the database snapshot to which you want to revert the database.</span></span> <span data-ttu-id="afdce-154">É possível exibir os instantâneos em um banco de dados do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (veja [Exibir um instantâneo de banco de dados &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="afdce-154">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md)).</span></span> <span data-ttu-id="afdce-155">Além disso, você pode identificar o banco de dados de origem em uma exibição da coluna **source_database_id** da exibição dr catálogo [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="afdce-155">Also, you can identify the source database of a view from the **source_database_id** column of the [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
2.  <span data-ttu-id="afdce-156">Cancele qualquer outro instantâneo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-156">Drop any other database snapshots.</span></span>  
  
     <span data-ttu-id="afdce-157">Para obter informações sobre como remover instantâneos, veja [Remover um instantâneo do banco de dados &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-157">For information on dropping snapshots, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span> <span data-ttu-id="afdce-158">Se o banco de dados usar o modelo de recuperação completa, antes de fazer a reversão, você deve fazer o backup do log.</span><span class="sxs-lookup"><span data-stu-id="afdce-158">If the database uses the full recovery model, before reverting, you should back up the log.</span></span> <span data-ttu-id="afdce-159">Para obter mais informações, veja [Fazer backup do log de transações &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) ou [Fazer backup do log de transações quando o banco de dados está danificado &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-159">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) or [Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="afdce-160">Execute a operação de reversão.</span><span class="sxs-lookup"><span data-stu-id="afdce-160">Perform the revert operation.</span></span>  
  
     <span data-ttu-id="afdce-161">Uma operação de reversão requer permissões RESTORE DATABASE no banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="afdce-161">A revert operation requires RESTORE DATABASE permissions on the source database.</span></span> <span data-ttu-id="afdce-162">Para reverter o banco de dados, use a seguinte instrução Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="afdce-162">To revert the database, use the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="afdce-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=** _database_snapshot_name_</span><span class="sxs-lookup"><span data-stu-id="afdce-163">RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=**_database_snapshot_name_</span></span>  
  
     <span data-ttu-id="afdce-164">Em que *database_name* é o banco de dados de origem e *database_snapshot_name* é o nome do instantâneo para o qual você deseja reverter o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-164">Where *database_name* is the source database and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="afdce-165">Observe que nessa instrução, você deve especificar um nome de instantâneo em vez de um dispositivo de backup.</span><span class="sxs-lookup"><span data-stu-id="afdce-165">Notice that in this statement, you must specify a snapshot name rather than a backup device.</span></span>  
  
     <span data-ttu-id="afdce-166">Para obter mais informações, veja [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="afdce-166">For more information, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="afdce-167">Durante a operação de reversão, o instantâneo e o banco de dados de origem estão indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="afdce-167">During the revert operation, both the snapshot and the source database are unavailable.</span></span> <span data-ttu-id="afdce-168">O instantâneo e o banco de dados de origem ficam ambos marcados como “Em restauração”.</span><span class="sxs-lookup"><span data-stu-id="afdce-168">The source database and snapshot are both marked as "In restore."</span></span> <span data-ttu-id="afdce-169">Se ocorrer um erro durante a operação de reversão, ela tentará terminar a reversão quando o banco de dados for novamente inicializado.</span><span class="sxs-lookup"><span data-stu-id="afdce-169">If an error occurs during the revert operation, it will try to finish reverting when the database starts up again.</span></span>  
  
4.  <span data-ttu-id="afdce-170">Se o proprietário do banco de dados mudou desde a criação do instantâneo do banco de dados, convém atualizar o proprietário do banco de dados do banco de dados revertido.</span><span class="sxs-lookup"><span data-stu-id="afdce-170">If the database owner changed since creation of the database snapshot, you may want to update the database owner of the reverted database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="afdce-171">O banco de dados revertido retém as permissões e configuração (como proprietário de banco de dados e modelo de recuperação) do instantâneo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-171">The reverted database retains the permissions and configuration (such as database owner and recovery model) of the database snapshot.</span></span>  
  
5.  <span data-ttu-id="afdce-172">Inicie o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afdce-172">Start the database.</span></span>  
  
6.  <span data-ttu-id="afdce-173">Opcionalmente, faça backup do banco de dados revertido, especialmente se usar o modelo de recuperação completa (ou registrada em massa).</span><span class="sxs-lookup"><span data-stu-id="afdce-173">Optionally, back up the reverted database, especially if it uses the full (or bulk-logged) recovery model.</span></span> <span data-ttu-id="afdce-174">Para fazer backup de um banco de dados, veja [Criar um backup completo de banco de dados &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-174">To back up a database, see [Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="afdce-175">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="afdce-175">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="afdce-176">Esta seção contém os seguintes exemplos de reversão de um banco de dados para um instantâneo do banco de dados:</span><span class="sxs-lookup"><span data-stu-id="afdce-176">This section contains the following examples of reverting a database to a database snapshot:</span></span>  
  
-   <span data-ttu-id="afdce-177">a.</span><span class="sxs-lookup"><span data-stu-id="afdce-177">A.</span></span> [<span data-ttu-id="afdce-178">Revertendo um instantâneo no banco de dados AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="afdce-178">Reverting a snapshot on the AdventureWorks database</span></span>](#Reverting_AW)  
  
-   <span data-ttu-id="afdce-179">B.</span><span class="sxs-lookup"><span data-stu-id="afdce-179">B.</span></span> [<span data-ttu-id="afdce-180">Revertendo um instantâneo no banco de dados Sales</span><span class="sxs-lookup"><span data-stu-id="afdce-180">Reverting a snapshot on the Sales database</span></span>](#Reverting_Sales)  
  
####  <a name="a-reverting-a-snapshot-on-the-adventureworks-database"></a><a name="Reverting_AW"></a> <span data-ttu-id="afdce-181">A.</span><span class="sxs-lookup"><span data-stu-id="afdce-181">A.</span></span> <span data-ttu-id="afdce-182">Revertendo um instantâneo no banco de dados AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="afdce-182">Reverting a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="afdce-183">Este exemplo presume que existe apenas um instantâneo atualmente no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afdce-183">This example assumes that only one snapshot currently exists on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="afdce-184">Por obter o exemplo que cria o instantâneo para o qual o banco de dados é revertido, veja [Criar um instantâneo de banco de dados &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-184">For the example that creates the snapshot to which the database is reverted here, see [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
USE master;  
-- Reverting AdventureWorks to AdventureWorks_dbss1800  
RESTORE DATABASE AdventureWorks from   
DATABASE_SNAPSHOT = 'AdventureWorks_dbss1800';  
GO  
```  
  
####  <a name="b-reverting-a-snapshot-on-the-sales-database"></a><a name="Reverting_Sales"></a> <span data-ttu-id="afdce-185">B.</span><span class="sxs-lookup"><span data-stu-id="afdce-185">B.</span></span> <span data-ttu-id="afdce-186">Revertendo um instantâneo no banco de dados Sales</span><span class="sxs-lookup"><span data-stu-id="afdce-186">Reverting a snapshot on the Sales database</span></span>  
 <span data-ttu-id="afdce-187">Este exemplo presume que existem dois instantâneos atualmente no banco de dados **Sales** : **sales_snapshot0600** e **sales_snapshot1200**.</span><span class="sxs-lookup"><span data-stu-id="afdce-187">This example assumes that two snapshots currently exist on the **Sales** database: **sales_snapshot0600** and **sales_snapshot1200**.</span></span> <span data-ttu-id="afdce-188">O exemplo exclui o mais antigo dos instantâneos e reverte o banco de dados para o instantâneo mais recente.</span><span class="sxs-lookup"><span data-stu-id="afdce-188">The example deletes the older of the snapshots and reverts the database to the more recent snapshot.</span></span>  
  
 <span data-ttu-id="afdce-189">Para obter o código para criar o banco de dados de exemplo e instantâneos dos quais esse exemplo depende, consulte:</span><span class="sxs-lookup"><span data-stu-id="afdce-189">For the code for creating the sample database and snapshots on which this example depends, see:</span></span>  
  
-   <span data-ttu-id="afdce-190">Para obter o banco de dados **Sales** e o instantâneo **sales_snapshot0600**, veja “Criando um banco de dados com grupos de arquivo” e “Criando um instantâneo de banco de dados” em [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="afdce-190">For the **Sales** database and the **sales_snapshot0600** snapshot, see "Creating a database with filegroups" and "Creating a database snapshot" in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
-   <span data-ttu-id="afdce-191">Para obter o banco de dados **sales_snapshot1200** , veja “Criando um instantâneo do banco de dados Sales” em [Criar um instantâneo de banco de dados &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="afdce-191">For the **sales_snapshot1200** snapshot, see "Creating a snapshot on the Sales database" in [Create a Database Snapshot &#40;Transact-SQL&#41;](create-a-database-snapshot-transact-sql.md).</span></span>  
  
```  
--Test to see if sales_snapshot0600 exists and if it   
-- does, delete it.  
IF EXISTS (SELECT dbid FROM sys.databases  
    WHERE NAME='sales_snapshot0600')  
    DROP DATABASE SalesSnapshot0600;  
GO  
-- Reverting Sales to sales_snapshot1200  
USE master;  
RESTORE DATABASE Sales FROM DATABASE_SNAPSHOT = 'sales_snapshot1200';  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="afdce-192">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="afdce-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="afdce-193">Criar um instantâneo de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="afdce-193">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="afdce-194">Exibir um instantâneo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="afdce-194">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="afdce-195">Remover um instantâneo do banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="afdce-195">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="afdce-196">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="afdce-196">See Also</span></span>  
 <span data-ttu-id="afdce-197">[Instantâneos de banco de dados &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="afdce-197">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="afdce-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afdce-198">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="afdce-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afdce-199">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="afdce-200">Espelhamento de banco de dados e instantâneos de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="afdce-200">Database Mirroring and Database Snapshots &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-and-database-snapshots-sql-server.md)  
  
  
