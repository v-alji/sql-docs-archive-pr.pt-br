---
title: Exibir os destinos de eventos estendidos para pacotes registrados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- viewing event targets
- extended events [SQL Server], viewing targets
ms.assetid: 4985aa5f-ac99-49f6-852c-9d25916549e9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8e796d141ef943399fc2469c232b34b1956cef3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583756"
---
# <a name="view-the-extended-events-targets-for-registered-packages"></a><span data-ttu-id="5da8e-102">Exibir os destinos dos Eventos Estendidos de pacotes registrados</span><span class="sxs-lookup"><span data-stu-id="5da8e-102">View the Extended Events Targets for Registered Packages</span></span>
  <span data-ttu-id="5da8e-103">Antes de criar uma sessão de Eventos Estendidos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , determine quais destinos de Eventos Estendidos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5da8e-103">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to determine what Extended Events targets are available.</span></span> <span data-ttu-id="5da8e-104">Essa tarefa envolve o uso do Editor de Consultas no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para executar o seguinte procedimento.</span><span class="sxs-lookup"><span data-stu-id="5da8e-104">This task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to perform the following procedure.</span></span>  
  
 <span data-ttu-id="5da8e-105">Encerradas as instruções do procedimento, a guia **Resultados** do Editor de Consultas exibirá estas duas colunas:</span><span class="sxs-lookup"><span data-stu-id="5da8e-105">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following two columns:</span></span>  
  
-   <span data-ttu-id="5da8e-106">package_name</span><span class="sxs-lookup"><span data-stu-id="5da8e-106">package_name</span></span>  
  
-   <span data-ttu-id="5da8e-107">target_name</span><span class="sxs-lookup"><span data-stu-id="5da8e-107">target_name</span></span>  
  
## <a name="to-view-the-extended-events-targets-for-registered-packages-using-query-editor"></a><span data-ttu-id="5da8e-108">Para exibir os destinos de Eventos Estendidos de pacotes registrados usando o Editor de Consulta</span><span class="sxs-lookup"><span data-stu-id="5da8e-108">To view the Extended Events targets for registered packages using Query Editor</span></span>  
  
-   <span data-ttu-id="5da8e-109">No Editor de Consultas, emita as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="5da8e-109">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    USE msdb  
    SELECT p.name package_name, o.name target_name  
    FROM sys.dm_xe_objects o  
    JOIN sys.dm_xe_packages p  
         ON o.package_guid = p.guid  
    WHERE o.object_type = 'target'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5da8e-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5da8e-110">See Also</span></span>  
 <span data-ttu-id="5da8e-111">[Destinos de eventos estendidos do SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="5da8e-111">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="5da8e-112">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5da8e-112">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="5da8e-113">sys.dm_xe_packages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5da8e-113">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  
