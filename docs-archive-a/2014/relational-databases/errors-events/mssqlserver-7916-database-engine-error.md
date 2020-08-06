---
title: MSSQLSERVER_7916 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7916 (Database Engine error)
ms.assetid: 9bac3536-de14-4e98-84c2-bde9a59ba0d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 21b31eedf61369d9c4d1cfdfd5f53eebd3f5341c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574716"
---
# <a name="mssqlserver_7916"></a><span data-ttu-id="b9118-102">MSSQLSERVER_7916</span><span class="sxs-lookup"><span data-stu-id="b9118-102">MSSQLSERVER_7916</span></span>
    
## <a name="details"></a><span data-ttu-id="b9118-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b9118-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9118-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="b9118-104">Product Name</span></span>|<span data-ttu-id="b9118-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9118-105">SQL Server</span></span>|  
|<span data-ttu-id="b9118-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="b9118-106">Event ID</span></span>|<span data-ttu-id="b9118-107">7916</span><span class="sxs-lookup"><span data-stu-id="b9118-107">7916</span></span>|  
|<span data-ttu-id="b9118-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="b9118-108">Event Source</span></span>|<span data-ttu-id="b9118-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b9118-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b9118-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b9118-110">Component</span></span>|<span data-ttu-id="b9118-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b9118-111">SQLEngine</span></span>|  
|<span data-ttu-id="b9118-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="b9118-112">Symbolic Name</span></span>|<span data-ttu-id="b9118-113">DBCC2_REPAIR_RECORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="b9118-113">DBCC2_REPAIR_RECORD_DELETED</span></span>|  
|<span data-ttu-id="b9118-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="b9118-114">Message Text</span></span>|<span data-ttu-id="b9118-115">Reparar: registro excluído referente a ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE), na página P_ID, slot S_ID.</span><span class="sxs-lookup"><span data-stu-id="b9118-115">Repair: Deleted record for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), on page P_ID, slot S_ID.</span></span> <span data-ttu-id="b9118-116">Os índices serão recriados.</span><span class="sxs-lookup"><span data-stu-id="b9118-116">Indexes will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b9118-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="b9118-117">Explanation</span></span>  
 <span data-ttu-id="b9118-118">Essa é uma mensagem informativa da cláusula REPAIR que indica que o registro especificado foi excluído da página.</span><span class="sxs-lookup"><span data-stu-id="b9118-118">This is an information messages from REPAIR that indicates the specified record was deleted from the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9118-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="b9118-119">User Action</span></span>  
 <span data-ttu-id="b9118-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b9118-120">None</span></span>  
  
  
