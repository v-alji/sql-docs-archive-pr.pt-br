---
title: Monitorar o uso de memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- tuning databases [SQL Server], memory
- monitoring server performance [SQL Server], memory usage
- isolating memory [SQL Server]
- paging rate [SQL Server]
- memory [SQL Server], monitoring usage
- monitoring [SQL Server], memory usage
- low-memory conditions
- database monitoring [SQL Server], memory usage
- available memory [SQL Server]
- page faults [SQL Server]
- monitoring performance [SQL Server], memory usage
- server performance [SQL Server], memory
ms.assetid: 1aee3933-a11c-4b87-91b7-32f5ea38c87f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1986d9576f9b067cad18f27d4febbf097ed52703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684667"
---
# <a name="monitor-memory-usage"></a><span data-ttu-id="6c4f8-102">Monitorar o uso da memória</span><span class="sxs-lookup"><span data-stu-id="6c4f8-102">Monitor Memory Usage</span></span>
  <span data-ttu-id="6c4f8-103">Monitore uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodicamente para confirmar que o uso de memória está dentro de intervalos normais.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-103">Monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to confirm that memory usage is within typical ranges.</span></span>  
  
 <span data-ttu-id="6c4f8-104">Para monitorar uma condição da memória baixa, use os seguintes contadores de objetos:</span><span class="sxs-lookup"><span data-stu-id="6c4f8-104">To monitor for a low-memory condition, use the following object counters:</span></span>  
  
-   <span data-ttu-id="6c4f8-105">**Memória: Bytes Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="6c4f8-105">**Memory: Available Bytes**</span></span>  
  
-   <span data-ttu-id="6c4f8-106">**Memória: Páginas/segundo**</span><span class="sxs-lookup"><span data-stu-id="6c4f8-106">**Memory: Pages/sec**</span></span>  
  
 <span data-ttu-id="6c4f8-107">O contador **Bytes disponíveis** indica quantos bytes de memória estão atualmente disponíveis para uso dos processos.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-107">The **Available Bytes** counter indicates how many bytes of memory are currently available for use by processes.</span></span> <span data-ttu-id="6c4f8-108">O contador **Páginas/s** indica o número de páginas que foram recuperadas do disco devido a falhas de página física ou gravadas no disco para liberar espaço no conjunto de trabalho devido a falhas de página.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-108">The **Pages/sec** counter indicates the number of pages that either were retrieved from disk due to hard page faults or written to disk to free space in the working set due to page faults.</span></span>  
  
 <span data-ttu-id="6c4f8-109">Baixos valores no contador **Bytes disponíveis** podem indicar a existência de uma escassez global de memória no computador ou que um aplicativo não está liberando a memória.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-109">Low values for the **Available Bytes** counter can indicate that there is an overall shortage of memory on the computer or that an application is not releasing memory.</span></span> <span data-ttu-id="6c4f8-110">Uma taxa alta no contador **Páginas/s** pode indicar paginação excessiva.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-110">A high rate for the **Pages/sec** counter could indicate excessive paging.</span></span> <span data-ttu-id="6c4f8-111">Monitore o contador **Memória: Falhas de página/segundo** para ter certeza de que a atividade no disco não é provocada por paginação.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-111">Monitor the **Memory: Page Faults/sec** counter to make sure that the disk activity is not caused by paging.</span></span>  
  
 <span data-ttu-id="6c4f8-112">Uma taxa baixa de paginação (e, logo, de falhas de página) é normal, mesmo que o computador tenha muita memória disponível.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-112">A low rate of paging (and hence page faults) is typical, even if the computer has plenty of available memory.</span></span> <span data-ttu-id="6c4f8-113">O Gerenciador de Memória Virtual (VMM) do Microsoft Windows conta as páginas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e de outros processos, organizando os tamanhos de conjunto de trabalho desses processos.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-113">The Microsoft Windows Virtual Memory Manager (VMM) takes pages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and other processes as it trims the working-set sizes of those processes.</span></span> <span data-ttu-id="6c4f8-114">Essa atividade do VMM tende a causar falhas de página.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-114">This VMM activity tends to cause page faults.</span></span> <span data-ttu-id="6c4f8-115">Para determinar se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou outro processo é a causa da paginação excessiva, monitore o contador **Processo: Falhas de página/segundo** para a instância de processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c4f8-115">To determine whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or another process is the cause of excessive paging, monitor the **Process: Page Faults/sec** counter for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process instance.</span></span>  
  
 <span data-ttu-id="6c4f8-116">Para obter mais informações sobre como solucionar a paginação excessiva, consulte a documentação do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-116">For more information about resolving excessive paging, see the Windows operating system documentation.</span></span>  
  
