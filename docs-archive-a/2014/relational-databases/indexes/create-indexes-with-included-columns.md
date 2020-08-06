---
title: Criar índices com colunas incluídas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index size [SQL Server]
- index keys [SQL Server]
- index columns [SQL Server]
- size [SQL Server], indexes
- key columns [SQL Server]
- included columns
- nonclustered indexes [SQL Server], included columns
- designing indexes [SQL Server], included columns
- nonkey columns
ms.assetid: d198648d-fea5-416d-9f30-f9d4aebbf4ec
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5a464f9791ea635236069555647229bf1f0d79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685121"
---
# <a name="create-indexes-with-included-columns"></a><span data-ttu-id="f3537-102">Criar índices com colunas incluídas</span><span class="sxs-lookup"><span data-stu-id="f3537-102">Create Indexes with Included Columns</span></span>
  <span data-ttu-id="f3537-103">Este tópico descreve como adicionar colunas incluído (ou não chave) para estender a funcionalidade de índices não clusterizados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3537-103">This topic describes how to add included (or nonkey) columns to extend the functionality of nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f3537-104">Ao incluir colunas não chave, você pode criar você índices não clusterizados que abrangem mais consultas.</span><span class="sxs-lookup"><span data-stu-id="f3537-104">By including nonkey columns, you can create nonclustered indexes that cover more queries.</span></span> <span data-ttu-id="f3537-105">Isto porque as colunas não chave têm os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="f3537-105">This is because the nonkey columns have the following benefits:</span></span>  
  
-   <span data-ttu-id="f3537-106">Elas podem ser tipos de dados não permitidos como colunas de chave de índice.</span><span class="sxs-lookup"><span data-stu-id="f3537-106">They can be data types not allowed as index key columns.</span></span>  
  
