---
title: Criando e acessando tabelas em TempDB de procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 12be8011-b76c-45c1-8f55-7f46e0e374e9
author: rothja
ms.author: jroth
ms.openlocfilehash: a0bd2b4863cc3c257cd260bf381ebb3b890af219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685149"
---
# <a name="creating-and-accessing-tables-in-tempdb-from-natively-compiled-stored-procedures"></a><span data-ttu-id="a14d5-102">Criando e acessando tabelas em TempDB de procedimentos armazenados nativamente compilados</span><span class="sxs-lookup"><span data-stu-id="a14d5-102">Creating and Accessing Tables in TempDB from Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="a14d5-103">Não há suporte para criar e acessar tabelas em TempDB de procedimentos armazenados nativamente compilados.</span><span class="sxs-lookup"><span data-stu-id="a14d5-103">Creating and accessing tables in TempDB from natively compiled stored procedures is not supported.</span></span> <span data-ttu-id="a14d5-104">Use tipos e variáveis de tabela.</span><span class="sxs-lookup"><span data-stu-id="a14d5-104">Instead, use table types and table variables.</span></span> <span data-ttu-id="a14d5-105">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a14d5-105">For example:</span></span>  
  
```sql  
CREATE TYPE dbo.OrderQuantityByProduct   
  AS TABLE   
   (id INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=100000),   
    ProductID INT NOT NULL,   
    Quantity INT NOT NULL) WITH (MEMORY_OPTIMIZED=ON)  
GO  
CREATE PROCEDURE dbo.usp_OrderQuantityByProduct   
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH   
(  
    TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
    LANGUAGE = 'english'  
)  
  -- declare table variables for the list of orders   
  DECLARE @Input dbo.OrderQuantityByProduct  
  
  -- populate input  
  INSERT @Input SELECT ProductID, Quantity FROM dbo.[Order Details]  
  end  
```  
  
## <a name="see-also"></a><span data-ttu-id="a14d5-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a14d5-106">See Also</span></span>  
 <span data-ttu-id="a14d5-107">[Problemas de migração para procedimentos armazenados compilados nativamente](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a14d5-107">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="a14d5-108">Construções do Transact-SQL sem suporte pelo OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="a14d5-108">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
