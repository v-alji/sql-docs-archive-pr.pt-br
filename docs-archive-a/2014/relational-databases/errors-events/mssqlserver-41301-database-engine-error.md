---
title: MSSQLSERVER_41301 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41301 (Database Engine error)
ms.assetid: c6127e1e-2846-4ee9-bc42-2d896ea9730e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d4fa78b334f32033f96df002aeaf039994b396cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575151"
---
# <a name="mssqlserver_41301"></a><span data-ttu-id="46717-102">MSSQLSERVER_41301</span><span class="sxs-lookup"><span data-stu-id="46717-102">MSSQLSERVER_41301</span></span>
    
## <a name="details"></a><span data-ttu-id="46717-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="46717-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46717-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="46717-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="46717-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="46717-105">Event ID</span></span>|<span data-ttu-id="46717-106">41301</span><span class="sxs-lookup"><span data-stu-id="46717-106">41301</span></span>|  
|<span data-ttu-id="46717-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="46717-107">Event Source</span></span>|<span data-ttu-id="46717-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46717-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46717-109">Componente</span><span class="sxs-lookup"><span data-stu-id="46717-109">Component</span></span>|<span data-ttu-id="46717-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46717-110">SQLEngine</span></span>|  
|<span data-ttu-id="46717-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="46717-111">Symbolic Name</span></span>|<span data-ttu-id="46717-112">COMMIT_DEPENDENCY_FAILURE</span><span class="sxs-lookup"><span data-stu-id="46717-112">COMMIT_DEPENDENCY_FAILURE</span></span>|  
|<span data-ttu-id="46717-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="46717-113">Message Text</span></span>|<span data-ttu-id="46717-114">Uma transação anterior na qual a transação atual obteve uma dependência foi anulada, e a transação atual não pode mais ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="46717-114">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46717-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="46717-115">Explanation</span></span>  
 <span data-ttu-id="46717-116">A transação encontrou uma falha de dependência e agora está condenada.</span><span class="sxs-lookup"><span data-stu-id="46717-116">The transaction encountered a dependency failure, and is now doomed.</span></span>  
  
 <span data-ttu-id="46717-117">Esse erro também pode ser causado por transações dependentes demais.</span><span class="sxs-lookup"><span data-stu-id="46717-117">This error can also be caused by too many dependent transactions.</span></span> <span data-ttu-id="46717-118">Qualquer transação de gravação pode ter um número limitado de transações dependentes.</span><span class="sxs-lookup"><span data-stu-id="46717-118">Any write transaction can have a limited number of dependent transactions.</span></span> <span data-ttu-id="46717-119">Por exemplo, esse erro pode ocorrer se muitas transações de leitura tentarem executar uma dependência na transação de atualização.</span><span class="sxs-lookup"><span data-stu-id="46717-119">For example, this error can occur if too many read transactions try to take a dependency on the update transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46717-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="46717-120">User Action</span></span>  
 <span data-ttu-id="46717-121">Não execute nenhum trabalho na transação.</span><span class="sxs-lookup"><span data-stu-id="46717-121">Don't do any work on the transaction.</span></span> <span data-ttu-id="46717-122">Chame ROLLBACK TRAN para reverter a transação.</span><span class="sxs-lookup"><span data-stu-id="46717-122">Call ROLLBACK TRAN to roll back the transaction.</span></span> <span data-ttu-id="46717-123">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="46717-123">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46717-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46717-124">See Also</span></span>  
 [<span data-ttu-id="46717-125">Habilitar e desabilitar grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="46717-125">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md)  
  
  
