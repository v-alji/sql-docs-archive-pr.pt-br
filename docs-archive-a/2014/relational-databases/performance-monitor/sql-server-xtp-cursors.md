---
title: Cursores de XTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 84bf4654-3ef7-4d7f-a269-c8bb4ed4acad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 217a1196717492cb92adb24eaf7c06c8867abc2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682223"
---
# <a name="xtp-cursors"></a><span data-ttu-id="ea92d-102">Cursores de XTP</span><span class="sxs-lookup"><span data-stu-id="ea92d-102">XTP Cursors</span></span>
  <span data-ttu-id="ea92d-103">O objeto de desempenho Cursores de XTP contém os contadores relacionados aos cursores do mecanismo de XTP interno.</span><span class="sxs-lookup"><span data-stu-id="ea92d-103">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="ea92d-104">Os cursores são os blocos de construção de baixo nível que o mecanismo de XTP usa para processar consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea92d-104">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="ea92d-105">Como tal, você normalmente não tem controle direto sobre eles.</span><span class="sxs-lookup"><span data-stu-id="ea92d-105">As such, you do not typically have direct control over them.</span></span>  
  
 <span data-ttu-id="ea92d-106">Esta tabela descreve os contadores de **cursores de XTP** .</span><span class="sxs-lookup"><span data-stu-id="ea92d-106">This table describes the **XTP Cursors** counters.</span></span>  
  
|<span data-ttu-id="ea92d-107">Contador</span><span class="sxs-lookup"><span data-stu-id="ea92d-107">Counter</span></span>|<span data-ttu-id="ea92d-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="ea92d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea92d-109">**Exclusões de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-109">**Cursor deletes/sec**</span></span>|<span data-ttu-id="ea92d-110">O número de exclusões de cursor (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-110">The number of cursor deletes (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-111">**Inserções de Cursor/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-111">**Cursor inserts/sec**</span></span>|<span data-ttu-id="ea92d-112">O número de inserções de cursor (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-112">The number of cursor inserts (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-113">**Verificações de cursor iniciadas/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-113">**Cursor scans started /sec**</span></span>|<span data-ttu-id="ea92d-114">O número de verificações de cursor iniciadas (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-114">The number of cursor scans started (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-115">**Violações exclusivas de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-115">**Cursor unique violations/sec**</span></span>|<span data-ttu-id="ea92d-116">O número de violações de restrição exclusiva (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-116">The number of unique-constraint violations (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-117">**Atualizações de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-117">**Cursor updates/sec**</span></span>|<span data-ttu-id="ea92d-118">O número de atualizações de cursor (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-118">The number of cursor updates (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-119">**Conflitos de gravação de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-119">**Cursor write   conflicts/sec**</span></span>|<span data-ttu-id="ea92d-120">O número de conflitos de gravação/gravação para a mesma versão de linha (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-120">The number of write-write conflicts to the same row version (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-121">**Tentativas de verificação de canto sujo/s (emitido pelo usuário)**</span><span class="sxs-lookup"><span data-stu-id="ea92d-121">**Dusty corner scan retries/sec (user-issued)**</span></span>|<span data-ttu-id="ea92d-122">O número de novas tentativas de verificação devido a conflitos de gravação durante as varreduras de canto sujo emitidas pela verificação de tabela inteira de um usuário (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-122">The number of scan retries due to write conflicts during dusty corner sweeps issued by a user's full-table scan (on average), per second.</span></span> <span data-ttu-id="ea92d-123">Este é um contador de nível muito baixo, não planejado para uso do cliente.</span><span class="sxs-lookup"><span data-stu-id="ea92d-123">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="ea92d-124">**Linhas expiradas removidas/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-124">**Expired rows removed/sec**</span></span>|<span data-ttu-id="ea92d-125">O número de linhas expiradas removidas por cursores (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-125">The number of expired rows removed by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-126">**Linhas expiradas tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-126">**Expired rows touched/sec**</span></span>|<span data-ttu-id="ea92d-127">O número de linhas expiradas tocadas por cursores (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-127">The number of expired rows touched by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-128">**Linhas retornadas/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-128">**Rows returned/sec**</span></span>|<span data-ttu-id="ea92d-129">O número de linhas retornadas por cursores (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-129">The number of rows returned by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-130">**Linhas tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-130">**Rows touched/sec**</span></span>|<span data-ttu-id="ea92d-131">O número de linhas tocadas por cursores (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-131">The number of rows touched by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="ea92d-132">**Linhas excluídas por tentativa tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="ea92d-132">**Tentatively-deleted rows touched/sec**</span></span>|<span data-ttu-id="ea92d-133">O número de linhas expirando tocadas por cursores (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="ea92d-133">The number of expiring rows touched by cursors (on average), per second.</span></span> <span data-ttu-id="ea92d-134">Uma linha está expirando quando a transação que a excluiu ainda está ativa (ou seja, ainda não foi confirmada nem anulada).</span><span class="sxs-lookup"><span data-stu-id="ea92d-134">A row is expiring if the transaction that deleted it is still active (i.e. has not yet committed or aborted.)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea92d-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea92d-135">See Also</span></span>  
 [<span data-ttu-id="ea92d-136">&#40;de OLTP na memória&#41; contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="ea92d-136">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
