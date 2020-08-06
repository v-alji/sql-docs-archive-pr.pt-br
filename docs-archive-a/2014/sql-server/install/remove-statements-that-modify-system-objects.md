---
title: Remover instruções que modificam objetos do sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- direct system catalog updates [SQL Server]
- system catalogs [SQL Server]
ms.assetid: 221b46c2-c27e-4df8-bd8c-8b990d6d5e98
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 526181bc4bf7ab81df2eaa25f19e7627c9b7af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686050"
---
# <a name="remove-statements-that-modify-system-objects"></a><span data-ttu-id="8a797-102">Remover instruções que modificam objetos do sistema</span><span class="sxs-lookup"><span data-stu-id="8a797-102">Remove statements that modify system objects</span></span>
  <span data-ttu-id="8a797-103">O Supervisor de Atualização detectou instruções que atualizam o catálogo do sistema.</span><span class="sxs-lookup"><span data-stu-id="8a797-103">Upgrade Advisor detected statements that update the system catalog.</span></span> <span data-ttu-id="8a797-104">Atualizações diretas no catálogo do sistema não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="8a797-104">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="8a797-105">Modifique seus scripts SQL para usar APIs oficiais e documentadas.</span><span class="sxs-lookup"><span data-stu-id="8a797-105">Modify your SQL scripts to use official and documented APIs.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8a797-106">Componente</span><span class="sxs-lookup"><span data-stu-id="8a797-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="8a797-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="8a797-107">Description</span></span>  
 <span data-ttu-id="8a797-108">Atualizações diretas no catálogo do sistema não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="8a797-108">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="8a797-109">Qualquer tentativa para fazer essas atualizações gerará o erro seguinte:</span><span class="sxs-lookup"><span data-stu-id="8a797-109">Any attempt to do so will generate the following error:</span></span>  
  
 `Server: Msg 259, Level 16, State 1, Line 1`  
  
 `Ad hoc updates to system catalogs are not allowed.`  
  
## <a name="corrective-action"></a><span data-ttu-id="8a797-110">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="8a797-110">Corrective Action</span></span>  
 <span data-ttu-id="8a797-111">Modifique seus scripts SQL para usar APIs oficiais e documentadas.</span><span class="sxs-lookup"><span data-stu-id="8a797-111">Modify your SQL scripts to use official and documented APIs.</span></span> <span data-ttu-id="8a797-112">Por exemplo, use ALTER DATABASE *database_name* SET EMERGENCY em vez de executar uma instrução UPDATE na tabela de sistema **sysdatabases** .</span><span class="sxs-lookup"><span data-stu-id="8a797-112">For example, use ALTER DATABASE *database_name* SET EMERGENCY instead of running an UPDATE statement on the **sysdatabases** system table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a797-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a797-113">See Also</span></span>  
 <span data-ttu-id="8a797-114">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8a797-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8a797-115">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="8a797-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
