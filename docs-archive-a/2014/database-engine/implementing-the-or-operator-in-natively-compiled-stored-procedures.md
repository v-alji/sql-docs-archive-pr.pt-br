---
title: Implementando o operador OR em procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2528e74-2b1c-48cb-861b-c4e57b51ac35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ed762e062cbc6831eb46784ef71fc7889850676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681841"
---
# <a name="implementing-the-or-operator-in-natively-compiled-stored-procedures"></a><span data-ttu-id="979f2-102">Implementando o operador OR em procedimentos armazenados compilados de modo nativo</span><span class="sxs-lookup"><span data-stu-id="979f2-102">Implementing the OR Operator in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="979f2-103">Não há suporte para os operadores OR nos predicados de consulta em procedimentos armazenados compilados de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="979f2-103">OR operators are not supported in query predicates in natively compiled stored procedures.</span></span> <span data-ttu-id="979f2-104">Como também não há suporte para os operadores NOT nos predicados de consulta em procedimentos armazenados compilados de modo nativo, os efeitos dos operadores OR não podem ser simulados apenas através do uso de operadores lógicos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="979f2-104">Because NOT operators are also not supported in query predicates in natively compiled stored procedures, the effects of OR operators cannot be simulated through the use of equivalent logical operators alone.</span></span> <span data-ttu-id="979f2-105">No entanto, os efeitos de um operador OR podem ser simulados com variáveis de tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="979f2-105">However, the effects of an OR operator may be simulated with memory-optimized table variables.</span></span>  
  
## <a name="or-operator-in-where-clause"></a><span data-ttu-id="979f2-106">Operador OR na cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="979f2-106">OR Operator in WHERE Clause</span></span>  
 <span data-ttu-id="979f2-107">Se você tiver um operador OR na cláusula WHERE, poderá usar a abordagem a seguir para simular seu comportamento:</span><span class="sxs-lookup"><span data-stu-id="979f2-107">If you have an OR operator in a WHERE clause, you can use the following approach to simulate its behavior:</span></span>  
  
1.  <span data-ttu-id="979f2-108">Crie uma variável de tabela com otimização de memória usando o esquema apropriado.</span><span class="sxs-lookup"><span data-stu-id="979f2-108">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="979f2-109">Isso requer um tipo de tabela com otimização de memória predefinido.</span><span class="sxs-lookup"><span data-stu-id="979f2-109">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="979f2-110">Começando com o operador OR de nível superior, separe a cláusula WHERE em duas partes de acordo com os predicados unidos pelo operador OR.</span><span class="sxs-lookup"><span data-stu-id="979f2-110">Starting with the top level OR operator, separate the WHERE clause into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="979f2-111">Se houver mais de um operador OR em uma cláusula WHERE, talvez seja necessário fazer isso mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="979f2-111">If you have more than one OR operator in a WHERE clause, you may need to do this more than once.</span></span> <span data-ttu-id="979f2-112">Repita essa etapa até que não reste nenhum operador OR.</span><span class="sxs-lookup"><span data-stu-id="979f2-112">Repeat this step until no OR operators remain.</span></span> <span data-ttu-id="979f2-113">Por exemplo, se você tiver o seguinte predicado:</span><span class="sxs-lookup"><span data-stu-id="979f2-113">For example, if you have the following predicate:</span></span>  
  
    ```  
    pred1 OR (pred2 AND (pred3 OR pred4)) OR (pred5 AND pred6)  
    ```  
  
     <span data-ttu-id="979f2-114">Depois dessa etapa, você terá os seguintes predicados:</span><span class="sxs-lookup"><span data-stu-id="979f2-114">After this step, you should have the following predicates:</span></span>  
  
    ```  
    pred1  
    pred5 AND pred6  
    pred2 AND pred3  
    pred2 AND pred4  
    ```  
  
