---
title: Replicação para assinantes de tabela com otimização de memória | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
ms.assetid: 1a8e6bc7-433e-471d-b646-092dc80a2d1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df61b83d2f6d07cbbd21773b8940dd4e5341f76b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569326"
---
# <a name="replication-to-memory-optimized-table-subscribers"></a><span data-ttu-id="84433-102">Replicação para assinantes de tabela com otimização de memória</span><span class="sxs-lookup"><span data-stu-id="84433-102">Replication to Memory-Optimized Table Subscribers</span></span>
  <span data-ttu-id="84433-103">As tabelas que atuam como assinantes de replicação transacional, com exceção da replicação transacional ponto a ponto, podem ser configuradas como tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-103">Tables acting as transactional replication subscribers, excluding Peer-to-peer transactional replication, can be configured as memory-optimized tables.</span></span> <span data-ttu-id="84433-104">Outras configurações de replicação não são compatíveis com tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-104">Other replication configurations are not compatible with memory-optimized tables.</span></span>  
  
## <a name="configuring-a-memory-optimized-table-as-a-subscriber"></a><span data-ttu-id="84433-105">Configurando uma tabela com otimização de memória como um assinante</span><span class="sxs-lookup"><span data-stu-id="84433-105">Configuring a memory-optimized table as a subscriber</span></span>  
 <span data-ttu-id="84433-106">Para configurar uma tabela com otimização de memória como um assinante, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="84433-106">To configure a memory-optimized table as a subscriber, perform the following steps.</span></span>  
  
 <span data-ttu-id="84433-107">**Criar e habilitar a publicação**</span><span class="sxs-lookup"><span data-stu-id="84433-107">**Create and Enable Publication**</span></span>  
  
1.  <span data-ttu-id="84433-108">Crie uma publicação.</span><span class="sxs-lookup"><span data-stu-id="84433-108">Create a publication.</span></span>  
  
2.  <span data-ttu-id="84433-109">Adicione artigos à publicação.</span><span class="sxs-lookup"><span data-stu-id="84433-109">Add articles to the publication.</span></span> <span data-ttu-id="84433-110">Para o parâmetro `@upd_cmd`, use a convenção SCALL ou SQL.</span><span class="sxs-lookup"><span data-stu-id="84433-110">For the `@upd_cmd` parameter, use the SCALL or SQL convention.</span></span>  
  
    ```  
    EXEC sp_addarticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @source_owner = N'dbo',  
        @source_object = N'Mem_Table',  
        @type = N'logbased',  
        @description = null,  
        @creation_script = null,  
        @pre_creation_cmd = N'none',  
        @schema_option = 0x00000000080050DF,  
        @identityrangemanagementoption = N'manual',  
        @destination_table = N'Mem_Table',  
        @destination_owner = N'dbo',  
        @vertical_partition = N'false',  
        @ins_cmd = N'CALL sp_MSins_Mem_Table',  
        @del_cmd = N'CALL sp_MSdel_Mem_Table',  
        @upd_cmd = N'SCALL sp_MSupd_Mem_Table';  
    GO  
    ```  
  
 <span data-ttu-id="84433-111">**Gerar um instantâneo e ajustar o esquema**</span><span class="sxs-lookup"><span data-stu-id="84433-111">**Generate a Snapshot and Adjust the Schema**</span></span>  
  
1.  <span data-ttu-id="84433-112">Crie um trabalho de instantâneo e gere um instantâneo.</span><span class="sxs-lookup"><span data-stu-id="84433-112">Create a snapshot job and generate a snapshot.</span></span>  
  
    ```  
    EXEC sp_addpublication_snapshot @publication = N'Publication1', @frequency_type = 1;  
    EXEC sp_startpublication_snapshot @publication = N'Publication1';  
    ```  
  
