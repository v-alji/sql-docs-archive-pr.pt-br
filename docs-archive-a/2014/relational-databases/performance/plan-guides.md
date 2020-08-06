---
title: Guias de plano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- SQL plan guides
- OPTIMIZE FOR query hint
- RECOMPILE query hint
- OBJECT plan guide
- plan guides [SQL Server], about plan guides
- OPTION clause
- plan guides [SQL Server]
- USE PLAN query hint
ms.assetid: bfc97632-c14c-4768-9dc5-a9c512f6b2bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c97682163313a56acb8521174fa8d4012a69b529
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575790"
---
# <a name="plan-guides"></a><span data-ttu-id="d95c0-102">Guias de plano</span><span class="sxs-lookup"><span data-stu-id="d95c0-102">Plan Guides</span></span>
  <span data-ttu-id="d95c0-103">Guias de plano permitem otimizar o desempenho das consultas quando você não pode ou não quer alterar diretamente o texto da consulta real no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d95c0-103">Plan guides let you optimize the performance of queries when you cannot or do not want to directly change the text of the actual query in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="d95c0-104">As guias de plano influenciam a otimização das consultas, anexando dicas de consulta ou um plano de consulta fixo.</span><span class="sxs-lookup"><span data-stu-id="d95c0-104">Plan guides influence the optimization of queries by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="d95c0-105">Guias de plano podem ser úteis quando um subconjunto pequeno de consultas em um aplicativo de banco de dados fornecido por um terceiro não estiver executando como esperado.</span><span class="sxs-lookup"><span data-stu-id="d95c0-105">Plan guides can be useful when a small subset of queries in a database application provided by a third-party vendor are not performing as expected.</span></span> <span data-ttu-id="d95c0-106">No guia de plano, especifique a instrução Transact-SQL que deve ser otimizada, e uma cláusula OPTION que contenha as dicas de consulta a serem usadas ou um plano de consulta específico a ser usado para otimizar a consulta.</span><span class="sxs-lookup"><span data-stu-id="d95c0-106">In the plan guide, you specify the Transact-SQL statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="d95c0-107">Quando a consulta é feita, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] corresponde a instrução Transact-SQL com a guia de plano e anexa a cláusula OPTION à consulta em tempo de execução ou usa o plano de consulta especificado.</span><span class="sxs-lookup"><span data-stu-id="d95c0-107">When the query executes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] matches the Transact-SQL statement to the plan guide and attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="d95c0-108">O número total de guias de plano que é possível criar só está limitado através de recursos do sistema disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d95c0-108">The total number of plan guides you can create is limited only by available system resources.</span></span> <span data-ttu-id="d95c0-109">De outro modo, guias de plano devem ser limitados para consultas de missão-crítica que são direcionados para aprimorar ou estabilizar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="d95c0-109">Nevertheless, plan guides should be limited to mission-critical queries that are targeted for improved or stabilized performance.</span></span> <span data-ttu-id="d95c0-110">Guias de plano não podem ser usados para influenciar a maioria da carga de consulta de um aplicativo implantado.</span><span class="sxs-lookup"><span data-stu-id="d95c0-110">Plan guides should not be used to influence most of the query load of a deployed application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d95c0-111">Os guias de plano não podem ser usados em todas as edições do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d95c0-111">Plan guides cannot be used in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d95c0-112">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="d95c0-112">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="d95c0-113">As guias de plano são visíveis em qualquer edição.</span><span class="sxs-lookup"><span data-stu-id="d95c0-113">Plan guides are visible in any edition.</span></span> <span data-ttu-id="d95c0-114">Também é possível anexar um banco de dados contendo guias de plano a qualquer edição.</span><span class="sxs-lookup"><span data-stu-id="d95c0-114">You can also attach a database that contains plan guides to any edition.</span></span> <span data-ttu-id="d95c0-115">Os guias de plano permanecem intactos quando o banco de dados é restaurado ou anexado a uma versão atualizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d95c0-115">Plan guides remain intact when you restore or attach a database to an upgraded version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="types-of-plan-guides"></a><span data-ttu-id="d95c0-116">Tipos de guias de plano</span><span class="sxs-lookup"><span data-stu-id="d95c0-116">Types of Plan Guides</span></span>  
 <span data-ttu-id="d95c0-117">Podem ser criados os tipos de guias de plano a seguir.</span><span class="sxs-lookup"><span data-stu-id="d95c0-117">The following types of plan guides can be created.</span></span>  
  
 <span data-ttu-id="d95c0-118">Guia de plano OBJECT</span><span class="sxs-lookup"><span data-stu-id="d95c0-118">OBJECT plan guide</span></span>  
 <span data-ttu-id="d95c0-119">O guia de plano OBJECT corresponde as consultas executadas no contexto dos procedimentos armazenados do [!INCLUDE[tsql](../../includes/tsql-md.md)] , funções escalares definidas pelo usuário, funções com valor de tabela de várias instruções definidas pelo usuário e gatilhos DML.</span><span class="sxs-lookup"><span data-stu-id="d95c0-119">An OBJECT plan guide matches queries that execute in the context of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, scalar user-defined functions, multi-statement table-valued user-defined functions, and DML triggers.</span></span>  
  
 <span data-ttu-id="d95c0-120">Suponha que o procedimento armazenado a seguir, que usa o parâmetro `@Country`_`region` , esteja em um aplicativo de banco de dados implantado no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d95c0-120">Suppose the following stored procedure, which takes the `@Country`_`region` parameter, is in a database application that is deployed against the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
