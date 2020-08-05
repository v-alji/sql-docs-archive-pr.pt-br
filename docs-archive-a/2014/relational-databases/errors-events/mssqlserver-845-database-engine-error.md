---
title: MSSQLSERVER_845 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 845 (Database Engine error)
ms.assetid: 8fff6ad4-234c-44be-b123-e25d5e1cd63e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 24bfb8b3758d0656dad96e4af4ed3b94aa51e07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572572"
---
# <a name="mssqlserver_845"></a><span data-ttu-id="a3e74-102">MSSQLSERVER_845</span><span class="sxs-lookup"><span data-stu-id="a3e74-102">MSSQLSERVER_845</span></span>
    
## <a name="details"></a><span data-ttu-id="a3e74-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a3e74-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3e74-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a3e74-104">Product Name</span></span>|<span data-ttu-id="a3e74-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3e74-105">SQL Server</span></span>|  
|<span data-ttu-id="a3e74-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a3e74-106">Event ID</span></span>|<span data-ttu-id="a3e74-107">845</span><span class="sxs-lookup"><span data-stu-id="a3e74-107">845</span></span>|  
|<span data-ttu-id="a3e74-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a3e74-108">Event Source</span></span>|<span data-ttu-id="a3e74-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3e74-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3e74-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3e74-110">Component</span></span>|<span data-ttu-id="a3e74-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a3e74-111">SQLEngine</span></span>|  
|<span data-ttu-id="a3e74-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a3e74-112">Symbolic Name</span></span>|<span data-ttu-id="a3e74-113">BUFLATCH_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3e74-113">BUFLATCH_TIMEOUT</span></span>|  
|<span data-ttu-id="a3e74-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a3e74-114">Message Text</span></span>|<span data-ttu-id="a3e74-115">Tempo limite excedido ao aguardar pelo tipo de fechamento de buffer %d para página %S_PGID, da ID de banco de dados %d.</span><span class="sxs-lookup"><span data-stu-id="a3e74-115">Time-out occurred while waiting for buffer latch type %d for page %S_PGID, database ID %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3e74-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="a3e74-116">Explanation</span></span>  
 <span data-ttu-id="a3e74-117">Um processo estava aguardando a aquisição de uma trava, mas ele aguardou até o tempo limite expirar e não foi capaz de adquiri-la.</span><span class="sxs-lookup"><span data-stu-id="a3e74-117">A process was waiting to acquire a latch, but the process waited until the time limit expired and failed to acquire one.</span></span> <span data-ttu-id="a3e74-118">Isso pode ocorrer se uma operação de E/S levar muito tempo para ser concluída, geralmente porque outras tarefas estão bloqueando os processos do sistema.</span><span class="sxs-lookup"><span data-stu-id="a3e74-118">This can occur if an I/O operation takes too long to complete, usually as a result of other tasks blocking system processes.</span></span> <span data-ttu-id="a3e74-119">Em algumas instâncias, esse erro pode ser o resultado de um problema de hardware.</span><span class="sxs-lookup"><span data-stu-id="a3e74-119">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3e74-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a3e74-120">User Action</span></span>  
 <span data-ttu-id="a3e74-121">Executar as seguintes tarefas pode evitar esse erro:</span><span class="sxs-lookup"><span data-stu-id="a3e74-121">Performing the following tasks may prevent this error:</span></span>  
  
-   <span data-ttu-id="a3e74-122">Reduza a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a3e74-122">Reduce the workload.</span></span>  
  
-   <span data-ttu-id="a3e74-123">Verifique se há falhas de E/S associadas no log de erros ou no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="a3e74-123">Verify whether there are associated I/O failures in the error log or event log.</span></span> <span data-ttu-id="a3e74-124">Geralmente, as falhas de E/S são causadas por funcionamento inadequado do disco.</span><span class="sxs-lookup"><span data-stu-id="a3e74-124">I/O failures are typically caused by disk malfunction.</span></span>  
  
-   <span data-ttu-id="a3e74-125">Verifique o log de erros de tarefas não produzidas e outros erros críticos.</span><span class="sxs-lookup"><span data-stu-id="a3e74-125">Check error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="a3e74-126">Se ocorrerem erros críticos frequentemente, como afirmações, resolva esses problemas.</span><span class="sxs-lookup"><span data-stu-id="a3e74-126">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="a3e74-127">Se o erro persistir, contate o Serviço de Suporte e Atendimento ao Cliente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3e74-127">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
