---
title: Consultas FOR XML AUTO retornam referências de tabela derivadas nos modos de compatibilidade 90 ou posteriores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FOR XML AUTO [SQL Server]
ms.assetid: 10c32f06-f7e1-40e0-8f79-6d921f2bef1d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 702cb2ca1d437dff03cee09c98d72082500709d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583993"
---
# <a name="for-xml-auto-queries-return-derived-table-references-in-90-or-later-compatibility-modes"></a><span data-ttu-id="cb421-102">Consultas FOR XML AUTO retornam referências de tabela derivada no modo de compatibilidade 90 ou posterior</span><span class="sxs-lookup"><span data-stu-id="cb421-102">FOR XML AUTO queries return derived table references in 90 or later compatibility modes</span></span>
  <span data-ttu-id="cb421-103">Quando o nível de compatibilidade do banco de dados está definido como 90 ou posterior, as consultas FOR XML que executam no modo AUTO retornam referências para aliases de tabela derivada.</span><span class="sxs-lookup"><span data-stu-id="cb421-103">When the database compatibility level is set to 90 or later, FOR XML queries that execute in AUTO mode return references to derived table aliases.</span></span> <span data-ttu-id="cb421-104">Quando o nível de compatibilidade está definido como 80, as consultas FOR XML AUTO retornam referências para as tabelas base que definem uma tabela derivada.</span><span class="sxs-lookup"><span data-stu-id="cb421-104">When the compatibility level is set to 80, FOR XML AUTO queries return references to the base tables that define a derived table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="cb421-105">Componente</span><span class="sxs-lookup"><span data-stu-id="cb421-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="cb421-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb421-106">Description</span></span>  
 <span data-ttu-id="cb421-107">Por exemplo, considere a seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="cb421-107">For example, consider the following table:</span></span>  
  
```  
CREATE TABLE Test(id int);  
INSERT INTO Test VALUES(1);  
INSERT INTO Test VALUES(2);  
```  
  
 <span data-ttu-id="cb421-108">A consulta a seguir, que inclui uma tabela derivada, produz resultados diferentes no nível de compatibilidade 80, 90 ou posterior:</span><span class="sxs-lookup"><span data-stu-id="cb421-108">The following query, which includes a derived table, produces different results under compatibility levels 80, 90, or later:</span></span>  
  
```  
SELECT * FROM   
   (SELECT a.id AS a, b.id AS b   
    FROM Test a JOIN Test b ON a.id=b.id)  
AS DerivedTest   
FOR XML AUTO;  
```  
  
 <span data-ttu-id="cb421-109">No nível de compatibilidade 80, a consulta retorna os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="cb421-109">Under compatibility level 80, the query returns the following results.</span></span> <span data-ttu-id="cb421-110">Os resultados referenciam os aliases de tabela base `a` e `b` da tabela derivada em vez do alias de tabela derivada.</span><span class="sxs-lookup"><span data-stu-id="cb421-110">The results reference the base table aliases `a` and `b` of the derived table instead of the derived table alias.</span></span>  
  
```  
<a a="1"><b b="1"/></a><a a="2"><b b="2"/></a>  
```  
  
 <span data-ttu-id="cb421-111">No nível de compatibilidade 90 ou posterior, a consulta retorna referências para o alias de tabela derivada `DerivedTest` em vez de retornar para as tabelas base da tabela derivada.</span><span class="sxs-lookup"><span data-stu-id="cb421-111">Under compatibility level 90 or later, the query returns references to the derived table alias `DerivedTest` instead of to the derived table's base tables.</span></span>  
  
```  
<DerivedTest a="1" b="1"/><DerivedTest a="2" b="2"/>  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="cb421-112">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="cb421-112">Corrective Action</span></span>  
 <span data-ttu-id="cb421-113">Modifique seu aplicativo conforme necessário para adequar os resultados de consultas FOR XML AUTO que incluam tabelas derivadas e que executem no nível de compatibilidade 90 ou posterior. </span><span class="sxs-lookup"><span data-stu-id="cb421-113">Modify your application as required to account for the changes in results of FOR XML AUTO queries that include derived tables and that run under compatibility level 90 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb421-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cb421-114">See Also</span></span>  
 <span data-ttu-id="cb421-115">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="cb421-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="cb421-116">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="cb421-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  