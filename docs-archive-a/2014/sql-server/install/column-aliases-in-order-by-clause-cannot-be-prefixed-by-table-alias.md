---
title: Aliases de coluna na cláusula ORDER BY não podem ser prefixados pelo alias de tabela | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], columns
ms.assetid: fee7328f-6e8d-4005-930b-56fb6f17e0b2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 44333d778753a2f8761d32d181681b798e3bc409
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573497"
---
# <a name="column-aliases-in-order-by-clause-cannot-be-prefixed-by-table-alias"></a><span data-ttu-id="ef801-102">Aliases de coluna na cláusula ORDER BY não podem ter como prefixo o alias da tabela</span><span class="sxs-lookup"><span data-stu-id="ef801-102">Column aliases in ORDER BY clause cannot be prefixed by table alias</span></span>
  <span data-ttu-id="ef801-103">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e em versões posteriores, aliases de coluna na cláusula ORDER BY não podem ter como prefixo o alias da tabela.</span><span class="sxs-lookup"><span data-stu-id="ef801-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, column aliases in the ORDER BY clause cannot be prefixed by the table alias.</span></span>  
  
## <a name="component"></a><span data-ttu-id="ef801-104">Componente</span><span class="sxs-lookup"><span data-stu-id="ef801-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="ef801-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="ef801-105">Description</span></span>  
 <span data-ttu-id="ef801-106">Por exemplo, a consulta a seguir executa no [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], mas retorna uma erro no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ef801-106">For example, the following query executes in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but returns an error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.l  
```  
  
 <span data-ttu-id="ef801-107">O [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] não corresponde `p.l` na cláusula `ORDER BY` a uma coluna válida na tabela.</span><span class="sxs-lookup"><span data-stu-id="ef801-107">The [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] does not match `p.l` in the `ORDER BY` clause to a valid column in the table.</span></span>  
  
### <a name="exception"></a><span data-ttu-id="ef801-108">Exceção</span><span class="sxs-lookup"><span data-stu-id="ef801-108">Exception</span></span>  
 <span data-ttu-id="ef801-109">Se o alias de coluna prefixado que é especificado na cláusula ORDER BY for um nome de coluna válido na tabela especificada, a consulta executará sem erro; no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], a semântica da instrução pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="ef801-109">If the prefixed column alias that is specified in the ORDER BY clause is a valid column name in the specified table, the query executes without error; in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the semantics of the statement might be different.</span></span> <span data-ttu-id="ef801-110">Por exemplo, o alias de coluna (`id`) especificado na instrução a seguir é um nome de coluna válido na tabela `sysobjects`.</span><span class="sxs-lookup"><span data-stu-id="ef801-110">For example, the column alias (`id`) specified in the following statement is a valid column name in the `sysobjects` table.</span></span> <span data-ttu-id="ef801-111">No [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], quando a instrução é executada, a operação `CAST` é executada depois que o conjunto de resultados é classificado.</span><span class="sxs-lookup"><span data-stu-id="ef801-111">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], when the statement executes, the `CAST` operation is performed after the result set is sorted.</span></span> <span data-ttu-id="ef801-112">Isso significa a coluna `name` é usada na operação de classificação.</span><span class="sxs-lookup"><span data-stu-id="ef801-112">This means the `name` column is used in the sort operation.</span></span> <span data-ttu-id="ef801-113">No [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], a operação `CAST` acontece antes da operação de classificação.</span><span class="sxs-lookup"><span data-stu-id="ef801-113">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the `CAST` operation occurs before the sort operation.</span></span> <span data-ttu-id="ef801-114">Isso significa que a coluna `id` na tabela é usada na operação de classificação e retorna o conjunto de resultados em uma ordem inesperada.</span><span class="sxs-lookup"><span data-stu-id="ef801-114">This means the `id` column in the table is used in the sort operation and returns the result set in an unexpected order.</span></span>  
  
```  
SELECT CAST (o.name AS char(128)) AS id  
FROM sysobjects AS o  
ORDER BY o.id;  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="ef801-115">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="ef801-115">Corrective Action</span></span>  
 <span data-ttu-id="ef801-116">Modifique as consultas que usam aliases de coluna prefixados por aliases de tabelas na cláusula ORDER BY de uma das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="ef801-116">Modify queries that use column aliases prefixed by table aliases in the ORDER BY clause in either of the following ways:</span></span>  
  
-   <span data-ttu-id="ef801-117">Não coloque prefixo no alias de coluna da cláusula ORDER BY, se possível.</span><span class="sxs-lookup"><span data-stu-id="ef801-117">Do not prefix the column alias in the ORDER BY clause, if possible.</span></span>  
  
-   <span data-ttu-id="ef801-118">Substitua o alias de coluna pelo nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="ef801-118">Replace the column alias with the column name.</span></span>  
  
 <span data-ttu-id="ef801-119">Por exemplo, ambas as consultas a seguir executam sem erro no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ef801-119">For example, both of the following queries execute without error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY l  
  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.LastName  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef801-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ef801-120">See Also</span></span>  
 <span data-ttu-id="ef801-121">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="ef801-121">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="ef801-122">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="ef801-122">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
