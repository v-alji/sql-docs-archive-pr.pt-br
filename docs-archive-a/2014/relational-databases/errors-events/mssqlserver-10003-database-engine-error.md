---
title: MSSQLSERVER_10003 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10003 (Database Engine error)
ms.assetid: 9e2cb199-f077-4d88-8117-1b7550afc696
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ea44fc9591602bfc8279924e10a1803d0d5a87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569548"
---
# <a name="mssqlserver_10003"></a><span data-ttu-id="ebbe5-102">MSSQLSERVER_10003</span><span class="sxs-lookup"><span data-stu-id="ebbe5-102">MSSQLSERVER_10003</span></span>
    
## <a name="details"></a><span data-ttu-id="ebbe5-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ebbe5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ebbe5-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ebbe5-104">Product Name</span></span>|<span data-ttu-id="ebbe5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ebbe5-105">SQL Server</span></span>|  
|<span data-ttu-id="ebbe5-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ebbe5-106">Event ID</span></span>|<span data-ttu-id="ebbe5-107">10003</span><span class="sxs-lookup"><span data-stu-id="ebbe5-107">10003</span></span>|  
|<span data-ttu-id="ebbe5-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ebbe5-108">Event Source</span></span>|<span data-ttu-id="ebbe5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ebbe5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ebbe5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ebbe5-110">Component</span></span>|<span data-ttu-id="ebbe5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ebbe5-111">SQLEngine</span></span>|  
|<span data-ttu-id="ebbe5-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ebbe5-112">Symbolic Name</span></span>|<span data-ttu-id="ebbe5-113">HR_E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ebbe5-113">HR_E_OUTOFMEMORY</span></span>|  
|<span data-ttu-id="ebbe5-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ebbe5-114">Message Text</span></span>|<span data-ttu-id="ebbe5-115">O provedor ficou sem memória.</span><span class="sxs-lookup"><span data-stu-id="ebbe5-115">The provider ran out of memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ebbe5-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="ebbe5-116">Explanation</span></span>  
 <span data-ttu-id="ebbe5-117">A pouca memória do sistema fez com que o provedor do OLE DB ficasse sem memória.</span><span class="sxs-lookup"><span data-stu-id="ebbe5-117">Low system memory has caused the OLE DB provider to run out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ebbe5-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ebbe5-118">User Action</span></span>  
 <span data-ttu-id="ebbe5-119">Reinicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebbe5-119">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ebbe5-120">Se isso não ajudar, reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="ebbe5-120">If that does not help, restart the computer.</span></span> <span data-ttu-id="ebbe5-121">Se o problema persistir, colete eventos de rastreamento OLE DB usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] e forneça esses dados ao suporte do produto do provedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="ebbe5-121">If the problem persists, collect OLE DB trace events using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and provide this data to product support for the OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebbe5-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ebbe5-122">See Also</span></span>  
 <span data-ttu-id="ebbe5-123">[Modelos e permissões do SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="ebbe5-123">[SQL Server Profiler Templates and Permissions](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="ebbe5-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ebbe5-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
