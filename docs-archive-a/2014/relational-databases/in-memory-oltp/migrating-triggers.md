---
title: Migrando gatilhos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: ad5385c5-5a50-40ca-a319-97d5606b8511
author: rothja
ms.author: jroth
ms.openlocfilehash: 25965e7cce84b0dcfcd3b6ce6176e8ad3ddabc6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685689"
---
# <a name="migrating-triggers"></a><span data-ttu-id="9893a-102">Migrando gatilhos</span><span class="sxs-lookup"><span data-stu-id="9893a-102">Migrating Triggers</span></span>
  <span data-ttu-id="9893a-103">Este tópico discute gatilhos DDL e DML, e tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="9893a-103">This topic discusses DDL and DML triggers and memory-optimized tables.</span></span>  
  
 <span data-ttu-id="9893a-104">Os gatilhos LOGON são gatilhos definidos para serem disparados em eventos LOGON.</span><span class="sxs-lookup"><span data-stu-id="9893a-104">LOGON triggers are triggers defined to fire on LOGON events.</span></span> <span data-ttu-id="9893a-105">Os gatilhos LOGON não afetam tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="9893a-105">LOGON triggers do not affect memory-optimized tables.</span></span>  
  
## <a name="ddl-triggers"></a><span data-ttu-id="9893a-106">Gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="9893a-106">DDL Triggers</span></span>  
 <span data-ttu-id="9893a-107">Os gatilhos DDL são gatilhos definidos para disparar quando uma instrução CREATE, ALTER, DROP, GRANT, DENY, REVOKE ou UPDATE STATISTICS é executada no banco de dados ou no servidor no qual está definida.</span><span class="sxs-lookup"><span data-stu-id="9893a-107">DDL triggers are triggers defined to fire when a CREATE, ALTER, DROP, GRANT, DENY, REVOKE, or UPDATE STATISTICS statement is executed on the database or server on which it is defined.</span></span>  
  
 <span data-ttu-id="9893a-108">Você não pode criar tabelas com otimização de memória se o banco de dados ou o servidor tem um ou mais gatilhos DDL definidos em CREATE_TABLE ou em qualquer grupo de eventos que o inclua.</span><span class="sxs-lookup"><span data-stu-id="9893a-108">You cannot create memory-optimized tables if the database or server has one or more DDL trigger defined on CREATE_TABLE or any event group that includes it.</span></span> <span data-ttu-id="9893a-109">Você não pode descartar uma tabela com otimização de memória se o banco de dados ou o servidor tem um ou mais gatilhos DDL definidos em DROP_TABLE ou em qualquer grupo de eventos que o inclua.</span><span class="sxs-lookup"><span data-stu-id="9893a-109">You cannot drop a memory-optimized table if the database or server has one or more DDL trigger defined on DROP_TABLE or any event group that includes it.</span></span>  
  
 <span data-ttu-id="9893a-110">Você não pode criar procedimentos armazenados compilados de modo nativo quando há um ou mais gatilhos DDL em CREATE_PROCEDURE, em DROP_PROCEDURE ou em qualquer grupo de eventos que inclua esses eventos.</span><span class="sxs-lookup"><span data-stu-id="9893a-110">You cannot create natively compiled stored procedures if there are one or more DDL triggers on CREATE_PROCEDURE, DROP_PROCEDURE, or any event group that includes those events.</span></span>  
  
