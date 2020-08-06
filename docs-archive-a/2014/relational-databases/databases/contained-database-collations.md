---
title: Ordenações de banco de dados independentes | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- contained database, collations
ms.assetid: 4b44f6b9-2359-452f-8bb1-5520f2528483
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2648dbedea7708c4f39c922c56bba96cf38b0c0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681685"
---
# <a name="contained-database-collations"></a><span data-ttu-id="aca02-102">Ordenações de banco de dados independentes</span><span class="sxs-lookup"><span data-stu-id="aca02-102">Contained Database Collations</span></span>
  <span data-ttu-id="aca02-103">Várias propriedades afetam a ordem de classificação e a semântica de igualdade dos dados textuais, incluindo diferenciação de maiúsculas e minúsculas, distinção de acentos e o idioma base em uso.</span><span class="sxs-lookup"><span data-stu-id="aca02-103">Various properties affect the sort order and equality semantics of textual data, including case sensitivity, accent sensitivity, and the base language being used.</span></span> <span data-ttu-id="aca02-104">Essas qualidades são demonstradas para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pela escolha da ordenação dos dados.</span><span class="sxs-lookup"><span data-stu-id="aca02-104">These qualities are expressed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the choice of collation for the data.</span></span> <span data-ttu-id="aca02-105">Para obter uma discussão mais detalhada sobre as ordenações, consulte [Suporte a ordenações e a Unicode](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="aca02-105">For a more in-depth discussion of collations themselves, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="aca02-106">As ordenações se aplicam não apenas aos dados armazenados nas tabelas de usuário, mas também a todo o texto tratado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], incluindo metadados, objetos temporários, nomes de variável etc. O tratamento deles varia nos bancos de dados dependentes e independentes.</span><span class="sxs-lookup"><span data-stu-id="aca02-106">Collations apply not only to data stored in user tables, but to all text handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], including metadata, temporary objects, variable names, etc. The handling of these differs in contained and non-contained databases.</span></span> <span data-ttu-id="aca02-107">Essa alteração não afetará muitos usuários, mas ajuda a fornecer independência de instância e uniformidade.</span><span class="sxs-lookup"><span data-stu-id="aca02-107">This change will not affect many users, but helps provide instance independence and uniformity.</span></span> <span data-ttu-id="aca02-108">Mas isso também pode causar alguma confusão, bem como problemas em sessões que acessam bancos de dados contidos e não contidos.</span><span class="sxs-lookup"><span data-stu-id="aca02-108">But this may also cause some confusion, as well as problems for sessions that access both contained and non-contained databases.</span></span>  
  
 <span data-ttu-id="aca02-109">Este tópico esclarece o conteúdo da alteração e examina algumas áreas onde a alteração pode causar problemas.</span><span class="sxs-lookup"><span data-stu-id="aca02-109">This topic clarifies the content of the change, and examines areas where the change may cause problems.</span></span>  
  
