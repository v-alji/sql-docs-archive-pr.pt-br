---
title: Definir ou alterar a ordenação de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], database
- database collations [SQL Server]
ms.assetid: 1379605c-1242-4ac8-ab1b-e2a2b5b1f895
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d7f7c3e3ddba7ba0ea9701993dbe0fad3a8d975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583644"
---
# <a name="set-or-change-the-database-collation"></a><span data-ttu-id="9363f-102">Definir ou alterar a ordenação de banco de dados</span><span class="sxs-lookup"><span data-stu-id="9363f-102">Set or Change the Database Collation</span></span>
  <span data-ttu-id="9363f-103">Este tópico descreve como definir e alterar a ordenação de banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9363f-103">This topic describes how set and change the database collation in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9363f-104">Se nenhuma ordenação for especificada, será usada a ordenação do servidor.</span><span class="sxs-lookup"><span data-stu-id="9363f-104">If no collation is specified, the server collation is used.</span></span>  
  
 <span data-ttu-id="9363f-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="9363f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9363f-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="9363f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9363f-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9363f-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9363f-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="9363f-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="9363f-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="9363f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9363f-110">**Para definir ou alterar a ordenação de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="9363f-110">**To set or change the database collation, using:**</span></span>  
  
     [<span data-ttu-id="9363f-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9363f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9363f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9363f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9363f-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9363f-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9363f-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9363f-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9363f-115">Ordenações somente Unicode do Windows podem ser usadas somente com a cláusula COLLATE para aplicar ordenações aos tipos de dados `nchar`, `nvarchar` e `ntext` em dados nos níveis de coluna e de expressão.</span><span class="sxs-lookup"><span data-stu-id="9363f-115">Windows Unicode-only collations can only be used with the COLLATE clause to apply collations to the `nchar`, `nvarchar`, and `ntext` data types on column level and expression-level data.</span></span> <span data-ttu-id="9363f-116">Não é possível usá-los com a cláusula COLLATE para alterar a ordenação de uma instância de banco de dados ou de servidor.</span><span class="sxs-lookup"><span data-stu-id="9363f-116">They cannot be used with the COLLATE clause to change the collation of a database or server instance.</span></span>  
  
-   <span data-ttu-id="9363f-117">Se a ordenação especificada ou a ordenação usada pelo objeto referenciado usar uma página de código sem suporte no Windows, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] exibirá um erro.</span><span class="sxs-lookup"><span data-stu-id="9363f-117">If the specified collation or the collation used by the referenced object uses a code page that is not supported by Windows, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] displays an error.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9363f-118">Recomendações</span><span class="sxs-lookup"><span data-stu-id="9363f-118">Recommendations</span></span>  
  
