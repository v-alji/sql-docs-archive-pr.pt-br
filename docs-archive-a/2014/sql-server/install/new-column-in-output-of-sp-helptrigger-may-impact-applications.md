---
title: A nova coluna na saída de sp_helptrigger pode afetar os aplicativos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sp_helptrigger
ms.assetid: b7c42a8f-f2e0-4fa3-b046-3cf39c854c47
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b1f5e936843ed84a5c6b88e2f3685e7a4272bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582760"
---
# <a name="new-column-in-output-of-sp_helptrigger-may-impact-applications"></a><span data-ttu-id="757ac-102">Coluna nova no resultado do sp_helptrigger pode impactar nos aplicativos</span><span class="sxs-lookup"><span data-stu-id="757ac-102">New column in output of sp_helptrigger may impact applications</span></span>
  <span data-ttu-id="757ac-103">trigger_schemaias a última coluna no conjunto de resultados retornado pelo procedimento armazenado do sistema sp_helptrigger.</span><span class="sxs-lookup"><span data-stu-id="757ac-103">trigger_schemaias the last column in the result set returned by the sp_helptrigger system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="757ac-104">Para obter informações sobre gatilhos definidos em uma tabela particular, consulte a exibição do catálogo sys.triggers.</span><span class="sxs-lookup"><span data-stu-id="757ac-104">To obtain information about triggers defined on a particular table, query the sys.triggers catalog view.</span></span>  
  
## <a name="component"></a><span data-ttu-id="757ac-105">Componente</span><span class="sxs-lookup"><span data-stu-id="757ac-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="757ac-106">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="757ac-106">Corrective Action</span></span>  
 <span data-ttu-id="757ac-107">Revise o uso de aplicativos sp_helptrigger.</span><span class="sxs-lookup"><span data-stu-id="757ac-107">Review the use of sp_helptrigger in applications.</span></span> <span data-ttu-id="757ac-108">Talvez seja necessário modificar seus aplicativos para acomodar a coluna adicional.</span><span class="sxs-lookup"><span data-stu-id="757ac-108">You may need to modify your applications to accommodate the additional column.</span></span> <span data-ttu-id="757ac-109">Como alternativa, você pode usar a exibição do catálogo sys.triggers.</span><span class="sxs-lookup"><span data-stu-id="757ac-109">Alternatively, you can use the sys.triggers catalog view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757ac-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="757ac-110">See Also</span></span>  
 <span data-ttu-id="757ac-111">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="757ac-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="757ac-112">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="757ac-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
