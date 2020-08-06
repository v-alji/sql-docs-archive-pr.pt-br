---
title: Usar conjuntos de colunas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- sparse columns, column sets
- column sets
ms.assetid: a4f9de95-dc8f-4ad8-b957-137e32bfa500
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cb496137c3986b78a55862e434c153d354a42ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583455"
---
# <a name="use-column-sets"></a><span data-ttu-id="0477d-102">Usar conjuntos de colunas</span><span class="sxs-lookup"><span data-stu-id="0477d-102">Use Column Sets</span></span>
  <span data-ttu-id="0477d-103">As tabelas que usam colunas esparsas podem designar um conjunto de colunas para retornar todas as colunas esparsas na tabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-103">Tables that use sparse columns can designate a column set to return all sparse columns in the table.</span></span> <span data-ttu-id="0477d-104">Um conjunto de colunas é uma representação em XML sem-tipo que combina todas as colunas esparsas de uma tabela em uma saída estruturada.</span><span class="sxs-lookup"><span data-stu-id="0477d-104">A column set is an untyped XML representation that combines all the sparse columns of a table into a structured output.</span></span> <span data-ttu-id="0477d-105">Um conjunto de colunas é como uma coluna calculada em que o conjunto de colunas não é fisicamente armazenado na tabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-105">A column set is like a calculated column in that the column set is not physically stored in the table.</span></span> <span data-ttu-id="0477d-106">Um conjunto de colunas difere de uma coluna calculada em que o conjunto de colunas é diretamente atualizável.</span><span class="sxs-lookup"><span data-stu-id="0477d-106">A column set differs from a calculated column in that the column set is directly updatable.</span></span>  
  
 <span data-ttu-id="0477d-107">Considere o uso de conjuntos de colunas quando o número de colunas em uma tabela for grande e trabalhar nelas individualmente for difícil.</span><span class="sxs-lookup"><span data-stu-id="0477d-107">You should consider using column sets when the number of columns in a table is large, and operating on them individually is cumbersome.</span></span> <span data-ttu-id="0477d-108">Os aplicativos devem observar alguma melhoria no desempenho quando selecionam e inserem dados usando conjuntos de colunas em tabelas com muitas colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-108">Applications might see some performance improvement when they select and insert data by using column sets on tables that have lots of columns.</span></span> <span data-ttu-id="0477d-109">Entretanto, o desempenho de conjuntos de colunas pode ser reduzido quando muitos índices são definidos nas colunas das tabelas.</span><span class="sxs-lookup"><span data-stu-id="0477d-109">However, the performance of column sets can be reduced when many indexes are defined on the columns in the table.</span></span> <span data-ttu-id="0477d-110">Isso porque a quantidade de memória necessária para um plano de execução aumenta.</span><span class="sxs-lookup"><span data-stu-id="0477d-110">This is because the amount of memory that is required for an execution plan increases.</span></span>  
  
 <span data-ttu-id="0477d-111">Para definir um conjunto de colunas, use as palavras-chave *<column_set_name>* FOR ALL_SPARSE_COLUMNS nas instruções [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) ou [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0477d-111">To define a column set, use the *<column_set_name>* FOR ALL_SPARSE_COLUMNS keywords in the[CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) or [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) statements.</span></span>  
  
## <a name="guidelines-for-using-column-sets"></a><span data-ttu-id="0477d-112">Diretrizes para usar conjuntos de colunas</span><span class="sxs-lookup"><span data-stu-id="0477d-112">Guidelines for Using Column Sets</span></span>  
 <span data-ttu-id="0477d-113">Ao usar conjuntos de colunas, considere as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="0477d-113">When you use column sets, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="0477d-114">Colunas esparsas e um conjunto de colunas podem ser adicionados como parte da mesma instrução.</span><span class="sxs-lookup"><span data-stu-id="0477d-114">Sparse columns and a column set can be added as part of the same statement.</span></span>  
  
-   <span data-ttu-id="0477d-115">O conjunto de colunas não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="0477d-115">The column set cannot be changed.</span></span> <span data-ttu-id="0477d-116">Para alterar um conjunto de colunas, ele deve ser excluído e recriado.</span><span class="sxs-lookup"><span data-stu-id="0477d-116">To change a column set, you must delete and re-create the column set.</span></span>  
  
-   <span data-ttu-id="0477d-117">Um conjunto de colunas não poderá ser adicionado a uma tabela se ela já contiver colunas esparsas.</span><span class="sxs-lookup"><span data-stu-id="0477d-117">A column set cannot be added to a table if that table already contains sparse columns.</span></span>  
  
-   <span data-ttu-id="0477d-118">Um conjunto de colunas pode ser adicionado a uma tabela que não inclui colunas esparsas.</span><span class="sxs-lookup"><span data-stu-id="0477d-118">A column set can be added to a table that does not include any sparse columns.</span></span> <span data-ttu-id="0477d-119">Se, posteriormente, forem adicionadas colunas esparsas à tabela, elas serão exibidas no conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-119">If sparse columns are later added to the table, they will appear in the column set.</span></span>  
  
-   <span data-ttu-id="0477d-120">Somente um conjunto de colunas é permitido por tabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-120">Only one column set is allowed per table.</span></span>  
  
-   <span data-ttu-id="0477d-121">Um conjunto de colunas é opcional e não é exigido para usar colunas esparsas.</span><span class="sxs-lookup"><span data-stu-id="0477d-121">A column set is optional and is not required to use sparse columns.</span></span>  
  
-   <span data-ttu-id="0477d-122">Restrições ou valores padrão não podem ser definidos em um conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-122">Constraints or default values cannot be defined on a column set.</span></span>  
  
-   <span data-ttu-id="0477d-123">Colunas computadas não podem conter colunas de conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-123">Computed columns cannot contain column set columns.</span></span>  
  
-   <span data-ttu-id="0477d-124">Consultas distribuídas não têm suporte em tabelas que contêm conjuntos de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-124">Distributed queries are not supported on tables that contain column sets.</span></span>  
  
-   <span data-ttu-id="0477d-125">Replicação não oferece suporte a conjuntos de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-125">Replication does not support column sets.</span></span>  
  
-   <span data-ttu-id="0477d-126">Change data capture não oferece suporte a conjuntos de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-126">Change data capture does not support column sets.</span></span>  
  
-   <span data-ttu-id="0477d-127">Um conjunto de colunas não pode fazer parte de nenhum tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="0477d-127">A column set cannot be part of any kind of index.</span></span> <span data-ttu-id="0477d-128">Incluindo índices XML, índices de texto completo e exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="0477d-128">This includes XML indexes, full-text indexes, and indexed views.</span></span> <span data-ttu-id="0477d-129">Um conjunto de colunas não pode ser adicionado como uma coluna incluída em qualquer índice.</span><span class="sxs-lookup"><span data-stu-id="0477d-129">A column set cannot be added as an included column in any index.</span></span>  
  
-   <span data-ttu-id="0477d-130">Um conjunto de colunas não pode ser usado na expressão de filtro de um índice filtrado ou estatísticas filtradas.</span><span class="sxs-lookup"><span data-stu-id="0477d-130">A column set cannot be used in the filter expression of a filtered index or filtered statistics.</span></span>  
  
-   <span data-ttu-id="0477d-131">Quando uma exibição inclui um conjunto de colunas, ele é exibido na exibição como uma coluna XML.</span><span class="sxs-lookup"><span data-stu-id="0477d-131">When a view includes a column set, the column set appears in the view as an XML column.</span></span>  
  
-   <span data-ttu-id="0477d-132">Um conjunto de colunas não pode ser incluído em uma definição de exibição indexada.</span><span class="sxs-lookup"><span data-stu-id="0477d-132">A column set cannot be included in an indexed view definition.</span></span>  
  
-   <span data-ttu-id="0477d-133">Exibições particionadas que incluem tabelas com conjuntos de colunas são atualizáveis quando a exibição particionada especifica as colunas esparsas por nome.</span><span class="sxs-lookup"><span data-stu-id="0477d-133">Partitioned views that include tables that contain column sets are updatable when the partitioned view specifies the sparse columns by name.</span></span> <span data-ttu-id="0477d-134">Uma exibição particionada não é atualizável quando referencia o conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-134">A partitioned view is not updatable when it references the column set.</span></span>  
  
-   <span data-ttu-id="0477d-135">Notificações de consulta referentes a conjuntos de colunas não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="0477d-135">Query notifications that refer to column sets are not permitted.</span></span>  
  
-   <span data-ttu-id="0477d-136">Dados XML têm um limite de tamanho de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="0477d-136">XML data has a size limit of 2 GB.</span></span> <span data-ttu-id="0477d-137">Se os dados combinados de todas as colunas esparsas não nulas em uma linha excederem esse limite, a operação de consulta ou DML produzirá um erro.</span><span class="sxs-lookup"><span data-stu-id="0477d-137">If the combined data of all the nonnull sparse columns in a row exceeds this limit, the query or DML operation will produce an error.</span></span>  
  
-   <span data-ttu-id="0477d-138">Para obter informações sobre os dados retornados pela função COLUMNS_UPDATED, veja [Usar colunas esparsas](use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="0477d-138">For information about the data that is returned by the COLUMNS_UPDATED function, see [Use Sparse Columns](use-sparse-columns.md).</span></span>  
  
## <a name="guidelines-for-selecting-data-from-a-column-set"></a><span data-ttu-id="0477d-139">Diretrizes para selecionar dados de um conjunto de colunas</span><span class="sxs-lookup"><span data-stu-id="0477d-139">Guidelines for Selecting Data from a Column Set</span></span>  
 <span data-ttu-id="0477d-140">Considere as seguintes diretrizes para selecionar dados de um conjunto de colunas:</span><span class="sxs-lookup"><span data-stu-id="0477d-140">Consider the following guidelines for selecting data from a column set:</span></span>  
  
-   <span data-ttu-id="0477d-141">Conceitualmente, um conjunto de colunas é um tipo coluna XML computada, atualizável, que agrega um conjunto de colunas relacionais subjacentes em uma representação XML única.</span><span class="sxs-lookup"><span data-stu-id="0477d-141">Conceptually, a column set is a type of updatable, computed XML column that aggregates a set of underlying relational columns into a single XML representation.</span></span> <span data-ttu-id="0477d-142">O conjunto de colunas só oferece suporte à propriedade ALL_SPARSE_COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="0477d-142">The column set only supports the ALL_SPARSE_COLUMNS property.</span></span> <span data-ttu-id="0477d-143">Essa propriedade é usada para agregar todos os valores não nulos de todas as colunas esparsas para uma linha específica.</span><span class="sxs-lookup"><span data-stu-id="0477d-143">This property is used to aggregate all nonnull values from all sparse columns for a particular row.</span></span>  
  
-   <span data-ttu-id="0477d-144">No editor de tabela do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] os conjuntos de colunas são exibidos como um campo XML editável.</span><span class="sxs-lookup"><span data-stu-id="0477d-144">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] table editor, column sets are displayed as an editable XML field.</span></span> <span data-ttu-id="0477d-145">Defina os conjuntos de colunas no formato:</span><span class="sxs-lookup"><span data-stu-id="0477d-145">Define column sets in the format:</span></span>  
  
    ```  
    <column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...  
    ```  
  
     <span data-ttu-id="0477d-146">Exemplos de conjuntos de colunas:</span><span class="sxs-lookup"><span data-stu-id="0477d-146">Examples of column set values are as follows:</span></span>  
  
    -   `<sparseProp1>10</sparseProp1><sparseProp3>20</sparseProp3>`  
  
    -   `<DocTitle>Bicycle Parts List</DocTitle><Region>West</Region>`  
  
