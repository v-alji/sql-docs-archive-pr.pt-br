---
title: Criar índices exclusivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- unique indexes
- designing indexes [SQL Server], unique
- clustered indexes, unique
- indexes [SQL Server], unique
- nonclustered indexes [SQL Server], unique
- unique indexes, design guidelines
ms.assetid: 56b5982e-cb94-46c0-8fbb-772fc275354a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c96c4e17a8ce0863452db171302d650f6114919
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685117"
---
# <a name="create-unique-indexes"></a><span data-ttu-id="91eaa-102">Criar índices exclusivos</span><span class="sxs-lookup"><span data-stu-id="91eaa-102">Create Unique Indexes</span></span>
  <span data-ttu-id="91eaa-103">Este tópico descreve como criar um índice exclusivo em uma tabela no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91eaa-103">This topic describes how to create a unique index on a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="91eaa-104">Um índice exclusivo garante que a chave de índice não contém nenhum valor duplicado e, portanto, cada linha na tabela é exclusiva de algum modo.</span><span class="sxs-lookup"><span data-stu-id="91eaa-104">A unique index guarantees that the index key contains no duplicate values and therefore every row in the table is in some way unique.</span></span> <span data-ttu-id="91eaa-105">Não existe nenhuma diferença significativa entre criar uma restrição UNIQUE e criar um índice exclusivo que seja independente de uma restrição.</span><span class="sxs-lookup"><span data-stu-id="91eaa-105">There are no significant differences between creating a UNIQUE constraint and creating a unique index that is independent of a constraint.</span></span> <span data-ttu-id="91eaa-106">A validação de dados ocorre da mesma maneira, e o otimizador de consultas não diferencia entre um índice exclusivo criado por uma restrição ou manualmente criado.</span><span class="sxs-lookup"><span data-stu-id="91eaa-106">Data validation occurs in the same manner, and the query optimizer does not differentiate between a unique index created by a constraint or manually created.</span></span> <span data-ttu-id="91eaa-107">No entanto, criar uma restrição UNIQUE na coluna torna claro o objetivo do índice.</span><span class="sxs-lookup"><span data-stu-id="91eaa-107">However, creating a UNIQUE constraint on the column makes the objective of the index clear.</span></span> <span data-ttu-id="91eaa-108">Para obter mais informações sobre restrições UNIQUE, consulte [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="91eaa-108">For more information on UNIQUE constraints, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="91eaa-109">Quando você criar um índice exclusivo, será possível definir uma opção para ignorar chaves duplicadas.</span><span class="sxs-lookup"><span data-stu-id="91eaa-109">When you create a unique index, you can set an option to ignore duplicate keys.</span></span> <span data-ttu-id="91eaa-110">Se essa opção for definida como **Sim** e você tentar criar chaves duplicadas adicionando dados que afetem várias linhas (com a instrução INSERT), a linha que contém uma duplicata não será adicionada.</span><span class="sxs-lookup"><span data-stu-id="91eaa-110">If this option is set to **Yes** and you attempt to create duplicate keys by adding data that affects multiple rows (with the INSERT statement), the row containing a duplicate is not added.</span></span> <span data-ttu-id="91eaa-111">Se ela for definida como **Não**, ocorrerá falha em toda a operação de inserção e todos os dados serão revertidos.</span><span class="sxs-lookup"><span data-stu-id="91eaa-111">If it is set to **No**, the entire insert operation fails and all the data is rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91eaa-112">Você não poderá criar um índice exclusivo em uma única coluna se ela tiver NULL em mais de uma linha.</span><span class="sxs-lookup"><span data-stu-id="91eaa-112">You cannot create a unique index on a single column if that column contains NULL in more than one row.</span></span> <span data-ttu-id="91eaa-113">Da mesma forma, você não poderá criar um índice exclusivo em várias colunas se a combinação de colunas tiver NULL em mais de uma linha.</span><span class="sxs-lookup"><span data-stu-id="91eaa-113">Similarly, you cannot create a unique index on multiple columns if the combination of columns contains NULL in more than one row.</span></span> <span data-ttu-id="91eaa-114">Isso é tratado como valores duplicados para fins de indexação.</span><span class="sxs-lookup"><span data-stu-id="91eaa-114">These are treated as duplicate values for indexing purposes.</span></span>  
  
 <span data-ttu-id="91eaa-115">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="91eaa-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="91eaa-116">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="91eaa-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="91eaa-117">Benefícios de um índice exclusivo</span><span class="sxs-lookup"><span data-stu-id="91eaa-117">Benefits of a Unique Index</span></span>](#Benefits)  
  
     [<span data-ttu-id="91eaa-118">Implementações comuns</span><span class="sxs-lookup"><span data-stu-id="91eaa-118">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="91eaa-119">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="91eaa-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="91eaa-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="91eaa-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="91eaa-121">**Para criar um índice exclusivo em uma tabela usando:**</span><span class="sxs-lookup"><span data-stu-id="91eaa-121">**To create a unique index on a table, using:**</span></span>  
  
     [<span data-ttu-id="91eaa-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="91eaa-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="91eaa-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="91eaa-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="91eaa-124">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="91eaa-124">Before You Begin</span></span>  
  
###  <a name="benefits-of-a-unique-index"></a><a name="Benefits"></a> <span data-ttu-id="91eaa-125">Benefícios de um índice exclusivo</span><span class="sxs-lookup"><span data-stu-id="91eaa-125">Benefits of a Unique Index</span></span>  
  
-   <span data-ttu-id="91eaa-126">Índices exclusivos de multicolunas garantem que cada combinação de valores na chave de índice é exclusivo.</span><span class="sxs-lookup"><span data-stu-id="91eaa-126">Multicolumn unique indexes guarantee that each combination of values in the index key is unique.</span></span> <span data-ttu-id="91eaa-127">Por exemplo, se um índice exclusivo for criado em uma combinação de colunas **LastName**, **FirstName**e **MiddleName** , duas linhas na tabela não poderão ter a mesma combinação de valores que essas colunas.</span><span class="sxs-lookup"><span data-stu-id="91eaa-127">For example, if a unique index is created on a combination of **LastName**, **FirstName**, and **MiddleName** columns, no two rows in the table could have the same combination of values for these columns.</span></span>  
  
-   <span data-ttu-id="91eaa-128">Contanto que os dados em cada coluna sejam exclusivos, você pode criar um índice clusterizado exclusivo e vários índices exclusivos não clusterizados na mesma tabela.</span><span class="sxs-lookup"><span data-stu-id="91eaa-128">Provided that the data in each column is unique, you can create both a unique clustered index and multiple unique nonclustered indexes on the same table.</span></span>  
  
-   <span data-ttu-id="91eaa-129">Os índices exclusivos garantem a integridade de dados das colunas definidas.</span><span class="sxs-lookup"><span data-stu-id="91eaa-129">Unique indexes ensure the data integrity of the defined columns.</span></span>  
  
-   <span data-ttu-id="91eaa-130">Índices exclusivos fornecem informações adicionais úteis para o otimizador de consulta que pode gerar planos de execução mais eficientes.</span><span class="sxs-lookup"><span data-stu-id="91eaa-130">Unique indexes provide additional information helpful to the query optimizer that can produce more efficient execution plans.</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="91eaa-131">Implementações comuns</span><span class="sxs-lookup"><span data-stu-id="91eaa-131">Typical Implementations</span></span>  
 <span data-ttu-id="91eaa-132">Os índices exclusivos são implementados das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="91eaa-132">Unique indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="91eaa-133">**Restrição PRIMARY KEY ou UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="91eaa-133">**PRIMARY KEY or UNIQUE constraint**</span></span>  
  
     <span data-ttu-id="91eaa-134">Quando se cria uma restrição PRIMARY KEY, é criado automaticamente um índice clusterizado exclusivo na coluna ou a coluna é automaticamente criada se não existir um índice clusterizado na tabela e você não especificar um índice não clusterizado exclusivo.</span><span class="sxs-lookup"><span data-stu-id="91eaa-134">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="91eaa-135">A coluna de chave primária não pode permitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="91eaa-135">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="91eaa-136">Quando se cria uma restrição UNIQUE, é criado, por padrão, um índice não clusterizado exclusivo para impor uma restrição UNIQUE por padrão.</span><span class="sxs-lookup"><span data-stu-id="91eaa-136">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="91eaa-137">Você pode especificar um índice clusterizado exclusivo caso ainda não exista um índice clusterizado na tabela.</span><span class="sxs-lookup"><span data-stu-id="91eaa-137">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="91eaa-138">Para obter mais informações, consulte [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) e [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="91eaa-138">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) and [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span></span>  
  
-   <span data-ttu-id="91eaa-139">**Índice independente de uma restrição**</span><span class="sxs-lookup"><span data-stu-id="91eaa-139">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="91eaa-140">Vários índices não clusterizado exclusivos podem ser definidos em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="91eaa-140">Multiple unique nonclustered indexes can be defined on a table.</span></span>  
  
     <span data-ttu-id="91eaa-141">Para obter mais informações, consulte [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="91eaa-141">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="91eaa-142">**Exibição indexada**</span><span class="sxs-lookup"><span data-stu-id="91eaa-142">**Indexed view**</span></span>  
  
     <span data-ttu-id="91eaa-143">Para criar uma exibição indexada, um índice clusterizado exclusivo é definido em uma ou mais colunas de exibição.</span><span class="sxs-lookup"><span data-stu-id="91eaa-143">To create an indexed view, a unique clustered index is defined on one or more view columns.</span></span> <span data-ttu-id="91eaa-144">A exibição é executada e o conjunto de resultados é armazenado no nível folha do índice da mesma forma que os dados de tabela são armazenados em um índice clusterizado.</span><span class="sxs-lookup"><span data-stu-id="91eaa-144">The view is executed and the result set is stored in the leaf level of the index in the same way table data is stored in a clustered index.</span></span> <span data-ttu-id="91eaa-145">Para obter mais informações, veja [Criar exibições indexadas](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="91eaa-145">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="91eaa-146">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="91eaa-146">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="91eaa-147">Um índice exclusivo, uma restrição UNIQUE ou uma restrição PRIMARY KEY não poderão ser criados, se existirem valores de chave duplicados nos dados.</span><span class="sxs-lookup"><span data-stu-id="91eaa-147">A unique index, UNIQUE constraint, or PRIMARY KEY constraint cannot be created if duplicate key values exist in the data.</span></span>  
  
-   <span data-ttu-id="91eaa-148">Um índice não clusterizado exclusivo pode conter colunas não chave incluídas.</span><span class="sxs-lookup"><span data-stu-id="91eaa-148">A unique nonclustered index can contain included nonkey columns.</span></span> <span data-ttu-id="91eaa-149">Para obter mais informações, consulte [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="91eaa-149">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="91eaa-150">Segurança</span><span class="sxs-lookup"><span data-stu-id="91eaa-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="91eaa-151">Permissões</span><span class="sxs-lookup"><span data-stu-id="91eaa-151">Permissions</span></span>  
 <span data-ttu-id="91eaa-152">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="91eaa-152">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="91eaa-153">O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-153">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="91eaa-154">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="91eaa-154">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-index-by-using-the-table-designer"></a><span data-ttu-id="91eaa-155">Para criar um índice exclusivo usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="91eaa-155">To create a unique index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="91eaa-156">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja criar um índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="91eaa-156">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="91eaa-157">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-157">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="91eaa-158">Clique com o botão direito do mouse na tabela na qual você deseja criar um índice exclusivo e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-158">Right-click the table on which you want to create a unique index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="91eaa-159">No menu **Designer de Tabela** , selecione **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-159">On the **Table Designer** menu, select **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="91eaa-160">Na caixa de diálogo **Índices/Chaves** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-160">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="91eaa-161">Selecione o novo índice na caixa de texto **Índice ou Chave Exclusiva/Primária Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-161">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="91eaa-162">Na grade principal, em **(Geral)** , selecione **Tipo** e escolha **Índice** na lista.</span><span class="sxs-lookup"><span data-stu-id="91eaa-162">In the main grid, under **(General)**, select **Type** and then choose **Index** from the list.</span></span>  
  
8.  <span data-ttu-id="91eaa-163">Selecione **Colunas** e clique no botão reticências **(...)** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-163">Select **Columns**, and then click the ellipsis **(...)**.</span></span>  
  
9. <span data-ttu-id="91eaa-164">Na caixa de diálogo **Colunas de Índice** , em **Nome da Coluna**, selecione as colunas que você deseja indexar.</span><span class="sxs-lookup"><span data-stu-id="91eaa-164">In the **Index Columns** dialog box, under **Column Name**, select the columns you want to index.</span></span> <span data-ttu-id="91eaa-165">Você pode selecionar até 16 colunas.</span><span class="sxs-lookup"><span data-stu-id="91eaa-165">You can select up to 16 columns.</span></span> <span data-ttu-id="91eaa-166">Para um desempenho ideal, selecione somente uma ou duas colunas por índice.</span><span class="sxs-lookup"><span data-stu-id="91eaa-166">For optimal performance, select only one or two columns per index.</span></span> <span data-ttu-id="91eaa-167">Para cada coluna selecionada, indique se o índice organiza os valores dessa coluna em ordem crescente ou decrescente.</span><span class="sxs-lookup"><span data-stu-id="91eaa-167">For each column you select, indicate whether the index arranges values of this column in ascending or descending order.</span></span>  
  
10. <span data-ttu-id="91eaa-168">Quando todas as colunas para o índice estiverem selecionadas, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-168">When all columns for the index are selected, click **OK**.</span></span>  
  
11. <span data-ttu-id="91eaa-169">Na grade, em **(Geral)** , selecione **É Exclusivo** e escolha **Sim** na lista.</span><span class="sxs-lookup"><span data-stu-id="91eaa-169">In the grid, under **(General)**, select **Is Unique** and then choose **Yes** from the list.</span></span>  
  
12. <span data-ttu-id="91eaa-170">Opcional: na grade principal, em **Designer de Tabela**, selecione **Ignorar Chaves Duplicadas** e escolha **Sim** na lista.</span><span class="sxs-lookup"><span data-stu-id="91eaa-170">Optional: In the main grid, under **Table Designer**, select **Ignore Duplicate Keys** and then choose **Yes** from the list.</span></span> <span data-ttu-id="91eaa-171">Faça isso se você desejar ignorar as tentativas de adição de dados que criariam uma chave duplicada no índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="91eaa-171">Do this if you want to ignore attempts to add data that would create a duplicate key in the unique index.</span></span>  
  
13. <span data-ttu-id="91eaa-172">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="91eaa-172">Click **Close**.</span></span>  
  
14. <span data-ttu-id="91eaa-173">No menu **Arquivo** , clique em **Salvar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="91eaa-173">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="create-a-unique-index-by-using-object-explorer"></a><span data-ttu-id="91eaa-174">Crie um índice exclusivo usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="91eaa-174">Create a unique index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="91eaa-175">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja criar um índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="91eaa-175">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="91eaa-176">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-176">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="91eaa-177">Expanda a tabela na qual você deseja criar um índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="91eaa-177">Expand the table on which you want to create a unique index.</span></span>  
  
4.  <span data-ttu-id="91eaa-178">Clique com o botão direito do mouse na pasta **Índices**, aponte para **Novo Índice** e selecione **Índice Não Clusterizado...** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-178">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="91eaa-179">Na caixa de diálogo **Novo Índice** , na página **Geral** , insira o nome do novo índice na caixa **Nome do índice** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-179">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="91eaa-180">Marque a caixa de seleção **Exclusivo** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-180">Select the **Unique** check box.</span></span>  
  
7.  <span data-ttu-id="91eaa-181">Em **Colunas de chave de índice**, clique em **Adicionar...** .</span><span class="sxs-lookup"><span data-stu-id="91eaa-181">Under **Index key columns**, click **Add...**.</span></span>  
  
8.  <span data-ttu-id="91eaa-182">Na caixa de diálogo **selecionar colunas de**_table_name_ , marque as caixas de seleção das colunas da tabela a serem adicionadas ao índice exclusivo.</span><span class="sxs-lookup"><span data-stu-id="91eaa-182">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
9. <span data-ttu-id="91eaa-183">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-183">Click **OK**.</span></span>  
  
10. <span data-ttu-id="91eaa-184">Na caixa de diálogo **Novo Índice** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-184">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="91eaa-185">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="91eaa-185">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-index-on-a-table"></a><span data-ttu-id="91eaa-186">Para criar um índice exclusivo em uma tabela</span><span class="sxs-lookup"><span data-stu-id="91eaa-186">To create a unique index on a table</span></span>  
  
1.  <span data-ttu-id="91eaa-187">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91eaa-187">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="91eaa-188">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-188">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="91eaa-189">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="91eaa-189">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named AK_UnitMeasure_Name and delete it if found  
    IF EXISTS (SELECT name from sys.indexes  
               WHERE name = N'AK_UnitMeasure_Name')   
       DROP INDEX AK_UnitMeasure_Name ON Production.UnitMeasure;   
    GO  
    -- Create a unique index called AK_UnitMeasure_Name  
    -- on the Production.UnitMeasure table using the Name column.  
    CREATE UNIQUE INDEX AK_UnitMeasure_Name   
       ON Production.UnitMeasure (Name);   
    GO  
    ```  
  
 <span data-ttu-id="91eaa-190">Para obter mais informações, consulte [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="91eaa-190">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
