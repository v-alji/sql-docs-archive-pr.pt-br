---
title: Modificar aplicativos para esperar valores bigint de sysperfinfo. cntr_value | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sysperfinfo
- bigint values [SQL Server]
ms.assetid: b0345303-6e9a-4078-8148-6e1bce207b8c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 108a9b981debc95e182b16847c39a03d4b242088
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684994"
---
# <a name="modify-applications-to-expect-bigint-values-from-sysperfinfocntr_value"></a><span data-ttu-id="878b2-102">Modificar aplicativos para esperar valores bigint de sysperfinfo.cntr_value</span><span class="sxs-lookup"><span data-stu-id="878b2-102">Modify applications to expect bigint values from sysperfinfo.cntr_value</span></span>
  <span data-ttu-id="878b2-103">sysperfinfo retorna um `bigint` valor para a coluna cntr_value.</span><span class="sxs-lookup"><span data-stu-id="878b2-103">sysperfinfo returns a `bigint` value for the cntr_value column.</span></span>  
  
## <a name="component"></a><span data-ttu-id="878b2-104">Componente</span><span class="sxs-lookup"><span data-stu-id="878b2-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="878b2-105">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="878b2-105">Corrective Action</span></span>  
 <span data-ttu-id="878b2-106">Modifique os aplicativos que usam sysperfinfo para assegurar que eles possam lidar com os valores `bigint` da coluna cntr_value.</span><span class="sxs-lookup"><span data-stu-id="878b2-106">Modify applications that use sysperfinfo to ensure that they can handle the `bigint` values of the cntr_value column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="878b2-107">sysperfinfo é uma exibição de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="878b2-107">sysperfinfo is a compatibility view.</span></span> <span data-ttu-id="878b2-108">Em vez disso, você deve usar o gerenciamento dinâmico sys.dm_os_performance_counter.</span><span class="sxs-lookup"><span data-stu-id="878b2-108">You should use the sys.dm_os_performance_counter dynamic management view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="878b2-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="878b2-109">See Also</span></span>  
 <span data-ttu-id="878b2-110">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="878b2-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="878b2-111">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="878b2-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
