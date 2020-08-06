---
title: Usando o OLTP na memória em um ambiente de VM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 27ec7eb3-3a24-41db-aa65-2f206514c6f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83cf785fbcd2df9449d61e328e3bf8e374a6656d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680619"
---
# <a name="using-in-memory-oltp-in-a-vm-environment"></a><span data-ttu-id="1989b-102">Usando OLTP na Memória em um Ambiente de VM</span><span class="sxs-lookup"><span data-stu-id="1989b-102">Using In-Memory OLTP in a VM Environment</span></span>
  <span data-ttu-id="1989b-103">A virtualização do servidor pode ajudá-lo a diminuir os custos operacionais e de capital com a TI, e atingir uma maior eficiência de TI com processos de provisionamento de aplicativo, manutenção, disponibilidade e backup/recuperação aprimorados.</span><span class="sxs-lookup"><span data-stu-id="1989b-103">Server virtualization can help you lower IT capital and operational costs and attain greater IT efficiency with improved application provisioning, maintenance, availability, and backup/recovery processes.</span></span> <span data-ttu-id="1989b-104">Com os avanços tecnológicos recentes, as cargas de trabalho de banco de dados complexas podem mais ser prontamente consolidadas usando a virtualização.</span><span class="sxs-lookup"><span data-stu-id="1989b-104">With recent technological advances, complex database workloads can be more readily consolidated using virtualization.</span></span> <span data-ttu-id="1989b-105">Este tópico sobre as práticas recomendadas para usar o [!INCLUDE[hek_1](../includes/hek-1-md.md)] em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="1989b-105">This topic covers best practices for using [!INCLUDE[hek_1](../includes/hek-1-md.md)] in a virtualized environment.</span></span>  
  
##  <a name="memory-pre-allocation"></a><a name="bkmk_memoryPreAllocation"></a><span data-ttu-id="1989b-106">Pré-alocação de memória</span><span class="sxs-lookup"><span data-stu-id="1989b-106">Memory pre-allocation</span></span>  
 <span data-ttu-id="1989b-107">Para a memória em um ambiente virtualizado, o melhor desempenho e o suporte aprimorado são considerações essenciais.</span><span class="sxs-lookup"><span data-stu-id="1989b-107">For memory in a virtualized environment, better performance and enhanced support are essential considerations.</span></span> <span data-ttu-id="1989b-108">Você deve ser capaz de alocar memória rapidamente para máquinas virtuais dependendo de seus requisitos (cargas de pico e fora de pico) e garantir que a memória não seja desperdiçada.</span><span class="sxs-lookup"><span data-stu-id="1989b-108">You must be able to both quickly allocate memory to virtual machines depending on their requirements (peak and off-peak loads) and ensure that the memory is not wasted.</span></span> <span data-ttu-id="1989b-109">O recurso de Memória Dinâmica do Hyper-V aumenta a agilidade sobre como a memória é alocada e gerenciada entre as máquinas virtuais executadas em um host.</span><span class="sxs-lookup"><span data-stu-id="1989b-109">The Hyper-V Dynamic Memory feature increases agility in how the memory is allocated and managed between virtual machines running on a host.</span></span>  
  
 <span data-ttu-id="1989b-110">Algumas práticas recomendadas para virtualizar e gerenciar o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] precisam ser alteradas ao virtualizar um banco de dados com tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="1989b-110">Some best practices for virtualizing and managing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] need to be modified when virtualizing a database with memory-optimized tables.</span></span> <span data-ttu-id="1989b-111">Sem tabelas com otimização de memória, duas das práticas recomendadas são:</span><span class="sxs-lookup"><span data-stu-id="1989b-111">Without memory-optimized tables, two of the best practices are:</span></span>  
  
-   <span data-ttu-id="1989b-112">Se você usar MIN_SERVER_MEMORY, será melhor atribuir somente a quantidade de memória necessária para que a memória suficiente permaneça para outros processos (impedindo a paginação).</span><span class="sxs-lookup"><span data-stu-id="1989b-112">If you use MIN_SERVER_MEMORY, it is better to assign only the amount of memory that is required so sufficient memory remains for other processes (thereby avoiding paging).</span></span>  
  
-   <span data-ttu-id="1989b-113">Não defina o valor de pré-alocação de memória muito alto.</span><span class="sxs-lookup"><span data-stu-id="1989b-113">Do not set the memory pre-allocation value too high.</span></span> <span data-ttu-id="1989b-114">Caso contrário, outros processos podem não obter memória suficiente no momento em que a exigirem e isso pode levar à paginação de memória.</span><span class="sxs-lookup"><span data-stu-id="1989b-114">Otherwise, other processes may not get sufficient memory at the time when they require it, and this can result in memory paging.</span></span>  
  
 <span data-ttu-id="1989b-115">Se você seguir as práticas acima para um banco de dados com tabelas otimizadas pela memória, uma tentativa de restaurar e recuperar um banco de dados poderá resultar no banco de dados ficando em um estado de “Recuperação Pendente”, mesmo se você tiver memória suficiente para recuperá-lo.</span><span class="sxs-lookup"><span data-stu-id="1989b-115">If you follow the above practices for a database with memory-optimized tables, an attempt to restore and recover a database could result in the database being in a "Recovery Pending" state, even if you have sufficient memory to recover the database.</span></span> <span data-ttu-id="1989b-116">A razão para isso é que, ao iniciar, o [!INCLUDE[hek_2](../includes/hek-2-md.md)] coloca os dados na memória de maneira mais agressiva que a alocação dinâmica de memória aloca a memória para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1989b-116">The reason for this is that, when starting up, [!INCLUDE[hek_2](../includes/hek-2-md.md)] brings data into memory more aggressively than dynamic memory allocation allocates memory to the database.</span></span>  
  
 <span data-ttu-id="1989b-117">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="1989b-117">**Resolution**</span></span>  
  
 <span data-ttu-id="1989b-118">Para solucionar isso, pré-aloque memória suficiente para o banco de dados a ser recuperado ou reinicie o banco de dados, não um valor mínimo que depende da memória dinâmica para fornecer a memória adicional quando for necessário.</span><span class="sxs-lookup"><span data-stu-id="1989b-118">To mitigate this, pre-allocate sufficient memory to the database to recover or restart the database, not a minimum value relying on dynamic memory to provide the additional memory when needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1989b-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1989b-119">See Also</span></span>  
 [<span data-ttu-id="1989b-120">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="1989b-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
