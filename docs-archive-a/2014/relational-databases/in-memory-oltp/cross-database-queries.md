---
title: Consultas de bancos de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a0305f5b-91bd-4d18-a2fc-ec235b062fd3
author: rothja
ms.author: jroth
ms.openlocfilehash: 4afbb580a55273ec241005493fd37f99e98ec0e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571391"
---
# <a name="cross-database-queries"></a><span data-ttu-id="e36bd-102">Consultas de bancos de dados</span><span class="sxs-lookup"><span data-stu-id="e36bd-102">Cross-Database Queries</span></span>
  <span data-ttu-id="e36bd-103">No [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], as tabelas com otimização de memória não oferecem suporte a transações envolvendo todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="e36bd-103">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], memory-optimized tables do not support cross-database transactions.</span></span> <span data-ttu-id="e36bd-104">Você não pode acessar outro banco de dados da mesma transação ou na mesma consulta que também acesse uma tabela com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="e36bd-104">You cannot access another database from the same transaction or the same query that also accesses a memory-optimized table.</span></span> <span data-ttu-id="e36bd-105">Você não pode copiar facilmente dados de uma tabela em um banco de dados, para uma tabela com otimização de memória em outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e36bd-105">You cannot easily copy data from a table in one database, to a memory-optimized table in another database.</span></span>  
  
 <span data-ttu-id="e36bd-106">Variáveis de tabela não são transacionais.</span><span class="sxs-lookup"><span data-stu-id="e36bd-106">Table variables are not transactional.</span></span> <span data-ttu-id="e36bd-107">Assim, as variáveis de tabela com otimização de memória podem ser usadas em consultas de bancos de dados e, portanto, podem facilitar a movimentação de dados de um banco de dados para tabelas com otimização de memória em outro.</span><span class="sxs-lookup"><span data-stu-id="e36bd-107">Therefore, memory-optimized table variables can be used in cross-database queries, and can thus facilitate moving data from one database into memory-optimized tables in another.</span></span> <span data-ttu-id="e36bd-108">Você pode usar duas transações.</span><span class="sxs-lookup"><span data-stu-id="e36bd-108">You can use two transactions.</span></span> <span data-ttu-id="e36bd-109">Na primeira transação, insira os dados da tabela remota na variável.</span><span class="sxs-lookup"><span data-stu-id="e36bd-109">In the first transaction, insert the data from the remote table into the variable.</span></span> <span data-ttu-id="e36bd-110">Na segunda transação, insira os dados na tabela com otimização de memória local da variável.</span><span class="sxs-lookup"><span data-stu-id="e36bd-110">In the second transaction, insert the data into the local memory-optimized table from the variable.</span></span>  
  
 <span data-ttu-id="e36bd-111">Por exemplo, para copiar a linha da tabela T1 no banco de dados db1 para a tabela T2 no DB2, usando a variável @v1 do tipo dbo. TT1, você pode usar algo como:</span><span class="sxs-lookup"><span data-stu-id="e36bd-111">For example, to copy the row from table t1 in database db1 to table t2 in db2, using variable @v1 of type dbo.tt1, you can use something like:</span></span>  
  
```sql  
USE db2   
GO   
DECLARE @v1 dbo.tt1   
INSERT @v1 SELECT * FROM db1.dbo.t1   
INSERT dbo.t2 SELECT * FROM @v1   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e36bd-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e36bd-112">See Also</span></span>  
 [<span data-ttu-id="e36bd-113">Migrando para OLTP na memória</span><span class="sxs-lookup"><span data-stu-id="e36bd-113">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
