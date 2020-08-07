---
title: Gerenciar a tabela suspect_pages (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
- restoring pages [SQL Server]
- pages [SQL Server], suspect
- pages [SQL Server], restoring
- suspect_pages system table
- suspect pages [SQL Server]
- restoring [SQL Server], pages
ms.assetid: f394d4bc-1518-4e61-97fc-bf184d972e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dd7aea63ae85a16e23ff532c7e18ace3c376a707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583656"
---
# <a name="manage-the-suspect_pages-table-sql-server"></a><span data-ttu-id="466e9-102">Gerenciar a tabela suspect_pages (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="466e9-102">Manage the suspect_pages Table (SQL Server)</span></span>
  <span data-ttu-id="466e9-103">Este tópico descreve como gerenciar a tabela **suspect_pages** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="466e9-103">This topic describes how to manage the **suspect_pages** table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="466e9-104">A tabela **suspect_pages** é usada para manter informações sobre páginas suspeitas e é relevante para ajudar a decidir se a restauração é necessária.</span><span class="sxs-lookup"><span data-stu-id="466e9-104">The **suspect_pages** table is used for maintaining information about suspect pages, and is relevant in helping to decide whether a restore is necessary.</span></span> <span data-ttu-id="466e9-105">A tabela [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) reside no [banco de dados msdb](../databases/msdb-database.md).</span><span class="sxs-lookup"><span data-stu-id="466e9-105">The [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) table resides in the [msdb database](../databases/msdb-database.md).</span></span>  
  
 <span data-ttu-id="466e9-106">Uma página é considerada "suspeita" quando o [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] encontra um dos seguintes erros ao tentar ler uma página de dados:</span><span class="sxs-lookup"><span data-stu-id="466e9-106">A page is considered "suspect" when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] encounters one of the following errors when it tries to read a data page:</span></span>  
  
-   <span data-ttu-id="466e9-107">Um [erro 823](../errors-events/mssqlserver-823-database-engine-error.md) causado por uma CRC (verificação de redundância cíclica) emitida pelo sistema operacional, como um erro de disco (determinados erros de hardware)</span><span class="sxs-lookup"><span data-stu-id="466e9-107">An [823 error](../errors-events/mssqlserver-823-database-engine-error.md) that was caused by a cyclic redundancy check (CRC) issued by the operating system, such as a disk error (certain hardware errors)</span></span>  
  
-   <span data-ttu-id="466e9-108">Um [erro 824](../errors-events/mssqlserver-824-database-engine-error.md), como uma página interrompida (qualquer erro lógico)</span><span class="sxs-lookup"><span data-stu-id="466e9-108">An [824 error](../errors-events/mssqlserver-824-database-engine-error.md), such as a torn page (any logical error)</span></span>  
  
 <span data-ttu-id="466e9-109">A ID de cada página suspeita é registrada na tabela **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="466e9-109">The page ID of every suspect page is recorded in the **suspect_pages** table.</span></span> <span data-ttu-id="466e9-110">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] registra qualquer página suspeita encontrada durante o processamento regular, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="466e9-110">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] records any suspect pages encountered during regular processing, such as the following:</span></span>  
  
-   <span data-ttu-id="466e9-111">Uma consulta precisa ler uma página.</span><span class="sxs-lookup"><span data-stu-id="466e9-111">A query has to read a page.</span></span>  
  
-   <span data-ttu-id="466e9-112">Durante uma operação DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="466e9-112">During a DBCC CHECKDB operation.</span></span>  
  
-   <span data-ttu-id="466e9-113">Durante uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="466e9-113">During a backup operation.</span></span>  
  
 <span data-ttu-id="466e9-114">A tabela **suspect_pages** também é atualizada conforme necessário durante uma operação de restauração, uma operação de reparo DBCC ou uma operação de remoção de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="466e9-114">The **suspect_pages** table is also updated as necessary during a restore operation, a DBCC repair operation, or a drop database operation.</span></span>  
  
 <span data-ttu-id="466e9-115">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="466e9-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="466e9-116">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="466e9-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="466e9-117">Recomendações</span><span class="sxs-lookup"><span data-stu-id="466e9-117">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="466e9-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="466e9-118">Security</span></span>](#Security)  
  
