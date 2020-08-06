---
title: Gerenciar FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], security
- FileTables [SQL Server], managing access
ms.assetid: 93af982c-b4fe-4be0-8268-11f86dae27e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a15a914c243f1fafd3b913d98113e984bf533086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680479"
---
# <a name="manage-filetables"></a><span data-ttu-id="64a16-102">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="64a16-102">Manage FileTables</span></span>
  <span data-ttu-id="64a16-103">Descreve tarefas administrativas comuns para gerenciar FileTables.</span><span class="sxs-lookup"><span data-stu-id="64a16-103">Describes common administrative tasks for managing FileTables.</span></span>  
  
##  <a name="how-to-get-a-list-of-filetables-and-related-objects"></a><a name="HowToEnumerate"></a> <span data-ttu-id="64a16-104">Como Obter uma lista de FileTables e objetos relacionados</span><span class="sxs-lookup"><span data-stu-id="64a16-104">How To: Get a List of FileTables and Related Objects</span></span>  
 <span data-ttu-id="64a16-105">Para obter uma lista de FileTables, consulte um das exibições do catálogo a seguir:</span><span class="sxs-lookup"><span data-stu-id="64a16-105">To get a list of FileTables, query one of the following catalog views:</span></span>  
  
-   [<span data-ttu-id="64a16-106">sys.filetables &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64a16-106">sys.filetables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-filetables-transact-sql)  
  
-   <span data-ttu-id="64a16-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Verifique o valor da coluna **is_filetable**.)</span><span class="sxs-lookup"><span data-stu-id="64a16-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Check the value of the **is_filetable** column.)</span></span>  
  
