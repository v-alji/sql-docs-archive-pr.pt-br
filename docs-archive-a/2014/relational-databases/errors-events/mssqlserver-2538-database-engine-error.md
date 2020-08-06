---
title: MSSQLSERVER_2538 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2538 (Database Engine error)
ms.assetid: 0a0f7d79-f1ba-4749-8804-fb660cca3492
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9f4ae886a6fd0abee2f7aa22c6a234c0a6c2d040
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581858"
---
# <a name="mssqlserver_2538"></a><span data-ttu-id="93469-102">MSSQLSERVER_2538</span><span class="sxs-lookup"><span data-stu-id="93469-102">MSSQLSERVER_2538</span></span>
    
## <a name="details"></a><span data-ttu-id="93469-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="93469-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93469-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="93469-104">Product Name</span></span>|<span data-ttu-id="93469-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="93469-105">SQL Server</span></span>|  
|<span data-ttu-id="93469-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="93469-106">Event ID</span></span>|<span data-ttu-id="93469-107">2538</span><span class="sxs-lookup"><span data-stu-id="93469-107">2538</span></span>|  
|<span data-ttu-id="93469-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="93469-108">Event Source</span></span>|<span data-ttu-id="93469-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="93469-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="93469-110">Componente</span><span class="sxs-lookup"><span data-stu-id="93469-110">Component</span></span>|<span data-ttu-id="93469-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="93469-111">SQLEngine</span></span>|  
|<span data-ttu-id="93469-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="93469-112">Symbolic Name</span></span>|<span data-ttu-id="93469-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span><span class="sxs-lookup"><span data-stu-id="93469-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span></span>|  
|<span data-ttu-id="93469-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="93469-114">Message Text</span></span>|<span data-ttu-id="93469-115">Arquivo FILE:</span><span class="sxs-lookup"><span data-stu-id="93469-115">File FILE.</span></span> <span data-ttu-id="93469-116">Número de extensões = EXTENTS, páginas usadas = USED_PAGES, páginas reservadas = RESERVED_PAGES.</span><span class="sxs-lookup"><span data-stu-id="93469-116">Number of extents = EXTENTS, used pages = USED_PAGES, reserved pages = RESERVED_PAGES.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="93469-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="93469-117">Explanation</span></span>  
 <span data-ttu-id="93469-118">Essas informações fazem parte da saída do comando DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="93469-118">This information is part of the output from the DBCC CHECKALLOC command.</span></span> <span data-ttu-id="93469-119">Elas são um resumo por arquivo de extensões alocadas, páginas usadas e páginas reservadas para o banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="93469-119">This information is the per-file summary of allocated extents, used pages, and reserved pages for the specified database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="93469-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="93469-120">User Action</span></span>  
 <span data-ttu-id="93469-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="93469-121">None</span></span>  
  
  