## <a name="non-contained-databases"></a><span data-ttu-id="aca02-110">Bancos de dados dependentes</span><span class="sxs-lookup"><span data-stu-id="aca02-110">Non-Contained Databases</span></span>  
 <span data-ttu-id="aca02-111">Todos os bancos de dados têm uma ordenação padrão (que pode ser definida durante a criação ou alteração de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aca02-111">All databases have a default collation (which can be set when creating or altering a database.</span></span> <span data-ttu-id="aca02-112">Essa ordenação é usada para todos os metadados do banco de dados, bem como para o padrão de todas as colunas de cadeias de caracteres no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aca02-112">This collation is used for all metadata in the database, as well as the default for all string columns within the database.</span></span> <span data-ttu-id="aca02-113">Os usuários podem escolher uma ordenação diferente para qualquer coluna específica usando a cláusula `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="aca02-113">Users can choose a different collation for any particular column by using the `COLLATE` clause.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="aca02-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="aca02-114">Example 1</span></span>  
 <span data-ttu-id="aca02-115">Por exemplo, se estivéssemos trabalhando em Beijing, nós poderíamos usar uma ordenação de chinês:</span><span class="sxs-lookup"><span data-stu-id="aca02-115">For example, if we were working in Beijing, we might use a Chinese collation:</span></span>  
  
```sql  
ALTER DATABASE MyDB COLLATE Chinese_Simplified_Pinyin_100_CI_AS;  
```  
  
 <span data-ttu-id="aca02-116">Agora, se criarmos uma coluna, sua ordenação padrão será essa ordenação de chinês, mas podemos escolher outra se quisermos:</span><span class="sxs-lookup"><span data-stu-id="aca02-116">Now if we create a column, its default collation will be this Chinese collation, but we can choose another one if we want:</span></span>  
  
```sql  
CREATE TABLE MyTable  
      (mycolumn1 nvarchar,  
      mycolumn2 nvarchar COLLATE Frisian_100_CS_AS);  
GO  
SELECT name, collation_name  
FROM sys.columns  
WHERE name LIKE 'mycolumn%' ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```sql  
name            collation_name  
--------------- ----------------------------------  
mycolumn1       Chinese_Simplified_Pinyin_100_CI_AS  
mycolumn2       Frisian_100_CS_AS  
```  
  
 <span data-ttu-id="aca02-117">Isso parece relativamente simples, mas vários problemas ocorrem.</span><span class="sxs-lookup"><span data-stu-id="aca02-117">This appears relatively simple, but several problems arise.</span></span> <span data-ttu-id="aca02-118">Como o agrupamento de uma coluna depende do banco de dados no qual a tabela é criada, os problemas surgem com o uso de tabelas temporárias que são armazenadas no `tempdb` .</span><span class="sxs-lookup"><span data-stu-id="aca02-118">Because the collation for a column is dependent on the database in which the table is created, problems arise with the use of temporary tables which are stored in `tempdb`.</span></span> <span data-ttu-id="aca02-119">O agrupamento `tempdb` geralmente corresponde ao agrupamento para a instância, que não precisa corresponder ao agrupamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aca02-119">The collation of `tempdb` usually matches the collation for the instance, which does not have to match the database collation.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="aca02-120">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="aca02-120">Example 2</span></span>  
 <span data-ttu-id="aca02-121">Por exemplo, considere o banco de dados (chinês) acima quando usado em uma instância com uma ordenação **Latin1_General**:</span><span class="sxs-lookup"><span data-stu-id="aca02-121">For example, consider the (Chinese) database above when used on an instance with a **Latin1_General** collation:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max)) ;  
GO  
```  
  
 <span data-ttu-id="aca02-122">À primeira vista, essas duas tabelas parecem ter o mesmo esquema, mas como as ordenações dos bancos de dados são diferentes, na verdade, os valores são incompatíveis:</span><span class="sxs-lookup"><span data-stu-id="aca02-122">At first glance, these two tables look like they have the same schema, but since the collations of the databases differ, the values are actually incompatible:</span></span>  
  
```  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="aca02-123">Msg 468, Nível 16, Estado 9, Linha 2</span><span class="sxs-lookup"><span data-stu-id="aca02-123">Msg 468, Level 16, State 9, Line 2</span></span>  
  
 <span data-ttu-id="aca02-124">Não é possível resolver o conflito de ordenação entre "Latin1_General_100_CI_AS_KS_WS_SC" e Chinese_Simplified_Pinyin_100_CI_AS" na operação de igualdade.</span><span class="sxs-lookup"><span data-stu-id="aca02-124">Cannot resolve the collation conflict between "Latin1_General_100_CI_AS_KS_WS_SC" and Chinese_Simplified_Pinyin_100_CI_AS" in the equal to operation.</span></span>  
  
 <span data-ttu-id="aca02-125">Podemos corrigir isso agrupando explicitamente a tabela temporária.</span><span class="sxs-lookup"><span data-stu-id="aca02-125">We can fix this by explicitly collating the temporary table.</span></span> <span data-ttu-id="aca02-126">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] torna isso um pouco mais fácil ao fornecer a palavra-chave `DATABASE_DEFAULT` para a cláusula `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="aca02-126">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] makes this somewhat easier by providing the `DATABASE_DEFAULT` keyword for the `COLLATE` clause.</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max) COLLATE DATABASE_DEFAULT);  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="aca02-127">Agora, o processo é executado sem erros.</span><span class="sxs-lookup"><span data-stu-id="aca02-127">This now runs without error.</span></span>  
  
 <span data-ttu-id="aca02-128">Também é possível observar o comportamento dependente de ordenação com variáveis.</span><span class="sxs-lookup"><span data-stu-id="aca02-128">We can also see collation-dependent behavior with variables.</span></span> <span data-ttu-id="aca02-129">Considere a seguinte função:</span><span class="sxs-lookup"><span data-stu-id="aca02-129">Consider the following function:</span></span>  
  
```  
CREATE FUNCTION f(@x INT) RETURNS INT  
AS BEGIN   
      DECLARE @I INT = 1  
      DECLARE @?? INT = 2  
      RETURN @x * @i  
