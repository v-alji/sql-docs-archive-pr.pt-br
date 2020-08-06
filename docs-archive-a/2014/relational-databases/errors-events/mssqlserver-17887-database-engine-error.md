---
title: MSSQLSERVER_17887 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17887 (Database Engine error)
ms.assetid: ad0806e6-3296-4c32-b103-fccf0f8a8d3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 006e616d80ef7e8d083f60675b02b4e6a4e8dc24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569540"
---
# <a name="mssqlserver_17887"></a><span data-ttu-id="92e0b-102">MSSQLSERVER_17887</span><span class="sxs-lookup"><span data-stu-id="92e0b-102">MSSQLSERVER_17887</span></span>
    
## <a name="details"></a><span data-ttu-id="92e0b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="92e0b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92e0b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="92e0b-104">Product Name</span></span>|<span data-ttu-id="92e0b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="92e0b-105">SQL Server</span></span>|  
|<span data-ttu-id="92e0b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="92e0b-106">Event ID</span></span>|<span data-ttu-id="92e0b-107">17887</span><span class="sxs-lookup"><span data-stu-id="92e0b-107">17887</span></span>|  
|<span data-ttu-id="92e0b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="92e0b-108">Event Source</span></span>|<span data-ttu-id="92e0b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="92e0b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="92e0b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="92e0b-110">Component</span></span>|<span data-ttu-id="92e0b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="92e0b-111">SQLEngine</span></span>|  
|<span data-ttu-id="92e0b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="92e0b-112">Symbolic Name</span></span>|<span data-ttu-id="92e0b-113">SRV_IO_COMP_LISTENER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="92e0b-113">SRV_IO_COMP_LISTENER_NONYIELDING</span></span>|  
|<span data-ttu-id="92e0b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="92e0b-114">Message Text</span></span>|<span data-ttu-id="92e0b-115">Ouvinte de Conclusão de E/S (0x%lx) Trabalho 0x%p parece não estar respondendo no Nó %ld.</span><span class="sxs-lookup"><span data-stu-id="92e0b-115">IO Completion Listener (0x%lx) Worker 0x%p appears to be non-yielding on Node %ld.</span></span> <span data-ttu-id="92e0b-116">Quant. aprox. de CPU usada: kernel %I64d ms, usuário %I64d ms, Intervalo: %I64d.</span><span class="sxs-lookup"><span data-stu-id="92e0b-116">Approx CPU Used: kernel %I64d ms, user %I64d ms, Interval: %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="92e0b-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="92e0b-117">Explanation</span></span>  
 <span data-ttu-id="92e0b-118">Indica que há um problema possível com o Ouvinte de Porta de Conclusão de E/S no nó especificado ao executar a rotina de Conclusão de E/S para um evento de leitura/gravação de rede.</span><span class="sxs-lookup"><span data-stu-id="92e0b-118">Indicates that there is a possible problem with the I/O Completion Port Listener on the specified node when executing the I/O Completion routine for a network read/write event.</span></span> <span data-ttu-id="92e0b-119">Este erro será removido quando o Ouvinte de Porta de Conclusão de E/S retornar da execução da rotina de Conclusão de E/S.</span><span class="sxs-lookup"><span data-stu-id="92e0b-119">This error will go away when the I/O Completion Port Listener returns from executing the I/O Completion routine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="92e0b-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="92e0b-120">User Action</span></span>  
 <span data-ttu-id="92e0b-121">Contate os Serviços de Atendimento ao Cliente da Microsoft (CSS).</span><span class="sxs-lookup"><span data-stu-id="92e0b-121">Contact Microsoft Customer Support Services (CSS).</span></span>  
  
  