CREATE PROCEDURE Sales.GetSalesOrderByCountry (@Country_region nvarchar(60))  
AS  
BEGIN  
    SELECT *  
    FROM Sales.SalesOrderHeader AS h, Sales.Customer AS c,   
        Sales.SalesTerritory AS t  
    WHERE h.CustomerID = c.CustomerID  
        AND c.TerritoryID = t.TerritoryID  
        AND CountryRegionCode = @Country_region  
END;  
```  
  
 <span data-ttu-id="d95c0-121">Suponha que esse procedimento armazenado foi compilado e otimizado para `@Country`_`region = N'AU'` (Austrália).</span><span class="sxs-lookup"><span data-stu-id="d95c0-121">Assume that this stored procedure has been compiled and optimized for `@Country`_`region = N'AU'` (Australia).</span></span> <span data-ttu-id="d95c0-122">Entretanto, já que há relativamente poucas vendas oriundas da Austrália, o desempenho cai quando a consulta é executada com os valores de parâmetro de países com mais pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="d95c0-122">However, because there are relatively few sales orders that originate from Australia, performance decreases when the query executes using parameter values of countries with more sales orders.</span></span> <span data-ttu-id="d95c0-123">Como a maioria dos pedidos de vendas tem origem nos Estados Unidos, um plano de consulta gerado para `@Country`\_`region = N'US'` provavelmente teria execução melhor para todos os valores possíveis do parâmetro `@Country`\_`region` .</span><span class="sxs-lookup"><span data-stu-id="d95c0-123">Because the most sales orders originate in the United States, a query plan that is generated for `@Country`\_`region = N'US'` would likely perform better for all possible values of the `@Country`\_`region` parameter.</span></span>  
  
 <span data-ttu-id="d95c0-124">É possível corrigir esse problema ao modificar o procedimento armazenado para adicionar a dica de consulta `OPTIMIZE FOR` à consulta.</span><span class="sxs-lookup"><span data-stu-id="d95c0-124">You could address this problem by modifying the stored procedure to add the `OPTIMIZE FOR` query hint to the query.</span></span> <span data-ttu-id="d95c0-125">Porém, já que o procedimento armazenado está em um aplicativo implantado, não é possível modificar diretamente o código do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d95c0-125">However, because the stored procedure is in a deployed application, you cannot directly modify the application code.</span></span> <span data-ttu-id="d95c0-126">Ao contrário, é possível criar o guia de plano a seguir no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d95c0-126">Instead, you can create the following plan guide in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT *FROM Sales.SalesOrderHeader AS h,  
        Sales.Customer AS c,  
        Sales.SalesTerritory AS t  
        WHERE h.CustomerID = c.CustomerID   
            AND c.TerritoryID = t.TerritoryID  
            AND CountryRegionCode = @Country_region',  
@type = N'OBJECT',  
@module_or_batch = N'Sales.GetSalesOrderByCountry',  
@params = NULL,  
@hints = N'OPTION (OPTIMIZE FOR (@Country_region = N''US''))';  
```  
  
 <span data-ttu-id="d95c0-127">Quando a consulta especificada na instrução `sp_create_plan_guide` é executada, a consulta é modificada antes da otimização para incluir a cláusula `OPTIMIZE FOR (@Country = N''US'')` .</span><span class="sxs-lookup"><span data-stu-id="d95c0-127">When the query specified in the `sp_create_plan_guide` statement executes, the query is modified before optimization to include the `OPTIMIZE FOR (@Country = N''US'')` clause.</span></span>  
  
 <span data-ttu-id="d95c0-128">Guia de plano SQL</span><span class="sxs-lookup"><span data-stu-id="d95c0-128">SQL plan guide</span></span>  
 <span data-ttu-id="d95c0-129">O guia de plano SQL correlaciona consultas que são executadas no contexto de instruções e lotes do [!INCLUDE[tsql](../../includes/tsql-md.md)] autônomo que não fazem parte de um objeto do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d95c0-129">An SQL plan guide matches queries that execute in the context of stand-alone [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and batches that are not part of a database object.</span></span> <span data-ttu-id="d95c0-130">Os guias de plano com base em SQL também podem ser usados para corresponder consultas com parâmetros uma forma especificada.</span><span class="sxs-lookup"><span data-stu-id="d95c0-130">SQL-based plan guides can also be used to match queries that parameterize to a specified form.</span></span> <span data-ttu-id="d95c0-131">Os guias de plano SQL se aplicam a instruções e lotes [!INCLUDE[tsql](../../includes/tsql-md.md)] autônomos.</span><span class="sxs-lookup"><span data-stu-id="d95c0-131">SQL plan guides apply to stand-alone [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and batches.</span></span> <span data-ttu-id="d95c0-132">Frequentemente, essas instruções são submetidas por um aplicativo por meio do procedimento armazenado do sistema [sp_executesql](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d95c0-132">Frequently, these statements are submitted by an application by using the [sp_executesql](/sql/relational-databases/system-stored-procedures/sp-executesql-transact-sql) system stored procedure.</span></span> <span data-ttu-id="d95c0-133">Por exemplo, considere o seguinte lote autônomo:</span><span class="sxs-lookup"><span data-stu-id="d95c0-133">For example, consider the following stand-alone batch:</span></span>  
  
