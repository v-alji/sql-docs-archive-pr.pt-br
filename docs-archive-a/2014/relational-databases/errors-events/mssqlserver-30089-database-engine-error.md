---
title: MSSQLSERVER_30089 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9992 (Database Engine error)
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d0b9c71ea620174f993ae87befed8a21bb3d0bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574035"
---
# <a name="mssqlserver_30089"></a><span data-ttu-id="18c5d-102">MSSQLSERVER_30089</span><span class="sxs-lookup"><span data-stu-id="18c5d-102">MSSQLSERVER_30089</span></span>
    
## <a name="details"></a><span data-ttu-id="18c5d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="18c5d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="18c5d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="18c5d-104">Product Name</span></span>|<span data-ttu-id="18c5d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="18c5d-105">SQL Server</span></span>|  
|<span data-ttu-id="18c5d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="18c5d-106">Event ID</span></span>|<span data-ttu-id="18c5d-107">30089</span><span class="sxs-lookup"><span data-stu-id="18c5d-107">30089</span></span>|  
|<span data-ttu-id="18c5d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="18c5d-108">Event Source</span></span>|<span data-ttu-id="18c5d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="18c5d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="18c5d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="18c5d-110">Component</span></span>|<span data-ttu-id="18c5d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="18c5d-111">SQLEngine</span></span>|  
|<span data-ttu-id="18c5d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="18c5d-112">Symbolic Name</span></span>|<span data-ttu-id="18c5d-113">IFTS_FDHOST_TERMINATEDABNORMAL</span><span class="sxs-lookup"><span data-stu-id="18c5d-113">IFTS_FDHOST_TERMINATEDABNORMAL</span></span>|  
|<span data-ttu-id="18c5d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="18c5d-114">Message Text</span></span>|<span data-ttu-id="18c5d-115">O processo FDHost (host do daemon de filtro de texto completo) foi interrompido de maneira anormal.</span><span class="sxs-lookup"><span data-stu-id="18c5d-115">The fulltext filter daemon host (FDHost) process has stopped abnormally.</span></span> <span data-ttu-id="18c5d-116">Isso poderá ocorrer se um componente linguístico configurado incorretamente ou que não está funcionando bem, como um separador de palavras, lematizador ou filtro, gerou um erro irrecuperável durante a indexação de texto completo ou no processamento de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="18c5d-116">This can occur if an incorrectly configured or malfunctioning linguistic component, such as a wordbreaker, stemmer or filter has caused an irrecoverable error during full-text indexing or query processing.</span></span> <span data-ttu-id="18c5d-117">O processo será reiniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="18c5d-117">The process will be restarted automatically.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="18c5d-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="18c5d-118">Explanation</span></span>  
 <span data-ttu-id="18c5d-119">O host do daemon de filtro de texto completo encontrou um problema que forçou seu encerramento de maneira anormal.</span><span class="sxs-lookup"><span data-stu-id="18c5d-119">The full-text filter daemon host has encountered some problem that has forced it to stop abnormally.</span></span> <span data-ttu-id="18c5d-120">A causa do problema pode ser um documento malformatado, um bug no filtro ou no separador de palavras ou um problema no daemon de filtro.</span><span class="sxs-lookup"><span data-stu-id="18c5d-120">The cause of the problem could be a badly formatted document, a bug in the filter or word-breaker, or a problem in filter daemon.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="18c5d-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="18c5d-121">User Action</span></span>  
 <span data-ttu-id="18c5d-122">Normalmente, o daemon se recupera do erro.</span><span class="sxs-lookup"><span data-stu-id="18c5d-122">Typically, the daemon will recover from the error.</span></span> <span data-ttu-id="18c5d-123">Se ele apresentar falhas constantes, será necessário diagnosticar e solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="18c5d-123">If it is consistently failing, troubleshooting is necessary.</span></span> <span data-ttu-id="18c5d-124">Tente fazer o seguinte para isolar o problema:</span><span class="sxs-lookup"><span data-stu-id="18c5d-124">Try the following to isolate the issue:</span></span>  
  
1.  <span data-ttu-id="18c5d-125">Se um novo componente linguístico foi instalado recentemente, remova-o do sistema.</span><span class="sxs-lookup"><span data-stu-id="18c5d-125">If a new linguistic component has been installed recently, remove it from the system.</span></span>  
  
2.  <span data-ttu-id="18c5d-126">Consulte o log de rastreamento para identificar qualquer documento novo cuja indexação de texto completo tenha falhado e remova esse documento.</span><span class="sxs-lookup"><span data-stu-id="18c5d-126">Look at the crawl log to identify any new document that failed to be full-text indexed, and remove it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c5d-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18c5d-127">See Also</span></span>  
 <span data-ttu-id="18c5d-128">[&#41;&#40;Transact-SQL de sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="18c5d-128">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="18c5d-129">[Configurar e gerenciar separadores de palavras e lematizadores para pesquisa](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="18c5d-129">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="18c5d-130">Configurar e gerenciar filtros de pesquisa</span><span class="sxs-lookup"><span data-stu-id="18c5d-130">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
