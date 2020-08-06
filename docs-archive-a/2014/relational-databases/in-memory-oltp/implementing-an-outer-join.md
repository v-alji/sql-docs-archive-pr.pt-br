---
title: Implementando uma junção externa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 67084043-6b23-4975-b9db-6e49923d4bab
author: rothja
ms.author: jroth
ms.openlocfilehash: 73017541a8fc7b933c4ace1ef6539d53047ea5df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569453"
---
# <a name="implementing-an-outer-join"></a><span data-ttu-id="535fc-102">Implementando uma junção externa</span><span class="sxs-lookup"><span data-stu-id="535fc-102">Implementing an Outer Join</span></span>
  <span data-ttu-id="535fc-103">A junção externa não tem suporte em procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="535fc-103">Outer join is not supported in natively compiled stored procedures.</span></span> <span data-ttu-id="535fc-104">O exemplo a seguir mostra uma maneira de implementar a funcionalidade de uma junção externa esquerda em um procedimento armazenado compilado nativamente.</span><span class="sxs-lookup"><span data-stu-id="535fc-104">The following sample shows a way to implement the functionality of a left outer join in a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="535fc-105">Os exemplos usam uma variável de tabela para simular um cursor no lado esquerdo da junção e um único conjunto de resultados de uma variável de tabela, que só é adequado ao processar um número limitado de linhas, pois isso envolve a criação de uma cópia adicional das linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="535fc-105">The samples uses a table variable to simulate a cursor on the left side of the join, and a table variable to construct a single result set, which is only suitable when processing a limited number of rows as it involves creating an additional copy of the data rows.</span></span>  
  
 <span data-ttu-id="535fc-106">Uma variável ( @outer ) do tipo t1_type é usada para iterar sobre as linhas de T1, usando um loop while para simular um cursor.</span><span class="sxs-lookup"><span data-stu-id="535fc-106">A variable (@outer) of type t1_type is used to iterate over the rows from t1, using a while loop to simulate a cursor.</span></span> <span data-ttu-id="535fc-107">A variável @result do tipo t1t2_join_type é usada para construir o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="535fc-107">The variable @result of type t1t2_join_type is then used to construct the result set.</span></span>  
  
 <span data-ttu-id="535fc-108">Você deve testar o desempenho dessa solução alternativa, para garantir que ela seja executada como esperado em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="535fc-108">You should test the performance of this workaround, to be sure that it performs as expected in your application.</span></span>  
  
```  
-- original query:  
select   
   t1.c1 as t1c1,  
   t1.c2 as t1c2,  
   t2.c2 as t2c2,  
   t2.c3 as t2c3  
   from t1 left join t2 on t1.c2=t2.c3  
GO  
  
create table dbo.t1  
(c1 int not null primary key nonclustered,  
c2 int not null) with (memory_optimized=on)  
  
create table dbo.t2  
(c2 int not null primary key nonclustered,  
c3 int not null) with (memory_optimized=on)  
  
INSERT t1 VALUES (1,2)  
INSERT t1 VALUES (2,3)  
INSERT t1 VALUES (3,2)  
INSERT t2 VALUES (2,3)  
INSERT t2 VALUES (4,3)  
GO  
  
create type dbo.t1_type as table  
(  
   id int identity not null primary key nonclustered hash with (bucket_count=1024),  
   c1 int,  
   c2 int  
) with (memory_optimized=on)  
GO  
  
create type dbo.t1t2_join_type as table  
(  
   t1c1 int not null index ix_t1c1,  
   t1c2 int not null,  
   t2c2 int,  
   t2c3 int  
) with (memory_optimized=on)  
GO  
  
-- ====== scenario: generic left join  
  
-- stored procedure including the workaround  
create procedure dbo.usp_left_join  
with native_compilation, execute as owner, schemabinding  
as  
begin atomic with (transaction isolation level = snapshot, language = N'us_english')  
  
   DECLARE @outer dbo.t1_type  
   DECLARE @result dbo.t1t2_join_type  
  
   -- populate the variable used for iterating over the outer rows  
   INSERT @outer(c1, c2) select c1,c2 from dbo.t1  
  
   DECLARE @i int = 1  
   DECLARE @max int = scope_identity()  
  
   DECLARE @t1c1 int  
   DECLARE @t1c2 int  
  
   while @i <= @max  
   begin     
      select @t1c1 = c1, @t1c2 = c2 from @outer where id = @i  
  
      INSERT @result select @t1c1, @t1c2, c2, c3 from dbo.t2 where c3 = @t1c2  
  
      if @@rowcount = 0   
         INSERT @result (t1c1, t1c2) VALUES (@t1c1, @t1c2)  
  
      set @i += 1  
   end  
  
   select   
      t1c1,  
      t1c2,  
      t2c2,  
      t2c3  
   from @result  
end  
GO  
  
exec dbo.usp_left_join  
```  
  
## <a name="see-also"></a><span data-ttu-id="535fc-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="535fc-109">See Also</span></span>  
 <span data-ttu-id="535fc-110">[Problemas de migração para procedimentos armazenados compilados nativamente](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="535fc-110">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="535fc-111">Construções do Transact-SQL sem suporte pelo OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="535fc-111">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
