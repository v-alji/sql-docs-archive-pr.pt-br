---
title: Criar chaves primárias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- primary keys [SQL Server], creating
ms.assetid: 85c623ca-4656-4d70-a9db-ee4d897cd214
author: stevestein
ms.author: sstein
ms.openlocfilehash: c515ef8f978b41225ff45e87646b0aa7a9706a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584085"
---
# <a name="create-primary-keys"></a><span data-ttu-id="274fc-102">Criar chaves primárias</span><span class="sxs-lookup"><span data-stu-id="274fc-102">Create Primary Keys</span></span>
  <span data-ttu-id="274fc-103">Você pode definir uma chave primária no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="274fc-103">You can define a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="274fc-104">Criar uma chave primária cria automaticamente um índice correspondente exclusivo, clusterizado ou não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="274fc-104">Creating a primary key automatically creates a corresponding unique, clustered or nonclustered index.</span></span>  
  
 <span data-ttu-id="274fc-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="274fc-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="274fc-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="274fc-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="274fc-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="274fc-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="274fc-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="274fc-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="274fc-109">**Para criar uma chave primária usando:**</span><span class="sxs-lookup"><span data-stu-id="274fc-109">**To create a primary key, using:**</span></span>  
  
     [<span data-ttu-id="274fc-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="274fc-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="274fc-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="274fc-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="274fc-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="274fc-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="274fc-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="274fc-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="274fc-114">Uma tabela pode conter apenas uma restrição PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="274fc-114">A table can contain only one PRIMARY KEY constraint.</span></span>  
  
-   <span data-ttu-id="274fc-115">Todas as colunas definidas em uma restrição PRIMARY KEY devem ser definidas como NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="274fc-115">All columns defined within a PRIMARY KEY constraint must be defined as NOT NULL.</span></span> <span data-ttu-id="274fc-116">Se a nulidade não for especificada, todas as colunas participantes de uma restrição FOREIGN KEY devem ter sua nulidade definida como NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="274fc-116">If nullability is not specified, all columns participating in a PRIMARY KEY constraint have their nullability set to NOT NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="274fc-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="274fc-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="274fc-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="274fc-118">Permissions</span></span>  
 <span data-ttu-id="274fc-119">A criação de uma nova tabela com uma chave primária requer a permissão CREATE TABLE no banco de dados e a permissão ALTER no esquema no qual a tabela está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="274fc-119">Creating a new table with a primary key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="274fc-120">Criar uma chave primária em uma tabela existente requer a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="274fc-120">Creating a primary key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="274fc-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="274fc-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-primary-key"></a><span data-ttu-id="274fc-122">Para criar uma chave primária</span><span class="sxs-lookup"><span data-stu-id="274fc-122">To create a primary key</span></span>  
  
1.  <span data-ttu-id="274fc-123">No Pesquisador de objetos, clique com o botão direito do mouse na tabela à qual você deseja adicionar uma restrição exclusiva e clique em **design**.</span><span class="sxs-lookup"><span data-stu-id="274fc-123">In Object Explorer, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="274fc-124">No **Designer de Tabela**, clique no seletor de linha para a coluna de banco de dados que você deseja definir como chave primária.</span><span class="sxs-lookup"><span data-stu-id="274fc-124">In **Table Designer**, click the row selector for the database column you want to define as the primary key.</span></span> <span data-ttu-id="274fc-125">Se desejar selecionar colunas múltiplas, digite a tecla CTRL enquanto você clica nos seletores de linha para as outras colunas.</span><span class="sxs-lookup"><span data-stu-id="274fc-125">If you want to select multiple columns, hold down the CTRL key while you click the row selectors for the other columns.</span></span>  
  
3.  <span data-ttu-id="274fc-126">Clique com o botão direito do mouse no seletor de linha da coluna e selecione **Definir Chave Primária**.</span><span class="sxs-lookup"><span data-stu-id="274fc-126">Right-click the row selector for the column and select **Set Primary Key**.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="274fc-127">Se você quiser redefinir a chave primária, qualquer relação com a chave primária existente deve ser excluída antes que a nova chave primária seja criada.</span><span class="sxs-lookup"><span data-stu-id="274fc-127">If you want to redefine the primary key, any relationships to the existing primary key must be deleted before the new primary key can be created.</span></span> <span data-ttu-id="274fc-128">Uma mensagem avisará que as relações existentes serão excluídas automaticamente como parte desse processo.</span><span class="sxs-lookup"><span data-stu-id="274fc-128">A message will warn you that existing relationships will be automatically deleted as part of this process.</span></span>  
  
 <span data-ttu-id="274fc-129">Uma coluna de chave primária é identificada por um símbolo de chave primária em seu seletor de linha.</span><span class="sxs-lookup"><span data-stu-id="274fc-129">A primary key column is identified by a primary key symbol in its row selector.</span></span>  
  
 <span data-ttu-id="274fc-130">Se uma chave primária consistir em mais de uma coluna, serão permitidos valores duplicados em uma coluna, mas cada combinação de valores de todas as colunas na chave primária deve ser única.</span><span class="sxs-lookup"><span data-stu-id="274fc-130">If a primary key consists of more than one column, duplicate values are allowed in one column, but each combination of values from all the columns in the primary key must be unique.</span></span>  
  
 <span data-ttu-id="274fc-131">Se você definir uma chave combinada, a ordem das colunas na chave primária corresponderá à ordem das colunas, como é mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="274fc-131">If you define a compound key, the order of columns in the primary key matches the order of columns as shown in the table.</span></span> <span data-ttu-id="274fc-132">Entretanto, você poderá alterar a ordem de colunas depois que a chave primária for criada.</span><span class="sxs-lookup"><span data-stu-id="274fc-132">However, you can change the order of columns after the primary key is created.</span></span> <span data-ttu-id="274fc-133">Para obter mais informações, veja [Modificar chaves primárias](modify-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="274fc-133">For more information, see [Modify Primary Keys](modify-primary-keys.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="274fc-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="274fc-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-primary-key-in-an-existing-table"></a><span data-ttu-id="274fc-135">Para criar uma chave primária em uma tabela existente</span><span class="sxs-lookup"><span data-stu-id="274fc-135">To create a primary key in an existing table</span></span>  
  
1.  <span data-ttu-id="274fc-136">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="274fc-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="274fc-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="274fc-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="274fc-138">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="274fc-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="274fc-139">O exemplo cria uma chave primária no coluna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="274fc-139">The example creates a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Production.TransactionHistoryArchive   
    ADD CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID);  
    GO  
  
    ```  
  
#### <a name="to-create-a-primary-key-in-a-new-table"></a><span data-ttu-id="274fc-140">Para criar uma chave primária em uma nova tabela</span><span class="sxs-lookup"><span data-stu-id="274fc-140">To create a primary key in a new table</span></span>  
  
1.  <span data-ttu-id="274fc-141">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="274fc-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="274fc-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="274fc-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="274fc-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="274fc-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="274fc-144">O exemplo cria uma tabela e define uma chave primária na coluna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="274fc-144">The example creates a table and defines a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive1  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="274fc-145">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) e [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="274fc-145">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
