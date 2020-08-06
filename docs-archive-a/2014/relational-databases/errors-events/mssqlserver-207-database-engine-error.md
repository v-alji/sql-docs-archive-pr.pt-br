---
title: MSSQLSERVER_207 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 207 (Database Engine error)
ms.assetid: d1ab00c7-0331-437a-84fe-bae53b82feec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd6044c08ecd5a73f539bfbc1139d6257c2db9d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679973"
---
# <a name="mssqlserver_207"></a><span data-ttu-id="d2aab-102">MSSQLSERVER_207</span><span class="sxs-lookup"><span data-stu-id="d2aab-102">MSSQLSERVER_207</span></span>
    
## <a name="details"></a><span data-ttu-id="d2aab-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d2aab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2aab-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d2aab-104">Product Name</span></span>|<span data-ttu-id="d2aab-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d2aab-105">SQL Server</span></span>|  
|<span data-ttu-id="d2aab-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d2aab-106">Event ID</span></span>|<span data-ttu-id="d2aab-107">207</span><span class="sxs-lookup"><span data-stu-id="d2aab-107">207</span></span>|  
|<span data-ttu-id="d2aab-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d2aab-108">Event Source</span></span>|<span data-ttu-id="d2aab-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d2aab-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d2aab-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d2aab-110">Component</span></span>|<span data-ttu-id="d2aab-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d2aab-111">SQLEngine</span></span>|  
|<span data-ttu-id="d2aab-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d2aab-112">Symbolic Name</span></span>|<span data-ttu-id="d2aab-113">SQ_BADCOL</span><span class="sxs-lookup"><span data-stu-id="d2aab-113">SQ_BADCOL</span></span>|  
|<span data-ttu-id="d2aab-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d2aab-114">Message Text</span></span>|<span data-ttu-id="d2aab-115">Nome de coluna inválido '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="d2aab-115">Invalid column name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d2aab-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="d2aab-116">Explanation</span></span>  
 <span data-ttu-id="d2aab-117">Esse erro de consulta pode ser provocado por um dos problemas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d2aab-117">This query error can be caused by one of the following problems.</span></span>  
  
-   <span data-ttu-id="d2aab-118">O nome da coluna foi digitado incorretamente ou a coluna não existe em nenhuma das tabelas especificadas.</span><span class="sxs-lookup"><span data-stu-id="d2aab-118">The column name is misspelled or the column does not exist in any of the specified tables.</span></span>  
  
-   <span data-ttu-id="d2aab-119">A ordenação do banco de dados diferencia maiúsculas e minúsculas e as maiúsculas e minúsculas do nome da coluna especificado na consulta não correspondem às maiúsculas e minúsculas definidas na tabela.</span><span class="sxs-lookup"><span data-stu-id="d2aab-119">The collation of the database is case-sensitive and the case of the column name specified in the query does not match the case of the column defined in the table.</span></span> <span data-ttu-id="d2aab-120">Por exemplo, quando uma coluna estiver definida em uma tabela como **LastName** e o banco de dados usar uma ordenação com diferenciação de maiúsculas e minúsculas, as consultas que fizerem referência à coluna como **Lastname** ou **lastname** retornarão o erro 207, pois o nome da coluna não é correspondente.</span><span class="sxs-lookup"><span data-stu-id="d2aab-120">For example, when a column is defined in a table as **LastName** and the database uses a case-sensitive collation, queries that refer to the column as **Lastname** or **lastname** will cause error 207 to return because the column name does not match.</span></span>  
  
