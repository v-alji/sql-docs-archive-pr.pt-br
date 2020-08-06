---
title: MSSQLSERVER_17803 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17803 (Database Engine error)
ms.assetid: 28591a19-258d-4891-b78a-4686789bb2d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be63b3d05bff2ebf90122f66af4297d77376fce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581876"
---
# <a name="mssqlserver_17803"></a><span data-ttu-id="a89a6-102">MSSQLSERVER_17803</span><span class="sxs-lookup"><span data-stu-id="a89a6-102">MSSQLSERVER_17803</span></span>
    
## <a name="details"></a><span data-ttu-id="a89a6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a89a6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a89a6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a89a6-104">Product Name</span></span>|<span data-ttu-id="a89a6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a89a6-105">SQL Server</span></span>|  
|<span data-ttu-id="a89a6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a89a6-106">Event ID</span></span>|<span data-ttu-id="a89a6-107">17803</span><span class="sxs-lookup"><span data-stu-id="a89a6-107">17803</span></span>|  
|<span data-ttu-id="a89a6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a89a6-108">Event Source</span></span>|<span data-ttu-id="a89a6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a89a6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a89a6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a89a6-110">Component</span></span>|<span data-ttu-id="a89a6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a89a6-111">SQLEngine</span></span>|  
|<span data-ttu-id="a89a6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a89a6-112">Symbolic Name</span></span>|<span data-ttu-id="a89a6-113">SRV_NOMEMORY</span><span class="sxs-lookup"><span data-stu-id="a89a6-113">SRV_NOMEMORY</span></span>|  
|<span data-ttu-id="a89a6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a89a6-114">Message Text</span></span>|<span data-ttu-id="a89a6-115">Ocorreu uma falha de alocação de memória ao estabelecer conexão.</span><span class="sxs-lookup"><span data-stu-id="a89a6-115">There was a memory allocation failure during connection establishment.</span></span> <span data-ttu-id="a89a6-116">Reduce nonessential memory load, or increase system memory.</span><span class="sxs-lookup"><span data-stu-id="a89a6-116">Reduce nonessential memory load, or increase system memory.</span></span> <span data-ttu-id="a89a6-117">A conexão foi fechada.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="a89a6-117">The connection has been closed.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a89a6-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="a89a6-118">Explanation</span></span>  
 <span data-ttu-id="a89a6-119">O servidor está sendo executado sem memória.</span><span class="sxs-lookup"><span data-stu-id="a89a6-119">Server is running out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a89a6-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a89a6-120">User Action</span></span>  
 <span data-ttu-id="a89a6-121">Determine o motivo pelo qual o servidor está sendo executado sem memória.</span><span class="sxs-lookup"><span data-stu-id="a89a6-121">Determine the cause for server running out of memory.</span></span> <span data-ttu-id="a89a6-122">Etapas genéricas para a solução de problemas de memória podem ser úteis</span><span class="sxs-lookup"><span data-stu-id="a89a6-122">Generic memory troubleshooting steps may be useful</span></span>  
  
  
