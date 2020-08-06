---
title: MSSQLSERVER_7915 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7915 (Database Engine error)
ms.assetid: 63338587-7dd3-40e6-b70e-d8ae18fff47b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1dc7a69023e49b48a10da9f0388cbd72fbe46be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574715"
---
# <a name="mssqlserver_7915"></a><span data-ttu-id="777bf-102">MSSQLSERVER_7915</span><span class="sxs-lookup"><span data-stu-id="777bf-102">MSSQLSERVER_7915</span></span>
    
## <a name="details"></a><span data-ttu-id="777bf-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="777bf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="777bf-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="777bf-104">Product Name</span></span>|<span data-ttu-id="777bf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="777bf-105">SQL Server</span></span>|  
|<span data-ttu-id="777bf-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="777bf-106">Event ID</span></span>|<span data-ttu-id="777bf-107">7915</span><span class="sxs-lookup"><span data-stu-id="777bf-107">7915</span></span>|  
|<span data-ttu-id="777bf-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="777bf-108">Event Source</span></span>|<span data-ttu-id="777bf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="777bf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="777bf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="777bf-110">Component</span></span>|<span data-ttu-id="777bf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="777bf-111">SQLEngine</span></span>|  
|<span data-ttu-id="777bf-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="777bf-112">Symbolic Name</span></span>|<span data-ttu-id="777bf-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span><span class="sxs-lookup"><span data-stu-id="777bf-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span></span>|  
|<span data-ttu-id="777bf-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="777bf-114">Message Text</span></span>|<span data-ttu-id="777bf-115">Reparar: a cadeia IAM relativa à ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE), ficou truncada antes da página P_ID e será recriada.</span><span class="sxs-lookup"><span data-stu-id="777bf-115">Repair: IAM chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), has been truncated before page P_ID and will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="777bf-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="777bf-116">Explanation</span></span>  
 <span data-ttu-id="777bf-117">Essa é uma mensagem informativa enviada pela cláusula REPAIR que indica que foi aplicado um patch à cadeia IAM especificada para que ela pudesse ser reconstruída.</span><span class="sxs-lookup"><span data-stu-id="777bf-117">This is an information message sent by REPAIR that indicates that the specified Index Allocation Map (IAM) chain was patched so that it could be rebuilt.</span></span> <span data-ttu-id="777bf-118">Essa aplicação de patch pode ter exigido a alocação de um novo cabeçalho da cadeia IAM ou a remoção de páginas inválidas da cadeia.</span><span class="sxs-lookup"><span data-stu-id="777bf-118">This patching may have required the allocation of a new head of the IAM chain or the removal of bad pages from the chain.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="777bf-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="777bf-119">User Action</span></span>  
 <span data-ttu-id="777bf-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="777bf-120">None</span></span>  
  
  