-   <span data-ttu-id="9363f-119">Você pode encontrar os nomes de ordenação com suporte no [Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) e [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) ou pode usar a função do sistema [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9363f-119">You can find the supported collation names in [Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) and [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql); or you can use the [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) system function.</span></span>  
  
-   <span data-ttu-id="9363f-120">Ao alterar a ordenação de banco de dados, você altera o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9363f-120">When you change the database collation, you change the following:</span></span>  
  
    -   <span data-ttu-id="9363f-121">Qualquer coluna `char`, `varchar`, `text`, `nchar`, `nvarchar` ou `ntext` nas tabelas do sistema são alteradas para a nova ordenação.</span><span class="sxs-lookup"><span data-stu-id="9363f-121">Any `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` columns in system tables are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="9363f-122">Todos os parâmetros `char`, `varchar`, `text`, `nchar`, `nvarchar` ou `ntext` e valores de retorno escalar para procedimentos armazenados e funções definidas pelo usuário existentes são alterados para a nova ordenação.</span><span class="sxs-lookup"><span data-stu-id="9363f-122">All existing `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` parameters and scalar return values for stored procedures and user-defined functions are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="9363f-123">Os tipos de dados do sistema `char`, `varchar`, `text`, `nchar`, `nvarchar` ou `ntext` e todos os tipos de dados definidos pelo usuário com base nesses tipos de dados do sistema são alterados para a nova ordenação padrão.</span><span class="sxs-lookup"><span data-stu-id="9363f-123">The `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` system data types, and all user-defined data types based on these system data types, are changed to the new default collation.</span></span>  
  
-   <span data-ttu-id="9363f-124">Você pode alterar a ordenação de qualquer novo objeto que seja criado em um banco de dados de usuário, usando a cláusula COLLATE da instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9363f-124">You can change the collation of any new objects that are created in a user database by using the COLLATE clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="9363f-125">Essa instrução não altera a ordenação das colunas em nenhuma tabela existente definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9363f-125">This statement does not change the collation of the columns in any existing user-defined tables.</span></span> <span data-ttu-id="9363f-126">Essas podem ser alteradas usando-se a cláusula COLLATE de [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9363f-126">These can be changed by using the COLLATE clause of [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9363f-127">Segurança</span><span class="sxs-lookup"><span data-stu-id="9363f-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9363f-128">Permissões</span><span class="sxs-lookup"><span data-stu-id="9363f-128">Permissions</span></span>  
 <span data-ttu-id="9363f-129">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="9363f-129">CREATE DATABASE</span></span>  
 <span data-ttu-id="9363f-130">Requer a permissão CREATE DATABASE no banco de dados **mestre** ou requer a permissão CREATE ANY DATABASE ou ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="9363f-130">Requires CREATE DATABASE permission in the **master** database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="9363f-131">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="9363f-131">ALTER DATABASE</span></span>  
 <span data-ttu-id="9363f-132">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9363f-132">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9363f-133">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9363f-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-or-change-the-database-collation"></a><span data-ttu-id="9363f-134">Para definir ou alterar a ordenação de banco de dados</span><span class="sxs-lookup"><span data-stu-id="9363f-134">To set or change the database collation</span></span>  
  
1.  <span data-ttu-id="9363f-135">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expanda essa instância e expanda **Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="9363f-135">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="9363f-136">Se você estiver criando um novo banco de dados, clique com o botão direito do mouse em **Bancos de Dados** e clique em **Novo Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="9363f-136">If you are creating a new database, right-click **Databases** and then click **New Database**.</span></span> <span data-ttu-id="9363f-137">Se você não desejar a ordenação padrão, clique na página **Opções** e selecione uma ordenação na lista suspensa **Ordenação**.</span><span class="sxs-lookup"><span data-stu-id="9363f-137">If you do not want the default collation, click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
     <span data-ttu-id="9363f-138">De maneira alternativa, se o banco de dados já existir, clique com o botão direito do mouse no banco de dados desejado e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9363f-138">Alternatively, if the database already exists, right-click the database that you want and click **Properties**.</span></span> <span data-ttu-id="9363f-139">Clique na página **Opções** e selecione uma ordenação na lista suspensa **Ordenação**.</span><span class="sxs-lookup"><span data-stu-id="9363f-139">Click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
3.  <span data-ttu-id="9363f-140">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9363f-140">After you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9363f-141">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9363f-141">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-database-collation"></a><span data-ttu-id="9363f-142">Para definir a ordenação de banco de dados</span><span class="sxs-lookup"><span data-stu-id="9363f-142">To set the database collation</span></span>  
  
1.  <span data-ttu-id="9363f-143">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9363f-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9363f-144">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="9363f-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9363f-145">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9363f-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9363f-146">Este exemplo mostra como usar a cláusula [COLLATE](/sql/t-sql/statements/collations) para especificar um nome de ordenação.</span><span class="sxs-lookup"><span data-stu-id="9363f-146">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause to specify a collation name.</span></span> <span data-ttu-id="9363f-147">O exemplo cria o banco de dados `MyOptionsTest` que usa a ordenação `Latin1_General_100_CS_AS_SC`.</span><span class="sxs-lookup"><span data-stu-id="9363f-147">The example creates the database `MyOptionsTest` that uses the `Latin1_General_100_CS_AS_SC` collation.</span></span> <span data-ttu-id="9363f-148">Depois de criar o banco de dados, execute a instrução `SELECT` para verificar a configuração.</span><span class="sxs-lookup"><span data-stu-id="9363f-148">After you create the database, execute the `SELECT` statement to verify the setting.</span></span>  
  
```sql  
USE master;  
GO  
IF DB_ID (N'MyOptionsTest') IS NOT NULL  
DROP DATABASE MyOptionsTest;  
GO  
CREATE DATABASE MyOptionsTest  
COLLATE Latin1_General_100_CS_AS_SC;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
#### <a name="to-change-the-database-collation"></a><span data-ttu-id="9363f-149">Para alterar a ordenação de banco de dados</span><span class="sxs-lookup"><span data-stu-id="9363f-149">To change the database collation</span></span>  
  
1.  <span data-ttu-id="9363f-150">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9363f-150">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9363f-151">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="9363f-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9363f-152">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9363f-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9363f-153">Este exemplo mostra como usar a cláusula [COLLATE](/sql/t-sql/statements/collations) em uma instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) para alterar o nome da ordenação.</span><span class="sxs-lookup"><span data-stu-id="9363f-153">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause in an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to change the collation name.</span></span> <span data-ttu-id="9363f-154">Execute a instrução `SELECT` para verificar a alteração.</span><span class="sxs-lookup"><span data-stu-id="9363f-154">Execute the `SELECT` statement to verify the change.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE MyOptionsTest  
COLLATE French_CI_AS ;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="9363f-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9363f-155">See Also</span></span>  
 <span data-ttu-id="9363f-156">[Suporte a ordenações e a Unicode](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="9363f-156">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="9363f-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9363f-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="9363f-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9363f-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="9363f-159">[Nome de ordenação do SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9363f-159">[SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="9363f-160">[Nome de ordenação do Windows &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9363f-160">[Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="9363f-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span><span class="sxs-lookup"><span data-stu-id="9363f-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span></span>  
 <span data-ttu-id="9363f-162">[Precedência de ordenação &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9363f-162">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 <span data-ttu-id="9363f-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9363f-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="9363f-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9363f-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="9363f-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9363f-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="9363f-166">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9363f-166">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
