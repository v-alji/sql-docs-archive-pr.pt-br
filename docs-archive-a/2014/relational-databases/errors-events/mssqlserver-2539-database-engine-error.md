---
title: MSSQLSERVER_2539 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2539 (Database Engine error)
ms.assetid: e638efcc-56f4-40f9-9740-17ef67b47d79
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9f061d2a827dca641bfc0c348af1328fd71856fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581857"
---
# <a name="mssqlserver_2539"></a><span data-ttu-id="aa4e8-102">MSSQLSERVER_2539</span><span class="sxs-lookup"><span data-stu-id="aa4e8-102">MSSQLSERVER_2539</span></span>
    
## <a name="details"></a><span data-ttu-id="aa4e8-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="aa4e8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa4e8-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="aa4e8-104">Product Name</span></span>|<span data-ttu-id="aa4e8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa4e8-105">SQL Server</span></span>|  
|<span data-ttu-id="aa4e8-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="aa4e8-106">Event ID</span></span>|<span data-ttu-id="aa4e8-107">2539</span><span class="sxs-lookup"><span data-stu-id="aa4e8-107">2539</span></span>|  
|<span data-ttu-id="aa4e8-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="aa4e8-108">Event Source</span></span>|<span data-ttu-id="aa4e8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa4e8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa4e8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="aa4e8-110">Component</span></span>|<span data-ttu-id="aa4e8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aa4e8-111">SQLEngine</span></span>|  
|<span data-ttu-id="aa4e8-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="aa4e8-112">Symbolic Name</span></span>|<span data-ttu-id="aa4e8-113">DBCC_ALLOCATION_SUMMARY_FOR_DATABASE</span><span class="sxs-lookup"><span data-stu-id="aa4e8-113">DBCC_ALLOCATION_SUMMARY_FOR_DATABASE</span></span>|  
|<span data-ttu-id="aa4e8-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="aa4e8-114">Message Text</span></span>|<span data-ttu-id="aa4e8-115">O número total de extensões = EXTENTS, páginas usadas = USED_PAGES, páginas reservadas = RESERVED_PAGES neste banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aa4e8-115">Total number of extents = EXTENTS, used pages = USED_PAGES, reserved pages = RESERVED_PAGES in this database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa4e8-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="aa4e8-116">Explanation</span></span>  
 <span data-ttu-id="aa4e8-117">Essas informações fazem parte da saída do comando DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="aa4e8-117">This information is part of the output from the DBCC CHECKALLOC command.</span></span> <span data-ttu-id="aa4e8-118">Elas são um resumo de extensões alocadas, páginas usadas e páginas reservadas para o banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="aa4e8-118">This information is the summary of allocated extents, used pages, and reserved pages for the specified database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa4e8-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="aa4e8-119">User Action</span></span>  
 <span data-ttu-id="aa4e8-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa4e8-120">None</span></span>  
  
  
