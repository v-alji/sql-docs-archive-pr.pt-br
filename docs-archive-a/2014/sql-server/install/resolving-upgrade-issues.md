---
title: Resolvendo problemas de atualização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Upgrade Advisor [SQL Server], reference
- component issue resolution [Upgrade Advisor]
- resolving upgrade issues
- upgrade blocks [Upgrade Advisor]
- detecting upgrade issues
- finding upgrade issues
- Upgrade Advisor [SQL Server], blocking issues
- configurations preventing upgrading [Upgrade Advisor]
- locating upgrade issues
- blocking issues [Upgrade Advisor]
- issues preventing upgrading [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, reference
- analyzing system [Upgrade Advisor], resolving issues
- settings preventing upgrading [Upgrade Advisor]
- upgrade issue reference [Upgrade Advisor]
- identifying upgrade issues
- fixing upgrade issues [Upgrade Advisor]
ms.assetid: 113eb435-8d36-4ed6-9790-b5e4c14809c8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c00b08d40bc8c17013e6af19b5d11b0b7ad78c4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583336"
---
# <a name="resolving-upgrade-issues"></a><span data-ttu-id="484e1-102">Solucionando problemas de atualização</span><span class="sxs-lookup"><span data-stu-id="484e1-102">Resolving Upgrade Issues</span></span>
  <span data-ttu-id="484e1-103">Os tópicos desta seção descrevem os problemas de atualização que podem ser detectados e os que não podem, mas que talvez afetem a atualização ou a experiência pós-atualização.</span><span class="sxs-lookup"><span data-stu-id="484e1-103">The topics in this section describe upgrade issues that can be detected as well as those that cannot be detected, but that might affect the upgrade or post-upgrade experience.</span></span> <span data-ttu-id="484e1-104">Esses problemas foram organizados por componente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="484e1-104">The issues are organized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="484e1-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="484e1-105">In This Section</span></span>  
  
-   [<span data-ttu-id="484e1-106">Problemas detectados recentemente que podem interromper a instalação</span><span class="sxs-lookup"><span data-stu-id="484e1-106">Late-Breaking Upgrade Issues</span></span>](../../../2014/sql-server/install/late-breaking-upgrade-issues.md)  
  
-   [<span data-ttu-id="484e1-107">Problemas de atualização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="484e1-107">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
-   [<span data-ttu-id="484e1-108">Problemas de atualização da Pesquisa de Texto Completo</span><span class="sxs-lookup"><span data-stu-id="484e1-108">Full-Text Search Upgrade Issues</span></span>](../../../2014/sql-server/install/full-text-search-upgrade-issues.md)  
  
-   [<span data-ttu-id="484e1-109">Problemas na atualização da replicação</span><span class="sxs-lookup"><span data-stu-id="484e1-109">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
-   [<span data-ttu-id="484e1-110">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="484e1-110">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
-   [<span data-ttu-id="484e1-111">Problemas de atualização do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="484e1-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
## <a name="issues-that-prevent-upgrading"></a><span data-ttu-id="484e1-112">Problemas que impedem a atualização</span><span class="sxs-lookup"><span data-stu-id="484e1-112">Issues That Prevent Upgrading</span></span>  
 <span data-ttu-id="484e1-113">Algumas configurações ou definições em uma versão anterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem impedir a atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="484e1-113">A few configurations or settings in a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="484e1-114">Se a Instalação detectar esses problemas ao instalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], ela interromperá o processo de atualização e solicitará que você execute o Supervisor de Atualização e corrija os impedimentos.</span><span class="sxs-lookup"><span data-stu-id="484e1-114">If Setup detects these issues when you install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Setup stops the upgrade process and requests that you run Upgrade Advisor and fix any blocking issues.</span></span>  
  
### [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
 <span data-ttu-id="484e1-115">Se as tarefas a seguir forem listadas no relatório de atualização do [!INCLUDE[ssDE](../../includes/ssde-md.md)], você deverá executar as ações necessárias antes de atualizar para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="484e1-115">If the following tasks are listed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)] upgrade report, you must perform the required actions before you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span></span>  
  
-   [<span data-ttu-id="484e1-116">Desanexar identificação 32767 do banco de dados</span><span class="sxs-lookup"><span data-stu-id="484e1-116">Detach database ID 32767</span></span>](../../../2014/sql-server/install/detach-database-id-32767.md)  
  
-   [<span data-ttu-id="484e1-117">Renomear logons que coincidem com nomes de funções fixas do servidor</span><span class="sxs-lookup"><span data-stu-id="484e1-117">Rename logins matching fixed server role names</span></span>](../../../2014/sql-server/install/rename-logins-matching-fixed-server-role-names.md)  
  
-   [<span data-ttu-id="484e1-118">Renomear usuário sys</span><span class="sxs-lookup"><span data-stu-id="484e1-118">Rename user sys</span></span>](../../../2014/sql-server/install/rename-user-sys.md)  
  
-   [<span data-ttu-id="484e1-119">Usar sp_rename para renomear o nome do índice duplicado</span><span class="sxs-lookup"><span data-stu-id="484e1-119">Use sp_rename to rename duplicate index name</span></span>](../../../2014/sql-server/install/use-sp-rename-to-rename-duplicate-index-name.md)  
  
## <a name="see-also"></a><span data-ttu-id="484e1-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="484e1-120">See Also</span></span>  
 [<span data-ttu-id="484e1-121">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="484e1-121">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