-   <span data-ttu-id="466e9-119">**Para gerenciar a tabela suspect_pages usando:**</span><span class="sxs-lookup"><span data-stu-id="466e9-119">**To manage the suspect_pages table, using:**</span></span>  
  
     [<span data-ttu-id="466e9-120">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="466e9-120">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="466e9-121">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="466e9-121">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="466e9-122">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="466e9-122">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="466e9-123">Recomendações</span><span class="sxs-lookup"><span data-stu-id="466e9-123">Recommendations</span></span>  
  
-   <span data-ttu-id="466e9-124">**Erros registrados na tabela suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="466e9-124">**Errors Recorded in suspect_pages Table**</span></span>  
  
     <span data-ttu-id="466e9-125">A tabela **suspect_pages** contém uma linha por página que falhou com um erro 824 até o limite de 1.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="466e9-125">The **suspect_pages** table contains one row per page that failed with an 824 error, up to a limit of 1,000 rows.</span></span> <span data-ttu-id="466e9-126">A tabela a seguir mostra erros registrados na coluna **event_type** da tabela **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="466e9-126">The following table shows errors logged in the **event_type** column of the **suspect_pages** table.</span></span>  
  
    |<span data-ttu-id="466e9-127">Descrição do erro</span><span class="sxs-lookup"><span data-stu-id="466e9-127">Error description</span></span>|<span data-ttu-id="466e9-128">Valor**event_type**</span><span class="sxs-lookup"><span data-stu-id="466e9-128">**event_type** value</span></span>|  
    |-----------------------|---------------------------|  
    |<span data-ttu-id="466e9-129">Erro 823 causado por um erro CRC de sistema operacional ou erro 824 diferente de uma soma de verificação inválida ou uma página danificada (por exemplo, uma ID de página inválida).</span><span class="sxs-lookup"><span data-stu-id="466e9-129">823 error caused by an operating system CRC error  or 824 error other than a bad checksum or a torn page (for example, a bad page ID)</span></span>|<span data-ttu-id="466e9-130">1</span><span class="sxs-lookup"><span data-stu-id="466e9-130">1</span></span>|  
    |<span data-ttu-id="466e9-131">Soma de verificação inválida</span><span class="sxs-lookup"><span data-stu-id="466e9-131">Bad checksum</span></span>|<span data-ttu-id="466e9-132">2</span><span class="sxs-lookup"><span data-stu-id="466e9-132">2</span></span>|  
    |<span data-ttu-id="466e9-133">Página danificada</span><span class="sxs-lookup"><span data-stu-id="466e9-133">Torn page</span></span>|<span data-ttu-id="466e9-134">3</span><span class="sxs-lookup"><span data-stu-id="466e9-134">3</span></span>|  
    |<span data-ttu-id="466e9-135">Restaurada (a página foi restaurada depois de marcada como inválida)</span><span class="sxs-lookup"><span data-stu-id="466e9-135">Restored (The page was restored after it was marked bad)</span></span>|<span data-ttu-id="466e9-136">4</span><span class="sxs-lookup"><span data-stu-id="466e9-136">4</span></span>|  
    |<span data-ttu-id="466e9-137">Reparada (DBCC, AlwaysOn ou espelhamento reparou a página)</span><span class="sxs-lookup"><span data-stu-id="466e9-137">Repaired (DBCC, AlwaysOn, or mirroring repaired the page)</span></span>|<span data-ttu-id="466e9-138">5</span><span class="sxs-lookup"><span data-stu-id="466e9-138">5</span></span>|  
    |<span data-ttu-id="466e9-139">Desalocada pelo DBCC</span><span class="sxs-lookup"><span data-stu-id="466e9-139">Deallocated by DBCC</span></span>|<span data-ttu-id="466e9-140">7</span><span class="sxs-lookup"><span data-stu-id="466e9-140">7</span></span>|  
  
     <span data-ttu-id="466e9-141">A tabela **suspect_pages** também registra erros temporários.</span><span class="sxs-lookup"><span data-stu-id="466e9-141">The **suspect_pages** table also records transient errors.</span></span> <span data-ttu-id="466e9-142">Fontes de erros temporários incluem um erro de E/S (por exemplo, um cabo desconectado) ou uma página que temporariamente falha em um teste de soma de verificação repetido.</span><span class="sxs-lookup"><span data-stu-id="466e9-142">Sources of transient errors include an I/O error (for example, a cable was disconnected) or a page that temporarily fails a repeated checksum test.</span></span>  
  
-   <span data-ttu-id="466e9-143">**Como o Mecanismo de Banco de Dados atualiza a tabela suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="466e9-143">**How the Database Engine Updates the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="466e9-144">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] realiza as seguintes ações na tabela **suspect_pages** :</span><span class="sxs-lookup"><span data-stu-id="466e9-144">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes the following actions on the **suspect_pages** table:</span></span>  
  
    -   <span data-ttu-id="466e9-145">Se a tabela não estiver completa, a cada erro 824 ela será atualizada para indicar a ocorrência de um erro, e o contador de erros será incrementado.</span><span class="sxs-lookup"><span data-stu-id="466e9-145">If the table is not full, it is updated for every 824 error, to indicate that an error has occurred, and the error counter is incremented.</span></span> <span data-ttu-id="466e9-146">Se uma página tiver um erro consertado pela restauração, restaurado ou desalocado, sua contagem de **number_of_errors** será incrementada e sua coluna **last_update** será atualizada</span><span class="sxs-lookup"><span data-stu-id="466e9-146">If a page has an error after it is fixed by being repaired, restored, or deallocated, its **number_of_errors** count is incremented and its **last_update** column is updated</span></span>  
  
    -   <span data-ttu-id="466e9-147">Depois que uma página listada for corrigida por uma operação de restauração ou reparo, a operação atualizará a linha **suspect_pages** para indicar que a página foi reparada (**event_type** = 5) ou restaurada (**event_type** = 4).</span><span class="sxs-lookup"><span data-stu-id="466e9-147">After a listed page is fixed by a restore or a repair operation, the operation updates the **suspect_pages** row to indicate that the page is repaired (**event_type** = 5) or restored (**event_type** = 4).</span></span>  
  
    -   <span data-ttu-id="466e9-148">Se uma verificação DBCC for executada, a verificação marcará as páginas sem-erros como reparadas (**event_type** = 5) ou desalocadas (**event_type** = 7).</span><span class="sxs-lookup"><span data-stu-id="466e9-148">If a DBCC check is run, the check marks any error-free pages as repaired (**event_type** = 5) or deallocated (**event_type** = 7).</span></span>  
  
