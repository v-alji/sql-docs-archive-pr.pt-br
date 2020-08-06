---
title: Corrigir sobreposição de máscara de afinidade e máscara de saída de entrada de afinidade | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1a0da6df-57ff-4f3f-aae9-2fbc4897508c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486b4441a20db7630082344fb1f277bba053f3ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686257"
---
# <a name="correct-affinity-mask-and-affinity-input-output-mask-overlap"></a><span data-ttu-id="6ef19-102">Corrigir sobreposição de máscara de afinidade e máscara de saída de entrada de afinidade</span><span class="sxs-lookup"><span data-stu-id="6ef19-102">Correct Affinity Mask and Affinity Input Output Mask Overlap</span></span>
  <span data-ttu-id="6ef19-103">Esta regra verifica se a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possui um ou mais processadores atribuídos para serem usados com as opções de máscara de afinidade e máscara de E/S de afinidade.</span><span class="sxs-lookup"><span data-stu-id="6ef19-103">This rule checks whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one or more processors that are assigned to be used with both the affinity mask and the affinity I/O mask options.</span></span> <span data-ttu-id="6ef19-104">Em um computador com mais de um processador, as opções de máscara de afinidade e máscara de E/S de afinidade são empregadas para designar quais CPUs o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]utiliza.</span><span class="sxs-lookup"><span data-stu-id="6ef19-104">On a computer that has more than one processor, the affinity mask and the affinity I/O mask options are used to designate which CPUs are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6ef19-105">Ao habilitar uma CPU com a máscara de afinidade e a máscara de E/S de afinidade você poderá reduzir o desempenho forçando o uso excessivo do processador.</span><span class="sxs-lookup"><span data-stu-id="6ef19-105">Enabling a CPU with both the affinity mask and the affinity I/O mask can slow performance by forcing the processor to be overused.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="6ef19-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="6ef19-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="6ef19-107">Ao especificar a opção de máscara de afinidade ou de máscara de E/S de afinidade, você deve especificar as duas, mas cada CPU só pode ser habilitada uma vez.</span><span class="sxs-lookup"><span data-stu-id="6ef19-107">When you specify either the affinity mask or the affinity I/O mask options, you should specify both, but only enable each CPU no more than once.</span></span>  
  
 <span data-ttu-id="6ef19-108">Não habilite a mesma CPU na opção de máscara de afinidade e na opção de máscara de E/S de afinidade.</span><span class="sxs-lookup"><span data-stu-id="6ef19-108">Do not enable the same CPU in both the affinity mask option and the affinity I/O mask option.</span></span> <span data-ttu-id="6ef19-109">Os bits que correspondem a cada CPU devem estar em um dos seguintes estados:</span><span class="sxs-lookup"><span data-stu-id="6ef19-109">The bits that correspond to each CPU should be in one of the following states:</span></span>  
  
-   <span data-ttu-id="6ef19-110">0 na opção de máscara de afinidade e na opção de máscara de afinidade de E/S</span><span class="sxs-lookup"><span data-stu-id="6ef19-110">0 in both the affinity mask option and the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="6ef19-111">0 na opção de máscara de afinidade e 1 na opção de máscara de E/S de afinidade</span><span class="sxs-lookup"><span data-stu-id="6ef19-111">0 in the affinity mask option and 1 in the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="6ef19-112">1 na opção de máscara de afinidade e 0 na opção de máscara de E/S de afinidade</span><span class="sxs-lookup"><span data-stu-id="6ef19-112">1 in the affinity mask option and 0 in the affinity I/O mask option</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="6ef19-113">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="6ef19-113">For More Information</span></span>  
 [<span data-ttu-id="6ef19-114">Opção affinity mask de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="6ef19-114">affinity mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="6ef19-115">Opção de configuração do servidor de máscara de Entrada-Saída de afinidade</span><span class="sxs-lookup"><span data-stu-id="6ef19-115">affinity Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="6ef19-116">Opção affinity64 mask de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="6ef19-116">affinity64 mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="6ef19-117">Opção de configuração do servidor affinity64 I/O mask</span><span class="sxs-lookup"><span data-stu-id="6ef19-117">affinity64 Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-input-output-mask-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ef19-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ef19-118">See Also</span></span>  
 [<span data-ttu-id="6ef19-119">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="6ef19-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