```sql  
SELECT * FROM sys.filetables;  
GO  
  
SELECT * FROM sys.tables WHERE is_filetable = 1;  
GO  
```  
  
 <span data-ttu-id="64a16-108">Para obter uma lista dos objetos definidos pelo sistema que foram criados quando as FileTables associadas foram criadas, consulte a exibição de catálogo [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="64a16-108">To get a list of the system-defined objects that were created when the associated FileTables were created, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
SELECT object_id, OBJECT_NAME(object_id) AS 'Object Name'  
    FROM sys.filetable_system_defined_objects  
    WHERE object_id = filetable_object_id;  
GO  
```  
  
##  <a name="disabling-and-re-enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsDisabling"></a> <span data-ttu-id="64a16-109">Desabilitando e reabilitando o acesso não transacional no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="64a16-109">Disabling and Re-enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="64a16-110">Para adquirir o acesso exclusivo que é necessário para determinadas tarefas administrativas, talvez seja necessário desabilitar temporariamente o acesso não transacional.</span><span class="sxs-lookup"><span data-stu-id="64a16-110">To acquire the exclusive access that is required for certain administrative tasks, you may have to disable non-transactional access temporarily.</span></span>  
  
 <span data-ttu-id="64a16-111">**Comportamento da instrução ALTER DATABASE ao alterar o nível de acesso não transacional**</span><span class="sxs-lookup"><span data-stu-id="64a16-111">**Behavior of the ALTER DATABASE statement when changing the level of non-transactional access**</span></span>  
  
-   <span data-ttu-id="64a16-112">Quando você definir o acesso não transacional como READ_ONLY ou OFF, o comando ALTER DATABASE não retornará o controle ao usuário enquanto houver identificadores de arquivos abertos em conflito com a operação solicitada.</span><span class="sxs-lookup"><span data-stu-id="64a16-112">When you set non-transactional access to READ_ONLY or OFF, the ALTER DATABASE command does not return control to the user as long as there are open file handles that conflict with the requested operation.</span></span> <span data-ttu-id="64a16-113">Os identificadores de arquivos que estão em conflito com esta operação incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="64a16-113">The file handles that conflict with this operation include the following:</span></span>  
  
    -   <span data-ttu-id="64a16-114">Quando você está definindo o acesso como **NONE**, todos os identificadores de arquivos abertos.</span><span class="sxs-lookup"><span data-stu-id="64a16-114">When you are setting access to **NONE**, all open file handles.</span></span>  
  
    -   <span data-ttu-id="64a16-115">Quando você define o acesso como **READ_ONLY**, todos os identificadores de arquivos são abertos para o acesso de gravação.</span><span class="sxs-lookup"><span data-stu-id="64a16-115">When you are setting access to **READ_ONLY**, all file handles opened for write access.</span></span>  
  
     <span data-ttu-id="64a16-116">Para obter informações sobre como eliminar identificadores de arquivos abertos, consulte [Eliminando identificadores de arquivos abertos associados a um FileTable](#BasicsKilling) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="64a16-116">For information about killing open file handles, see [Killing Open File Handles Associated with a FileTable](#BasicsKilling) in this topic.</span></span>  
  
     <span data-ttu-id="64a16-117">Se o comando ALTER DATABASE for cancelado ou terminar com um tempo limite, o nível de acesso transacional não será alterado.</span><span class="sxs-lookup"><span data-stu-id="64a16-117">If the ALTER DATABASE command is canceled or ends with a timeout, then the level of transactional access is not changed.</span></span>  
  
-   <span data-ttu-id="64a16-118">Se você chamar a instrução ALTER DATABASE com uma cláusula WITH \<termination> (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), todos os identificadores de arquivos não transacionais abertos serão encerrados.</span><span class="sxs-lookup"><span data-stu-id="64a16-118">If you call the ALTER DATABASE statement with a WITH \<termination> clause (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), then all open non-transactional file handles are killed.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="64a16-119">A eliminação de identificadores de arquivos abertos pode levar os usuários a perderem dados não salvos.</span><span class="sxs-lookup"><span data-stu-id="64a16-119">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="64a16-120">Esse comportamento é consistente com o comportamento do próprio sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="64a16-120">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
 <span data-ttu-id="64a16-121">**Efeitos de desabilitar o acesso não transacional**</span><span class="sxs-lookup"><span data-stu-id="64a16-121">**Effects of disabling non-transactional access**</span></span>  
  
 <span data-ttu-id="64a16-122">A alteração do nível de acesso não transacional no nível de banco de dados tem os seguintes efeitos nos diretórios de FileTable sob o diretório em nível de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="64a16-122">Changing the level of non-transactional access at the database level has the following effects on the FileTable directories under the database-level directory:</span></span>  
  
-   <span data-ttu-id="64a16-123">Quando você definir o acesso como **NONE**, todos os diretórios FileTable e seu conteúdo não ficará mais acessível nem visível.</span><span class="sxs-lookup"><span data-stu-id="64a16-123">When you set access to **NONE**, then all the FileTable directories and their contents are no longer accessible or visible.</span></span>  
  
-   <span data-ttu-id="64a16-124">Quando você define o acesso como **READ_ONLY**, todos os diretórios de FileTable e seu conteúdo também são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="64a16-124">When you set access to **READ_ONLY**, then all the FileTable directories and their contents are also read-only.</span></span>  
  
 <span data-ttu-id="64a16-125">A desabilitação de FILESTREAM no nível de instância tem os seguintes efeitos nos diretórios em nível de banco de dados nessa instância e nos diretórios de FileTable sob eles:</span><span class="sxs-lookup"><span data-stu-id="64a16-125">Disabling FILESTREAM at the instance level has the following effects on the database-level directories on that instance, and the FileTable directories under them:</span></span>  
  
-   <span data-ttu-id="64a16-126">Nenhum dos diretórios em nível de banco de dados na instância estará visível se FILESTREAM for desabilitado no nível de instância.</span><span class="sxs-lookup"><span data-stu-id="64a16-126">None of the database-level directories on the instance are visible if FILESTREAM is disabled at the instance level.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-non-transactional-access-at-the-database-level"></a><a name="HowToDisable"></a> <span data-ttu-id="64a16-127">Como Desabilitar e reabilitar o acesso não transacional no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="64a16-127">How To: Disable and Re-enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="64a16-128">Para obter mais informações, veja [Opções ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="64a16-128">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="64a16-129">**Para desabilitar o acesso não transacional**</span><span class="sxs-lookup"><span data-stu-id="64a16-129">**To disable full non-transactional access**</span></span>  
 <span data-ttu-id="64a16-130">Chame a instrução **ALTER DATABASE** e defina o valor de **NON_TRANSACTED_ACCESS** como **READ_ONLY** ou **OFF**.</span><span class="sxs-lookup"><span data-stu-id="64a16-130">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **READ_ONLY** or **OFF**.</span></span>  
  
```sql  
-- Disable write access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = READ_ONLY );  
GO  
  
