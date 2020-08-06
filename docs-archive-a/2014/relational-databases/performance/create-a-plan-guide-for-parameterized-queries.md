---
title: Criar um guia de plano para consultas parametrizadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- parameterized queries, plan guides for
- plan guides [SQL Server], parameterized queries
ms.assetid: b532ae16-66e7-4641-9bc8-b0d805853477
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 565610826f704274724ea05d821205a5b3391060
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583558"
---
# <a name="create-a-plan-guide-for-parameterized-queries"></a><span data-ttu-id="c501e-102">Criar um guia de plano para consultas parametrizadas</span><span class="sxs-lookup"><span data-stu-id="c501e-102">Create a Plan Guide for Parameterized Queries</span></span>
  <span data-ttu-id="c501e-103">O guia de plano TEMPLATE corresponde consultas autônomas com parâmetros com uma forma especificada.</span><span class="sxs-lookup"><span data-stu-id="c501e-103">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span>  
  
 <span data-ttu-id="c501e-104">O exemplo a seguir cria um guia de plano que faz a correspondência de qualquer consulta com parâmetros com um formulário especificado, e direciona o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para forçar a aplicação de parâmetros da consulta.</span><span class="sxs-lookup"><span data-stu-id="c501e-104">The following example creates a plan guide that matches any query that parameterizes to a specified form, and directs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to force parameterization of the query.</span></span> <span data-ttu-id="c501e-105">As duas consultas a seguir são sintaticamente equivalentes, mas só diferem nos valores literais constantes.</span><span class="sxs-lookup"><span data-stu-id="c501e-105">The following two queries are syntactically equivalent, but differ only in their constant literal values.</span></span>  
  
```  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45639;  
  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45640;  
```  
  
 <span data-ttu-id="c501e-106">Este é o guia de plano na forma com parâmetros da consulta:</span><span class="sxs-lookup"><span data-stu-id="c501e-106">Here is the plan guide on the parameterized form of the query:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'TemplateGuide1',  
    @stmt = N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
              INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
                  ON h.SalesOrderID = d.SalesOrderID  
              WHERE h.SalesOrderID = @0',  
    @type = N'TEMPLATE',  
    @module_or_batch = NULL,  
    @params = N'@0 int',  
    @hints = N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="c501e-107">No exemplo anterior, o valor do parâmetro `@stmt` é a forma com parâmetros da consulta.</span><span class="sxs-lookup"><span data-stu-id="c501e-107">In the previous example, the value for the `@stmt` parameter is the parameterized form of the query.</span></span> <span data-ttu-id="c501e-108">O único modo confiável de obter esse valor para uso em sp_create_plan_guide é por meio do procedimento armazenado do sistema [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c501e-108">The only reliable way to obtain this value for use in sp_create_plan_guide is to use the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span> <span data-ttu-id="c501e-109">O script a seguir pode ser usado para obter a consulta parametrizada e, em seguida, criar um guia de plano para ela.</span><span class="sxs-lookup"><span data-stu-id="c501e-109">The following script can be used both to obtain the parameterized query and then create a plan guide on it.</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
      INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
          ON h.SalesOrderID = d.SalesOrderID  
      WHERE h.SalesOrderID = 45639;',  
    @stmt OUTPUT,   
    @params OUTPUT  
EXEC sp_create_plan_guide N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c501e-110">O valor dos literais constantes no parâmetro `@stmt` passado para `sp_get_query_template` pode afetar o tipo de dados escolhido para o parâmetro que substitui a literal.</span><span class="sxs-lookup"><span data-stu-id="c501e-110">The value of the constant literals in the `@stmt` parameter passed to `sp_get_query_template` might affect the data type that is chosen for the parameter that replaces the literal.</span></span> <span data-ttu-id="c501e-111">Isso afetará a correspondência do guia de plano.</span><span class="sxs-lookup"><span data-stu-id="c501e-111">This will affect plan guide matching.</span></span> <span data-ttu-id="c501e-112">Pode ser necessário criar mais de um guia de plano para lidar com diferentes intervalos de valores de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c501e-112">You may have to create more than one plan guide to handle different parameter value ranges.</span></span>  
  
 <span data-ttu-id="c501e-113">Também é possível usar os guias de plano TEMPLATE com os guias de plano SQL.</span><span class="sxs-lookup"><span data-stu-id="c501e-113">You can also use TEMPLATE plan guides together with SQL plan guides.</span></span> <span data-ttu-id="c501e-114">Por exemplo, você pode criar um guia de plano TEMPLATE para ter certeza que uma classe de consultas contém parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c501e-114">For example, you can create a TEMPLATE plan guide to make sure that a class of queries is parameterized.</span></span> <span data-ttu-id="c501e-115">Em seguida, é possível criar um guia de plano SQL na forma com parâmetros dessa consulta.</span><span class="sxs-lookup"><span data-stu-id="c501e-115">You can then create an SQL plan guide on the parameterized form of that query.</span></span>  
  
  
