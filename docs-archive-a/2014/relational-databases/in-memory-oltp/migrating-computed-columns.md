---
title: Migrando colunas computadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 64a9eade-22c3-4a9d-ab50-956219e08df1
author: rothja
ms.author: jroth
ms.openlocfilehash: feb50ef64f42d95913ad4e13f9a79e6e0e4ecad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685694"
---
# <a name="migrating-computed-columns"></a><span data-ttu-id="71675-102">Criando colunas computadas</span><span class="sxs-lookup"><span data-stu-id="71675-102">Migrating Computed Columns</span></span>
  <span data-ttu-id="71675-103">As colunas computadas não têm suporte em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="71675-103">Computed columns are not supported in memory-optimized tables.</span></span> <span data-ttu-id="71675-104">No entanto, você pode simular uma coluna computada.</span><span class="sxs-lookup"><span data-stu-id="71675-104">However, you can simulate a computed column.</span></span>  
  
 <span data-ttu-id="71675-105">Considere a necessidade da persistência de suas colunas computadas ao migrar as tabelas baseadas em disco para as tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="71675-105">You should consider the need to persist your computed columns when you migrate your disk-based tables to memory-optimized tables.</span></span> <span data-ttu-id="71675-106">As diferentes características de desempenho das tabelas com otimização de memória e dos procedimentos armazenados compilados nativamente podem negar a necessidade da persistência.</span><span class="sxs-lookup"><span data-stu-id="71675-106">The different performance characteristics of memory-optimized tables and natively compiled stored procedures may negate the need for persistence.</span></span>  
  
## <a name="non-persisted-computed-columns"></a><span data-ttu-id="71675-107">Colunas computadas não persistentes</span><span class="sxs-lookup"><span data-stu-id="71675-107">Non-Persisted Computed Columns</span></span>  
 <span data-ttu-id="71675-108">Para simular os efeitos de uma coluna computada não persistente, crie uma exibição na tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="71675-108">To simulate the effects of a non-persisted computed column, create a view on the memory-optimized table.</span></span> <span data-ttu-id="71675-109">Na instrução SELECT que define a exibição, adicione a definição de coluna computada à exibição.</span><span class="sxs-lookup"><span data-stu-id="71675-109">In the SELECT statement that defines the view, add the computed column definition into the view.</span></span> <span data-ttu-id="71675-110">A não ser em um procedimento armazenado compilado nativamente, as consultas que usam valores da coluna computada devem ler a exibição.</span><span class="sxs-lookup"><span data-stu-id="71675-110">Except in a natively compiled stored procedure, queries that use values from the computed column should read from the view.</span></span> <span data-ttu-id="71675-111">Nos procedimentos armazenados compilados nativamente, você deve atualizar qualquer instrução select, update ou delete de acordo com sua definição de coluna computada.</span><span class="sxs-lookup"><span data-stu-id="71675-111">Inside natively compiled stored procedures, you should update any select, update, or delete statement according to your computed column definition.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is not persisted.  
CREATE VIEW dbo.v_order_details AS  
   SELECT  
      OrderId,  
      ProductId,  
      SalePrice,  
      Quantity,  
      Quantity * SalePrice AS Total  
   FROM dbo.order_details  
```  
  
## <a name="persisted-computed-columns"></a><span data-ttu-id="71675-112">Colunas computadas persistentes</span><span class="sxs-lookup"><span data-stu-id="71675-112">Persisted Computed Columns</span></span>  
 <span data-ttu-id="71675-113">Para simular os efeitos de uma coluna computada persistente, crie um procedimento armazenado para inserção na tabela e outro procedimento armazenado para atualizar a tabela.</span><span class="sxs-lookup"><span data-stu-id="71675-113">To simulate the effects of a persisted computed column, create a stored procedure for inserting into the table and another stored procedure for updating the table.</span></span> <span data-ttu-id="71675-114">Ao inserir ou atualizar a tabela, chame esses procedimentos armazenados para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="71675-114">When inserting or updating the table, invoke these stored procedures to perform these tasks.</span></span> <span data-ttu-id="71675-115">Nos procedimentos armazenados, calcule o valor do campo computado de acordo com as entradas, praticamente da mesma maneira que a coluna computada é definida na tabela baseada em disco original.</span><span class="sxs-lookup"><span data-stu-id="71675-115">Inside the stored procedures, calculate the value for the computed field according to the inputs, much like how the computed column is defined on the original disk-based table.</span></span> <span data-ttu-id="71675-116">Em seguida, insira ou atualize a tabela conforme necessário no procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="71675-116">Then, insert or update the table as needed inside the stored procedure.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is persisted.  
-- we need to create insert and update procedures to calculate Total.  
CREATE PROCEDURE sp_insert_order_details   
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
-- for bulk inserts, accept a table-valued parameter into the stored procedure  
-- and use an INSERT INTO SELECT statement.  
DECLARE @total money = @SalePrice * @Quantity  
INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
DECLARE @total money = @SalePrice * @Quantity  
UPDATE dbo.OrderDetails   
SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
WHERE OrderId = @OrderId  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="71675-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71675-117">See Also</span></span>  
 [<span data-ttu-id="71675-118">Migrando para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="71675-118">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
