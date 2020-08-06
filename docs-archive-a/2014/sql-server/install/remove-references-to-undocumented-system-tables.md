---
title: Remover referências a tabelas do sistema não documentadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system tables [SQL Server]
- system tables [SQL Server]
ms.assetid: 010b1236-2219-4bf4-a6db-e3fc3abfa37a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 45c38038ee3d3214e4303c0ddbe0110be926c37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683319"
---
# <a name="remove-references-to-undocumented-system-tables"></a><span data-ttu-id="8fce2-102">Remover referências a tabelas do sistema não documentadas</span><span class="sxs-lookup"><span data-stu-id="8fce2-102">Remove references to undocumented system tables</span></span>
  <span data-ttu-id="8fce2-103">Muitas tabelas do sistema que não foram documentadas em versões anteriores foram alteradas ou deixaram de existir. Portanto, utilizar essas tabelas após a atualização pode causar erros.</span><span class="sxs-lookup"><span data-stu-id="8fce2-103">Many system tables that were undocumented in prior releases have changed or no longer exist; therefore, using these tables may cause errors after upgrading.</span></span> <span data-ttu-id="8fce2-104">O Supervisor de Atualização procura referências a nomes de tabelas do sistema, portanto ele reportará referências a qualquer tabela do usuário que contenha o mesmo nome de uma tabela do sistema.</span><span class="sxs-lookup"><span data-stu-id="8fce2-104">Because Upgrade Advisor looks for references to system table names, it will report references to any user tables that have the same names as system tables.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8fce2-105">Componente</span><span class="sxs-lookup"><span data-stu-id="8fce2-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="8fce2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="8fce2-106">Description</span></span>  
 <span data-ttu-id="8fce2-107">As seguintes tabelas do sistema não documentadas foram removidas:</span><span class="sxs-lookup"><span data-stu-id="8fce2-107">The following undocumented system tables are removed:</span></span>  
  
-   <span data-ttu-id="8fce2-108">**spt_datatype_info**</span><span class="sxs-lookup"><span data-stu-id="8fce2-108">**spt_datatype_info**</span></span>  
  
-   <span data-ttu-id="8fce2-109">**spt_datatype_info_ext**</span><span class="sxs-lookup"><span data-stu-id="8fce2-109">**spt_datatype_info_ext**</span></span>  
  
-   <span data-ttu-id="8fce2-110">**spt_provider_types**</span><span class="sxs-lookup"><span data-stu-id="8fce2-110">**spt_provider_types**</span></span>  
  
-   <span data-ttu-id="8fce2-111">**spt_server_info**</span><span class="sxs-lookup"><span data-stu-id="8fce2-111">**spt_server_info**</span></span>  
  
-   <span data-ttu-id="8fce2-112">**spt_values**</span><span class="sxs-lookup"><span data-stu-id="8fce2-112">**spt_values**</span></span>  
  
-   <span data-ttu-id="8fce2-113">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="8fce2-113">**sysfulltextnotify**</span></span>  
  
-   <span data-ttu-id="8fce2-114">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="8fce2-114">**syslocks**</span></span>  
  
-   <span data-ttu-id="8fce2-115">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="8fce2-115">**sysproperties**</span></span>  
  
-   <span data-ttu-id="8fce2-116">**sysprotects_aux**</span><span class="sxs-lookup"><span data-stu-id="8fce2-116">**sysprotects_aux**</span></span>  
  
-   <span data-ttu-id="8fce2-117">**sysprotects_view**</span><span class="sxs-lookup"><span data-stu-id="8fce2-117">**sysprotects_view**</span></span>  
  
-   <span data-ttu-id="8fce2-118">**SYSREMOTE_CATALOGS**</span><span class="sxs-lookup"><span data-stu-id="8fce2-118">**SYSREMOTE_CATALOGS**</span></span>  
  
-   <span data-ttu-id="8fce2-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="8fce2-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="8fce2-120">**SYSREMOTE_COLUMNS**</span><span class="sxs-lookup"><span data-stu-id="8fce2-120">**SYSREMOTE_COLUMNS**</span></span>  
  
-   <span data-ttu-id="8fce2-121">**SYSREMOTE_FOREIGN_KEYS**</span><span class="sxs-lookup"><span data-stu-id="8fce2-121">**SYSREMOTE_FOREIGN_KEYS**</span></span>  
  
-   <span data-ttu-id="8fce2-122">**SYSREMOTE_INDEXES**</span><span class="sxs-lookup"><span data-stu-id="8fce2-122">**SYSREMOTE_INDEXES**</span></span>  
  
