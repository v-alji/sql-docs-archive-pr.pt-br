---
title: Exibir ou alterar o modelo de recuperação de um banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], recovery models
- recovery [SQL Server], recovery model
- backing up databases [SQL Server], recovery models
- recovery models [SQL Server], switching
- recovery models [SQL Server], viewing
- database restores [SQL Server], recovery models
- modifying database recovery models
ms.assetid: 94918d1d-7c10-4be7-bf9f-27e00b003a0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889080301109938f0514bd6b81265c100237ab60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681706"
---
# <a name="view-or-change-the-recovery-model-of-a-database-sql-server"></a><span data-ttu-id="aa056-102">Exibir ou alterar o modelo de recuperação de um banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="aa056-102">View or Change the Recovery Model of a Database (SQL Server)</span></span>
  <span data-ttu-id="aa056-103">Este tópico descreve como exibir ou alterar o modelo de recuperação de um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa056-103">This topic describes how to view or change the recovery model of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="aa056-104">Um *modelo de recuperação* é uma propriedade de banco de dados que controla como as transações são registradas, se o log de transações exige (e permite) backup e que tipos de operações de restauração estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="aa056-104">A *recovery model* is a database property that controls how transactions are logged, whether the transaction log requires (and allows) backing up, and what kinds of restore operations are available.</span></span> <span data-ttu-id="aa056-105">Existem três modelos de recuperação: simples, completo e bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="aa056-105">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="aa056-106">Geralmente, um banco de dados usa o modelo de recuperação completa ou o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="aa056-106">Typically, a database uses the full recovery model or simple recovery model.</span></span> <span data-ttu-id="aa056-107">É possível alternar para outro modelo de recuperação do banco de dados a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="aa056-107">A database can be switched to another recovery model at any time.</span></span> <span data-ttu-id="aa056-108">Os banco de dados **modelo** define o modelo de recuperação padrão de novos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="aa056-108">The **model** database sets the default recovery model of new databases.</span></span>  
  
 <span data-ttu-id="aa056-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="aa056-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aa056-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="aa056-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aa056-111">Recomendações</span><span class="sxs-lookup"><span data-stu-id="aa056-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="aa056-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="aa056-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aa056-113">**Para exibir ou alterar o modelo de recuperação de um banco de dados, usando:**</span><span class="sxs-lookup"><span data-stu-id="aa056-113">**To view or change the recovery model of a database, using:**</span></span>  
  
     [<span data-ttu-id="aa056-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa056-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="aa056-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa056-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="aa056-116">**Recomendações de acompanhamento:**  [depois que você alterar o modelo de recuperação](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="aa056-116">**Follow Up Recommendations:**  [After You Change the Recovery Model](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="aa056-117">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="aa056-117">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aa056-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="aa056-118">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="aa056-119">Recomendações</span><span class="sxs-lookup"><span data-stu-id="aa056-119">Recommendations</span></span>  
  
-   <span data-ttu-id="aa056-120">Antes de mudar de modelo de recuperação completa ou de recuperação bulk-logged, faça o backup do log de transações.</span><span class="sxs-lookup"><span data-stu-id="aa056-120">Before switching from the full recovery or bulk-logged recovery model, back up the transaction log.</span></span>  
  
-   <span data-ttu-id="aa056-121">A recuperação pontual não é possível com modelo bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="aa056-121">Point-in-time recovery is not possible with bulk-logged model.</span></span> <span data-ttu-id="aa056-122">Portanto, se você executar transações sob o modelo de recuperação bulk-logged que pode exigir uma restauração do log de transação, estas transações estarão sujeitas a perda de dados.</span><span class="sxs-lookup"><span data-stu-id="aa056-122">Therefore, if you run transactions under the bulk-logged recovery model that might require a transaction log restore, these transactions could be exposed to data loss.</span></span> <span data-ttu-id="aa056-123">Para maximizar a recuperabilidade de dados em um cenário de recuperação de desastres, recomendamos que você alterne para o modelo de recuperação bulk-logged somente nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="aa056-123">To maximize data recoverability in a disaster-recovery scenario, we recommend that you switch to the bulk-logged recovery model only under the following conditions:</span></span>  
  
    -   <span data-ttu-id="aa056-124">Atualmente, não são permitidos usuários no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aa056-124">Users are currently not allowed in the database.</span></span>  
  
    -   <span data-ttu-id="aa056-125">Todas as modificações feitas durante o processamento em massa são recuperáveis sem depender de fazer um backup de log; por exemplo, executar novamente os processos em massa.</span><span class="sxs-lookup"><span data-stu-id="aa056-125">All modifications made during bulk processing are recoverable without depending on taking a log backup; for example, by re-running the bulk processes.</span></span>  
  
     <span data-ttu-id="aa056-126">Se você atender a estas duas condições, não será exposto a perda de dados enquanto estiver restaurando um log de transação que teve o backup feito no modelo de recuperação bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="aa056-126">If you satisfy these two conditions, you will not be exposed to any data loss while restoring a transaction log that was backed up under the bulk-logged recovery model..</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa056-127">Se você alternar para o modelo de recuperação completa durante uma operação em massa, o registro em log da operação em massa passará de registro em log mínimo para registro em log completo, e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="aa056-127">If you switch to the full recovery model during a bulk operation, the logging of the bulk operation changes from minimal logging to full logging, and vice versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aa056-128">Segurança</span><span class="sxs-lookup"><span data-stu-id="aa056-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aa056-129">Permissões</span><span class="sxs-lookup"><span data-stu-id="aa056-129">Permissions</span></span>  
 <span data-ttu-id="aa056-130">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aa056-130">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aa056-131">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa056-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-recovery-model"></a><span data-ttu-id="aa056-132">Para exibir ou alterar o modelo de recuperação</span><span class="sxs-lookup"><span data-stu-id="aa056-132">To view or change the recovery model</span></span>  
  
1.  <span data-ttu-id="aa056-133">Depois de conectar-se à instância adequada do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], no Pesquisador de Objeto, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa056-133">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="aa056-134">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="aa056-134">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="aa056-135">Clique com o botão direito do mouse no banco de dados e clique em **Propriedades**, o que abrirá a caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="aa056-135">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="aa056-136">No painel **Selecionar uma página** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="aa056-136">In the **Select a page** pane, click **Options**.</span></span>  
  
5.  <span data-ttu-id="aa056-137">O modelo de recuperação atual é exibido na caixa de listagem **Modelo de Recuperação** .</span><span class="sxs-lookup"><span data-stu-id="aa056-137">The current recovery model is displayed in the **Recovery model** list box.</span></span>  
  
6.  <span data-ttu-id="aa056-138">Opcionalmente, para alterar o modelo de recuperação, selecione uma lista de modelos diferente.</span><span class="sxs-lookup"><span data-stu-id="aa056-138">Optionally, to change the recovery model select a different model list.</span></span> <span data-ttu-id="aa056-139">As escolhas são **Completo**, **Bulk-logged**ou **Simples**.</span><span class="sxs-lookup"><span data-stu-id="aa056-139">The choices are **Full**, **Bulk-logged**, or **Simple**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="aa056-140">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa056-140">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-recovery-model"></a><span data-ttu-id="aa056-141">Para exibir o modelo de recuperação</span><span class="sxs-lookup"><span data-stu-id="aa056-141">To view the recovery model</span></span>  
  
1.  <span data-ttu-id="aa056-142">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa056-142">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa056-143">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="aa056-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aa056-144">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="aa056-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="aa056-145">Este exemplo mostra como consultar a exibição de catálogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) para aprender o modelo de recuperação do banco de dados **modelo** .</span><span class="sxs-lookup"><span data-stu-id="aa056-145">This example shows how to query the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to learn the recovery model of the **model** database.</span></span>  
  
```sql  
SELECT name, recovery_model_desc  
   FROM sys.databases  
      WHERE name = 'model' ;  
GO  
  
```  
  
#### <a name="to-change-the-recovery-model"></a><span data-ttu-id="aa056-146">Para alterar o modelo de recuperação</span><span class="sxs-lookup"><span data-stu-id="aa056-146">To change the recovery model</span></span>  
  
1.  <span data-ttu-id="aa056-147">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa056-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa056-148">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="aa056-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aa056-149">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="aa056-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="aa056-150">Este exemplo mostra como alterar o modelo de recuperação no banco de dados `model` para `FULL` usando a opção `SET RECOVERY` da instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="aa056-150">This example shows how to change the recovery model in the `model` database to `FULL` by using the `SET RECOVERY` option of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement.</span></span>  
  
```sql  
USE master ;  
ALTER DATABASE model SET RECOVERY FULL ;  
```  
  
##  <a name="follow-up-recommendations-after-you-change-the-recovery-model"></a><a name="FollowUp"></a><span data-ttu-id="aa056-151">Recomendações de acompanhamento: depois de alterar o modelo de recuperação</span><span class="sxs-lookup"><span data-stu-id="aa056-151">Follow Up Recommendations: After You Change the Recovery Model</span></span>  
  
-   <span data-ttu-id="aa056-152">**Depois de alternar entre os modelos de recuperação completa e bulk-logged**</span><span class="sxs-lookup"><span data-stu-id="aa056-152">**After switching between the full and bulk-logged recovery models**</span></span>  
  
    -   <span data-ttu-id="aa056-153">Depois de concluir as operações em massa, retorne imediatamente para o modo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="aa056-153">After completing the bulk operations, immediately switch back to full recovery mode.</span></span>  
  
    -   <span data-ttu-id="aa056-154">Depois de alternar do modelo de recuperação bulk-logged novamente para o modelo de recuperação completa, faça backup do log.</span><span class="sxs-lookup"><span data-stu-id="aa056-154">After switching from the bulk-logged recovery model back to the full recovery model, back up the log.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="aa056-155">Sua estratégia de backup permanecerá a mesma: continue executando backups periódicos do banco de dados, do log e backups diferenciais.</span><span class="sxs-lookup"><span data-stu-id="aa056-155">Your backup strategy remains the same: continue performing periodic database, log, and differential backups.</span></span>  
  
-   <span data-ttu-id="aa056-156">**Depois de alternar do modelo de recuperação simples**</span><span class="sxs-lookup"><span data-stu-id="aa056-156">**After switching from the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="aa056-157">Imediatamente depois de alternar para a troca para o modelo de recuperação completa ou modelo de recuperação bulk-logged, faça um backup completo ou diferencial de banco de dados para iniciar a cadeia de logs.</span><span class="sxs-lookup"><span data-stu-id="aa056-157">Immediately after switching to the full recovery model or bulk-logged recovery model, take a full or differential database backup to start the log chain.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="aa056-158">A alternância para o modelo de recuperação completa ou com log de operações em massa só entrará em vigor depois do primeiro backup de dados.</span><span class="sxs-lookup"><span data-stu-id="aa056-158">The switch to the full or bulk-logged recovery model takes effect only after the first data backup.</span></span>  
  
    -   <span data-ttu-id="aa056-159">Agende backups de log regulares e atualize seu plano de restauração adequadamente.</span><span class="sxs-lookup"><span data-stu-id="aa056-159">Schedule regular log backups, and update your restore plan accordingly.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="aa056-160">Se você não fizer backup do log com a frequência necessária, o log de transações poderá expandir-se até exceder o espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="aa056-160">If you do not back up the log frequently enough, the transaction log can expand until it runs out of disk space.</span></span>  
  
-   <span data-ttu-id="aa056-161">**Depois de alternar para o modelo de recuperação simples**</span><span class="sxs-lookup"><span data-stu-id="aa056-161">**After switching to the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="aa056-162">Descontinue os trabalhos agendados para fazer backup do log de transação.</span><span class="sxs-lookup"><span data-stu-id="aa056-162">Discontinue any scheduled jobs for backing up the transaction log.</span></span>  
  
    -   <span data-ttu-id="aa056-163">Verifique se os backups periódicos de banco de dados estão agendados.</span><span class="sxs-lookup"><span data-stu-id="aa056-163">Ensure periodic database backups are scheduled.</span></span> <span data-ttu-id="aa056-164">Fazer backup de seu banco de dados é essencial para proteger seus dados e truncar a porção inativa do log de transações.</span><span class="sxs-lookup"><span data-stu-id="aa056-164">Backing up your database is essential both to protect your data and to truncate the inactive portion of the transaction log.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="aa056-165">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="aa056-165">Related Tasks</span></span>  
  
-   [<span data-ttu-id="aa056-166">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aa056-166">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="aa056-167">Fazer backup de um log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aa056-167">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="aa056-168">Criar um trabalho</span><span class="sxs-lookup"><span data-stu-id="aa056-168">Create a Job</span></span>](../../ssms/agent/create-a-job.md)  
  
-   [<span data-ttu-id="aa056-169">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="aa056-169">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="aa056-170">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="aa056-170">Related Content</span></span>  
  
-   <span data-ttu-id="aa056-171">[Planos de manutenção de banco de dados](../maintenance-plans/maintenance-plans.md) (nos Manuais Online do [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="aa056-171">[Database Maintenance Plans](../maintenance-plans/maintenance-plans.md) (in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa056-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa056-172">See Also</span></span>  
 <span data-ttu-id="aa056-173">[Modelos de recuperação &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aa056-173">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="aa056-174">[O log de transações &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aa056-174">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="aa056-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aa056-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="aa056-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aa056-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="aa056-177">Modelos de recuperação &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aa056-177">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
