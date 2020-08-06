---
title: Monitorar o uso da CPU | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], CPU usage
- tuning databases [SQL Server], CPU usage
- processors [SQL Server], monitoring usage
- database performance [SQL Server], CPU usage
- monitoring CPU usage [SQL Server]
- server performance [SQL Server], CPU usage
- database monitoring [SQL Server], CPU usage
- monitoring [SQL Server], CPU usage
- processors [SQL Server]
- CPU [SQL Server], monitoring
- monitoring server performance [SQL Server], CPU usage
ms.assetid: 2a02a3b6-07b2-4ad0-8a24-670414d19812
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f08d49348fd25593f27a87f2b0123f7ce43e35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684670"
---
# <a name="monitor-cpu-usage"></a><span data-ttu-id="9ed34-102">Monitorar o uso da CPU</span><span class="sxs-lookup"><span data-stu-id="9ed34-102">Monitor CPU Usage</span></span>
  <span data-ttu-id="9ed34-103">Monitore uma instância do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodicamente para determinar se as taxas de uso de CPU estão dentro dos intervalos normais.</span><span class="sxs-lookup"><span data-stu-id="9ed34-103">Monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to determine whether CPU usage rates are within normal ranges.</span></span> <span data-ttu-id="9ed34-104">Uma taxa de uso de CPU continuamente alta pode indicar a necessidade de atualizar a CPU ou de adicionar vários processadores.</span><span class="sxs-lookup"><span data-stu-id="9ed34-104">A continually high rate of CPU usage may indicate the need to upgrade the CPU or add multiple processors.</span></span> <span data-ttu-id="9ed34-105">Alternativamente, uma taxa de uso de CPU alta pode indicar um aplicativo mal-ajustado ou malprojetado.</span><span class="sxs-lookup"><span data-stu-id="9ed34-105">Alternatively, a high CPU usage rate may indicate a poorly tuned or designed application.</span></span> <span data-ttu-id="9ed34-106">Otimizar o aplicativo pode baixar a utilização de CPU.</span><span class="sxs-lookup"><span data-stu-id="9ed34-106">Optimizing the application can lower CPU utilization.</span></span>  
  
 <span data-ttu-id="9ed34-107">Um modo eficiente de determinar o uso de CPU é usar o contador **Processador: %tempo de processador** do Monitor do Sistema.</span><span class="sxs-lookup"><span data-stu-id="9ed34-107">An efficient way to determine CPU usage is to use the **Processor:% Processor Time** counter in System Monitor.</span></span> <span data-ttu-id="9ed34-108">Esse contador monitora o tempo gasto pela CPU para executar um thread que não está ocioso.</span><span class="sxs-lookup"><span data-stu-id="9ed34-108">This counter monitors the amount of time the CPU spends executing a thread that is not idle.</span></span> <span data-ttu-id="9ed34-109">Um estado consistente de 80 a 90 por cento pode indicar a necessidade de atualizar a CPU ou de adicionar mais processadores.</span><span class="sxs-lookup"><span data-stu-id="9ed34-109">A consistent state of 80 percent to 90 percent may indicate the need to upgrade your CPU or add more processors.</span></span> <span data-ttu-id="9ed34-110">Para sistemas com vários processadores, monitore uma instância separada desse contador para cada processador.</span><span class="sxs-lookup"><span data-stu-id="9ed34-110">For multiprocessor systems, monitor a separate instance of this counter for each processor.</span></span> <span data-ttu-id="9ed34-111">Esse valor representa a soma do tempo de processador em um processador específico.</span><span class="sxs-lookup"><span data-stu-id="9ed34-111">This value represents the sum of processor time on a specific processor.</span></span> <span data-ttu-id="9ed34-112">Para determinar a média de todos os processadores, use o contador **Sistema: %tempo total de processador** .</span><span class="sxs-lookup"><span data-stu-id="9ed34-112">To determine the average for all processors, use the **System: %Total Processor Time** counter instead.</span></span>  
  
 <span data-ttu-id="9ed34-113">Opcionalmente, você também pode monitorar os seguintes contadores para monitorar o uso de processador:</span><span class="sxs-lookup"><span data-stu-id="9ed34-113">Optionally, you can also monitor the following counters to monitor processor usage:</span></span>  
  
