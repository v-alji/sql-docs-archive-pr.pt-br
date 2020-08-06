---
title: MSSQL_ENG014005 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014005 error
ms.assetid: f168f0d6-cb11-45d4-9781-c374d7f388ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d820fd26cceee72b0d08204d6f6ce73a76508e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569368"
---
# <a name="mssql_eng014005"></a><span data-ttu-id="2229f-102">MSSQL_ENG014005</span><span class="sxs-lookup"><span data-stu-id="2229f-102">MSSQL_ENG014005</span></span>
    
## <a name="message-details"></a><span data-ttu-id="2229f-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="2229f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2229f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2229f-104">Product Name</span></span>|<span data-ttu-id="2229f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2229f-105">SQL Server</span></span>|  
|<span data-ttu-id="2229f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2229f-106">Event ID</span></span>|<span data-ttu-id="2229f-107">14005</span><span class="sxs-lookup"><span data-stu-id="2229f-107">14005</span></span>|  
|<span data-ttu-id="2229f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2229f-108">Event Source</span></span>|<span data-ttu-id="2229f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2229f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2229f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2229f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="2229f-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2229f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="2229f-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2229f-112">Message Text</span></span>|<span data-ttu-id="2229f-113">Não foi possível descartar a publicação.</span><span class="sxs-lookup"><span data-stu-id="2229f-113">Could not drop publication.</span></span> <span data-ttu-id="2229f-114">Existe uma assinatura para ela.</span><span class="sxs-lookup"><span data-stu-id="2229f-114">A subscription exists to it.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2229f-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="2229f-115">Explanation</span></span>  
 <span data-ttu-id="2229f-116">Você tentou descartar uma publicação que tem uma ou mais assinatura associadas.</span><span class="sxs-lookup"><span data-stu-id="2229f-116">You have tried to drop a publication which has one or more associated subscriptions.</span></span> <span data-ttu-id="2229f-117">Uma publicação pode ser descartada somente se não houver nenhuma assinatura associada.</span><span class="sxs-lookup"><span data-stu-id="2229f-117">A publication can only be dropped if there are no associated subscriptions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2229f-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2229f-118">User Action</span></span>  
 <span data-ttu-id="2229f-119">Descarte as assinaturas antes de descartar a publicação.</span><span class="sxs-lookup"><span data-stu-id="2229f-119">Drop the subscriptions before dropping the publication.</span></span> <span data-ttu-id="2229f-120">Se você usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para descartar a publicação, haverá a opção de descartar automaticamente todas as assinaturas associadas antes de descartar a publicação.</span><span class="sxs-lookup"><span data-stu-id="2229f-120">If you use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to drop the publication, it will give you the option to automatically drop all associated subscriptions before dropping the publication.</span></span> <span data-ttu-id="2229f-121">Se você usar procedimentos armazenados, primeiro será necessário descartar explicitamente as assinaturas.</span><span class="sxs-lookup"><span data-stu-id="2229f-121">If you use stored procedures, you must explicitly drop the subscriptions first.</span></span> <span data-ttu-id="2229f-122">Para obter mais informações, consulte [Delete a Push Subscription](delete-a-push-subscription.md) e [Delete a Pull Subscription](delete-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="2229f-122">For more information, see [Delete a Push Subscription](delete-a-push-subscription.md) and [Delete a Pull Subscription](delete-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="2229f-123">Se não existirem assinaturas para a publicação ou se o erro for exibido ao criar uma publicação, talvez exista uma assinatura anterior que não foi limpa completamente quando você tentou removê-la.</span><span class="sxs-lookup"><span data-stu-id="2229f-123">If no subscriptions appear to exist for the publication or if you see this error when you create a publication, you might have a previous subscription that was not completely cleaned up when it was removed.</span></span> <span data-ttu-id="2229f-124">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) no banco de dados para remover todas as configurações e todos os objetos relacionados à replicação.</span><span class="sxs-lookup"><span data-stu-id="2229f-124">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) on the database to remove all objects and settings related to replication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2229f-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2229f-125">See Also</span></span>  
 [<span data-ttu-id="2229f-126">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="2229f-126">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