END;  
```  
  
 <span data-ttu-id="aca02-130">Essa é uma função bastante peculiar.</span><span class="sxs-lookup"><span data-stu-id="aca02-130">This is a rather peculiar function.</span></span> <span data-ttu-id="aca02-131">Em um agrupamento com diferenciação de maiúsculas e minúsculas, o @i na cláusula return não pode ser associado a @I nem a @??.</span><span class="sxs-lookup"><span data-stu-id="aca02-131">In a case-sensitive collation, the @i in the return clause cannot bind to either @I or @??.</span></span> <span data-ttu-id="aca02-132">Em uma ordenação Latin1_General sem diferenciação de maiúsculas e minúsculas, @i é associado a @I e a função retorna 1.</span><span class="sxs-lookup"><span data-stu-id="aca02-132">In a case-insensitive Latin1_General collation, @i binds to @I, and the function returns 1.</span></span> <span data-ttu-id="aca02-133">Mas, em um agrupamento turco que não diferencia maiúsculas de minúsculas, é @i associado a @??, e a função retorna 2.</span><span class="sxs-lookup"><span data-stu-id="aca02-133">But in a case-insensitive Turkish collation, @i binds to @??, and the function returns 2.</span></span> <span data-ttu-id="aca02-134">Isso pode causar confusão em um banco de dados que se move entre instâncias com ordenações diferentes.</span><span class="sxs-lookup"><span data-stu-id="aca02-134">This can wreak havoc on a database that moves between instances with different collations.</span></span>  
  
## <a name="contained-databases"></a><span data-ttu-id="aca02-135">Bancos de dados independentes</span><span class="sxs-lookup"><span data-stu-id="aca02-135">Contained Databases</span></span>  
 <span data-ttu-id="aca02-136">Como um objetivo de design dos bancos de dados independentes é torná-los dependentes, a dependência da instância e das ordenações `tempdb` deve ser removida.</span><span class="sxs-lookup"><span data-stu-id="aca02-136">Since a design objective of contained databases is to make them self-contained, the dependence on the instance and `tempdb` collations must be severed.</span></span> <span data-ttu-id="aca02-137">Para isso, os bancos de dados independentes apresentam o conceito de ordenação de catálogo.</span><span class="sxs-lookup"><span data-stu-id="aca02-137">To do this, contained databases introduce the concept of the catalog collation.</span></span> <span data-ttu-id="aca02-138">A ordenação de catálogo é usada para metadados de sistema e objetos transitórios.</span><span class="sxs-lookup"><span data-stu-id="aca02-138">The catalog collation is used for system metadata and transient objects.</span></span> <span data-ttu-id="aca02-139">Os detalhes são fornecidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="aca02-139">Details are provided below.</span></span>  
  
 <span data-ttu-id="aca02-140">Em um banco de dados independente, a ordenação de catálogo **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="aca02-140">In a contained database, the catalog collation **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="aca02-141">Essa ordenação é a mesma para todos os bancos de dados independentes em todas as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="aca02-141">This collation is the same for all contained databases on all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and cannot be changed.</span></span>  
  
 <span data-ttu-id="aca02-142">A ordenação de banco de dados é mantida, mas é usada somente como a ordenação padrão para dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="aca02-142">The database collation is retained, but is only used as the default collation for user data.</span></span> <span data-ttu-id="aca02-143">Por padrão, o agrupamento de banco de dados é igual ao agrupamento de banco de dados modelo, mas pode ser alterado pelo usuário por meio de um `CREATE` comando ou, `ALTER DATABASE` como com bancos de dados não independentes.</span><span class="sxs-lookup"><span data-stu-id="aca02-143">By default, the database collation is equal to the model database collation, but can be changed by the user through a `CREATE` or `ALTER DATABASE` command as with non-contained databases.</span></span>  
  
 <span data-ttu-id="aca02-144">Uma nova palavra-chave, `CATALOG_DEFAULT`, está disponível na cláusula `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="aca02-144">A new keyword, `CATALOG_DEFAULT`, is available in the `COLLATE` clause.</span></span> <span data-ttu-id="aca02-145">Ela é usada como um atalho para a ordenação atual de metadados em bancos de dados contidos e não contidos.</span><span class="sxs-lookup"><span data-stu-id="aca02-145">This is used as a shortcut to the current collation of metadata in both contained and non-contained databases.</span></span> <span data-ttu-id="aca02-146">Isso significa que, em um banco de dados não contido, `CATALOG_DEFAULT` retornará a ordenação de banco de dados atual, pois os metadados são agrupados na ordenação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aca02-146">That is, in a non-contained database, `CATALOG_DEFAULT` will return the current database collation, since metadata is collated in the database collation.</span></span> <span data-ttu-id="aca02-147">Em um banco de dados contido, esses valores podem ser diferentes, pois o usuário pode alterar a ordenação do banco de dados para que ele não corresponda à ordenação de catálogo.</span><span class="sxs-lookup"><span data-stu-id="aca02-147">In a contained database, these two values may be different, since the user can change the database collation so that it does not match the catalog collation.</span></span>  
  
 <span data-ttu-id="aca02-148">O comportamento de vários objetos nos bancos de dados contidos e não contidos é resumido nesta tabela:</span><span class="sxs-lookup"><span data-stu-id="aca02-148">The behavior of various objects in both non-contained and contained databases is summarized in this table:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="aca02-149">**Item**</span><span class="sxs-lookup"><span data-stu-id="aca02-149">**Item**</span></span>|<span data-ttu-id="aca02-150">**Banco de dados não contido**</span><span class="sxs-lookup"><span data-stu-id="aca02-150">**Non-Contained Database**</span></span>|<span data-ttu-id="aca02-151">**Banco de dados contido**</span><span class="sxs-lookup"><span data-stu-id="aca02-151">**Contained Database**</span></span>|  
