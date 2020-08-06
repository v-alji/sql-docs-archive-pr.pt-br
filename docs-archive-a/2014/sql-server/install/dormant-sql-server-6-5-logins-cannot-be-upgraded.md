---
title: Os logons inativos SQL Server 6,5 não podem ser atualizados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- passwords [SQL Server], dormant logins
- dormant logins
- logins [SQL Server], upgrading dormant logins
- identifying dormant logins
- password hashes [SQL Server]
ms.assetid: ebe18a74-0375-4df4-b894-239f8fdabb64
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f78bca9bf2b99b2ab6f530613b64bc0e46c4001c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573483"
---
# <a name="dormant-sql-server-65-logins-cannot-be-upgraded"></a><span data-ttu-id="b16e2-102">Logons inativos do SQL Server 6.5 não podem ser atualizados</span><span class="sxs-lookup"><span data-stu-id="b16e2-102">Dormant SQL Server 6.5 logins cannot be upgraded</span></span>
  <span data-ttu-id="b16e2-103">O Supervisor de Atualização detectou um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuja senha não pode ser atualizada diretamente para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b16e2-103">Upgrade Advisor detected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login whose password cannot be directly upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="b16e2-104">Para ativar esse logon, você deve redefinir a senha.</span><span class="sxs-lookup"><span data-stu-id="b16e2-104">To enable this login, you must reset its password.</span></span> <span data-ttu-id="b16e2-105">Isso pode ser feito usando ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="b16e2-105">You can reset the password by using ALTER LOGIN.</span></span>  
  
```  
ALTER LOGIN <login name> WITH PASSWORD = '<new password>' MUST_CHANGE  
```  
  
 <span data-ttu-id="b16e2-106">A nova senha será validada de acordo com a política de complexidade de senha do seu sistema, a menos que a verificação de política seja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="b16e2-106">The new password will be validated against your system's password complexity policy, unless policy checking is disabled.</span></span> <span data-ttu-id="b16e2-107">Nós recomendamos que você use senhas complexas e não desabilite a verificação de política.</span><span class="sxs-lookup"><span data-stu-id="b16e2-107">We recommend that you use complex passwords and not disable policy checking.</span></span> <span data-ttu-id="b16e2-108">A opção MUST_CHANGE obriga o usuário a selecionar uma senha nova.</span><span class="sxs-lookup"><span data-stu-id="b16e2-108">The MUST_CHANGE option forces the user to select a new password.</span></span> <span data-ttu-id="b16e2-109">Isso não é obrigatório, mas é recomendado.</span><span class="sxs-lookup"><span data-stu-id="b16e2-109">This is not required, but it is recommended.</span></span>  
  
 <span data-ttu-id="b16e2-110">Você pode identificar logons inativos usando a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="b16e2-110">You can identify dormant logins by using the following query:</span></span>  
  
```  
SELECT * FROM sysxlogins WHERE (xstatus & 2048) = 2048;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b16e2-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b16e2-111">See Also</span></span>  
 <span data-ttu-id="b16e2-112">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b16e2-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b16e2-113">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="b16e2-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