-   <span data-ttu-id="0477d-147">Colunas esparsas que contêm valores nulos são omitidas da representação XML do conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-147">Sparse columns that contain null values are omitted from the XML representation for the column set.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0477d-148">A adição de um conjunto de colunas altera o comportamento de consultas SELECT \*.</span><span class="sxs-lookup"><span data-stu-id="0477d-148">Adding a column set changes the behavior of SELECT \* queries.</span></span> <span data-ttu-id="0477d-149">A consulta retornará o conjunto de colunas como uma coluna XML e não retornará as colunas esparsas individuais.</span><span class="sxs-lookup"><span data-stu-id="0477d-149">The query will return the column set as an XML column and not return the individual sparse columns.</span></span> <span data-ttu-id="0477d-150">Designers de esquema e desenvolvedores de software devem ter cuidado para não violar aplicativos existentes.</span><span class="sxs-lookup"><span data-stu-id="0477d-150">Schema designers and software developers must be careful not to break existing applications.</span></span>  
  
## <a name="inserting-or-modifying-data-in-a-column-set"></a><span data-ttu-id="0477d-151">Inserindo ou modificando dados em um conjunto de colunas</span><span class="sxs-lookup"><span data-stu-id="0477d-151">Inserting or Modifying Data in a Column Set</span></span>  
 <span data-ttu-id="0477d-152">A manipulação de dados de uma coluna esparsa pode ser executada usando o nome de colunas individuais ou referenciando o nome do conjunto de colunas e especificando seus valores usando o formato XML do conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-152">Data manipulation of a sparse column can be performed by using the name of the individual columns, or by referencing the name of the column set and specifying the values of the column set by using the XML format of the column set.</span></span> <span data-ttu-id="0477d-153">As colunas esparsas podem ser exibidas em qualquer ordem na coluna XML.</span><span class="sxs-lookup"><span data-stu-id="0477d-153">Sparse columns can appear in any order in the XML column.</span></span>  
  
 <span data-ttu-id="0477d-154">Quando os valores de colunas esparsas são inseridos ou atualizados usando o conjunto de colunas XML, os valores inseridos nas colunas esparsas subjacentes são implicitamente convertidos do tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="0477d-154">When sparse column values are inserted or updated by using the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="0477d-155">No caso de colunas numéricas, um valor em branco no XML para a coluna numérica é convertido em uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="0477d-155">In the case of numeric columns, a blank value in the XML for the numeric column converts to an empty string.</span></span> <span data-ttu-id="0477d-156">Isso faz com que um zero seja inserido na coluna numérica, como mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="0477d-156">This causes a zero to be inserted into the numeric column as shown in the following example.</span></span>  
  