3.  <span data-ttu-id="979f2-115">Executar uma consulta com cada uma das duas partes encontradas na etapa 2 como predicado.</span><span class="sxs-lookup"><span data-stu-id="979f2-115">Execute a query with each of the two parts found in Step 2 as the predicate.</span></span> <span data-ttu-id="979f2-116">Insira o resultado de cada consulta na variável de tabela com otimização de memória criada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="979f2-116">Insert the result for each query into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="979f2-117">Se necessário, remova as duplicatas da variável de tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="979f2-117">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="979f2-118">Use o conteúdo da variável de tabela com otimização de memória como resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="979f2-118">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="979f2-119">O exemplo a seguir usa tabelas do banco de dados AdventureWorks2012 que foram atualizadas no [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="979f2-119">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="979f2-120">Para baixar os arquivos para este exemplo, vá para [bancos de dados AdventureWorks-2012, 2008R2 e 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="979f2-120">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="979f2-121">Para aplicar o [!INCLUDE[hek_2](../includes/hek-2-md.md)] exemplo de código a AdventureWorks2012, acesse [SQL Server exemplo de OLTP em memória 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="979f2-121">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="979f2-122">Adicione o seguinte procedimento armazenado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="979f2-122">Add the following stored procedure to the database.</span></span> <span data-ttu-id="979f2-123">Converteremos esse procedimento armazenado para usar a compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="979f2-123">We will convert this stored procedure to use native compilation.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_ondisk  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
AS BEGIN  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  WHERE  s.SalesOrderId = @SalesOrderId  
      OR s.SalesOrderDetailId = @SalesOrderDetailId  
      OR s.CarrierTrackingNumber = @CarrierTrackingNumber  
      OR s.ProductID = @ProductId  
      OR (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
END  
GO  
```  
  
 <span data-ttu-id="979f2-124">Após a conversão, o esquema da tabela e do procedimento armazenado será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="979f2-124">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesOrderDetailType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailTempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  recordcount int not null  
  INDEX ix_fuzzySearchSalesOrderDetailTempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_inmem  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.fuzzySearchSalesOrderDetailType  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderId = @SalesOrderId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderDetailId = @SalesOrderDetailId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.CarrierTrackingNumber COLLATE Latin1_General_BIN2 = @CarrierTrackingNumber COLLATE Latin1_General_BIN2   
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.ProductID = @ProductId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
  
  -- After the above statements, there will be duplicates inside @retValue  
  -- Delete the duplicates from @retValue  
  DECLARE @duplicates Sales.fuzzySearchSalesOrderDetailTempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, recordcount)   
  SELECT SalesOrderId, SalesOrderDetailId, COUNT(*) AS recordCount  
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId  
  
  -- Now we have one row per pair  
  -- clear and rebuild the result set  
  DELETE FROM @retValue  
  
  INSERT INTO @retValue  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates d ON s.SalesOrderId = d.SalesOrderId AND s.SalesOrderDetailId = d.SalesOrderDetailId  
  
  -- After this every pair of (SalesOrderId, SalesOrderDetailId) in @retValue should be unique.  
  SELECT SalesorderId, SalesOrderDetailId, ModifiedDate FROM @retValue  
END  
GO  
```  
  
## <a name="or-operator-in-join-condition"></a><span data-ttu-id="979f2-125">Operador OR na condição JOIN</span><span class="sxs-lookup"><span data-stu-id="979f2-125">OR Operator in JOIN Condition</span></span>  
 <span data-ttu-id="979f2-126">Se você tiver um operador OR na condição JOIN de uma instrução SELECT, poderá usar a abordagem a seguir para simular seu comportamento.</span><span class="sxs-lookup"><span data-stu-id="979f2-126">If you have an OR operator in a JOIN condition of a SELECT statement, you may use the following approach to simulate its behavior.</span></span> <span data-ttu-id="979f2-127">Se houver mais de um operador OR em uma condição JOIN ou várias condições JOIN com operadores OR, talvez seja necessário fazer isso mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="979f2-127">If you have more than one OR operator in a JOIN condition or you have multiple JOIN condition with OR operators, you may need to do this more than once.</span></span>  
  
 <span data-ttu-id="979f2-128">Se você tiver condições OUTER JOIN, poderá combinar essa solução com a solução das condições OUTER JOIN.</span><span class="sxs-lookup"><span data-stu-id="979f2-128">If you have OUTER JOIN conditions, you may combine this workaround with the workaround for OUTER JOIN conditions.</span></span>  
  
1.  <span data-ttu-id="979f2-129">Crie uma variável de tabela com otimização de memória usando o esquema apropriado.</span><span class="sxs-lookup"><span data-stu-id="979f2-129">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="979f2-130">Isso requer um tipo de tabela com otimização de memória predefinido.</span><span class="sxs-lookup"><span data-stu-id="979f2-130">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="979f2-131">Separe o predicado na condição JOIN em duas partes de acordo com os predicados unidos pelo operador OR.</span><span class="sxs-lookup"><span data-stu-id="979f2-131">Separate the predicate in the JOIN condition into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="979f2-132">Se você tiver várias condições JOIN, talvez precise fazer isso em cada condição JOIN e criar um conjunto de combinações dos fragmentos resultantes.</span><span class="sxs-lookup"><span data-stu-id="979f2-132">If you have multiple JOIN conditions, you may need to do this for each JOIN condition and then create a set of combinations of the resulting fragments.</span></span> <span data-ttu-id="979f2-133">Por exemplo, se você tiver três condições JOIN com um operador OR em cada condição JOIN, talvez tenha os predicados 2x2x2=8.</span><span class="sxs-lookup"><span data-stu-id="979f2-133">For example, if you have three JOIN conditions with one OR operator in each JOIN condition, you may have 2x2x2=8 predicates.</span></span>  
  
3.  <span data-ttu-id="979f2-134">Para cada predicado gerado pela etapa 2, crie uma consulta que inserirá o resultado na variável de tabela com otimização de memória criada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="979f2-134">For each predicate produced by Step 2, create a query that will insert its result into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="979f2-135">Se necessário, remova as duplicatas da variável de tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="979f2-135">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="979f2-136">Use o conteúdo da variável de tabela com otimização de memória como resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="979f2-136">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="979f2-137">O exemplo a seguir usa tabelas do banco de dados AdventureWorks2012 que foram atualizadas no [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="979f2-137">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="979f2-138">Para baixar os arquivos para este exemplo, vá para [bancos de dados AdventureWorks-2012, 2008R2 e 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="979f2-138">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="979f2-139">Para aplicar o [!INCLUDE[hek_2](../includes/hek-2-md.md)] exemplo de código a AdventureWorks2012, acesse [SQL Server exemplo de OLTP em memória 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="979f2-139">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="979f2-140">Adicione o seguinte procedimento armazenado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="979f2-140">Add the following stored procedure to the database.</span></span> <span data-ttu-id="979f2-141">Converteremos esse procedimento armazenado para usar a compilação nativa.</span><span class="sxs-lookup"><span data-stu-id="979f2-141">We will convert this stored procedure to use native compilation.</span></span> <span data-ttu-id="979f2-142">Esse exemplo usa condições INNER JOIN.</span><span class="sxs-lookup"><span data-stu-id="979f2-142">This sample uses INNER JOIN conditions.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_ondisk  
  @SpecialOfferId int  
AS BEGIN  
  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  JOIN Sales.SpecialOffer_onDisk offer   
    ON s.SpecialOfferID = offer.SpecialOfferID   
    OR s.ProductID IN (SELECT ProductId FROM Sales.SpecialOfferProduct sop WHERE sop.SpecialOfferID = @SpecialOfferId)  
END  
```  
  
 <span data-ttu-id="979f2-143">Após a conversão, o esquema da tabela e do procedimento armazenado será o seguinte:</span><span class="sxs-lookup"><span data-stu-id="979f2-143">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_Type AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesSpecialOffers_Type NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_TempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  recordcount int null  
  INDEX ix_fuzzySearchSalesSpecialOffers_TempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_inmem  
  @SpecialOfferId int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.FuzzySearchSalesSpecialOffers_Type  
  
  -- Find all special offers matching the conditions  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOffer_inmem offer   
    ON s.SpecialOfferID = offer.SpecialOfferID  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOfferProduct_inmem sop   
    ON sop.SpecialOfferId = @SpecialOfferId AND s.ProductID = sop.ProductId  
  
  -- Now we need to remove the duplicates from @matchingSpecialOffers  
  DECLARE @duplicates Sales.fuzzySearchSalesSpecialOffers_TempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, SpecialOfferid, recordcount)  
  SELECT SalesOrderId, SalesOrderDetailId, SpecialOfferId, COUNT(*)   
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId, SpecialOfferId  
  
  -- now there should be no duplicates within @duplicate  
  -- use @duplicate for join.  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates offer   
    ON    s.SalesOrderId = offer.SalesOrderId   
      AND s.SalesOrderDetailId = offer.SalesOrderDetailID   
      AND s.SpecialOfferId = offer.SpecialOfferId  
END  
GO  
```  
  
## <a name="side-effects"></a><span data-ttu-id="979f2-144">Efeitos colaterais</span><span class="sxs-lookup"><span data-stu-id="979f2-144">Side Effects</span></span>  
 <span data-ttu-id="979f2-145">Se houver mais de um operador OR na cláusula WHERE ou na condição JOIN, o número de consultas que você precisa executar para simular o comportamento pode aumentar exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="979f2-145">If you have more than one OR operator in the WHERE clause or JOIN condition, the number of queries you need to execute to simulate the behavior may increase exponentially.</span></span> <span data-ttu-id="979f2-146">Isso pode reduzir o desempenho da consulta e aumentar o uso da memória devido à necessidade de uso das variáveis de tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="979f2-146">This may slow down query performance and may increase memory usage due to the need to use memory-optimized table variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="979f2-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="979f2-147">See Also</span></span>  
 [<span data-ttu-id="979f2-148">Problemas de migração para procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="979f2-148">Migration Issues for Natively Compiled Stored Procedures</span></span>](../relational-databases/in-memory-oltp/migration-issues-for-natively-compiled-stored-procedures.md)  
  
