---
title: MSSQLSERVER_7308 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7308 (Database Engine error)
- single-threaded apartment mode
ms.assetid: cca9eab9-afb9-463d-abfd-0802257e2c99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9978f35ebe41eeda1470220772f87e83ab1ad942
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574020"
---
# <a name="mssqlserver_7308"></a><span data-ttu-id="59e11-102">MSSQLSERVER_7308</span><span class="sxs-lookup"><span data-stu-id="59e11-102">MSSQLSERVER_7308</span></span>
    
## <a name="details"></a><span data-ttu-id="59e11-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="59e11-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59e11-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="59e11-104">Product Name</span></span>|<span data-ttu-id="59e11-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="59e11-105">SQL Server</span></span>|  
|<span data-ttu-id="59e11-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="59e11-106">Event ID</span></span>|<span data-ttu-id="59e11-107">7308</span><span class="sxs-lookup"><span data-stu-id="59e11-107">7308</span></span>|  
|<span data-ttu-id="59e11-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="59e11-108">Event Source</span></span>|<span data-ttu-id="59e11-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="59e11-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="59e11-110">Componente</span><span class="sxs-lookup"><span data-stu-id="59e11-110">Component</span></span>|<span data-ttu-id="59e11-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="59e11-111">SQLEngine</span></span>|  
|<span data-ttu-id="59e11-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="59e11-112">Symbolic Name</span></span>|<span data-ttu-id="59e11-113">RMT_STA_DISABLED</span><span class="sxs-lookup"><span data-stu-id="59e11-113">RMT_STA_DISABLED</span></span>|  
|<span data-ttu-id="59e11-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="59e11-114">Message Text</span></span>|<span data-ttu-id="59e11-115">Não é possível usar o provedor OLE DB '%ls' para consultas distribuídas porque ele está configurado para execução no modo STA.</span><span class="sxs-lookup"><span data-stu-id="59e11-115">OLE DB provider '%ls' cannot be used for distributed queries because the provider is configured to run in single-threaded apartment mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="59e11-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="59e11-116">Explanation</span></span>  
 <span data-ttu-id="59e11-117">Você usou um provedor OLE DB configurado para execução no modo STA.</span><span class="sxs-lookup"><span data-stu-id="59e11-117">You have used an OLE DB provider that is configured to run in single-threaded apartment (STA) mode.</span></span> <span data-ttu-id="59e11-118">Provedores do OLE DB executados no modo STA não podem ser usados para consultas distribuídas.</span><span class="sxs-lookup"><span data-stu-id="59e11-118">OLE DB providers that run in single-threaded apartment (STA) mode cannot be used for distributed queries.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="59e11-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="59e11-119">User Action</span></span>  
 <span data-ttu-id="59e11-120">Para resolver o erro, configure o provedor para execução no modo MTA.</span><span class="sxs-lookup"><span data-stu-id="59e11-120">To resolve this error, configure the provider to run in multithreaded apartment (MTA) mode.</span></span> <span data-ttu-id="59e11-121">Se o provedor não tiver suporte para MTA e não for possível atualizá-lo para uma versão com suporte a MTA, considere configurá-lo para execução fora do processo.</span><span class="sxs-lookup"><span data-stu-id="59e11-121">If the provider does not support MTA, and the provider cannot be upgraded to a version that supports MTA, consider configuring the provider to run out-of-process.</span></span> <span data-ttu-id="59e11-122">O fornecedor do provedor deverá ser capaz de informar se o provedor dá suporte para MTA ou execução fora do processo.</span><span class="sxs-lookup"><span data-stu-id="59e11-122">The provider vendor should be able to tell you if the provider supports MTA or running out-of-process.</span></span>  
  
  
