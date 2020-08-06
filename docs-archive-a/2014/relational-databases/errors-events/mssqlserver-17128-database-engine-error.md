---
title: MSSQLSERVER_17128 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17128 (Database Engine error)
ms.assetid: 7b15a5e6-fd41-47ce-ba87-54f72acea4bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e08c668acd0a8b2decb14da338b8d1f1e650de5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679976"
---
# <a name="mssqlserver_17128"></a><span data-ttu-id="d1794-102">MSSQLSERVER_17128</span><span class="sxs-lookup"><span data-stu-id="d1794-102">MSSQLSERVER_17128</span></span>
    
## <a name="details"></a><span data-ttu-id="d1794-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d1794-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1794-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d1794-104">Product Name</span></span>|<span data-ttu-id="d1794-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1794-105">SQL Server</span></span>|  
|<span data-ttu-id="d1794-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d1794-106">Event ID</span></span>|<span data-ttu-id="d1794-107">17128</span><span class="sxs-lookup"><span data-stu-id="d1794-107">17128</span></span>|  
|<span data-ttu-id="d1794-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d1794-108">Event Source</span></span>|<span data-ttu-id="d1794-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d1794-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d1794-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d1794-110">Component</span></span>|<span data-ttu-id="d1794-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d1794-111">SQLEngine</span></span>|  
|<span data-ttu-id="d1794-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d1794-112">Symbolic Name</span></span>|<span data-ttu-id="d1794-113">INIT_NOBUFSPACE</span><span class="sxs-lookup"><span data-stu-id="d1794-113">INIT_NOBUFSPACE</span></span>|  
|<span data-ttu-id="d1794-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d1794-114">Message Text</span></span>|<span data-ttu-id="d1794-115">initdata: sem memória para buffers de kernel.</span><span class="sxs-lookup"><span data-stu-id="d1794-115">initdata: No memory for kernel buffers.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d1794-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="d1794-116">Explanation</span></span>  
 <span data-ttu-id="d1794-117">Falha nas alocações ou reservas de memória iniciais do pool de buffers. O SQL Server foi encerrado.</span><span class="sxs-lookup"><span data-stu-id="d1794-117">The buffer pool's initial memory allocations or reservations have failed, and SQL Server exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1794-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d1794-118">User Action</span></span>  
 <span data-ttu-id="d1794-119">Isso geralmente ocorre ao iniciar o SQL Server em um computador extremamente pequeno (bem menor que os requisitos mínimos do sistema).</span><span class="sxs-lookup"><span data-stu-id="d1794-119">Usually caused by starting SQL Server on an extremely small machine - far smaller than the minimum system requirements.</span></span>  
  
  