-   <span data-ttu-id="f3537-107">Eles não são considerados pelo [!INCLUDE[ssDE](../../includes/ssde-md.md)] ao calcular o número de colunas de chave de índice ou o tamanho da chave de índice.</span><span class="sxs-lookup"><span data-stu-id="f3537-107">They are not considered by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] when calculating the number of index key columns or index key size.</span></span>  
  
 <span data-ttu-id="f3537-108">Um índice com colunas não chave pode melhorar o desempenho de consulta significativamente quando todas as colunas na consulta são incluídas no índice como colunas de chave ou não chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-108">An index with nonkey columns can significantly improve query performance when all columns in the query are included in the index either as key or nonkey columns.</span></span> <span data-ttu-id="f3537-109">Os ganhos de desempenho são alcançados pois o otimizador de consulta pode localizar todos os valores de coluna dentro do índice, a tabela, ou dados de índice clusterizado não são acessados, resultando em poucas operações de E/S de disco.</span><span class="sxs-lookup"><span data-stu-id="f3537-109">Performance gains are achieved because the query optimizer can locate all the column values within the index; table or clustered index data is not accessed resulting in fewer disk I/O operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3537-110">Quando um índice contém todas as colunas referenciadas por uma consulta, ele costuma ser referenciado como se *abrangendo a consulta*.</span><span class="sxs-lookup"><span data-stu-id="f3537-110">When an index contains all the columns referenced by a query it is typically referred to as *covering the query*.</span></span>  
  
 <span data-ttu-id="f3537-111">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f3537-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f3537-112">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="f3537-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f3537-113">Recomendações de design</span><span class="sxs-lookup"><span data-stu-id="f3537-113">Design Recommendations</span></span>](#DesignRecs)  
  
     [<span data-ttu-id="f3537-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f3537-114">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f3537-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="f3537-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f3537-116">**Para criar um índice com colunas não chave, usando:**</span><span class="sxs-lookup"><span data-stu-id="f3537-116">**To create an index with nonkey columns, using:**</span></span>  
  
     [<span data-ttu-id="f3537-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3537-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f3537-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3537-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f3537-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f3537-119">Before You Begin</span></span>  
  
###  <a name="design-recommendations"></a><a name="DesignRecs"></a> <span data-ttu-id="f3537-120">Recomendações de design</span><span class="sxs-lookup"><span data-stu-id="f3537-120">Design Recommendations</span></span>  
  
-   <span data-ttu-id="f3537-121">Redesenhe índices não clusterizados com um comprimento de chave de índice, de tal forma que apenas as colunas usadas para buscas e pesquisas sejam colunas de chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-121">Redesign nonclustered indexes with a large index key size so that only columns used for searching and lookups are key columns.</span></span> <span data-ttu-id="f3537-122">Transforme todas as outras colunas que abrangem a consulta em colunas não chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-122">Make all other columns that cover the query into nonkey columns.</span></span> <span data-ttu-id="f3537-123">Deste modo, você terá todas as colunas necessárias para abranger a consulta, mas a chave de índice em si é pequena e eficiente.</span><span class="sxs-lookup"><span data-stu-id="f3537-123">In this way, you will have all columns needed to cover the query, but the index key itself is small and efficient.</span></span>  
  
-   <span data-ttu-id="f3537-124">Inclua colunas não chave em um índice não clusterizado para evitar exceder as limitações do tamanho atual do índice, de um máximo de 16 colunas de chave, e um tamanho máximo de chave de índice de 900 bytes.</span><span class="sxs-lookup"><span data-stu-id="f3537-124">Include nonkey columns in a nonclustered index to avoid exceeding the current index size limitations of a maximum of 16 key columns and a maximum index key size of 900 bytes.</span></span> <span data-ttu-id="f3537-125">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] não considera as colunas não chave ao calcular o número de colunas de chave de índice, ou o tamanho da chave do índice.</span><span class="sxs-lookup"><span data-stu-id="f3537-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not consider nonkey columns when calculating the number of index key columns or index key size.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f3537-126">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f3537-126">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f3537-127">As colunas não chave só podem ser definidas em índices não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="f3537-127">Nonkey columns can only be defined on nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="f3537-128">Todos os tipos de dados, exceto `text`, `ntext` e `image`, podem ser usados como colunas não chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-128">All data types except `text`, `ntext`, and `image` can be used as nonkey columns.</span></span>  
  
-   <span data-ttu-id="f3537-129">As colunas computadas que são determinísticas e precisas ou imprecisas podem ser colunas não chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-129">Computed columns that are deterministic and either precise or imprecise can be nonkey columns.</span></span> <span data-ttu-id="f3537-130">Para obter mais informações, consulte [Indexes on Computed Columns](indexes-on-computed-columns.md).</span><span class="sxs-lookup"><span data-stu-id="f3537-130">For more information, see [Indexes on Computed Columns](indexes-on-computed-columns.md).</span></span>  
  
-   <span data-ttu-id="f3537-131">As colunas computadas derivadas dos tipos de dados `image`, `ntext` e `text` podem ser colunas não chave, desde que o tipo de dados da coluna computada seja permitido como uma coluna de índice não chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-131">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey columns as long as the computed column data type is allowed as a nonkey index column.</span></span>  
  
-   <span data-ttu-id="f3537-132">As colunas que não são de chave não podem ser removidas de uma tabela, a menos que o índice dessa tabela seja removido primeiro.</span><span class="sxs-lookup"><span data-stu-id="f3537-132">Nonkey columns cannot be dropped from a table unless that table's index is dropped first.</span></span>  
  
-   <span data-ttu-id="f3537-133">As colunas não chave não podem ser alteradas, exceto para fazerem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3537-133">Nonkey columns cannot be changed, except to do the following:</span></span>  
  
    -   <span data-ttu-id="f3537-134">Alterar a nulidade da coluna da coluna NOT NULL até NULL.</span><span class="sxs-lookup"><span data-stu-id="f3537-134">Change the nullability of the column from NOT NULL to NULL.</span></span>  
  
    -   <span data-ttu-id="f3537-135">Aumentar o comprimento das colunas `varchar`, `nvarchar`, ou `varbinary` .</span><span class="sxs-lookup"><span data-stu-id="f3537-135">Increase the length of `varchar`, `nvarchar`, or `varbinary` columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f3537-136">Segurança</span><span class="sxs-lookup"><span data-stu-id="f3537-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f3537-137">Permissões</span><span class="sxs-lookup"><span data-stu-id="f3537-137">Permissions</span></span>  
 <span data-ttu-id="f3537-138">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="f3537-138">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="f3537-139">O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="f3537-139">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f3537-140">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3537-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="f3537-141">Para criar um índice com colunas não chave</span><span class="sxs-lookup"><span data-stu-id="f3537-141">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="f3537-142">No Pesquisador de Objetos, clique no sinal de adição para expandir o banco de dados que contém a tabela na qual você deseja criar um índice com colunas não chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-142">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create an index with nonkey columns.</span></span>  
  
2.  <span data-ttu-id="f3537-143">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="f3537-143">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f3537-144">Clique no sinal de adição para expandir a tabela na qual você deseja criar um índice com colunas não chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-144">Click the plus sign to expand the table on which you want to create an index with nonkey columns.</span></span>  
  
4.  <span data-ttu-id="f3537-145">Clique com o botão direito do mouse na pasta **Índices**, aponte para **Novo Índice** e selecione **Índice Não Clusterizado...** .</span><span class="sxs-lookup"><span data-stu-id="f3537-145">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="f3537-146">Na caixa de diálogo **Novo Índice** , na página **Geral** , insira o nome do novo índice na caixa **Nome do índice** .</span><span class="sxs-lookup"><span data-stu-id="f3537-146">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="f3537-147">Na guia **Colunas de chave de índice**, clique em **Adicionar...** .</span><span class="sxs-lookup"><span data-stu-id="f3537-147">Under the **Index key columns** tab, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="f3537-148">Na caixa de diálogo **selecionar colunas de**_table_name_ , marque a caixa de seleção ou caixas de seleção da coluna ou das colunas da tabela a serem adicionadas ao índice.</span><span class="sxs-lookup"><span data-stu-id="f3537-148">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index.</span></span>  
  
8.  <span data-ttu-id="f3537-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3537-149">Click **OK**.</span></span>  
  
9. <span data-ttu-id="f3537-150">Na guia **Colunas incluídas**, clique em **Adicionar...** .</span><span class="sxs-lookup"><span data-stu-id="f3537-150">Under the **Included columns** tab, click **Add...**.</span></span>  
  
10. <span data-ttu-id="f3537-151">Na caixa de diálogo **selecionar colunas de**_table_name_ , marque as caixas de seleção da coluna de tabela ou das colunas a serem adicionadas ao índice como colunas não chave.</span><span class="sxs-lookup"><span data-stu-id="f3537-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the index as nonkey columns.</span></span>  
  
11. <span data-ttu-id="f3537-152">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3537-152">Click **OK**.</span></span>  
  
12. <span data-ttu-id="f3537-153">Na caixa de diálogo **Novo Índice** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3537-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f3537-154">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3537-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-index-with-nonkey-columns"></a><span data-ttu-id="f3537-155">Para criar um índice com colunas não chave</span><span class="sxs-lookup"><span data-stu-id="f3537-155">To create an index with nonkey columns</span></span>  
  
1.  <span data-ttu-id="f3537-156">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3537-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f3537-157">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f3537-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f3537-158">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f3537-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates a nonclustered index on the Person.Address table with four included (nonkey) columns.   
    -- index key column is PostalCode and the nonkey columns are  
    -- AddressLine1, AddressLine2, City, and StateProvinceID.  
    CREATE NONCLUSTERED INDEX IX_Address_PostalCode  
    ON Person.Address (PostalCode)  
    INCLUDE (AddressLine1, AddressLine2, City, StateProvinceID);  
    GO  
    ```  
  
 <span data-ttu-id="f3537-159">Para obter mais informações, consulte [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3537-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
