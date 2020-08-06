---
title: Criar relações de chaves estrangeiras | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], creating
ms.assetid: 867a54b8-5be4-46e6-9702-49ae6dabf67c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ee0de3311eb6abffcdb71ab725d0650fe96b04c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584084"
---
# <a name="create-foreign-key-relationships"></a><span data-ttu-id="6f35e-102">Criar relações de chaves estrangeiras</span><span class="sxs-lookup"><span data-stu-id="6f35e-102">Create Foreign Key Relationships</span></span>
  <span data-ttu-id="6f35e-103">Este tópico descreve como criar relações de chaves estrangeiras no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f35e-103">This topic describes how to create foreign key relationships in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6f35e-104">Você cria uma relação entre duas tabelas quando deseja associar linhas de uma tabela com linhas de outra.</span><span class="sxs-lookup"><span data-stu-id="6f35e-104">You create a relationship between two tables when you want to associate rows of one table with rows of another.</span></span>  
  
 <span data-ttu-id="6f35e-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="6f35e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6f35e-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6f35e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6f35e-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="6f35e-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6f35e-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="6f35e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6f35e-109">**Para criar relações de chaves estrangeiras usando:**</span><span class="sxs-lookup"><span data-stu-id="6f35e-109">**To Create Foreign Key Relationships by using:**</span></span>  
  
     [<span data-ttu-id="6f35e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6f35e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6f35e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6f35e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6f35e-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6f35e-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6f35e-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="6f35e-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6f35e-114">Uma restrição de chave estrangeira não precisa estar vinculada apenas a uma restrição de chave primária em outra tabela; ela também pode ser definida para referenciar as colunas de uma restrição UNIQUE em outra tabela.</span><span class="sxs-lookup"><span data-stu-id="6f35e-114">A foreign key constraint does not have to be linked only to a primary key constraint in another table; it can also be defined to reference the columns of a UNIQUE constraint in another table.</span></span>  
  
-   <span data-ttu-id="6f35e-115">Quando um valor diferente de NULL é inserido na coluna de uma restrição FOREIGN KEY, o valor deve existir na coluna referenciada; caso contrário, será retornada uma mensagem de erro de violação de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="6f35e-115">When a value other than NULL is entered into the column of a FOREIGN KEY constraint, the value must exist in the referenced column; otherwise, a foreign key violation error message is returned.</span></span> <span data-ttu-id="6f35e-116">Para garantir que todos os valores de uma restrição FOREIGN KEY composta foram verificados, especifique NOT NULL em todas as colunas participantes.</span><span class="sxs-lookup"><span data-stu-id="6f35e-116">To make sure that all values of a composite foreign key constraint are verified, specify NOT NULL on all the participating columns.</span></span>  
  
-   <span data-ttu-id="6f35e-117">As restrições FOREIGN KEY só podem fazer referência a tabelas que estão no mesmo banco de dados e no mesmo servidor.</span><span class="sxs-lookup"><span data-stu-id="6f35e-117">FOREIGN KEY constraints can reference only tables within the same database on the same server.</span></span> <span data-ttu-id="6f35e-118">A integridade referencial em todos os bancos de dados deve ser implementada por gatilhos.</span><span class="sxs-lookup"><span data-stu-id="6f35e-118">Cross-database referential integrity must be implemented through triggers.</span></span> <span data-ttu-id="6f35e-119">Para obter mais informações, veja [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6f35e-119">For more information, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
-   <span data-ttu-id="6f35e-120">As restrições FOREIGN KEY podem fazer referência a outra coluna da mesma tabela.</span><span class="sxs-lookup"><span data-stu-id="6f35e-120">FOREIGN KEY constraints can reference another column in the same table.</span></span> <span data-ttu-id="6f35e-121">Isso se chama autorreferência.</span><span class="sxs-lookup"><span data-stu-id="6f35e-121">This is referred to as a self-reference.</span></span>  
  
-   <span data-ttu-id="6f35e-122">Uma restrição FOREIGN KEY especificada no nível da coluna pode listar apenas uma coluna de referência.</span><span class="sxs-lookup"><span data-stu-id="6f35e-122">A FOREIGN KEY constraint specified at the column level can list only one reference column.</span></span> <span data-ttu-id="6f35e-123">Essa coluna deve ter o mesmo tipo de dados da coluna na qual a restrição foi definida.</span><span class="sxs-lookup"><span data-stu-id="6f35e-123">This column must have the same data type as the column on which the constraint is defined.</span></span>  
  
-   <span data-ttu-id="6f35e-124">Uma restrição FOREIGN KEY especificada no nível da tabela deve ter o mesmo número de colunas de referência da lista de colunas de restrição.</span><span class="sxs-lookup"><span data-stu-id="6f35e-124">A FOREIGN KEY constraint specified at the table level must have the same number of reference columns as the number of columns in the constraint column list.</span></span> <span data-ttu-id="6f35e-125">O tipo de dados de cada coluna de referência também deve ser igual ao da coluna correspondente na lista de colunas.</span><span class="sxs-lookup"><span data-stu-id="6f35e-125">The data type of each reference column must also be the same as the corresponding column in the column list.</span></span>  
  
-   <span data-ttu-id="6f35e-126">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] não tem um limite predefinido quanto ao número de restrições FOREIGN KEY que uma tabela pode conter para referenciar outras tabelas nem quanto ao número de restrições FOREIGN KEY que são propriedade de outras tabelas e fazem referência a uma tabela específica.</span><span class="sxs-lookup"><span data-stu-id="6f35e-126">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not have a predefined limit on either the number of FOREIGN KEY constraints a table can contain that reference other tables, or the number of FOREIGN KEY constraints that are owned by other tables that reference a specific table.</span></span> <span data-ttu-id="6f35e-127">Entretanto, o número real de restrições FOREIGN KEY que pode ser usado é limitado pela configuração do hardware e pelo design do banco de dados e do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6f35e-127">Nevertheless, the actual number of FOREIGN KEY constraints that can be used is limited by the hardware configuration and by the design of the database and application.</span></span> <span data-ttu-id="6f35e-128">Recomendamos que uma tabela não contenha mais de 253 restrições FOREIGN KEY e que ela não seja referenciada por mais de 253 restrições FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="6f35e-128">We recommend that a table contain no more than 253 FOREIGN KEY constraints, and that it be referenced by no more than 253 FOREIGN KEY constraints.</span></span>  
  
-   <span data-ttu-id="6f35e-129">As restrições FOREIGN KEY não são impostas a tabelas temporárias.</span><span class="sxs-lookup"><span data-stu-id="6f35e-129">FOREIGN KEY constraints are not enforced on temporary tables.</span></span>  
  
-   <span data-ttu-id="6f35e-130">Se a chave estrangeira for definida em uma coluna de tipo de dados CLR definido pelo usuário, a implementação do tipo deverá oferecer suporte a uma ordenação binária.</span><span class="sxs-lookup"><span data-stu-id="6f35e-130">If a foreign key is defined on a CLR user-defined type column, the implementation of the type must support binary ordering.</span></span> <span data-ttu-id="6f35e-131">Para obter mais informações, veja [Tipos CLR definidos pelo usuário](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="6f35e-131">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
-   <span data-ttu-id="6f35e-132">A coluna do tipo `varchar(max)` poderá participar de uma restrição FOREIGN KEY somente se a chave primária que ela referencia também estiver definida como tipo `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="6f35e-132">A column of type `varchar(max)` can participate in a FOREIGN KEY constraint only if the primary key it references is also defined as type `varchar(max)`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6f35e-133">Segurança</span><span class="sxs-lookup"><span data-stu-id="6f35e-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6f35e-134">Permissões</span><span class="sxs-lookup"><span data-stu-id="6f35e-134">Permissions</span></span>  
 <span data-ttu-id="6f35e-135">A criação de uma nova tabela com uma chave estrangeira requer a permissão CREATE TABLE no banco de dados e a permissão ALTER no esquema no qual a tabela está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="6f35e-135">Creating a new table with a foreign key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="6f35e-136">Criar uma chave estrangeira em uma tabela existente requer a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="6f35e-136">Creating a foreign key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6f35e-137">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6f35e-137">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-foreign-key-relationship-in-table-designer"></a><span data-ttu-id="6f35e-138">Para criar uma relação de chave estrangeira no Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="6f35e-138">To create a foreign key relationship in Table Designer</span></span>  
  
1.  <span data-ttu-id="6f35e-139">No Pesquisador de Objetos, clique com o botão direito do mouse na tabela que estará ao lado da chave estrangeira da relação e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="6f35e-139">In Object Explorer, right-click the table that will be on the foreign-key side of the relationship and click **Design**.</span></span>  
  
     <span data-ttu-id="6f35e-140">A tabela é aberta no **Designer de Tabela**.</span><span class="sxs-lookup"><span data-stu-id="6f35e-140">The table opens in **Table Designer**.</span></span>  
  
2.  <span data-ttu-id="6f35e-141">No menu **Designer de Tabela** , clique em **Relações**.</span><span class="sxs-lookup"><span data-stu-id="6f35e-141">From the **Table Designer** menu, click **Relationships**.</span></span>  
  
3.  <span data-ttu-id="6f35e-142">Na caixa de diálogo **Relações de Chave Estrangeira** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6f35e-142">In the **Foreign-key Relationships** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="6f35e-143">A relação aparece na lista **Relação Selecionada** com um nome fornecido pelo sistema no formato FK_\<*tablename*>_\<*tablename*>, em que *tablename* é o nome da tabela de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="6f35e-143">The relationship appears in the **Selected Relationship** list with a system-provided name in the format FK_\<*tablename*>_\<*tablename*>, where *tablename* is the name of the foreign key table.</span></span>  
  
4.  <span data-ttu-id="6f35e-144">Clique na relação na lista **Relação Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="6f35e-144">Click the relationship in the **Selected Relationship** list.</span></span>  
  
5.  <span data-ttu-id="6f35e-145">Clique em **Especificação de Tabelas e Colunas** na grade à direita e clique nas reticências ( **...** ) à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6f35e-145">Click **Tables and Columns Specification** in the grid to the right and click the ellipses (**...**) to the right of the property.</span></span>  
  
6.  <span data-ttu-id="6f35e-146">Na caixa de diálogo **Tabelas e Colunas** , na lista suspensa **Chave Primária** , escolha a tabela que estará ao lado da chave primária da relação.</span><span class="sxs-lookup"><span data-stu-id="6f35e-146">In the **Tables and Columns** dialog box, in the **Primary Key** drop-down list, choose the table that will be on the primary-key side of the relationship.</span></span>  
  
7.  <span data-ttu-id="6f35e-147">Na grade inferior, escolha as colunas que contribuem para chave primária da tabela.</span><span class="sxs-lookup"><span data-stu-id="6f35e-147">In the grid beneath, choose the columns contributing to the table's primary key.</span></span> <span data-ttu-id="6f35e-148">Na célula da grade adjacente à esquerda de cada coluna, escolha a coluna da chave estrangeira correspondente da tabela da chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="6f35e-148">In the adjacent grid cell to the left of each column, choose the corresponding foreign-key column of the foreign-key table.</span></span>  
  
     <span data-ttu-id="6f35e-149">O**Designer de Tabela** sugere um nome para a relação.</span><span class="sxs-lookup"><span data-stu-id="6f35e-149">**Table Designer** suggests a name for the relationship.</span></span> <span data-ttu-id="6f35e-150">Para mudar esse nome, edite o conteúdo da caixa de texto **Nome da Relação** .</span><span class="sxs-lookup"><span data-stu-id="6f35e-150">To change this name, edit the contents of the **Relationship Name** text box.</span></span>  
  
8.  <span data-ttu-id="6f35e-151">Escolha **OK** para criar a relação.</span><span class="sxs-lookup"><span data-stu-id="6f35e-151">Choose **OK** to create the relationship.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6f35e-152">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6f35e-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-foreign-key-in-a-new-table"></a><span data-ttu-id="6f35e-153">Para criar uma chave estrangeira em uma nova tabela</span><span class="sxs-lookup"><span data-stu-id="6f35e-153">To create a foreign key in a new table</span></span>  
  
1.  <span data-ttu-id="6f35e-154">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f35e-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6f35e-155">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6f35e-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6f35e-156">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6f35e-156">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6f35e-157">O exemplo cria uma tabela e define uma restrição de chave estrangeira na coluna `TempID` que referencia a coluna `SalesReasonID` na tabela `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="6f35e-157">The example creates a table and defines a foreign key constraint on the column `TempID` that references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span> <span data-ttu-id="6f35e-158">As cláusulas ON DELETE CASCADE e ON UPDATE CASCADE são usadas para assegurar a propagação das alterações feitas na tabela `Sales.SalesReason` automaticamente para a tabela `Sales.TempSalesReason` .</span><span class="sxs-lookup"><span data-stu-id="6f35e-158">The ON DELETE CASCADE and ON UPDATE CASCADE clauses are used to ensure that changes made to `Sales.SalesReason` table are automatically propagated to the `Sales.TempSalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Sales.TempSalesReason (TempID int NOT NULL, Name nvarchar(50),   
    CONSTRAINT PK_TempSales PRIMARY KEY NONCLUSTERED (TempID),   
    CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    );GO  
  
    ```  
  
#### <a name="to-create-a-foreign-key-in-an-existing-table"></a><span data-ttu-id="6f35e-159">Para criar uma chave estrangeira em uma tabela existente</span><span class="sxs-lookup"><span data-stu-id="6f35e-159">To create a foreign key in an existing table</span></span>  
  
1.  <span data-ttu-id="6f35e-160">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f35e-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6f35e-161">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6f35e-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6f35e-162">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6f35e-162">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6f35e-163">O exemplo cria uma chave estrangeira na coluna `TempID` e referencia a coluna `SalesReasonID` na tabela `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="6f35e-163">The example creates a foreign key on the column `TempID` and references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Sales.TempSalesReason   
    ADD CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    ;  
    GO  
  
    ```  
  
     <span data-ttu-id="6f35e-164">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) e [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6f35e-164">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
  
