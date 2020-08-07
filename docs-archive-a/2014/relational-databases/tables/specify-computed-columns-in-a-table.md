---
title: Especificar colunas computadas em uma tabela | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, define
ms.assetid: 731a4576-09c1-47f0-a8f6-edd0b55679f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22e4df8d67b61e50383ffd8e33f982990ff3f2ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581702"
---
# <a name="specify-computed-columns-in-a-table"></a><span data-ttu-id="cec7d-102">Especificar colunas computadas em uma tabela</span><span class="sxs-lookup"><span data-stu-id="cec7d-102">Specify Computed Columns in a Table</span></span>
  <span data-ttu-id="cec7d-103">Uma coluna computada é uma coluna virtual que não está fisicamente armazenada na tabela, a menos que a coluna esteja marcada como PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="cec7d-103">A computed column is a virtual column that is not physically stored in the table, unless the column is marked PERSISTED.</span></span> <span data-ttu-id="cec7d-104">Uma expressão de coluna computada pode usar dados de outras colunas para calcular um valor para a coluna à qual pertence.</span><span class="sxs-lookup"><span data-stu-id="cec7d-104">A computed column expression can use data from other columns to calculate a value for the column to which it belongs.</span></span> <span data-ttu-id="cec7d-105">Você pode especificar uma expressão para uma coluna computada no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec7d-105">You can specify an expression for a computed column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="cec7d-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="cec7d-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cec7d-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="cec7d-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cec7d-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="cec7d-108">Limitations and Restrictions</span></span>](#Limitations)  
  
     [<span data-ttu-id="cec7d-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="cec7d-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cec7d-110">**Para especificar uma coluna computada usando:**</span><span class="sxs-lookup"><span data-stu-id="cec7d-110">**To specify a computed column, using:**</span></span>  
  
     [<span data-ttu-id="cec7d-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cec7d-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cec7d-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cec7d-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cec7d-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cec7d-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="cec7d-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="cec7d-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cec7d-115">Uma coluna computada não pode ser usada como uma definição de restrição DEFAULT ou FOREIGN KEY ou com uma definição de restrição NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="cec7d-115">A computed column cannot be used as a DEFAULT or FOREIGN KEY constraint definition or with a NOT NULL constraint definition.</span></span> <span data-ttu-id="cec7d-116">Entretanto, se o valor da coluna computada for definido por uma expressão determinística e o tipo de dados do resultado for permitido em colunas de índice, uma coluna computada poderá ser usada como uma coluna de chave em um índice ou como parte de qualquer restrição PRIMARY KEY ou UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="cec7d-116">However, if the computed column value is defined by a deterministic expression and the data type of the result is allowed in index columns, a computed column can be used as a key column in an index or as part of any PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="cec7d-117">Por exemplo, se a tabela tiver colunas de inteiros a e b, a coluna computada a + b poderá ser indexada, mas a coluna computada a +DATEPART(dd, GETDATE()) não poderá ser indexada, pois o valor pode ser alterado em invocações subsequentes.</span><span class="sxs-lookup"><span data-stu-id="cec7d-117">For example, if the table has integer columns a and b, the computed column a + b may be indexed, but computed column a + DATEPART(dd, GETDATE()) cannot be indexed, because the value might change in subsequent invocations.</span></span>  
  
-   <span data-ttu-id="cec7d-118">Uma coluna computada não pode ser o destino de uma instrução INSERT ou UPDATE.</span><span class="sxs-lookup"><span data-stu-id="cec7d-118">A computed column cannot be the target of an INSERT or UPDATE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cec7d-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="cec7d-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cec7d-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="cec7d-120">Permissions</span></span>  
 <span data-ttu-id="cec7d-121">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="cec7d-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cec7d-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cec7d-122">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-add-a-new-computed-column"></a><a name="NewColumn"></a> <span data-ttu-id="cec7d-123">Para adicionar uma nova coluna computada</span><span class="sxs-lookup"><span data-stu-id="cec7d-123">To add a new computed column</span></span>  
  
1.  <span data-ttu-id="cec7d-124">No **Pesquisador de Objetos**, expanda a tabela na qual você deseja adicionar a nova coluna computada.</span><span class="sxs-lookup"><span data-stu-id="cec7d-124">In **Object Explorer**, expand the table for which you want to add the new computed column.</span></span> <span data-ttu-id="cec7d-125">Clique com o botão direito do mouse em **Colunas** e selecione **Nova Coluna**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-125">Right-click **Columns** and select **New Column**.</span></span>  
  
2.  <span data-ttu-id="cec7d-126">Digite o nome da coluna e aceite o tipo de dados padrão (`nchar`(10)).</span><span class="sxs-lookup"><span data-stu-id="cec7d-126">Enter the column name and accept the default data type (`nchar`(10)).</span></span> <span data-ttu-id="cec7d-127">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] determina o tipo de dados da coluna computada, aplicando as regras de precedência de tipos de dados às expressões especificadas na fórmula.</span><span class="sxs-lookup"><span data-stu-id="cec7d-127">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines the data type of the computed column by applying the rules of data type precedence to the expressions specified in the formula.</span></span> <span data-ttu-id="cec7d-128">Por exemplo, se a fórmula referenciar uma coluna de tipo `money` e uma coluna de tipo `int`, a coluna computada será do tipo `money` porque esse tipo de dados tem maior precedência.</span><span class="sxs-lookup"><span data-stu-id="cec7d-128">For example, if the formula references a column of type `money` and a column of type `int`, the computed column will be of type `money` because that data type has the higher precedence.</span></span> <span data-ttu-id="cec7d-129">Para obter mais informações, veja [Precedência de tipo de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cec7d-129">For more information, see [Data Type Precedence &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span></span>  
  
3.  <span data-ttu-id="cec7d-130">Na guia **Propriedades da Coluna** , expanda a propriedade **Especificação de Coluna Computada** .</span><span class="sxs-lookup"><span data-stu-id="cec7d-130">In the **Column Properties** tab, expand the **Computed Column Specification** property.</span></span>  
  
4.  <span data-ttu-id="cec7d-131">Na propriedade filho **(Fórmula)** , insira a expressão para essa coluna na célula de grade à direita.</span><span class="sxs-lookup"><span data-stu-id="cec7d-131">In the **(Formula)** child property, enter the expression for this column in the grid cell to the right.</span></span> <span data-ttu-id="cec7d-132">Por exemplo, em uma coluna `SalesTotal` , a fórmula que você insere pode ser `SubTotal+TaxAmt+Freight`, que associa o valor nessas colunas a cada linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="cec7d-132">For example, in a `SalesTotal` column, the formula you enter might be `SubTotal+TaxAmt+Freight`, which adds the value in these columns for each row in the table.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="cec7d-133">Quando uma fórmula combina duas expressões de tipos de dados diferentes, as regras de precedência do tipo de dados especificam que o tipo de dados com menor precedência é convertido no tipo de dados de maior precedência.</span><span class="sxs-lookup"><span data-stu-id="cec7d-133">When a formula combines two expressions of different data types, the rules for data type precedence specify that the data type with the lower precedence is converted to the data type with the higher precedence.</span></span> <span data-ttu-id="cec7d-134">Se a conversão não for uma conversão implícita com suporte, o erro "`Error validating the formula for column column_name.`" será retornado.</span><span class="sxs-lookup"><span data-stu-id="cec7d-134">If the conversion is not a supported implicit conversion, the error "`Error validating the formula for column column_name.`" is returned.</span></span> <span data-ttu-id="cec7d-135">Use a função CAST ou CONVERT para resolver o conflito de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="cec7d-135">Use the CAST or CONVERT function to resolve the data type conflict.</span></span> <span data-ttu-id="cec7d-136">Por exemplo, se uma coluna de tipo `nvarchar` é combinada com uma coluna de tipo `int`, o tipo inteiro deve ser convertido em `nvarchar`, conforme mostrado nesta fórmula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span><span class="sxs-lookup"><span data-stu-id="cec7d-136">For example, if a column of type `nvarchar` is combined with a column of type `int`, the integer type must be converted to `nvarchar` as shown in this formula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span></span> <span data-ttu-id="cec7d-137">Para obter mais informações, veja [CAST e CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cec7d-137">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
5.  <span data-ttu-id="cec7d-138">Indique se os dados são persistentes escolhendo **Sim** ou **Não** na lista suspensa da propriedade filho **Is Persisted** .</span><span class="sxs-lookup"><span data-stu-id="cec7d-138">Indicate whether the data is persisted by choosing **Yes** or **No** from the drop-down for the **Is Persisted** child property.</span></span>  
  
6.  <span data-ttu-id="cec7d-139">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="cec7d-139">On the **File** menu, click **Save**_table name_.</span></span>  
  
#### <a name="to-add-a-computed-column-definition-to-an-existing-column"></a><span data-ttu-id="cec7d-140">Para adicionar uma definição de coluna computada em uma coluna existente</span><span class="sxs-lookup"><span data-stu-id="cec7d-140">To add a computed column definition to an existing column</span></span>  
  
1.  <span data-ttu-id="cec7d-141">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela com a coluna que você deseja alterar e expanda a pasta **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="cec7d-141">In **Object Explorer**, right-click the table with the column for which you want to change and expand the **Columns** folder.</span></span>  
  
2.  <span data-ttu-id="cec7d-142">Clique com o botão direito do mouse na coluna para a qual você deseja especificar uma fórmula de coluna computada e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-142">Right-click the column for which you want to specify a computed column formula and click **Delete**.</span></span> <span data-ttu-id="cec7d-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="cec7d-144">Adicione uma nova coluna e especifique a fórmula de coluna computada seguindo o procedimento anterior para adicionar uma nova coluna computada.</span><span class="sxs-lookup"><span data-stu-id="cec7d-144">Add a new column and specify the computed column formula by following the previous procedure to add a new computed column.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cec7d-145">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cec7d-145">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-computed-column-when-creating-a-table"></a><span data-ttu-id="cec7d-146">Para adicionar uma coluna computada ao criar uma tabela</span><span class="sxs-lookup"><span data-stu-id="cec7d-146">To add a computed column when creating a table</span></span>  
  
1.  <span data-ttu-id="cec7d-147">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec7d-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cec7d-148">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cec7d-149">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-149">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="cec7d-150">O exemplo a seguir cria uma tabela com uma coluna computada que multiplica o valor da coluna `QtyAvailable` pelo valor da coluna `UnitPrice` .</span><span class="sxs-lookup"><span data-stu-id="cec7d-150">The example creates a table with a computed column that multiplies the value in the `QtyAvailable` column times the value in the `UnitPrice` column.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products   
    (  
        ProductID int IDENTITY (1,1) NOT NULL  
      , QtyAvailable smallint  
      , UnitPrice money  
      , InventoryValue AS QtyAvailable * UnitPrice  
    );  
  
    -- Insert values into the table.  
    INSERT INTO dbo.Products (QtyAvailable, UnitPrice)  
    VALUES (25, 2.00), (10, 1.5);  
  
    -- Display the rows in the table.  
    SELECT ProductID, QtyAvailable, UnitPrice, InventoryValue  
    FROM dbo.Products;  
  
    ```  
  
#### <a name="to-add-a-new-computed-column-to-an-existing-table"></a><span data-ttu-id="cec7d-151">Para adicionar uma nova coluna computada em uma tabela existente</span><span class="sxs-lookup"><span data-stu-id="cec7d-151">To add a new computed column to an existing table</span></span>  
  
1.  <span data-ttu-id="cec7d-152">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec7d-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cec7d-153">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cec7d-154">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-154">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="cec7d-155">O exemplo a seguir adiciona uma nova coluna à tabela criada no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="cec7d-155">The following example adds a new column to the table created in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.35);  
  
    ```  
  
#### <a name="to-change-an-existing-column-to-a-computed-column"></a><span data-ttu-id="cec7d-156">Para transformar uma coluna existente em coluna computada</span><span class="sxs-lookup"><span data-stu-id="cec7d-156">To change an existing column to a computed column</span></span>  
  
1.  <span data-ttu-id="cec7d-157">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec7d-157">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cec7d-158">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cec7d-159">Para transformar uma coluna existente em coluna computada, é necessário descartar e recriar a coluna computada.</span><span class="sxs-lookup"><span data-stu-id="cec7d-159">To change an existing column to a computed column you must drop and re-create the computed column.</span></span> <span data-ttu-id="cec7d-160">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="cec7d-160">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="cec7d-161">O exemplo a seguir modifica a coluna adicionada no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="cec7d-161">The following example modifies the column added in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products DROP COLUMN RetailValue;  
    GO  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.5);  
  
    ```  
  
     <span data-ttu-id="cec7d-162">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cec7d-162">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