-- Disable non-transactional access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = OFF );  
GO  
```  
  
 <span data-ttu-id="64a16-131">**Para reabilitar o acesso não transacional**</span><span class="sxs-lookup"><span data-stu-id="64a16-131">**To re-enable full non-transactional access**</span></span>  
 <span data-ttu-id="64a16-132">Chame a instrução **ALTER DATABASE** e defina o valor de **NON_TRANSACTED_ACCESS** como **FULL**.</span><span class="sxs-lookup"><span data-stu-id="64a16-132">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **FULL**.</span></span>  
  
```sql  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL );  
GO  
```  
  
###  <a name="how-to-ensure-the-visibility-of-the-filetables-in-a-database"></a><a name="visible"></a> <span data-ttu-id="64a16-133">Como garantir a visibilidade do FileTables em um banco de dados</span><span class="sxs-lookup"><span data-stu-id="64a16-133">How to: Ensure the Visibility of the FileTables in a Database</span></span>  
 <span data-ttu-id="64a16-134">Um diretório em nível de banco de dados e os diretórios FileTable sob ele estarão visíveis quando todas essa condições forem atendidas</span><span class="sxs-lookup"><span data-stu-id="64a16-134">A database-level directory and the FileTable directories under it are visible when all of these conditions are true:</span></span>  
  
1.  <span data-ttu-id="64a16-135">O FILESTREAM está habilitado no nível de instância.</span><span class="sxs-lookup"><span data-stu-id="64a16-135">FILESTREAM is enabled at the instance level.</span></span>  
  
2.  <span data-ttu-id="64a16-136">O acesso não transacional está habilitado no nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="64a16-136">Non-transactional access is enabled at the database level.</span></span>  
  
3.  <span data-ttu-id="64a16-137">Um diretório válido foi especificado ao nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="64a16-137">A valid directory has been specified at the database level.</span></span>  
  
##  <a name="disabling-and-re-enabling-the-filetable-namespace-at-the-table-level"></a><a name="BasicsEnabling"></a> <span data-ttu-id="64a16-138">Desabilitando e reabilitando o namespace FileTable no nível de tabela</span><span class="sxs-lookup"><span data-stu-id="64a16-138">Disabling and Re-enabling the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="64a16-139">Desabilitar o namespace FileTable desabilita todos os gatilhos e restrições definidos pelo sistema que foram criados com o FileTable.</span><span class="sxs-lookup"><span data-stu-id="64a16-139">Disabling the FileTable namespace disables all the system-defined constraints and triggers that were created with the FileTable.</span></span> <span data-ttu-id="64a16-140">Isso é útil em casos em que um FileTable precisa ser reorganizado em grande escala usando operações [!INCLUDE[tsql](../../includes/tsql-md.md)] sem recorrer à imposição de semântica de FileTable.</span><span class="sxs-lookup"><span data-stu-id="64a16-140">This is useful in cases where a FileTable has to be reorganized on a large scale by using [!INCLUDE[tsql](../../includes/tsql-md.md)] operations without incurring the expense of enforcing FileTable semantics.</span></span> <span data-ttu-id="64a16-141">Entretanto, essas operações podem deixar FileTable em um estado inconsistente e podem impedir a reabilitação do namespace FileTable.</span><span class="sxs-lookup"><span data-stu-id="64a16-141">However these operations can leave the FileTable in an inconsistent state, and can prevent the re-enabling of the FileTable namespace.</span></span>  
  
 <span data-ttu-id="64a16-142">A desabilitação de um namespace FileTable tem os resultados seguintes:</span><span class="sxs-lookup"><span data-stu-id="64a16-142">Disabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="64a16-143">As colunas e dados de FileTable não são fisicamente removidos da tabela.</span><span class="sxs-lookup"><span data-stu-id="64a16-143">FileTable columns and data are not physically dropped from the table.</span></span>  
  
-   <span data-ttu-id="64a16-144">O diretório de FileTable, e seus arquivos e diretórios, desaparecem do sistema de arquivo e não estão disponíveis para o acesso de E/S de arquivo.</span><span class="sxs-lookup"><span data-stu-id="64a16-144">The FileTable directory and the files and directories that it contains disappear from the file system and are not available for file i/o access.</span></span>  
  
-   <span data-ttu-id="64a16-145">As colunas de FileTable definidas pelo sistema não podem ser removidas e recriadas; caso contrário, contudo elas se comportam como qualquer outra coluna em operações DML.</span><span class="sxs-lookup"><span data-stu-id="64a16-145">System-defined FileTable columns cannot be dropped and recreated; otherwise, however, they behave like ordinary columns for DML operations.</span></span>  
  
-   <span data-ttu-id="64a16-146">Identificadores de arquivos abertos impedem que as restrições de FileTable sejam desabilitadas, pois essa operação requer um bloqueio de esquema na tabela.</span><span class="sxs-lookup"><span data-stu-id="64a16-146">Open file handles prevent the FileTable constraints from being disabled, since this operation requires a schema lock on the table.</span></span>  
  
-   <span data-ttu-id="64a16-147">A execução de toda a semântica de FileTable, inclusive restrições definidas por sistema e gatilhos, é interrompida depois que o namespace FileTable é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="64a16-147">Enforcement of all the FileTable semantics, including system-defined constraints and triggers, stops after the FileTable namespace is disabled.</span></span>  
  
 <span data-ttu-id="64a16-148">A reabilitação de um namespace FileTable tem os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="64a16-148">Re-enabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="64a16-149">É verificada a consistência de FileTable.</span><span class="sxs-lookup"><span data-stu-id="64a16-149">The FileTable is checked for consistency.</span></span> <span data-ttu-id="64a16-150">Se forem encontradas inconsistências, um erro ocorrerá e o FileTable permanecerá desabilitado; caso contrário, o FileTable será reabilitado.</span><span class="sxs-lookup"><span data-stu-id="64a16-150">If inconsistencies are found, then an error is raised and the FileTable remains disabled; otherwise, the FileTable is re-enabled.</span></span>  
  
-   <span data-ttu-id="64a16-151">A imposição da semântica de FileTable, inclusive restrições definidas pelo sistema e gatilhos, é restaurada.</span><span class="sxs-lookup"><span data-stu-id="64a16-151">The enforcement of FileTable semantics, including system-defined constraints and triggers, is restored.</span></span>  
  
-   <span data-ttu-id="64a16-152">O diretório de FileTable, e seus arquivos e diretórios, ficam visíveis no sistema de arquivo e ficam disponíveis para o acesso de E/S de arquivo.</span><span class="sxs-lookup"><span data-stu-id="64a16-152">The FileTable directory and the files and directories that it contains become visible in the file system and become available for file i/o access.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-the-filetable-namespace-at-the-table-level"></a><a name="HowToEnableNS"></a> <span data-ttu-id="64a16-153">Como desabilitar e reabilitar o namespace FileTable no nível de tabela</span><span class="sxs-lookup"><span data-stu-id="64a16-153">How To: Disable and Re-enable the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="64a16-154">Chame a instrução ALTER TABLE com a opção **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** .</span><span class="sxs-lookup"><span data-stu-id="64a16-154">Call the ALTER TABLE statement with the **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** option.</span></span>  
  
 <span data-ttu-id="64a16-155">**Para desabilitar o namespace da FileTable**</span><span class="sxs-lookup"><span data-stu-id="64a16-155">**To disable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    DISABLE FILETABLE_NAMESPACE;  
GO  
```  
  
 <span data-ttu-id="64a16-156">**Para reabilitar o namespace da FileTable**</span><span class="sxs-lookup"><span data-stu-id="64a16-156">**To re-enable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    ENABLE FILETABLE_NAMESPACE;  
