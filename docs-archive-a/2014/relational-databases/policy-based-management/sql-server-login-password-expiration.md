---
title: Expiração da senha de logon do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7e3bf9da-a436-433d-847a-47c30428cad3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 678e8e9c6b567014bdd49e89d043165bc48d168a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569392"
---
# <a name="sql-server-login-password-expiration"></a><span data-ttu-id="42ed3-102">Vencimento da senha de logon do SQL Server</span><span class="sxs-lookup"><span data-stu-id="42ed3-102">SQL Server Login Password Expiration</span></span>
  <span data-ttu-id="42ed3-103">Esta regra verifica se a "Expiração de senha" de cada logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitada.</span><span class="sxs-lookup"><span data-stu-id="42ed3-103">This rule checks whether "Password expiration" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="42ed3-104">Se a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver habilitada e a versão do sistema operacional for anterior ao [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], um invasor poderá explorar repetidamente uma senha conhecida de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42ed3-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="42ed3-105">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="42ed3-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="42ed3-106">Recomendamos que você atualize o sistema operacional para o [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42ed3-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="42ed3-107">Se a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não for necessária em seu ambiente, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="42ed3-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span> <span data-ttu-id="42ed3-108">Para obter mais informações, veja [Escolher um modo de autenticação](../security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="42ed3-108">For more information, see [Choose an Authentication Mode](../security/choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="42ed3-109">Habilite a "Expiração de senha" para todos os logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42ed3-109">Enable "Password expiration" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="42ed3-110">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) para configurar a política de senha para o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42ed3-110">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="42ed3-111">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="42ed3-111">For More Information</span></span>  
 [<span data-ttu-id="42ed3-112">Política de senha</span><span class="sxs-lookup"><span data-stu-id="42ed3-112">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="42ed3-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42ed3-113">See Also</span></span>  
 [<span data-ttu-id="42ed3-114">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="42ed3-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
