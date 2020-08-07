---
title: Categoria de evento de transações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Transactions event category
- event classes [SQL Server], Transactions event category
- Transactions event category [SQL Server]
ms.assetid: bfc75c5b-7115-49d8-9148-a0c84ee66a9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b68a91fb166797c220cb0c4f5cf2607ca267538
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576414"
---
# <a name="transactions-event-category"></a><span data-ttu-id="015bc-102">Categoria de eventos Transactions</span><span class="sxs-lookup"><span data-stu-id="015bc-102">Transactions Event Category</span></span>
  <span data-ttu-id="015bc-103">As classes de evento **Transactions** podem ser usadas para monitorar o status das transações.</span><span class="sxs-lookup"><span data-stu-id="015bc-103">The **Transactions** event classes can be used to monitor the status of transactions.</span></span> <span data-ttu-id="015bc-104">Os nomes da classe de evento que são predeterminados com **TM:** são usados para rastrear as operações relacionadas à transação que são enviadas pela interface de gerenciamento de transações.</span><span class="sxs-lookup"><span data-stu-id="015bc-104">The event class names that are prefixed with **TM:** are used to track the transaction-related operations that are sent through the transaction management interface.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="015bc-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="015bc-105">In This Section</span></span>  
  
|<span data-ttu-id="015bc-106">Tópico</span><span class="sxs-lookup"><span data-stu-id="015bc-106">Topic</span></span>|<span data-ttu-id="015bc-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="015bc-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="015bc-108">Classe de evento DTCTransaction</span><span class="sxs-lookup"><span data-stu-id="015bc-108">DTCTransaction Event Class</span></span>](dtctransaction-event-class.md)|<span data-ttu-id="015bc-109">Rastreia as transações coordenadas pelo MS DTC (Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="015bc-109">Tracks transactions coordinated by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="015bc-110">Essas são transações distribuídas entre dois ou mais bancos de dados ou instâncias do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="015bc-110">These are transactions distributed between two or more databases or instances of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>|  
|[<span data-ttu-id="015bc-111">Classe de evento SQLTransaction</span><span class="sxs-lookup"><span data-stu-id="015bc-111">SQLTransaction Event Class</span></span>](sqltransaction-event-class.md)|<span data-ttu-id="015bc-112">Rastreia as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN e ROLLBACK TRAN.</span><span class="sxs-lookup"><span data-stu-id="015bc-112">Tracks [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN, and ROLLBACK TRAN statements.</span></span>|  
|[<span data-ttu-id="015bc-113">Classe de evento TM: Begin Tran Completed</span><span class="sxs-lookup"><span data-stu-id="015bc-113">TM: Begin Tran Completed Event Class</span></span>](tm-begin-tran-completed-event-class.md)|<span data-ttu-id="015bc-114">Indica que uma solicitação BEGIN TRANSACTION foi concluída.</span><span class="sxs-lookup"><span data-stu-id="015bc-114">Indicates that a BEGIN TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="015bc-115">Classe de evento TM: Begin Tran Starting</span><span class="sxs-lookup"><span data-stu-id="015bc-115">TM: Begin Tran Starting Event Class</span></span>](tm-begin-tran-starting-event-class.md)|<span data-ttu-id="015bc-116">Indica que uma solicitação BEGIN TRANSACTION está iniciando.</span><span class="sxs-lookup"><span data-stu-id="015bc-116">Indicates that a BEGIN TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="015bc-117">Classe de evento TM: Commit Tran Completed</span><span class="sxs-lookup"><span data-stu-id="015bc-117">TM: Commit Tran Completed Event Class</span></span>](tm-commit-tran-completed-event-class.md)|<span data-ttu-id="015bc-118">Indica que uma solicitação COMMIT TRANSACTION foi concluída.</span><span class="sxs-lookup"><span data-stu-id="015bc-118">Indicates that a COMMIT TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="015bc-119">Classe de evento TM: Commit Tran Starting</span><span class="sxs-lookup"><span data-stu-id="015bc-119">TM: Commit Tran Starting Event Class</span></span>](tm-commit-tran-starting-event-class.md)|<span data-ttu-id="015bc-120">Indica que uma solicitação COMMIT TRANSACTION está iniciando.</span><span class="sxs-lookup"><span data-stu-id="015bc-120">Indicates that a COMMIT TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="015bc-121">Classe de evento TM: Promote Tran Completed</span><span class="sxs-lookup"><span data-stu-id="015bc-121">TM: Promote Tran Completed Event Class</span></span>](tm-promote-tran-completed-event-class.md)|<span data-ttu-id="015bc-122">Indica que uma solicitação PROMOTE TRANSACTION foi concluída.</span><span class="sxs-lookup"><span data-stu-id="015bc-122">Indicates that a PROMOTE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="015bc-123">Classe de evento TM: Promote Tran Starting</span><span class="sxs-lookup"><span data-stu-id="015bc-123">TM: Promote Tran Starting Event Class</span></span>](tm-promote-tran-starting-event-class.md)|<span data-ttu-id="015bc-124">Indica que uma solicitação PROMOTE TRANSACTION está iniciando.</span><span class="sxs-lookup"><span data-stu-id="015bc-124">Indicates that a PROMOTE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="015bc-125">Classe de evento TM: Rollback Tran Completed</span><span class="sxs-lookup"><span data-stu-id="015bc-125">TM: Rollback Tran Completed Event Class</span></span>](tm-rollback-tran-completed-event-class.md)|<span data-ttu-id="015bc-126">Indica que uma solicitação ROLLBACK TRANSACTION foi concluída.</span><span class="sxs-lookup"><span data-stu-id="015bc-126">Indicates that a ROLLBACK TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="015bc-127">Classe de evento TM: Rollback Tran Starting</span><span class="sxs-lookup"><span data-stu-id="015bc-127">TM: Rollback Tran Starting Event Class</span></span>](tm-rollback-tran-starting-event-class.md)|<span data-ttu-id="015bc-128">Indica que uma solicitação ROLLBACK TRANSACTION está iniciando.</span><span class="sxs-lookup"><span data-stu-id="015bc-128">Indicates that a ROLLBACK TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="015bc-129">Classe de evento TM: Save Tran Completed</span><span class="sxs-lookup"><span data-stu-id="015bc-129">TM: Save Tran Completed Event Class</span></span>](tm-save-tran-completed-event-class.md)|<span data-ttu-id="015bc-130">Indica que uma solicitação SAVE TRANSACTION foi concluída.</span><span class="sxs-lookup"><span data-stu-id="015bc-130">Indicates that a SAVE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="015bc-131">Classe de evento TM: Save Tran Starting</span><span class="sxs-lookup"><span data-stu-id="015bc-131">TM: Save Tran Starting Event Class</span></span>](tm-save-tran-starting-event-class.md)|<span data-ttu-id="015bc-132">Indica que uma solicitação SAVE TRANSACTION está iniciando.</span><span class="sxs-lookup"><span data-stu-id="015bc-132">Indicates that a SAVE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="015bc-133">Classe de evento TransactionLog</span><span class="sxs-lookup"><span data-stu-id="015bc-133">TransactionLog Event Class</span></span>](transactionlog-event-class.md)|<span data-ttu-id="015bc-134">Rastreia quando as transações são gravadas em um log de transações do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="015bc-134">Tracks when transactions are written to a database transaction log.</span></span>|  
  
  
