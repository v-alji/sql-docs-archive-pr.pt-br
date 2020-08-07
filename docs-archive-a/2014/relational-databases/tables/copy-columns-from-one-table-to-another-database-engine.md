---
title: Copiar colunas de uma tabela para outra (mecanismo de banco de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying columns
- columns [SQL Server], copying
ms.assetid: 5f5e70dc-69f9-44b8-bc48-b5d51ac20d77
author: stevestein
ms.author: sstein
ms.openlocfilehash: 37b98bf0910cbbb4c2a1d7fe01f11d52703ec88c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584092"
---
# <a name="copy-columns-from-one-table-to-another-database-engine"></a><span data-ttu-id="a8228-102">Copiar colunas de uma tabela em outra (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="a8228-102">Copy Columns from One Table to Another (Database Engine)</span></span>
  <span data-ttu-id="a8228-103">Este tópico descreve como copiar colunas de uma tabela para outra, copiando apenas a definição da coluna ou a definição e os dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8228-103">This topic describes how to copy columns from one table to another, copying either just the column definition, or the definition and data in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a8228-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a8228-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a8228-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a8228-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a8228-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a8228-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a8228-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="a8228-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a8228-108">**Para copiar colunas, usando:**</span><span class="sxs-lookup"><span data-stu-id="a8228-108">**To coy columns, using:**</span></span>  
  
     [<span data-ttu-id="a8228-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8228-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a8228-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8228-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a8228-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a8228-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a8228-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a8228-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a8228-113">Quando uma coluna com um tipo de dados de alias é copiada de um banco de dados para outro, o tipo de dados de alias pode não estar disponível no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="a8228-113">When you copy a column that has an alias data type from one database to another, the alias data type may not be available in the destination database.</span></span> <span data-ttu-id="a8228-114">Nesse caso, a coluna receberá o tipo de dados base correspondente, mais próximo e disponível naquele banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a8228-114">In such a case, the column will be assigned the nearest matching base data type available in that database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a8228-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="a8228-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a8228-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="a8228-116">Permissions</span></span>  
 <span data-ttu-id="a8228-117">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="a8228-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a8228-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8228-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="a8228-119">Para copiar definições de coluna de uma tabela para outra</span><span class="sxs-lookup"><span data-stu-id="a8228-119">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="a8228-120">Abra a tabela que contém as colunas a serem copiadas e a tabela na qual deseja copiar as colunas clicando com o botão direito do mouse nas tabelas e clicando em **Design**.</span><span class="sxs-lookup"><span data-stu-id="a8228-120">Open the table with columns you want to copy and the one you want to copy into by right-clicking the tables, and then clicking **Design**.</span></span>  
  
2.  <span data-ttu-id="a8228-121">Clique na guia da tabela que contém as colunas a serem copiadas e selecione as colunas.</span><span class="sxs-lookup"><span data-stu-id="a8228-121">Click the tab for the table with the columns you want to copy and select those columns.</span></span>  
  
3.  <span data-ttu-id="a8228-122">No menu **Editar** clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="a8228-122">From the **Edit** menu, click **Copy**.</span></span>  
  
4.  <span data-ttu-id="a8228-123">Clique na guia da tabela, na qual você pretende copiar as colunas.</span><span class="sxs-lookup"><span data-stu-id="a8228-123">Click the tab for the table into which you want to copy the columns.</span></span>  
  
5.  <span data-ttu-id="a8228-124">Selecione a coluna à qual se seguirão as colunas inseridas e, no menu **Editar** , clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="a8228-124">Select the column you want to follow the inserted columns and, from the **Edit** menu, click **Paste**.</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="a8228-125">Para copiar dados de uma tabela para outra</span><span class="sxs-lookup"><span data-stu-id="a8228-125">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="a8228-126">Siga as orientações para copiar as definições da coluna acima.</span><span class="sxs-lookup"><span data-stu-id="a8228-126">Follow the directions for copying column definitions above.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8228-127">Antes de começar a copiar dados de uma tabela para outra, verifique se os tipos de dados nas colunas de destino são compatíveis com os tipos de dados das colunas de origem.</span><span class="sxs-lookup"><span data-stu-id="a8228-127">Before you begin to copy data from one table to another, make sure that the data types in the destination columns are compatible with the data types of the source columns</span></span>  
  
2.  <span data-ttu-id="a8228-128">No Pesquisador de Objetos, clique com o botão direito do mouse no nó **Exibições** e clique em **Nova Exibição**.</span><span class="sxs-lookup"><span data-stu-id="a8228-128">In Object Explorer, right-click the **Views** node, and then click **New View**.</span></span>  
  
3.  <span data-ttu-id="a8228-129">No menu **Designer de Consulta** , aponte para **Alterar Tipo**e clique em **Inserir Resultados**.</span><span class="sxs-lookup"><span data-stu-id="a8228-129">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
4.  <span data-ttu-id="a8228-130">Na caixa de diálogo **Escolher Tabela de Destino para Inserir Resultados** , selecione a tabela em que serão copiados os dados e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8228-130">In the **Choose Target Table for Insert Results** dialog box, select the table into which you want to copy the data, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a8228-131">Se você estiver copiando linhas em uma tabela, poderá adicionar a tabela de origem como tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="a8228-131">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8228-132">O**Designer de Consulta** não pode determinar antecipadamente quais tabelas e exibições poderão ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="a8228-132">**Query Designer** cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="a8228-133">Portanto a lista de tabelas da caixa de diálogo **Escolher Tabela de Destino para Inserir Resultados** mostra todas as tabelas e exibições disponíveis na conexão de dados que está sendo consultada, até mesmo aquelas nas quais não é possível copiar linhas.</span><span class="sxs-lookup"><span data-stu-id="a8228-133">Therefore, the list of tables in the **Choose Target Table for Insert Results** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
5.  <span data-ttu-id="a8228-134">Clique com o botão direito do mouse no corpo do painel do diagrama e, no menu de atalho, clique em **Adicionar Tabela ao Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="a8228-134">Right-click in the body of the diagram pane and, from the shortcut menu, click **Add Table to Diagram**.</span></span>  
  
6.  <span data-ttu-id="a8228-135">Na caixa de diálogo **Adicionar Tabela** , selecione as tabelas das quais você deseja copiar dados, clique em **Adicionar**e, em seguida, em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a8228-135">In the **Add Table** dialog box, select each table from which you want to copy data, click **Add**, and then click **Close**.</span></span>  
  
     <span data-ttu-id="a8228-136">As tabelas, em uma forma abreviada, aparecem no painel de diagrama.</span><span class="sxs-lookup"><span data-stu-id="a8228-136">The tables, in an abbreviated form, appear in the diagram pane.</span></span>  
  
7.  <span data-ttu-id="a8228-137">Nas tabelas abreviadas, marque as caixas de todas as colunas das quais você deseja copiar dados.</span><span class="sxs-lookup"><span data-stu-id="a8228-137">In the abbreviated tables, check the boxes for any columns from which you want to copy data.</span></span>  
  
8.  <span data-ttu-id="a8228-138">No painel de critérios, na coluna **Anexar** , para cada coluna de destino escolha uma coluna da qual você deseja copiar dados.</span><span class="sxs-lookup"><span data-stu-id="a8228-138">In the criteria pane, in the **Append** column, for each target column choose a column from which you want to copy data.</span></span>  
  
9. <span data-ttu-id="a8228-139">Especifique as linhas a serem copiadas inserindo critérios de pesquisa no painel de critérios.</span><span class="sxs-lookup"><span data-stu-id="a8228-139">Specify the rows to copy by entering search conditions in the criteria pane.</span></span> <span data-ttu-id="a8228-140">Para obter detalhes, veja [Especificar condições de pesquisa &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a8228-140">For details, see [Specify Search Conditions &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="a8228-141">Se você não especificar um critério de pesquisa, todas as linhas da tabela de origem serão copiadas na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="a8228-141">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
10. <span data-ttu-id="a8228-142">Se você quiser copiar informações de resumo, especifique opções **Agrupar por** .</span><span class="sxs-lookup"><span data-stu-id="a8228-142">If you want to copy summary information, specify **Group By** options.</span></span> <span data-ttu-id="a8228-143">Para obter detalhes, veja [Resumir ou agregar valores para todas as linhas de uma tabela &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a8228-143">For details, see [Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span></span>  
  
11. <span data-ttu-id="a8228-144">Clique no botão **Executar SQL** para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="a8228-144">Click the **Execute SQL button** to run the query.</span></span>  
  
     <span data-ttu-id="a8228-145">Quando uma consulta para inserir resultados é executada, nenhum resultado é relatado no [Painel de Resultados](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a8228-145">When you execute an insert results query, no results are reported in the [Results Pane](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="a8228-146">Em vez disso, será exibida uma mensagem indicando o total de linhas copiadas.</span><span class="sxs-lookup"><span data-stu-id="a8228-146">Instead, a message appears indicating how many rows were copied.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a8228-147">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8228-147">Using Transact-SQL</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="a8228-148">Para copiar definições de coluna de uma tabela para outra</span><span class="sxs-lookup"><span data-stu-id="a8228-148">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="a8228-149">Você não pode copiar colunas individuais de uma tabela para outra tabela existente usando instruções Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a8228-149">You cannot copy individual columns from one table to another existing table by using Transact-SQL statements.</span></span> <span data-ttu-id="a8228-150">No entanto, pode criar uma tabela nova no grupo de arquivos padrão e insere nela as linhas resultantes da consulta usando SELECT INTO.</span><span class="sxs-lookup"><span data-stu-id="a8228-150">However, you can create a new table in the default filegroup and inserts the resulting rows from the query into it by using SELECT INTO.</span></span> <span data-ttu-id="a8228-151">Para obter mais informações, veja [INTO Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a8228-151">For more information, see [INTO Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="a8228-152">Para copiar dados de uma tabela para outra</span><span class="sxs-lookup"><span data-stu-id="a8228-152">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="a8228-153">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8228-153">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a8228-154">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="a8228-154">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a8228-155">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a8228-155">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.EmployeeSales  
    ( BusinessEntityID   varchar(11) NOT NULL,  
      SalesYTD money NOT NULL  
    );  
    GO  
    INSERT INTO dbo.EmployeeSales  
        SELECT BusinessEntityID, SalesYTD   
        FROM Sales.SalesPerson;  
    GO  
    ```  
  
  
