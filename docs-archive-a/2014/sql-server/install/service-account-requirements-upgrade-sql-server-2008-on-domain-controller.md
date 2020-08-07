---
title: Requisitos de conta de serviço para atualização para o SQL Server 2008 em um controlador de domínio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- domain controllers
- service accounts
- network service accounts
- local service accounts
ms.assetid: 574245b6-11e2-4849-b0ca-836d673ecd0d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0680e09548e38760f6ac317fec63152486a4e5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573456"
---
# <a name="service-account-requirements-for-upgrading-to-sql-server-2008-on-a-domain-controller"></a><span data-ttu-id="6816f-102">Requisitos da conta de serviço para atualização para o SQL Server 2008 em um controlador de domínio</span><span class="sxs-lookup"><span data-stu-id="6816f-102">Service account requirements for upgrading to SQL Server 2008 on a domain controller</span></span>
  <span data-ttu-id="6816f-103">O supervisor de atualização detectou uma instância do em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] execução em um serviço de rede ou em uma conta de serviço local em um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="6816f-103">Upgrade Advisor detected an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running under a Network Service or Local Service account on a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller.</span></span> <span data-ttu-id="6816f-104">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado em um controlador de domínio do [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não podem executar em privilégios de conta de Serviço Local ou Serviço de Rede.</span><span class="sxs-lookup"><span data-stu-id="6816f-104">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services cannot run under Local Service account or Network Service account privileges.</span></span>  
  
## <a name="component"></a><span data-ttu-id="6816f-105">Componente</span><span class="sxs-lookup"><span data-stu-id="6816f-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="6816f-106">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="6816f-106">Corrective Action</span></span>  
 <span data-ttu-id="6816f-107">Certifique-se de que todas as contas de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estão atribuídas a contas de Domínio ou Sistema Local.</span><span class="sxs-lookup"><span data-stu-id="6816f-107">Make sure that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service accounts are assigned to either Domain accounts or Local System accounts.</span></span> <span data-ttu-id="6816f-108">Caso essa alteração não seja feita antes da atualização, a Instalação será interrompida.</span><span class="sxs-lookup"><span data-stu-id="6816f-108">Failure to make this change before upgrading will block Setup.</span></span> <span data-ttu-id="6816f-109">As contas de serviço do Gravador do SQL, o Auxiliar do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] os Serviços Auxiliares do Active Directory são exceções, pois eles são codificados para a conta de Serviço de Rede e não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="6816f-109">The service accounts SQL Writer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Active Directory Helper services are exceptions because they are hard-coded to the Network Service account and cannot be changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6816f-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6816f-110">See Also</span></span>  
 <span data-ttu-id="6816f-111">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6816f-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="6816f-112">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="6816f-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
