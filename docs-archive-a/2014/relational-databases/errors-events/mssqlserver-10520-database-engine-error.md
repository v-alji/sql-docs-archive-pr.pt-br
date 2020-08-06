---
title: MSSQLSERVER_10520 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b8bdf080703fa6bd02fc34b8c31f59407814b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680471"
---
# <a name="mssqlserver_10520"></a><span data-ttu-id="8dd1c-102">MSSQLSERVER_10520</span><span class="sxs-lookup"><span data-stu-id="8dd1c-102">MSSQLSERVER_10520</span></span>
    
## <a name="details"></a><span data-ttu-id="8dd1c-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8dd1c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8dd1c-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8dd1c-104">Product Name</span></span>|<span data-ttu-id="8dd1c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8dd1c-105">SQL Server</span></span>|  
|<span data-ttu-id="8dd1c-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8dd1c-106">Event ID</span></span>|<span data-ttu-id="8dd1c-107">10520</span><span class="sxs-lookup"><span data-stu-id="8dd1c-107">10520</span></span>|  
|<span data-ttu-id="8dd1c-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8dd1c-108">Event Source</span></span>|<span data-ttu-id="8dd1c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8dd1c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8dd1c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8dd1c-110">Component</span></span>|<span data-ttu-id="8dd1c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8dd1c-111">SQLEngine</span></span>|  
|<span data-ttu-id="8dd1c-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8dd1c-112">Symbolic Name</span></span>|<span data-ttu-id="8dd1c-113">PG_PARAM_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="8dd1c-113">PG_PARAM_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="8dd1c-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8dd1c-114">Message Text</span></span>|<span data-ttu-id="8dd1c-115">Não é possível criar o guia de plano '%.\*ls' porque @type foi especificado como '%ls' e um valor não NULL está especificado para o parâmetro '%ls'.</span><span class="sxs-lookup"><span data-stu-id="8dd1c-115">Cannot create plan guide '%.\*ls' because @type was specified as '%ls' and a non-NULL value is specified for the parameter '%ls'.</span></span> <span data-ttu-id="8dd1c-116">Esse tipo requer um valor NULL para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8dd1c-116">This type requires a NULL value for the parameter.</span></span> <span data-ttu-id="8dd1c-117">Especifique um valor NULL para o parâmetro ou altere o tipo para um que permita um valor não NULL para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8dd1c-117">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8dd1c-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="8dd1c-118">Explanation</span></span>  
 <span data-ttu-id="8dd1c-119">O tipo especificado em @type exige um valor NULL para o parâmetro especificado; entretanto, foi fornecido um valor não NULL.</span><span class="sxs-lookup"><span data-stu-id="8dd1c-119">The type specified in @type requires a NULL value for the specified parameter, however a non-NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8dd1c-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8dd1c-120">User Action</span></span>  
 <span data-ttu-id="8dd1c-121">Especifique um valor NULL para o parâmetro ou altere o tipo para um que permita um valor não NULL para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8dd1c-121">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dd1c-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8dd1c-122">See Also</span></span>  
 <span data-ttu-id="8dd1c-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dd1c-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="8dd1c-124">Guias de plano</span><span class="sxs-lookup"><span data-stu-id="8dd1c-124">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
