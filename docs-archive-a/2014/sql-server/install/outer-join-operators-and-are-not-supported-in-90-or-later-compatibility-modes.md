---
title: Operadores de junção externa *= e =* não têm suporte nos modos de compatibilidade 90 ou posteriores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- =* join
- '*= join'
- joins [SQL Server]
ms.assetid: ca4aa11f-1048-411f-9c6c-3d0a8e319f2f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 357c729e6d53cc17f2e4c169dd66613b6cfd2f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683325"
---
# <a name="outer-join-operators--and--are-not-supported-in-90-or-later-compatibility-modes"></a><span data-ttu-id="6ae53-102">Os operadores de junção externa \*= e =\* não são compatíveis com o modo de compatibilidade 90 ou posterior</span><span class="sxs-lookup"><span data-stu-id="6ae53-102">Outer join operators \*= and =\* are not supported in 90 or later compatibility modes</span></span>
  <span data-ttu-id="6ae53-103">O supervisor de atualização detectou o uso de operadores de junção externa \* = e = \* .</span><span class="sxs-lookup"><span data-stu-id="6ae53-103">Upgrade Advisor detected the use of outer join operators \*= and =\*.</span></span> <span data-ttu-id="6ae53-104">Esses operadores não são aceitos no modo de compatibilidade 90 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6ae53-104">These operators are not supported in 90 or later compatibility modes.</span></span> <span data-ttu-id="6ae53-105">Quando você faz a atualização, os bancos de dados de usuários mantêm seus modos de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="6ae53-105">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="6ae53-106">As instruções que usam esses operadores falhará.</span><span class="sxs-lookup"><span data-stu-id="6ae53-106">Statements that use these operators will fail.</span></span>  
  
## <a name="component"></a><span data-ttu-id="6ae53-107">Componente</span><span class="sxs-lookup"><span data-stu-id="6ae53-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="6ae53-108">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="6ae53-108">Corrective Action</span></span>  
 <span data-ttu-id="6ae53-109">Antes de alterar o modo de compatibilidade do banco de dados para 90 ou posterior, modifique as instruções que usam os operadores de junção externa \* = e = \* para usar palavras-chave de junção externa equivalentes.</span><span class="sxs-lookup"><span data-stu-id="6ae53-109">Before you change the database compatibility mode to 90 or later, modify statements that use the outer join operators \*= and =\* to use equivalent OUTER JOIN keywords.</span></span> <span data-ttu-id="6ae53-110">O exemplo a seguir mostra uma consulta que usa o operador `\*=` e uma consulta equivalente que usa as palavras-chave `LEFT OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="6ae53-110">The following example shows a query that uses the `\*=` operator and an equivalent query that uses the `LEFT OUTER JOIN` keywords.</span></span>  
  
```  
-- This query uses an old-style outer join operator.  
USE pubs  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee, jobs   
WHERE employee.job_id *= jobs.job_id  
ORDER BY employee.job_id  
  
-- This query uses the ANSI standard keywords LEFT OUTER JOIN.  
USE pubs;  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
ORDER BY employee.job_id  
```  
  
 <span data-ttu-id="6ae53-111">Para obter mais informações sobre junções externas, consulte "Usando junções externas" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6ae53-111">For more information about outer joins, see "Using Outer Joins" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae53-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ae53-112">See Also</span></span>  
 <span data-ttu-id="6ae53-113">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6ae53-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="6ae53-114">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="6ae53-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