## <a name="dml-triggers"></a><span data-ttu-id="9893a-111">Gatilhos DML</span><span class="sxs-lookup"><span data-stu-id="9893a-111">DML Triggers</span></span>  
 <span data-ttu-id="9893a-112">Os gatilhos DML não podem ser definidos em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="9893a-112">DML triggers cannot be defined on memory-optimized tables.</span></span> <span data-ttu-id="9893a-113">No entanto, a OLTP em Memória permitirá atingir um efeito semelhante aos gatilhos DML se você usar explicitamente procedimentos armazenados para inserir, atualizar ou excluir dados.</span><span class="sxs-lookup"><span data-stu-id="9893a-113">However, In-Memory OLTP allows you to achieve an effect similar to DML triggers if you explicitly use stored procedures to insert, update, or delete data.</span></span> <span data-ttu-id="9893a-114">Se o sistema contiver consultas ad hoc, converta-as para usar esses procedimentos armazenados em vez de simular o efeito dos gatilhos DML.</span><span class="sxs-lookup"><span data-stu-id="9893a-114">If your system contains ad-hoc queries, convert them to use these stored procedures instead to simulate the effect of DML triggers.</span></span>  
  
 <span data-ttu-id="9893a-115">Dependendo do evento de gatilho (FOR/AFTER ou INSTEAD OF), você pode incluir o conteúdo do gatilho no procedimento armazenado apropriado que executa INSERT, UPDATE ou DELETE nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="9893a-115">Depending on the trigger event (FOR/AFTER or INSTEAD OF), you may include the content of the trigger in the appropriate stored procedure that performs INSERT, UPDATE, or DELETE on that table.</span></span> <span data-ttu-id="9893a-116">Por exemplo, ao migrar um gatilho AFTER INSERT, você pode modificar o procedimento armazenado que executa a operação de inserção, incluindo o conteúdo do gatilho após a instrução INSERT apropriada.</span><span class="sxs-lookup"><span data-stu-id="9893a-116">For example, when migrating an AFTER INSERT trigger, you could alter the stored procedure that performs the insert operation by including the content of the trigger after the appropriate INSERT statement.</span></span>  
  
 <span data-ttu-id="9893a-117">Você pode usar um procedimento armazenado interpretado ou um procedimento armazenado compilado de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="9893a-117">You can use an interpreted stored procedure or a natively compiled stored procedure.</span></span> <span data-ttu-id="9893a-118">A maioria das construções [!INCLUDE[tsql](../../includes/tsql-md.md)] em um procedimento armazenado interpretado podem ser executadas em uma tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="9893a-118">Most [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs in an interpreted stored procedure can execute on a memory-optimized table.</span></span> <span data-ttu-id="9893a-119">Entretanto, apenas um subconjunto de construções [!INCLUDE[tsql](../../includes/tsql-md.md)] tem suporte em procedimentos armazenados compilados de modo nativo.</span><span class="sxs-lookup"><span data-stu-id="9893a-119">However, only a subset of [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs are supported in natively compiled stored procedures.</span></span> <span data-ttu-id="9893a-120">Para obter informações sobre o suporte ao [!INCLUDE[tsql](../../includes/tsql-md.md)] em tabelas com otimização de memória, consulte [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9893a-120">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support on memory-optimized tables, see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span> <span data-ttu-id="9893a-121">Para obter informações sobre o suporte ao [!INCLUDE[tsql](../../includes/tsql-md.md)] em procedimentos armazenados compilados de modo nativo, consulte [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="9893a-121">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support in natively compiled stored procedures, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="9893a-122">Veja a seguir um exemplo simples de simulação do comportamento do gatilho DML em uma tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="9893a-122">The following is a simple example of simulating DML trigger behavior on a memory-optimized table.</span></span>  
  
 <span data-ttu-id="9893a-123">O banco de dados contém os seguintes objetos, incluídos no script como instruções CREATE TABLE, CREATE TRIGGER e CREATE PROCEDURE:</span><span class="sxs-lookup"><span data-stu-id="9893a-123">The database contains the following objects, scripted as CREATE TABLE, CREATE TRIGGER, and CREATE PROCEDURE statements:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null primary key,  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
)  
GO  
  
CREATE TRIGGER tr_order_details_insteadof_insert  
ON OrderDetails  
INSTEAD OF INSERT AS  
BEGIN  
   DECLARE @pid int, @qty_buy int, @qty_remain int  
   SELECT @pid = ProductId, @qty_buy = Quantity FROM inserted  
   SELECT @qty_remain = Quantity FROM Inventory WHERE ProductId = @pid  
   IF (@qty_remain <= @qty_buy)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      SELECT OrderId, ProductId, SalePrice, Quantity, Total FROM inserted  
      UPDATE Inventory SET Quantity = Quantity - @qty_buy WHERE ProductId = @pid  
   END  
END  
GO  
  
CREATE TRIGGER tr_order_details_after_update  
ON OrderDetails  
AFTER UPDATE AS  
BEGIN  
   INSERT INTO UpdateNotifications (OrderId, UpdateTime) SELECT OrderId, GETDATE() FROM inserted     
END  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
AS BEGIN  
   INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
   VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
AS BEGIN  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
END  
GO  
```  
  
 <span data-ttu-id="9893a-124">Os seguintes objetos são funcionalmente equivalentes ao estado de pré-migração:</span><span class="sxs-lookup"><span data-stu-id="9893a-124">The following objects are functionally equivalent to the pre-migration state:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 1048576),  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE Inventory  
(  
   ProductId int not null PRIMARY KEY NONCLUSTERED,  
   Quantity int not null  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE UpdateNotifications  
(  
   OrderId int not null,  
   UpdateTime datetime2 not null  
   CONSTRAINT pk_updateNotifications PRIMARY KEY NONCLUSTERED (OrderId, UpdateTime)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   DECLARE @qty_remain int  
   SELECT @qty_remain = Quantity FROM dbo.Inventory WHERE ProductId = @ProductId  
   IF (@qty_remain <= @Quantity)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
      UPDATE dbo.Inventory SET Quantity = Quantity - @Quantity WHERE ProductId = @ProductId  
   END  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
   INSERT INTO dbo.UpdateNotifications (OrderId, UpdateTime) VALUES (@OrderId, GETDATE())  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9893a-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9893a-125">See Also</span></span>  
 [<span data-ttu-id="9893a-126">Migrando para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="9893a-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
