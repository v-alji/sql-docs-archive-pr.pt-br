---
title: Alterando tabelas com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 690b70b7-5be1-4014-af97-54e531997839
author: rothja
ms.author: jroth
ms.openlocfilehash: 4eedc6fdb45efc6c87765cd2208ead90c1887c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582453"
---
# <a name="altering-memory-optimized-tables"></a><span data-ttu-id="be869-102">Alterando tabelas com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="be869-102">Altering Memory-Optimized Tables</span></span>
  <span data-ttu-id="be869-103">Não há suporte para as operações de ALTER nas tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="be869-103">Performing ALTER operations on memory-optimized tables is not supported.</span></span> <span data-ttu-id="be869-104">Isso inclui operações como alteração do bucket_count, adição ou remoção de um índice, e adição ou remoção de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="be869-104">This includes such operations as changing the bucket_count, adding or removing an index, and adding or removing a column.</span></span> <span data-ttu-id="be869-105">Este tópico fornece diretrizes sobre como atualizar tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="be869-105">This topic provides guidelines on how to update memory-optimized tables.</span></span>  
  
## <a name="updating-the-definition-of-a-memory-optimized-table"></a><span data-ttu-id="be869-106">Atualizando a definição de uma tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="be869-106">Updating the Definition of a Memory-Optimized Table</span></span>  
 <span data-ttu-id="be869-107">A atualização da definição de uma tabela com otimização de memória exige que você crie uma nova tabela com a definição de tabela atualizada, copie os dados na nova tabela e comece a usar a nova tabela.</span><span class="sxs-lookup"><span data-stu-id="be869-107">Updating the definition of a memory-optimized table requires you to create a new table with the updated table definition, copy the data to the new table, and start using the new table.</span></span> <span data-ttu-id="be869-108">A menos que a tabela seja somente leitura, isso requer a interrupção da carga de trabalho na tabela, de modo a garantir que nenhuma alteração seja feita na tabela enquanto a cópia dos dados é realizada.</span><span class="sxs-lookup"><span data-stu-id="be869-108">Unless the table is read-only, this requires stopping the workload on the table, to ensure no changes are made to the table while the data copy is performed.</span></span>  
  
 <span data-ttu-id="be869-109">O procedimento a seguir destaca as etapas necessárias para atualizar uma tabela.</span><span class="sxs-lookup"><span data-stu-id="be869-109">The following procedure outlines the steps required to update a table.</span></span> <span data-ttu-id="be869-110">Neste exemplo, a atualização adiciona um índice.</span><span class="sxs-lookup"><span data-stu-id="be869-110">In this example, the update adds an index.</span></span> <span data-ttu-id="be869-111">Esse procedimento preserva o nome da tabela e requer duas operações de cópia de dados: uma vez em uma tabela temporária e outra na nova tabela.</span><span class="sxs-lookup"><span data-stu-id="be869-111">This procedure preserves the name of the table and requires two data copy operations: once to a temporary table, and once to the new table.</span></span> <span data-ttu-id="be869-112">A alteração de bucket_count de um índice, ou a adição ou remoção de uma coluna são executadas da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="be869-112">Changing the bucket_count of an index or adding or removing a column is performed the same way.</span></span>  
  
1.  <span data-ttu-id="be869-113">Interrompa a carga de trabalho na tabela.</span><span class="sxs-lookup"><span data-stu-id="be869-113">Stop the workload on the table.</span></span>  
  
2.  <span data-ttu-id="be869-114">Gere o script para a tabela e adicione o novo índice ao script.</span><span class="sxs-lookup"><span data-stu-id="be869-114">Generate script for the table and add the new index to the script.</span></span>  
  
3.  <span data-ttu-id="be869-115">Gere o script para os objetos associados ao esquema (principalmente procedimentos armazenados compilados nativamente) que fazem referência a T e suas permissões.</span><span class="sxs-lookup"><span data-stu-id="be869-115">Generate script for the schema-bound objects (mainly natively compiled stored procedures) referencing T and their permissions.</span></span>  
  
     <span data-ttu-id="be869-116">Os objetos associados ao esquema que fazem referência à tabela podem ser encontrados com a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="be869-116">The schema-bound objects referencing the table can be found using the following query:</span></span>  
  
    ```sql  
    declare @t nvarchar(255) = N'<table name>'  
  
    select r.referencing_schema_name, r.referencing_entity_name  
    from sys.dm_sql_referencing_entities (@t, 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
    where r.is_caller_dependent = 0 and m.is_schema_bound=1;  
    ```  
  
     <span data-ttu-id="be869-117">As permissões de um procedimento armazenado podem ser colocadas em script usando o seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="be869-117">The permissions of a stored procedure can be scripted using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
    ```sql  
    declare @sp nvarchar(255) = N'<procedure name>'  
    declare @permissions nvarchar(max) = N''  
  
    select @permissions += dp.state_desc + N' ' + dp.permission_name + N' ON ' +   
       quotename(schema_name(o.schema_id)) + N'.' + quotename(o.name) + N' TO ' +  
       quotename(u.name) + N'; ' + char(13)  
    from sys.database_permissions as dp  
  
    join sys.database_principals as u  
       on u.principal_id = dp.grantee_principal_id  
  
    join sys.objects as o  
       on o.object_id = dp.major_id  
    where dp.class = 1 /* object */  
       and dp.minor_id = 0 and o.object_id=object_id(@sp);  
  
    select @permissions  
    ```  
  
