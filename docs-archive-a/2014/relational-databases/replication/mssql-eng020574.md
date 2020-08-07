---
title: MSSQL_ENG020574 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG02574 error
ms.assetid: 4e98f8de-287c-4090-81ee-dc8f80dfa6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e224e9a87d40fa826a05c669216649c45185037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583532"
---
# <a name="mssql_eng020574"></a><span data-ttu-id="67d51-102">MSSQL_ENG020574</span><span class="sxs-lookup"><span data-stu-id="67d51-102">MSSQL_ENG020574</span></span>
    
## <a name="message-details"></a><span data-ttu-id="67d51-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="67d51-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67d51-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="67d51-104">Product Name</span></span>|<span data-ttu-id="67d51-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="67d51-105">SQL Server</span></span>|  
|<span data-ttu-id="67d51-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="67d51-106">Event ID</span></span>|<span data-ttu-id="67d51-107">20574</span><span class="sxs-lookup"><span data-stu-id="67d51-107">20574</span></span>|  
|<span data-ttu-id="67d51-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="67d51-108">Event Source</span></span>|<span data-ttu-id="67d51-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="67d51-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="67d51-110">Componente</span><span class="sxs-lookup"><span data-stu-id="67d51-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="67d51-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="67d51-111">Symbolic Name</span></span>||  
|<span data-ttu-id="67d51-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="67d51-112">Message Text</span></span>|<span data-ttu-id="67d51-113">Falha na validação de dados na assinatura do assinante '%s' para o artigo '%s' na publicação '%s'.</span><span class="sxs-lookup"><span data-stu-id="67d51-113">Subscriber '%s' subscription to article '%s' in publication '%s' failed data validation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67d51-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="67d51-114">Explanation</span></span>  
 <span data-ttu-id="67d51-115">Os dados no Assinante foram validados de acordo com os dados no Publicador, e os dados não corresponderam, portanto, houve falha na validação.</span><span class="sxs-lookup"><span data-stu-id="67d51-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="67d51-116">Para obter mais informações sobre validação, consulte [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="67d51-116">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67d51-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="67d51-117">User Action</span></span>  
 <span data-ttu-id="67d51-118">Recomendamos que você faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="67d51-118">We recommend that you do the following:</span></span>  
  
-   <span data-ttu-id="67d51-119">Determine por que a validação falhou.</span><span class="sxs-lookup"><span data-stu-id="67d51-119">Determine why validation failed.</span></span>  
  
-   <span data-ttu-id="67d51-120">Corrija o problema que realmente causou a falha.</span><span class="sxs-lookup"><span data-stu-id="67d51-120">Correct the underlying issue that caused the failure.</span></span>  
  
-   <span data-ttu-id="67d51-121">Torne os dados convergentes reiniciando a assinatura ou através de qualquer outro método.</span><span class="sxs-lookup"><span data-stu-id="67d51-121">Bring the data into convergence by reinitializing the subscription or through another method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d51-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67d51-122">See Also</span></span>  
 [<span data-ttu-id="67d51-123">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="67d51-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
