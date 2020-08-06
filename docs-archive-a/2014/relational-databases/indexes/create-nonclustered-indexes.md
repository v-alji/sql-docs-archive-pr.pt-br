---
title: Criar índices não clusterizados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], nonclustered indexes
- nonclustered indexes [SQL Server], creating
- nonclustered indexes [SQL Server], UNIQUE constraint
- indexes [SQL Server], nonclustered
- nonclustered indexes [SQL Server], PRIMARY KEY constraint
ms.assetid: 9402029a-1227-46c4-93aa-c2122eb1b943
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fae0c06b1f562dc3fc518a319df1787b3384c0cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685114"
---
# <a name="create-nonclustered-indexes"></a><span data-ttu-id="8e59d-102">Criar índices não clusterizados</span><span class="sxs-lookup"><span data-stu-id="8e59d-102">Create Nonclustered Indexes</span></span>
  <span data-ttu-id="8e59d-103">Você pode criar índices não clusterizados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e59d-103">You can create nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8e59d-104">Um índice não clusterizado é uma estrutura de índice separada dos dados armazenados em uma tabela que reorganiza um ou mais colunas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="8e59d-104">A nonclustered index is an index structure separate from the data stored in a table that reorders one or more selected columns.</span></span> <span data-ttu-id="8e59d-105">Índices não clusterizados costumam ser uma forma mais rápida de localizar dados do que a busca na tabela subjacente; as consultas às vezes podem ser totalmente respondidas pelos dados no índice não clusterizado, ou o índice não clusterizado pode apontar o [!INCLUDE[ssDE](../../includes/ssde-md.md)] para as linhas na tabela subjacente.</span><span class="sxs-lookup"><span data-stu-id="8e59d-105">Nonclustered indexes can often help you find data more quickly than searching the underlying table; queries can sometimes be answered entirely by the data in the nonclustered index, or the nonclustered index can point the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to the rows in the underlying table.</span></span> <span data-ttu-id="8e59d-106">Geralmente, os índices não clusterizados são criados para aprimorar o desempenho de consultas utilizadas com frequência, não cobertas pelo índice clusterizado, ou para localizar linhas em uma tabela sem um índice clusterizado (denominado heap).</span><span class="sxs-lookup"><span data-stu-id="8e59d-106">Generally, nonclustered indexes are created to improve the performance of frequently used queries not covered by the clustered index or to locate rows in a table without a clustered index (called a heap).</span></span> <span data-ttu-id="8e59d-107">Você pode criar vários índices não clusterizados em uma tabela ou exibição indexada.</span><span class="sxs-lookup"><span data-stu-id="8e59d-107">You can create multiple nonclustered indexes on a table or indexed view.</span></span>  
  
 <span data-ttu-id="8e59d-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8e59d-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8e59d-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8e59d-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8e59d-110">Implementações comuns</span><span class="sxs-lookup"><span data-stu-id="8e59d-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="8e59d-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="8e59d-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8e59d-112">**Para criar um índice não clusterizado, usando:**</span><span class="sxs-lookup"><span data-stu-id="8e59d-112">**To create a nonclustered index, using:**</span></span>  
  
     [<span data-ttu-id="8e59d-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e59d-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8e59d-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e59d-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8e59d-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8e59d-115">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a><span data-ttu-id="8e59d-116">Implementações típicas</span><span class="sxs-lookup"><span data-stu-id="8e59d-116">Typical Implementations</span></span>  
 <span data-ttu-id="8e59d-117">Os índices não clusterizados são implementados das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="8e59d-117">Nonclustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="8e59d-118">**Restrições EXCLUSIVAs**</span><span class="sxs-lookup"><span data-stu-id="8e59d-118">**UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="8e59d-119">Quando se cria uma restrição UNIQUE, é criado, por padrão, um índice não clusterizado exclusivo para impor uma restrição UNIQUE por padrão.</span><span class="sxs-lookup"><span data-stu-id="8e59d-119">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="8e59d-120">Você pode especificar um índice clusterizado exclusivo caso ainda não exista um índice clusterizado na tabela.</span><span class="sxs-lookup"><span data-stu-id="8e59d-120">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span> <span data-ttu-id="8e59d-121">Para obter mais informações, consulte [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="8e59d-121">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="8e59d-122">**Índice independente de uma restrição**</span><span class="sxs-lookup"><span data-stu-id="8e59d-122">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="8e59d-123">Por padrão, será criado um índice não clusterizado se não for especificado como clusterizado.</span><span class="sxs-lookup"><span data-stu-id="8e59d-123">By default, a nonclustered index is created if clustered is not specified.</span></span> <span data-ttu-id="8e59d-124">O número máximo de índices não clusterizados que podem ser criados em uma tabela é 999.</span><span class="sxs-lookup"><span data-stu-id="8e59d-124">The maximum number of nonclustered indexes that can be created per table is 999.</span></span> <span data-ttu-id="8e59d-125">Isso inclui qualquer índice criado por restrições PRIMARY KEY ou UNIQUE, mas não inclui índices XML.</span><span class="sxs-lookup"><span data-stu-id="8e59d-125">This includes any indexes created by PRIMARY KEY or UNIQUE constraints, but does not include XML indexes.</span></span>  
  
-   <span data-ttu-id="8e59d-126">**Índice não clusterizado em uma exibição indexada**</span><span class="sxs-lookup"><span data-stu-id="8e59d-126">**Nonclustered index on an indexed view**</span></span>  
  
     <span data-ttu-id="8e59d-127">Depois que for criado um índice clusterizado exclusivo em uma exibição, poderão ser criados índices não clusterizados.</span><span class="sxs-lookup"><span data-stu-id="8e59d-127">After a unique clustered index has been created on a view, nonclustered indexes can be created.</span></span> <span data-ttu-id="8e59d-128">Para obter mais informações, veja [Criar exibições indexadas](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="8e59d-128">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8e59d-129">Segurança</span><span class="sxs-lookup"><span data-stu-id="8e59d-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8e59d-130">Permissões</span><span class="sxs-lookup"><span data-stu-id="8e59d-130">Permissions</span></span>  
 <span data-ttu-id="8e59d-131">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="8e59d-131">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="8e59d-132">O usuário deve ser membro da função de servidor fixa **sysadmin** ou das funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-132">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8e59d-133">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e59d-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-the-table-designer"></a><span data-ttu-id="8e59d-134">Para criar um índice não clusterizado usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="8e59d-134">To create a nonclustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="8e59d-135">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja criar um índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="8e59d-135">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="8e59d-136">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-136">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="8e59d-137">Clique com o botão direito do mouse na tabela na qual você deseja criar um índice não clusterizado e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-137">Right-click the table on which you want to create a nonclustered index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="8e59d-138">No menu **Designer de tabela** , clique em **índices/chaves**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-138">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="8e59d-139">Na caixa de diálogo **Índices/Chaves** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-139">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="8e59d-140">Selecione o novo índice na caixa de texto **Índice ou Chave Exclusiva/Primária Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-140">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="8e59d-141">Na grade, selecione **Criar como Clusterizado**e escolha **Não** na lista suspensa, à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="8e59d-141">In the grid, select **Create as Clustered**, and choose **No** from the drop-down list to the right of the property.</span></span>  
  
8.  <span data-ttu-id="8e59d-142">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-142">Click **Close**.</span></span>  
  
9. <span data-ttu-id="8e59d-143">No menu **Arquivo** , clique em **Salvar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="8e59d-143">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-object-explorer"></a><span data-ttu-id="8e59d-144">Para criar um índice não clusterizado usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="8e59d-144">To create a nonclustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="8e59d-145">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela na qual você deseja criar um índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="8e59d-145">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="8e59d-146">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-146">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="8e59d-147">Expanda a tabela na qual você deseja criar um índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="8e59d-147">Expand the table on which you want to create a nonclustered index.</span></span>  
  
4.  <span data-ttu-id="8e59d-148">Clique com o botão direito do mouse na pasta **Índices**, aponte para **Novo Índice** e selecione **Índice Não Clusterizado...** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-148">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="8e59d-149">Na caixa de diálogo **Novo Índice** , na página **Geral** , insira o nome do novo índice na caixa **Nome do índice** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-149">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="8e59d-150">Em **Colunas de chave de índice**, clique em **Adicionar...** .</span><span class="sxs-lookup"><span data-stu-id="8e59d-150">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="8e59d-151">Na caixa de diálogo **Selecionar Colunas de**_table_name_ , marque as caixas de seleção das colunas da tabela a serem adicionadas ao índice não clusterizado.</span><span class="sxs-lookup"><span data-stu-id="8e59d-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the nonclustered index.</span></span>  
  
8.  <span data-ttu-id="8e59d-152">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="8e59d-153">Na caixa de diálogo **Novo Índice** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8e59d-154">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e59d-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-nonclustered-index-on-a-table"></a><span data-ttu-id="8e59d-155">Para criar um índice não clusterizado em uma tabela</span><span class="sxs-lookup"><span data-stu-id="8e59d-155">To create a nonclustered index on a table</span></span>  
  
1.  <span data-ttu-id="8e59d-156">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e59d-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8e59d-157">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8e59d-158">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8e59d-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named IX_ProductVendor_VendorID and delete it if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
                WHERE name = N'IX_ProductVendor_VendorID')   
        DROP INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor;   
    GO  
    -- Create a nonclustered index called IX_ProductVendor_VendorID   
    -- on the Purchasing.ProductVendor table using the BusinessEntityID column.   
    CREATE NONCLUSTERED INDEX IX_ProductVendor_VendorID   
        ON Purchasing.ProductVendor (BusinessEntityID);   
    GO  
    ```  
  
 <span data-ttu-id="8e59d-159">Para obter mais informações, consulte [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8e59d-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