-   <span data-ttu-id="8fce2-123">**SYSREMOTE_PRIMARY_KEYS**</span><span class="sxs-lookup"><span data-stu-id="8fce2-123">**SYSREMOTE_PRIMARY_KEYS**</span></span>  
  
-   <span data-ttu-id="8fce2-124">**SYSREMOTE_PROVIDER_TYPES**</span><span class="sxs-lookup"><span data-stu-id="8fce2-124">**SYSREMOTE_PROVIDER_TYPES**</span></span>  
  
-   <span data-ttu-id="8fce2-125">**SYSREMOTE_SCHEMATA**</span><span class="sxs-lookup"><span data-stu-id="8fce2-125">**SYSREMOTE_SCHEMATA**</span></span>  
  
-   <span data-ttu-id="8fce2-126">**SYSREMOTE_STATISTICS**</span><span class="sxs-lookup"><span data-stu-id="8fce2-126">**SYSREMOTE_STATISTICS**</span></span>  
  
-   <span data-ttu-id="8fce2-127">**SYSREMOTE_TABLE_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="8fce2-127">**SYSREMOTE_TABLE_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="8fce2-128">**SYSREMOTE_TABLES**</span><span class="sxs-lookup"><span data-stu-id="8fce2-128">**SYSREMOTE_TABLES**</span></span>  
  
-   <span data-ttu-id="8fce2-129">**SYSREMOTE_VIEWS**</span><span class="sxs-lookup"><span data-stu-id="8fce2-129">**SYSREMOTE_VIEWS**</span></span>  
  
-   <span data-ttu-id="8fce2-130">**syssegments**</span><span class="sxs-lookup"><span data-stu-id="8fce2-130">**syssegments**</span></span>  
  
-   <span data-ttu-id="8fce2-131">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="8fce2-131">**sysxlogins**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="8fce2-132">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="8fce2-132">Corrective Action</span></span>  
 <span data-ttu-id="8fce2-133">Modifique seus aplicativos de acordo com a tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="8fce2-133">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="8fce2-134">Em vez de</span><span class="sxs-lookup"><span data-stu-id="8fce2-134">Instead of</span></span>|<span data-ttu-id="8fce2-135">Uso</span><span class="sxs-lookup"><span data-stu-id="8fce2-135">Use</span></span>|  
|----------------|---------|  
|<span data-ttu-id="8fce2-136">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="8fce2-136">**sysfulltextnotify**</span></span>|<span data-ttu-id="8fce2-137">Propriedade**TableFulltextPendingChanges** da função OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="8fce2-137">**TableFulltextPendingChanges** property of the OBJECTPROPERTYEX function.</span></span>|  
|<span data-ttu-id="8fce2-138">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="8fce2-138">**syslocks**</span></span>|<span data-ttu-id="8fce2-139">Exibição de gerenciamento dinâmico**sys.dm_tran_locks** , sp_lock ou exibição de compatibilidade **sys.syslockinfo** .</span><span class="sxs-lookup"><span data-stu-id="8fce2-139">**sys.dm_tran_locks** dynamic management view, or sp_lock, or the **sys.syslockinfo** compatibility view.</span></span>|  
|<span data-ttu-id="8fce2-140">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="8fce2-140">**sysproperties**</span></span>|<span data-ttu-id="8fce2-141">Exibição de catálogo**sys.extended_properties** ou função **fn_listextendedproperty**</span><span class="sxs-lookup"><span data-stu-id="8fce2-141">**sys.extended_properties** catalog view or the **fn_listextendedproperty** function</span></span>|  
|<span data-ttu-id="8fce2-142">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="8fce2-142">**sysxlogins**</span></span>|<span data-ttu-id="8fce2-143">Exibição de catálogo**sys.server_principals** ou exibição de compatibilidade **syslogins** .</span><span class="sxs-lookup"><span data-stu-id="8fce2-143">**sys.server_principals** catalog view or **syslogins** compatibility view.</span></span>|  
|<span data-ttu-id="8fce2-144">Todas as tabelas **spt_** .</span><span class="sxs-lookup"><span data-stu-id="8fce2-144">all **spt_** tables</span></span>|<span data-ttu-id="8fce2-145">Não há substituição disponível.</span><span class="sxs-lookup"><span data-stu-id="8fce2-145">No replacement available</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8fce2-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8fce2-146">See Also</span></span>  
 <span data-ttu-id="8fce2-147">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8fce2-147">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8fce2-148">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="8fce2-148">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