```  
CREATE TABLE t (i int SPARSE, cs xml column_set FOR ALL_SPARSE_COLUMNS);  
GO  
INSERT t(cs) VALUES ('<i/>');  
GO  
SELECT i FROM t;  
GO  
```  
  
 <span data-ttu-id="0477d-157">Nesse exemplo, nenhum valor foi especificado para a coluna `i`, mas o valor `0` foi inserido.</span><span class="sxs-lookup"><span data-stu-id="0477d-157">In this example, no value was specified for the column `i`, but the value `0` was inserted.</span></span>  
  
## <a name="using-the-sql_variant-data-type"></a><span data-ttu-id="0477d-158">Usando o tipo de dados sql_variant</span><span class="sxs-lookup"><span data-stu-id="0477d-158">Using the sql_variant Data Type</span></span>  
 <span data-ttu-id="0477d-159">O tipo de dados `sql_variant` pode armazenar vários tipos de dados diferentes, como `int`, `char` e `date`.</span><span class="sxs-lookup"><span data-stu-id="0477d-159">The `sql_variant` date type can store multiple different data types, such as `int`, `char`, and `date`.</span></span> <span data-ttu-id="0477d-160">Os conjuntos de colunas geram informações de tipo de dados como escala, precisão e informações de localidade que são associadas a um valor `sql_variant` como atributo na coluna XML gerada.</span><span class="sxs-lookup"><span data-stu-id="0477d-160">Column sets output the data type information such as scale, precision, and locale information that is associated with a `sql_variant` value as attributes in the generated XML column.</span></span> <span data-ttu-id="0477d-161">Se você tentar fornecer esses atributos em uma instrução XML personalizada como uma entrada para uma operação de inserção ou atualização em um conjunto de colunas, alguns desses atributos serão exigidos e a outros será atribuído um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="0477d-161">If you try to provide these attributes in a custom-generated XML statement as an input for an insert or update operation on a column set, some of these attributes are required and some of them are assigned a default value.</span></span> <span data-ttu-id="0477d-162">A tabela a seguir lista os tipos de dados e os valores padrão que o servidor gera quando o valor não é fornecido.</span><span class="sxs-lookup"><span data-stu-id="0477d-162">The following table lists the data types and the default values that the server generates when the value is not provided.</span></span>  
  