2.  <span data-ttu-id="84433-113">Navegue para a pasta do instantâneo.</span><span class="sxs-lookup"><span data-stu-id="84433-113">Navigate to the snapshot folder.</span></span> <span data-ttu-id="84433-114">O local padrão é "C:\Program Files\Microsoft SQL Server\MSSQL12. \<INSTANCE> \MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS \\ ".</span><span class="sxs-lookup"><span data-stu-id="84433-114">The default location is "C:\Program Files\Microsoft SQL Server\MSSQL12.\<INSTANCE>\MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS\\".</span></span>  
  
3.  <span data-ttu-id="84433-115">Localize o **. SCH** o arquivo para a tabela e abra-o no Management Studio.</span><span class="sxs-lookup"><span data-stu-id="84433-115">Locate the **.SCH** file for your table and open it in Management Studio.</span></span> <span data-ttu-id="84433-116">Altere o esquema da tabela e atualize o procedimento armazenado conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="84433-116">Change the table schema and update the stored procedure as described below.</span></span>  
  
     <span data-ttu-id="84433-117">Avalie os índices definidos no arquivo IDX.</span><span class="sxs-lookup"><span data-stu-id="84433-117">Evaluate the indexes defined in the IDX file.</span></span> <span data-ttu-id="84433-118">Modifique `CREATE TABLE` para especificar os índices necessários, as restrições, a chave primária e a sintaxe com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-118">Modify `CREATE TABLE` to specify the required indexes, constraints, primary key, and memory-optimized syntax.</span></span> <span data-ttu-id="84433-119">Para tabelas com otimização de memória, as colunas de índice devem ser NOT NULL e as colunas de índice de tipos de caractere devem ser Unicode e usar a ordenação BIN2.</span><span class="sxs-lookup"><span data-stu-id="84433-119">For memory-optimized tables, index columns should be NOT NULL and index columns of character types must be Unicode and use BIN2 collation.</span></span> <span data-ttu-id="84433-120">Veja o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="84433-120">See example below:</span></span>  
  
    ```  
    SET ANSI_PADDING ON;  
    GO  
  
    SET ANSI_NULLS ON;  
    GO  
  
    SET QUOTED_IDENTIFIER ON;  
    GO  
  
    CREATE TABLE [dbo].[Mem_Table]([c1] [int] NOT NULL,  
        [c2] [float] NOT NULL,  
        [c3] [decimal](10, 2) NOT NULL,  
        [c4] [nvarchar](5) COLLATE SQL_Latin1_General_CP850_BIN2 NOT NULL,  
        INDEX [hash_index_sample_memoryoptimizedtable_c2] HASH (c2) WITH (BUCKET_COUNT = 1024),  
        INDEX [index_sample_memoryoptimizedtable_c3] NONCLUSTERED ([c3]),  
        INDEX [nvarchar_index_sample_memoryoptimizedtable_c4] ([c4]),  
        CONSTRAINT [PK_sample_memoryoptimizedtable] PRIMARY KEY NONCLUSTERED ([c1])) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA);  
    GO  
    ```  
  