|<span data-ttu-id="aca02-152">Dados de usuário (padrão)</span><span class="sxs-lookup"><span data-stu-id="aca02-152">User Data (default)</span></span>|<span data-ttu-id="aca02-153">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-153">DATABASE_DEFAULT</span></span>|<span data-ttu-id="aca02-154">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-154">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="aca02-155">Dados temp (padrão)</span><span class="sxs-lookup"><span data-stu-id="aca02-155">Temp Data (default)</span></span>|<span data-ttu-id="aca02-156">Ordenação TempDB</span><span class="sxs-lookup"><span data-stu-id="aca02-156">TempDB Collation</span></span>|<span data-ttu-id="aca02-157">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-157">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="aca02-158">Metadados</span><span class="sxs-lookup"><span data-stu-id="aca02-158">Metadata</span></span>|<span data-ttu-id="aca02-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span></span>|<span data-ttu-id="aca02-160">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-160">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="aca02-161">Metadados temporários</span><span class="sxs-lookup"><span data-stu-id="aca02-161">Temporary Metadata</span></span>|<span data-ttu-id="aca02-162">Ordenação tempdb</span><span class="sxs-lookup"><span data-stu-id="aca02-162">tempdb Collation</span></span>|<span data-ttu-id="aca02-163">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-163">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="aca02-164">Variáveis</span><span class="sxs-lookup"><span data-stu-id="aca02-164">Variables</span></span>|<span data-ttu-id="aca02-165">Ordenação de instância</span><span class="sxs-lookup"><span data-stu-id="aca02-165">Instance Collation</span></span>|<span data-ttu-id="aca02-166">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-166">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="aca02-167">Rótulos Goto</span><span class="sxs-lookup"><span data-stu-id="aca02-167">Goto Labels</span></span>|<span data-ttu-id="aca02-168">Ordenação de instância</span><span class="sxs-lookup"><span data-stu-id="aca02-168">Instance Collation</span></span>|<span data-ttu-id="aca02-169">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-169">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="aca02-170">Nomes de cursor</span><span class="sxs-lookup"><span data-stu-id="aca02-170">Cursor Names</span></span>|<span data-ttu-id="aca02-171">Ordenação de instância</span><span class="sxs-lookup"><span data-stu-id="aca02-171">Instance Collation</span></span>|<span data-ttu-id="aca02-172">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="aca02-172">CATALOG_DEFAULT</span></span>|  
  
 <span data-ttu-id="aca02-173">No exemplo de tabela temp descrito anteriormente, podemos ver que esse comportamento de ordenação elimina a necessidade de uma cláusula `COLLATE` explícita na maioria dos usos da tabela temp.</span><span class="sxs-lookup"><span data-stu-id="aca02-173">If we temp table example previously described, we can see that this collation behavior eliminates the need for an explicit `COLLATE` clause in most temp table uses.</span></span> <span data-ttu-id="aca02-174">Em um banco de dados contido, esse código agora é executado sem erro, mesmo que as ordenações de banco de dados e de instância sejam diferentes:</span><span class="sxs-lookup"><span data-stu-id="aca02-174">In a contained database, this code now runs without error, even if the database and instance collations differ:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max));  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="aca02-175">Isso funciona porque `T1_txt` e `T2_txt` são coletados na ordenação de banco de dados contido.</span><span class="sxs-lookup"><span data-stu-id="aca02-175">This works because both `T1_txt` and `T2_txt` are collated in the database collation of the contained database.</span></span>  
  