-   <span data-ttu-id="466e9-149">**Atualizações automáticas na tabela suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="466e9-149">**Automatic Updates to the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="466e9-150">Um parceiro de espelhamento de banco de dados ou réplica de disponibilidade AlwaysOn atualiza a tabela **suspect_pages** quando a tentativa de ler uma página de um arquivo de dados falha por uma das razões a seguir.</span><span class="sxs-lookup"><span data-stu-id="466e9-150">A database mirroring partner or AlwaysOn availability replica updates the **suspect_pages** table after an attempt to read a page from a data file fails for one of the following reasons.</span></span>  
  
    -   <span data-ttu-id="466e9-151">Um erro 823 causado por um erro CRC do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="466e9-151">An 823 error that is caused by an operating system CRC error.</span></span>  
  
    -   <span data-ttu-id="466e9-152">Um erro 824 (dano lógico como uma página corrompida).</span><span class="sxs-lookup"><span data-stu-id="466e9-152">An 824 error (logical corruption such as a torn page).</span></span>  
  
     <span data-ttu-id="466e9-153">As ações a seguir também atualizam automaticamente as linhas na tabela **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="466e9-153">The following actions also automatically update rows in the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="466e9-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS atualiza a tabela **suspect_pages** para indicar cada página que deve ser desalocada ou reparada.</span><span class="sxs-lookup"><span data-stu-id="466e9-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS updates the **suspect_pages** table to indicate each page that it has deallocated or repaired.</span></span>  
  
    -   <span data-ttu-id="466e9-155">Uma RESTORE completa, de página ou de arquivo marca as entradas de página como restauradas.</span><span class="sxs-lookup"><span data-stu-id="466e9-155">A full, file, or page RESTORE marks the page entries as restored.</span></span>  
  
     <span data-ttu-id="466e9-156">As ações a seguir excluem automaticamente as linhas da tabela **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="466e9-156">The following actions automatically delete rows from the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="466e9-157">ALTER DATABASE REMOVE FILE</span><span class="sxs-lookup"><span data-stu-id="466e9-157">ALTER DATABASE REMOVE FILE</span></span>  
  
    -   <span data-ttu-id="466e9-158">DROP DATABASE</span><span class="sxs-lookup"><span data-stu-id="466e9-158">DROP DATABASE</span></span>  
  