```  
SELECT TOP 1 * FROM Sales.SalesOrderHeader ORDER BY OrderDate DESC;  
```  
  
 <span data-ttu-id="d95c0-134">Para impedir que um plano de execução paralelo seja gerado nessa consulta, crie o guia de plano a seguir e defina a dica de consulta `MAXDOP` como `1` no parâmetro `@hints` .</span><span class="sxs-lookup"><span data-stu-id="d95c0-134">To prevent a parallel execution plan from being generated on this query, create the following plan guide and set the `MAXDOP` query hint to `1` in the `@hints` parameter.</span></span>  
  
```  
sp_create_plan_guide   
@name = N'Guide2',   
@stmt = N'SELECT TOP 1 * FROM Sales.SalesOrderHeader ORDER BY OrderDate DESC',  
@type = N'SQL',  
@module_or_batch = NULL,   
@params = NULL,   
@hints = N'OPTION (MAXDOP 1)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d95c0-135">Os valores fornecidos para os argumentos `@module_or_batch` e `@params` da instrução `sp_create_plan guide` devem coincidir com o texto correspondente submetido na consulta real.</span><span class="sxs-lookup"><span data-stu-id="d95c0-135">The values that are supplied for the `@module_or_batch` and `@params` arguments of the `sp_create_plan guide` statement must match the corresponding text submitted in the actual query.</span></span> <span data-ttu-id="d95c0-136">Para obter mais informações, veja [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) e [Usar o SQL Server Profiler para criar e testar guias de plano](plan-guides.md).</span><span class="sxs-lookup"><span data-stu-id="d95c0-136">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) and [Use SQL Server Profiler to Create and Test Plan Guides](plan-guides.md).</span></span>  
  
 <span data-ttu-id="d95c0-137">Os guias de plano SQL também podem ser criados em consultas com parâmetros da mesma forma quando a opção de banco de dados PARAMETERIZATION for SET to FORCED ou quando um guia de plano TEMPLATE for criado especificando uma classe de consulta com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d95c0-137">SQL plan guides can also be created on queries that parameterize to the same form when the PARAMETERIZATION database option is SET to FORCED, or when a TEMPLATE plan guide is created specifying that a parameterized class of queries.</span></span>  
  
 <span data-ttu-id="d95c0-138">guia de plano TEMPLATE</span><span class="sxs-lookup"><span data-stu-id="d95c0-138">TEMPLATE plan guide</span></span>  
 <span data-ttu-id="d95c0-139">O guia de plano TEMPLATE corresponde consultas autônomas com parâmetros com uma forma especificada.</span><span class="sxs-lookup"><span data-stu-id="d95c0-139">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span> <span data-ttu-id="d95c0-140">Esses guias de plano são usados para substituir a opção SET do banco de dados PARAMETERIZATION atual de um banco de dados para a classe de consultas.</span><span class="sxs-lookup"><span data-stu-id="d95c0-140">These plan guides are used to override the current PARAMETERIZATION database SET option of a database for a class of queries.</span></span>  
  
 <span data-ttu-id="d95c0-141">É possível criar um guia de plano TEMPLATE em qualquer uma das seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="d95c0-141">You can create a TEMPLATE plan guide in either of the following situations:</span></span>  
  
-   <span data-ttu-id="d95c0-142">A opção de banco de dados PARAMETERIZATION é SET to FORCED, mas há consultas que devem ser compiladas de acordo com as regras de parametrização simples.</span><span class="sxs-lookup"><span data-stu-id="d95c0-142">The PARAMETERIZATION database option is SET to FORCED, but there are queries you want compiled according to the rules of simple parameterization.</span></span>  
  
-   <span data-ttu-id="d95c0-143">A opção de banco de dados PARAMETERIZATION é SET to SIMPLE (configuração padrão), mas é preciso que a parametrização forçada seja testada em uma classe de consultas.</span><span class="sxs-lookup"><span data-stu-id="d95c0-143">The PARAMETERIZATION database option is SET to SIMPLE (the default setting), but you want forced parameterization to be tried on a class of queries.</span></span>  
  
## <a name="plan-guide-matching-requirements"></a><span data-ttu-id="d95c0-144">Guia de plano correspondente a requisitos</span><span class="sxs-lookup"><span data-stu-id="d95c0-144">Plan Guide Matching Requirements</span></span>  
 <span data-ttu-id="d95c0-145">Guias de plano são aplicados ao banco de dados no qual eles são criados.</span><span class="sxs-lookup"><span data-stu-id="d95c0-145">Plan guides are scoped to the database in which they are created.</span></span> <span data-ttu-id="d95c0-146">Portanto, somente os guias de plano presentes no banco de dados se tornam atuais quando uma consulta pode ser combinada com outra.</span><span class="sxs-lookup"><span data-stu-id="d95c0-146">Therefore, only plan guides that are in the database that is current when a query executes can be matched to the query.</span></span> <span data-ttu-id="d95c0-147">Por exemplo, se [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] for o banco de dados atual e a consulta seguinte executa:</span><span class="sxs-lookup"><span data-stu-id="d95c0-147">For example, if [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] is the current database and the following query executes:</span></span>  
  
 `SELECT FirstName, LastName FROM Person.Person;`  
  
 <span data-ttu-id="d95c0-148">Somente guias de plano do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] são elegíveis para corresponderem a essa consulta.</span><span class="sxs-lookup"><span data-stu-id="d95c0-148">Only plan guides in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database are eligible to be matched to this query.</span></span> <span data-ttu-id="d95c0-149">Porém, se [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] for o banco de dados atual e as instruções seguintes são executadas:</span><span class="sxs-lookup"><span data-stu-id="d95c0-149">However, if [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] is the current database and the following statements are run:</span></span>  
  
 `USE DB1;`  
  
 `SELECT FirstName, LastName FROM Person.Person;`  
  
 <span data-ttu-id="d95c0-150">Somente os guias de plano no `DB1` são elegíveis para combinar com a consulta porque ela é executada no contexto de `DB1`.</span><span class="sxs-lookup"><span data-stu-id="d95c0-150">Only plan guides in `DB1` are eligible to be matched to the query because the query is executing in the context of `DB1`.</span></span>  
  
 <span data-ttu-id="d95c0-151">Para guias de plano baseados em SQL ou em MODELO, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] faz a correspondência dos valores dos argumentos @module_or_batch and @params com uma consulta, comparando os dois valores, caractere por caractere.</span><span class="sxs-lookup"><span data-stu-id="d95c0-151">For SQL- or TEMPLATE-based plan guides, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] matches the values for the @module_or_batch and @params arguments to a query by comparing the two values character by character.</span></span> <span data-ttu-id="d95c0-152">Isso significa você deve fornecer o texto exatamente como [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recebe no lote atual.</span><span class="sxs-lookup"><span data-stu-id="d95c0-152">This means you must provide the text exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it in the actual batch.</span></span>  
  
 <span data-ttu-id="d95c0-153">Quando @type = 'SQL' e @module_or_batch forem definidos como NULL, o valor @module_or_batch será definido com o valor @stmt. Isso significa que o valor de *statement_text* deve ser fornecido exatamente no mesmo formato, caractere a caractere, como enviado para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d95c0-153">When @type = 'SQL' and @module_or_batch is set to NULL, the value of @module_or_batch is set to the value of @stmt. This means that the value for *statement_text* must be provided in the identical format, character-for-character, as it is submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d95c0-154">Nenhuma conversão interna é executada para facilitar essa correspondência.</span><span class="sxs-lookup"><span data-stu-id="d95c0-154">No internal conversion is performed to facilitate this match.</span></span>  
  
 <span data-ttu-id="d95c0-155">Quando um guia de plano normal (SQL ou OBJECT) e um guia de plano de MODELO puderem ser aplicados a uma instrução, somente o guia de plano normal será usado.</span><span class="sxs-lookup"><span data-stu-id="d95c0-155">When both a regular (SQL or OBJECT) plan guide and a TEMPLATE plan guide can apply to a statement, only the regular plan guide will be used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d95c0-156">O lote que contém a instrução na qual se quer criar o guia de plano não pode conter uma instrução de USE *database* .</span><span class="sxs-lookup"><span data-stu-id="d95c0-156">The batch that contains the statement on which you want to create a plan guide cannot contain a USE *database* statement.</span></span>  
  
## <a name="plan-guide-effect-on-the-plan-cache"></a><span data-ttu-id="d95c0-157">Efeito do guia de plano no cache do esquema</span><span class="sxs-lookup"><span data-stu-id="d95c0-157">Plan Guide Effect on the Plan Cache</span></span>  
 <span data-ttu-id="d95c0-158">Criar um guia de plano em um módulo remove o plano de consulta desse módulo do cache do esquema.</span><span class="sxs-lookup"><span data-stu-id="d95c0-158">Creating a plan guide on a module removes the query plan for that module from the plan cache.</span></span> <span data-ttu-id="d95c0-159">Criar um guia de plano do tipo OBJECT ou SQL em um lote remove o plano de consulta de um lote que tem o mesmo valor de hash.</span><span class="sxs-lookup"><span data-stu-id="d95c0-159">Creating a plan guide of type OBJECT or SQL on a batch removes the query plan for a batch that has the same hash value.</span></span> <span data-ttu-id="d95c0-160">Criar um guia de plano do tipo TEMPLATE remove todos os lotes da instrução única do cache do esquema dentro desse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d95c0-160">Creating a plan guide of type TEMPLATE removes all single-statement batches from the plan cache within that database.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d95c0-161">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d95c0-161">Related Tasks</span></span>  
  
|<span data-ttu-id="d95c0-162">Tarefa</span><span class="sxs-lookup"><span data-stu-id="d95c0-162">Task</span></span>|<span data-ttu-id="d95c0-163">Tópico</span><span class="sxs-lookup"><span data-stu-id="d95c0-163">Topic</span></span>|  
|----------|-----------|  
|<span data-ttu-id="d95c0-164">Descreve como criar um guia de plano.</span><span class="sxs-lookup"><span data-stu-id="d95c0-164">Describes how to create a plan guide.</span></span>|[<span data-ttu-id="d95c0-165">Criar um novo guia de plano</span><span class="sxs-lookup"><span data-stu-id="d95c0-165">Create a New Plan Guide</span></span>](create-a-new-plan-guide.md)|  
|<span data-ttu-id="d95c0-166">Descreve como criar uma guia de plano para consultas parametrizadas.</span><span class="sxs-lookup"><span data-stu-id="d95c0-166">Describes how to create a plan guide for parameterized queries.</span></span>|[<span data-ttu-id="d95c0-167">Criar um guia de plano para consultas parametrizadas</span><span class="sxs-lookup"><span data-stu-id="d95c0-167">Create a Plan Guide for Parameterized Queries</span></span>](create-a-plan-guide-for-parameterized-queries.md)|  
|<span data-ttu-id="d95c0-168">Descreve como controlar o comportamento de parametrização da consulta usando guias de plano.</span><span class="sxs-lookup"><span data-stu-id="d95c0-168">Describes how to control query parameterization behavior by using plan guides.</span></span>|[<span data-ttu-id="d95c0-169">Especificar comportamento de parametrização de consulta usando guias de plano</span><span class="sxs-lookup"><span data-stu-id="d95c0-169">Specify Query Parameterization Behavior by Using Plan Guides</span></span>](specify-query-parameterization-behavior-by-using-plan-guides.md)|  
|<span data-ttu-id="d95c0-170">Descreve como incluir um plano de consulta fixo em um guia de plano.</span><span class="sxs-lookup"><span data-stu-id="d95c0-170">Describes how to include a fixed query plan in a plan guide.</span></span>|[<span data-ttu-id="d95c0-171">Aplicar um plano de consulta fixo a um guia de plano</span><span class="sxs-lookup"><span data-stu-id="d95c0-171">Apply a Fixed Query Plan to a Plan Guide</span></span>](apply-a-fixed-query-plan-to-a-plan-guide.md)|  
|<span data-ttu-id="d95c0-172">Descreve como especificar dicas de consulta em um guia de plano.</span><span class="sxs-lookup"><span data-stu-id="d95c0-172">Describes how to specify query hints in a plan guide.</span></span>|[<span data-ttu-id="d95c0-173">Anexar dicas de consulta a um guia de plano</span><span class="sxs-lookup"><span data-stu-id="d95c0-173">Attach Query Hints to a Plan Guide</span></span>](attach-query-hints-to-a-plan-guide.md)|  
|<span data-ttu-id="d95c0-174">Descreve como exibir propriedades do guia de plano.</span><span class="sxs-lookup"><span data-stu-id="d95c0-174">Describes how to view plan guide properties.</span></span>|[<span data-ttu-id="d95c0-175">Exibir propriedades do guia de plano</span><span class="sxs-lookup"><span data-stu-id="d95c0-175">View Plan Guide Properties</span></span>](view-plan-guide-properties.md)|  
|<span data-ttu-id="d95c0-176">Descreve como usar o SQL Server Profiler para criar e testar guias de plano.</span><span class="sxs-lookup"><span data-stu-id="d95c0-176">Describes how to use SQL Server Profiler to create and test plan guides.</span></span>|[<span data-ttu-id="d95c0-177">Usar o SQL Server Profiler para criar e testar guias de plano</span><span class="sxs-lookup"><span data-stu-id="d95c0-177">Use SQL Server Profiler to Create and Test Plan Guides</span></span>](plan-guides.md)|  
|<span data-ttu-id="d95c0-178">Descreve como validar guias de plano.</span><span class="sxs-lookup"><span data-stu-id="d95c0-178">Describes how to validate plan guides.</span></span>|[<span data-ttu-id="d95c0-179">Validar guias de plano depois da atualização</span><span class="sxs-lookup"><span data-stu-id="d95c0-179">Validate Plan Guides After Upgrade</span></span>](validate-plan-guides-after-upgrade.md)|  
  
## <a name="see-also"></a><span data-ttu-id="d95c0-180">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d95c0-180">See Also</span></span>  
 <span data-ttu-id="d95c0-181">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d95c0-181">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="d95c0-182">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d95c0-182">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span></span>  
 <span data-ttu-id="d95c0-183">[sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d95c0-183">[sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="d95c0-184">[sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d95c0-184">[sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql) </span></span>  
 [<span data-ttu-id="d95c0-185">sys.fn_validate_plan_guide &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d95c0-185">sys.fn_validate_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql)  
  
  