-   <span data-ttu-id="d2aab-121">Um alias de coluna definido na cláusula SELECT é referenciado em outra cláusula, como em uma cláusula WHERE ou GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="d2aab-121">A column alias, defined in the SELECT clause, is referenced in another clause such as a WHERE or GROUP BY clause.</span></span> <span data-ttu-id="d2aab-122">Por exemplo, a consulta a seguir define o alias de coluna `Year` na cláusula SELECT e faz referência a ele na cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="d2aab-122">For example, the following query defines the column alias `Year` in the SELECT clause and refers to it in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year, SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY Year;  
    ```  
  
     <span data-ttu-id="d2aab-123">Devido à ordem em que as cláusulas da consulta são processadas logicamente, o exemplo retorna o erro 207.</span><span class="sxs-lookup"><span data-stu-id="d2aab-123">Due to the order in which query clauses are logically processed, the example returns error 207.</span></span> <span data-ttu-id="d2aab-124">A ordem do processamento é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="d2aab-124">The processing order is as follows:</span></span>  
  
    1.  <span data-ttu-id="d2aab-125">FROM</span><span class="sxs-lookup"><span data-stu-id="d2aab-125">FROM</span></span>  
  
    2.  <span data-ttu-id="d2aab-126">ATIVADO</span><span class="sxs-lookup"><span data-stu-id="d2aab-126">ON</span></span>  
  
    3.  <span data-ttu-id="d2aab-127">JOIN</span><span class="sxs-lookup"><span data-stu-id="d2aab-127">JOIN</span></span>  
  
    4.  <span data-ttu-id="d2aab-128">WHERE</span><span class="sxs-lookup"><span data-stu-id="d2aab-128">WHERE</span></span>  
  
    5.  <span data-ttu-id="d2aab-129">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="d2aab-129">GROUP BY</span></span>  
  
    6.  <span data-ttu-id="d2aab-130">WITH CUBE ou WITH ROLLUP</span><span class="sxs-lookup"><span data-stu-id="d2aab-130">WITH CUBE or WITH ROLLUP</span></span>  
  
    7.  <span data-ttu-id="d2aab-131">HAVING</span><span class="sxs-lookup"><span data-stu-id="d2aab-131">HAVING</span></span>  
  
    8.  <span data-ttu-id="d2aab-132">SELECT</span><span class="sxs-lookup"><span data-stu-id="d2aab-132">SELECT</span></span>  
  
    9. <span data-ttu-id="d2aab-133">DISTINTO</span><span class="sxs-lookup"><span data-stu-id="d2aab-133">DISTINCT</span></span>  
  
    10. <span data-ttu-id="d2aab-134">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d2aab-134">ORDER BY</span></span>  
  
    11. <span data-ttu-id="d2aab-135">INÍCIO</span><span class="sxs-lookup"><span data-stu-id="d2aab-135">TOP</span></span>  
  
     <span data-ttu-id="d2aab-136">Como um alias de coluna não é definido até que a cláusula SELECT seja processada, o nome do alias é desconhecido quando a cláusula GROUP BY é processada.</span><span class="sxs-lookup"><span data-stu-id="d2aab-136">Because a column alias is not defined until the SELECT clause is processed, the alias name is unknown when the GROUP BY clause is processed.</span></span>  
  
-   <span data-ttu-id="d2aab-137">A instrução MERGE aciona esse erro quando a cláusula *<merge_matched>* referencia colunas na tabela de origem, mas nenhuma linha é retornada pela tabela de origem na cláusula WHEN NOT MATCHED BY SOURCE.</span><span class="sxs-lookup"><span data-stu-id="d2aab-137">The MERGE statement raises this error when the *<merge_matched>* clause references columns in the source table but no rows are returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="d2aab-138">O erro ocorre porque as colunas na tabela de origem não podem ser acessadas quando nenhuma linha é retornada para a consulta.</span><span class="sxs-lookup"><span data-stu-id="d2aab-138">The error occurs because the columns in the source table cannot be accessed when no rows are returned to the query.</span></span> <span data-ttu-id="d2aab-139">Por exemplo, a cláusula `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` poderá fazer com que a instrução falhe se `Col1` estiver inacessível na tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="d2aab-139">For example, the clause `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` may cause the statement to fail if `Col1` in the source table is inaccessible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2aab-140">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d2aab-140">User Action</span></span>  
 <span data-ttu-id="d2aab-141">Verifique as informações a seguir e corrija a instrução conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="d2aab-141">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="d2aab-142">O nome da coluna existe na tabela e está digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="d2aab-142">The column name exists in the table and is spelled correctly.</span></span> <span data-ttu-id="d2aab-143">O exemplo a seguir consulta a exibição do catálogo **sys.columns** para retornar todos os nomes de colunas de determinada tabela.</span><span class="sxs-lookup"><span data-stu-id="d2aab-143">The following example queries the **sys.columns** catalog view to return all column names for a given table.</span></span>  
  
    ```  
    SELECT name FROM sys.columns WHERE object_id = OBJECT_ID('schema_name.table_name');  
    ```  
  
-   <span data-ttu-id="d2aab-144">A diferenciação de maiúsculas e minúsculas da ordenação de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d2aab-144">The case sensitivity of the database collation.</span></span> <span data-ttu-id="d2aab-145">A instrução a seguir retorna a ordenação do banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="d2aab-145">The following statement returns the collation of the specified database.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="d2aab-146">A abreviação CS no nome da ordenação indica que ela diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d2aab-146">The abbreviation CS in the collation name indicates the collation is case-sensitive.</span></span> <span data-ttu-id="d2aab-147">Por exemplo, Latin1_General_CS_AS é uma ordenação que tem diferenciação de maiúsculas e minúsculas e de acentos.</span><span class="sxs-lookup"><span data-stu-id="d2aab-147">For example, Latin1_General_CS_AS is a case-sensitive and accent-sensitive collation.</span></span> <span data-ttu-id="d2aab-148">Modifique o nome da coluna para que coincida com as maiúsculas e minúsculas do nome da coluna conforme definido na tabela.</span><span class="sxs-lookup"><span data-stu-id="d2aab-148">Modify the column name to match the case of the column name as it is defined in the table.</span></span>  
  
-   <span data-ttu-id="d2aab-149">O alias de uma coluna está referenciado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="d2aab-149">A column alias is referenced incorrectly.</span></span> <span data-ttu-id="d2aab-150">Modifique a instrução repetindo a expressão que define o alias na cláusula adequada ou usando uma tabela derivada.</span><span class="sxs-lookup"><span data-stu-id="d2aab-150">Modify the statement by repeating the expression that defines the alias in the appropriate clause or by using a derived table.</span></span> <span data-ttu-id="d2aab-151">O exemplo a seguir repete as expressões que definem o alias `Year` na cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="d2aab-151">The following example repeats the expressions that define the `Year` alias in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year ,SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY DATEPART(yyyy,OrderDate);  
    ```  
  
     <span data-ttu-id="d2aab-152">O exemplo a seguir usa uma tabela derivada para disponibilizar o nome do alias para outras cláusulas na consulta.</span><span class="sxs-lookup"><span data-stu-id="d2aab-152">The following example uses a derived table to make the alias name available to other clauses in the query.</span></span> <span data-ttu-id="d2aab-153">Observe que o alias `Year` está definido na cláusula FROM que é processada primeiro e, portanto, disponibiliza o alias para uso em outras cláusulas na consulta.</span><span class="sxs-lookup"><span data-stu-id="d2aab-153">Notice that the alias `Year` is defined in the FROM clause, which is processed first, and so makes the alias available for use in other clauses in the query.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT d.Year, SUM(TotalDue) AS Total  
    FROM (SELECT DATEPART(yyyy,OrderDate) AS Year, TotalDue  
          FROM Sales.SalesOrderHeader)AS d  
    GROUP BY Year;  
    ```  
  
-   <span data-ttu-id="d2aab-154">A cláusula WHEN NOT MATCHED BY SOURCE na instrução MERGE faz referência a um valor que pode ser acessado.</span><span class="sxs-lookup"><span data-stu-id="d2aab-154">The WHEN NOT MATCHED BY SOURCE clause in the MERGE statement refers to a value that can be accessed.</span></span> <span data-ttu-id="d2aab-155">Modifique a instrução MERGE de forma que pelo menos uma linha seja retornada pela tabela de origem na cláusula WHEN NOT MATCHED BY SOURCE.</span><span class="sxs-lookup"><span data-stu-id="d2aab-155">Modify the MERGE statement so that at least one row is returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="d2aab-156">Por exemplo, talvez você precise adicionar ou revisar a condição da pesquisa especificada para a cláusula.</span><span class="sxs-lookup"><span data-stu-id="d2aab-156">For example, you might need to add or revise the search condition specified for the clause.</span></span> <span data-ttu-id="d2aab-157">Como alternativa, é possível modificar a cláusula para especificar um valor que não faz referência à tabela de origem.</span><span class="sxs-lookup"><span data-stu-id="d2aab-157">Alternatively, you can modify the clause to specify a value that does not reference the source table.</span></span> <span data-ttu-id="d2aab-158">Por exemplo, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span><span class="sxs-lookup"><span data-stu-id="d2aab-158">For example, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2aab-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d2aab-159">See Also</span></span>  
 <span data-ttu-id="d2aab-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2aab-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span></span>  
 <span data-ttu-id="d2aab-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2aab-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span></span>  
 <span data-ttu-id="d2aab-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2aab-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="d2aab-163">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2aab-163">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