|<span data-ttu-id="0477d-163">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0477d-163">Data type</span></span>|<span data-ttu-id="0477d-164">localeID\*</span><span class="sxs-lookup"><span data-stu-id="0477d-164">localeID\*</span></span>|<span data-ttu-id="0477d-165">sqlCompareOptions</span><span class="sxs-lookup"><span data-stu-id="0477d-165">sqlCompareOptions</span></span>|<span data-ttu-id="0477d-166">sqlCollationVersion</span><span class="sxs-lookup"><span data-stu-id="0477d-166">sqlCollationVersion</span></span>|<span data-ttu-id="0477d-167">SqlSortId</span><span class="sxs-lookup"><span data-stu-id="0477d-167">SqlSortId</span></span>|<span data-ttu-id="0477d-168">Comprimento máximo</span><span class="sxs-lookup"><span data-stu-id="0477d-168">Maximum length</span></span>|<span data-ttu-id="0477d-169">Precisão</span><span class="sxs-lookup"><span data-stu-id="0477d-169">Precision</span></span>|<span data-ttu-id="0477d-170">Escala</span><span class="sxs-lookup"><span data-stu-id="0477d-170">Scale</span></span>|  
|---------------|----------------|-----------------------|-------------------------|---------------|--------------------|---------------|-----------|  
|<span data-ttu-id="0477d-171">`char`, `varchar`, `binary`</span><span class="sxs-lookup"><span data-stu-id="0477d-171">`char`, `varchar`, `binary`</span></span>|<span data-ttu-id="0477d-172">-1</span><span class="sxs-lookup"><span data-stu-id="0477d-172">-1</span></span>|<span data-ttu-id="0477d-173">'Padrão'</span><span class="sxs-lookup"><span data-stu-id="0477d-173">'Default'</span></span>|<span data-ttu-id="0477d-174">0</span><span class="sxs-lookup"><span data-stu-id="0477d-174">0</span></span>|<span data-ttu-id="0477d-175">0</span><span class="sxs-lookup"><span data-stu-id="0477d-175">0</span></span>|<span data-ttu-id="0477d-176">8000</span><span class="sxs-lookup"><span data-stu-id="0477d-176">8000</span></span>|<span data-ttu-id="0477d-177">Não aplicável\*\*</span><span class="sxs-lookup"><span data-stu-id="0477d-177">Not applicable\*\*</span></span>|<span data-ttu-id="0477d-178">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-178">Not applicable</span></span>|  
|`nvarchar`|<span data-ttu-id="0477d-179">-1</span><span class="sxs-lookup"><span data-stu-id="0477d-179">-1</span></span>|<span data-ttu-id="0477d-180">'Padrão'</span><span class="sxs-lookup"><span data-stu-id="0477d-180">'Default'</span></span>|<span data-ttu-id="0477d-181">0</span><span class="sxs-lookup"><span data-stu-id="0477d-181">0</span></span>|<span data-ttu-id="0477d-182">0</span><span class="sxs-lookup"><span data-stu-id="0477d-182">0</span></span>|<span data-ttu-id="0477d-183">4000</span><span class="sxs-lookup"><span data-stu-id="0477d-183">4000</span></span>|<span data-ttu-id="0477d-184">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-184">Not applicable</span></span>|<span data-ttu-id="0477d-185">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-185">Not applicable</span></span>|  
|<span data-ttu-id="0477d-186">`decimal`, `float`, `real`</span><span class="sxs-lookup"><span data-stu-id="0477d-186">`decimal`, `float`, `real`</span></span>|<span data-ttu-id="0477d-187">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-187">Not applicable</span></span>|<span data-ttu-id="0477d-188">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-188">Not applicable</span></span>|<span data-ttu-id="0477d-189">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-189">Not applicable</span></span>|<span data-ttu-id="0477d-190">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-190">Not applicable</span></span>|<span data-ttu-id="0477d-191">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-191">Not applicable</span></span>|<span data-ttu-id="0477d-192">18</span><span class="sxs-lookup"><span data-stu-id="0477d-192">18</span></span>|<span data-ttu-id="0477d-193">0</span><span class="sxs-lookup"><span data-stu-id="0477d-193">0</span></span>|  
|<span data-ttu-id="0477d-194">`integer`, `bigint`, `tinyint`, `smallint`</span><span class="sxs-lookup"><span data-stu-id="0477d-194">`integer`, `bigint`, `tinyint`, `smallint`</span></span>|<span data-ttu-id="0477d-195">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-195">Not applicable</span></span>|<span data-ttu-id="0477d-196">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-196">Not applicable</span></span>|<span data-ttu-id="0477d-197">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-197">Not applicable</span></span>|<span data-ttu-id="0477d-198">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-198">Not applicable</span></span>|<span data-ttu-id="0477d-199">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-199">Not applicable</span></span>|<span data-ttu-id="0477d-200">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-200">Not applicable</span></span>|<span data-ttu-id="0477d-201">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-201">Not applicable</span></span>|  
|`datetime2`|<span data-ttu-id="0477d-202">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-202">Not applicable</span></span>|<span data-ttu-id="0477d-203">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-203">Not applicable</span></span>|<span data-ttu-id="0477d-204">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-204">Not applicable</span></span>|<span data-ttu-id="0477d-205">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-205">Not applicable</span></span>|<span data-ttu-id="0477d-206">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-206">Not applicable</span></span>|<span data-ttu-id="0477d-207">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-207">Not applicable</span></span>|<span data-ttu-id="0477d-208">7</span><span class="sxs-lookup"><span data-stu-id="0477d-208">7</span></span>|  
|`datetime offset`|<span data-ttu-id="0477d-209">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-209">Not applicable</span></span>|<span data-ttu-id="0477d-210">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-210">Not applicable</span></span>|<span data-ttu-id="0477d-211">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-211">Not applicable</span></span>|<span data-ttu-id="0477d-212">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-212">Not applicable</span></span>|<span data-ttu-id="0477d-213">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-213">Not applicable</span></span>|<span data-ttu-id="0477d-214">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-214">Not applicable</span></span>|<span data-ttu-id="0477d-215">7</span><span class="sxs-lookup"><span data-stu-id="0477d-215">7</span></span>|  
|<span data-ttu-id="0477d-216">`datetime`, `date`, `smalldatetime`</span><span class="sxs-lookup"><span data-stu-id="0477d-216">`datetime`, `date`, `smalldatetime`</span></span>|<span data-ttu-id="0477d-217">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-217">Not applicable</span></span>|<span data-ttu-id="0477d-218">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-218">Not applicable</span></span>|<span data-ttu-id="0477d-219">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-219">Not applicable</span></span>|<span data-ttu-id="0477d-220">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-220">Not applicable</span></span>|<span data-ttu-id="0477d-221">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-221">Not applicable</span></span>|<span data-ttu-id="0477d-222">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-222">Not applicable</span></span>|<span data-ttu-id="0477d-223">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-223">Not applicable</span></span>|  
|<span data-ttu-id="0477d-224">`money`, `smallmoney`</span><span class="sxs-lookup"><span data-stu-id="0477d-224">`money`, `smallmoney`</span></span>|<span data-ttu-id="0477d-225">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-225">Not applicable</span></span>|<span data-ttu-id="0477d-226">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-226">Not applicable</span></span>|<span data-ttu-id="0477d-227">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-227">Not applicable</span></span>|<span data-ttu-id="0477d-228">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-228">Not applicable</span></span>|<span data-ttu-id="0477d-229">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-229">Not applicable</span></span>|<span data-ttu-id="0477d-230">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-230">Not applicable</span></span>|<span data-ttu-id="0477d-231">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-231">Not applicable</span></span>|  
|`time`|<span data-ttu-id="0477d-232">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-232">Not applicable</span></span>|<span data-ttu-id="0477d-233">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-233">Not applicable</span></span>|<span data-ttu-id="0477d-234">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-234">Not applicable</span></span>|<span data-ttu-id="0477d-235">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-235">Not applicable</span></span>|<span data-ttu-id="0477d-236">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-236">Not applicable</span></span>|<span data-ttu-id="0477d-237">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="0477d-237">Not applicable</span></span>|<span data-ttu-id="0477d-238">7</span><span class="sxs-lookup"><span data-stu-id="0477d-238">7</span></span>|  
  
 <span data-ttu-id="0477d-239">\*  localeID -1 significa a localidade padrão.</span><span class="sxs-lookup"><span data-stu-id="0477d-239">\*  localeID -1 means the default locale.</span></span> <span data-ttu-id="0477d-240">A localidade Inglês é 1033.</span><span class="sxs-lookup"><span data-stu-id="0477d-240">The English locale is 1033.</span></span>  
  
 <span data-ttu-id="0477d-241">\*\* Não aplicável = nenhum valor é produzido para esses atributos durante uma operação de seleção no conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-241">\*\*  Not applicable = No values are output for these attributes during a select operation on the column set.</span></span> <span data-ttu-id="0477d-242">Gera um erro quando um valor é especificado para esse atributo pelo chamador na representação XML fornecida por um conjunto de colunas, em uma operação de inserção ou atualização.</span><span class="sxs-lookup"><span data-stu-id="0477d-242">Generates an error when a value is specified for this attribute by the caller in the XML representation provided for a column set in an insert or update operation.</span></span>  
  
