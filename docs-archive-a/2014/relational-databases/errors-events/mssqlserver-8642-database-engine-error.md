---
title: MSSQLSERVER_8642 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8642 (Database Engine error)
ms.assetid: fc498059-202f-4d0b-8599-4e784b47c186
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e30296fa569599b91ca74edc7535d330119e1680
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575860"
---
# <a name="mssqlserver_8642"></a><span data-ttu-id="7d59b-102">MSSQLSERVER_8642</span><span class="sxs-lookup"><span data-stu-id="7d59b-102">MSSQLSERVER_8642</span></span>
    
## <a name="details"></a><span data-ttu-id="7d59b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7d59b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d59b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="7d59b-104">Product Name</span></span>|<span data-ttu-id="7d59b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d59b-105">SQL Server</span></span>|  
|<span data-ttu-id="7d59b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="7d59b-106">Event ID</span></span>|<span data-ttu-id="7d59b-107">8642</span><span class="sxs-lookup"><span data-stu-id="7d59b-107">8642</span></span>|  
|<span data-ttu-id="7d59b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="7d59b-108">Event Source</span></span>|<span data-ttu-id="7d59b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7d59b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7d59b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7d59b-110">Component</span></span>|<span data-ttu-id="7d59b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7d59b-111">SQLEngine</span></span>|  
|<span data-ttu-id="7d59b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="7d59b-112">Symbolic Name</span></span>|<span data-ttu-id="7d59b-113">EXCHNGSTART_ERR</span><span class="sxs-lookup"><span data-stu-id="7d59b-113">EXCHNGSTART_ERR</span></span>|  
|<span data-ttu-id="7d59b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="7d59b-114">Message Text</span></span>|<span data-ttu-id="7d59b-115">O processador de consultas não pôde iniciar os recursos de threads necessários para execução paralela da consulta.</span><span class="sxs-lookup"><span data-stu-id="7d59b-115">The query processor could not start the necessary thread resources for parallel query execution.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d59b-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="7d59b-116">Explanation</span></span>  
 <span data-ttu-id="7d59b-117">O servidor não dispõe de recursos de thread suficientes.</span><span class="sxs-lookup"><span data-stu-id="7d59b-117">Thread resources are low in the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d59b-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="7d59b-118">User Action</span></span>  
 <span data-ttu-id="7d59b-119">Reduza a carga no servidor e execute a consulta novamente.</span><span class="sxs-lookup"><span data-stu-id="7d59b-119">Reduce load on the server, and run the query again.</span></span>  
  
  