4.  <span data-ttu-id="be869-118">Crie uma cópia da tabela e copie os dados da tabela original na cópia da tabela.</span><span class="sxs-lookup"><span data-stu-id="be869-118">Create a copy of the table and copy the data from the original table to the copy of the table.</span></span> <span data-ttu-id="be869-119">A cópia pode ser criada usando o seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)] <sup>1</sup>.</span><span class="sxs-lookup"><span data-stu-id="be869-119">The copy can be created using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]<sup>1</sup>.</span></span>  
  
    ```sql  
    select * into dbo.T_copy from dbo.T  
    ```  
  
     <span data-ttu-id="be869-120">Se houver memória suficiente disponível, `T_copy` o poderá ser uma tabela com otimização de memória, o que torna a cópia de dados mais rápida.<sup> 2</sup></span><span class="sxs-lookup"><span data-stu-id="be869-120">If there is enough available memory, `T_copy` could be a memory-optimized table, which makes the data copy faster.<sup>2</sup></span></span>  
  
5.  <span data-ttu-id="be869-121">Descarte os objetos associados ao esquema que fazem referência à tabela original.</span><span class="sxs-lookup"><span data-stu-id="be869-121">Drop the schema-bound objects referencing the original table.</span></span>  
  
6.  <span data-ttu-id="be869-122">Descarte a tabela original.</span><span class="sxs-lookup"><span data-stu-id="be869-122">Drop the original table.</span></span>  
  
7.  <span data-ttu-id="be869-123">Crie a nova tabela (`T`) com o script que contém o novo índice.</span><span class="sxs-lookup"><span data-stu-id="be869-123">Create the new table (`T`) with the script containing the new index.</span></span>  
  
8.  <span data-ttu-id="be869-124">Copie os dados de `T_copy` em `T`.</span><span class="sxs-lookup"><span data-stu-id="be869-124">Copy the data from `T_copy` to `T`.</span></span>  
  
9. <span data-ttu-id="be869-125">Recrie os objetos associados ao esquema de referência e aplique as permissões.</span><span class="sxs-lookup"><span data-stu-id="be869-125">Recreate the referencing schema-bound objects and apply the permissions.</span></span>  
  
10. <span data-ttu-id="be869-126">Inicie a carga de trabalho em `T`.</span><span class="sxs-lookup"><span data-stu-id="be869-126">Start the workload on `T`.</span></span>  
  
 <span data-ttu-id="be869-127"><sup>1</sup> Observe que `T_copy` é persistido no disco neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="be869-127"><sup>1</sup> Note that `T_copy` is persisted to disk in this example.</span></span> <span data-ttu-id="be869-128">Se um backup de `T` estiver disponível, `T_copy` poderá ser uma tabela temporária ou não durável.</span><span class="sxs-lookup"><span data-stu-id="be869-128">If a backup of `T` is available, `T_copy` could be a temporary or a non-durable table.</span></span>  
  
 <span data-ttu-id="be869-129"><sup>2</sup> deve haver memória suficiente para `T_copy` .</span><span class="sxs-lookup"><span data-stu-id="be869-129"><sup>2</sup> There must be enough memory for `T_copy`.</span></span> <span data-ttu-id="be869-130">A memória não é liberada imediatamente em `DROP TABLE`.</span><span class="sxs-lookup"><span data-stu-id="be869-130">Memory is not freed immediately on `DROP TABLE`.</span></span> <span data-ttu-id="be869-131">Se `T_copy` tiver otimização de memória, haverá necessidade de memória suficiente para duas cópias adicionais de `T`.</span><span class="sxs-lookup"><span data-stu-id="be869-131">If `T_copy` is memory optimized, there needs to be enough memory for two additional copies of `T`.</span></span> <span data-ttu-id="be869-132">Se `T_copy` for uma tabela baseada em disco, haverá necessidade de memória suficiente apenas para uma cópia adicional de `T`, devido ao coletor de lixo que precisa ser atualizado depois de descartar a versão antiga de `T`.</span><span class="sxs-lookup"><span data-stu-id="be869-132">If `T_copy` is a disk-based table, there only needs to be enough memory for one additional copy of `T`, due to the garbage collector needing to catch up after dropping the old version of `T`.</span></span>  
  
