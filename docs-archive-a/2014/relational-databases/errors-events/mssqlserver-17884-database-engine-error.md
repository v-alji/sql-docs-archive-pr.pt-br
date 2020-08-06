---
title: MSSQLSERVER_17884 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17884 (Database Engine error)
ms.assetid: 8d05ba05-3f71-4dc3-bd81-2ea5ac9fe843
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd5beca2a7dfd20afbf9eff196d89452ef3533d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681671"
---
# <a name="mssqlserver_17884"></a><span data-ttu-id="a7507-102">MSSQLSERVER_17884</span><span class="sxs-lookup"><span data-stu-id="a7507-102">MSSQLSERVER_17884</span></span>
    
## <a name="details"></a><span data-ttu-id="a7507-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a7507-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7507-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a7507-104">Product Name</span></span>|<span data-ttu-id="a7507-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a7507-105">SQL Server</span></span>|  
|<span data-ttu-id="a7507-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a7507-106">Event ID</span></span>|<span data-ttu-id="a7507-107">17884</span><span class="sxs-lookup"><span data-stu-id="a7507-107">17884</span></span>|  
|<span data-ttu-id="a7507-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a7507-108">Event Source</span></span>|<span data-ttu-id="a7507-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a7507-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a7507-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a7507-110">Component</span></span>|<span data-ttu-id="a7507-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a7507-111">SQLEngine</span></span>|  
|<span data-ttu-id="a7507-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a7507-112">Symbolic Name</span></span>|<span data-ttu-id="a7507-113">SRV_SCHEDULER_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="a7507-113">SRV_SCHEDULER_DEADLOCK</span></span>|  
|<span data-ttu-id="a7507-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a7507-114">Message Text</span></span>|<span data-ttu-id="a7507-115">Novas consultas atribuídas ao processo no Nó %d não foram selecionadas por um thread de trabalho nos últimos %d segundos.</span><span class="sxs-lookup"><span data-stu-id="a7507-115">New queries assigned to process on Node %d have not been picked  up by a worker thread in the last %d seconds.</span></span> <span data-ttu-id="a7507-116">Consultas de execução longa ou bloqueios podem contribuir para essa condição e afetar o tempo de resposta do cliente.</span><span class="sxs-lookup"><span data-stu-id="a7507-116">Blocking or long-running queries can contribute to this condition, and may degrade client response time.</span></span> <span data-ttu-id="a7507-117">Use a opção de configuração "max worker threads" (máximo de threads de trabalho) para aumentar o número de threads permitidos ou otimizar as consultas que estão sendo executadas atualmente.</span><span class="sxs-lookup"><span data-stu-id="a7507-117">Use the "max worker threads" configuration option to increase number  of allowable threads, or optimize current running queries.</span></span>  <span data-ttu-id="a7507-118">SQL Process Utilization: %d%%.</span><span class="sxs-lookup"><span data-stu-id="a7507-118">SQL Process Utilization: %d%%.</span></span> <span data-ttu-id="a7507-119">Sistema inativo: %d%%.</span><span class="sxs-lookup"><span data-stu-id="a7507-119">System Idle: %d%%.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a7507-120">Explicação</span><span class="sxs-lookup"><span data-stu-id="a7507-120">Explanation</span></span>  
 <span data-ttu-id="a7507-121">Não há sinal de progresso nos agendadores e isso pode ser causado por deadlocks onde nenhum dos threads pode avançar e/ou nenhum trabalho novo pode ser selecionado e processado.</span><span class="sxs-lookup"><span data-stu-id="a7507-121">There is no sign of progress in each of the schedulers and could be caused by deadlocks where none of the threads can advance and/or no new work can be picked up and processed.</span></span> <span data-ttu-id="a7507-122">Caso a utilização do processo esteja baixa, outros processos na máquina podem estar causando a privação de processo da CPU.</span><span class="sxs-lookup"><span data-stu-id="a7507-122">If process utilization is low then other processes on the machine may be causing the server process CPU starvation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7507-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a7507-123">User Action</span></span>  
 <span data-ttu-id="a7507-124">Determine porque existe um bloqueio e porque nenhum progresso está sendo feito. Em seguida, resolva a situação de maneira adequada.</span><span class="sxs-lookup"><span data-stu-id="a7507-124">Determine why there is blocking and no progress being made and resolve situation accordingly.</span></span> <span data-ttu-id="a7507-125">Caso a utilização do processo esteja baixa, verifique a carga no sistema causada por outros processos.</span><span class="sxs-lookup"><span data-stu-id="a7507-125">If process utilization is low check the load on the system caused by other processes.</span></span>  
  
  
