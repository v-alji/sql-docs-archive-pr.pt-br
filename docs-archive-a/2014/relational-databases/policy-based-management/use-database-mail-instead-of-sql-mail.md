---
title: Usando o Database Mail em vez do SQL Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b08df7be-d8be-4184-a661-38ec0ac85cd1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a6a957b65975645bdeb9f55faee4e650b53718b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571990"
---
# <a name="use-database-mail-instead-of-sql-mail"></a><span data-ttu-id="92942-102">Usando o Database Mail em vez do SQL Mail</span><span class="sxs-lookup"><span data-stu-id="92942-102">Use Database Mail Instead of SQL Mail</span></span>
  <span data-ttu-id="92942-103">Esta regra verifica a exibição do catálogo sys.configurations para determinar se a opção de configuração do servidor do SQL Mail XPs está definida como ON.</span><span class="sxs-lookup"><span data-stu-id="92942-103">This rule checks the sys.configurations catalog view to determine whether the SQL Mail XPs server-wide configuration option is set to ON.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="92942-104">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="92942-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="92942-105">O SQL Mail será removido em uma versão futura do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92942-105">SQL Mail will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="92942-106">Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam.</span><span class="sxs-lookup"><span data-stu-id="92942-106">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="92942-107">Para enviar email, use o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="92942-107">To send mail, use Database Mail.</span></span>  
  
 <span data-ttu-id="92942-108">O SQL Mail é executado em processo de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92942-108">SQL Mail runs in-process to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="92942-109">Se o SQL Mail ficar inoperante, o servidor também ficará.</span><span class="sxs-lookup"><span data-stu-id="92942-109">If SQL Mail goes down, so does the server.</span></span> <span data-ttu-id="92942-110">O Database Mail é executado fora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um processo separado, é escalável e não requer a instalação de componentes de cliente MAPI estendido no servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="92942-110">Database Mail runs outside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a separate process, is scalable, and does not require Extended MAPI client components to be installed on the production server.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="92942-111">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="92942-111">For More Information</span></span>  
 [<span data-ttu-id="92942-112">Database Mail</span><span class="sxs-lookup"><span data-stu-id="92942-112">Database Mail</span></span>](../database-mail/database-mail.md)  
  
## <a name="see-also"></a><span data-ttu-id="92942-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92942-113">See Also</span></span>  
 [<span data-ttu-id="92942-114">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="92942-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
