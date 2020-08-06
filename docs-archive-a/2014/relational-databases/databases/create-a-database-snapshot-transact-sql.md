---
title: Criar um instantâneo de banco de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], creating
ms.assetid: 187fbba3-c555-4030-9bdf-0f01994c5230
author: stevestein
ms.author: sstein
ms.openlocfilehash: bae68c2d507e1dd3809e76a9d842b765d72234e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685758"
---
# <a name="create-a-database-snapshot-transact-sql"></a><span data-ttu-id="db736-102">Criar um instantâneo do banco de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="db736-102">Create a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="db736-103">A única maneira de criar um instantâneo do banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é usando o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db736-103">The only way to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot is to use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="db736-104">não dá suporte à criação de instantâneos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-104">does not support the creation of database snapshots.</span></span>  
  
-   <span data-ttu-id="db736-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="db736-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="db736-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="db736-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="db736-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="db736-107">Security</span></span>](#Security)  
  
     [<span data-ttu-id="db736-108">Melhor prática: Nomeando instantâneos do banco de dados</span><span class="sxs-lookup"><span data-stu-id="db736-108">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   <span data-ttu-id="db736-109">**Para criar um instantâneo do banco de dados usando:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="db736-109">**To create a database snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="db736-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="db736-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="db736-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="db736-111">Prerequisites</span></span>  
 <span data-ttu-id="db736-112">O banco de dados de origem, que pode usar qualquer modelo de recuperação, deve atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="db736-112">The source database, which can use any recovery model, must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="db736-113">A instância de servidor deve estar sendo executada em uma edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que oferece suporte a instantâneos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-113">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports database snapshot.</span></span> <span data-ttu-id="db736-114">Para obter informações sobre o suporte para instantâneos de banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , consulte [recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="db736-114">For information about support for database snapshots in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="db736-115">O banco de dados de origem precisa estar online, a menos que se trate de um banco de dados espelho dentro de uma sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-115">The source database must be online, unless the database is a mirror database within a database mirroring session.</span></span>  
  
-   <span data-ttu-id="db736-116">Para criar um instantâneo do banco de dados em um banco de dados espelho, o banco de dados precisa estar no[estado de espelhamento](../../database-engine/database-mirroring/mirroring-states-sql-server.md)sincronizado.</span><span class="sxs-lookup"><span data-stu-id="db736-116">To create a database snapshot on a mirror database, the database must be in the synchronized[mirroring state](../../database-engine/database-mirroring/mirroring-states-sql-server.md).</span></span>  
  
-   <span data-ttu-id="db736-117">O banco de dados de origem não pode ser configurado como banco de dados compartilhado escalonável.</span><span class="sxs-lookup"><span data-stu-id="db736-117">The source database cannot be configured as a scalable shared database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="db736-118">Para obter informações sobre outras considerações significativas, consulte [Instantâneos de banco de dados &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="db736-118">For information about other significant considerations, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="db736-119">Recomendações</span><span class="sxs-lookup"><span data-stu-id="db736-119">Recommendations</span></span>  
 <span data-ttu-id="db736-120">Esta seção aborda as seguintes práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="db736-120">This section discusses the following best practices:</span></span>  
  
-   [<span data-ttu-id="db736-121">Melhor prática: Nomeando instantâneos do banco de dados</span><span class="sxs-lookup"><span data-stu-id="db736-121">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   [<span data-ttu-id="db736-122">Melhor prática: Limitando o número de instantâneos do banco de dados</span><span class="sxs-lookup"><span data-stu-id="db736-122">Best Practice: Limiting the Number of Database Snapshots</span></span>](#Limiting_Number)  
  
-   [<span data-ttu-id="db736-123">Melhor prática: Conexões de cliente com um instantâneo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="db736-123">Best Practice: Client Connections to a Database Snapshot</span></span>](#Client_Connections)  
  
####  <a name="best-practice-naming-database-snapshots"></a><a name="Naming"></a> <span data-ttu-id="db736-124">Melhor prática: Nomeando instantâneos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="db736-124">Best Practice: Naming Database Snapshots</span></span>  
 <span data-ttu-id="db736-125">Antes de criar instantâneos, é importante considerar como serão nomeados.</span><span class="sxs-lookup"><span data-stu-id="db736-125">Before creating snapshots, it is important to consider how to name them.</span></span> <span data-ttu-id="db736-126">Cada instantâneo de banco de dados requer um nome exclusivo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-126">Each database snapshot requires a unique database name.</span></span> <span data-ttu-id="db736-127">Para facilidade administrativa, o nome de um instantâneo pode inserir informações que identifiquem o banco de dados, como:</span><span class="sxs-lookup"><span data-stu-id="db736-127">For administrative ease, the name of a snapshot can incorporate information that identifies the database, such as:</span></span>  
  
-   <span data-ttu-id="db736-128">O nome do banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="db736-128">The name of the source database.</span></span>  
  
-   <span data-ttu-id="db736-129">Uma indicação de que o nome novo destina-se a um instantâneo.</span><span class="sxs-lookup"><span data-stu-id="db736-129">An indication that the new name is for a snapshot.</span></span>  
  
-   <span data-ttu-id="db736-130">A data de criação e o horário do instantâneo, um número de sequência ou alguma outra informação, como hora do dia, para distinguir instantâneos sequenciais em um determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-130">The creation date and time of the snapshot, a sequence number, or some other information, such as time of day, to distinguish sequential snapshots on a given database.</span></span>  
  
 <span data-ttu-id="db736-131">Por exemplo, considere uma série de instantâneos para o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db736-131">For example, consider a series of snapshots for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="db736-132">Três instantâneos diários são criados em intervalos de 6 horas entre 6h</span><span class="sxs-lookup"><span data-stu-id="db736-132">Three daily snapshots are created at 6-hour intervals between 6 A.M.</span></span> <span data-ttu-id="db736-133">e 18h, com base em um relógio de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="db736-133">and 6 P.M., based on a 24-hour clock.</span></span> <span data-ttu-id="db736-134">Cada instantâneo diário é mantido durante 24 horas antes de ser descartado e substituído por um instantâneo novo de mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="db736-134">Each daily snapshot is kept for 24 hours before being dropped and replaced by a new snapshot of the same name.</span></span> <span data-ttu-id="db736-135">Note que cada nome de instantâneo indica a hora, mas não o dia:</span><span class="sxs-lookup"><span data-stu-id="db736-135">Note that each snapshot name indicates the hour, but not the day:</span></span>  
  
```  
AdventureWorks_snapshot_0600  
AdventureWorks_snapshot_1200  
AdventureWorks_snapshot_1800  
```  
  
 <span data-ttu-id="db736-136">Como alternativa, se a hora de criação desses instantâneos diários variar de um dia para o outro, uma convenção de nomenclatura menos precisa poderia ser preferível, como por exemplo:</span><span class="sxs-lookup"><span data-stu-id="db736-136">Alternatively, if the creation time of these daily snapshots varies from day to day, a less precise naming convention might be preferable, for example:</span></span>  
  
```  
AdventureWorks_snapshot_morning  
AdventureWorks_snapshot_noon  
AdventureWorks_snapshot_evening  
```  
  
####  <a name="best-practice-limiting-the-number-of-database-snapshots"></a><a name="Limiting_Number"></a> <span data-ttu-id="db736-137">Melhor prática: Limitando o número de instantâneos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="db736-137">Best Practice: Limiting the Number of Database Snapshots</span></span>  
 <span data-ttu-id="db736-138">Criar uma série de instantâneos do longo do tempo captura instantâneos sequenciais do banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="db736-138">Creating a series of snapshots over time captures sequential snapshots of the source database.</span></span> <span data-ttu-id="db736-139">Cada instantâneo persiste até que seja explicitamente descartado.</span><span class="sxs-lookup"><span data-stu-id="db736-139">Each snapshot persists until it is explicitly dropped.</span></span> <span data-ttu-id="db736-140">Como cada instantâneo continuará crescendo à medida que as páginas originais forem atualizadas, você pode preferir conservar espaço de disco excluindo um instantâneo mais antigo depois de criar um instantâneo novo.</span><span class="sxs-lookup"><span data-stu-id="db736-140">Because each snapshot will continue to grow as original pages are updated, you may want to conserve disk space by deleting an older snapshot after creating a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db736-141">Se você quiser reverter a um instantâneo de banco de dados, precisará excluir qualquer outro instantâneo desse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-141">If you want to revert to a database snapshot, you need to delete any other snapshots from that database.</span></span>  
  
####  <a name="best-practice-client-connections-to-a-database-snapshot"></a><a name="Client_Connections"></a> <span data-ttu-id="db736-142">Melhor prática: Conexões do cliente a um instantâneo de banco de dados</span><span class="sxs-lookup"><span data-stu-id="db736-142">Best Practice: Client Connections to a Database Snapshot</span></span>  
 <span data-ttu-id="db736-143">Para usar um instantâneo de banco de dados, os clientes precisam saber onde encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="db736-143">To use a database snapshot, clients need to know where to find it.</span></span> <span data-ttu-id="db736-144">Os usuários podem ler de um instantâneo de banco de dados enquanto outro está sendo criado ou excluído.</span><span class="sxs-lookup"><span data-stu-id="db736-144">Users can read from one database snapshot while another is being created or deleted.</span></span> <span data-ttu-id="db736-145">Porém, quando você substituir um instantâneo novo por um já existente, será necessário redirecionar os clientes ao novo instantâneo.</span><span class="sxs-lookup"><span data-stu-id="db736-145">However, when you substitute a new snapshot for an existing one, you need to redirect clients to the new snapshot.</span></span> <span data-ttu-id="db736-146">Os usuários podem se conectar manualmente a um instantâneo de banco de dados por meio do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db736-146">Users can manually connect to a database snapshot by means of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="db736-147">No entanto, para dar suporte a um ambiente de produção, você deverá criar uma solução programática que direcione de maneira transparente os clientes de gravação de relatório ao último instantâneo de banco de dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-147">However, to support a production environment, you should create a programmatic solution that transparently directs report-writing clients to the latest database snapshot of the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="db736-148">Segurança</span><span class="sxs-lookup"><span data-stu-id="db736-148">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="db736-149">Permissões</span><span class="sxs-lookup"><span data-stu-id="db736-149">Permissions</span></span>  
 <span data-ttu-id="db736-150">Qualquer usuário que possa criar um banco de dados pode criar um instantâneo de banco de dados, entretanto, para criar um instantâneo de um banco de dados espelho, você deve ser um membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="db736-150">Any user who can create a database can create a database snapshot; however, to create a snapshot of a mirror database, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="how-to-create-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="db736-151">Como criar um instantâneo de banco de dados (usando o Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="db736-151">How to Create a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="db736-152">**Para criar um instantâneo do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="db736-152">**To create a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db736-153">Para obter um exemplo deste procedimento, consulte [Exemplos (Transact-SQL)](#TsqlExample), posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="db736-153">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="db736-154">Com base no tamanho atual do banco de dados de origem, verifique se você tem espaço em disco suficiente para suportar o instantâneo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-154">Based on the current size of the source database, ensure that you have sufficient disk space to hold the database snapshot.</span></span> <span data-ttu-id="db736-155">O tamanho máximo de um instantâneo do banco de dados é o tamanho do banco de dados de origem no momento da criação do instantâneo.</span><span class="sxs-lookup"><span data-stu-id="db736-155">The maximum size of a database snapshot is the size of the source database at snapshot creation.</span></span> <span data-ttu-id="db736-156">Para obter mais informações, consulte [Exibir o tamanho do arquivo esparso de um instantâneo de banco de dados &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="db736-156">For more information, see [View the Size of the Sparse File of a Database Snapshot &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="db736-157">Emita uma instrução CREATE DATABASE nos arquivos usando a cláusula AS SNAPSHOT OF.</span><span class="sxs-lookup"><span data-stu-id="db736-157">Issue a CREATE DATABASE statement on the files using the AS SNAPSHOT OF clause.</span></span> <span data-ttu-id="db736-158">Criar um instantâneo requer especificar o nome lógico de cada arquivo de banco de dados do banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="db736-158">Creating a snapshot requires specifying the logical name of every database file of the source database.</span></span> <span data-ttu-id="db736-159">A sintaxe é mostrada a seguir:</span><span class="sxs-lookup"><span data-stu-id="db736-159">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="db736-160">CREATE DATABASE *database_snapshot_name*</span><span class="sxs-lookup"><span data-stu-id="db736-160">CREATE DATABASE *database_snapshot_name*</span></span>  
  
     <span data-ttu-id="db736-161">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="db736-161">ON</span></span>  
  
     <span data-ttu-id="db736-162">(</span><span class="sxs-lookup"><span data-stu-id="db736-162">(</span></span>  
  
     <span data-ttu-id="db736-163">NAME =*logical_file_name*,</span><span class="sxs-lookup"><span data-stu-id="db736-163">NAME =*logical_file_name*,</span></span>  
  
     <span data-ttu-id="db736-164">FILENAME ='*os_file_name*'</span><span class="sxs-lookup"><span data-stu-id="db736-164">FILENAME ='*os_file_name*'</span></span>  
  
     <span data-ttu-id="db736-165">) [ ,...*n* ]</span><span class="sxs-lookup"><span data-stu-id="db736-165">) [ ,...*n* ]</span></span>  
  
     <span data-ttu-id="db736-166">AS SNAPSHOT OF *source_database_name*</span><span class="sxs-lookup"><span data-stu-id="db736-166">AS SNAPSHOT OF *source_database_name*</span></span>  
  
     <span data-ttu-id="db736-167">[;]</span><span class="sxs-lookup"><span data-stu-id="db736-167">[;]</span></span>  
  
     <span data-ttu-id="db736-168">Quando *source_\*\*database_name* é o banco de dados de origem, *logical_file_name* é o nome lógico usado no SQL Server ao referenciar o arquivo, *os_file_name* é o caminho e o nome do arquivo usado pelo sistema operacional quando você cria o arquivo e *database_snapshot_name* é o nome do instantâneo para o qual você deseja reverter o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="db736-168">Where *source_\*\*database_name* is the source database, *logical_file_name i*s the logical name used in SQL Server when referencing the file, *os_file_name* is the path and file name used by the operating system when you create the file, and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="db736-169">Para obter uma descrição completa dessa sintaxe, consulte [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="db736-169">For a full description of this syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="db736-170">Quando você cria um instantâneo do banco de dados, arquivos de log, arquivos offline, arquivos de restauração e arquivos excluídos não são permitidos na instrução CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="db736-170">When you create a database snapshot, log files, offline files, restoring files, and defunct files are not allowed in the CREATE DATABASE statement.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="db736-171">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="db736-171">Examples (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db736-172">A extensão `.ss` usada nos exemplos é arbitrária.</span><span class="sxs-lookup"><span data-stu-id="db736-172">The `.ss` extension used in the examples is arbitrary.</span></span>  
  
 <span data-ttu-id="db736-173">Esta seção contém os seguintes exemplos:</span><span class="sxs-lookup"><span data-stu-id="db736-173">This section contains the following examples:</span></span>  
  
-   <span data-ttu-id="db736-174">a.</span><span class="sxs-lookup"><span data-stu-id="db736-174">A.</span></span> [<span data-ttu-id="db736-175">Criando um instantâneo no banco de dados AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="db736-175">Creating a snapshot on the AdventureWorks database</span></span>](#Creating_on_AW)  
  
-   <span data-ttu-id="db736-176">B.</span><span class="sxs-lookup"><span data-stu-id="db736-176">B.</span></span> [<span data-ttu-id="db736-177">Criando um instantâneo no banco de dados Vendas</span><span class="sxs-lookup"><span data-stu-id="db736-177">Creating a snapshot on the Sales database</span></span>](#Creating_on_Sales)  
  
####  <a name="a-creating-a-snapshot-on-the-adventureworks-database"></a><a name="Creating_on_AW"></a> <span data-ttu-id="db736-178">A.</span><span class="sxs-lookup"><span data-stu-id="db736-178">A.</span></span> <span data-ttu-id="db736-179">Criando um instantâneo no banco de dados AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="db736-179">Creating a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="db736-180">Este exemplo cria um instantâneo de banco de dados no banco de dados `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="db736-180">This example creates a database snapshot on the `AdventureWorks` database.</span></span> <span data-ttu-id="db736-181">O nome do instantâneo, `AdventureWorks_dbss_1800`e o nome do arquivo de seu respectivo arquivo esparso, `AdventureWorks_data_1800.ss`, indicam a hora da criação, 18h00.</span><span class="sxs-lookup"><span data-stu-id="db736-181">The snapshot name, `AdventureWorks_dbss_1800`, and the file name of its sparse file, `AdventureWorks_data_1800.ss`, indicate the creation time, 6 P.M (1800 hours).</span></span>  
  
```  
CREATE DATABASE AdventureWorks_dbss1800 ON  
( NAME = AdventureWorks_Data, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data\AdventureWorks_data_1800.ss' )  
AS SNAPSHOT OF AdventureWorks;  
GO  
```  
  
####  <a name="b-creating-a-snapshot-on-the-sales-database"></a><a name="Creating_on_Sales"></a> <span data-ttu-id="db736-182">B.</span><span class="sxs-lookup"><span data-stu-id="db736-182">B.</span></span> <span data-ttu-id="db736-183">Criando um instantâneo no banco de dados Vendas</span><span class="sxs-lookup"><span data-stu-id="db736-183">Creating a snapshot on the Sales database</span></span>  
 <span data-ttu-id="db736-184">Este exemplo cria um instantâneo do banco de dados, `sales_snapshot1200`, no banco de dados `Sales` .</span><span class="sxs-lookup"><span data-stu-id="db736-184">This example creates a database snapshot, `sales_snapshot1200`, on the `Sales` database.</span></span> <span data-ttu-id="db736-185">Esse banco de dados foi criado no exemplo "criando um banco de dados que tem grupos de dados" em [create database &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="db736-185">This database was created in the example, "Creating a database that has filegroups," in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
```  
--Creating sales_snapshot1200 as snapshot of the  
--Sales database:  
CREATE DATABASE sales_snapshot1200 ON  
( NAME = SPri1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri1dat_1200.ss'),  
( NAME = SPri2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri2dt_1200.ss'),  
( NAME = SGrp1Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\mssql\data\SG1Fi1dt_1200.ss'),  
( NAME = SGrp1Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG1Fi2dt_1200.ss'),  
( NAME = SGrp2Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi1dt_1200.ss'),  
( NAME = SGrp2Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi2dt_1200.ss')  
AS SNAPSHOT OF Sales;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="db736-186">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="db736-186">Related Tasks</span></span>  
  
-   [<span data-ttu-id="db736-187">Exibir um instantâneo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db736-187">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="db736-188">Reverter um banco de dados para um instantâneo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="db736-188">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="db736-189">Remover um instantâneo do banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="db736-189">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="db736-190">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db736-190">See Also</span></span>  
 <span data-ttu-id="db736-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="db736-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="db736-192">Instantâneos de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db736-192">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
