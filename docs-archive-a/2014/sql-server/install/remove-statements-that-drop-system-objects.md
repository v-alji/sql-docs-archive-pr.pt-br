---
title: Remover instruções que removem objetos do sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- drop system objects [SQL Server]
ms.assetid: cdfc3c50-c801-4039-a4bf-b35f876f1c61
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d9e8fbfd4a436e87cee413d95468ccf5dd36b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569044"
---
# <a name="remove-statements-that-drop-system-objects"></a><span data-ttu-id="7ebfa-102">Remover instruções que descartam objetos do sistema</span><span class="sxs-lookup"><span data-stu-id="7ebfa-102">Remove statements that drop system objects</span></span>
  <span data-ttu-id="7ebfa-103">O Supervisor de Atualização detectou instruções que descartam objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="7ebfa-103">Upgrade Advisor detected statements that drop system objects.</span></span> <span data-ttu-id="7ebfa-104">Os objetos do sistema, incluindo procedimentos armazenados estendidos, são implantados no banco de dados de **recurso** (mssqlsystemresource) somente leitura e não podem ser descartados.</span><span class="sxs-lookup"><span data-stu-id="7ebfa-104">System objects, including extended stored procedures, are deployed in the read-only **resource** database (mssqlsystemresource) and cannot be dropped.</span></span> <span data-ttu-id="7ebfa-105">Modifique seus aplicativos para revocar ou negar a permissão EXECUTE em objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="7ebfa-105">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="7ebfa-106">Componente</span><span class="sxs-lookup"><span data-stu-id="7ebfa-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="7ebfa-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="7ebfa-107">Description</span></span>  
 <span data-ttu-id="7ebfa-108">Instruções como DROP TABLE, DROP PROCEDURE e **sp_dropextendedproc** não podem ser usadas para remover objetos do sistema, pois esses objetos são implantados no banco de dados de **recurso** somente leitura.</span><span class="sxs-lookup"><span data-stu-id="7ebfa-108">Statements such as DROP TABLE, DROP PROCEDURE, and **sp_dropextendedproc** cannot be used to remove system objects, because these objects are deployed in the read-only **resource** database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7ebfa-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="7ebfa-109">Corrective Action</span></span>  
 <span data-ttu-id="7ebfa-110">Remova todas as instruções que tentam descartar objetos do sistema de seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7ebfa-110">Remove all statements that try to drop system objects from your applications.</span></span> <span data-ttu-id="7ebfa-111">Modifique seus aplicativos para revocar ou negar a permissão EXECUTE em objetos do sistema.</span><span class="sxs-lookup"><span data-stu-id="7ebfa-111">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span> <span data-ttu-id="7ebfa-112">Como alternativa, você pode usar a ferramenta SAC (Configuração da Área de Superfície) para desabilitar alguns desses objetos.</span><span class="sxs-lookup"><span data-stu-id="7ebfa-112">Alternatively, you can use the Surface Area Configuration (SAC) tool to disable some of these objects.</span></span> <span data-ttu-id="7ebfa-113">Por exemplo, o procedimento armazenado estendido **xp_cmdshell** pode ser desabilitado ou habilitado usando a ferramenta SAC.</span><span class="sxs-lookup"><span data-stu-id="7ebfa-113">For example, the **xp_cmdshell** extended stored procedure can be disabled or enabled using the SAC tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ebfa-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ebfa-114">See Also</span></span>  
 <span data-ttu-id="7ebfa-115">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="7ebfa-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="7ebfa-116">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="7ebfa-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
