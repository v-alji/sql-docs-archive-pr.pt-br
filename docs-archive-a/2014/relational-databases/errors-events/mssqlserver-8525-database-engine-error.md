---
title: MSSQLSERVER_8525 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "8525"
helpviewer_keywords:
- 8525 (Database Engine error)
ms.assetid: 297867c1-691e-4d6b-a3be-a7575015ecfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 36db48ca2a9afd08dadcd12abc13b9978e227b00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575865"
---
# <a name="mssqlserver_8525"></a><span data-ttu-id="7fece-102">MSSQLSERVER_8525</span><span class="sxs-lookup"><span data-stu-id="7fece-102">MSSQLSERVER_8525</span></span>
    
## <a name="details"></a><span data-ttu-id="7fece-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7fece-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7fece-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7fece-104">Product Name</span></span>|<span data-ttu-id="7fece-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fece-105">SQL Server</span></span>|  
|<span data-ttu-id="7fece-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7fece-106">Event ID</span></span>|<span data-ttu-id="7fece-107">8525</span><span class="sxs-lookup"><span data-stu-id="7fece-107">8525</span></span>|  
|<span data-ttu-id="7fece-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7fece-108">Event Source</span></span>|<span data-ttu-id="7fece-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7fece-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7fece-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7fece-110">Component</span></span>|<span data-ttu-id="7fece-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7fece-111">SQLEngine</span></span>|  
|<span data-ttu-id="7fece-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7fece-112">Symbolic Name</span></span>||  
|<span data-ttu-id="7fece-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7fece-113">Message Text</span></span>|<span data-ttu-id="7fece-114">Transação distribuída concluída.</span><span class="sxs-lookup"><span data-stu-id="7fece-114">Distributed transaction completed.</span></span> <span data-ttu-id="7fece-115">Inscreva esta sessão em uma transação nova ou na transação NULL.</span><span class="sxs-lookup"><span data-stu-id="7fece-115">Either enlist this session in a new transaction or the NULL transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7fece-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="7fece-116">Explanation</span></span>  
 <span data-ttu-id="7fece-117">O modelo de programação para usar o Coordenador de Transações Distribuídas com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requer que os aplicativos sejam explicitamente inscritos e removidos de uma transação distribuída.</span><span class="sxs-lookup"><span data-stu-id="7fece-117">The programming model for using the Distributed Transaction Coordinator with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires applications to explicitly enlist to and defect from a distributed transaction.</span></span>  
  
 <span data-ttu-id="7fece-118">Este erro acontece quando as quatro condições seguintes são cumpridas:</span><span class="sxs-lookup"><span data-stu-id="7fece-118">This error occurs when the following four conditions are met:</span></span>  
  
-   <span data-ttu-id="7fece-119">O aplicativo foi inscrito em uma transação distribuída.</span><span class="sxs-lookup"><span data-stu-id="7fece-119">The application has enlisted into a distributed transaction.</span></span>  
  
-   <span data-ttu-id="7fece-120">A transação terminou, foi confirmada ou revertida, por alguma razão.</span><span class="sxs-lookup"><span data-stu-id="7fece-120">The transaction has ended, either committed or rolled back, for any reason.</span></span>  
  
-   <span data-ttu-id="7fece-121">O aplicativo de usuário não foi explicitamente removido de uma transação distribuída nem foi explicitamente inscrito em uma nova transação distribuída.</span><span class="sxs-lookup"><span data-stu-id="7fece-121">The user application has not explicitly defected from a distributed transaction or explicitly enlisted into a new distributed transaction.</span></span>  
  
-   <span data-ttu-id="7fece-122">O aplicativo tenta fazer alguma operação transacional diferente de remover-se de uma transação distribuída existente ou de inscrever-se em uma nova transação distribuída, como emitir uma consulta ou iniciar uma transação local.</span><span class="sxs-lookup"><span data-stu-id="7fece-122">The application tries to do any transactional operation other than defecting from existing distributed transaction or enlisting to a new distributed transaction, such as issuing a query or starting a local transaction.</span></span>  
  
 <span data-ttu-id="7fece-123">O estado do erro 1 é usado quando o aplicativo executa uma operação que cria transações locais, e o estado do erro 2 é usado quando aplicativo tenta se inscrever em uma sessão associada.</span><span class="sxs-lookup"><span data-stu-id="7fece-123">Error state 1 is used when the application performs an operation that creates local transactions, and state 2 is used when application tries to enlist to a bound session.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7fece-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7fece-124">User Action</span></span>  
 <span data-ttu-id="7fece-125">Depois de um aplicativo inscrever-se em uma transação distribuída, o aplicativo deve ser removido explicitamente da transação distribuída ou deve ser inscrito em outra transação distribuída.</span><span class="sxs-lookup"><span data-stu-id="7fece-125">After an application has enlisted into a distributed transaction, the application must explicitly defect from the distributed transaction or enlist to another distributed transaction.</span></span> <span data-ttu-id="7fece-126">Isto irá removê-lo implicitamente de uma transação inscrita anterior.</span><span class="sxs-lookup"><span data-stu-id="7fece-126">This will implicitly defect from a previous enlisted transaction.</span></span> <span data-ttu-id="7fece-127">Para a sintaxe exata para remoção ou inscrição em uma transação distribuída, consulte o manual de programação de interface do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7fece-127">For the exact syntax to defect from or enlist to a distributed transaction, see the programming interface manual for the application.</span></span>  
  
  
