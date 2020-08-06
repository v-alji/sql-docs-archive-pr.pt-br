---
title: MSSQLSERVER_10521 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10521 (Database Engine error)
ms.assetid: ba2d7e44-207c-4428-b5f0-c975ac122c0d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c034bd13e212b9b39bfd348353d59e23fc748079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680469"
---
# <a name="mssqlserver_10521"></a><span data-ttu-id="2c5a7-102">MSSQLSERVER_10521</span><span class="sxs-lookup"><span data-stu-id="2c5a7-102">MSSQLSERVER_10521</span></span>
    
## <a name="details"></a><span data-ttu-id="2c5a7-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2c5a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c5a7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2c5a7-104">Product Name</span></span>|<span data-ttu-id="2c5a7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c5a7-105">SQL Server</span></span>|  
|<span data-ttu-id="2c5a7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2c5a7-106">Event ID</span></span>|<span data-ttu-id="2c5a7-107">10521</span><span class="sxs-lookup"><span data-stu-id="2c5a7-107">10521</span></span>|  
|<span data-ttu-id="2c5a7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2c5a7-108">Event Source</span></span>|<span data-ttu-id="2c5a7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2c5a7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2c5a7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2c5a7-110">Component</span></span>|<span data-ttu-id="2c5a7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2c5a7-111">SQLEngine</span></span>|  
|<span data-ttu-id="2c5a7-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2c5a7-112">Symbolic Name</span></span>|<span data-ttu-id="2c5a7-113">PG_PARAM_NEEDED</span><span class="sxs-lookup"><span data-stu-id="2c5a7-113">PG_PARAM_NEEDED</span></span>|  
|<span data-ttu-id="2c5a7-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2c5a7-114">Message Text</span></span>|<span data-ttu-id="2c5a7-115">Não é possível criar o guia de plano '%.\*ls' porque `@type` foi especificado como '%ls' e o parâmetro '%ls' é NULL.</span><span class="sxs-lookup"><span data-stu-id="2c5a7-115">Cannot create plan guide '%.\*ls' because `@type` was specified as '%ls' and the parameter '%ls' is NULL.</span></span> <span data-ttu-id="2c5a7-116">Esse tipo requer um valor não NULL para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2c5a7-116">This type requires a non-NULL value for the parameter.</span></span> <span data-ttu-id="2c5a7-117">Especifique um valor não NULL para o parâmetro ou altere o tipo para um que permita um valor NULL para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2c5a7-117">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2c5a7-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="2c5a7-118">Explanation</span></span>  
 <span data-ttu-id="2c5a7-119">O tipo especificado em `@type` requer um valor não NULL para o parâmetro especificado; entretanto, foi fornecido um valor NULL.</span><span class="sxs-lookup"><span data-stu-id="2c5a7-119">The type specified in `@type` requires a non-NULL value for the specified parameter; however a NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2c5a7-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2c5a7-120">User Action</span></span>  
 <span data-ttu-id="2c5a7-121">Especifique um valor não NULL para o parâmetro ou altere o tipo para um que permita um valor NULL para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2c5a7-121">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c5a7-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c5a7-122">See Also</span></span>  
 <span data-ttu-id="2c5a7-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2c5a7-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="2c5a7-124">[Guias de plano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="2c5a7-124">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="2c5a7-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2c5a7-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
