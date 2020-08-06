---
title: MSSQLSERVER_5231 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5231 (Database Engine error)
ms.assetid: 6954ae84-ed0b-4f4c-9d0a-e73f3d71476c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 68f40ac3a566280526757bd8b83c784954ba3dde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679367"
---
# <a name="mssqlserver_5231"></a><span data-ttu-id="30f5a-102">MSSQLSERVER_5231</span><span class="sxs-lookup"><span data-stu-id="30f5a-102">MSSQLSERVER_5231</span></span>
    
## <a name="details"></a><span data-ttu-id="30f5a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="30f5a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30f5a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="30f5a-104">Product Name</span></span>|<span data-ttu-id="30f5a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="30f5a-105">SQL Server</span></span>|  
|<span data-ttu-id="30f5a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="30f5a-106">Event ID</span></span>|<span data-ttu-id="30f5a-107">5231</span><span class="sxs-lookup"><span data-stu-id="30f5a-107">5231</span></span>|  
|<span data-ttu-id="30f5a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="30f5a-108">Event Source</span></span>|<span data-ttu-id="30f5a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="30f5a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="30f5a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="30f5a-110">Component</span></span>|<span data-ttu-id="30f5a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="30f5a-111">SQLEngine</span></span>|  
|<span data-ttu-id="30f5a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="30f5a-112">Symbolic Name</span></span>|<span data-ttu-id="30f5a-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span><span class="sxs-lookup"><span data-stu-id="30f5a-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span></span>|  
|<span data-ttu-id="30f5a-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="30f5a-114">Message Text</span></span>|<span data-ttu-id="30f5a-115">ID de objeto O_ID (objeto 'NAME'): Ocorreu um deadlock ao tentar bloquear este objeto para verificação.</span><span class="sxs-lookup"><span data-stu-id="30f5a-115">Object ID O_ID (object 'NAME'): A deadlock occurred while trying to lock this object for checking.</span></span> <span data-ttu-id="30f5a-116">Esse objeto foi ignorado e não será processado.</span><span class="sxs-lookup"><span data-stu-id="30f5a-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="30f5a-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="30f5a-117">Explanation</span></span>  
 <span data-ttu-id="30f5a-118">Ocorreu um deadlock quando DBCC estava tentando bloquear o objeto, e DBCC foi escolhido como vítima do deadlock.</span><span class="sxs-lookup"><span data-stu-id="30f5a-118">A deadlock occurred when DBCC was trying to lock the object, and DBCC was chosen as the deadlock victim.</span></span> <span data-ttu-id="30f5a-119">O objeto não será processado.</span><span class="sxs-lookup"><span data-stu-id="30f5a-119">The object will not be processed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="30f5a-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="30f5a-120">User Action</span></span>  
 <span data-ttu-id="30f5a-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="30f5a-121">None</span></span>  
  
  
