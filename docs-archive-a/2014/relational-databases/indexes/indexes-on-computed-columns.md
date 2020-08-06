---
title: Índices em colunas computadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, index creation
- index creation [SQL Server], computed columns
- imprecise columns
- persisted computed columns
- precise [SQL Server]
ms.assetid: 8d17ac9c-f3af-4bbb-9cc1-5cf647e994c4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ecbca9e7838c4c9395a8bcb6e11351c40f7037f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685676"
---
# <a name="indexes-on-computed-columns"></a><span data-ttu-id="ba1f3-102">Índices em colunas computadas</span><span class="sxs-lookup"><span data-stu-id="ba1f3-102">Indexes on Computed Columns</span></span>
  <span data-ttu-id="ba1f3-103">Você pode definir índices em colunas computadas contanto que os seguintes requisitos sejam satisfeitos:</span><span class="sxs-lookup"><span data-stu-id="ba1f3-103">You can define indexes on computed columns as long as the following requirements are met:</span></span>  
  
-   <span data-ttu-id="ba1f3-104">Requisitos de propriedade</span><span class="sxs-lookup"><span data-stu-id="ba1f3-104">Ownership requirements</span></span>  
  
-   <span data-ttu-id="ba1f3-105">Requisitos de determinismo</span><span class="sxs-lookup"><span data-stu-id="ba1f3-105">Determinism requirements</span></span>  
  
-   <span data-ttu-id="ba1f3-106">Requisitos de precisão</span><span class="sxs-lookup"><span data-stu-id="ba1f3-106">Precision requirements</span></span>  
  
-   <span data-ttu-id="ba1f3-107">Requisitos de tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ba1f3-107">Data type requirements</span></span>  
  
