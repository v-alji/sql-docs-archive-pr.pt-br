---
title: O nome do pipe nomeado inválido pode bloquear a atualização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- invalid named pipes [SQL Server]
- named pipes
ms.assetid: 58c2199c-4fdf-4d43-ac1c-842703344b75
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bacfd3d097d7cccb0a5780328c4db95dc5afc733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685001"
---
# <a name="invalid-named-pipe-name-can-block-upgrade"></a><span data-ttu-id="7e6e5-102">Nome de pipe nomeado inválido pode interromper atualização</span><span class="sxs-lookup"><span data-stu-id="7e6e5-102">Invalid named pipe name can block upgrade</span></span>
  <span data-ttu-id="7e6e5-103">A atualização falhará se o protocolo de pipes nomeados estiver configurado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-103">Upgrade fails if the named pipes protocol is incorrectly configured.</span></span>  
  
## <a name="component"></a><span data-ttu-id="7e6e5-104">Componente</span><span class="sxs-lookup"><span data-stu-id="7e6e5-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="7e6e5-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="7e6e5-105">Description</span></span>  
 <span data-ttu-id="7e6e5-106">Durante a atualização, o programa de instalação inicia a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] instância com suporte à memória compartilhada, um pipe nomeado que só aceita conexões locais.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-106">During upgrade, the Setup program starts the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] instance with shared memory support, a named pipe that only accepts local connections.</span></span> <span data-ttu-id="7e6e5-107">Se o nome do pipe especificado no servidor não estiver em branco, ele deverá começar com a cadeia de caracteres " \\ \\ .\pipe \\ " para ser válido.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-107">If the pipe name specified on the server is not blank, it must begin with the string "\\\\.\pipe\\" to be valid.</span></span> <span data-ttu-id="7e6e5-108">Se o nome de pipe não for válido, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] não iniciará e a instalação falhará.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-108">If the pipe name is not valid, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will not start, and setup will fail.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7e6e5-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="7e6e5-109">Corrective Action</span></span>  
 <span data-ttu-id="7e6e5-110">Use o \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utilitário de rede\*\* para fornecer um nome de pipe válido e, em seguida, execute a instalação.</span><span class="sxs-lookup"><span data-stu-id="7e6e5-110">Use the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Utility** to supply a valid pipe name, and then run Setup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e6e5-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e6e5-111">See Also</span></span>  
 <span data-ttu-id="7e6e5-112">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="7e6e5-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="7e6e5-113">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="7e6e5-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
