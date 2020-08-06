---
title: Implementando uma instrução CASE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 2f82db01-da7e-4a7d-8bc0-48b245e6f768
author: rothja
ms.author: jroth
ms.openlocfilehash: 27059cc09d5507bf2548b23b60f3c2f485c3fe36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684216"
---
# <a name="implementing-a-case-statement"></a><span data-ttu-id="3148b-102">Implementando uma instrução CASE</span><span class="sxs-lookup"><span data-stu-id="3148b-102">Implementing a CASE Statement</span></span>
  <span data-ttu-id="3148b-103">As instruções case não têm suporte em procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="3148b-103">Case statements are not supported in natively compiled stored procedures.</span></span> <span data-ttu-id="3148b-104">O exemplo a seguir mostra uma maneira de implementar a funcionalidade de uma instrução case em um procedimento armazenado compilado nativamente.</span><span class="sxs-lookup"><span data-stu-id="3148b-104">The following sample shows a way to implement the functionality of a case statement in a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="3148b-105">Os exemplos usam uma variável de tabela para criar um único conjunto de resultados, que só é adequado ao processar um número limitado de linhas, pois ele envolve a criação de uma cópia adicional das linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="3148b-105">The samples uses a table variable to construct a single result set, which is only suitable when processing a limited number of rows, as it involves creating an additional copy of the data rows.</span></span>  
  
 <span data-ttu-id="3148b-106">Você deve testar o desempenho dessa solução alternativa, para garantir que ela seja executada como esperado em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3148b-106">You should test the performance of this workaround, to be sure that it performs as expected in your application.</span></span>  
  
```  
-- original query  
SELECT   
   SalesOrderID,   
   CASE (OnlineOrderFlag)   
   WHEN 1 THEN N'Order placed online by customer'  
   ELSE N'Order placed by sales person'  
   END  
FROM Sales.SalesOrderHeader_inmem  
  
--  workaround for CASE in natively compiled stored procedures  
--  use a table for the single resultset  
CREATE TYPE dbo.SOHOnlineOrderResult AS TABLE  
(  
   SalesOrderID uniqueidentifier not null index ix_SalesOrderID,  
     OrderFlag nvarchar(100) not null  
) with (memory_optimized=on)  
go  
  
-- natively compiled stored procedure that includes the query  
CREATE PROCEDURE dbo.usp_SOHOnlineOrderResult  
   WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
   AS BEGIN ATOMIC WITH  
      (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE=N'us_english')  
  
   -- table variable for creating the single resultset  
   DECLARE @result dbo.SOHOnlineOrderResult  
  
   -- CASE OnlineOrderFlag=1  
   INSERT @result   
   SELECT SalesOrderID, N'Order placed online by customer'  
      FROM Sales.SalesOrderHeader_inmem  
      WHERE OnlineOrderFlag=1  
  
   -- ELSE  
   INSERT @result   
   SELECT SalesOrderID, placed by sales person'  
      FROM Sales.SalesOrderHeader_inmem  
      WHERE OnlineOrderFlag!=1  
  
   -- return single resultset  
   SELECT SalesOrderID, OrderFlag FROM @result  
END  
GO  
  
EXEC dbo.usp_SOHOnlineOrderResult  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3148b-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3148b-107">See Also</span></span>  
 <span data-ttu-id="3148b-108">[Problemas de migração para procedimentos armazenados compilados nativamente](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="3148b-108">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="3148b-109">Construções do Transact-SQL sem suporte pelo OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="3148b-109">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
