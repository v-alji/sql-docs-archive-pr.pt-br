---
title: Migrar para um banco de dados parcialmente independente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, migrating to
ms.assetid: 90faac38-f79e-496d-b589-e8b2fe01c562
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6142d46dc0540e5998fa66d463538d1453a17d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685726"
---
# <a name="migrate-to-a-partially-contained-database"></a><span data-ttu-id="cd8ee-102">Migrate to a Partially Contained Database</span><span class="sxs-lookup"><span data-stu-id="cd8ee-102">Migrate to a Partially Contained Database</span></span>
  <span data-ttu-id="cd8ee-103">Este tópico discute como preparar para alterar para o modelo de banco de dados independente parcialmente e, em seguida, fornece as etapas de migração.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-103">This topic discusses how to prepare to change to the partially contained database model and then provides the migration steps.</span></span>  
  
 <span data-ttu-id="cd8ee-104">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="cd8ee-104">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="cd8ee-105">Preparando para migrar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="cd8ee-105">Preparing to Migrate a Database</span></span>](#prepare)  
  
-   [<span data-ttu-id="cd8ee-106">Habilitar bancos de dados independentes</span><span class="sxs-lookup"><span data-stu-id="cd8ee-106">Enable Contained Databases</span></span>](#enable)  
  
-   [<span data-ttu-id="cd8ee-107">Convertendo um banco de dados para parcialmente independente</span><span class="sxs-lookup"><span data-stu-id="cd8ee-107">Converting a Database to Partially Contained</span></span>](#convert)  
  
-   [<span data-ttu-id="cd8ee-108">Migrando usuários para usuários de bancos de dados independentes</span><span class="sxs-lookup"><span data-stu-id="cd8ee-108">Migrating Users to Contained Database Users</span></span>](#users)  
  
##  <a name="preparing-to-migrate-a-database"></a><a name="prepare"></a> <span data-ttu-id="cd8ee-109">Preparando para migrar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="cd8ee-109">Preparing to Migrate a Database</span></span>  
 <span data-ttu-id="cd8ee-110">Analise os itens a seguir se desejar migrar um banco de dados para o modelo de banco de dados independente parcialmente.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-110">Review the following items when considering migrating a database to the partially contained database model.</span></span>  
  
-   <span data-ttu-id="cd8ee-111">Você deve entender o modelo de banco de dados independente parcialmente.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-111">You should understand the partially contained database model.</span></span> <span data-ttu-id="cd8ee-112">Para obter mais informações, veja [Bancos de dados independentes](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="cd8ee-112">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
-   <span data-ttu-id="cd8ee-113">Você deve entender os riscos que são exclusivos para bancos de dados independentes parcialmente.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-113">You should understand risks that are unique to partially contained databases.</span></span> <span data-ttu-id="cd8ee-114">Para obter mais informações, consulte [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="cd8ee-114">For more information, see [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span></span>  
  
-   <span data-ttu-id="cd8ee-115">Bancos de dados independentes não oferecem suporte à replicação, Change Data Capture ou controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-115">Contained databases do not support replication, change data capture, or change tracking.</span></span> <span data-ttu-id="cd8ee-116">Confirme que o banco de dados não usa estes recursos.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-116">Confirm the database does not use these features.</span></span>  
  
-   <span data-ttu-id="cd8ee-117">Analise a lista de recursos de banco de dados que são modificados para bancos de dados independentes parcialmente.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-117">Review the list of database features that are modified for partially contained databases.</span></span> <span data-ttu-id="cd8ee-118">Para obter mais informações, veja [Recursos modificados &#40;Banco de dados independente&#41;](modified-features-contained-database.md).</span><span class="sxs-lookup"><span data-stu-id="cd8ee-118">For more information, see [Modified Features &#40;Contained Database&#41;](modified-features-contained-database.md).</span></span>  
  
-   <span data-ttu-id="cd8ee-119">Consulte [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) para localizar recursos ou objetos independentes no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-119">Query [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) to find uncontained objects or features in the database.</span></span> <span data-ttu-id="cd8ee-120">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="cd8ee-120">For more information, see.</span></span>  
  
-   <span data-ttu-id="cd8ee-121">Monitore o XEvent **database_uncontained_usage** para ver quando são usados recursos dependentes.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-121">Monitor the **database_uncontained_usage** XEvent to see when uncontained features are used.</span></span>  
  
##  <a name="enable-contained-databases"></a><a name="enable"></a> <span data-ttu-id="cd8ee-122">Habilitar bancos de dados independentes</span><span class="sxs-lookup"><span data-stu-id="cd8ee-122">Enable Contained Databases</span></span>  
 <span data-ttu-id="cd8ee-123">Os bancos de dados independentes devem ser habilitados na instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], antes de os bancos de dados independentes poderem ser criados.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-123">Contained databases must be enabled on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], before contained databases can be created.</span></span>  
  
### <a name="enabling-contained-databases-using-transact-sql"></a><span data-ttu-id="cd8ee-124">Habilitando bancos de dados independentes usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd8ee-124">Enabling Contained Databases Using Transact-SQL</span></span>  
 <span data-ttu-id="cd8ee-125">O exemplo a seguir habilita bancos de dados independentes na instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd8ee-125">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE ;  
GO  
```  
  
#### <a name="enabling-contained-databases-using-management-studio"></a><span data-ttu-id="cd8ee-126">Habilitando bancos de dados independentes usando o Management Studio</span><span class="sxs-lookup"><span data-stu-id="cd8ee-126">Enabling Contained Databases Using Management Studio</span></span>  
 <span data-ttu-id="cd8ee-127">O exemplo a seguir habilita bancos de dados independentes na instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd8ee-127">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="cd8ee-128">No Pesquisador de Objetos, clique com o botão direito do mouse no nome do servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-128">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="cd8ee-129">Na página **Avançado** , na seção **Retenção** , defina a opção **Habilitar Bancos de Dados Independentes** como **True**.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-129">On the **Advanced** page, in the **Containment** section, set the **Enable Contained Databases** option to **True**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="converting-a-database-to-partially-contained"></a><a name="convert"></a> <span data-ttu-id="cd8ee-130">Convertendo um banco de dados para parcialmente independente</span><span class="sxs-lookup"><span data-stu-id="cd8ee-130">Converting a Database to Partially Contained</span></span>  
 <span data-ttu-id="cd8ee-131">Um banco de dados é convertido para um banco de dados independente alterando a opção **CONTAINMENT** .</span><span class="sxs-lookup"><span data-stu-id="cd8ee-131">A database is converted to a contained database by changing the **CONTAINMENT** option.</span></span>  
  
### <a name="converting-a-database-to-partially-contained-using-transact-sql"></a><span data-ttu-id="cd8ee-132">Convertendo um banco de dados para independente parcialmente usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cd8ee-132">Converting a Database to Partially Contained Using Transact-SQL</span></span>  
 <span data-ttu-id="cd8ee-133">O exemplo a seguir converte um banco de dados chamado `Accounting` para um banco de dados independente parcialmente.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-133">The following example converts a database named `Accounting` to a partially contained database.</span></span>  
  
```sql  
USE [master]  
GO  
ALTER DATABASE [Accounting] SET CONTAINMENT = PARTIAL  
GO  
```  
  
### <a name="converting-a-database-to-partially-contained-using-management-studio"></a><span data-ttu-id="cd8ee-134">Convertendo um banco de dados para independente parcialmente usando Management Studio</span><span class="sxs-lookup"><span data-stu-id="cd8ee-134">Converting a Database to Partially contained Using Management Studio</span></span>  
 <span data-ttu-id="cd8ee-135">O exemplo a seguir converte um banco de dados para um banco de dados independente parcialmente.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-135">The following example converts a database to a partially contained database.</span></span>  
  
1.  <span data-ttu-id="cd8ee-136">No Pesquisador de Objetos, expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados que será convertido e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-136">In Object Explorer, expand **Databases**, right-click the database to be converted, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="cd8ee-137">Na página **Opções** , altere a opção **Tipo de retenção** para **Parcial**.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-137">On the **Options** page, change the **Containment type** option to **Partial**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="migrating-users-to-contained-database-users"></a><a name="users"></a> <span data-ttu-id="cd8ee-138">Migrando usuários para usuários de bancos de dados independentes</span><span class="sxs-lookup"><span data-stu-id="cd8ee-138">Migrating Users to Contained Database Users</span></span>  
 <span data-ttu-id="cd8ee-139">O exemplo a seguir migra todos os usuários baseados em logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para usuários de bancos de dados independentes com senhas.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-139">The following example migrates all users that are based on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins to contained database users with passwords.</span></span> <span data-ttu-id="cd8ee-140">O exemplo exclui os logons que não estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-140">The example excludes logins that are not enabled.</span></span> <span data-ttu-id="cd8ee-141">O exemplo deve ser executado no banco de dados independente.</span><span class="sxs-lookup"><span data-stu-id="cd8ee-141">The example must be executed in the contained database.</span></span>  
  
```sql  
DECLARE @username sysname ;  
DECLARE user_cursor CURSOR  
    FOR   
        SELECT dp.name   
        FROM sys.database_principals AS dp  
        JOIN sys.server_principals AS sp   
        ON dp.sid = sp.sid  
        WHERE dp.authentication_type = 1 AND sp.is_disabled = 0;  
OPEN user_cursor  
FETCH NEXT FROM user_cursor INTO @username  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        EXECUTE sp_migrate_user_to_contained   
        @username = @username,  
        @rename = N'keep_name',  
        @disablelogin = N'disable_login';  
    FETCH NEXT FROM user_cursor INTO @username  
    END  
CLOSE user_cursor ;  
DEALLOCATE user_cursor ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd8ee-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cd8ee-142">See Also</span></span>  
 <span data-ttu-id="cd8ee-143">[Bancos de dados independentes](contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="cd8ee-143">[Contained Databases](contained-databases.md) </span></span>  
 <span data-ttu-id="cd8ee-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd8ee-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span></span>  
 [<span data-ttu-id="cd8ee-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd8ee-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql)  
  
  