-   <span data-ttu-id="466e9-159">**Função de manutenção do administrador de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="466e9-159">**Maintenance Role of the Database Administrator**</span></span>  
  
     <span data-ttu-id="466e9-160">Os administradores de banco de dados são responsáveis por gerenciar a tabela, principalmente excluindo linhas antigas.</span><span class="sxs-lookup"><span data-stu-id="466e9-160">Database administrators are responsible for managing the table, primarily by deleting old rows.</span></span> <span data-ttu-id="466e9-161">A tabela **suspect_pages** é limitada em tamanho e, quando está cheia, os erros novos não são registrados.</span><span class="sxs-lookup"><span data-stu-id="466e9-161">The **suspect_pages** table is limited in size, and if it fills, new errors are not logged.</span></span> <span data-ttu-id="466e9-162">Para impedir que a tabela fique cheia, o administrador do banco de dados ou do sistema deve limpar manualmente as entradas antigas dessa tabela excluindo as linhas.</span><span class="sxs-lookup"><span data-stu-id="466e9-162">To prevent this table from filling up, the database administrator or system administrator must manually clear out old entries from this table by deleting rows.</span></span> <span data-ttu-id="466e9-163">Portanto, recomendamos que você exclua periodicamente ou arquive linhas com **event_type** restaurado ou reparado ou linhas com valor de **last_update** antigo.</span><span class="sxs-lookup"><span data-stu-id="466e9-163">Therefore, we recommend that you periodically delete or archive rows that have an **event_type** of restored or repaired, or rows that have an old **last_update** value.</span></span>  
  
     <span data-ttu-id="466e9-164">Para monitorar a atividade na tabela suspect_pages, é possível usar a [Classe de evento Database Suspect Data Page](../event-classes/database-suspect-data-page-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="466e9-164">To monitor the activity on the suspect_pages table, you can use the [Database Suspect Data Page Event Class](../event-classes/database-suspect-data-page-event-class.md).</span></span> <span data-ttu-id="466e9-165">Às vezes, são adicionadas linhas à tabela **suspect_pages** devido a erros temporários.</span><span class="sxs-lookup"><span data-stu-id="466e9-165">Rows are sometimes added to the **suspect_pages** table because of transient errors.</span></span> <span data-ttu-id="466e9-166">Contudo, se muitas linhas estiverem sendo adicionadas à tabela, talvez haja um problema com o subsistema de E/S.</span><span class="sxs-lookup"><span data-stu-id="466e9-166">If many rows are being added to the table, however, a problem probably exists with the I/O subsystem.</span></span> <span data-ttu-id="466e9-167">Se você perceber um aumento repentino no número de linhas que estão sendo adicionadas à tabela, recomendamos que investigue os possíveis problemas em seu subsistema de E/S.</span><span class="sxs-lookup"><span data-stu-id="466e9-167">If you notice a sudden increase in the number of rows being added to the table, we recommend that you investigate possible problems in your I/O subsystem.</span></span>  
  
     <span data-ttu-id="466e9-168">Um administrador de banco de dados pode também inserir ou atualizar registros.</span><span class="sxs-lookup"><span data-stu-id="466e9-168">A database administrator can also insert or update records.</span></span> <span data-ttu-id="466e9-169">Por exemplo, a atualização de uma linha pode ser útil quando o administrador do banco de dados sabe que uma determinada página suspeita está realmente intacta, mas quer preservar o registro por algum tempo.</span><span class="sxs-lookup"><span data-stu-id="466e9-169">For example, updating a row might useful when the database administrator knows that a particular suspect page is actually intact, but wants to preserve the record for a while.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="466e9-170">Segurança</span><span class="sxs-lookup"><span data-stu-id="466e9-170">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="466e9-171">Permissões</span><span class="sxs-lookup"><span data-stu-id="466e9-171">Permissions</span></span>  
 <span data-ttu-id="466e9-172">Qualquer pessoa com acesso ao **msdb** pode ler os dados na tabela **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="466e9-172">Anyone with access to **msdb** can read the data in the **suspect_pages** table.</span></span> <span data-ttu-id="466e9-173">Qualquer um com permissão UPDATE na tabela suspect_pages pode atualizar seus registros.</span><span class="sxs-lookup"><span data-stu-id="466e9-173">Anyone with UPDATE permission on the suspect_pages table can update its records.</span></span> <span data-ttu-id="466e9-174">Os membros da função de banco de dados fixa **db_owner** no **msdb** ou da função de servidor fixa **sysadmin** podem inserir, atualizar e excluir registros.</span><span class="sxs-lookup"><span data-stu-id="466e9-174">Members the **db_owner** fixed database role on **msdb** or the **sysadmin** fixed server role can insert, update, and delete records.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="466e9-175">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="466e9-175">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="466e9-176">Para gerenciar a tabela suspect_pages</span><span class="sxs-lookup"><span data-stu-id="466e9-176">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="466e9-177">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], expanda essa instância e expanda **Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="466e9-177">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="466e9-178">Expanda **Bancos de Dados do Sistema**, expanda **msdb**, expanda **Tabelas**e então expanda **Tabelas do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="466e9-178">Expand **System Databases**, expand **msdb**, expand **Tables**, and then expand **System Tables**.</span></span>  
  