-   <span data-ttu-id="ba1f3-108">Requisitos de opção SET</span><span class="sxs-lookup"><span data-stu-id="ba1f3-108">SET option requirements</span></span>  
  
 <span data-ttu-id="ba1f3-109">**Ownership Requirements**</span><span class="sxs-lookup"><span data-stu-id="ba1f3-109">**Ownership Requirements**</span></span>  
  
 <span data-ttu-id="ba1f3-110">Todas as referências de função na coluna computada devem ter o mesmo proprietário da tabela.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-110">All function references in the computed column must have the same owner as the table.</span></span>  
  
 <span data-ttu-id="ba1f3-111">**Determinism Requirements**</span><span class="sxs-lookup"><span data-stu-id="ba1f3-111">**Determinism Requirements**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ba1f3-112">Expressões são determinísticas se elas sempre retornarem o mesmo resultado para um conjunto de entradas especificado.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-112">Expressions are deterministic if they always return the same result for a specified set of inputs.</span></span> <span data-ttu-id="ba1f3-113">A propriedade **IsDeterministic** da função [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) relata se um *computed_column_expression* é determinístico.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-113">The **IsDeterministic** property of the [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) function reports whether a *computed_column_expression* is deterministic.</span></span>  
  
 <span data-ttu-id="ba1f3-114">A *computed_column_expression* deve ser determinística.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-114">The *computed_column_expression* must be deterministic.</span></span> <span data-ttu-id="ba1f3-115">Uma *computed_column_expression* é determinística quando uma ou mais das seguintes opções é verdadeira:</span><span class="sxs-lookup"><span data-stu-id="ba1f3-115">A *computed_column_expression* is deterministic when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="ba1f3-116">Todas as funções mencionadas pela expressão são determinísticas e precisas.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-116">All functions that are referenced by the expression are deterministic and precise.</span></span> <span data-ttu-id="ba1f3-117">Essas funções incluem as funções definidas pelo usuário e internas.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-117">These functions include both user-defined and built-in functions.</span></span> <span data-ttu-id="ba1f3-118">Para obter mais informações, veja [Funções determinísticas e não determinísticas](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span><span class="sxs-lookup"><span data-stu-id="ba1f3-118">For more information, see [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span></span> <span data-ttu-id="ba1f3-119">Funções podem ser imprecisas se a coluna computada for PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-119">Functions might be imprecise if the computed column is PERSISTED.</span></span> <span data-ttu-id="ba1f3-120">Para obter mais informações, veja [Criando índices em colunas computadas persistentes](#BKMK_persisted) , mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-120">For more information, see [Creating Indexes on Persisted Computed Columns](#BKMK_persisted) later in this topic.</span></span>  
  
-   <span data-ttu-id="ba1f3-121">Todas as colunas mencionadas na expressão vêm da tabela que contém a coluna computada.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-121">All columns that are referenced in the expression come from the table that contains the computed column.</span></span>  
  
-   <span data-ttu-id="ba1f3-122">Nenhuma referência de coluna recebe dados de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-122">No column reference pulls data from multiple rows.</span></span> <span data-ttu-id="ba1f3-123">Por exemplo, funções de agregação como SUM ou AVG dependem de dados de várias linhas e criam uma *computed_column_expression* não determinística.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-123">For example, aggregate functions such as SUM or AVG depend on data from multiple rows and would make a *computed_column_expression* nondeterministic.</span></span>  
  
-   <span data-ttu-id="ba1f3-124">A *computed_column_expression* não tem acesso a dados do sistema nem a dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-124">The *computed_column_expression* has no system data access or user data access.</span></span>  
  
 <span data-ttu-id="ba1f3-125">Qualquer coluna computada que contenha uma expressão CLR (Common Language Runtime) deve ser determinística e marcada como PERSISTED antes que a coluna possa ser indexada.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-125">Any computed column that contains a common language runtime (CLR) expression must be deterministic and marked PERSISTED before the column can be indexed.</span></span> <span data-ttu-id="ba1f3-126">Expressões de tipo de dado CLR definido pelo usuário são permitidas em definições de coluna computada.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-126">CLR user-defined type expressions are allowed in computed column definitions.</span></span> <span data-ttu-id="ba1f3-127">Colunas computadas cujo tipo é um tipo de dado CLR definido pelo usuário podem ser indexadas contanto que o tipo seja comparável.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-127">Computed columns whose type is a CLR user-defined type can be indexed as long as the type is comparable.</span></span> <span data-ttu-id="ba1f3-128">Para obter mais informações, veja [Tipos CLR definidos pelo usuário](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="ba1f3-128">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba1f3-129">Quando você se referir a literais de cadeia de caracteres do tipo de dados de data em colunas computadas indexadas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], recomendamos que você converta explicitamente o literal para o tipo de data desejado, usando um estilo de formato de data determinístico.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-129">When you refer to string literals of the date data type in indexed computed columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], we recommend that you explicitly convert the literal to the date type that you want by using a deterministic date format style.</span></span> <span data-ttu-id="ba1f3-130">Para obter uma lista de estilos de formato de data determinísticos, veja [CAST e CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba1f3-130">For a list of the date format styles that are deterministic, see [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span> <span data-ttu-id="ba1f3-131">Expressões que envolvem conversão implícita de cadeias de caracteres para tipos de dados de data são consideradas não determinísticas, a menos que o nível de compatibilidade de banco de dados seja definido como 80 ou abaixo disso.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-131">Expressions that involve implicit conversion of character strings to date data types are considered nondeterministic, unless the database compatibility level is set to 80 or earlier.</span></span> <span data-ttu-id="ba1f3-132">Isso ocorre porque os resultados dependem das configurações de [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) e [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) da sessão de servidor.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-132">This is because the results depend on the [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) and [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) settings of the server session.</span></span> <span data-ttu-id="ba1f3-133">Por exemplo, os resultados da expressão `CONVERT (datetime, '30 listopad 1996', 113)` dependem da configuração LANGUAGE porque a cadeia de caracteres '`30 listopad 1996`' significa meses diferentes em idiomas.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-133">For example, the results of the expression `CONVERT (datetime, '30 listopad 1996', 113)` depend on the LANGUAGE setting because the string '`30 listopad 1996`' means different months in different languages.</span></span> <span data-ttu-id="ba1f3-134">Semelhantemente, na expressão `DATEADD(mm,3,'2000-12-01')`, o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interpreta a cadeia de caracteres `'2000-12-01'` com base na configuração DATEFORMAT.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-134">Similarly, in the expression `DATEADD(mm,3,'2000-12-01')`, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interprets the string `'2000-12-01'` based on the DATEFORMAT setting.</span></span>  
>   
>  <span data-ttu-id="ba1f3-135">A conversão implícita de dados de caracteres não Unicode entre ordenações também é considerada não determinística, a menos que o nível de compatibilidade seja definido como 80 ou abaixo disso.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-135">Implicit conversion of non-Unicode character data between collations is also considered nondeterministic, unless the compatibility level is set to 80 or earlier.</span></span>  
>   
>  <span data-ttu-id="ba1f3-136">Quando o nível da configuração da compatibilidade de banco de dados é 90, você não pode criar índices em colunas computadas que contêm essas expressões.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-136">When the database compatibility level setting is 90, you cannot create indexes on computed columns that contain these expressions.</span></span> <span data-ttu-id="ba1f3-137">Porém, a existência de colunas computadas com essas expressões de um banco de dados atualizado é sustentável.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-137">However, existing computed columns that contain these expressions from an upgraded database are maintainable.</span></span> <span data-ttu-id="ba1f3-138">Se você usar colunas computadas indexadas que contêm conversões implícitas de cadeia de caracteres para datas; para evitar possível corrupção de índice, verifique se as configurações LANGUAGE e DATEFORMAT estão consistentes em seus bancos de dados e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-138">If you use indexed computed columns that contain implicit string to date conversions, to avoid possible index corruption, make sure that the LANGUAGE and DATEFORMAT settings are consistent in your databases and applications.</span></span>  
  
 <span data-ttu-id="ba1f3-139">**Precision Requirements**</span><span class="sxs-lookup"><span data-stu-id="ba1f3-139">**Precision Requirements**</span></span>  
  
 <span data-ttu-id="ba1f3-140">A *computed_column_expression* deve ser precisa.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-140">The *computed_column_expression* must be precise.</span></span> <span data-ttu-id="ba1f3-141">Uma *computed_column_expression* é precisa quando uma ou mais das seguintes opções é verdadeira:</span><span class="sxs-lookup"><span data-stu-id="ba1f3-141">A *computed_column_expression* is precise when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="ba1f3-142">Não é uma expressão de tipos de dados `float` ou `real`.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-142">It is not an expression of the `float` or `real` data types.</span></span>  
  
-   <span data-ttu-id="ba1f3-143">Não usa `float` ou tipo de dados `real` em sua definição.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-143">It does not use a `float` or `real` data type in its definition.</span></span> <span data-ttu-id="ba1f3-144">Por exemplo, na instrução a seguir, a coluna `y` é `int` e determinística mas não é precisa.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-144">For example, in the following statement, column `y` is `int` and deterministic but not precise.</span></span>  
  
    ```  
    CREATE TABLE t2 (a int, b int, c int, x float,   
       y AS CASE x   
             WHEN 0 THEN a   
             WHEN 1 THEN b   
             ELSE c   
          END);  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="ba1f3-145">Qualquer expressão `float` ou `real` é considerada imprecisa e não pode ser uma chave de um índice; uma expressão `float` ou `real` pode ser usada em uma exibição indexada mas não como uma chave.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-145">Any `float` or `real` expression is considered imprecise and cannot be a key of an index; a `float` or `real` expression can be used in an indexed view but not as a key.</span></span> <span data-ttu-id="ba1f3-146">Isso também é verdade para colunas computadas.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-146">This is true also for computed columns.</span></span> <span data-ttu-id="ba1f3-147">Qualquer função, expressão, ou função definida pelo usuário será considerada imprecisa se contiver qualquer expressão `float` ou `real`.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-147">Any function, expression, or user-defined function is considered imprecise if it contains any `float` or `real` expressions.</span></span> <span data-ttu-id="ba1f3-148">Isso inclui as lógicas (comparações).</span><span class="sxs-lookup"><span data-stu-id="ba1f3-148">This includes logical ones (comparisons).</span></span>  
  
 <span data-ttu-id="ba1f3-149">A propriedade **IsPrecise** da função COLUMNPROPERTY relata se uma *computed_column_expression* é precisa.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-149">The **IsPrecise** property of the COLUMNPROPERTY function reports whether a *computed_column_expression* is precise.</span></span>  
  
 <span data-ttu-id="ba1f3-150">**Data Type Requirements**</span><span class="sxs-lookup"><span data-stu-id="ba1f3-150">**Data Type Requirements**</span></span>  
  
-   <span data-ttu-id="ba1f3-151">A *computed_column_expression* definida para a coluna computada não pode ser avaliada como os `text` `ntext` tipos de dados, ou `image` .</span><span class="sxs-lookup"><span data-stu-id="ba1f3-151">The *computed_column_expression* defined for the computed column cannot evaluate to the `text`, `ntext`, or `image` data types.</span></span>  
  
-   <span data-ttu-id="ba1f3-152">Colunas computadas derivadas de `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, e tipos de dados `xml` podem ser indexados contanto que o tipo de dados de coluna computada seja permitido como coluna de índice chave.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-152">Computed columns derived from `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, and `xml` data types can be indexed as long as the computed column data type is allowable as an index key column.</span></span>  
  
-   <span data-ttu-id="ba1f3-153">Colunas computadas derivadas de `image`, `ntext`, e tipos de dados `text` podem ser colunas não chave (inclusas) em um índice não clusterizado contanto que o tipo de dados da coluna computada seja permitida como coluna de índice não chave.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-153">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey (included) columns in a nonclustered index as long as the computed column data type is allowable as a nonkey index column.</span></span>  
  
 <span data-ttu-id="ba1f3-154">**Requisitos de opção SET**</span><span class="sxs-lookup"><span data-stu-id="ba1f3-154">**SET Option Requirements**</span></span>  
  
-   <span data-ttu-id="ba1f3-155">A opção de nível de conexão ANSI_NULLS deve ser definida como ON quando a instrução CREATE TABLE ou ALTER TABLE que define a coluna computada é executada.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-155">The ANSI_NULLS connection-level option must be set to ON when the CREATE TABLE or ALTER TABLE statement that defines the computed column is executed.</span></span> <span data-ttu-id="ba1f3-156">A função [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) relata se a opção está ativa pela propriedade **IsAnsiNullsOn** .</span><span class="sxs-lookup"><span data-stu-id="ba1f3-156">The [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) function reports whether the option is on through the **IsAnsiNullsOn** property.</span></span>  
  
-   <span data-ttu-id="ba1f3-157">A conexão na qual o índice é criado e todas as conexões que tentam instruções INSERT, UPDATE ou DELETE que alterarão valores no índice, deve ter seis opções de SET definidas como ON e uma opção definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-157">The connection on which the index is created, and all connections trying INSERT, UPDATE, or DELETE statements that will change values in the index, must have six SET options set to ON and one option set to OFF.</span></span> <span data-ttu-id="ba1f3-158">O otimizador ignora um índice em uma coluna computada para qualquer instrução SELECT executada por uma conexão que não tenha essas mesmas opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-158">The optimizer ignores an index on a computed column for any SELECT statement executed by a connection that does not have these same option settings.</span></span>  
  
    -   <span data-ttu-id="ba1f3-159">A opção de NUMERIC_ROUNDABORT deve ser definida como OFF e as opções seguintes devem ser definidas como ON:</span><span class="sxs-lookup"><span data-stu-id="ba1f3-159">The NUMERIC_ROUNDABORT option must be set to OFF, and the following options must be set to ON:</span></span>  
  
    -   <span data-ttu-id="ba1f3-160">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="ba1f3-160">ANSI_NULLS</span></span>  
  
    -   <span data-ttu-id="ba1f3-161">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="ba1f3-161">ANSI_PADDING</span></span>  
  
    -   <span data-ttu-id="ba1f3-162">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="ba1f3-162">ANSI_WARNINGS</span></span>  
  
    -   <span data-ttu-id="ba1f3-163">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="ba1f3-163">ARITHABORT</span></span>  
  
    -   <span data-ttu-id="ba1f3-164">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="ba1f3-164">CONCAT_NULL_YIELDS_NULL</span></span>  
  
    -   <span data-ttu-id="ba1f3-165">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="ba1f3-165">QUOTED_IDENTIFIER</span></span>  
  
     <span data-ttu-id="ba1f3-166">A definição de ANSI_WARNINGS como ON definirá ARITHABORT implicitamente como ON quando o nível de compatibilidade do banco de dados estiver definido como 90 ou mais.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-166">Setting ANSI_WARNINGS to ON implicitly sets ARITHABORT to ON when the database compatibility level is set to 90 or higher.</span></span>  
  
##  <a name="creating-indexes-on-persisted-computed-columns"></a><a name="BKMK_persisted"></a> <span data-ttu-id="ba1f3-167">Criando índices em colunas computadas persistentes</span><span class="sxs-lookup"><span data-stu-id="ba1f3-167">Creating Indexes on Persisted Computed Columns</span></span>  
 <span data-ttu-id="ba1f3-168">Você pode criar um índice em uma coluna computada que está definida com uma expressão determinística, mas imprecisa, se a coluna for marcada como PERSISTED na instrução CREATE TABLE ou ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-168">You can create an index on a computed column that is defined with a deterministic, but imprecise, expression if the column is marked PERSISTED in the CREATE TABLE or ALTER TABLE statement.</span></span> <span data-ttu-id="ba1f3-169">Isso significa que o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] usa esses valores persistentes ao criar um índice na coluna e quando o índice é referenciado em uma consulta.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-169">This means that the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] uses these persisted values when it creates an index on the column, and when the index is referenced in a query.</span></span> <span data-ttu-id="ba1f3-170">Essa opção permite que você crie um índice em uma coluna computada quando [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)] , é determinístico e preciso.</span><span class="sxs-lookup"><span data-stu-id="ba1f3-170">This option enables you to create an index on a computed column when [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)], is both deterministic and precise.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="ba1f3-171">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="ba1f3-171">Related Content</span></span>  
 [<span data-ttu-id="ba1f3-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ba1f3-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
  
