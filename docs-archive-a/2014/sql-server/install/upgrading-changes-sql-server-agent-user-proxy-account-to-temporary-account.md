---
title: A atualização alterará o SQL Server Agent conta proxy do usuário para o UpgradedProxyAccount temporário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
ms.assetid: cd2d08c3-4e56-4034-8b68-0c78df8b5471
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2bca80580a50f2acebed1b6fbea2dec1f6458dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569028"
---
# <a name="upgrading-will-change-the-sql-server-agent-user-proxy-account-to-the-temporary-upgradedproxyaccount"></a><span data-ttu-id="d9ef3-102">Atualização mudará a Conta Proxy do Usuário do SQL Server Agent para o UpgradedProxyAccount temporário</span><span class="sxs-lookup"><span data-stu-id="d9ef3-102">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>
  <span data-ttu-id="d9ef3-103">Planos de manutenção de banco de dados que têm envio de log habilitado não serão ativados após a atualização.</span><span class="sxs-lookup"><span data-stu-id="d9ef3-103">Database maintenance plans that have log shipping enabled will not be enabled after upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="d9ef3-104">Componente</span><span class="sxs-lookup"><span data-stu-id="d9ef3-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d9ef3-105">Agent</span><span class="sxs-lookup"><span data-stu-id="d9ef3-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="d9ef3-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9ef3-106">Description</span></span>  
 <span data-ttu-id="d9ef3-107">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece um conjunto novo de funções de envio de log que não são diretamente compatíveis com planos de manutenção do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d9ef3-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a new set of log shipping functions that are not directly compatible with database maintenance plans.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d9ef3-108">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="d9ef3-108">Corrective Action</span></span>  
 <span data-ttu-id="d9ef3-109">Usuários do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] que possuem planos de manutenção do banco de dados com funções de envio de log devem configurar o envio de log usando as novas funções.</span><span class="sxs-lookup"><span data-stu-id="d9ef3-109">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] users that have database maintenance plans that contain log shipping functions should configure log shipping by using the new functions.</span></span> <span data-ttu-id="d9ef3-110">Para obter mais informações, pesquise sobre 'envio de log’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9ef3-110">For more information, search on "log shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ef3-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9ef3-111">See Also</span></span>  
 <span data-ttu-id="d9ef3-112">[SQL Server Agent categoria de trabalho de envio de logs faz com que a atualização falhe](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="d9ef3-112">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 [<span data-ttu-id="d9ef3-113">Envio de log não executará após a atualização</span><span class="sxs-lookup"><span data-stu-id="d9ef3-113">Log shipping will not run after upgrading</span></span>](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md)  
  
  
