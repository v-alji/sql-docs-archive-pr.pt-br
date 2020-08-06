---
title: MSSQLSERVER_617 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 617 (Database Engine error)
ms.assetid: 213545d9-08a7-4427-bfd1-8b7e16644281
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88e9feb7c3ac5d8cf646d2243319b2b160b7757e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681655"
---
# <a name="mssqlserver_617"></a><span data-ttu-id="8eb1b-102">MSSQLSERVER_617</span><span class="sxs-lookup"><span data-stu-id="8eb1b-102">MSSQLSERVER_617</span></span>
    
## <a name="details"></a><span data-ttu-id="8eb1b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8eb1b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8eb1b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8eb1b-104">Product Name</span></span>|<span data-ttu-id="8eb1b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8eb1b-105">SQL Server</span></span>|  
|<span data-ttu-id="8eb1b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8eb1b-106">Event ID</span></span>|<span data-ttu-id="8eb1b-107">617</span><span class="sxs-lookup"><span data-stu-id="8eb1b-107">617</span></span>|  
|<span data-ttu-id="8eb1b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8eb1b-108">Event Source</span></span>|<span data-ttu-id="8eb1b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8eb1b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8eb1b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8eb1b-110">Component</span></span>|<span data-ttu-id="8eb1b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8eb1b-111">SQLEngine</span></span>|  
|<span data-ttu-id="8eb1b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8eb1b-112">Symbolic Name</span></span>|<span data-ttu-id="8eb1b-113">NODESHASH</span><span class="sxs-lookup"><span data-stu-id="8eb1b-113">NODESHASH</span></span>|  
|<span data-ttu-id="8eb1b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8eb1b-114">Message Text</span></span>|<span data-ttu-id="8eb1b-115">O descritor da ID de objeto %ld na ID de banco de dados %d não foi encontrado na tabela de hash durante a tentativa de remoção do hash.</span><span class="sxs-lookup"><span data-stu-id="8eb1b-115">Descriptor for object ID %ld in database ID %d not found in the hash table during attempt to unhash it.</span></span> <span data-ttu-id="8eb1b-116">Uma entrada está ausente em uma tabela de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8eb1b-116">A work table is missing an entry.</span></span> <span data-ttu-id="8eb1b-117">Execute a consulta novamente.</span><span class="sxs-lookup"><span data-stu-id="8eb1b-117">Rerun the query.</span></span> <span data-ttu-id="8eb1b-118">Se um cursor estiver envolvido, feche e abra o cursor novamente.</span><span class="sxs-lookup"><span data-stu-id="8eb1b-118">If a cursor is involved, close and reopen the cursor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8eb1b-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="8eb1b-119">Explanation</span></span>  
 <span data-ttu-id="8eb1b-120">O SQL Server não pode localizar a tabela de trabalho da entrada específica.</span><span class="sxs-lookup"><span data-stu-id="8eb1b-120">SQL Server cannot locate the work table for a specific entry.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8eb1b-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8eb1b-121">User Action</span></span>  
  
1.  <span data-ttu-id="8eb1b-122">Se um cursor estiver envolvido, feche e reabra o cursor.</span><span class="sxs-lookup"><span data-stu-id="8eb1b-122">If a cursor is involved, close the cursor and re-open the cursor.</span></span>  
  
2.  <span data-ttu-id="8eb1b-123">Execute a consulta novamente.</span><span class="sxs-lookup"><span data-stu-id="8eb1b-123">Run the query again.</span></span>  
  
  