## <a name="changing-schema-powershell"></a><span data-ttu-id="be869-133">Alterando o esquema (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="be869-133">Changing Schema (PowerShell)</span></span>  
 <span data-ttu-id="be869-134">Os scripts do PowerShell a seguir preparam e geram alterações de esquema gerando o script da tabela e das permissões associadas.</span><span class="sxs-lookup"><span data-stu-id="be869-134">The following PowerShell scripts prepare and generate for schema changes by scripting the table and associated permissions.</span></span>  
  
```powershell
prepare_schema_change.ps1 <serverName> <databaseName> <schemaName> <tableName>
```
  
 <span data-ttu-id="be869-135">Esse script usa como argumentos uma tabela e gera o script do objeto e de suas permissões, além de fazer referência a objetos associados ao esquema e suas permissões na pasta atual.</span><span class="sxs-lookup"><span data-stu-id="be869-135">This script takes as arguments a table, and scripts the object and its permissions and referencing schema-bound objects and their permissions in the current folder.</span></span> <span data-ttu-id="be869-136">Um total de 7 scripts é gerado para atualizar o esquema da tabela de entrada:</span><span class="sxs-lookup"><span data-stu-id="be869-136">A total of 7 scripts are generated for updating the schema of the input table:</span></span>  
  
-   <span data-ttu-id="be869-137">Copie os dados em uma tabela temporária (um heap).</span><span class="sxs-lookup"><span data-stu-id="be869-137">Copy data to a temporary table (a heap).</span></span>  
  
-   <span data-ttu-id="be869-138">Descarte os objetos associados ao esquema que fazem referência à tabela.</span><span class="sxs-lookup"><span data-stu-id="be869-138">Drop schema-bound objects referencing the table.</span></span>  
  
-   <span data-ttu-id="be869-139">Descarte a tabela.</span><span class="sxs-lookup"><span data-stu-id="be869-139">Drop the table.</span></span>  
  
-   <span data-ttu-id="be869-140">Recrie a tabela com o novo esquema e reaplique as permissões.</span><span class="sxs-lookup"><span data-stu-id="be869-140">Recreate the table with the new schema and reapply permissions.</span></span>  
  
-   <span data-ttu-id="be869-141">Copie os dados da tabela temporária na tabela recriada.</span><span class="sxs-lookup"><span data-stu-id="be869-141">Copy data from the temporary table to the recreated table.</span></span>  
  
-   <span data-ttu-id="be869-142">Recrie os objetos associados ao esquema que fazem referência à tabela e suas permissões.</span><span class="sxs-lookup"><span data-stu-id="be869-142">Recreate schema-bound objects referencing the table and their permissions.</span></span>  
  
-   <span data-ttu-id="be869-143">Descarte a tabela temporária.</span><span class="sxs-lookup"><span data-stu-id="be869-143">Drop the temporary table.</span></span>  
  
 <span data-ttu-id="be869-144">O script da etapa 4 deve ser atualizado para refletir as alterações desejadas de esquema.</span><span class="sxs-lookup"><span data-stu-id="be869-144">The script for step 4 should be updated to reflect the desired schema changes.</span></span> <span data-ttu-id="be869-145">Se houver qualquer alteração nas colunas da tabela, os scripts das etapas 5 (copiar dados de tabela temporária) e 6 (recriar procedimentos armazenados) devem ser atualizados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="be869-145">If there are any changes in the columns of the table, the scripts for steps 5 (copy data from temporary table) and 6 (recreate stored procedures) should be updated as necessary.</span></span>  
  
