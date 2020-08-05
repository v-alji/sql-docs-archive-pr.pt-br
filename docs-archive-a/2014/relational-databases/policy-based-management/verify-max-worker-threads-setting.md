---
title: Verificar a configuração máxima de threads de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 2d94adfd-3ba1-493a-b29a-b436f9d583df
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dbffb87f58d2beb633f43ff18680222ea62cf5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571988"
---
# <a name="verify-max-worker-threads-setting"></a><span data-ttu-id="4a8d1-102">Verificar a configuração máxima de threads de trabalho</span><span class="sxs-lookup"><span data-stu-id="4a8d1-102">Verify Max Worker Threads Setting</span></span>
  <span data-ttu-id="4a8d1-103">Esta regra verifica a opção do servidor de máximo de threads de trabalho para configurações potencialmente incorretas.</span><span class="sxs-lookup"><span data-stu-id="4a8d1-103">This rule checks the max worker threads server option for potentially incorrect settings.</span></span> <span data-ttu-id="4a8d1-104">A configuração da opção de máximo de threads de trabalho com um valor pequeno pode impedir que threads suficientes atendam às solicitações de entrada do cliente de maneira oportuna e, assim, causar uma "escassez de threads".</span><span class="sxs-lookup"><span data-stu-id="4a8d1-104">Setting the max worker threads option to a small value may prevent enough threads from servicing incoming client requests in a timely manner and could lead to "thread starvation".</span></span> <span data-ttu-id="4a8d1-105">Entretanto, a configuração da opção com um valor grande pode desperdiçar espaço de endereço, porque cada thread ativo consome 512 KB de servidores de 32 bits e até 4 MB de servidores de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4a8d1-105">However, setting the option to a large value can waste address space, because each active thread consumes 512 KB on 32-bit servers and up to 4 MB on 64-bit servers.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="4a8d1-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="4a8d1-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="4a8d1-107">Defina a opção max worker threads como 0.</span><span class="sxs-lookup"><span data-stu-id="4a8d1-107">Set the max worker threads option to 0.</span></span> <span data-ttu-id="4a8d1-108">Isso permite que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] determine automaticamente o número correto de threads de trabalho ativos com base nas solicitações do usuário.</span><span class="sxs-lookup"><span data-stu-id="4a8d1-108">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically determine the correct number of active worker threads based on user requests.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="4a8d1-109">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="4a8d1-109">For More Information</span></span>  
 [<span data-ttu-id="4a8d1-110">Configurar a opção max worker threads de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="4a8d1-110">Configure the max worker threads Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a8d1-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a8d1-111">See Also</span></span>  
 [<span data-ttu-id="4a8d1-112">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="4a8d1-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
