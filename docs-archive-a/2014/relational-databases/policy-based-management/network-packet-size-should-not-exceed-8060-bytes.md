---
title: O tamanho do pacote de rede não deve exceder 8060 Bytes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 86db5da1-afe4-4fbb-8bf8-33cedc7e4361
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 01b500cbe65107767d73bc2901b6d5e028b94ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572004"
---
# <a name="network-packet-size-should-not-exceed-8060-bytes"></a><span data-ttu-id="50982-102">O tamanho do pacote de rede não dever exceder 8060 bytes</span><span class="sxs-lookup"><span data-stu-id="50982-102">Network Packet Size Should Not Exceed 8060 Bytes</span></span>
  <span data-ttu-id="50982-103">Se o valor especificado para sp_configure 'network packet size' ou se o tamanho do pacote de rede de qualquer usuário que fez logon for maior que 8060, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executará operações de alocação de memória diferentes.</span><span class="sxs-lookup"><span data-stu-id="50982-103">If the value specified for sp_configure 'network packet size' or if the network packet size of any logged-in user is more than 8060 bytes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs different memory allocation operations.</span></span> <span data-ttu-id="50982-104">Isso pode causar um aumento no espaço de endereço virtual de processo que não está reservado para o pool de buffers.</span><span class="sxs-lookup"><span data-stu-id="50982-104">This can cause an increase in the process virtual address space that is not reserved for the buffer pool.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="50982-105">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="50982-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="50982-106">O tamanho do pacote de rede não dever exceder 8060 bytes</span><span class="sxs-lookup"><span data-stu-id="50982-106">The network packet size should not exceed 8060 bytes.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="50982-107">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="50982-107">For More Information</span></span>  
 [<span data-ttu-id="50982-108">Artigo 903002 da Base de Dados de Conhecimento Microsoft</span><span class="sxs-lookup"><span data-stu-id="50982-108">Microsoft Knowledge Base article 903002</span></span>](https://go.microsoft.com/fwlink/?linkid=117749)  
  
## <a name="see-also"></a><span data-ttu-id="50982-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50982-109">See Also</span></span>  
 [<span data-ttu-id="50982-110">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="50982-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
