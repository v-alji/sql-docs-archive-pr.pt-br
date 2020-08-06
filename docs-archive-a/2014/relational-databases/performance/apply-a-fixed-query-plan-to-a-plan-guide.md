---
title: Aplicar um plano de consulta fixo a um guia de plano | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: bbf401f9-af7c-48e7-8a43-bf25e8af2fd7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 318955c4d0550e311873d8b4a6f79f72e04ac8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679309"
---
# <a name="apply-a-fixed-query-plan-to-a-plan-guide"></a><span data-ttu-id="602d3-102">Aplicar um plano de consulta fixo a um guia de plano</span><span class="sxs-lookup"><span data-stu-id="602d3-102">Apply a Fixed Query Plan to a Plan Guide</span></span>
  <span data-ttu-id="602d3-103">É possível aplicar um plano de consulta fixo a um guia de plano do tipo OBJECT ou SQL.</span><span class="sxs-lookup"><span data-stu-id="602d3-103">You can apply a fixed query plan to a plan guide of type OBJECT or SQL.</span></span> <span data-ttu-id="602d3-104">Os guias de plano que se aplicam a um plano de consulta fixo são úteis quando se conhece um plano de execução existente que é melhor do que aquele selecionado pelo otimizador para uma consulta específica.</span><span class="sxs-lookup"><span data-stu-id="602d3-104">Plan guides that apply a fixed query plan are useful when you know about an existing execution plan that performs better than the one selected by the optimizer for a particular query.</span></span>  
  
 <span data-ttu-id="602d3-105">O exemplo a seguir cria um guia de plano para uma instrução SQL ad hoc simples.</span><span class="sxs-lookup"><span data-stu-id="602d3-105">The following example creates a plan guide for a simple ad hoc SQL statement.</span></span> <span data-ttu-id="602d3-106">Especifique o XML Showplan para a consulta diretamente no parâmetro `@hints` para que o plano de consulta desejado para essa instrução seja fornecido no guia de plano.</span><span class="sxs-lookup"><span data-stu-id="602d3-106">The desired query plan for this statement is provided in the plan guide by specifying the XML Showplan for the query directly in the `@hints` parameter.</span></span> <span data-ttu-id="602d3-107">O exemplo executa a instrução SQL primeiro para gerar um plano no cache do esquema.</span><span class="sxs-lookup"><span data-stu-id="602d3-107">The example first executes the SQL statement to generate a plan in the plan cache.</span></span> <span data-ttu-id="602d3-108">Nesse exemplo, supõe-se que o plano gerado é o desejado e que nenhum ajuste de consulta adicional é necessário.</span><span class="sxs-lookup"><span data-stu-id="602d3-108">For the purposes of this example, it is assumed that the generated plan is the desired plan and no additional query tuning is required.</span></span> <span data-ttu-id="602d3-109">O Plano de execução XML da consulta é obtido por meio da consulta das exibições de gerenciamento dinâmico `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`e `sys.dm_exec_text_query_plan` e é atribuído à variável `@xml_showplan` .</span><span class="sxs-lookup"><span data-stu-id="602d3-109">The XML Showplan for the query is obtained by querying the `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`, and `sys.dm_exec_text_query_plan` dynamic management views and is assigned to the `@xml_showplan` variable.</span></span> <span data-ttu-id="602d3-110">Em seguida, a variável `@xml_showplan` é passada à instrução `sp_create_plan_guide` no parâmetro `@hints` .</span><span class="sxs-lookup"><span data-stu-id="602d3-110">The `@xml_showplan` variable is then passed to the `sp_create_plan_guide` statement in the `@hints` parameter.</span></span> <span data-ttu-id="602d3-111">Também é possível criar um guia de plano com base em um plano de consulta no cache de plano por meio do procedimento armazenado [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="602d3-111">Or, you can create a plan guide from a query plan in the plan cache by using the [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;  
GO  
DECLARE @xml_showplan nvarchar(max);  
SET @xml_showplan = (SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%');  
  
EXEC sp_create_plan_guide   
    @name = N'Guide1_from_XML_showplan',   
    @stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',   
    @type = N'SQL',  
    @module_or_batch = NULL,   
    @params = NULL,   
    @hints = @xml_showplan;  
GO  
```  
  
  