## <a name="security"></a><span data-ttu-id="0477d-243">Segurança</span><span class="sxs-lookup"><span data-stu-id="0477d-243">Security</span></span>  
 <span data-ttu-id="0477d-244">O modelo de segurança para um conjunto de colunas funciona de modo semelhante ao modelo de segurança que existe entre tabela e colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-244">The security model for a column set works similar to the security model that exists between table and columns.</span></span> <span data-ttu-id="0477d-245">Os conjuntos de colunas podem ser visualizados como uma minitabela e uma operação de seleção é como uma operação SELECT \* nessa minitabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-245">Column sets can be visualized as a minitable and a select operation is like a SELECT \* operation on this minitable.</span></span> <span data-ttu-id="0477d-246">Mas a relação entre o conjunto de colunas e as colunas esparsas é uma relação de agrupamento, em vez de estritamente um contêiner.</span><span class="sxs-lookup"><span data-stu-id="0477d-246">But, the relationship between column set to sparse columns is a grouping relationship instead of strictly a container.</span></span> <span data-ttu-id="0477d-247">O modelo de segurança verifica a segurança na coluna do conjunto de colunas e respeita as operações DENY nas colunas esparsas subjacentes.</span><span class="sxs-lookup"><span data-stu-id="0477d-247">The security model checks the security on the column set column, and honors the DENY operations on the underlying sparse columns.</span></span> <span data-ttu-id="0477d-248">Características adicionais do modelo de segurança:</span><span class="sxs-lookup"><span data-stu-id="0477d-248">Additional characteristics of the security model are as follows:</span></span>  
  