GO  
```  
  
##  <a name="killing-open-file-handles-associated-with-a-filetable"></a><a name="BasicsKilling"></a> <span data-ttu-id="64a16-157">Eliminando identificadores de arquivos abertos associados a um FileTable</span><span class="sxs-lookup"><span data-stu-id="64a16-157">Killing Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="64a16-158">Os identificadores abertos para os arquivos armazenados em uma FileTable podem impedir o acesso exclusivo que é necessário para determinadas tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="64a16-158">Open handles to the files stored in a FileTable can prevent the exclusive access that is required for certain administrative tasks.</span></span> <span data-ttu-id="64a16-159">Para habilitar tarefas urgentes, você poderá precisar eliminar identificadores de arquivos abertos associados a uma ou mais FileTables.</span><span class="sxs-lookup"><span data-stu-id="64a16-159">To enable urgent tasks, you may have to kill open file handles associated with one or more FileTables.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="64a16-160">A eliminação de identificadores de arquivos abertos pode levar os usuários a perderem dados não salvos.</span><span class="sxs-lookup"><span data-stu-id="64a16-160">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="64a16-161">Esse comportamento é consistente com o comportamento do próprio sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="64a16-161">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
###  <a name="how-to-get-a-list-of-open-file-handles-associated-with-a-filetable"></a><a name="HowToListOpen"></a> <span data-ttu-id="64a16-162">Como obter uma lista de identificadores de arquivos abertos associados a um FileTable</span><span class="sxs-lookup"><span data-stu-id="64a16-162">How To: Get a List of Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="64a16-163">Consulte a exibição de catálogo [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="64a16-163">Query the catalog view [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.dm_filestream_non_transacted_handles;  
GO  
```  
  