## <a name="crossing-between-contained-and-uncontained-contexts"></a><span data-ttu-id="aca02-176">Cruzando entre contextos contidos e não contidos</span><span class="sxs-lookup"><span data-stu-id="aca02-176">Crossing Between Contained and Uncontained Contexts</span></span>  
 <span data-ttu-id="aca02-177">Desde que uma sessão em um banco de dados contido permaneça contida, ela deve permanecer no banco de dados ao qual está conectada.</span><span class="sxs-lookup"><span data-stu-id="aca02-177">As long as a session in a contained database remains contained, it must remain within the database to which it connected.</span></span> <span data-ttu-id="aca02-178">Nesse caso, o comportamento é muito simples.</span><span class="sxs-lookup"><span data-stu-id="aca02-178">In this case the behavior is very straightforward.</span></span> <span data-ttu-id="aca02-179">Mas se uma sessão cruzar entre contextos contidos e não contidos, o comportamento se tornará mais complexo, pois os dois conjuntos de regras deverão ser ligados.</span><span class="sxs-lookup"><span data-stu-id="aca02-179">But if a session crosses between contained and non-contained contexts, the behavior becomes more complex, since the two sets of rules must be bridged.</span></span> <span data-ttu-id="aca02-180">Isso pode ocorrer em um banco de dados parcialmente contido, pois um usuário pode `USE` para outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aca02-180">This can happen in a partially-contained database, since a user may `USE` to another database.</span></span> <span data-ttu-id="aca02-181">Nesse caso, a diferença nas regras de ordenação é tratada pelo princípio a seguir.</span><span class="sxs-lookup"><span data-stu-id="aca02-181">In this case, the difference in collation rules is handled by the following principle.</span></span>  
  
-   <span data-ttu-id="aca02-182">O comportamento de ordenação para um lote é determinado pelo banco de dados no qual o lote começa.</span><span class="sxs-lookup"><span data-stu-id="aca02-182">The collation behavior for a batch is determined by the database in which the batch begins.</span></span>  
  
 <span data-ttu-id="aca02-183">Observe que essa decisão é tomada antes da emissão de qualquer comando, inclusive um `USE` inicial.</span><span class="sxs-lookup"><span data-stu-id="aca02-183">Note that this decision is made before any commands are issued, including an initial `USE`.</span></span> <span data-ttu-id="aca02-184">Ou seja, se um lote começar em um banco de dados independente, mas se o primeiro comando for um `USE` para um banco de dados dependente, o comportamento da ordenação independente ainda será usado para o lote.</span><span class="sxs-lookup"><span data-stu-id="aca02-184">That is, if a batch begins in a contained database, but the first command is a `USE` to a non-contained database, the contained collation behavior will still be used for the batch.</span></span> <span data-ttu-id="aca02-185">Dito isto, uma referência para uma variável, por exemplo, pode ter vários possíveis resultados:</span><span class="sxs-lookup"><span data-stu-id="aca02-185">Given this, a reference to a variable, for example, may have multiple possible outcomes:</span></span>  
  
