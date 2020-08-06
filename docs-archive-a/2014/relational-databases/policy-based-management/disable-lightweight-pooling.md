---
title: Desabilitar o Lightweight Pooling | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 481bb43d-6fe5-497c-9096-971fb6bf733b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13b9ccba0a3a5805dab2eec1d04cc161e6dbd6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685601"
---
# <a name="disable-lightweight-pooling"></a><span data-ttu-id="985d7-102">Desabilitar o Lightweight Pooling</span><span class="sxs-lookup"><span data-stu-id="985d7-102">Disable Lightweight Pooling</span></span>
  <span data-ttu-id="985d7-103">Esta regra verifica se o lightweight pooling está desabilitado no servidor.</span><span class="sxs-lookup"><span data-stu-id="985d7-103">This rule checks that lightweight pooling is disabled on the server.</span></span> <span data-ttu-id="985d7-104">Definir lightweightpooling como 1 faz com que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alterne para a programação de modo fibra.</span><span class="sxs-lookup"><span data-stu-id="985d7-104">Setting lightweightpooling to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="985d7-105">O modo fibra foi projetado para determinadas situações nas quais a alternância de contexto dos trabalhadores UMS é o gargalo importante no desempenho.</span><span class="sxs-lookup"><span data-stu-id="985d7-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers is the important bottleneck in performance.</span></span> <span data-ttu-id="985d7-106">Como isso é raro, o modo fibra raramente aumenta o desempenho ou a escalabilidade no sistema típico.</span><span class="sxs-lookup"><span data-stu-id="985d7-106">Because this is rare, fiber mode seldom improves performance or scalability on the typical system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="985d7-107">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="985d7-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="985d7-108">A opção lightweightpooling deve ser habilitada apenas depois de testes extensivos, depois de todas as outras alternativas de ajuste de desempenho serem avaliadas e quando a alternância de contexto for um problema conhecido no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="985d7-108">The lightweightpooling option should only be enabled after thorough testing, after all other performance tuning opportunities are evaluated, and when context switching is a known issue in your environment.</span></span>  
  
 <span data-ttu-id="985d7-109">Recomendamos que você não use o agendamento do modo fibra para a operação de rotina porque pode diminuir o desempenho ao inibir os benefícios comuns da alternância de contexto e porque alguns componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usam o TLS (Armazenamento de Thread Local) ou objetos de propriedade de thread, como mutexes (um tipo de objeto kernel de Win32), talvez não funcionem corretamente nesse modo.</span><span class="sxs-lookup"><span data-stu-id="985d7-109">We recommend that you do not use fiber mode scheduling for routine operation because it can decrease performance by preventing the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a kind of Win32 kernel object), cannot function correctly in fiber mode</span></span>  
  
 <span data-ttu-id="985d7-110">Para remover o lightweight pooling, execute a seguinte instrução e reinicie o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="985d7-110">To remove lightweight pooling, execute the following statement, and then restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
sp_configure 'lightweightpooling', 0;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="985d7-111">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="985d7-111">For More Information</span></span>  
 [<span data-ttu-id="985d7-112">Opção lightweight pooling de configuração de Servidor</span><span class="sxs-lookup"><span data-stu-id="985d7-112">lightweight pooling Server Configuration Option</span></span>](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="985d7-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="985d7-113">See Also</span></span>  
 [<span data-ttu-id="985d7-114">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="985d7-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
