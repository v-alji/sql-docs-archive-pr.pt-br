---
title: Habilitar e desabilitar o Change Data Capture (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change data capture [SQL Server], enabling tables
- change data capture [SQL Server], enabling databases
- change data capture [SQL Server], disabling databases
- change data capture [SQL Server], disabling tables
ms.assetid: b741894f-d267-4b10-adfe-cbc14aa6caeb
author: rothja
ms.author: jroth
ms.openlocfilehash: df0a2fd4a2c6ffb2de58d6b52360d1730d0fa7df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573866"
---
# <a name="enable-and-disable-change-data-capture-sql-server"></a><span data-ttu-id="9f6ba-102">Habilitar e desabilitar o Change Data Capture (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9f6ba-102">Enable and Disable Change Data Capture (SQL Server)</span></span>
  <span data-ttu-id="9f6ba-103">Este tópico descreve como habilitar e desabilitar o Change data Capture para um banco de dados e uma tabela.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-103">This topic describes how to enable and disable change data capture for a database and a table.</span></span>  
  
## <a name="enable-change-data-capture-for-a-database"></a><span data-ttu-id="9f6ba-104">Habilitar o Change Data Capture para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="9f6ba-104">Enable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="9f6ba-105">Para que uma instância de captura possa ser criada para tabelas individuais, um membro da função de servidor fixa `sysadmin` deve primeiro habilitar o banco de dados para o Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-105">Before a capture instance can be created for individual tables, a member of the `sysadmin` fixed server role must first enable the database for change data capture.</span></span> <span data-ttu-id="9f6ba-106">Isso é feito usando o procedimento armazenado [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) no contexto de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-106">This is done by running the stored procedure [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) in the database context.</span></span> <span data-ttu-id="9f6ba-107">Para determinar se um banco de dados já está habilitado, consulte a coluna `is_cdc_enabled` na exibição do catálogo `sys.databases`.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-107">To determine if a database is already enabled, query the `is_cdc_enabled` column in the `sys.databases` catalog view.</span></span>  
  
 <span data-ttu-id="9f6ba-108">Quando um banco de dados está habilitado para o Change Data Capture, o esquema `cdc`, o usuário `cdc`, as tabelas de metadados e outros objetos de sistema são criados para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-108">When a database is enabled for change data capture, the `cdc` schema, `cdc` user, metadata tables, and other system objects are created for the database.</span></span> <span data-ttu-id="9f6ba-109">O esquema `cdc` contém as tabelas de metadados do Change Data Capture e, depois que as tabelas de origem são habilitadas para o Change Data Capture, as tabelas de alterações individuais atuam como repositório para os dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-109">The `cdc` schema contains the change data capture metadata tables and, after source tables are enabled for change data capture, the individual change tables serve as a repository for change data.</span></span> <span data-ttu-id="9f6ba-110">O esquema `cdc` também contém funções de sistema associadas usadas para consultar dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-110">The `cdc` schema also contains associated system functions used to query for change data.</span></span>  
  
 <span data-ttu-id="9f6ba-111">O Change Data Capture requer o uso exclusivo do esquema `cdc` e do usuário `cdc`.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-111">Change data capture requires exclusive use of the `cdc` schema and `cdc` user.</span></span> <span data-ttu-id="9f6ba-112">Se um esquema ou usuário de banco de dados denominado *cdc* existir atualmente em um banco de dados, o banco de dados não poderá ser habilitado para Change Data Capture até que o esquema e/ou o usuário sejam descartados ou renomeados.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-112">If either a schema or a database user named *cdc* currently exists in a database, the database cannot be enabled for change data capture until the schema and or user are dropped or renamed.</span></span>  
  
 <span data-ttu-id="9f6ba-113">Consulte o modelo Habilitar Banco de dados para Change Data Capture para obter um exemplo de como habilitar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-113">See the Enable Database for Change Data Capture template for an example of enabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9f6ba-114">Para localizar os modelos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vá para **Exibir**, clique em **Explorador de Modelos**e selecione **Modelos do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-114">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then select **SQL Server Templates**.</span></span> <span data-ttu-id="9f6ba-115">**Change Data Capture** é uma subpasta.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-115">**Change Data Capture** is a sub-folder.</span></span> <span data-ttu-id="9f6ba-116">Nesta pasta, você encontrará todos os modelos referenciados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-116">Under this folder, you will find all the templates referenced in this topic.</span></span> <span data-ttu-id="9f6ba-117">Também há um ícone do **Explorador de Modelos** na barra de ferramentas [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f6ba-117">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- ====  
-- Enable Database for CDC template   
-- ====  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_db  
GO  
```  
  
## <a name="disable-change-data-capture-for-a-database"></a><span data-ttu-id="9f6ba-118">Desabilitar o Change Data Capture para um banco de dados</span><span class="sxs-lookup"><span data-stu-id="9f6ba-118">Disable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="9f6ba-119">Um membro da `sysadmin` função de servidor fixa pode executar o procedimento armazenado [sys. Sp_cdc_disable_db &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) no contexto do banco de dados para desabilitar o Change Data Capture para um banco de dado.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-119">A member of the `sysadmin` fixed server role can run the stored procedure [sys.sp_cdc_disable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) in the database context to disable change data capture for a database.</span></span> <span data-ttu-id="9f6ba-120">Não é necessário desabilitar tabelas individuais antes de desabilitar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-120">It is not necessary to disable individual tables before you disable the database.</span></span> <span data-ttu-id="9f6ba-121">A desabilitação do banco de dados removerá todos os metadados de Change Data Capture associados, inclusive o usuário e o esquema `cdc` e os trabalhos de Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-121">Disabling the database removes all associated change data capture metadata, including the `cdc` user and schema and the change data capture jobs.</span></span> <span data-ttu-id="9f6ba-122">No entanto, qualquer função associada criada pelo Change Data Capture não será removida automaticamente e deverá ser excluída explicitamente.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-122">However, any gating roles created by change data capture will not be removed automatically and must be explicitly deleted.</span></span> <span data-ttu-id="9f6ba-123">Para determinar se um banco de dados está habilitado, consulte a coluna `is_cdc_enabled` na exibição de catálogo sys.databases.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-123">To determine if a database is enabled, query the `is_cdc_enabled` column in the sys.databases catalog view.</span></span>  
  
 <span data-ttu-id="9f6ba-124">Se um banco de dados habilitado do Change Data Capture for descartado, os trabalhos de Change Data Capture serão removidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-124">If a change data capture enabled database is dropped, change data capture jobs are automatically removed.</span></span>  
  
 <span data-ttu-id="9f6ba-125">Consulte o modelo Desabilitar Banco de dados para Change Data Capture para obter um exemplo de como desabilitar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-125">See the Disable Database for Change Data Capture template for an example of disabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9f6ba-126">Para localizar os modelos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vá para **Exibir**, clique em **Explorador de Modelos**e em **Modelos do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-126">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then click **SQL Server Templates**.</span></span> <span data-ttu-id="9f6ba-127">**Change Data Capture** é uma subpasta na qual você encontrará todos os modelos referenciados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-127">**Change Data Capture** is a sub-folder where you will find all the templates that are referenced in this topic.</span></span> <span data-ttu-id="9f6ba-128">Também há um ícone do **Explorador de Modelos** na barra de ferramentas [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f6ba-128">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- =======  
-- Disable Database for Change Data Capture template   
-- =======  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_db  
GO  
```  
  
## <a name="enable-change-data-capture-for-a-table"></a><span data-ttu-id="9f6ba-129">Habilitar o Change Data Capture para uma tabela</span><span class="sxs-lookup"><span data-stu-id="9f6ba-129">Enable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="9f6ba-130">Após a habilitação de um banco de dados para Change Data Capture, os membros da função de banco de dados fixa `db_owner` poderão criar uma instância de captura para tabelas de origem individuais usando o procedimento armazenado `sys.sp_cdc_enable_table`.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-130">After a database has been enabled for change data capture, members of the `db_owner` fixed database role can create a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_enable_table`.</span></span> <span data-ttu-id="9f6ba-131">Para determinar se uma tabela de origem já foi habilitada para Change Data Capture, examine a coluna is_tracked_by_cdc na exibição do catálogo `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-131">To determine whether a source table has already been enabled for change data capture, examine the is_tracked_by_cdc column in the `sys.tables` catalog view.</span></span>  
  
 <span data-ttu-id="9f6ba-132">As seguintes opções podem ser especificadas durante a criação de uma instância de captura:</span><span class="sxs-lookup"><span data-stu-id="9f6ba-132">The following options can be specified when creating a capture instance:</span></span>  
  
 <span data-ttu-id="9f6ba-133">`Columns in the source table to be captured`.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-133">`Columns in the source table to be captured`.</span></span>  
  
 <span data-ttu-id="9f6ba-134">Por padrão, todas as colunas na tabela de origem são identificadas como colunas capturadas.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-134">By default, all of the columns in the source table are identified as captured columns.</span></span> <span data-ttu-id="9f6ba-135">Se apenas um subconjunto de colunas precisar ser acompanhado, por exemplo, por motivos de privacidade ou desempenho, use o *@captured_column_list* parâmetro para especificar o subconjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-135">If only a subset of columns need to be tracked, such as for privacy or performance reasons, use the *@captured_column_list* parameter to specify the subset of columns.</span></span>  
  
 `A filegroup to contain the change table.`  
  
 <span data-ttu-id="9f6ba-136">Por padrão, a tabela de alteração está localizada no grupo de arquivos padrão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-136">By default, the change table is located in the default filegroup of the database.</span></span> <span data-ttu-id="9f6ba-137">Proprietários de banco de dados que desejam controlar o posicionamento de tabelas de alteração individuais podem usar o *@filegroup_name* parâmetro para especificar um grupo de arquivos específico para a tabela de alteração associada à instância de captura.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-137">Database owners who want to control the placement of individual change tables can use the *@filegroup_name* parameter to specify a particular filegroup for the change table associated with the capture instance.</span></span> <span data-ttu-id="9f6ba-138">O grupo de arquivos nomeado já deve existir.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-138">The named filegroup must already exist.</span></span> <span data-ttu-id="9f6ba-139">Geralmente, é recomendável que tabelas de alterações sejam colocadas em um grupo de arquivos separado das tabelas de origem.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-139">Generally, it is recommended that change tables be placed in a filegroup separate from source tables.</span></span> <span data-ttu-id="9f6ba-140">Consulte o `Enable a Table Specifying Filegroup Option` modelo para ver um exemplo que mostra o uso do *@filegroup_name* parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-140">See the `Enable a Table Specifying Filegroup Option` template for an example showing use of the *@filegroup_name* parameter.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Specifying Filegroup Option Template  
-- =========  
USE MyDB  
GO  
  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@filegroup_name = N'MyDB_CT',  
@supports_net_changes = 1  
GO  
```  
  
 `A role for controlling access to a change table.`  
  
 <span data-ttu-id="9f6ba-141">O propósito da função nomeada é controlar o acesso aos dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-141">The purpose of the named role is to control access to the change data.</span></span> <span data-ttu-id="9f6ba-142">A função especificada pode ser uma função de servidor fixa existente ou uma função de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-142">The specified role can be an existing fixed server role or a database role.</span></span> <span data-ttu-id="9f6ba-143">Se a função especificada ainda não existir, uma função de banco de dados com esse nome será criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-143">If the specified role does not already exist, a database role of that name is created automatically.</span></span> <span data-ttu-id="9f6ba-144">Os membros da função `sysadmin` ou `db_owner` têm acesso completo aos dados nas tabelas de alterações.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-144">Members of either the `sysadmin` or `db_owner` role have full access to the data in the change tables.</span></span> <span data-ttu-id="9f6ba-145">Todos os outros usuários devem ter a permissão SELECT em todas as colunas capturadas da tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-145">All other users must have SELECT permission on all the captured columns of the source table.</span></span> <span data-ttu-id="9f6ba-146">Além disso, quando uma função é especificada, os usuários que não são membros da função `sysadmin` ou `db_owner` também devem ser membros da função especificada.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-146">In addition, when a role is specified, users who are not members of either the `sysadmin` or `db_owner` role must also be members of the specified role.</span></span>  
  
 <span data-ttu-id="9f6ba-147">Se você não quiser usar uma função de retenção, defina explicitamente o *@role_name* parâmetro como NULL.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-147">If you do not want to use a gating role, explicitly set the *@role_name* parameter to NULL.</span></span> <span data-ttu-id="9f6ba-148">Consulte o modelo `Enable a Table Without Using a Gating Role` para obter um exemplo de como habilitar uma tabela sem uma função associada.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-148">See the `Enable a Table Without Using a Gating Role` template for an example of enabling a table without a gating role.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Without Using a Gating Role template   
-- =========  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = NULL,  
@supports_net_changes = 1  
GO  
  
```  
  
 `A function to query for net changes.`  
  
 <span data-ttu-id="9f6ba-149">Uma instância de captura sempre incluirá uma função com valor de tabela para retornar todas as entradas de tabela de alterações que ocorreram dentro de um intervalo definido.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-149">A capture instance will always include a table valued function for returning all change table entries that occurred within a defined interval.</span></span> <span data-ttu-id="9f6ba-150">Essa função é denominada com a anexação do nome da instância de captura para "cdc.fn_cdc_get_all_changes_".</span><span class="sxs-lookup"><span data-stu-id="9f6ba-150">This function is named by appending the capture instance name to "cdc.fn_cdc_get_all_changes_".</span></span> <span data-ttu-id="9f6ba-151">Para obter mais informações, veja [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9f6ba-151">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="9f6ba-152">Se o parâmetro *@supports_net_changes* for definido como 1, uma função de alterações líquidas também será gerada para a instância de captura.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-152">If the parameter *@supports_net_changes* is set to 1, a net changes function is also generated for the capture instance.</span></span> <span data-ttu-id="9f6ba-153">Essa função retorna apenas uma alteração para cada linha distinta alterada no intervalo especificado na chamada.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-153">This function returns only one change for each distinct row changed in the interval specified in the call.</span></span> <span data-ttu-id="9f6ba-154">Para obter mais informações, veja [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9f6ba-154">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="9f6ba-155">Para dar suporte às consultas de entradas, a tabela de origem deve ter uma chave primária ou índice exclusivo para identificar linhas.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-155">To support net changes queries, the source table must have a primary key or unique index to uniquely identify rows.</span></span> <span data-ttu-id="9f6ba-156">Se um índice exclusivo for usado, o nome do índice deverá ser especificado usando o *@index_name* parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-156">If a unique index is used, the name of the index must be specified using the *@index_name* parameter.</span></span> <span data-ttu-id="9f6ba-157">As colunas definidas na chave primária ou índice exclusivo deverão ser incluídas na lista de colunas de origem a serem capturadas.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-157">The columns defined in the primary key or unique index must be included in the list of source columns to be captured.</span></span>  
  
 <span data-ttu-id="9f6ba-158">Consulte o modelo `Enable a Table for All and Net Changes Queries` para obter um exemplo que demonstra a criação de uma instância de captura com ambas as funções de consulta.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-158">See the `Enable a Table for All and Net Changes Queries` template for an example demonstrating the creation of a capture instance with both query functions.</span></span>  
  
```sql  
-- =============  
-- Enable a Table for All and Net Changes Queries template   
-- =============  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@supports_net_changes = 1  
GO  
```  
  
> [!NOTE]
>  <span data-ttu-id="9f6ba-159">Se a captura de dados de alterações estiver habilitada em uma tabela com uma chave primária existente e o *@index_name* parâmetro não for usado para identificar um índice exclusivo alternativo, o recurso de captura de dados de alterações usará a chave primária.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-159">If change data capture is enabled on a table with an existing primary key, and the *@index_name* parameter is not used to identify an alternative unique index, the change data capture feature will use the primary key.</span></span> <span data-ttu-id="9f6ba-160">Alterações subsequentes à chave primária não serão permitidas sem a desabilitação primeiro do Change Data Capture para a tabela.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-160">Subsequent changes to the primary key will not be allowed without first disabling change data capture for the table.</span></span> <span data-ttu-id="9f6ba-161">Isso é verdadeiro quer o suporte para consultas de alterações globais tenha sido solicitado ou não durante a configuração do Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-161">This is true regardless of whether support for net changes queries was requested when change data capture was configured.</span></span> <span data-ttu-id="9f6ba-162">Se não houver nenhuma chave primária em uma tabela quando ela for habilitada para o Change Data Capture, a adição subsequente de uma chave primária será ignorada pelo Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-162">If there is no primary key on a table at the time it is enabled for change data capture, the subsequent addition of a primary key is ignored by change data capture.</span></span> <span data-ttu-id="9f6ba-163">Como o Change Data Capture não usará uma chave primária criada após a habilitação da tabela, a chave e as colunas de chave poderão ser removidas sem restrições.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-163">Because change data capture will not use a primary key that is created after the table was enabled, the key and key columns can be removed without restrictions.</span></span>  
  
## <a name="disable-change-data-capture-for-a-table"></a><span data-ttu-id="9f6ba-164">Desabilitar o Change Data Capture para uma tabela</span><span class="sxs-lookup"><span data-stu-id="9f6ba-164">Disable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="9f6ba-165">Os membros da função de banco de dados fixa `db_owner` poderão remover uma instância de captura para tabelas de origem individuais usando o procedimento armazenado `sys.sp_cdc_disable_table`.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-165">Members of the `db_owner` fixed database role can remove a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_disable_table`.</span></span> <span data-ttu-id="9f6ba-166">Para determinar se uma tabela de origem está habilitada atualmente para Change Data Capture, examine a coluna `is_tracked_by_cdc` na exibição de catálogo `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-166">To determine whether a source table is currently enabled for change data capture, examine the `is_tracked_by_cdc` column in the `sys.tables` catalog view.</span></span> <span data-ttu-id="9f6ba-167">Se não houver tabelas habilitadas para o banco de dados após a desabilitação, os trabalhos do Change Data Capture também serão removidos.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-167">If there are no tables enabled for the database after the disabling takes place, the change data capture jobs are also removed.</span></span>  
  
 <span data-ttu-id="9f6ba-168">Se uma tabela habilitado do Change Data Capture for descartada, os metadados associados à tabela de Change Data Capture serão removidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-168">If a change data capture-enabled table is dropped, change data capture metadata that is associated with the table is automatically removed.</span></span>  
  
 <span data-ttu-id="9f6ba-169">Consulte o modelo Desabilitar uma Instância de Captura para uma Tabela para obter um exemplo de como desabilitar uma tabela.</span><span class="sxs-lookup"><span data-stu-id="9f6ba-169">See the Disable a Capture Instance for a Table template for an example of disabling a table.</span></span>  
  
```sql  
-- =====  
-- Disable a Capture Instance for a Table template   
-- =====  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@capture_instance = N'dbo_MyTable'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f6ba-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f6ba-170">See Also</span></span>  
 <span data-ttu-id="9f6ba-171">[Controle de alterações de dados &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f6ba-171">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="9f6ba-172">[Sobre a captura de dados de alterações &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f6ba-172">[About Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span></span>  
 <span data-ttu-id="9f6ba-173">[Trabalhar com dados de alterações &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f6ba-173">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="9f6ba-174">Administrar e monitorar a captura de dados de alteração &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9f6ba-174">Administer and Monitor Change Data Capture &#40;SQL Server&#41;</span></span>](../track-changes/administer-and-monitor-change-data-capture-sql-server.md)  
  
  
