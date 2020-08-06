---
title: Migrar planos de consulta | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- query plans [SQL Server], migrating
- upgrading SQL Server, migrating query plans
- plan guides [SQL Server], migrating query plans
ms.assetid: 7e02a137-6867-4f6a-a45a-2b02674f7e65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dafd3a5f8a460bb08e63919c2cb853ad74dc2f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681832"
---
# <a name="migrate-query-plans"></a><span data-ttu-id="dbb0d-102">Migrar planos de consulta</span><span class="sxs-lookup"><span data-stu-id="dbb0d-102">Migrate Query Plans</span></span>
  <span data-ttu-id="dbb0d-103">Na maioria dos casos, a atualização de um banco de dados para a versão mais recente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resultará em melhoria do desempenho de consulta.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-103">In most cases, upgrading a database to the most recent version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will result in improved query performance.</span></span> <span data-ttu-id="dbb0d-104">No entanto, se você tiver consultas essenciais que foram cuidadosamente ajustadas para desempenho, pode desejar preservar os planos dessas consultas antes da atualização através da criação de um guia de plano para cada consulta.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-104">However, if you have mission-critical queries that have been carefully tuned for performance, you may want to preserve the query plans for these queries before upgrading by creating a plan guide for each query.</span></span> <span data-ttu-id="dbb0d-105">Se depois da atualização o otimizador de consultas escolher um plano menos eficiente para uma ou mais consultas, você pode habilitar os guias de plano e forçar o otimizador de consulta a usar planos anteriores à atualização.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-105">If, after upgrading, the query optimizer chooses a less efficient plan for one or more of the queries, you can enable the plan guides and force the query optimizer to use the pre-upgrade plans.</span></span>  
  
 <span data-ttu-id="dbb0d-106">Para criar guias de plano antes da atualização siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="dbb0d-106">To create plan guides before upgrading follow these steps:</span></span>  
  
1.  <span data-ttu-id="dbb0d-107">Registre o plano atual para cada consulta de missão crítica usando o procedimento armazenado [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) e especificando o plano de consulta na dica de consulta use Plan.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-107">Record the current plan for each mission critical query by using the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure and specifying the query plan in the USE PLAN query hint.</span></span>  
  
2.  <span data-ttu-id="dbb0d-108">Verifique se o guia de plano foi aplicado à consulta.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-108">Verify that the plan guide is applied to the query.</span></span>  
  
3.  <span data-ttu-id="dbb0d-109">Atualize o banco de dados para a versão mais recente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbb0d-109">Upgrade the database to the newer version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="dbb0d-110">Os planos permanecem no banco de dados atualizado nos guias de plano e servem como sistema de apoio no caso de regressões de plano após a atualização.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-110">The plans are persisted in the upgraded database in the plan guides and serve as a fallback in case of plan regressions after the upgrade.</span></span>  
  
     <span data-ttu-id="dbb0d-111">Recomendamos que os guias de plano não sejam habilitados depois da atualização por que você pode perder oportunidades de planos melhores na versão nova ou recompilações vantajosas devido a estatísticas atualizadas.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-111">We recommend that you not enable the plan guides after the upgrade because you might miss opportunities for better plans in the new release or beneficial recompiles due to updated statistics.</span></span>  
  
4.  <span data-ttu-id="dbb0d-112">Se planos menos eficientes forem escolhidos após a atualização, habilite todos ou um subconjunto dos guias de planos para substituir os planos novos.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-112">If less efficient plans are chosen after the upgrade, activate all or a subset of the plan guides to override the new plans.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbb0d-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dbb0d-113">Example</span></span>  
 <span data-ttu-id="dbb0d-114">O exemplo a seguir mostra como registrar um plano anterior à atualização para uma consulta através da criação de um guia de plano.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-114">The following example shows how to record a pre-upgrade plan for a query by creating a plan guide.</span></span>  
  
### <a name="step-1-collect-the-plan"></a><span data-ttu-id="dbb0d-115">Etapa 1: Colete o plano</span><span class="sxs-lookup"><span data-stu-id="dbb0d-115">Step 1: Collect the Plan</span></span>  
 <span data-ttu-id="dbb0d-116">O plano de consulta registrado no guia de plano deve estar em formato XML.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-116">The query plan recorded in the plan guide must be in XML format.</span></span> <span data-ttu-id="dbb0d-117">Planos de consulta em formato XML podem ser produzidos das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="dbb0d-117">XML-formatted query plans can be produced through the following ways:</span></span>  
  
-   [<span data-ttu-id="dbb0d-118">SET SHOWPLAN_XML</span><span class="sxs-lookup"><span data-stu-id="dbb0d-118">SET SHOWPLAN_XML</span></span>](/sql/t-sql/statements/set-showplan-xml-transact-sql)  
  
