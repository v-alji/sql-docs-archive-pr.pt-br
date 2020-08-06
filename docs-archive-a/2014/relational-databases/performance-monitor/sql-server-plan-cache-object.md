---
title: SQL Server, objeto Cache de planos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Plan Cache object
- SQLServer:Plan Cache
ms.assetid: 225e2b02-8d2f-4f29-9eba-f5847c36ea99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 002cbe261c531c18bdbb2170da9694cc8abde89d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679318"
---
# <a name="sql-server-plan-cache-object"></a><span data-ttu-id="427e1-102">SQL Server, objeto Cache de planos</span><span class="sxs-lookup"><span data-stu-id="427e1-102">SQL Server, Plan Cache Object</span></span>
  <span data-ttu-id="427e1-103">O objeto **Plan Cache** fornece contadores para monitorar como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa a memória para armazenar objetos, como procedimentos armazenados e instruções e gatilhos [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc e preparados.</span><span class="sxs-lookup"><span data-stu-id="427e1-103">The **Plan Cache** object provides counters to monitor how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses memory to store objects such as stored procedures, ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, and triggers.</span></span> <span data-ttu-id="427e1-104">Diversas instâncias do objeto **Plan Cache** podem ser monitoradas ao mesmo tempo, com cada instância representando um tipo de plano diferente para monitorar.</span><span class="sxs-lookup"><span data-stu-id="427e1-104">Multiple instances of the **Plan Cache** object can be monitored at the same time, with each instance representing a different type of plan to monitor.</span></span>  
  
 <span data-ttu-id="427e1-105">Esta tabela descreve os contadores **SQLServer:Plan Cache**.</span><span class="sxs-lookup"><span data-stu-id="427e1-105">This table describes are the **SQLServer:Plan Cache**counters.</span></span>  
  
|<span data-ttu-id="427e1-106">Contadores SQL Server Plan Cache</span><span class="sxs-lookup"><span data-stu-id="427e1-106">SQL Server Plan Cache counters</span></span>|<span data-ttu-id="427e1-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="427e1-107">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="427e1-108">**Taxa de Acertos do Cache**</span><span class="sxs-lookup"><span data-stu-id="427e1-108">**Cache Hit Ratio**</span></span>|<span data-ttu-id="427e1-109">Taxa entre acertos e pesquisas do cache.</span><span class="sxs-lookup"><span data-stu-id="427e1-109">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="427e1-110">**Contagens de Objeto do Cache**</span><span class="sxs-lookup"><span data-stu-id="427e1-110">**Cache Object Counts**</span></span>|<span data-ttu-id="427e1-111">Número de objetos do cache no cache.</span><span class="sxs-lookup"><span data-stu-id="427e1-111">Number of cache objects in the cache.</span></span>|  
|<span data-ttu-id="427e1-112">**Páginas do Cache**</span><span class="sxs-lookup"><span data-stu-id="427e1-112">**Cache Pages**</span></span>|<span data-ttu-id="427e1-113">Número de páginas de 8 quilobytes (KB) usado por objetos do cache.</span><span class="sxs-lookup"><span data-stu-id="427e1-113">Number of 8-kilobyte (KB) pages used by cache objects.</span></span>|  
|<span data-ttu-id="427e1-114">**Objetos do cache em uso**</span><span class="sxs-lookup"><span data-stu-id="427e1-114">**Cache Objects in use**</span></span>|<span data-ttu-id="427e1-115">Número de objetos do cache em uso.</span><span class="sxs-lookup"><span data-stu-id="427e1-115">Number of cache objects in use.</span></span>|  
  
 <span data-ttu-id="427e1-116">Cada contador no objeto contém as seguintes instâncias:</span><span class="sxs-lookup"><span data-stu-id="427e1-116">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="427e1-117">Instância do Cache de Plano</span><span class="sxs-lookup"><span data-stu-id="427e1-117">Plan Cache instance</span></span>|<span data-ttu-id="427e1-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="427e1-118">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="427e1-119">**_Total**</span><span class="sxs-lookup"><span data-stu-id="427e1-119">**_Total**</span></span>|<span data-ttu-id="427e1-120">Informações para todos os tipos de instâncias do cache.</span><span class="sxs-lookup"><span data-stu-id="427e1-120">Information for all types of cache instances.</span></span>|  
|<span data-ttu-id="427e1-121">**Planos Sql**</span><span class="sxs-lookup"><span data-stu-id="427e1-121">**Sql Plans**</span></span>|<span data-ttu-id="427e1-122">Os planos de consulta produzidos de uma consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc, inclusive consultas parametrizadas automaticamente ou de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] preparadas usando **sp_prepare** ou **sp_cursorprepare**.</span><span class="sxs-lookup"><span data-stu-id="427e1-122">Query plans produced from an ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] query, including auto-parameterized queries, or from [!INCLUDE[tsql](../../includes/tsql-md.md)] statements prepared using **sp_prepare** or **sp_cursorprepare**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="427e1-123">armazenará em cache os planos para instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc para reutilização posterior se a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] idêntica for executada mais tarde.</span><span class="sxs-lookup"><span data-stu-id="427e1-123">caches the plans for ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for later reuse if the identical [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is later executed.</span></span> <span data-ttu-id="427e1-124">Consultas parametrizadas pelo usuário (mesmo se não preparadas explicitamente) também são monitoradas como Planos SQL Preparados.</span><span class="sxs-lookup"><span data-stu-id="427e1-124">User-parameterized queries (even if not explicitly prepared) are also monitored as Prepared SQL Plans.</span></span>|  
|<span data-ttu-id="427e1-125">**Planos de Objeto**</span><span class="sxs-lookup"><span data-stu-id="427e1-125">**Object Plans**</span></span>|<span data-ttu-id="427e1-126">Planos de consulta gerados ao criar um procedimento armazenado, função ou gatilho.</span><span class="sxs-lookup"><span data-stu-id="427e1-126">Query plans generated by creating a stored procedure, function, or trigger.</span></span>|  
|<span data-ttu-id="427e1-127">**Associar árvores**</span><span class="sxs-lookup"><span data-stu-id="427e1-127">**Bound Trees**</span></span>|<span data-ttu-id="427e1-128">Árvores normalizadas para exibições, regras, colunas computadas e restrições de verificação.</span><span class="sxs-lookup"><span data-stu-id="427e1-128">Normalized trees for views, rules, computed columns, and check constraints.</span></span>|  
|<span data-ttu-id="427e1-129">**Procedimentos armazenados estendidos**</span><span class="sxs-lookup"><span data-stu-id="427e1-129">**Extended Stored Procedures**</span></span>|<span data-ttu-id="427e1-130">Informações do catalogo para procedimentos armazenados estendidos.</span><span class="sxs-lookup"><span data-stu-id="427e1-130">Catalog information for extended stores procedures.</span></span>|  
|<span data-ttu-id="427e1-131">**Tabelas temporárias & variáveis da tabela**</span><span class="sxs-lookup"><span data-stu-id="427e1-131">**Temporary Tables & Table Variables**</span></span>|<span data-ttu-id="427e1-132">Informações do cache relacionadas a tabelas temporárias e tabelas variáveis.</span><span class="sxs-lookup"><span data-stu-id="427e1-132">Cache information related to temporary tables and table variables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="427e1-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="427e1-133">See Also</span></span>  
 <span data-ttu-id="427e1-134">[Opções Server Memory de configuração do servidor](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="427e1-134">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="427e1-135">[SQL Server, objeto Buffer Manager](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="427e1-135">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="427e1-136">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="427e1-136">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