-   <span data-ttu-id="0477d-249">Permissões de segurança podem ser concedidas e revogadas da coluna do conjunto de colunas, semelhante a qualquer outra coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-249">Security permissions can be granted and revoked from the column set column, similar to any other column in the table.</span></span>  
  
-   <span data-ttu-id="0477d-250">Um GRANT ou REVOKE de permissões SELECT, INSERT, UPDATE, DELETE e REFERENCES em uma coluna de conjunto de colunas não se propaga às colunas membros subjacentes daquele conjunto.</span><span class="sxs-lookup"><span data-stu-id="0477d-250">A GRANT or REVOKE of SELECT, INSERT, UPDATE, DELETE, and REFERENCES permission on a column set column does not propagate to the underlying member columns of that set.</span></span> <span data-ttu-id="0477d-251">Só se aplica ao uso da coluna do conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-251">It applies only to the usage of the column set column.</span></span> <span data-ttu-id="0477d-252">Permissão DENY em um conjunto de colunas se propaga às colunas esparsas subjacentes da tabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-252">DENY permission on a column set does propagate to the underlying sparse columns of the table.</span></span>  
  
-   <span data-ttu-id="0477d-253">A execução das instruções SELECT, INSERT, UPDATE e DELETE na coluna do conjunto de colunas exige que o usuário tenha permissões correspondentes na coluna do conjunto de colunas e, também, a permissão correspondente em todas as colunas esparsas da tabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-253">Executing SELECT, INSERT, UPDATE, and DELETE statements on the column set column require that the user has corresponding permissions on the column set column, and also the corresponding permission on all the sparse columns in the table.</span></span> <span data-ttu-id="0477d-254">Como o conjunto de colunas representa todas as colunas esparsas na tabela, é necessário ter permissão para todas as colunas esparsas, incluindo as colunas esparsas que podem não estar sendo alteradas.</span><span class="sxs-lookup"><span data-stu-id="0477d-254">Because the column set represents all the sparse columns in the table, you must have permission on all the sparse columns, and this includes sparse columns that you might not be changing.</span></span>  
  
