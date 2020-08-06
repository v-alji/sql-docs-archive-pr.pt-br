---
title: osql não oferece suporte a comandos ED e !! comandos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- ED command
- osql utility [SQL Server]
- '!! command'
ms.assetid: 7cc2852f-94e8-4292-9326-c3f1a1acd281
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1ad92a32c47002c8f56e56a5b3695d42d3bdd671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574448"
---
# <a name="osql-no-longer-supports-the-ed-and--commands"></a><span data-ttu-id="fea17-103">osql não oferece suporte a comandos ED e !!</span><span class="sxs-lookup"><span data-stu-id="fea17-103">osql no longer supports the ED and !!</span></span> <span data-ttu-id="fea17-104">comandos</span><span class="sxs-lookup"><span data-stu-id="fea17-104">commands</span></span>
  <span data-ttu-id="fea17-105">O utilitário **osql** não oferece suporte a **Ed** e **!!**</span><span class="sxs-lookup"><span data-stu-id="fea17-105">The **osql** utility does not support the **ED** and **!!**</span></span> <span data-ttu-id="fea17-106">comandos.</span><span class="sxs-lookup"><span data-stu-id="fea17-106">commands.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="fea17-107">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="fea17-107">Corrective Action</span></span>  
 <span data-ttu-id="fea17-108">Remova as referências ao **Ed** e **!!**</span><span class="sxs-lookup"><span data-stu-id="fea17-108">Remove references to the **ED** and **!!**</span></span> <span data-ttu-id="fea17-109">comandos de seus scripts.</span><span class="sxs-lookup"><span data-stu-id="fea17-109">commands from your scripts.</span></span>  
  
 <span data-ttu-id="fea17-110">Se você quiser usar o **Ed** e o **!!**</span><span class="sxs-lookup"><span data-stu-id="fea17-110">If you want to use the **ED** and **!!**</span></span> <span data-ttu-id="fea17-111">comandos, use o utilitário **sqlcmd** em vez do **osql**.</span><span class="sxs-lookup"><span data-stu-id="fea17-111">commands, use the **sqlcmd** utility instead of **osql**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea17-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fea17-112">See Also</span></span>  
 <span data-ttu-id="fea17-113">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="fea17-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="fea17-114">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="fea17-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
