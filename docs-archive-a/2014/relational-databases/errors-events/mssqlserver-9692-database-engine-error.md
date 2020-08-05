---
title: MSSQLSERVER_9692 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9692 (Database Engine error)
ms.assetid: 02399d6e-ab5e-4f30-8a3e-2bb1e8c135b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6ba95771aafffa5a322ffa1b7443419936addd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573038"
---
# <a name="mssqlserver_9692"></a><span data-ttu-id="28278-102">MSSQLSERVER_9692</span><span class="sxs-lookup"><span data-stu-id="28278-102">MSSQLSERVER_9692</span></span>
    
## <a name="details"></a><span data-ttu-id="28278-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="28278-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28278-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="28278-104">Product Name</span></span>|<span data-ttu-id="28278-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="28278-105">SQL Server</span></span>|  
|<span data-ttu-id="28278-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="28278-106">Event ID</span></span>|<span data-ttu-id="28278-107">9692</span><span class="sxs-lookup"><span data-stu-id="28278-107">9692</span></span>|  
|<span data-ttu-id="28278-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="28278-108">Event Source</span></span>|<span data-ttu-id="28278-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="28278-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="28278-110">Componente</span><span class="sxs-lookup"><span data-stu-id="28278-110">Component</span></span>|<span data-ttu-id="28278-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="28278-111">SQLEngine</span></span>|  
|<span data-ttu-id="28278-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="28278-112">Symbolic Name</span></span>|<span data-ttu-id="28278-113">SB2_CANT_LISTEN_PORT_IN_USE</span><span class="sxs-lookup"><span data-stu-id="28278-113">SB2_CANT_LISTEN_PORT_IN_USE</span></span>|  
|<span data-ttu-id="28278-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="28278-114">Message Text</span></span>|<span data-ttu-id="28278-115">O protocolo de transporte %S_MSG não pode escutar na porta %d porque ela está em uso por outro processo.</span><span class="sxs-lookup"><span data-stu-id="28278-115">The %S_MSG protocol transport cannot listen on port %d because it is in use by another process.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28278-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="28278-116">Explanation</span></span>  
 <span data-ttu-id="28278-117">Outro programa no computador está usando a porta TCP indicada.</span><span class="sxs-lookup"><span data-stu-id="28278-117">Another program on the computer is using the TCP port indicated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28278-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="28278-118">User Action</span></span>  
 <span data-ttu-id="28278-119">Execute `netstat -aon` para determinar qual programa está usando a porta.</span><span class="sxs-lookup"><span data-stu-id="28278-119">Run `netstat -aon` to determine what program is using the port.</span></span> <span data-ttu-id="28278-120">Desabilite esse aplicativo ou especifique outra porta para o Service Broker.</span><span class="sxs-lookup"><span data-stu-id="28278-120">Disable that application or specify a different port for Service Broker.</span></span>  
  
  