4.  <span data-ttu-id="84433-121">Ao usar a convenção SCALL para o parâmetro `@upd_cmd`, acesse o arquivo de esquema (.SCH) e altere a instrução de atualização de tabela em `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` para remover as colunas de chave primária.</span><span class="sxs-lookup"><span data-stu-id="84433-121">When using SCALL convention for the `@upd_cmd` parameter, go to the schema (.SCH) file and change the table update statement in `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` to remove primary key columns.</span></span>  
  
     <span data-ttu-id="84433-122">Para oferecer suporte a atualizações de chave primária, use um procedimento armazenado de atualização personalizada para substituir a instrução de atualização de chave primária, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="84433-122">To support primary key updates, use a custom update stored procedure to replace the primary key update statement, as follows:</span></span>  
  
    1.  <span data-ttu-id="84433-123">Selecione valores de coluna ausentes (SCALL fornece apenas a coluna envolvida na operação de atualização).</span><span class="sxs-lookup"><span data-stu-id="84433-123">Select missing column values (SCALL only provides the column involved into the update operation).</span></span>  
  
    2.  <span data-ttu-id="84433-124">Exclua o registro existente.</span><span class="sxs-lookup"><span data-stu-id="84433-124">Delete the existing record.</span></span>  
  
    3.  <span data-ttu-id="84433-125">Insira um novo registro com os novos valores fornecidos incluindo a nova chave primária.</span><span class="sxs-lookup"><span data-stu-id="84433-125">Insert a new record with new values provided including the new primary key.</span></span>  
  
     <span data-ttu-id="84433-126">O procedimento de atualização original tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="84433-126">The original update procedure looks like this:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
                   [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="84433-127">Se a chave primária nunca deve ser atualizada em um publicador.</span><span class="sxs-lookup"><span data-stu-id="84433-127">If the primary key should never be updated on a publisher.</span></span> <span data-ttu-id="84433-128">Comente a partir da atualização dessas colunas no procedimento de atualização da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="84433-128">Comment out the update to such columns in the update procedure as follows:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
    --             [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="84433-129">Para permitir o suporte a atualizações para a chave primária, modifique o procedimento de atualização para ser da seguinte maneira</span><span class="sxs-lookup"><span data-stu-id="84433-129">To allow the support of updates to the primary key, modify the update procedure to read as follows</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                    @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    select  
                   @c1 = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   @c2 = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   @c3 = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   @c4 = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    from [dbo].[Mem_Table] where [c1] = @pkc1  
    if @@rowcount <> 0 begin  
            delete [dbo].[Mem_Table] where [c1] = @pkc1  
            if @@rowcount <> 0  
                   insert into [dbo].[Mem_Table]([c1],  
                           [c2],  
                           [c3],  
                           [c4]) values (  
                           @c1,  
                           @c2,  
                           @c3,  
                           @c4  
                   )   
    end  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
5.  <span data-ttu-id="84433-130">Crie um banco de dados do assinante usando a opção **elevar ao isolamento de instantâneo** e defina o agrupamento padrão como Latin1_General_CS_AS_KS_WS no caso de uso de tipos de dados de caracteres não Unicode.</span><span class="sxs-lookup"><span data-stu-id="84433-130">Create subscriber database using the **elevate to snapshot isolation** option and set the default collation to Latin1_General_CS_AS_KS_WS in case of using non Unicode character data types.</span></span>  
  
    ```  
    CREATE DATABASE [Sub]   
    CONTAINMENT = NONE   
    ON PRIMARY ( NAME = [Sub], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.mdf]),   
    FILEGROUP [mem] CONTAINS MEMORY_OPTIMIZED_DATA ( NAME = [mem],   
    FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub])  
    LOG ON ( NAME = [Sub_log], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.ldf])  
    COLLATE Latin1_General_CS_AS_KS_WS;  
  
    ALTER DATABASE [Sub] SET MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT = ON;  
    GO  
    ```  
  
6.  <span data-ttu-id="84433-131">Aplique o esquema ao banco de dados de um assinante e salve o esquema para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="84433-131">Apply the schema to a subscriber's database and save the schema for future use.</span></span>  
  
7.  <span data-ttu-id="84433-132">Carregue os dados do publicador (origem) para o assinante.</span><span class="sxs-lookup"><span data-stu-id="84433-132">Load the publisher (source) data to the subscriber.</span></span> <span data-ttu-id="84433-133">Os dados não devem ser alterados no publicador até que você adicione uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="84433-133">Data should not change at the publisher until you add a subscription.</span></span>  <span data-ttu-id="84433-134">Você pode usar BCP conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="84433-134">You can use BCP as shown below:</span></span>  
  
    ```  
    bcp Pub.dbo.Mem_Table out Mem_Table.bcp -S. -T -C1252 -n  
    bcp Sub.dbo.Mem_Table in Mem_Table.bcp -S. -T -C1252 -n  
    ```  
  
8.  <span data-ttu-id="84433-135">Reconfigure o artigo para desabilitar alterações de esquema no assinante:</span><span class="sxs-lookup"><span data-stu-id="84433-135">Reconfigure the article to disable schema changes on the subscriber:</span></span>  
  
    ```  
    EXEC sp_changearticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @property = N'schema_option',  
        @value = 0,  
        @force_invalidate_snapshot = 1,  
        @force_reinit_subscription = 1;  
    GO  
    ```  
  
 <span data-ttu-id="84433-136">**Adicionar assinatura sem sincronização**</span><span class="sxs-lookup"><span data-stu-id="84433-136">**Add no sync Subscription**</span></span>  
  
 <span data-ttu-id="84433-137">Adicione uma assinatura sem sincronização.</span><span class="sxs-lookup"><span data-stu-id="84433-137">Add a nosync subscription.</span></span>  
  
```  
EXEC sp_addsubscription  
    @publication = N' Publication1',  
    @subscriber = @@ServerName,  
    @destination_db = N'Sub',  
    @subscription_type = N'Push',  
    @sync_type = N'replication support only',  
    @article = N'all',  
    @update_mode = N'read only',  
    @subscriber_type = 0;  
GO  
```  
  
 <span data-ttu-id="84433-138">As tabelas com otimização de memória agora devem começar a receber atualizações do publicador.</span><span class="sxs-lookup"><span data-stu-id="84433-138">Memory-optimized tables should now start receiving updates from the publisher.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="84433-139">Restrições</span><span class="sxs-lookup"><span data-stu-id="84433-139">Restrictions</span></span>  
 <span data-ttu-id="84433-140">Somente há suporte para a replicação transacional unidirecional.</span><span class="sxs-lookup"><span data-stu-id="84433-140">Only one-way transactional replication is supported.</span></span> <span data-ttu-id="84433-141">Não há suporte para a replicação transacional ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="84433-141">Peer-to-peer transactional replication is not supported.</span></span>  
  
 <span data-ttu-id="84433-142">Não é possível publicar as tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-142">Memory-optimized tables cannot be published.</span></span>  
  
 <span data-ttu-id="84433-143">As tabelas de replicação no distribuidor não podem ser configuradas como tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-143">Replication tables on the distributor cannot be configured as memory-optimized tables.</span></span>  
  
 <span data-ttu-id="84433-144">A replicação de mesclagem não pode incluir tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-144">Merge replication cannot include memory-optimized tables.</span></span>  
  
 <span data-ttu-id="84433-145">No assinante, as tabelas envolvidas na replicação transacional podem ser configuradas como tabelas com otimização de memória, mas as tabelas do assinante devem atender aos requisitos de tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-145">At the subscriber, tables involved in transactional replication can be configured as memory optimized tables, but the subscriber tables must meet the requirements of memory-optimized tables.</span></span> <span data-ttu-id="84433-146">Isso requer as restrições a seguir.</span><span class="sxs-lookup"><span data-stu-id="84433-146">This requires the following restrictions.</span></span>  
  
-   <span data-ttu-id="84433-147">Para criar uma tabela com otimização de memória em um assinante de replicação transacional, os arquivos de esquema do instantâneo usados para criar as tabelas com otimização de memória deverão ser modificados manualmente.</span><span class="sxs-lookup"><span data-stu-id="84433-147">To create a memory-optimized table on a transactional replication subscriber, the snapshot schema files used to create the memory-optimized tables must be manually modified.</span></span> <span data-ttu-id="84433-148">Para obter mais informações, consulte [modificando um arquivo de esquema](#Schema).</span><span class="sxs-lookup"><span data-stu-id="84433-148">For more information, see [Modifying a schema file](#Schema).</span></span>  
  
-   <span data-ttu-id="84433-149">As tabelas replicadas nas tabelas com otimização de memória em um assinante estão limitadas a 8060 bytes por limite de linha de tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-149">Tables replicated to memory-optimized tables on a subscriber are limited to the 8060 bytes per row limit of memory-optimized tables.</span></span>  
  
-   <span data-ttu-id="84433-150">As tabelas replicadas nas tabelas com otimização de memória em um assinante estão limitadas a tipos de dados permitidos em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-150">Tables replicated to memory-optimized tables on a subscriber are limited to the data types permitted in memory-optimized tables.</span></span> <span data-ttu-id="84433-151">Para obter mais informações, consulte [tipos de dados com suporte](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="84433-151">For more information, see [Supported Data Types](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span></span>  
  
-   <span data-ttu-id="84433-152">Há restrições na atualização da chave primária das tabelas que estão sendo replicadas para uma tabela com otimização de memória em um assinante.</span><span class="sxs-lookup"><span data-stu-id="84433-152">There are restrictions on updating the primary key of tables being replicated to a memory-optimized table on a subscriber.</span></span> <span data-ttu-id="84433-153">Para obter mais informações, consulte [Replicando alterações em uma chave primária](#PrimaryKey).</span><span class="sxs-lookup"><span data-stu-id="84433-153">For more information, see [Replicating changes to a primary key](#PrimaryKey).</span></span>  
  
-   <span data-ttu-id="84433-154">A chave estrangeira, a restrição exclusiva, os disparadores, as modificações de esquema, ROWGUIDCOL, as colunas computadas, a compactação de dados, os tipos de dados de alias, o controle de versões e os bloqueios não têm suporte em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="84433-154">Foreign key, unique constraint, triggers, schema modifications, ROWGUIDCOL, computed columns, data compression, alias data types, versioning, and locks are not supported in memory-optimized tables.</span></span> <span data-ttu-id="84433-155">Consulte [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) para obter informações.</span><span class="sxs-lookup"><span data-stu-id="84433-155">See [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) for information.</span></span>  
  
##  <a name="modifying-a-schema-file"></a><a name="Schema"></a><span data-ttu-id="84433-156">Modificando um arquivo de esquema</span><span class="sxs-lookup"><span data-stu-id="84433-156">Modifying a schema file</span></span>  
  
-   <span data-ttu-id="84433-157">Índices clusterizados não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="84433-157">Clustered indexes are not supported.</span></span> <span data-ttu-id="84433-158">Altere todos os índices clusterizados para índices não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="84433-158">Change any clustered indexes to nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="84433-159">Todas as colunas na chave de um índice devem ser especificadas como `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="84433-159">All columns in the key of an index must be specified as `NOT NULL`.</span></span>  
  
-   <span data-ttu-id="84433-160">Se você estiver usando a opção de tabela com otimização de memória `DURABILITY = SCHEMA_AND_DATA` , a tabela deverá ter um índice de chave primária não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="84433-160">If using the memory-optimized table option `DURABILITY = SCHEMA_AND_DATA` the table must have a nonclustered primary key index.</span></span>  
  
-   <span data-ttu-id="84433-161">ANSI_PADDING deve ser ON.</span><span class="sxs-lookup"><span data-stu-id="84433-161">ANSI_PADDING must be ON.</span></span>  
  
##  <a name="replicating-changes-to-a-primary-key"></a><a name="PrimaryKey"></a><span data-ttu-id="84433-162">Replicando alterações em uma chave primária</span><span class="sxs-lookup"><span data-stu-id="84433-162">Replicating changes to a primary key</span></span>  
 <span data-ttu-id="84433-163">A chave primária de uma tabela com otimização de memória não pode ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="84433-163">The primary key of a memory-optimized table cannot be updated.</span></span> <span data-ttu-id="84433-164">Para replicar uma atualização de chave primária em um assinante, modifique o procedimento armazenado de atualização para fornecer a atualização como um par de inserção e exclusão.</span><span class="sxs-lookup"><span data-stu-id="84433-164">To replicate a primary key update on a subscriber, modify the update stored procedure to deliver the update as a delete and insert pair.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84433-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84433-165">See Also</span></span>  
 [<span data-ttu-id="84433-166">Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="84433-166">SQL Server Replication</span></span>](sql-server-replication.md)  
  
  
