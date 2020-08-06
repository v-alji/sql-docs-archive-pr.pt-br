---
title: MSSQLSERVER_10539 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10539 (Database Engine error)
ms.assetid: 49c26ff7-18b8-4f07-a087-f45f63463b3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd1f190b8f5d3ab9755409bdd034fa374ea5314
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680457"
---
# <a name="mssqlserver_10539"></a><span data-ttu-id="71a1e-102">MSSQLSERVER_10539</span><span class="sxs-lookup"><span data-stu-id="71a1e-102">MSSQLSERVER_10539</span></span>
    
## <a name="details"></a><span data-ttu-id="71a1e-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="71a1e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="71a1e-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="71a1e-104">Product Name</span></span>|<span data-ttu-id="71a1e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="71a1e-105">SQL Server</span></span>|  
|<span data-ttu-id="71a1e-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="71a1e-106">Event ID</span></span>|<span data-ttu-id="71a1e-107">10539</span><span class="sxs-lookup"><span data-stu-id="71a1e-107">10539</span></span>|  
|<span data-ttu-id="71a1e-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="71a1e-108">Event Source</span></span>|<span data-ttu-id="71a1e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="71a1e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="71a1e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="71a1e-110">Component</span></span>|<span data-ttu-id="71a1e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="71a1e-111">SQLEngine</span></span>|  
|<span data-ttu-id="71a1e-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="71a1e-112">Symbolic Name</span></span>|<span data-ttu-id="71a1e-113">PG_NO_PLAN_FOR_STMT</span><span class="sxs-lookup"><span data-stu-id="71a1e-113">PG_NO_PLAN_FOR_STMT</span></span>|  
|<span data-ttu-id="71a1e-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="71a1e-114">Message Text</span></span>|<span data-ttu-id="71a1e-115">Não é possível criar o guia de plano '%.\*ls' a partir do cache porque um plano de consulta não está disponível para a instrução com deslocamento inicial %d.</span><span class="sxs-lookup"><span data-stu-id="71a1e-115">Cannot create plan guide '%.\*ls' from cache because a query plan is not available for the statement with start offset %d.</span></span> <span data-ttu-id="71a1e-116">Esse problema poderá ocorrer se a instrução depender de objetos do banco de dados que ainda não foram criados.</span><span class="sxs-lookup"><span data-stu-id="71a1e-116">This problem can occur if the statement depends on database objects that have not yet been created.</span></span> <span data-ttu-id="71a1e-117">Verifique se todos os objetos de banco de dados necessários existem e execute a instrução antes de criar o guia de plano.</span><span class="sxs-lookup"><span data-stu-id="71a1e-117">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="71a1e-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="71a1e-118">Explanation</span></span>  
 <span data-ttu-id="71a1e-119">Não há um plano de consulta disponível no cache de planos para a instrução com o deslocamento inicial especificado.</span><span class="sxs-lookup"><span data-stu-id="71a1e-119">A query plan is not available in the plan cache for the statement with the specified starting offset.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="71a1e-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="71a1e-120">User Action</span></span>  
 <span data-ttu-id="71a1e-121">Verifique se todos os objetos de banco de dados necessários existem e execute a instrução antes de criar o guia de plano.</span><span class="sxs-lookup"><span data-stu-id="71a1e-121">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a1e-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71a1e-122">See Also</span></span>  
 [<span data-ttu-id="71a1e-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="71a1e-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