-   <span data-ttu-id="0477d-255">A execução de uma instrução REVOKE em uma coluna esparsa ou conjunto de colunas faz com que a segurança assuma como padrão seu objeto pai.</span><span class="sxs-lookup"><span data-stu-id="0477d-255">Executing a REVOKE statement on a sparse column or column set defaults the security to their parent object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0477d-256">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0477d-256">Examples</span></span>  
 <span data-ttu-id="0477d-257">Nos exemplos a seguir, uma tabela de documento contém o conjunto comum de colunas `DocID` e `Title`.</span><span class="sxs-lookup"><span data-stu-id="0477d-257">In the following examples, a document table contains the common set of columns `DocID` and `Title`.</span></span> <span data-ttu-id="0477d-258">O grupo de Produção quer uma coluna `ProductionSpecification` e `ProductionLocation` para todos os documentos da produção.</span><span class="sxs-lookup"><span data-stu-id="0477d-258">The Production group wants a `ProductionSpecification` and `ProductionLocation` column for all production documents.</span></span> <span data-ttu-id="0477d-259">O grupo Marketing quer uma coluna `MarketingSurveyGroup` para os documentos de marketing.</span><span class="sxs-lookup"><span data-stu-id="0477d-259">The Marketing group wants a `MarketingSurveyGroup` column for marketing documents.</span></span>  
  
### <a name="a-creating-a-table-that-has-a-column-set"></a><span data-ttu-id="0477d-260">a.</span><span class="sxs-lookup"><span data-stu-id="0477d-260">A.</span></span> <span data-ttu-id="0477d-261">Criando uma tabela que possui um conjunto de colunas</span><span class="sxs-lookup"><span data-stu-id="0477d-261">Creating a table that has a column set</span></span>  
 <span data-ttu-id="0477d-262">O exemplo a seguir cria a tabela que usa colunas esparsas e inclui o conjunto de colunas `SpecialPurposeColumns`.</span><span class="sxs-lookup"><span data-stu-id="0477d-262">The following example creates the table that uses sparse columns and includes the column set `SpecialPurposeColumns`.</span></span> <span data-ttu-id="0477d-263">O exemplo insere duas linhas na tabela e, depois, seleciona dados da tabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-263">The example inserts two rows into the table, and then selects data from the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0477d-264">Essa tabela tem somente cinco colunas para facilitar a exibição e a leitura.</span><span class="sxs-lookup"><span data-stu-id="0477d-264">This table has only five columns to make it easier to display and read.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
CREATE TABLE DocumentStoreWithColumnSet  
    (DocID int PRIMARY KEY,  
     Title varchar(200) NOT NULL,  
     ProductionSpecification varchar(20) SPARSE NULL,  
     ProductionLocation smallint SPARSE NULL,  
     MarketingSurveyGroup varchar(20) SPARSE NULL,  
     MarketingProgramID int SPARSE NULL,  
     SpecialPurposeColumns XML COLUMN_SET FOR ALL_SPARSE_COLUMNS);  
GO  
```  
  
### <a name="b-inserting-data-to-a-table-by-using-the-names-of-the-sparse-columns"></a><span data-ttu-id="0477d-265">B.</span><span class="sxs-lookup"><span data-stu-id="0477d-265">B.</span></span> <span data-ttu-id="0477d-266">Inserindo dados em uma tabela usando os nomes das colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="0477d-266">Inserting data to a table by using the names of the sparse columns</span></span>  
 <span data-ttu-id="0477d-267">Os exemplos a seguir inserem duas linhas na tabela criada no exemplo A. Os exemplos usam os nomes das colunas esparsas e não referenciam o conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-267">The following examples insert two rows into the table that is created in example A. The examples use the names of the sparse columns and do not reference the column set.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, ProductionSpecification, ProductionLocation)  
VALUES (1, 'Tire Spec 1', 'AXZZ217', 27);  
GO  
  
INSERT DocumentStoreWithColumnSet (DocID, Title, MarketingSurveyGroup)  
VALUES (2, 'Survey 2142', 'Men 25 - 35');  
GO  
```  
  
### <a name="c-inserting-data-to-a-table-by-using-the-name-of-the-column-set"></a><span data-ttu-id="0477d-268">C.</span><span class="sxs-lookup"><span data-stu-id="0477d-268">C.</span></span> <span data-ttu-id="0477d-269">Inserindo dados em uma tabela usando o nome do conjunto de colunas</span><span class="sxs-lookup"><span data-stu-id="0477d-269">Inserting data to a table by using the name of the column set</span></span>  
 <span data-ttu-id="0477d-270">O exemplo a seguir insere uma terceira linha na tabela criada no exemplo A. Dessa vez, os nomes das colunas esparsas não são usados.</span><span class="sxs-lookup"><span data-stu-id="0477d-270">The following example inserts a third row into the table that is created in example A. This time the names of the sparse columns are not used.</span></span> <span data-ttu-id="0477d-271">Em vez disso, o nome do conjunto de colunas é usado e a inserção fornece os valores para duas das colunas esparsas no formato XML.</span><span class="sxs-lookup"><span data-stu-id="0477d-271">Instead, the name of the column set is used, and the insert provides the values for two of the four sparse columns in XML format.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, SpecialPurposeColumns)  