-   <span data-ttu-id="aca02-186">A referência pode localizar uma correspondência exatamente.</span><span class="sxs-lookup"><span data-stu-id="aca02-186">The reference may find exactly one match.</span></span> <span data-ttu-id="aca02-187">Nesse caso, a referência funcionará sem erro.</span><span class="sxs-lookup"><span data-stu-id="aca02-187">In this case, the reference will work without error.</span></span>  
  
-   <span data-ttu-id="aca02-188">A referência pode não localizar uma correspondência na ordenação atual onde antes havia uma.</span><span class="sxs-lookup"><span data-stu-id="aca02-188">The reference may not find a match in the current collation where there was one before.</span></span> <span data-ttu-id="aca02-189">Isso gerará um erro que indica que a variável não existe, embora ela tenha sido criada aparentemente.</span><span class="sxs-lookup"><span data-stu-id="aca02-189">This will raise an error indicating that the variable does not exist, even though it was apparently created.</span></span>  
  
-   <span data-ttu-id="aca02-190">A referência pode localizar várias correspondências que originalmente eram distintas.</span><span class="sxs-lookup"><span data-stu-id="aca02-190">The reference may find multiple matches that were originally distinct.</span></span> <span data-ttu-id="aca02-191">Isso também gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="aca02-191">This will also raise an error.</span></span>  
  
 <span data-ttu-id="aca02-192">Isso será mostrado com alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="aca02-192">We'll illustrate this with a few examples.</span></span> <span data-ttu-id="aca02-193">Para eles, pressupomos que haja um banco de dados parcialmente independente denominado `MyCDB` com sua ordenação de banco de dados definida como ordenação padrão **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="aca02-193">For these we assume there is a partially-contained database named `MyCDB` with its database collation set to the default collation, **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="aca02-194">Assumimos que a ordenação de instância é `Latin1_General_100_CS_AS_WS_KS_SC`.</span><span class="sxs-lookup"><span data-stu-id="aca02-194">We assume that the instance collation is `Latin1_General_100_CS_AS_WS_KS_SC`.</span></span> <span data-ttu-id="aca02-195">As duas ordenações são distintas apenas na diferenciação de maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="aca02-195">The two collations differ only in case sensitivity.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="aca02-196">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="aca02-196">Example 1</span></span>  
 <span data-ttu-id="aca02-197">O exemplo a seguir mostra o caso onde a referência localiza uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="aca02-197">The following example illustrates the case where the reference finds exactly one match.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #a VALUES(1);  
GO  
  
USE master;  
GO  
  
SELECT * FROM #a;  
GO  
  
Results:  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
x  
-----------  
1  
```  
  
 <span data-ttu-id="aca02-198">Nesse caso, o símbolo #a identificado é associado à ordenação de catálogo sem diferenciação de maiúsculas/minúsculas e a ordenação de instância com diferenciação de maiúsculas/minúsculas, e o código funciona.</span><span class="sxs-lookup"><span data-stu-id="aca02-198">In this case, the identified #a binds in both the case-insensitive catalog collation and the case-sensitive instance collation, and the code works.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="aca02-199">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="aca02-199">Example 2</span></span>  
 <span data-ttu-id="aca02-200">O exemplo a seguir mostra o caso em que a referência não encontra uma correspondência na ordenação atual, na qual havia uma antes.</span><span class="sxs-lookup"><span data-stu-id="aca02-200">The following example illustrates the case where the reference does not find a match in the current collation where there was one before.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #A VALUES(1);  
GO  
```  
  
 <span data-ttu-id="aca02-201">Aqui, o #A é associado a #a na ordenação padrão sem diferenciação de maiúsculas e minúsculas e a inserção funciona,</span><span class="sxs-lookup"><span data-stu-id="aca02-201">Here, the #A binds to #a in the case-insensitive default collation, and the insert works,</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="aca02-202">Mas se continuarmos o script...</span><span class="sxs-lookup"><span data-stu-id="aca02-202">But if we continue the script...</span></span>  
  
