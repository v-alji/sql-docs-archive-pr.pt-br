---
title: MSSQLSERVER_17083 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17083 (Database Engine error)
ms.assetid: 6c83737d-0531-4fd9-88f6-2da5a150532d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 598cf9b0182178aa13a6d8b965ac10bedaaf5d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581882"
---
# <a name="mssqlserver_17083"></a><span data-ttu-id="f9db8-102">MSSQLSERVER_17083</span><span class="sxs-lookup"><span data-stu-id="f9db8-102">MSSQLSERVER_17083</span></span>
    
## <a name="details"></a><span data-ttu-id="f9db8-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f9db8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f9db8-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="f9db8-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="f9db8-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="f9db8-105">Event ID</span></span>|<span data-ttu-id="f9db8-106">17083</span><span class="sxs-lookup"><span data-stu-id="f9db8-106">17083</span></span>|  
|<span data-ttu-id="f9db8-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="f9db8-107">Event Source</span></span>|<span data-ttu-id="f9db8-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f9db8-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f9db8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f9db8-109">Component</span></span>|<span data-ttu-id="f9db8-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f9db8-110">SQLEngine</span></span>|  
|<span data-ttu-id="f9db8-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="f9db8-111">Symbolic Name</span></span>|<span data-ttu-id="f9db8-112">P3_HEKATON_NOT_ATOMIC</span><span class="sxs-lookup"><span data-stu-id="f9db8-112">P3_HEKATON_NOT_ATOMIC</span></span>|  
|<span data-ttu-id="f9db8-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="f9db8-113">Message Text</span></span>|<span data-ttu-id="f9db8-114">O corpo de um procedimento armazenado originalmente compilado deve ser um bloco ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="f9db8-114">The body of a natively compiled stored procedure must be an ATOMIC block.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f9db8-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="f9db8-115">Explanation</span></span>  
 <span data-ttu-id="f9db8-116">O corpo de um procedimento armazenado originalmente compilado não tinha um bloco ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="f9db8-116">The body of a natively compiled stored procedure did not have an ATOMIC block.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f9db8-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f9db8-117">User Action</span></span>  
 <span data-ttu-id="f9db8-118">Um procedimento armazenado originalmente compilado deve conter um bloco ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="f9db8-118">A natively compiled stored procedure must contain an ATOMIC block.</span></span> <span data-ttu-id="f9db8-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f9db8-119">For example:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="f9db8-120">Para obter mais informações, veja [OLTP in-memory &#40;Otimização na memória&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="f9db8-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9db8-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f9db8-121">See Also</span></span>  
 [<span data-ttu-id="f9db8-122">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="f9db8-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
