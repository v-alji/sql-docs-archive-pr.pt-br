---
title: Exibir propriedades de estatísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.details.f1
helpviewer_keywords:
- viewing statistics properties
- statistics [SQL Server], viewing properties
ms.assetid: 0eaa2101-006e-4015-9979-3468b50e0aaa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63cabc5d8844982604993acac6a791317ee36925
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582351"
---
# <a name="view-statistics-properties"></a><span data-ttu-id="740ca-102">Exibir propriedades de estatísticas</span><span class="sxs-lookup"><span data-stu-id="740ca-102">View Statistics Properties</span></span>
  <span data-ttu-id="740ca-103">Você pode exibir estatísticas de otimização de consulta atuais para uma tabela ou exibição indexada no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="740ca-103">You can display current query optimization statistics for a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="740ca-104">Os objetos de estatísticas incluem um cabeçalho com metadados sobre as estatísticas, um histograma com a distribuição de valores na primeira coluna de chave do objeto de estatísticas e um vetor de densidade para medir a correlação entre colunas.</span><span class="sxs-lookup"><span data-stu-id="740ca-104">Statistics objects include a header with metadata about the statistics, a histogram with the distribution of values in the first key column of the statistics object, and a density vector to measure cross-column correlation.</span></span> <span data-ttu-id="740ca-105">Para obter mais informações sobre histogramas e vetores de densidade, consulte [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="740ca-105">For more information about histograms and density vectors, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span></span>  
  
 <span data-ttu-id="740ca-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="740ca-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="740ca-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="740ca-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="740ca-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="740ca-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="740ca-109">**Para exibir propriedades de estatísticas usando:**</span><span class="sxs-lookup"><span data-stu-id="740ca-109">**To view statistics properties, using:**</span></span>  
  
     [<span data-ttu-id="740ca-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="740ca-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="740ca-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="740ca-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="740ca-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="740ca-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="740ca-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="740ca-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="740ca-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="740ca-114">Permissions</span></span>  
 <span data-ttu-id="740ca-115">Para exibir o objeto de estatísticas, o usuário deve ser proprietário da tabela ou deve ser membro da função de servidor fixa `sysadmin` ou das funções de banco de dados fixas `db_owner` ou `db_ddladmin`.</span><span class="sxs-lookup"><span data-stu-id="740ca-115">In order to view the statistics object, the user must own the table or the user must be a member of the `sysadmin` fixed server role, the `db_owner` fixed database role, or the `db_ddladmin` fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="740ca-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="740ca-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="740ca-117">Para exibir propriedades de estatísticas</span><span class="sxs-lookup"><span data-stu-id="740ca-117">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="740ca-118">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o banco de dados no qual você deseja criar uma nova estatística.</span><span class="sxs-lookup"><span data-stu-id="740ca-118">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="740ca-119">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="740ca-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="740ca-120">Clique no sinal de adição para expandir a tabela na qual você deseja exibir as propriedades de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-120">Click the plus sign to expand the table in which you want to view the statistic's properties.</span></span>  
  
4.  <span data-ttu-id="740ca-121">Clique no sinal de adição para expandir a pasta **Estatísticas** .</span><span class="sxs-lookup"><span data-stu-id="740ca-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="740ca-122">Clique com o botão direito do mouse no objeto de Estatísticas do qual você deseja exibir as propriedades e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="740ca-122">Right-click the Statistics object of which you want to view the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="740ca-123">Na caixa de diálogo **Propriedades de Estatísticas –** _statistics_name_, no painel **Selecionar uma página**, selecione **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="740ca-123">In the **Statistics Properties -** _statistics_name_ dialog box, in the **Select a page** pane, select **Details**.</span></span>  
  
     <span data-ttu-id="740ca-124">As propriedades a seguir são mostradas na página **Detalhes** na caixa de diálogo **Propriedades de Estatísticas –** _statistics_name_.</span><span class="sxs-lookup"><span data-stu-id="740ca-124">The following properties show on the **Details** page in the **Statistics Properties -** _statistics_name_ dialog box.</span></span>  
  
     <span data-ttu-id="740ca-125">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="740ca-125">**Table Name**</span></span>  
     <span data-ttu-id="740ca-126">Exibe o nome da tabela descrito pelas estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-126">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="740ca-127">**Nome das Estatísticas**</span><span class="sxs-lookup"><span data-stu-id="740ca-127">**Statistics Name**</span></span>  
     <span data-ttu-id="740ca-128">Exibe o nome do objeto de banco de dados onde as estatísticas são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="740ca-128">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="740ca-129">**Estatísticas para INDEXstatistics_name**</span><span class="sxs-lookup"><span data-stu-id="740ca-129">**Statistics for INDEXstatistics_name**</span></span>  
     <span data-ttu-id="740ca-130">Esta caixa de texto mostra as propriedades retornadas do objeto de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-130">This text box shows the properties returned from the statistics object.</span></span> <span data-ttu-id="740ca-131">Essas propriedades são divididas em três seções: Cabeçalho de Estatísticas, Vetor de Densidade e Histograma.</span><span class="sxs-lookup"><span data-stu-id="740ca-131">This properties are divided into three sections: Stats Header, Density Vector, and Histogram.</span></span>  
  
     <span data-ttu-id="740ca-132">As informações a seguir descrevem as colunas retornadas no conjunto de resultados do Cabeçalho de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-132">The following information describes the columns returned in the result set for the Stats Header.</span></span>  
  
     <span data-ttu-id="740ca-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="740ca-133">**Name**</span></span>  
     <span data-ttu-id="740ca-134">O nome do objeto de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-134">Name of the statistics object.</span></span>  
  
     <span data-ttu-id="740ca-135">**Updated**</span><span class="sxs-lookup"><span data-stu-id="740ca-135">**Updated**</span></span>  
     <span data-ttu-id="740ca-136">Data e hora da última atualização de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-136">Date and time the statistics were last updated.</span></span>  
  
     <span data-ttu-id="740ca-137">**Linhas**</span><span class="sxs-lookup"><span data-stu-id="740ca-137">**Rows**</span></span>  
     <span data-ttu-id="740ca-138">O número total de linhas na tabela ou exibição indexada quando as estatísticas foram atualizadas pela última vez.</span><span class="sxs-lookup"><span data-stu-id="740ca-138">Total number of rows in the table or indexed view when the statistics were last updated.</span></span> <span data-ttu-id="740ca-139">Se as estatísticas forem filtradas ou corresponderem a um índice filtrado, o número de linhas talvez seja menor do que o número de linhas na tabela.</span><span class="sxs-lookup"><span data-stu-id="740ca-139">If the statistics are filtered or correspond to a filtered index, the number of rows might be less than the number of rows in the table.</span></span>  
  
     <span data-ttu-id="740ca-140">**Linhas Amostradas**</span><span class="sxs-lookup"><span data-stu-id="740ca-140">**Rows Sampled**</span></span>  
     <span data-ttu-id="740ca-141">O número total de linhas amostradas para cálculos de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-141">Total number of rows sampled for statistics calculations.</span></span> <span data-ttu-id="740ca-142">Se Linhas Amostradas < Linhas, o histograma e os resultados de densidade exibidos serão estimativas com base nas linhas amostradas.</span><span class="sxs-lookup"><span data-stu-id="740ca-142">If Rows Sampled < Rows, the displayed histogram and density results are estimates based on the sampled rows.</span></span>  
  
     <span data-ttu-id="740ca-143">**Etapas**</span><span class="sxs-lookup"><span data-stu-id="740ca-143">**Steps**</span></span>  
     <span data-ttu-id="740ca-144">O número de etapas no histograma.</span><span class="sxs-lookup"><span data-stu-id="740ca-144">Number of steps in the histogram.</span></span> <span data-ttu-id="740ca-145">Cada etapa abrange uma gama de valores de colunas seguidos por um valor de coluna associada superior.</span><span class="sxs-lookup"><span data-stu-id="740ca-145">Each step spans a range of column values followed by an upper bound column value.</span></span> <span data-ttu-id="740ca-146">As etapas do histograma são definidas na primeira coluna de chave nas estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-146">The histogram steps are defined on the first key column in the statistics.</span></span> <span data-ttu-id="740ca-147">O número máximo de etapas é 200.</span><span class="sxs-lookup"><span data-stu-id="740ca-147">The maximum number of steps is 200.</span></span>  
  
     <span data-ttu-id="740ca-148">**Densidade**</span><span class="sxs-lookup"><span data-stu-id="740ca-148">**Density**</span></span>  
     <span data-ttu-id="740ca-149">Calculado como 1 / *valores distintos* para todos os valores na primeira coluna de chave do objeto de estatísticas, excluindo os valores de limite de histograma.</span><span class="sxs-lookup"><span data-stu-id="740ca-149">Calculated as 1 / *distinct values* for all values in the first key column of the statistics object, excluding the histogram boundary values.</span></span> <span data-ttu-id="740ca-150">Esse valor de Densidade não é usado pelo otimizador de consulta e é exibido para fins de compatibilidade com versões anteriores ao SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="740ca-150">This Density value is not used by the query optimizer and is displayed for backward compatibility with versions before SQL Server 2008.</span></span>  
  
     <span data-ttu-id="740ca-151">**Comprimento Médio de Chave**</span><span class="sxs-lookup"><span data-stu-id="740ca-151">**Average Key Length**</span></span>  
     <span data-ttu-id="740ca-152">O número médio de bytes por valor para todas as colunas de chave do objeto de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-152">Average number of bytes per value for all of the key columns in the statistics object.</span></span>  
  
     <span data-ttu-id="740ca-153">**Índice de Cadeia de Caracteres**</span><span class="sxs-lookup"><span data-stu-id="740ca-153">**String Index**</span></span>  
     <span data-ttu-id="740ca-154">Sim indica que o objeto de estatísticas contém estatísticas do resumo da cadeia de caracteres para melhorar a estimativa de cardinalidade para predicados de consulta que usam o operador LIKE; por exemplo, `WHERE ProductName LIKE '%Bike'`.</span><span class="sxs-lookup"><span data-stu-id="740ca-154">Yes indicates the statistics object contains string summary statistics to improve the cardinality estimates for query predicates that use the LIKE operator; for example, `WHERE ProductName LIKE '%Bike'`.</span></span> <span data-ttu-id="740ca-155">As estatísticas de resumo da cadeia de caracteres são armazenadas separadamente do histograma e são criadas na primeira coluna de chave do objeto de estatísticas quando ele é do tipo **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)** , **nvarchar(max)** , **text**ou **ntext**.</span><span class="sxs-lookup"><span data-stu-id="740ca-155">String summary statistics are stored separately from the histogram and are created on the first key column of the statistics object when it is of type **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)**, **nvarchar(max)**, **text**, or **ntext**.</span></span>  
  
     <span data-ttu-id="740ca-156">**Expressão de filtro**</span><span class="sxs-lookup"><span data-stu-id="740ca-156">**Filter Expression**</span></span>  
     <span data-ttu-id="740ca-157">Predicado do subconjunto de linhas de tabela incluído no objeto de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="740ca-157">Predicate for the subset of table rows included in the statistics object.</span></span> <span data-ttu-id="740ca-158">NULL = estatísticas não filtradas.</span><span class="sxs-lookup"><span data-stu-id="740ca-158">NULL = non-filtered statistics.</span></span>  
  
     <span data-ttu-id="740ca-159">**Linhas não filtradas**</span><span class="sxs-lookup"><span data-stu-id="740ca-159">**Unfiltered Rows**</span></span>  
     <span data-ttu-id="740ca-160">O número total de linhas na tabela antes da aplicação da expressão de filtro.</span><span class="sxs-lookup"><span data-stu-id="740ca-160">Total number of rows in the table before applying the filter expression.</span></span> <span data-ttu-id="740ca-161">Se o valor da Expressão de Filtro for NULL, as Linhas Não Filtradas serão iguais a Linhas.</span><span class="sxs-lookup"><span data-stu-id="740ca-161">If Filter Expression is NULL, Unfiltered Rows is equal to Rows.</span></span>  
  
     <span data-ttu-id="740ca-162">As informações a seguir descrevem as colunas retornadas no conjunto de resultados do Vetor de Densidade.</span><span class="sxs-lookup"><span data-stu-id="740ca-162">The following information describes the columns returned in the result set for the Density Vector.</span></span>  
  
     <span data-ttu-id="740ca-163">**Toda Densidade**</span><span class="sxs-lookup"><span data-stu-id="740ca-163">**All Density**</span></span>  
     <span data-ttu-id="740ca-164">A densidade é 1 / *valores distintos*.</span><span class="sxs-lookup"><span data-stu-id="740ca-164">Density is 1 / *distinct values*.</span></span> <span data-ttu-id="740ca-165">Os resultados exibem a densidade de cada prefixo de colunas no objeto de estatísticas, uma linha por densidade.</span><span class="sxs-lookup"><span data-stu-id="740ca-165">Results display density for each prefix of columns in the statistics object, one row per density.</span></span> <span data-ttu-id="740ca-166">Um valor distinto é uma lista distinta dos valores de coluna por linha e por prefixo de colunas.</span><span class="sxs-lookup"><span data-stu-id="740ca-166">A distinct value is a distinct list of the column values per row and per columns prefix.</span></span> <span data-ttu-id="740ca-167">Por exemplo, se o objeto de estatísticas contiver colunas de chave (A, B, C), os resultados reportarão a densidade de listas distintas de valores em cada um desses prefixos de colunas: (A), (A,B) e (A, B, C).</span><span class="sxs-lookup"><span data-stu-id="740ca-167">For example, if the statistics object contains key columns (A, B, C), the results report the density of the distinct lists of values in each of these column prefixes: (A), (A,B), and (A, B, C).</span></span> <span data-ttu-id="740ca-168">Usando o prefixo (A, B, C), cada uma dessas listas é uma lista de valores distintos: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span><span class="sxs-lookup"><span data-stu-id="740ca-168">Using the prefix (A, B, C), each of these lists is a distinct value list: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span></span> <span data-ttu-id="740ca-169">Usando o prefixo (A, B), os mesmos valores de coluna têm estas listas de valores distintos: (3, 5), (4, 4) e (4, 5).</span><span class="sxs-lookup"><span data-stu-id="740ca-169">Using the prefix (A, B) the same column values have these distinct value lists: (3, 5), (4, 4), and (4, 5).</span></span>  
  
     <span data-ttu-id="740ca-170">**Comprimento Médio**</span><span class="sxs-lookup"><span data-stu-id="740ca-170">**Average Length**</span></span>  
     <span data-ttu-id="740ca-171">O comprimento médio, em bytes, para armazenar uma lista dos valores das colunas para o prefixo da coluna.</span><span class="sxs-lookup"><span data-stu-id="740ca-171">Average length, in bytes, to store a list of the column values for the column prefix.</span></span> <span data-ttu-id="740ca-172">Por exemplo, se os valores na lista (3, 5, 6) exigirem cada um 4 bytes, o comprimento será de 12 bytes.</span><span class="sxs-lookup"><span data-stu-id="740ca-172">For example, if the values in the list (3, 5, 6) each require 4 bytes the length is 12 bytes.</span></span>  
  
     <span data-ttu-id="740ca-173">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="740ca-173">**Columns**</span></span>  
     <span data-ttu-id="740ca-174">Os nomes das colunas no prefixo para o qual as opções Toda a densidade e Comprimento médio são exibidos.</span><span class="sxs-lookup"><span data-stu-id="740ca-174">Names of columns in the prefix for which All density and Average length are displayed.</span></span>  
  
     <span data-ttu-id="740ca-175">As informações a seguir descrevem as colunas retornadas no conjunto de resultados do Histograma.</span><span class="sxs-lookup"><span data-stu-id="740ca-175">The following information describes the columns returned in the result set for the Histogram.</span></span>  
  
     <span data-ttu-id="740ca-176">**RANGE_HI_KEY**</span><span class="sxs-lookup"><span data-stu-id="740ca-176">**RANGE_HI_KEY**</span></span>  
     <span data-ttu-id="740ca-177">Valor da coluna associada superior de uma etapa do histograma.</span><span class="sxs-lookup"><span data-stu-id="740ca-177">Upper bound column value for a histogram step.</span></span> <span data-ttu-id="740ca-178">O valor da coluna também será denominado um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="740ca-178">The column value is also called a key value.</span></span>  
  
     <span data-ttu-id="740ca-179">**RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="740ca-179">**RANGE_ROWS**</span></span>  
     <span data-ttu-id="740ca-180">Número estimado de linhas cujo valor de coluna fica dentro de uma etapa do histograma, excluindo-se o limite superior.</span><span class="sxs-lookup"><span data-stu-id="740ca-180">Estimated number of rows whose column value falls within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="740ca-181">**EQ_ROWS**</span><span class="sxs-lookup"><span data-stu-id="740ca-181">**EQ_ROWS**</span></span>  
     <span data-ttu-id="740ca-182">Número estimado de linhas cujo valor de coluna é igual ao limite superior da etapa do histograma.</span><span class="sxs-lookup"><span data-stu-id="740ca-182">Estimated number of rows whose column value equals the upper bound of the histogram step.</span></span>  
  
     <span data-ttu-id="740ca-183">**DISTINCT_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="740ca-183">**DISTINCT_RANGE_ROWS**</span></span>  
     <span data-ttu-id="740ca-184">Número estimado de linhas com um valor de coluna distinto dentro de uma etapa do histograma, excluindo-se o limite superior.</span><span class="sxs-lookup"><span data-stu-id="740ca-184">Estimated number of rows with a distinct column value within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="740ca-185">**AVG_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="740ca-185">**AVG_RANGE_ROWS**</span></span>  
     <span data-ttu-id="740ca-186">Número médio de linhas com valores de colunas duplicados em uma etapa do histograma, excluindo o limite superior (RANGE_ROWS / DISTINCT_RANGE_ROWS para DISTINCT_RANGE_ROWS > 0).</span><span class="sxs-lookup"><span data-stu-id="740ca-186">Average number of rows with duplicate column values within a histogram step, excluding the upper bound (RANGE_ROWS / DISTINCT_RANGE_ROWS for DISTINCT_RANGE_ROWS > 0).</span></span>  
  