3.  <span data-ttu-id="466e9-179">Expanda **dbo.suspect_pages** e clique com o botão direito do mouse em **Editar 200 Primeiras Linhas**.</span><span class="sxs-lookup"><span data-stu-id="466e9-179">Expand **dbo.suspect_pages** and right-click **Edit Top 200 Rows**.</span></span>  
  
4.  <span data-ttu-id="466e9-180">Na janela de consulta, edite, atualize ou exclua as linhas desejadas.</span><span class="sxs-lookup"><span data-stu-id="466e9-180">In the query window, edit, update, or delete the rows that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="466e9-181">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="466e9-181">Using Transact-SQL</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="466e9-182">Para gerenciar a tabela suspect_pages</span><span class="sxs-lookup"><span data-stu-id="466e9-182">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="466e9-183">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="466e9-183">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="466e9-184">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="466e9-184">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="466e9-185">Copie e cole os exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="466e9-185">Copy and paste the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="466e9-186">Este exemplo exclui algumas das linhas da tabela `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="466e9-186">This example deletes some of the rows from the `suspect_pages` table.</span></span>  
  
```  
-- Delete restored, repaired, or deallocated pages.  
DELETE FROM msdb..suspect_pages  
   WHERE (event_type = 4 OR event_type = 5 OR event_type = 7);  
GO  
  
```  
  
 <span data-ttu-id="466e9-187">Este exemplo retorna as páginas incorretas na tabela `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="466e9-187">This example returns the bad pages in the `suspect_pages` table.</span></span>  
  
```  
-- Select nonspecific 824, bad checksum, and torn page errors.  
SELECT * FROM msdb..suspect_pages  
   WHERE (event_type = 1 OR event_type = 2 OR event_type = 3);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="466e9-188">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="466e9-188">See Also</span></span>  
 <span data-ttu-id="466e9-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="466e9-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 <span data-ttu-id="466e9-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="466e9-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="466e9-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="466e9-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="466e9-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="466e9-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="466e9-193">[Restaurar páginas &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="466e9-193">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 <span data-ttu-id="466e9-194">[&#41;&#40;Transact-SQL de suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="466e9-194">[suspect_pages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span></span>  
 <span data-ttu-id="466e9-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="466e9-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span></span>  
 [<span data-ttu-id="466e9-196">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="466e9-196">MSSQLSERVER_824</span></span>](../errors-events/mssqlserver-824-database-engine-error.md)  
  
  
