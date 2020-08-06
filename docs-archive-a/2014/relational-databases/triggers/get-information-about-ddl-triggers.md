---
title: Obter informações sobre gatilhos DDL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- status information [SQL Server], DDL triggers
- DDL triggers, metadata
ms.assetid: 462becea-292a-4b9e-bb98-533e89733911
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cd71d188c2f53bd9872359199c07d700688552d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582877"
---
# <a name="get-information-about-ddl-triggers"></a><span data-ttu-id="1cc62-102">Obter informações sobre gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="1cc62-102">Get Information About DDL Triggers</span></span>
  <span data-ttu-id="1cc62-103">Pode-se usar as exibições do catálogo listadas nesta seção para obter informações sobre gatilhos DDL.</span><span class="sxs-lookup"><span data-stu-id="1cc62-103">The catalog views listed in this section can be used to get information about DDL Triggers.</span></span>  
  
 <span data-ttu-id="1cc62-104">**Para obter informações sobre os eventos ou grupos de evento nos quais um gatilho DDL pode ser acionado.**</span><span class="sxs-lookup"><span data-stu-id="1cc62-104">**To get information about the events or event groups on which a DDL trigger can fire.**</span></span>  
  
-   [<span data-ttu-id="1cc62-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-event-types-transact-sql)  
  
 <span data-ttu-id="1cc62-106">**Para exibir as dependências de um gatilho**</span><span class="sxs-lookup"><span data-stu-id="1cc62-106">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="1cc62-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="1cc62-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="1cc62-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="database-scoped-ddl-triggers"></a><span data-ttu-id="1cc62-110">gatilhos DDL no escopo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="1cc62-110">Database-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="1cc62-111">**Para obter informações sobre gatilhos no escopo do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="1cc62-111">**To get information about database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="1cc62-112">sys.triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-112">sys.triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql)  
  
 <span data-ttu-id="1cc62-113">**Para obter informações sobre eventos de banco de dados que acionam gatilhos**</span><span class="sxs-lookup"><span data-stu-id="1cc62-113">**To get information about database events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="1cc62-114">sys.trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-114">sys.trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql)  
  
 <span data-ttu-id="1cc62-115">**Para exibir a definição de um gatilho no escopo do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="1cc62-115">**To view the definition of a database-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="1cc62-116">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-116">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
 <span data-ttu-id="1cc62-117">**Para obter informações sobre gatilhos no escopo do banco de dados CLR**</span><span class="sxs-lookup"><span data-stu-id="1cc62-117">**To get information about CLR database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="1cc62-118">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-118">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
## <a name="server-scoped-ddl-triggers"></a><span data-ttu-id="1cc62-119">Gatilhos DDL no escopo do servidor</span><span class="sxs-lookup"><span data-stu-id="1cc62-119">Server-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="1cc62-120">**Para obter informações sobre gatilhos no escopo do servidor**</span><span class="sxs-lookup"><span data-stu-id="1cc62-120">**To get information about server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="1cc62-121">sys.server_triggers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-121">sys.server_triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql)  
  
 <span data-ttu-id="1cc62-122">**Para obter informações sobre eventos de servidor que acionam gatilhos**</span><span class="sxs-lookup"><span data-stu-id="1cc62-122">**To get information about server events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="1cc62-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql)  
  
 <span data-ttu-id="1cc62-124">**Para exibir a definição de um gatilho no escopo do servidor**</span><span class="sxs-lookup"><span data-stu-id="1cc62-124">**To view the definition of a server-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="1cc62-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql)  
  
 <span data-ttu-id="1cc62-126">**Para obter informações sobre gatilhos no escopo do servidor CLR**</span><span class="sxs-lookup"><span data-stu-id="1cc62-126">**To get information about CLR server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="1cc62-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cc62-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="1cc62-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1cc62-128">See Also</span></span>  
 [<span data-ttu-id="1cc62-129">Gatilhos DDL</span><span class="sxs-lookup"><span data-stu-id="1cc62-129">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