```  
USE master;  
GO  
  
SELECT * FROM #A;  
GO  
```  
  
 <span data-ttu-id="aca02-203">Receberemos um erro ao tentar associar ao #A na ordenação de instância com diferenciação de maiúsculas e minúsculas;</span><span class="sxs-lookup"><span data-stu-id="aca02-203">We get an error trying to bind to #A in the case-sensitive instance collation;</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="aca02-204">Msg 208, Nível 16, Estado 0, Linha 2</span><span class="sxs-lookup"><span data-stu-id="aca02-204">Msg 208, Level 16, State 0, Line 2</span></span>  
  
 <span data-ttu-id="aca02-205">Nome do objeto inválido '#A'.</span><span class="sxs-lookup"><span data-stu-id="aca02-205">Invalid object name '#A'.</span></span>  
  
### <a name="example-3"></a><span data-ttu-id="aca02-206">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="aca02-206">Example 3</span></span>  
 <span data-ttu-id="aca02-207">O exemplo a seguir demonstra o caso em que a referência localiza várias correspondências que eram originalmente distintas.</span><span class="sxs-lookup"><span data-stu-id="aca02-207">The following example illustrates the case where the reference finds multiple matches that were originally distinct.</span></span> <span data-ttu-id="aca02-208">Primeiro, começamos `tempdb` (que tem o mesmo agrupamento que diferencia maiúsculas de minúsculas da nossa instância) e executamos as instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="aca02-208">First, we start in `tempdb` (which has the same case-sensitive collation as our instance) and execute the following statements.</span></span>  
  
```  
USE tempdb;  
GO  
  
CREATE TABLE #a(x int);  
GO  
CREATE TABLE #A(x int);  
GO  
INSERT INTO #a VALUES(1);  
GO  
INSERT INTO #A VALUES(2);  
GO  
```  
  
 <span data-ttu-id="aca02-209">Essa operação é bem-sucedida, pois as tabelas são distintas nesta ordenação:</span><span class="sxs-lookup"><span data-stu-id="aca02-209">This succeeds, since the tables are distinct in this collation:</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="aca02-210">Se entrarmos em nosso banco de dados contido, no entanto, descobriremos que não podemos mais associar a essas tabelas.</span><span class="sxs-lookup"><span data-stu-id="aca02-210">If we move into our contained database, however, we find that we can no longer bind to these tables.</span></span>  
  
```  
USE MyCDB;  
GO  
SELECT * FROM #a;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="aca02-211">Msg 12800, Nível 16, Estado 1, Linha 2</span><span class="sxs-lookup"><span data-stu-id="aca02-211">Msg 12800, Level 16, State 1, Line 2</span></span>  
  
 <span data-ttu-id="aca02-212">A referência ao nome da tabela temp '#a' é ambígua e não pode ser resolvida.</span><span class="sxs-lookup"><span data-stu-id="aca02-212">The reference to temp table name '#a' is ambiguous and cannot be resolved.</span></span> <span data-ttu-id="aca02-213">Possíveis candidatos são '#a' e '#A'.</span><span class="sxs-lookup"><span data-stu-id="aca02-213">Possible candidates are '#a' and '#A'.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="aca02-214">Conclusão</span><span class="sxs-lookup"><span data-stu-id="aca02-214">Conclusion</span></span>  
 <span data-ttu-id="aca02-215">O comportamento de ordenação de bancos de dados contidos é sutilmente diferente daquele em bancos de dados não contidos.</span><span class="sxs-lookup"><span data-stu-id="aca02-215">The collation behavior of contained databases differs subtly from that in non-contained databases.</span></span> <span data-ttu-id="aca02-216">Esse comportamento é geralmente benéfico, fornecendo independência de instância e simplicidade.</span><span class="sxs-lookup"><span data-stu-id="aca02-216">This behavior is generally beneficial, providing instance-independence and simplicity.</span></span> <span data-ttu-id="aca02-217">Alguns usuários podem ter problemas, particularmente quando uma sessão acessa bancos de dados contidos e não contidos.</span><span class="sxs-lookup"><span data-stu-id="aca02-217">Some users may have issues, particularly when a session accesses both contained and non-contained databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca02-218">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aca02-218">See Also</span></span>  
 [<span data-ttu-id="aca02-219">Bancos de dados independentes</span><span class="sxs-lookup"><span data-stu-id="aca02-219">Contained Databases</span></span>](contained-databases.md)  
  
  