## <a name="isolating-memory-used-by-sql-server"></a><span data-ttu-id="6c4f8-117">Isolando a memória usada pelo SQL Server</span><span class="sxs-lookup"><span data-stu-id="6c4f8-117">Isolating Memory Used by SQL Server</span></span>  
 <span data-ttu-id="6c4f8-118">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] altera seus requisitos de memória dinamicamente, com base nos recursos de sistema disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-118">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] changes its memory requirements dynamically, on the basis of available system resources.</span></span> <span data-ttu-id="6c4f8-119">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precisar de mais memória, ele consultará o sistema operacional para determinar se há memória física livre disponível e a usará.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-119">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] needs more memory, it queries the operating system to determine whether free physical memory is available and uses the available memory.</span></span> <span data-ttu-id="6c4f8-120">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não precisar da memória alocada para ele atualmente, ele a liberará para o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-120">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not need the memory currently allocated to it, it releases the memory to the operating system.</span></span> <span data-ttu-id="6c4f8-121">Porém, é possível substituir a opção de usar a memória dinamicamente, por meio das opções de configuração de servidor **minservermemory**e **maxservermemory** .</span><span class="sxs-lookup"><span data-stu-id="6c4f8-121">However, you can override the option to dynamically use memory by using the **minservermemory**, and **maxservermemory** server configuration options.</span></span> <span data-ttu-id="6c4f8-122">Para obter mais informações, consulte [Opções de memória do servidor](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="6c4f8-122">For more information, see [Server Memory Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md).</span></span>  
  
 <span data-ttu-id="6c4f8-123">Para monitorar a quantidade de memória utilizada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , examine os seguintes contadores de desempenho:</span><span class="sxs-lookup"><span data-stu-id="6c4f8-123">To monitor the amount of memory that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses, examine the following performance counters:</span></span>  
  
-   <span data-ttu-id="6c4f8-124">**Processo: Conjunto de trabalho**</span><span class="sxs-lookup"><span data-stu-id="6c4f8-124">**Process: Working Set**</span></span>  
  
-   <span data-ttu-id="6c4f8-125">**SQL Server: Gerenciador de buffer: Índice de Ocorrências no Cache do Buffer**</span><span class="sxs-lookup"><span data-stu-id="6c4f8-125">**SQL Server: Buffer Manager: Buffer Cache Hit Ratio**</span></span>  
  
-   <span data-ttu-id="6c4f8-126">**SQL Server: Gerenciador de buffer: Páginas do Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="6c4f8-126">**SQL Server: Buffer Manager: Database Pages**</span></span>  
  
-   <span data-ttu-id="6c4f8-127">**SQL Server: Gerenciador de memória: Memória Total do Servidor (KB)**</span><span class="sxs-lookup"><span data-stu-id="6c4f8-127">**SQL Server: Memory Manager: Total Server Memory (KB)**</span></span>  
  
 <span data-ttu-id="6c4f8-128">O contador **WorkingSet** mostra a quantidade de memória utilizada por um processo.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-128">The **WorkingSet** counter shows the amount of memory that is used by a process.</span></span> <span data-ttu-id="6c4f8-129">Se esse número estiver consistentemente abaixo da quantidade de memória definida pelas opções de servidor **min server memory** e **max server memory** , o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está configurado para usar memória demais.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-129">If this number is consistently below the amount of memory that is set by the **min server memory** and **max server memory** server options, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use too much memory.</span></span>  
  
 <span data-ttu-id="6c4f8-130">O contador **Taxa de acertos do cache do buffer** é específico ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-130">The **Buffer Cache Hit Ratio** counter is specific to an application.</span></span> <span data-ttu-id="6c4f8-131">Porém, uma taxa de 90 por cento ou mais é desejável.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-131">However, a rate of 90 percent or higher is desirable.</span></span> <span data-ttu-id="6c4f8-132">Adicione memória até que o valor seja consistentemente maior que 90%.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-132">Add more memory until the value is consistently greater than 90 percent.</span></span> <span data-ttu-id="6c4f8-133">Um valor maior que 90% indica que mais de 90% de todas as solicitações de dados foram satisfeitas pelo cache de dados.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-133">A value greater than 90 percent indicates that more than 90 percent of all requests for data were satisfied from the data cache.</span></span>  
  
 <span data-ttu-id="6c4f8-134">Se o contador **TotalServerMemory (KB)** estiver consistentemente alto, em comparação com a quantidade de memória física disponível no computador, isso pode indicar a necessidade de mais memória.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-134">If the **TotalServerMemory (KB)** counter is consistently high compared to the amount of physical memory in the computer, it may indicate that more memory is required.</span></span>  
  
## <a name="determining-current-memory-allocation"></a><span data-ttu-id="6c4f8-135">Determinando a alocação de memória atual</span><span class="sxs-lookup"><span data-stu-id="6c4f8-135">Determining Current Memory Allocation</span></span>  
 <span data-ttu-id="6c4f8-136">A instrução a seguir retorna informações sobre a memória alocada atualmente.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-136">The following query returns information about currently allocated memory.</span></span>  
  
```  
SELECT  
(physical_memory_in_use_kb/1024) AS Memory_usedby_Sqlserver_MB,  
(locked_page_allocations_kb/1024) AS Locked_pages_used_Sqlserver_MB,  
(total_virtual_address_space_kb/1024) AS Total_VAS_in_MB,  
process_physical_memory_low,  
process_virtual_memory_low  
FROM sys.dm_os_process_memory;  
```  
  
  