```powershell
# Prepare for schema changes by scripting out the table, as well as associated permissions
# Usage: prepare_schema_change.ps1 server_name db_name schema_name table_name  
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage prepare_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
$object_heap = "$object$(Get-Random)"  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$scripter = New-Object ("Microsoft.SqlServer.Management.SMO.Scripter") ($server)  
  
## initialize table variable  
$tableUrn = $server.Databases[$database].Tables[$object, $schema]  
if($tableUrn.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
## initialize scripting object  
$scriptingOptions = New-Object ("Microsoft.SqlServer.Management.SMO.ScriptingOptions")
$scriptingOptions.Permissions = $True  
$scriptingOptions.ScriptDrops = $True  
  
$scripter.Options = $scriptingOptions;  
  
Write-Host "(1) Scripting SELECT INTO $object_heap for table [$object] to 1_copy_to_heap_for_$schema`_$object.sql"  
Echo "SELECT * INTO $schema.$object_heap FROM $schema.$object WITH (SNAPSHOT)" | Out-File "1_copy_to_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Scripting DROP for procs schema-bound to [$object] 2_drop_procs_$schema`_$object.sql"  
## query referencing schema-bound objects  
$dt = $server.Databases[$database].ExecuteWithResults("select r.referencing_schema_name, r.referencing_entity_name  
from sys.dm_sql_referencing_entities ('$schema.$object', 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
where r.is_caller_dependent = 0 and m.is_schema_bound=1;")  
  
## initialize out file  
Echo "" | Out-File "2_drop_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script object   
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      $scripter.Script($so) | Out-File -Append "2_drop_procs_$schema`_$object.sql"  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
Write-Host "(3) Scripting DROP table for [$object] to 3_drop_table_$schema`_$object.sql"
$scripter.Script($tableUrn) | Out-File "3_drop_table_$schema`_$object.sql";
Write-Host "--done--"  
Write-Host ""  
  
## now script creates  
$scriptingOptions.ScriptDrops = $False  
  
Write-Host "(4) Scripting CREATE table and permissions for [$object] to !please_edit_4_create_table_$schema`_$object.sql"  
Write-Host "***** rename this script to 4_create_table.sql after completing the updates to the schema"
$scripter.Script($tableUrn) | Out-File "!please_edit_4_create_table_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Scripting INSERT INTO table from heap and UPDATE STATISTICS for [$object] to 5_copy_from_heap_$schema`_$object.sql"  
Write-Host "[update this script if columns are added to or removed from the table]"  
Echo "INSERT INTO [$schema].[$object] SELECT * FROM [$schema].[$object_heap]; UPDATE STATISTICS [$schema].[$object] WITH FULLSCAN, NORECOMPUTE" | Out-File "5_copy_from_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Scripting CREATE PROC and permissions for procedures schema-bound to [$object] to 6_create_procs_$schema`_$object.sql"  
Write-Host "[update the procedure definitions if columns are renamed or removed]"  
## initialize out file  
Echo "" | Out-File "6_create_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script the schema-bound object  
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      ForEach($s In $scripter.Script($so))  
        {  
            Echo $s | Out-File -Append "6_create_procs_$schema`_$object.sql"  
            Echo "GO" | Out-File -Append "6_create_procs_$schema`_$object.sql"  
        }  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Scripting DROP $object_heap to 7_drop_heap_$schema`_$object.sql"  
Echo "DROP TABLE $schema.$object_heap" | Out-File "7_drop_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
```  
  
 <span data-ttu-id="be869-146">O script de PowerShell a seguir executa as alterações do esquema que foram incluídas em script no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="be869-146">The following PowerShell script executes the schema changes that were scripted in the previous sample.</span></span> <span data-ttu-id="be869-147">Esse script é considerado argumento de uma tabela, além de executar os scripts de alteração do esquema que foram gerados para essa tabela e os procedimentos armazenados associados.</span><span class="sxs-lookup"><span data-stu-id="be869-147">This script takes as argument a table, and executes the schema change scripts that were generated for that table and the associated stored procedures.</span></span>  
  
 <span data-ttu-id="be869-148">Uso: execute_schema_change.ps1 *server_name \* \* db_name `schema_name` table_name*</span><span class="sxs-lookup"><span data-stu-id="be869-148">Usage: execute_schema_change.ps1 *server_name\*\*db_name`schema_name`table_name*</span></span>  
  
```powershell
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage execute_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$database = $server.Databases[$database]  
$table = $database.Tables[$object, $schema]  
if($table.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
$1 = Get-Item "1_copy_to_heap_$schema`_$object.sql"  
$2 = Get-Item "2_drop_procs_$schema`_$object.sql"  
$3 = Get-Item "3_drop_table_$schema`_$object.sql"  
$4 = Get-Item "4_create_table_$schema`_$object.sql"  
$5 = Get-Item "5_copy_from_heap_$schema`_$object.sql"  
$6 = Get-Item "6_create_procs_$schema`_$object.sql"  
$7 = Get-Item "7_drop_heap_$schema`_$object.sql"  
  
Write-Host "(1) Running SELECT INTO heap for table [$object] from 1_copy_to_heap_for_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $1.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Running DROP for procs schema-bound from [$object] 2_drop_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $2.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(3) Running DROP table for [$object] to 4_drop_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $3.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(4) Running CREATE table and permissions for [$object] from 4_create_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $4.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Running INSERT INTO table from heap for [$object] and UPDATE STATISTICS from 5_copy_from_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $5.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Running CREATE PROC and permissions for procedures schema-bound to [$object] from 6_create_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $6.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Running DROP heap from 7_drop_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $7.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
```  
  
## <a name="see-also"></a><span data-ttu-id="be869-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="be869-149">See Also</span></span>  
 [<span data-ttu-id="be869-150">Memory-Optimized Tables</span><span class="sxs-lookup"><span data-stu-id="be869-150">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
