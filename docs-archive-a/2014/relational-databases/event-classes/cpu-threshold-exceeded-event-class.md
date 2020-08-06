---
title: Classe de evento CPU Threshold Exceeded | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- CPU Threshold Exceeded Event Class
ms.assetid: eb106f7d-baa3-4a2b-96b2-f9fe0844057d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07b51e1a6f08f48c601b00d2dcb67bc6d09006f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570056"
---
# <a name="cpu-threshold-exceeded-event-class"></a><span data-ttu-id="c8867-102">Classe de evento CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="c8867-102">CPU Threshold Exceeded Event Class</span></span>
  <span data-ttu-id="c8867-103">A classe de evento CPU Threshold Exceeded indica que o Administrador de Recursos detecta uma consulta que excede o limite da CPU especificado para REQUEST_MAX_CPU_TIME_SEC.</span><span class="sxs-lookup"><span data-stu-id="c8867-103">The CPU Threshold Exceeded event class indicates that Resource Governor detects a query that exceeds the CPU threshold specified for REQUEST_MAX_CPU_TIME_SEC.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8867-104">O intervalo de detecção para esse evento é cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="c8867-104">The detection interval for this event is five seconds.</span></span> <span data-ttu-id="c8867-105">Há garantia de que um evento será gerado se uma consulta exceder o limite especificado em pelo menos cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="c8867-105">It is guaranteed that an event will be generated if a query exceeds the specified limit by at least five seconds.</span></span> <span data-ttu-id="c8867-106">Contudo, se uma consulta exceder o limite especificado em menos de cinco segundos, sua detecção poderá ser perdida, dependendo do controle de tempo da consulta e da hora da última varredura de detecção.</span><span class="sxs-lookup"><span data-stu-id="c8867-106">However, if a query exceeds the specified threshold by less than five seconds, its detection might be missed depending on the timing of the query and the time of last detection sweep.</span></span>  
  
## <a name="cpu-threshold-exceeded-data-columns"></a><span data-ttu-id="c8867-107">Colunas de dados de CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="c8867-107">CPU Threshold Exceeded Data Columns</span></span>  
  
|<span data-ttu-id="c8867-108">Nome da coluna de dados</span><span class="sxs-lookup"><span data-stu-id="c8867-108">Data column name</span></span>|<span data-ttu-id="c8867-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c8867-109">Data type</span></span>|<span data-ttu-id="c8867-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c8867-110">Description</span></span>|<span data-ttu-id="c8867-111">ID da coluna</span><span class="sxs-lookup"><span data-stu-id="c8867-111">Column ID</span></span>|<span data-ttu-id="c8867-112">Filtrável</span><span class="sxs-lookup"><span data-stu-id="c8867-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="c8867-113">CPU</span><span class="sxs-lookup"><span data-stu-id="c8867-113">CPU</span></span>|`int`|<span data-ttu-id="c8867-114">Uso de CPU em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="c8867-114">CPU usage in milliseconds.</span></span>|<span data-ttu-id="c8867-115">18</span><span class="sxs-lookup"><span data-stu-id="c8867-115">18</span></span>|<span data-ttu-id="c8867-116">Sim</span><span class="sxs-lookup"><span data-stu-id="c8867-116">Yes</span></span>|  
|<span data-ttu-id="c8867-117">EventClass</span><span class="sxs-lookup"><span data-stu-id="c8867-117">EventClass</span></span>|`int`|<span data-ttu-id="c8867-118">214</span><span class="sxs-lookup"><span data-stu-id="c8867-118">214</span></span>|<span data-ttu-id="c8867-119">27</span><span class="sxs-lookup"><span data-stu-id="c8867-119">27</span></span>|<span data-ttu-id="c8867-120">Não</span><span class="sxs-lookup"><span data-stu-id="c8867-120">No</span></span>|  
|<span data-ttu-id="c8867-121">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="c8867-121">EventSubClass</span></span>|`int`|<span data-ttu-id="c8867-122">Violação de limite da CPU.</span><span class="sxs-lookup"><span data-stu-id="c8867-122">CPU limit violation.</span></span>|<span data-ttu-id="c8867-123">21</span><span class="sxs-lookup"><span data-stu-id="c8867-123">21</span></span>|<span data-ttu-id="c8867-124">Sim</span><span class="sxs-lookup"><span data-stu-id="c8867-124">Yes</span></span>|  
|<span data-ttu-id="c8867-125">GroupID</span><span class="sxs-lookup"><span data-stu-id="c8867-125">GroupID</span></span>|`int`|<span data-ttu-id="c8867-126">ID do grupo onde a violação ocorreu.</span><span class="sxs-lookup"><span data-stu-id="c8867-126">Group ID where the violation occurred.</span></span>|<span data-ttu-id="c8867-127">66</span><span class="sxs-lookup"><span data-stu-id="c8867-127">66</span></span>|<span data-ttu-id="c8867-128">Sim</span><span class="sxs-lookup"><span data-stu-id="c8867-128">Yes</span></span>|  
|<span data-ttu-id="c8867-129">OwnerID</span><span class="sxs-lookup"><span data-stu-id="c8867-129">OwnerID</span></span>|`int`|<span data-ttu-id="c8867-130">SPID do processo que causou a violação.</span><span class="sxs-lookup"><span data-stu-id="c8867-130">SPID of the process that caused the violation.</span></span>|<span data-ttu-id="c8867-131">58</span><span class="sxs-lookup"><span data-stu-id="c8867-131">58</span></span>|<span data-ttu-id="c8867-132">Sim</span><span class="sxs-lookup"><span data-stu-id="c8867-132">Yes</span></span>|  
|<span data-ttu-id="c8867-133">SPID</span><span class="sxs-lookup"><span data-stu-id="c8867-133">SPID</span></span>|`int`|<span data-ttu-id="c8867-134">ID do processo de servidor que dispara este evento.</span><span class="sxs-lookup"><span data-stu-id="c8867-134">ID of the server process that fires this event.</span></span><br /><br /> <span data-ttu-id="c8867-135">Observação: poderá ser diferente do verdadeiro SPID do usuário se um thread de sistema validar o uso da CPU como uma tarefa em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c8867-135">Note: This can differ from the actual user SPID if a system thread validates CPU usage as a background task.</span></span>|<span data-ttu-id="c8867-136">12</span><span class="sxs-lookup"><span data-stu-id="c8867-136">12</span></span>|<span data-ttu-id="c8867-137">Sim</span><span class="sxs-lookup"><span data-stu-id="c8867-137">Yes</span></span>|  
|<span data-ttu-id="c8867-138">StartTime</span><span class="sxs-lookup"><span data-stu-id="c8867-138">StartTime</span></span>|`datetime`|<span data-ttu-id="c8867-139">A hora em que esse evento foi disparado.</span><span class="sxs-lookup"><span data-stu-id="c8867-139">The time when this event fired.</span></span>|<span data-ttu-id="c8867-140">14</span><span class="sxs-lookup"><span data-stu-id="c8867-140">14</span></span>|<span data-ttu-id="c8867-141">Sim</span><span class="sxs-lookup"><span data-stu-id="c8867-141">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8867-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8867-142">See Also</span></span>  
 [<span data-ttu-id="c8867-143">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8867-143">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
