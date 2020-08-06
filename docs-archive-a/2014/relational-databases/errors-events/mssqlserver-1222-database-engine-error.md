---
title: MSSQLSERVER_1222 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1222 (Database Engine error)
ms.assetid: c5b1c2f4-f591-4cc1-aa17-204636a27f29
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ac3fe9314386836633a11f17d6775c75019de93a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568614"
---
# <a name="mssqlserver_1222"></a><span data-ttu-id="53e4d-102">MSSQLSERVER_1222</span><span class="sxs-lookup"><span data-stu-id="53e4d-102">MSSQLSERVER_1222</span></span>
    
## <a name="details"></a><span data-ttu-id="53e4d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="53e4d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53e4d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="53e4d-104">Product Name</span></span>|<span data-ttu-id="53e4d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="53e4d-105">SQL Server</span></span>|  
|<span data-ttu-id="53e4d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="53e4d-106">Event ID</span></span>|<span data-ttu-id="53e4d-107">1222</span><span class="sxs-lookup"><span data-stu-id="53e4d-107">1222</span></span>|  
|<span data-ttu-id="53e4d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="53e4d-108">Event Source</span></span>|<span data-ttu-id="53e4d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="53e4d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="53e4d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="53e4d-110">Component</span></span>|<span data-ttu-id="53e4d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="53e4d-111">SQLEngine</span></span>|  
|<span data-ttu-id="53e4d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="53e4d-112">Symbolic Name</span></span>|<span data-ttu-id="53e4d-113">LK_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53e4d-113">LK_TIMEOUT</span></span>|  
|<span data-ttu-id="53e4d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="53e4d-114">Message Text</span></span>|<span data-ttu-id="53e4d-115">Tempo limite da solicitação de bloqueio excedido.</span><span class="sxs-lookup"><span data-stu-id="53e4d-115">Lock request time out period exceeded.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53e4d-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="53e4d-116">Explanation</span></span>  
 <span data-ttu-id="53e4d-117">Outra transação manteve um bloqueio em um recurso necessário por mais tempo do que esta consulta podia aguardar.</span><span class="sxs-lookup"><span data-stu-id="53e4d-117">Another transaction held a lock on a required resource longer than this query could wait for it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53e4d-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="53e4d-118">User Action</span></span>  
 <span data-ttu-id="53e4d-119">Execute as seguintes tarefas para aliviar o problema:</span><span class="sxs-lookup"><span data-stu-id="53e4d-119">Perform the following tasks to alleviate the problem:</span></span>  
  
1.  <span data-ttu-id="53e4d-120">Localize a transação que está mantendo o bloqueio no recurso necessário, se possível.</span><span class="sxs-lookup"><span data-stu-id="53e4d-120">Locate the transaction that is holding the lock on the required resource, if possible.</span></span> <span data-ttu-id="53e4d-121">Use as exibições de gerenciamento dinâmico **sys.dm_os_waiting_tasks** e **sys.dm_tran_locks**.</span><span class="sxs-lookup"><span data-stu-id="53e4d-121">Use **sys.dm_os_waiting_tasks** and **sys.dm_tran_locks** dynamic management views.</span></span>  
  
2.  <span data-ttu-id="53e4d-122">Se a transação ainda estiver mantendo o bloqueio, termine a transação, se necessário.</span><span class="sxs-lookup"><span data-stu-id="53e4d-122">If the transaction is still holding the lock, terminate that transaction if appropriate.</span></span>  
  
3.  <span data-ttu-id="53e4d-123">Execute a consulta novamente.</span><span class="sxs-lookup"><span data-stu-id="53e4d-123">Execute the query again.</span></span>  
  
 <span data-ttu-id="53e4d-124">Se esse erro ocorrer com frequência, altere o período de tempo limite de bloqueio ou modifique as transações incorretas para que mantenham o bloqueio por menos tempo.</span><span class="sxs-lookup"><span data-stu-id="53e4d-124">If this error occurs frequently change the lock time-out period or modify the offending transactions so that they hold the lock for less time.</span></span>  
  
  
