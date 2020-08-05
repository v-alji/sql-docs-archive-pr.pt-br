---
title: Implementando IDENTITY em uma tabela otimizada em memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0a704a3-3a31-4c2c-b967-addacda62ef8
author: rothja
ms.author: jroth
ms.openlocfilehash: 955f9f1a905a9d0c71304320f60abe300e430e4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572564"
---
# <a name="implementing-identity-in-a-memory-optimized-table"></a><span data-ttu-id="18c2c-102">Implementando IDENTITY em uma tabela otimizada em memória</span><span class="sxs-lookup"><span data-stu-id="18c2c-102">Implementing IDENTITY in a Memory-Optimized Table</span></span>
  <span data-ttu-id="18c2c-103">IDENTITY(1, 1) tem suporte em uma tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="18c2c-103">IDENTITY(1, 1) is supported on a memory-optimized table.</span></span> <span data-ttu-id="18c2c-104">No entanto, colunas de identidade com definição de IDENTITY(x, y) onde x != 1 ou y != 1 não tem suporte em tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="18c2c-104">However, identity columns with definition of IDENTITY(x, y) where x != 1 or y != 1 are not supported on memory-optimized tables.</span></span> <span data-ttu-id="18c2c-105">A solução alternativa para valores IDENTITY usa o objeto SEQUENCE ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span><span class="sxs-lookup"><span data-stu-id="18c2c-105">The workaround for IDENTITY values uses the SEQUENCE object ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span></span>  
  
 <span data-ttu-id="18c2c-106">Primeiramente, remova a propriedade IDENTITY da tabela que você está convertendo em OLTP na memória.</span><span class="sxs-lookup"><span data-stu-id="18c2c-106">First remove the IDENTITY property from the table you are converting to In-Memory OLTP.</span></span> <span data-ttu-id="18c2c-107">Em seguida, defina um novo objeto SEQUENCE para a coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="18c2c-107">Then, define a new SEQUENCE object for the column in the table.</span></span> <span data-ttu-id="18c2c-108">Os objetos SEQUENCE como as colunas de identidade dependem da capacidade de criar valores DEFAULT para colunas que usam a sintaxe NEXT VALUE FOR para obter um novo valor de identidade.</span><span class="sxs-lookup"><span data-stu-id="18c2c-108">SEQUENCE objects as identity columns rely on the ability to create DEFAULT values for columns that use the NEXT VALUE FOR syntax to get a new identity value.</span></span> <span data-ttu-id="18c2c-109">Como não há suporte para os valores DEFAULT na OLTP na memória, você precisa passar o valor SEQUENCE recentemente gerado para a instrução INSERT ou para um procedimento armazenado nativamente compilado que faça a inserção.</span><span class="sxs-lookup"><span data-stu-id="18c2c-109">Since DEFAULTs are not supported in In-Memory OLTP, you need to pass the newly-generated SEQUENCE value either to the INSERT statement or to a natively compiled stored procedure that does the insert.</span></span> <span data-ttu-id="18c2c-110">O exemplo a seguir demonstra esse padrão.</span><span class="sxs-lookup"><span data-stu-id="18c2c-110">The following example demonstrates this pattern.</span></span>  
  
```sql  
-- Create a new In-Memory OLTP table to simulate IDENTITY insert  
-- Here the column C1 was the identity column in the original table  
--  
create table T1  
(  
  
[c1] integer not null primary key T1_c1 nonclustered,  
[c2] varchar(32) not null,  
[c3] datetime not null  
  
) with (memory_optimized = on)  
go  
  
-- This is a sequence provider that will give us values for column [c1]  
--  
create sequence usq_SequenceForT1 as integer start with 2 increment by 1  
go  
  
--   insert a sample row using the sequence  
--   note that a new value needs to be retrieved form   
--   the sequence object for every insert  
--  
declare @c1 integer = next value for [dbo].[usq_SequenceForT1]  
insert into T1 values (@c1, 'test', getdate())  
```  
  
 <span data-ttu-id="18c2c-111">Após executar a inserção várias vezes, você verá valores válidos que aumentam de forma monotônica na coluna [c1].</span><span class="sxs-lookup"><span data-stu-id="18c2c-111">After performing the insert several times, you see valid monotonically increasing values in column [c1].</span></span> <span data-ttu-id="18c2c-112">Esse conjunto de resultados é gerado usando a verificação de tabela e o índice de hash sem `ORDER BY` para que as linhas não sejam ordenadas.</span><span class="sxs-lookup"><span data-stu-id="18c2c-112">This result set is generated using table scan and hash index without `ORDER BY` so the rows are not ordered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c2c-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18c2c-113">See Also</span></span>  
 [<span data-ttu-id="18c2c-114">Migrando para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="18c2c-114">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
