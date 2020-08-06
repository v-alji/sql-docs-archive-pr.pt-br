---
title: SQL Server, objeto Estatísticas TO do Agente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Broker Transmission Object object
- 'SQL Server: Broker Transmission Object'
ms.assetid: b5bc5dde-e540-4848-8aa3-5735c51df2fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 93d9c24a175dedfee171eccfccb34673501660ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581763"
---
# <a name="sql-server-broker-to-statistics-object"></a><span data-ttu-id="e0975-102">SQL Server, objeto Broker TO Statistics</span><span class="sxs-lookup"><span data-stu-id="e0975-102">SQL Server, Broker TO Statistics Object</span></span>
  <span data-ttu-id="e0975-103">O objeto de desempenho SQLServer:Broker TO Statistics informa quantas vezes os diálogos do [!INCLUDE[ssSB](../../includes/sssb-md.md)] requerem objetos de transmissão e com que frequência os objetos de transmissão são gravados no **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="e0975-103">The SQLServer:Broker TO Statistics performance object reports information about how many times [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialogs request transmission objects, and how often transmission objects are written to **tempdb**.</span></span>  
  
 <span data-ttu-id="e0975-104">Objetos de transmissão registram o estado de transmissões de mensagem para um diálogo do [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0975-104">Transmission objects record the state of message transmissions for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialog.</span></span> <span data-ttu-id="e0975-105">Eles são armazenados na memória.</span><span class="sxs-lookup"><span data-stu-id="e0975-105">They are stored in memory.</span></span> <span data-ttu-id="e0975-106">Para liberar a memória, o [!INCLUDE[ssSB](../../includes/sssb-md.md)] grava lotes de objetos de transmissão inativos periodicamente em tabelas de trabalho no **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="e0975-106">To free memory, [!INCLUDE[ssSB](../../includes/sssb-md.md)] periodically writes batches of inactive transmission objects to work tables in **tempdb**.</span></span>  
  
 <span data-ttu-id="e0975-107">A tabela a seguir lista os contadores contidos nesse objeto.</span><span class="sxs-lookup"><span data-stu-id="e0975-107">The following table lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="e0975-108">Contadores do SQL Server Broker TO Statistics</span><span class="sxs-lookup"><span data-stu-id="e0975-108">SQL Server Broker TO Statistics counters</span></span>|<span data-ttu-id="e0975-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0975-109">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<span data-ttu-id="e0975-110">**Méd. de gravações em lotes**</span><span class="sxs-lookup"><span data-stu-id="e0975-110">**Avg. Length of Batched Writes**</span></span>|<span data-ttu-id="e0975-111">O número médio de objetos de transmissão salvo em um lote.</span><span class="sxs-lookup"><span data-stu-id="e0975-111">The average number of transmission objects saved in a batch.</span></span>|  
|<span data-ttu-id="e0975-112">**Méd. de tempo de gravação em lote (ms)**</span><span class="sxs-lookup"><span data-stu-id="e0975-112">**Avg. Time To Write Batch (ms)**</span></span>|<span data-ttu-id="e0975-113">O número médio de milissegundos exigido para salvar um lote de objetos de transmissão.</span><span class="sxs-lookup"><span data-stu-id="e0975-113">The average number of milliseconds required to save a batch of transmission objects.</span></span>|  
|<span data-ttu-id="e0975-114">**Méd. de tempo entre lotes (ms)**</span><span class="sxs-lookup"><span data-stu-id="e0975-114">**Avg. Time Between Batches (ms)**</span></span>|<span data-ttu-id="e0975-115">O número médio de milissegundos entre gravações de lotes de objetos de transmissão.</span><span class="sxs-lookup"><span data-stu-id="e0975-115">The average number of milliseconds between writes of transmission object batches.</span></span>|  
|<span data-ttu-id="e0975-116">**Obtenções de Objeto de Transmissão/s**</span><span class="sxs-lookup"><span data-stu-id="e0975-116">**Tran Object Gets/sec**</span></span>|<span data-ttu-id="e0975-117">O número de vezes por segundo que os diálogos solicitaram objetos de transmissão.</span><span class="sxs-lookup"><span data-stu-id="e0975-117">The number of times per second that dialogs requested transmission objects.</span></span>|  
|<span data-ttu-id="e0975-118">**Objetos de Transmissão Marcados como Sujos/s**</span><span class="sxs-lookup"><span data-stu-id="e0975-118">**Tran Objects Marked Dirty/sec**</span></span>|<span data-ttu-id="e0975-119">O número de vezes por segundo que objetos de transmissão foram marcados como sujos.</span><span class="sxs-lookup"><span data-stu-id="e0975-119">The number of times per second that transmission objects were marked as dirty.</span></span> <span data-ttu-id="e0975-120">Os objetos de transmissão são marcados como sujos pela primeira modificação que faz com que a cópia na memória se diferencie da cópia armazenada no **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="e0975-120">Transmission objects are marked as dirty by the first modification that causes the in-memory copy to differ from the copy stored in **tempdb**.</span></span> <span data-ttu-id="e0975-121">Objetos de transmissão são modificados quando o [!INCLUDE[ssSB](../../includes/sssb-md.md)] precisa registrar uma alteração no estado das transmissões das mensagens para o diálogo.</span><span class="sxs-lookup"><span data-stu-id="e0975-121">Transmission objects are modified when [!INCLUDE[ssSB](../../includes/sssb-md.md)] has to record a change in the state of message transmissions for the dialog.</span></span>|  
|<span data-ttu-id="e0975-122">**Gravações de Objetos de Transmissão/s**</span><span class="sxs-lookup"><span data-stu-id="e0975-122">**Tran Object Writes/sec**</span></span>|<span data-ttu-id="e0975-123">O número de vezes por segundo que um lote de objetos de transmissão foi gravado nas tabelas de trabalho do **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="e0975-123">The number of times per second that a batch of transmission objects were written to **tempdb** work tables.</span></span> <span data-ttu-id="e0975-124">Gravações em grande número podem indicar que a memória do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está sendo pressionada.</span><span class="sxs-lookup"><span data-stu-id="e0975-124">Large numbers of writes could indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory is being stressed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0975-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e0975-125">See Also</span></span>  
 <span data-ttu-id="e0975-126">[SQL Server, Objeto Métodos de Acesso](sql-server-access-methods-object.md) </span><span class="sxs-lookup"><span data-stu-id="e0975-126">[SQL Server, Access Methods Object](sql-server-access-methods-object.md) </span></span>  
 <span data-ttu-id="e0975-127">[SQL Server, objeto Memory Manager](sql-server-memory-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="e0975-127">[SQL Server, Memory Manager Object](sql-server-memory-manager-object.md) </span></span>  
 [<span data-ttu-id="e0975-128">Monitorar o uso de recursos &#40;Monitor do Sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="e0975-128">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
