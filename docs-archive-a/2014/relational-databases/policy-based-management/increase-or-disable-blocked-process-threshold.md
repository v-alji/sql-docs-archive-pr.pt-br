---
title: Aumentar ou desabilitar o limite de processo bloqueado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 71db8ef6-341b-4465-99db-5c63e48d4c7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7a90aea3fa8fb4d9c423cea1ec6008b01cde883
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569983"
---
# <a name="increase-or-disable-blocked-process-threshold"></a><span data-ttu-id="c2788-102">Aumentar ou desabilitar o limite de processo bloqueado</span><span class="sxs-lookup"><span data-stu-id="c2788-102">Increase or Disable Blocked Process Threshold</span></span>
  <span data-ttu-id="c2788-103">Estas regras verificam se a opção de limite de processo bloqueado está definida como 0 (desabilitada) ou com um valor maior ou igual a 5 (segundos).</span><span class="sxs-lookup"><span data-stu-id="c2788-103">This rules checks that the blocked process threshold option is set to 0 (disabled) or set to a value higher than or equal to 5 (seconds).</span></span> <span data-ttu-id="c2788-104">Definir a opção de limite de processo bloqueado com um valor de 1 até 4 pode fazer o monitor de deadlock ser executado constantemente.</span><span class="sxs-lookup"><span data-stu-id="c2788-104">Setting the blocked process threshold option to a value from 1 to 4 can cause the deadlock monitor to run constantly.</span></span> <span data-ttu-id="c2788-105">Valores de 1 a 4 devem ser usados apenas para solução de problemas e nunca a longo prazo ou em um ambiente de produção sem a assistência do Suporte e Atendimento ao Cliente [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2788-105">Values 1 to 4 should only be used for troubleshooting, and never long term or in a production environment without the assistance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c2788-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="c2788-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c2788-107">Para resolver este problema, defina a opção de limite de processo bloqueado com um valor de 5 (segundos) ou mais ou desabilite o limite de processo bloqueado definindo o valor como 0.</span><span class="sxs-lookup"><span data-stu-id="c2788-107">To resolve this problem, set the blocked process threshold option to a value of 5 (seconds) or higher, or disable blocked process threshold by setting the value to 0.</span></span> <span data-ttu-id="c2788-108">Para definir o limite de processo bloqueado com um valor de `5` segundos, execute a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="c2788-108">To set the blocked process threshold to a value of `5` seconds, execute the following statement:</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 5 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="c2788-109">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="c2788-109">For More Information</span></span>  
 [<span data-ttu-id="c2788-110">Opção blocked process threshold de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="c2788-110">blocked process threshold Server Configuration Option</span></span>](../../database-engine/configure-windows/blocked-process-threshold-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="c2788-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2788-111">See Also</span></span>  
 [<span data-ttu-id="c2788-112">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="c2788-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