###  <a name="how-to-kill-open-file-handles-associated-with-a-filetable"></a><a name="HowToKill"></a> <span data-ttu-id="64a16-164">Como eliminar identificadores de arquivos abertos associados a um FileTable</span><span class="sxs-lookup"><span data-stu-id="64a16-164">How To: Kill Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="64a16-165">Chame o procedimento armazenado [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) com os argumentos apropriados para eliminar todos os identificadores de arquivos abertos no banco de dados ou na FileTable, ou para eliminar um identificador específico.</span><span class="sxs-lookup"><span data-stu-id="64a16-165">Call the stored procedure [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) with the appropriate arguments to kill all open file handles in the database or in the FileTable, or to kill a specific handle.</span></span>  
  
```  
USE database_name;  
  
-- Kill all open handles in all the filetables in the database.  
EXEC sp_kill_filestream_non_transacted_handles;  
GO  
  
-- Kill all open handles in a single filetable.  
EXEC sp_kill_filestream_non_transacted_handles @table_name = 'filetable_name';  
GO  
  
-- Kill a single handle.  
EXEC sp_kill_filestream_non_transacted_handles @handle_id = integer_handle_id;  
GO  
```  
  
###  <a name="how-to-identify-the-locks-held-by-filetables"></a><a name="HowToIdentifyLocks"></a> <span data-ttu-id="64a16-166">Como identificar os bloqueios mantidos por FileTables</span><span class="sxs-lookup"><span data-stu-id="64a16-166">How to: Identify the Locks Held by FileTables</span></span>  
 <span data-ttu-id="64a16-167">A maioria dos bloqueios feitos por FileTables correspondem a arquivos abertos por aplicativos.</span><span class="sxs-lookup"><span data-stu-id="64a16-167">Most locks taken by FileTables correspond to files opened by applications.</span></span>  
  
 <span data-ttu-id="64a16-168">**Para identificar arquivos abertos e os bloqueios associados**</span><span class="sxs-lookup"><span data-stu-id="64a16-168">**To identify open files and the associated locks**</span></span>  
 <span data-ttu-id="64a16-169">Una o campo **request_owner_id** à exibição de gerenciamento dinâmico [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) com o campo **fcb_id** em [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="64a16-169">Join the **request_owner_id** field in the dynamic management view [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) with the **fcb_id** field in [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span> <span data-ttu-id="64a16-170">Em alguns casos, o bloqueio não corresponde a um único identificador de arquivo aberto.</span><span class="sxs-lookup"><span data-stu-id="64a16-170">In some cases, the lock does not correspond to a single open file handle.</span></span>  
  
```sql  
SELECT opened_file_name  
    FROM sys.dm_filestream_non_transacted_handles  
    WHERE fcb_id IN  
        ( SELECT request_owner_id FROM sys.dm_tran_locks );  
GO  
```  
  
##  <a name="filetable-security"></a><a name="BasicsSecurity"></a> <span data-ttu-id="64a16-171">Segurança de FileTable</span><span class="sxs-lookup"><span data-stu-id="64a16-171">FileTable Security</span></span>  
 <span data-ttu-id="64a16-172">Os arquivos e diretórios armazenados em FileTables só ficam protegidos pela segurança do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="64a16-172">The files and directories stored in FileTables are secured by SQL Server security only.</span></span> <span data-ttu-id="64a16-173">A segurança com base em tabela e coluna é imposta para acesso de sistema de arquivos, assim como o acesso [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64a16-173">Table and column-based security is enforced for file system access as well as [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="64a16-174">Não há suporte para configurações de ACL e APIs de segurança do sistema de arquivos Windows.</span><span class="sxs-lookup"><span data-stu-id="64a16-174">Windows file system security APIs and ACL settings are not supported.</span></span>  
  
 <span data-ttu-id="64a16-175">As permissões de segurança e acesso aplicáveis a grupos de arquivos e contêineres FILESTREAM também se aplicam a FileTables, desde que os dados de arquivos estejam armazenados como uma coluna FILESTREAM no FileTable.</span><span class="sxs-lookup"><span data-stu-id="64a16-175">The security and access permissions that are applicable to FILESTREAM filegroups and containers also apply to FileTables, since the file data is stored as a FILESTREAM column in the FileTable.</span></span>  
  
 <span data-ttu-id="64a16-176">**Segurança de FileTable e acesso Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="64a16-176">**FileTable Security and Transact-SQL Access**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="64a16-177">acesso aos dados em FileTables é protegido da mesma maneira como em qualquer outra tabela.</span><span class="sxs-lookup"><span data-stu-id="64a16-177">access to data in FileTables is secured in the same way as any other table.</span></span> <span data-ttu-id="64a16-178">São feitas verificações de segurança apropriadas em nível de tabela e de coluna para cada operação que acessa ou altera os dados.</span><span class="sxs-lookup"><span data-stu-id="64a16-178">Appropriate table and column-level security checks are done for every operation that accesses or changes the data.</span></span>  
  
 <span data-ttu-id="64a16-179">**Segurança de FileTable e acesso ao sistema de arquivos**</span><span class="sxs-lookup"><span data-stu-id="64a16-179">**FileTable Security and File System Access**</span></span>  
 <span data-ttu-id="64a16-180">APIs do sistema de arquivos exigem permissões apropriadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na linha inteira no FileTable (ou seja, permissão em nível de tabela) para abrir um identificador em um arquivo ou diretório armazenado no FileTable.</span><span class="sxs-lookup"><span data-stu-id="64a16-180">File system APIs require appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions on the entire row in the FileTable (that is, table-level permission) to open a handle to a file or directory stored in the FileTable.</span></span> <span data-ttu-id="64a16-181">Se o usuário não tiver a permissão [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] apropriada em qualquer coluna do FileTable, o acesso ao sistema de arquivos será negado.</span><span class="sxs-lookup"><span data-stu-id="64a16-181">If the user does not have the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission on any column in the FileTable, then file system access is denied.</span></span>  
  
##  <a name="backup-and-filetables"></a><a name="OtherBackup"></a> <span data-ttu-id="64a16-182">Backup e FileTables</span><span class="sxs-lookup"><span data-stu-id="64a16-182">Backup and FileTables</span></span>  
 <span data-ttu-id="64a16-183">Quando você usa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para fazer backup de um FileTable, o backup dos dados FILESTREAM é feito com os dados estruturados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="64a16-183">When you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to back up a FileTable, the FILESTREAM data is backed up with the structured data in the database.</span></span> <span data-ttu-id="64a16-184">Se você não desejar fazer backup de dados FILESTREAM com dados relacionais, poderá usar um backup parcial para excluir grupos de arquivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="64a16-184">If you do not want to back up FILESTREAM data with relational data, you can use a partial backup to exclude FILESTREAM filegroups.</span></span>  
  
 <span data-ttu-id="64a16-185">**Consistência transacional de backups de FileTable**</span><span class="sxs-lookup"><span data-stu-id="64a16-185">**Transactional Consistency of FileTable Backups**</span></span>  
  
 <span data-ttu-id="64a16-186">Muitas ferramentas e operações administrativas, (inclusive backup, backup de log e replicação transacional) leem dados transacionalmente consistentes lendo os logs de transações.</span><span class="sxs-lookup"><span data-stu-id="64a16-186">Many administrative tools and operations, (including backup, log backup, and transactional replication) read transactionally consistent data by reading the transaction logs.</span></span> <span data-ttu-id="64a16-187">Neste momento, eles leem quaisquer dados FILESTREAM atualizados como parte de uma transação.</span><span class="sxs-lookup"><span data-stu-id="64a16-187">At this time, they read any FILESTREAM data updated as part of a transaction.</span></span> <span data-ttu-id="64a16-188">Quando o acesso não transacional não está habilitado no nível de banco de dados, essas ferramentas e operações funcionam com total consistência transacional.</span><span class="sxs-lookup"><span data-stu-id="64a16-188">When non-transactional access is not enabled at the database level, these tools and operations work with full transactional consistency.</span></span>  
  
 <span data-ttu-id="64a16-189">Entretanto, quando o acesso completo não transacional estiver habilitado, uma FileTable poderá conter dados que foram atualizados mais recentemente (por meio de uma atualização não transacional) do que a transação que a ferramenta ou o processo está lendo no log de transação.</span><span class="sxs-lookup"><span data-stu-id="64a16-189">However, when full non-transactional access is enabled, then a FileTable could contain data that was updated more recently (through a non-transactional update) than the transaction that the tool or process is reading from the transaction log.</span></span> <span data-ttu-id="64a16-190">Isso significa que uma operação de restauração de "ponto no tempo" em uma transação específica pode conter dados FILESTREAM mais recentes do que aquela transação.</span><span class="sxs-lookup"><span data-stu-id="64a16-190">This means that a "point in time" restore operation to a specific transaction may contain FILESTREAM data that is more recent than that transaction.</span></span> <span data-ttu-id="64a16-191">Esse é o comportamento esperado quando são permitidas atualizações não transacionais em FileTables.</span><span class="sxs-lookup"><span data-stu-id="64a16-191">This is the expected behavior when non-transactional updates are allowed on FileTables.</span></span>  
  
##  <a name="sql-server-profiler-and-filetables"></a><a name="Monitor"></a> <span data-ttu-id="64a16-192">Recursos do SQL Server Profiler e FileTables</span><span class="sxs-lookup"><span data-stu-id="64a16-192">SQL Server Profiler and FileTables</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="64a16-193">Profiler pode capturar as operações Abrir Arquivo e Fechar Arquivo do Windows no rastreamento gerado para arquivos que são armazenados em um FileTable.</span><span class="sxs-lookup"><span data-stu-id="64a16-193">Profiler can capture the Windows File Open and File Close operations in trace output for files that are stored in a FileTable.</span></span>  
  
##  <a name="auditing-and-filetables"></a><a name="OtherAuditing"></a> <span data-ttu-id="64a16-194">Auditoria e FileTables</span><span class="sxs-lookup"><span data-stu-id="64a16-194">Auditing and FileTables</span></span>  
 <span data-ttu-id="64a16-195">A FileTable pode ser auditada como qualquer outra tabela.</span><span class="sxs-lookup"><span data-stu-id="64a16-195">FileTable can be audited just like any other table.</span></span> <span data-ttu-id="64a16-196">Entretanto, os padrões de acesso Win32 não são operações baseadas em conjunto.</span><span class="sxs-lookup"><span data-stu-id="64a16-196">Howerver, Win32 access patterns are not set based operations.</span></span> <span data-ttu-id="64a16-197">Uma única ação no sistema de arquivos é traduzida em várias operações DML Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="64a16-197">A single action in the file system translates into multiple Transact-SQL DML operations.</span></span> <span data-ttu-id="64a16-198">Por exemplo, a abertura de um arquivo no Microsoft Word se traduz em várias operações de abertura/fechamento/criação/renomeação/exclusão e em atividades DML Transact-SQL correspondentes.</span><span class="sxs-lookup"><span data-stu-id="64a16-198">For example, opening a file in Microsoft Word translates into multiple open/close/create/rename/delete operations and corresponding Transact-SQL DML activities.</span></span> <span data-ttu-id="64a16-199">Isso resulta em registros de auditoria detalhados, onde é difícil correlacionar registros entre ações do sistema de arquivos e registros de auditoria DML Transact-SQL correspondentes.</span><span class="sxs-lookup"><span data-stu-id="64a16-199">This results in verbose audit records where it is hard to correlate records between file system actions and corresponding Transact-SQL DML audit records.</span></span>  
  
##  <a name="dbcc-and-filetables"></a><a name="OtherDBCC"></a> <span data-ttu-id="64a16-200">DBCC e FileTables</span><span class="sxs-lookup"><span data-stu-id="64a16-200">DBCC and FileTables</span></span>  
 <span data-ttu-id="64a16-201">Você pode usar DBCC CHECKCONSTRAINTS para validar as restrições em uma FileTable, inclusive restrições definidas pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="64a16-201">You can use DBCC CHECKCONSTRAINTS to validate the constraints on a FileTable including system-defined constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a16-202">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64a16-202">See Also</span></span>  
 <span data-ttu-id="64a16-203">[Compatibilidade do FileTable com outros recursos do SQL Server](filetable-compatibility-with-other-sql-server-features.md) </span><span class="sxs-lookup"><span data-stu-id="64a16-203">[FileTable Compatibility with Other SQL Server Features](filetable-compatibility-with-other-sql-server-features.md) </span></span>  
 [<span data-ttu-id="64a16-204">DDL, funções, procedimentos armazenados e exibições de FileTable</span><span class="sxs-lookup"><span data-stu-id="64a16-204">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