VALUES (3, 'Tire Spec 2', '<ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>');  
GO  
```  
  
### <a name="d-observing-the-results-of-a-column-set-when-select--is-used"></a><span data-ttu-id="0477d-272">D.</span><span class="sxs-lookup"><span data-stu-id="0477d-272">D.</span></span> <span data-ttu-id="0477d-273">Observando os resultados de um conjunto de colunas quando SELECT \* é usado</span><span class="sxs-lookup"><span data-stu-id="0477d-273">Observing the results of a column set when SELECT \* is used</span></span>  
 <span data-ttu-id="0477d-274">O exemplo a seguir seleciona todas as colunas da tabela que contém um conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-274">The following example selects all the columns from the table that contains a column set.</span></span> <span data-ttu-id="0477d-275">Retorna uma coluna XML com os valores combinados das colunas esparsas.</span><span class="sxs-lookup"><span data-stu-id="0477d-275">It returns an XML column with the combined values of the sparse columns.</span></span> <span data-ttu-id="0477d-276">Não retorna as colunas esparsas individualmente.</span><span class="sxs-lookup"><span data-stu-id="0477d-276">It does not return the sparse columns individually.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns FROM DocumentStoreWithColumnSet ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1      Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `2      Survey 2142  <MarketingSurveyGroup>Men 25 - 35</MarketingSurveyGroup>`  
  
 `3      Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="e-observing-the-results-of-selecting-the-column-set-by-name"></a><span data-ttu-id="0477d-277">E.</span><span class="sxs-lookup"><span data-stu-id="0477d-277">E.</span></span> <span data-ttu-id="0477d-278">Observando os resultados da seleção do conjunto de colunas por nome</span><span class="sxs-lookup"><span data-stu-id="0477d-278">Observing the results of selecting the column set by name</span></span>  
 <span data-ttu-id="0477d-279">Como o departamento de Produção não está interessado nos dados de marketing, este exemplo adiciona uma cláusula `WHERE` para restringir a saída.</span><span class="sxs-lookup"><span data-stu-id="0477d-279">Because the Production department is not interested in the marketing data, this example adds a `WHERE` clause to restrict the output.</span></span> <span data-ttu-id="0477d-280">O exemplo usa o nome do conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="0477d-280">The example uses the name of the column set.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns  
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1     Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `3     Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="f-observing-the-results-of-selecting-sparse-columns-by-name"></a><span data-ttu-id="0477d-281">F.</span><span class="sxs-lookup"><span data-stu-id="0477d-281">F.</span></span> <span data-ttu-id="0477d-282">Observando os resultados da seleção de colunas esparsas por nome</span><span class="sxs-lookup"><span data-stu-id="0477d-282">Observing the results of selecting sparse columns by name</span></span>  
 <span data-ttu-id="0477d-283">Quando uma tabela contém um conjunto de colunas, você ainda pode consultar a tabela usando nomes de colunas individuais, como mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="0477d-283">When a table contains a column set, you can still query the table by using the individual column names as shown in the following example.</span></span>  
  
```  
SELECT DocID, Title, ProductionSpecification, ProductionLocation   
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        ProductionSpecification ProductionLocation`  
  
 `1     Tire Spec 1  AXZZ217                 27`  
  
 `3     Tire Spec 2  AXW9R411                38`  
  
### <a name="g-updating-a-table-by-using-a-column-set"></a><span data-ttu-id="0477d-284">G.</span><span class="sxs-lookup"><span data-stu-id="0477d-284">G.</span></span> <span data-ttu-id="0477d-285">Atualizando uma tabela usando um conjunto de colunas</span><span class="sxs-lookup"><span data-stu-id="0477d-285">Updating a table by using a column set</span></span>  
 <span data-ttu-id="0477d-286">O exemplo a seguir atualiza o terceiro registro com os novos valores para as colunas esparsas usadas por aquela linha.</span><span class="sxs-lookup"><span data-stu-id="0477d-286">The following example updates the third record with new values for both sparse columns that are used by that row.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification><ProductionLocation>38</ProductionLocation>'  
WHERE DocID = 3 ;  
GO  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0477d-287">Uma instrução UPDATE que usa um conjunto de colunas atualiza todas as colunas esparsas na tabela.</span><span class="sxs-lookup"><span data-stu-id="0477d-287">An UPDATE statement that uses a column set updates all the sparse columns in the table.</span></span> <span data-ttu-id="0477d-288">As colunas esparsas que não são referenciadas são atualizadas como NULL.</span><span class="sxs-lookup"><span data-stu-id="0477d-288">Sparse columns that are not referenced are updated to NULL.</span></span>  
  
 <span data-ttu-id="0477d-289">O exemplo a seguir atualiza o terceiro registro, mas só especifica o valor de uma das duas colunas populadas.</span><span class="sxs-lookup"><span data-stu-id="0477d-289">The following example updates the third record, but only specifies the value of one of the two populated columns.</span></span> <span data-ttu-id="0477d-290">A segunda coluna `ProductionLocation` não é incluída na instrução `UPDATE` e é atualizada como NULL.</span><span class="sxs-lookup"><span data-stu-id="0477d-290">The second column `ProductionLocation` is not included in the `UPDATE` statement and is updated to NULL.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification>'  
WHERE DocID = 3 ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0477d-291">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0477d-291">See Also</span></span>  
 [<span data-ttu-id="0477d-292">Usar colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="0477d-292">Use Sparse Columns</span></span>](use-sparse-columns.md)  
  
  
