---
title: SQL Server Agent categoria de trabalho de envio de logs faz com que a atualização falhe | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
- job categories [SQL Server Agent]
ms.assetid: ef05ce53-c6ce-42ec-9df8-46c951626424
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2f5947e8fc8d459388fe35d86c75666e25b5d907
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686035"
---
# <a name="sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail"></a><span data-ttu-id="70679-102">Categoria do trabalho Envio de Logs do SQL Server Agent causa falha na atualização</span><span class="sxs-lookup"><span data-stu-id="70679-102">SQL Server Agent log shipping job category causes upgrade to fail</span></span>
  <span data-ttu-id="70679-103">O processo de atualização falhará se uma categoria de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, nomeada Envio de Log, existir.</span><span class="sxs-lookup"><span data-stu-id="70679-103">The upgrade process will fail if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category named Log Shipping exists.</span></span>  
  
## <a name="component"></a><span data-ttu-id="70679-104">Componente</span><span class="sxs-lookup"><span data-stu-id="70679-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="70679-105">Agent</span><span class="sxs-lookup"><span data-stu-id="70679-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="70679-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="70679-106">Description</span></span>  
 <span data-ttu-id="70679-107">Há uma categoria de trabalho do sistema chamada Envio de Logs.</span><span class="sxs-lookup"><span data-stu-id="70679-107">There is a system job category named Log Shipping.</span></span> <span data-ttu-id="70679-108">Se uma instalação que está sendo atualizada tiver uma categoria de trabalho criada pelo usuário com esse nome, o nome deverá ser alterado antes da atualização. Caso contrário, o processo de atualização falhará.</span><span class="sxs-lookup"><span data-stu-id="70679-108">If an installation that is being upgraded already contains a user-created job category named Log Shipping, you must rename the job category before you upgrade; otherwise, the upgrade process will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70679-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70679-109">See Also</span></span>  
 <span data-ttu-id="70679-110">[O envio de logs não será executado após a atualização](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span><span class="sxs-lookup"><span data-stu-id="70679-110">[Log shipping will not run after upgrading](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span></span>  
 <span data-ttu-id="70679-111">[A atualização alterará o SQL Server Agent conta proxy do usuário para o UpgradedProxyAccount temporário](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="70679-111">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 [<span data-ttu-id="70679-112">Problemas de atualização do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="70679-112">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