-   [<span data-ttu-id="dbb0d-119">SET STATISTICS XML</span><span class="sxs-lookup"><span data-stu-id="dbb0d-119">SET STATISTICS XML</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
-   <span data-ttu-id="dbb0d-120">Consultando a coluna query_plan da função de gerenciamento dinâmico [Sys. dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="dbb0d-120">Querying the query_plan column of the [sys.dm_exec_query_plan](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql) dynamic management function.</span></span>  
  
-   <span data-ttu-id="dbb0d-121">As [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] classes de evento [Showplan](../../relational-databases/event-classes/showplan-xml-event-class.md)XML, [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md)e [Showplan XML for Query compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="dbb0d-121">The [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] [Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md), [Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md), and [Showplan XML For Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md) event classes.</span></span>  
  
 <span data-ttu-id="dbb0d-122">O exemplo a seguir coleta o plano de consulta para a instrução `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` examinando exibições de gerenciamento dinâmico.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-122">The following example collects the query plan for the statement `SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;` by querying dynamic management views.</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%';  
GO  
```  
  
### <a name="step-2-create-the-plan-guide-to-force-the-plan"></a><span data-ttu-id="dbb0d-123">Etapa 2: Crie a guia de plano para forçar o plano</span><span class="sxs-lookup"><span data-stu-id="dbb0d-123">Step 2: Create the Plan Guide to Force the Plan</span></span>  
 <span data-ttu-id="dbb0d-124">Usando o plano de consulta com formato XML (obtido através de qualquer um dos métodos anteriormente descritos) no guia de plano, copie e cole o plano de consulta como uma literal de cadeia de caracteres dentro da dica de consulta USE PLAN especificada na cláusula OPTION de sp_create_plan_guide.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-124">Using the XML-formatted query plan (obtained by any of the methods previously described) in the plan guide, copy and paste the query plan as a string literal inside the USE PLAN query hint specified in the OPTION clause of sp_create_plan_guide.</span></span>  
  
 <span data-ttu-id="dbb0d-125">No próprio plano XML, faça a saída das aspas (') que aparecem no plano com um segundo sinal de aspas antes de criar o guia de plano.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-125">Within the XML plan itself, escape quotation marks (') that appear in the plan with a second quotation mark before creating the plan guide.</span></span> <span data-ttu-id="dbb0d-126">Por exemplo, a saída de um plano que contenha `WHERE A.varchar = 'This is a string'` deve ser feita modificando-se o código para `WHERE A.varchar = ''This is a string''`.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-126">For example, a plan that contains `WHERE A.varchar = 'This is a string'` must be escaped by modifying the code to `WHERE A.varchar = ''This is a string''`.</span></span>  
  
 <span data-ttu-id="dbb0d-127">O exemplo a seguir cria um guia de plano para o plano da consulta coletado na etapa 1 e insere o Plano de Execução XML para a consulta no parâmetro `@hints`.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-127">The following example creates a plan guide for the query plan collected in step 1 and inserts the XML Showplan for the query in the `@hints` parameter.</span></span> <span data-ttu-id="dbb0d-128">Para ser breve, apenas uma saída parcial do Plano de Execução é incluída no exemplo.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-128">For brevity, only partial Showplan output is included in the example.</span></span>  
  
```  
EXECUTE sp_create_plan_guide   
@name = N'Guide1',  
@stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',  
@type = N'SQL',  
@module_or_batch = NULL,  
@params = NULL,  
@hints = N'OPTION(USE PLAN N''<ShowPlanXML xmlns=''''https://schemas.microsoft.com/sqlserver/2004/07/showplan''''   
    Version=''''0.5'''' Build=''''9.00.1116''''>  
    <BatchSequence><Batch><Statements><StmtSimple>  
    ...  
    </StmtSimple></Statements></Batch>  
    </BatchSequence></ShowPlanXML>'')';  
GO  
```  
  
### <a name="step-3-verify-that-the-plan-guide-is-applied-to-the-query"></a><span data-ttu-id="dbb0d-129">Etapa 3: Verifique se o guia de plano foi aplicado à consulta.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-129">Step 3: Verify That the Plan Guide Is Applied to the Query</span></span>  
 <span data-ttu-id="dbb0d-130">Execute a consulta novamente e examine o plano de consulta produzido.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-130">Run the query again and examine the query plan that is produced.</span></span> <span data-ttu-id="dbb0d-131">Você deve verificar se o plano corresponde ao que você especificou no guia de plano.</span><span class="sxs-lookup"><span data-stu-id="dbb0d-131">You should see that the plan matches the one that you specified in the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb0d-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dbb0d-132">See Also</span></span>  
 <span data-ttu-id="dbb0d-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dbb0d-133">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="dbb0d-134">[Dicas de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="dbb0d-134">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="dbb0d-135">Guias de plano</span><span class="sxs-lookup"><span data-stu-id="dbb0d-135">Plan Guides</span></span>](../../relational-databases/performance/plan-guides.md)  
  
  
