---
title: Nível de segurança da senha de logon do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b0862c3a-926b-490c-a37f-382e50146a3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5534748fbbf810539f2dcfc22239e4b987cf0f77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679294"
---
# <a name="sql-server-login-password-strength"></a><span data-ttu-id="c1c31-102">Nível de segurança da senha de logon do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c1c31-102">SQL Server Login Password Strength</span></span>
  <span data-ttu-id="c1c31-103">Esta regra verifica se “Impor política de senha” de cada logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c1c31-103">This rule checks whether "Enforce password policy" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="c1c31-104">Se a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver habilitada e a versão do sistema operacional for anterior ao [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], um invasor poderá explorar repetidamente uma senha conhecida de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1c31-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c1c31-105">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="c1c31-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c1c31-106">Recomendamos que você atualize o sistema operacional para o [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1c31-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="c1c31-107">Se a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não for necessária em seu ambiente, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="c1c31-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="c1c31-108">Habilite “Impor política de senha” para todos os logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1c31-108">Enable "Enforce password policy" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="c1c31-109">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) para configurar a política de senha para o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1c31-109">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="c1c31-110">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="c1c31-110">For More Information</span></span>  
 [<span data-ttu-id="c1c31-111">Política de senha</span><span class="sxs-lookup"><span data-stu-id="c1c31-111">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1c31-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c1c31-112">See Also</span></span>  
 [<span data-ttu-id="c1c31-113">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="c1c31-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
