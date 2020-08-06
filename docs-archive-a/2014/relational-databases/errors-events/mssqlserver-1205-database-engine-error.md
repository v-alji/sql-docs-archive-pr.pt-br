---
title: MSSQLSERVER_1205 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1205 (Database Engine error)
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6afa81a05eea37bc67cd2e9ac2433b6c82f35b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568615"
---
# <a name="mssqlserver_1205"></a><span data-ttu-id="3cbfd-102">MSSQLSERVER_1205</span><span class="sxs-lookup"><span data-stu-id="3cbfd-102">MSSQLSERVER_1205</span></span>
    
## <a name="details"></a><span data-ttu-id="3cbfd-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3cbfd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3cbfd-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="3cbfd-104">Product Name</span></span>|<span data-ttu-id="3cbfd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3cbfd-105">SQL Server</span></span>|  
|<span data-ttu-id="3cbfd-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3cbfd-106">Event ID</span></span>|<span data-ttu-id="3cbfd-107">1205</span><span class="sxs-lookup"><span data-stu-id="3cbfd-107">1205</span></span>|  
|<span data-ttu-id="3cbfd-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="3cbfd-108">Event Source</span></span>|<span data-ttu-id="3cbfd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3cbfd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3cbfd-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3cbfd-110">Component</span></span>|<span data-ttu-id="3cbfd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3cbfd-111">SQLEngine</span></span>|  
|<span data-ttu-id="3cbfd-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="3cbfd-112">Symbolic Name</span></span>|<span data-ttu-id="3cbfd-113">LK_VICTIM</span><span class="sxs-lookup"><span data-stu-id="3cbfd-113">LK_VICTIM</span></span>|  
|<span data-ttu-id="3cbfd-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="3cbfd-114">Message Text</span></span>|<span data-ttu-id="3cbfd-115">A transação (ID do processo %d) entrou em deadlock em %.\*ls recursos com outro processo e foi escolhida como a vítima do deadlock.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-115">Transaction (Process ID %d) was deadlocked on %.\*ls resources with another process and has been chosen as the deadlock victim.</span></span> <span data-ttu-id="3cbfd-116">Execute a transação novamente.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-116">Rerun the transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3cbfd-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="3cbfd-117">Explanation</span></span>  
 <span data-ttu-id="3cbfd-118">Os recursos podem ser acessados em ordem conflitante em transações separadas, causando um deadlock.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-118">Resources are accessed in conflicting order on separate transactions, causing a deadlock.</span></span> <span data-ttu-id="3cbfd-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3cbfd-119">For example:</span></span>  
  
-   <span data-ttu-id="3cbfd-120">Transaction1 atualiza **Table1.Row1**, enquanto Transaction2 atualiza **Table2.Row2**.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-120">Transaction1 updates **Table1.Row1**, while Transaction2 updates **Table2.Row2**.</span></span>  
  
-   <span data-ttu-id="3cbfd-121">Transaction1 tenta atualizar **Table2.Row2**, mas é bloqueada, porque Transaction2 ainda não foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-121">Transaction1 tries to update **Table2.Row2** but is blocked because Transaction2 has not yet committed.</span></span>  
  
-   <span data-ttu-id="3cbfd-122">Transaction2 agora tenta atualizar **Table1.Row1**, mas é bloqueada porque Transaction1 ainda não foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-122">Transaction2 now tries to update **Table1.Row1** but is blocked because Transaction1 has not committed.</span></span>  
  
-   <span data-ttu-id="3cbfd-123">Um deadlock acontece porque a Transação1 está esperando a conclusão da Transação2, mas a Transação2 está esperando a conclusão da Transação1.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-123">A deadlock occurs because Transaction1 is waiting for Transaction2 to complete, but Transaction2 is waiting for Transaction1 to complete.</span></span>  
  
 <span data-ttu-id="3cbfd-124">O sistema detecta o deadlock, escolhe uma das transações envolvidas como 'vítima' e emite a mensagem, revertendo a transação da vítima.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-124">The system will detect this deadlock and will choose one of the transactions involved as a 'victim' and will issue this message, rolling back the victim's transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3cbfd-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3cbfd-125">User Action</span></span>  
 <span data-ttu-id="3cbfd-126">Execute a transação novamente.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-126">Execute the transaction again.</span></span> <span data-ttu-id="3cbfd-127">Você também pode revisar o aplicativo para evitar deadlocks.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-127">You can also revise the application to avoid deadlocks.</span></span> <span data-ttu-id="3cbfd-128">A transação escolhida como vítima pode ser testada novamente e, provavelmente, terá êxito, dependendo de quais operações estiverem sendo executadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-128">The transaction that was chosen as a victim can be retried and will likely succeed, depending on what operations are being executed simultaneously.</span></span>  
  
 <span data-ttu-id="3cbfd-129">Para impedir ou evitar a ocorrência de deadlocks, faça com que todas as transações acessem as linhas na mesma ordem (**Table1** e, depois, **Table2**); desse modo, embora possa acontecer um bloqueio, não ocorrerá um deadlock.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-129">To prevent or avoid deadlocks from occurring, consider having all transactions access rows in the same order (**Table1**, then **Table2**); this way, although blocking might occur, a deadlock will not occur.</span></span>  
  
  
