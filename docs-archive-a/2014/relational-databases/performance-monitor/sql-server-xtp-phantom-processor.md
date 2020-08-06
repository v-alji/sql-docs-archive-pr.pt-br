---
title: Processador fantasma de XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 0f691b3d-a8fd-4459-ad21-2cfc8574a8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14158b7097427b6704cf5e747fa998a11217ecd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679900"
---
# <a name="xtp-phantom-processor"></a><span data-ttu-id="dc039-102">Processador Fantasma de XTP</span><span class="sxs-lookup"><span data-stu-id="dc039-102">XTP Phantom Processor</span></span>
  <span data-ttu-id="dc039-103">O objeto de desempenho Processador Fantasma de XTP contém os contadores relacionados ao subsistema de processamento fantasma do mecanismo de XTP.</span><span class="sxs-lookup"><span data-stu-id="dc039-103">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="dc039-104">Esse componente é responsável por detectar as linhas fantasmas nas transações que são executadas no nível de isolamento SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="dc039-104">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>  
  
 <span data-ttu-id="dc039-105">Esta tabela descreve os contadores do **Processador Fantasma de XTP** .</span><span class="sxs-lookup"><span data-stu-id="dc039-105">This table describes the **XTP Phantom Processor** counters.</span></span>  
  
|<span data-ttu-id="dc039-106">Contador</span><span class="sxs-lookup"><span data-stu-id="dc039-106">Counter</span></span>|<span data-ttu-id="dc039-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="dc039-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc039-108">**Tentativas de verificação de canto sujo/s (emitido pelo fantasma)**</span><span class="sxs-lookup"><span data-stu-id="dc039-108">**Dusty corner scan retries/sec (Phantom-issued)**</span></span>|<span data-ttu-id="dc039-109">O número de tentativas de digitalização devido a conflitos de gravação durante as varreduras de canto sujo emitidas pelo processador fantasma (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="dc039-109">The number of scan retries due to write conflicts during dusty corner sweeps issued by the phantom processor (on average), per second.</span></span> <span data-ttu-id="dc039-110">Este é um contador de nível muito baixo, não planejado para uso do cliente.</span><span class="sxs-lookup"><span data-stu-id="dc039-110">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="dc039-111">**Linhas fantasma expiradas removidas/s**</span><span class="sxs-lookup"><span data-stu-id="dc039-111">**Phantom expired rows removed/sec**</span></span>|<span data-ttu-id="dc039-112">O número de linhas expiradas removidas por verificações fantasma (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="dc039-112">The number of expired rows removed by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="dc039-113">**Linhas fantasma expiradas tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="dc039-113">**Phantom expired rows touched/sec**</span></span>|<span data-ttu-id="dc039-114">O número de linhas expiradas tocadas por verificações fantasma (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="dc039-114">The number of expired rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="dc039-115">**Linhas fantasma expirando tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="dc039-115">**Phantom expiring rows touched/sec**</span></span>|<span data-ttu-id="dc039-116">O número de linhas expirando tocadas por verificações fantasma (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="dc039-116">The number of expiring rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="dc039-117">**Linhas fantasma tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="dc039-117">**Phantom rows touched/sec**</span></span>|<span data-ttu-id="dc039-118">O número de linhas tocadas por verificações fantasma (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="dc039-118">The number of rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="dc039-119">**Verificações fantasma iniciadas/s**</span><span class="sxs-lookup"><span data-stu-id="dc039-119">**Phantom scans started/sec**</span></span>|<span data-ttu-id="dc039-120">O número de verificações fantasma iniciadas (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="dc039-120">The number of phantom scans started (on average), per second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc039-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc039-121">See Also</span></span>  
 [<span data-ttu-id="dc039-122">&#40;de OLTP na memória&#41; contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="dc039-122">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
