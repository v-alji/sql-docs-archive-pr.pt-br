---
title: MSSQLSERVER_5554 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5554 (Database Engine error)
ms.assetid: 7134bbe5-d240-4a98-85ce-b13cc8ae9b0e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5095a50f257abafb6ebde97bb32c57bc71fc4e09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574723"
---
# <a name="mssqlserver_5554"></a><span data-ttu-id="0215c-102">MSSQLSERVER_5554</span><span class="sxs-lookup"><span data-stu-id="0215c-102">MSSQLSERVER_5554</span></span>
    
## <a name="details"></a><span data-ttu-id="0215c-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0215c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0215c-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="0215c-104">Product Name</span></span>|<span data-ttu-id="0215c-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0215c-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0215c-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="0215c-106">Event ID</span></span>|<span data-ttu-id="0215c-107">5554</span><span class="sxs-lookup"><span data-stu-id="0215c-107">5554</span></span>|  
|<span data-ttu-id="0215c-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="0215c-108">Event Source</span></span>|<span data-ttu-id="0215c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0215c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0215c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0215c-110">Component</span></span>|<span data-ttu-id="0215c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0215c-111">SQLEngine</span></span>|  
|<span data-ttu-id="0215c-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="0215c-112">Symbolic Name</span></span>|<span data-ttu-id="0215c-113">FS_MINIVER_OVERFLOW</span><span class="sxs-lookup"><span data-stu-id="0215c-113">FS_MINIVER_OVERFLOW</span></span>|  
|<span data-ttu-id="0215c-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="0215c-114">Message Text</span></span>|<span data-ttu-id="0215c-115">O número total de versões para um único arquivo atingiu o limite máximo definido pelo sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0215c-115">The total number of versions for a single file has reached the maximum limit set by the file system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0215c-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="0215c-116">Explanation</span></span>  
 <span data-ttu-id="0215c-117">No MARS (conjunto de resultados ativos múltiplos) ou em cenários de gatilho, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa a miniversão especificada pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="0215c-117">In multiple active result sets (MARS) or trigger scenarios, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the miniversion specified by the operating system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0215c-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="0215c-118">User Action</span></span>  
 <span data-ttu-id="0215c-119">Tente evitar atualizações repetidas nos dados da mesma transação.</span><span class="sxs-lookup"><span data-stu-id="0215c-119">Try to avoid repeated updates to the data in the same transaction.</span></span>  
  
  
