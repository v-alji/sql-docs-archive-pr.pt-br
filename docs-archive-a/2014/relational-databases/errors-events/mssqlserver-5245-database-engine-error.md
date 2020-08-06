---
title: MSSQLSERVER_5245 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5245 (Database Engine error)
ms.assetid: 6005c9ec-ccdd-4def-9eb4-37cdb599ddb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f98c831642580587552bf60c604d84c38fffca8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581830"
---
# <a name="mssqlserver_5245"></a><span data-ttu-id="4448b-102">MSSQLSERVER_5245</span><span class="sxs-lookup"><span data-stu-id="4448b-102">MSSQLSERVER_5245</span></span>
    
## <a name="details"></a><span data-ttu-id="4448b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4448b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4448b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="4448b-104">Product Name</span></span>|<span data-ttu-id="4448b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4448b-105">SQL Server</span></span>|  
|<span data-ttu-id="4448b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4448b-106">Event ID</span></span>|<span data-ttu-id="4448b-107">5245</span><span class="sxs-lookup"><span data-stu-id="4448b-107">5245</span></span>|  
|<span data-ttu-id="4448b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="4448b-108">Event Source</span></span>|<span data-ttu-id="4448b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4448b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4448b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4448b-110">Component</span></span>|<span data-ttu-id="4448b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4448b-111">SQLEngine</span></span>|  
|<span data-ttu-id="4448b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="4448b-112">Symbolic Name</span></span>|<span data-ttu-id="4448b-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="4448b-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span></span>|  
|<span data-ttu-id="4448b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="4448b-114">Message Text</span></span>|<span data-ttu-id="4448b-115">ID de objeto O_ID (objeto 'NAME'): o DBCC não pôde obter um bloqueio nesse objeto porque o tempo limite da solicitação de bloqueio foi ultrapassado.</span><span class="sxs-lookup"><span data-stu-id="4448b-115">Object ID O_ID (object 'NAME'): DBCC could not obtain a lock on this object because the lock request time-out period was exceeded.</span></span> <span data-ttu-id="4448b-116">Esse objeto foi ignorado e não será processado.</span><span class="sxs-lookup"><span data-stu-id="4448b-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4448b-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="4448b-117">Explanation</span></span>  
 <span data-ttu-id="4448b-118">O limite de tempo do bloqueio expirou enquanto DBCC estava aguardando um bloqueio de tabela para o objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="4448b-118">A lock time-out occurred while DBCC was waiting on a table lock for the specified object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4448b-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="4448b-119">User Action</span></span>  
 <span data-ttu-id="4448b-120">Execute o comando DBCC novamente.</span><span class="sxs-lookup"><span data-stu-id="4448b-120">Rerun the DBCC command.</span></span>  
  
  
