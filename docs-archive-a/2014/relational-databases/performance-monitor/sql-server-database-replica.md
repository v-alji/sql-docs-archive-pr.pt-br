---
title: SQL Server, Réplica de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- SQLServer:Database Replica
- performance counters [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], performance counters
ms.assetid: a5f6bdce-2b13-4924-aaeb-b50b57d624d8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c8830ae30ad3514e107b718f9a02fef873e20295
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576297"
---
# <a name="sql-server-database-replica"></a><span data-ttu-id="5e5ca-102">SQL Server, Réplica de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="5e5ca-102">SQL Server, Database Replica</span></span>
  <span data-ttu-id="5e5ca-103">O objeto de desempenho **SQLServer:Database Replica** contém contadores de desempenho que relatam informações sobre os bancos de dados secundários na réplica secundária de um grupo de disponibilidade AlwaysOn no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e5ca-103">The **SQLServer:Database Replica** performance object contains performance counters that report information about the secondary databases of an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5e5ca-104">Esse objeto só é válido em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda uma réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-104">This object is valid only on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts a secondary replica.</span></span>  
  
|<span data-ttu-id="5e5ca-105">Nome do contador</span><span class="sxs-lookup"><span data-stu-id="5e5ca-105">Counter Name</span></span>|<span data-ttu-id="5e5ca-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e5ca-106">Description</span></span>|<span data-ttu-id="5e5ca-107">Exibir em...</span><span class="sxs-lookup"><span data-stu-id="5e5ca-107">View on...</span></span>|  
|------------------|-----------------|--------------|  
|<span data-ttu-id="5e5ca-108">**Bytes de Arquivo Recebidos/s**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-108">**File Bytes Received/sec**</span></span>|<span data-ttu-id="5e5ca-109">Quantidade de dados FILESTREAM recebida pela réplica secundária para o banco de dados secundário no último segundo.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-109">Amount of FILESTREAM data received by the secondary replica for the secondary database in the last second.</span></span>|<span data-ttu-id="5e5ca-110">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-110">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-111">**Bytes de Log Recebidos/s**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-111">**Log Bytes Received/sec**</span></span>|<span data-ttu-id="5e5ca-112">Quantidade registros de log recebida pela réplica secundária para o banco de dados secundário no último segundo.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-112">Amount of log records received by the secondary replica for the database in the last second.</span></span>|<span data-ttu-id="5e5ca-113">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-113">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-114">**Log restante para desfazer**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-114">**Log remaining for undo**</span></span>|<span data-ttu-id="5e5ca-115">A quantidade de log em quilobytes restante para a conclusão da fase desfazer.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-115">The amount of log in kilobytes remaining to complete the undo phase.</span></span>|<span data-ttu-id="5e5ca-116">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-116">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-117">**Fila de Envio de Log**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-117">**Log Send Queue**</span></span>|<span data-ttu-id="5e5ca-118">Quantidade de registros de log nos arquivos de log do banco de dados primário, em quilobytes, que ainda não foram enviados à réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-118">Amount of log records in the log files of the primary database, in kilobytes, that has not yet been sent to the secondary replica.</span></span> <span data-ttu-id="5e5ca-119">Esse valor é enviado à réplica secundária da réplica primária.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-119">This value is sent to the secondary replica from the primary replica.</span></span> <span data-ttu-id="5e5ca-120">O tamanho da fila não inclui arquivos FILESTREAM enviados a um secundário.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-120">Queue size does not include FILESTREAM files that are sent to a secondary.</span></span>|<span data-ttu-id="5e5ca-121">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-121">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-122">**Transação de Gravação Espelhada/s**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-122">**Mirrored Write Transaction/sec**</span></span>|<span data-ttu-id="5e5ca-123">Número de transações que foram gravadas no banco de dados primário e depois aguardaram para confirmar até que o log fosse enviado para o banco de dados secundário, no último segundo.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-123">Number of transactions that were written to the primary database and then waited to commit until the log was sent to the secondary database, in the last second.</span></span>|<span data-ttu-id="5e5ca-124">Réplica primária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-124">Primary replica</span></span>|  
|<span data-ttu-id="5e5ca-125">**Fila de Recuperação**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-125">**Recovery Queue**</span></span>|<span data-ttu-id="5e5ca-126">Quantidade de registros de log nos arquivos de log da réplica secundária que ainda não foram refeitos.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-126">Amount of log records in the log files of the secondary replica that has not yet been redone.</span></span>|<span data-ttu-id="5e5ca-127">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-127">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-128">**Ações de refazer bloqueadas/s**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-128">**Redo blocked/sec**</span></span>|<span data-ttu-id="5e5ca-129">Número de vezes que o thread de restauração é bloqueado nos bloqueios mantidos por leitores do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-129">Number of times the redo thread is blocked on locks held by readers of the database.</span></span>|<span data-ttu-id="5e5ca-130">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-130">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-131">**Bytes de Restauração Restantes**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-131">**Redo Bytes Remaining**</span></span>|<span data-ttu-id="5e5ca-132">A quantidade de log em quilobytes a ser refeita para concluir a fase de reversão.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-132">The amount of log in kilobytes remaining to be redone to finish the reverting phase.</span></span>|<span data-ttu-id="5e5ca-133">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-133">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-134">**Bytes Refeitos/s**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-134">**Redone Bytes/sec**</span></span>|<span data-ttu-id="5e5ca-135">Quantidade de registros de log refeitos no banco de dados secundário no último segundo.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-135">Amount of log records redone on the secondary database in the last second.</span></span>|<span data-ttu-id="5e5ca-136">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-136">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-137">**Total de Log a ser desfeito**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-137">**Total Log requiring undo**</span></span>|<span data-ttu-id="5e5ca-138">Total de quilobytes de log que deve ser desfeito.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-138">Total kilobytes of log that must be undone.</span></span>|<span data-ttu-id="5e5ca-139">Réplica secundária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-139">Secondary replica</span></span>|  
|<span data-ttu-id="5e5ca-140">**Atraso na Transação**</span><span class="sxs-lookup"><span data-stu-id="5e5ca-140">**Transaction Delay**</span></span>|<span data-ttu-id="5e5ca-141">Atraso na espera por reconhecimento de confirmação não terminado, em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="5e5ca-141">Delay in waiting for unterminated commit acknowledgement, in milliseconds.</span></span>|<span data-ttu-id="5e5ca-142">Réplica primária</span><span class="sxs-lookup"><span data-stu-id="5e5ca-142">Primary replica</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e5ca-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5e5ca-143">See Also</span></span>  
 <span data-ttu-id="5e5ca-144">[Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="5e5ca-144">[Monitor Resource Usage &#40;System Monitor&#41;](monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="5e5ca-145">[SQL Server, Réplica de Disponibilidade](sql-server-availability-replica.md) </span><span class="sxs-lookup"><span data-stu-id="5e5ca-145">[SQL Server, Availability Replica](sql-server-availability-replica.md) </span></span>  
 <span data-ttu-id="5e5ca-146">[SQL Server, objeto Databases](sql-server-databases-object.md) </span><span class="sxs-lookup"><span data-stu-id="5e5ca-146">[SQL Server, Databases Object](sql-server-databases-object.md) </span></span>  
 [<span data-ttu-id="5e5ca-147">Grupos de Disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5e5ca-147">AlwaysOn Availability Groups (SQL Server)</span></span>](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  