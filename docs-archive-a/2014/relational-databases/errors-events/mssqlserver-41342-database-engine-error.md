---
title: MSSQLSERVER_41342 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41342 (Database Engine error)
ms.assetid: 28270d98-c543-4e7d-b40c-2200e38dce1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c0269322b30cee88e5ba3d50b6d391464b735f54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575877"
---
# <a name="mssqlserver_41342"></a><span data-ttu-id="8f4a6-102">MSSQLSERVER_41342</span><span class="sxs-lookup"><span data-stu-id="8f4a6-102">MSSQLSERVER_41342</span></span>
    
## <a name="details"></a><span data-ttu-id="8f4a6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8f4a6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f4a6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8f4a6-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8f4a6-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8f4a6-105">Event ID</span></span>|<span data-ttu-id="8f4a6-106">41342</span><span class="sxs-lookup"><span data-stu-id="8f4a6-106">41342</span></span>|  
|<span data-ttu-id="8f4a6-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8f4a6-107">Event Source</span></span>|<span data-ttu-id="8f4a6-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8f4a6-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8f4a6-109">Componente</span><span class="sxs-lookup"><span data-stu-id="8f4a6-109">Component</span></span>|<span data-ttu-id="8f4a6-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8f4a6-110">SQLEngine</span></span>|  
|<span data-ttu-id="8f4a6-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8f4a6-111">Symbolic Name</span></span>|<span data-ttu-id="8f4a6-112">HK_HW_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="8f4a6-112">HK_HW_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="8f4a6-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8f4a6-113">Message Text</span></span>|<span data-ttu-id="8f4a6-114">O modelo do processador no sistema não dá suporte à criação de *construct*.</span><span class="sxs-lookup"><span data-stu-id="8f4a6-114">The model of the processor on the system does not support creating *construct*.</span></span> <span data-ttu-id="8f4a6-115">Esse erro normalmente ocorre com processadores mais antigos.</span><span class="sxs-lookup"><span data-stu-id="8f4a6-115">This error typically occurs with older processors.</span></span> <span data-ttu-id="8f4a6-116">Consulte os Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para obter informações sobre modelos com suporte.</span><span class="sxs-lookup"><span data-stu-id="8f4a6-116">See [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for information on supported models.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8f4a6-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="8f4a6-117">Explanation</span></span>  
 <span data-ttu-id="8f4a6-118">As tabelas com otimização de memória exigem um modelo de processador que dá suporte a operações atômicas de comparar-e-trocar em valores de 128 bits, que exigem instrução de assembly CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="8f4a6-118">Memory-optimized tables require a processor model that supports atomic compare-and-exchange operations on 128-bit values, which require the assembly instruction CMPXCHG16B.</span></span> <span data-ttu-id="8f4a6-119">Alguns modelos mais antigos de processadores AMD não dão suporte à instrução CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="8f4a6-119">Certain older AMD processor models do not support the CMPXCHG16B instruction.</span></span> <span data-ttu-id="8f4a6-120">Além disso, alguns ambientes de virtualização não habilitam essa instrução por padrão.</span><span class="sxs-lookup"><span data-stu-id="8f4a6-120">Also, certain virtualization environments do not enable this instruction by default.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f4a6-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8f4a6-121">User Action</span></span>  
 <span data-ttu-id="8f4a6-122">Atualize o processador.</span><span class="sxs-lookup"><span data-stu-id="8f4a6-122">Upgrade your processor.</span></span> <span data-ttu-id="8f4a6-123">Se o processador der suporte à instrução e você estiver executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em uma máquina virtual, altere a configuração para dar suporte à instrução CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="8f4a6-123">If your processor supports the instruction and you are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a virtual machine, change the configuration to support the instruction CMPXCHG16B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4a6-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f4a6-124">See Also</span></span>  
 [<span data-ttu-id="8f4a6-125">OLTP in-memory &#40;Otimização na memória&#41;</span><span class="sxs-lookup"><span data-stu-id="8f4a6-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