7.  <span data-ttu-id="740ca-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="740ca-187">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="740ca-188">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="740ca-188">Using Transact-SQL</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="740ca-189">Para exibir propriedades de estatísticas</span><span class="sxs-lookup"><span data-stu-id="740ca-189">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="740ca-190">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="740ca-190">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="740ca-191">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="740ca-191">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="740ca-192">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="740ca-192">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example displays all statistics information for the AK_Address_rowguid index of the Person.Address table.   
    DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid);   
    GO  
    ```  
  
 <span data-ttu-id="740ca-193">Para obter mais informações, veja [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="740ca-193">For more information, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span></span>  
  
#### <a name="to-find-all-of-the-statistics-on-a-table-or-view"></a><span data-ttu-id="740ca-194">Para localizar todas as estatísticas em uma tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="740ca-194">To find all of the statistics on a table or view</span></span>  
  
1.  <span data-ttu-id="740ca-195">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="740ca-195">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="740ca-196">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="740ca-196">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="740ca-197">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="740ca-197">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Gets the following information: name and ID of the statistics, whether the statistics were created automatically or by the user, whether the statistics were created with the NORECOMPUTE option, and whether the statistics have a filter and, if so, what that filter is.  
    */  
    SELECT name AS statistics_name  
        ,stats_id  
        ,auto_created  
        ,user_created  
        ,no_recompute  
        ,has_filter  
        ,filter_definition  
    -- using the sys.stats catalog view  
    FROM sys.stats  
    -- for the Sales.SpecialOffer table  
    WHERE object_id = OBJECT_ID('Sales.SpecialOffer');  
    GO  
    ```  
  
 <span data-ttu-id="740ca-198">Para obter mais informações, veja [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="740ca-198">For more information, see [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span></span>  
  
  
