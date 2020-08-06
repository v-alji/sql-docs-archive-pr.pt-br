---
title: Criar restrições exclusivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- UNIQUE constraints [SQL Server], creating
- constraints [SQL Server], creating
- constraints [SQL Server], unique
ms.assetid: a86f9d6f-f242-43be-b65d-b3435b71b62a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 252de63f965f98734a6d62d94bfff9dc5774cab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684143"
---
# <a name="create-unique-constraints"></a><span data-ttu-id="00c1e-102">Criar restrições exclusivas</span><span class="sxs-lookup"><span data-stu-id="00c1e-102">Create Unique Constraints</span></span>
  <span data-ttu-id="00c1e-103">Você pode criar uma restrição exclusiva no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] para assegurar que nenhum valor duplicado seja digitado em colunas específicas que não integram uma chave primária.</span><span class="sxs-lookup"><span data-stu-id="00c1e-103">You can create a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] to ensure no duplicate values are entered in specific columns that do not participate in a primary key.</span></span> <span data-ttu-id="00c1e-104">Criar uma restrição exclusiva cria automaticamente um índice exclusivo correspondente.</span><span class="sxs-lookup"><span data-stu-id="00c1e-104">Creating a unique constraint automatically creates a corresponding unique index.</span></span>  
  
 <span data-ttu-id="00c1e-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="00c1e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="00c1e-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="00c1e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="00c1e-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="00c1e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="00c1e-108">**Para criar restrição exclusiva usando:**</span><span class="sxs-lookup"><span data-stu-id="00c1e-108">**To create a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="00c1e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00c1e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="00c1e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="00c1e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="00c1e-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="00c1e-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="00c1e-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="00c1e-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="00c1e-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="00c1e-113">Permissions</span></span>  
 <span data-ttu-id="00c1e-114">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="00c1e-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="00c1e-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00c1e-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="00c1e-116">Para criar restrição exclusiva</span><span class="sxs-lookup"><span data-stu-id="00c1e-116">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="00c1e-117">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela à qual você deseja adicionar uma restrição exclusiva e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-117">In **Object Explorer**, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="00c1e-118">No menu **Designer de tabela** , clique em **índices/chaves**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-118">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="00c1e-119">Na caixa de diálogo **Índices/Chaves** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-119">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="00c1e-120">Na grade, em **Geral**, clique em **Tipo** e selecione **Chave Exclusiva** na caixa de listagem suspensa à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="00c1e-120">In the grid under **General**, click **Type** and choose **Unique Key** from the drop-down list box to the right of the property.</span></span>  
  
5.  <span data-ttu-id="00c1e-121">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="00c1e-121">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="00c1e-122">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="00c1e-122">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="00c1e-123">Para criar restrição exclusiva</span><span class="sxs-lookup"><span data-stu-id="00c1e-123">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="00c1e-124">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00c1e-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="00c1e-125">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="00c1e-126">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-126">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="00c1e-127">O exemplo cria a tabela `TransactionHistoryArchive4` e cria uma restrição exclusiva na coluna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="00c1e-127">The example creates the table `TransactionHistoryArchive4` and creates a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive4  
     (  
       TransactionID int NOT NULL,   
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)   
    );   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-on-an-existing-table"></a><span data-ttu-id="00c1e-128">Para criar uma restrição exclusiva em uma tabela existente</span><span class="sxs-lookup"><span data-stu-id="00c1e-128">To create a unique constraint on an existing table</span></span>  
  
1.  <span data-ttu-id="00c1e-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00c1e-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="00c1e-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="00c1e-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-131">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="00c1e-132">O exemplo cria uma restrição exclusiva nas colunas `PasswordHash` e `PasswordSalt` na tabela `Person.Password`.</span><span class="sxs-lookup"><span data-stu-id="00c1e-132">The example creates a unique constraint on the columns `PasswordHash` and `PasswordSalt` in the table `Person.Password`.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    ALTER TABLE Person.Password   
    ADD CONSTRAINT AK_Password UNIQUE (PasswordHash, PasswordSalt);   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-in-an-new-table"></a><span data-ttu-id="00c1e-133">Para criar uma restrição exclusiva em uma nova tabela</span><span class="sxs-lookup"><span data-stu-id="00c1e-133">To create a unique constraint in an new table</span></span>  
  
1.  <span data-ttu-id="00c1e-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00c1e-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="00c1e-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="00c1e-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="00c1e-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="00c1e-137">O exemplo cria uma tabela e define uma restrição exclusiva na coluna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="00c1e-137">The example creates a table and defines a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive2  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="00c1e-138">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) e [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00c1e-138">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
