---
title: MSSQLSERVER_844 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4870d6e43ec12b49033ea3b5f88fa0d0cdd597a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572576"
---
# <a name="mssqlserver_844"></a><span data-ttu-id="de67e-102">MSSQLSERVER_844</span><span class="sxs-lookup"><span data-stu-id="de67e-102">MSSQLSERVER_844</span></span>
    
## <a name="details"></a><span data-ttu-id="de67e-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="de67e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="de67e-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="de67e-104">Product Name</span></span>|<span data-ttu-id="de67e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="de67e-105">SQL Server</span></span>|  
|<span data-ttu-id="de67e-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="de67e-106">Event ID</span></span>|<span data-ttu-id="de67e-107">844</span><span class="sxs-lookup"><span data-stu-id="de67e-107">844</span></span>|  
|<span data-ttu-id="de67e-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="de67e-108">Event Source</span></span>|<span data-ttu-id="de67e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="de67e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="de67e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="de67e-110">Component</span></span>|<span data-ttu-id="de67e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="de67e-111">SQLEngine</span></span>|  
|<span data-ttu-id="de67e-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="de67e-112">Symbolic Name</span></span>|<span data-ttu-id="de67e-113">BUFLATCH_TIMEOUT_CONTINUE</span><span class="sxs-lookup"><span data-stu-id="de67e-113">BUFLATCH_TIMEOUT_CONTINUE</span></span>|  
|<span data-ttu-id="de67e-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="de67e-114">Message Text</span></span>|<span data-ttu-id="de67e-115">Tempo limite excedido ao aguardar a trava do buffer - tipo %d, bp %p, página %d:%d, stat %#x, id do banco de dados %d; id da unidade de alocação: %I64d%ls, tarefa 0x%p: %d, tempo de espera %d, sinalizadores 0x%I64x, tarefa proprietária 0x%p.</span><span class="sxs-lookup"><span data-stu-id="de67e-115">Time-out occurred while waiting for buffer latch -- type %d, bp %p, page %d:%d, stat %#x, database id: %d, allocation unit id: %I64d%ls, task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span>  <span data-ttu-id="de67e-116">Continuando espera.</span><span class="sxs-lookup"><span data-stu-id="de67e-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="de67e-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="de67e-117">Explanation</span></span>  
 <span data-ttu-id="de67e-118">Um processo está aguardando travamento.</span><span class="sxs-lookup"><span data-stu-id="de67e-118">A process is waiting to acquire a latch.</span></span> <span data-ttu-id="de67e-119">Esse problema pode ser causado por uma operação de E/S que leva muito tempo para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="de67e-119">This problem can be caused by an I/O operation taking too long to complete.</span></span> <span data-ttu-id="de67e-120">Normalmente esse tipo de erro é o resultado de outros processos do sistema de bloqueio de tarefas.</span><span class="sxs-lookup"><span data-stu-id="de67e-120">Typically this type of error is the result of other tasks blocking system processes.</span></span> <span data-ttu-id="de67e-121">Em algumas instâncias, esse erro pode ser o resultado de um problema de hardware.</span><span class="sxs-lookup"><span data-stu-id="de67e-121">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="de67e-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="de67e-122">User Action</span></span>  
 <span data-ttu-id="de67e-123">Tente o seguinte para evitar que esse erro ocorra:</span><span class="sxs-lookup"><span data-stu-id="de67e-123">Try the following to prevent this error from occurring:</span></span>  
  
-   <span data-ttu-id="de67e-124">Reduza a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="de67e-124">Reduce workload.</span></span>  
  
-   <span data-ttu-id="de67e-125">Verifique se há falhas de E/S associadas no log de erros ou no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="de67e-125">Check for associated I/O failures in error log or event log.</span></span> <span data-ttu-id="de67e-126">Normalmente as falhas de E/S indicam um funcionamento inadequado do disco.</span><span class="sxs-lookup"><span data-stu-id="de67e-126">I/O failures typically point to a disk malfunction.</span></span>  
  
-   <span data-ttu-id="de67e-127">Verifique no log de erros se existem tarefas não produzidas e outros erros críticos.</span><span class="sxs-lookup"><span data-stu-id="de67e-127">Check the error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="de67e-128">Se ocorrerem erros críticos frequentemente, como afirmações, resolva esses problemas.</span><span class="sxs-lookup"><span data-stu-id="de67e-128">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="de67e-129">Se o erro persistir, contate o Serviço de Suporte e Atendimento ao Cliente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de67e-129">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
