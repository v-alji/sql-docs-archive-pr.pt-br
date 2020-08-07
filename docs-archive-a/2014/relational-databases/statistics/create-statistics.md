---
title: Criar estatísticas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.propertis.f1
- sql12.swb.statistics.filter.f1
- sql12.swb.stat.properties.f1
- sql12.swb.stat.columns.f1
helpviewer_keywords:
- creating statistics
- statistics [SQL Server], creating
ms.assetid: 95a455fb-664d-4c95-851e-c6b62d7ebe04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 230bd4d840c3d59dc1267dd6801754b68386cb32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582365"
---
# <a name="create-statistics"></a><span data-ttu-id="1c84c-102">Criar estatísticas</span><span class="sxs-lookup"><span data-stu-id="1c84c-102">Create Statistics</span></span>
  <span data-ttu-id="1c84c-103">Você pode criar estatísticas de otimização de consulta em uma ou mais colunas de uma tabela ou exibição indexada no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c84c-103">You can create query optimization statistics on one or more columns of a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1c84c-104">Para a maioria das consultas, o otimizador de consulta já gera as estatísticas necessárias para um plano de consulta de alta qualidade; em alguns casos, é necessário criar estatísticas adicionais.</span><span class="sxs-lookup"><span data-stu-id="1c84c-104">For most queries, the query optimizer already generates the necessary statistics for a high-quality query plan; in a few cases, you need to create additional statistics.</span></span>  
  
 <span data-ttu-id="1c84c-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="1c84c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1c84c-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="1c84c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1c84c-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="1c84c-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1c84c-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="1c84c-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1c84c-109">**Para criar estatísticas usando:**</span><span class="sxs-lookup"><span data-stu-id="1c84c-109">**To create statistics, using:**</span></span>  
  
     [<span data-ttu-id="1c84c-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c84c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1c84c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c84c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1c84c-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1c84c-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1c84c-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="1c84c-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1c84c-114">Antes de criar estatísticas com a instrução de CREATE STATISTICS, verifique se a opção AUTO_CREATE_STATISTICS está definida no nível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1c84c-114">Before creating statistics with the CREATE STATISTICS statement, verify that the AUTO_CREATE_STATISTICS option is set at the database level.</span></span> <span data-ttu-id="1c84c-115">Isso assegurará que o otimizador de consulta continue criando rotineiramente estatísticas de coluna única para colunas de predicado de consulta.</span><span class="sxs-lookup"><span data-stu-id="1c84c-115">This will ensure that the query optimizer continues to routinely create single-column statistics for query predicate columns.</span></span>  
  
-   <span data-ttu-id="1c84c-116">Você pode listar até 32 colunas por objeto de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-116">You can list up to 32 columns per statistics object.</span></span>  
  
-   <span data-ttu-id="1c84c-117">Não é possível descartar, renomear ou alterar a definição de uma coluna de tabela definida em um predicado de estatísticas filtrado.</span><span class="sxs-lookup"><span data-stu-id="1c84c-117">You cannot drop, rename, or alter the definition of a table column that is defined in a filtered statistics predicate.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1c84c-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="1c84c-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1c84c-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="1c84c-119">Permissions</span></span>  
 <span data-ttu-id="1c84c-120">exige que o usuário seja o proprietário da tabela ou exibição indexada ou um membro de uma das seguintes funções: função de servidor fixa **sysadmin** , função de banco de dados fixa **db_owner** ou função de banco de dados fixa **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="1c84c-120">Requires that the user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1c84c-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c84c-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="1c84c-122">Para criar estatísticas</span><span class="sxs-lookup"><span data-stu-id="1c84c-122">To create statistics</span></span>  
  
1.  <span data-ttu-id="1c84c-123">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o banco de dados no qual você deseja criar uma nova estatística.</span><span class="sxs-lookup"><span data-stu-id="1c84c-123">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="1c84c-124">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="1c84c-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="1c84c-125">Clique no sinal de adição ao lado da tabela na qual você deseja criar uma nova estatística.</span><span class="sxs-lookup"><span data-stu-id="1c84c-125">Click the plus sign to expand the table in which you want to create a new statistic.</span></span>  
  
4.  <span data-ttu-id="1c84c-126">Clique com o botão direito do mouse na pasta **Estatísticas** e selecione **Novas Estatísticas...** .</span><span class="sxs-lookup"><span data-stu-id="1c84c-126">Right-click the **Statistics** folder and select **New Statistics...**.</span></span>  
  
     <span data-ttu-id="1c84c-127">As propriedades a seguir são exibidas na página **geral** na caixa de diálogo **novas estatísticas na tabela**_table_name_ .</span><span class="sxs-lookup"><span data-stu-id="1c84c-127">The following properties show on the **General** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="1c84c-128">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="1c84c-128">**Table Name**</span></span>  
     <span data-ttu-id="1c84c-129">Exibe o nome da tabela descrito pelas estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-129">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="1c84c-130">**Nome das Estatísticas**</span><span class="sxs-lookup"><span data-stu-id="1c84c-130">**Statistics Name**</span></span>  
     <span data-ttu-id="1c84c-131">Exibe o nome do objeto de banco de dados onde as estatísticas são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-131">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="1c84c-132">**Colunas de Estatísticas**</span><span class="sxs-lookup"><span data-stu-id="1c84c-132">**Statistics Columns**</span></span>  
     <span data-ttu-id="1c84c-133">Essa grade mostra as colunas descritas por esse conjunto de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-133">This grid shows the columns described by this set of statistics.</span></span> <span data-ttu-id="1c84c-134">Todos os valores na grade são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="1c84c-134">All values in the grid are read-only.</span></span>  
  
     <span data-ttu-id="1c84c-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1c84c-135">**Name**</span></span>  
     <span data-ttu-id="1c84c-136">Exibe o nome da coluna descrito pelas estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-136">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="1c84c-137">Esse pode ser uma única coluna ou uma combinação de colunas em uma única tabela.</span><span class="sxs-lookup"><span data-stu-id="1c84c-137">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="1c84c-138">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="1c84c-138">**Data Type**</span></span>  
     <span data-ttu-id="1c84c-139">Indica o tipo de dados das colunas descritas pelas estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-139">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="1c84c-140">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="1c84c-140">**Size**</span></span>  
     <span data-ttu-id="1c84c-141">Exibe o tamanho do tipo de dados para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="1c84c-141">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="1c84c-142">**Identidade**</span><span class="sxs-lookup"><span data-stu-id="1c84c-142">**Identity**</span></span>  
     <span data-ttu-id="1c84c-143">Indica uma coluna de identidade quando é verificado.</span><span class="sxs-lookup"><span data-stu-id="1c84c-143">Indicates an identity column when it is checked.</span></span>  
  
     <span data-ttu-id="1c84c-144">**Permitir Nulos**</span><span class="sxs-lookup"><span data-stu-id="1c84c-144">**Allow Nulls**</span></span>  
     <span data-ttu-id="1c84c-145">Indica se a coluna aceita valores nulos.</span><span class="sxs-lookup"><span data-stu-id="1c84c-145">Indicates whether the column accepts NULL values.</span></span>  
  
     <span data-ttu-id="1c84c-146">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="1c84c-146">**Add**</span></span>  
     <span data-ttu-id="1c84c-147">Adiciona colunas da tabela à grade de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-147">Add additional columns from the table to the statistics grid.</span></span>  
  
     <span data-ttu-id="1c84c-148">**Remover**</span><span class="sxs-lookup"><span data-stu-id="1c84c-148">**Remove**</span></span>  
     <span data-ttu-id="1c84c-149">Remove a coluna selecionada da grade de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-149">Remove the selected column from the statistics grid.</span></span>  
  
     <span data-ttu-id="1c84c-150">**Mover para Cima**</span><span class="sxs-lookup"><span data-stu-id="1c84c-150">**Move Up**</span></span>  
     <span data-ttu-id="1c84c-151">Move a coluna selecionada para um local anterior na grade de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-151">Move the selected column to an earlier location in the statistics grid.</span></span> <span data-ttu-id="1c84c-152">O local na grade pode ter um impacto significativo na utilidade das estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-152">The location in the grid can substantially impact the usefulness of the statistics.</span></span>  
  
     <span data-ttu-id="1c84c-153">**Mover para Baixo**</span><span class="sxs-lookup"><span data-stu-id="1c84c-153">**Move Down**</span></span>  
     <span data-ttu-id="1c84c-154">Move a coluna selecionada a um local posterior na grade de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-154">Move the selected column to a later location in the statistics grid.</span></span>  
  
     <span data-ttu-id="1c84c-155">**Estatísticas para essas colunas foram atualizadas por último:**</span><span class="sxs-lookup"><span data-stu-id="1c84c-155">**Statistics for these columns were last updated:**</span></span>  
     <span data-ttu-id="1c84c-156">Indica a idade das estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-156">Indicates how old the statistics are.</span></span> <span data-ttu-id="1c84c-157">As estatísticas são mais valiosas quando são atuais.</span><span class="sxs-lookup"><span data-stu-id="1c84c-157">Statistics are more valuable when they are current.</span></span> <span data-ttu-id="1c84c-158">Atualize as estatísticas depois de grandes alterações nos dados ou depois de adicionar dados atípicos.</span><span class="sxs-lookup"><span data-stu-id="1c84c-158">Update statistics after large changes to the data or after adding atypical data.</span></span> <span data-ttu-id="1c84c-159">As estatísticas para tabelas que têm uma distribuição consistente de dados precisam ser atualizadas com menos frequência.</span><span class="sxs-lookup"><span data-stu-id="1c84c-159">Statistics for tables that have a consistent distribution of data need to be updated less frequently.</span></span>  
  
     <span data-ttu-id="1c84c-160">**Atualize estatísticas para essas colunas**</span><span class="sxs-lookup"><span data-stu-id="1c84c-160">**Update statistics for these columns**</span></span>  
     <span data-ttu-id="1c84c-161">Verifique para atualizar as estatísticas quando a caixa de diálogo estiver fechada.</span><span class="sxs-lookup"><span data-stu-id="1c84c-161">Check to update the statistics when the dialog box is closed.</span></span>  
  
     <span data-ttu-id="1c84c-162">A propriedade a seguir é mostrada na página **filtro** na caixa de diálogo **novas estatísticas na tabela**_table_name_ .</span><span class="sxs-lookup"><span data-stu-id="1c84c-162">The following property shows on the **Filter** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="1c84c-163">**Expressão de filtro**</span><span class="sxs-lookup"><span data-stu-id="1c84c-163">**Filter Expression**</span></span>  
     <span data-ttu-id="1c84c-164">Define quais linhas de dados devem ser incluídas nas estatísticas filtradas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-164">Defines which data rows to include in the filtered statistics.</span></span> <span data-ttu-id="1c84c-165">Por exemplo, `Production.ProductSubcategoryID IN ( 1,2,3 )`</span><span class="sxs-lookup"><span data-stu-id="1c84c-165">For example, `Production.ProductSubcategoryID IN ( 1,2,3 )`</span></span>  
  
5.  <span data-ttu-id="1c84c-166">Na caixa de diálogo **novas estatísticas na tabela**_table_name_ , na página **geral** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1c84c-166">In the **New Statistics on Table**_table_name_ dialog box, on the **General** page, click **Add**.</span></span>  
  
     <span data-ttu-id="1c84c-167">As propriedades a seguir aparecem na caixa de diálogo **Selecionar Colunas** .</span><span class="sxs-lookup"><span data-stu-id="1c84c-167">The following properties show in the **Select Columns** dialog box.</span></span> <span data-ttu-id="1c84c-168">Essas informações são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="1c84c-168">This information is read-only.</span></span>  
  
     <span data-ttu-id="1c84c-169">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1c84c-169">**Name**</span></span>  
     <span data-ttu-id="1c84c-170">Exibe o nome da coluna descrito pelas estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-170">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="1c84c-171">Esse pode ser uma única coluna ou uma combinação de colunas em uma única tabela.</span><span class="sxs-lookup"><span data-stu-id="1c84c-171">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="1c84c-172">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="1c84c-172">**Data Type**</span></span>  
     <span data-ttu-id="1c84c-173">Indica o tipo de dados das colunas descritas pelas estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c84c-173">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="1c84c-174">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="1c84c-174">**Size**</span></span>  
     <span data-ttu-id="1c84c-175">Exibe o tamanho do tipo de dados para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="1c84c-175">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="1c84c-176">**Identidade**</span><span class="sxs-lookup"><span data-stu-id="1c84c-176">**Identity**</span></span>  
     <span data-ttu-id="1c84c-177">Indica uma coluna de identidade quando marcado.</span><span class="sxs-lookup"><span data-stu-id="1c84c-177">Indicates an identity column when checked.</span></span>  
  
     <span data-ttu-id="1c84c-178">**Permitir Nulos**</span><span class="sxs-lookup"><span data-stu-id="1c84c-178">**Allow NULLs**</span></span>  
     <span data-ttu-id="1c84c-179">Indica se a coluna aceita valores nulos.</span><span class="sxs-lookup"><span data-stu-id="1c84c-179">Indicates whether the column accepts NULL values.</span></span>  
  
6.  <span data-ttu-id="1c84c-180">Na caixa de diálogo **Selecionar Colunas** , marque as caixas de seleção de cada coluna para as quais você deseja criar uma estatística e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c84c-180">In the **Select Columns** dialog box, select the check box or check boxes of each column for which you want to create a statistic and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="1c84c-181">Na caixa de diálogo **novas estatísticas na tabela**_table_name_ , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c84c-181">In the **New Statistics on Table**_table_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1c84c-182">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c84c-182">Using Transact-SQL</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="1c84c-183">Para criar estatísticas</span><span class="sxs-lookup"><span data-stu-id="1c84c-183">To create statistics</span></span>  
  
1.  <span data-ttu-id="1c84c-184">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c84c-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1c84c-185">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="1c84c-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1c84c-186">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1c84c-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Create new statistic object called ContactMail1  
    -- on the BusinessEntityID and EmailPromotion columns in the Person.Person table.   
  
    CREATE STATISTICS ContactMail1  
        ON Person.Person (BusinessEntityID, EmailPromotion);   
    GO  
    ```  
  
4.  <span data-ttu-id="1c84c-187">A estatística criada acima potencialmente melhora os resultados para a consulta seguinte.</span><span class="sxs-lookup"><span data-stu-id="1c84c-187">The statistic created above potentially improves the results for the following query.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT LastName, FirstName  
    FROM Person.Person  
    WHERE EmailPromotion = 2  
    ORDER BY LastName, FirstName;   
    GO  
    ```  
  
 <span data-ttu-id="1c84c-188">Para obter mais informações, veja [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1c84c-188">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