-   <span data-ttu-id="9ed34-114">**Processador: % tempo privilegiado**</span><span class="sxs-lookup"><span data-stu-id="9ed34-114">**Processor: % Privileged Time**</span></span>  
  
     <span data-ttu-id="9ed34-115">Corresponde à porcentagem de tempo que o processador gasta na execução de comandos de kernel do Microsoft Windows, como o processamento de solicitações de E/S do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ed34-115">Corresponds to the percentage of time the processor spends on execution of Microsoft Windows kernel commands, such as processing of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] I/O requests.</span></span> <span data-ttu-id="9ed34-116">Se esse contador estiver consistentemente alto quando os contadores do **Disco Físico** estiverem altos, considere instalar um subsistema de disco mais rápido ou eficiente.</span><span class="sxs-lookup"><span data-stu-id="9ed34-116">If this counter is consistently high when the **Physical Disk** counters are high, consider installing a faster or more efficient disk subsystem.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ed34-117">Controladores de disco e drivers diferentes usam tempos diferentes de processamento de kernel.</span><span class="sxs-lookup"><span data-stu-id="9ed34-117">Different disk controllers and drivers use different amounts of kernel processing time.</span></span> <span data-ttu-id="9ed34-118">Controladores e drivers eficientes usam menos tempo privilegiado, deixando mais tempo de processamento disponível para aplicativos de usuário, o que aumenta o processamento global.</span><span class="sxs-lookup"><span data-stu-id="9ed34-118">Efficient controllers and drivers use less privileged time, leaving more processing time available for user applications, increasing overall throughput.</span></span>  
  
-   <span data-ttu-id="9ed34-119">**Processador: % tempo de usuário**</span><span class="sxs-lookup"><span data-stu-id="9ed34-119">**Processor: %User Time**</span></span>  
  
     <span data-ttu-id="9ed34-120">Corresponde à porcentagem de tempo que o processador gasta na execução de processos de usuário, como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ed34-120">Corresponds to the percentage of time that the processor spends on executing user processes such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9ed34-121">**Sistema: Extensão da Fila do Processador**</span><span class="sxs-lookup"><span data-stu-id="9ed34-121">**System: Processor Queue Length**</span></span>  
  
     <span data-ttu-id="9ed34-122">Corresponde ao número de threads que esperam por tempo de processador.</span><span class="sxs-lookup"><span data-stu-id="9ed34-122">Corresponds to the number of threads waiting for processor time.</span></span> <span data-ttu-id="9ed34-123">Um gargalo de processador acontece quando os threads de um processo exigem mais ciclos de processador do que os disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9ed34-123">A processor bottleneck develops when threads of a process require more processor cycles than are available.</span></span> <span data-ttu-id="9ed34-124">Se muitos processos tentarem utilizar o tempo de processador, pode ser necessário instalar um processador mais rápido.</span><span class="sxs-lookup"><span data-stu-id="9ed34-124">If more than a few processes attempt to utilize the processor's time, you might need to install a faster processor.</span></span> <span data-ttu-id="9ed34-125">Caso seja um sistema com vários processadores, você pode adicionar um processador.</span><span class="sxs-lookup"><span data-stu-id="9ed34-125">Or, if you have a multiprocessor system, you could add a processor.</span></span>  
  
 <span data-ttu-id="9ed34-126">Ao examinar o uso de processador, considere o tipo de trabalho que a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa.</span><span class="sxs-lookup"><span data-stu-id="9ed34-126">When you examine processor usage, consider the type of work that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs.</span></span> <span data-ttu-id="9ed34-127">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] efetua muitos cálculos, como consultas envolvendo agregações ou consultas associadas à memória que não requerem E/S em disco, pode ser usado 100 % do tempo de processador.</span><span class="sxs-lookup"><span data-stu-id="9ed34-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs many calculations, such as queries involving aggregates or memory-bound queries that require no disk I/O, 100 percent of the processor's time can be used.</span></span> <span data-ttu-id="9ed34-128">Se isso influir no desempenho de outros aplicativos, experimente alterar a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9ed34-128">If this causes the performance of other applications to suffer, try changing the workload.</span></span> <span data-ttu-id="9ed34-129">Por exemplo, dedique o computador à execução da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ed34-129">For example, dedicate the computer to running the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9ed34-130">Taxas de uso em torno de 100 %, quando estão sendo processadas muitas solicitações de cliente, podem indicar que os processos estão formando fila para aguardar o tempo de processador e provocando um gargalo.</span><span class="sxs-lookup"><span data-stu-id="9ed34-130">Usage rates around 100 percent, where many client requests are being processed, may indicate that processes are queuing up, waiting for processor time, and causing a bottleneck.</span></span> <span data-ttu-id="9ed34-131">Resolva o problema adicionando processadores mais rápidos.</span><span class="sxs-lookup"><span data-stu-id="9ed34-131">Resolve the problem by adding faster processors.</span></span>  
  
  
