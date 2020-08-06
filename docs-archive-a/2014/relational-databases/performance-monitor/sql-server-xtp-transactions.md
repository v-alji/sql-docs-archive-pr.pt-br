---
title: Transações XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 443d67e4-1c7f-41d7-b18d-2d657f58c22a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 75fa8bc9a673d9e0e018b8578a35af2e46b5044c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679897"
---
# <a name="xtp-transactions"></a><span data-ttu-id="de957-102">Transações de XTP</span><span class="sxs-lookup"><span data-stu-id="de957-102">XTP Transactions</span></span>
  <span data-ttu-id="de957-103">O objeto de desempenho Transações de XTP contém os contadores relacionados às transações do mecanismo de XTP no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de957-103">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="de957-104">Esta tabela descreve os contadores **Transações de XTP** .</span><span class="sxs-lookup"><span data-stu-id="de957-104">This table describes the **XTP Transactions** counters.</span></span>  
  
|<span data-ttu-id="de957-105">Contador</span><span class="sxs-lookup"><span data-stu-id="de957-105">Counter</span></span>|<span data-ttu-id="de957-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="de957-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de957-107">**Anulações em cascata/s**</span><span class="sxs-lookup"><span data-stu-id="de957-107">**Cascading aborts/sec**</span></span>|<span data-ttu-id="de957-108">O número de transações que foram revertidas devido a uma reversão de dependência de confirmação (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-108">The number of transactions that rolled back to due a commit dependency rollback (on average), per second.</span></span>|  
|<span data-ttu-id="de957-109">**Dependências de confirmação realizadas/s**</span><span class="sxs-lookup"><span data-stu-id="de957-109">**Commit dependencies taken/sec**</span></span>|<span data-ttu-id="de957-110">O número de dependências de confirmação realizadas por transações (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-110">The number of commit dependencies taken by transactions (on average), per second.</span></span>|  
|<span data-ttu-id="de957-111">**Transações somente leitura preparadas/s**</span><span class="sxs-lookup"><span data-stu-id="de957-111">**Read-only transactions prepared/sec**</span></span>|<span data-ttu-id="de957-112">O número de transações somente leitura que foram preparadas para o processamento da confirmação, por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-112">The number of read-only transactions that were prepared for commit processing, per second.</span></span>|  
|<span data-ttu-id="de957-113">**Atualizações de ponto de salvamento/s**</span><span class="sxs-lookup"><span data-stu-id="de957-113">**Save point refreshes/sec**</span></span>|<span data-ttu-id="de957-114">O número de vezes que um ponto de salvamento foi “atualizado”, (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-114">The number of times a savepoint was "refreshed", (on average), per second.</span></span> <span data-ttu-id="de957-115">Uma atualização de ponto de salvamento é quando um ponto de salvamento existente é redefinido para o momento atual no tempo de vida da transação.</span><span class="sxs-lookup"><span data-stu-id="de957-115">A savepoint refresh is when an existing savepoint is reset to the current point in the transaction's lifetime.</span></span>|  
|<span data-ttu-id="de957-116">**Reversões de ponto de salvamento/s**</span><span class="sxs-lookup"><span data-stu-id="de957-116">**Save point rollbacks/sec**</span></span>|<span data-ttu-id="de957-117">O número de vezes que uma transação foi revertida para um ponto de salvamento (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-117">The number of times a transaction rolled back to a save point (on average), per second.</span></span>|  
|<span data-ttu-id="de957-118">**Pontos de salvamento criados/s**</span><span class="sxs-lookup"><span data-stu-id="de957-118">**Save points created /sec**</span></span>|<span data-ttu-id="de957-119">O número de pontos de salvamento criados (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-119">The number of save points created (on average), per second.</span></span>|  
|<span data-ttu-id="de957-120">**Falha de validação de transação/s**</span><span class="sxs-lookup"><span data-stu-id="de957-120">**Transaction validation failure/sec**</span></span>|<span data-ttu-id="de957-121">O número de transações que falharam no processamento de validação (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-121">The number of transactions that failed validation processing (on average), per second.</span></span>|  
|<span data-ttu-id="de957-122">**Transações anuladas por usuário/s**</span><span class="sxs-lookup"><span data-stu-id="de957-122">**Transactions aborted by user/sec**</span></span>|<span data-ttu-id="de957-123">O número de transações que foram anuladas pelo usuário (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-123">The number of transactions that were aborted by the user (on average), per second.</span></span>|  
|<span data-ttu-id="de957-124">**Transações anuladas/s**</span><span class="sxs-lookup"><span data-stu-id="de957-124">**Transactions aborted/sec**</span></span>|<span data-ttu-id="de957-125">O número de transações que foram anuladas (pelo usuário e pelo sistema) em média, por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-125">The number of transactions that aborted (both by the user and the system, on average), per second.</span></span>|  
|<span data-ttu-id="de957-126">**Transações criadas/s**</span><span class="sxs-lookup"><span data-stu-id="de957-126">**Transactions created/sec**</span></span>|<span data-ttu-id="de957-127">O número de transações criadas no sistema (em média), por segundo.</span><span class="sxs-lookup"><span data-stu-id="de957-127">The number of transactions created in the system (on average), per second.</span></span><br /><br /> <span data-ttu-id="de957-128">As transações de XTP são contadas diferentemente de transações baseadas em disco (conforme refletido em bancos de dados:transações/s).</span><span class="sxs-lookup"><span data-stu-id="de957-128">XTP transactions are counted differently than disk-based transactions (as reflected in Databases:Transactions/sec).</span></span> <span data-ttu-id="de957-129">Por exemplo, transações criadas/s contam como transações somente leitura, mas isso não ocorre com bancos de dados:transações/s.</span><span class="sxs-lookup"><span data-stu-id="de957-129">For example, Transactions created/sec counts read/only transactions, while Databases:Transactions/sec does not.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de957-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de957-130">See Also</span></span>  
 [<span data-ttu-id="de957-131">&#40;de OLTP na memória&#41; contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="de957-131">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
