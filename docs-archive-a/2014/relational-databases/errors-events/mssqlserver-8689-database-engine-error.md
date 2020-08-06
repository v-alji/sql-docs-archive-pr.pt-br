---
title: MSSQLSERVER_8689 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8689 (Database Engine error)
ms.assetid: 99467a32-6576-4272-a076-b16c06933f2a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdca0a3cd9ce47ccb39ebeaf8fd1cd260aafbd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679960"
---
# <a name="mssqlserver_8689"></a><span data-ttu-id="79362-102">MSSQLSERVER_8689</span><span class="sxs-lookup"><span data-stu-id="79362-102">MSSQLSERVER_8689</span></span>
    
## <a name="details"></a><span data-ttu-id="79362-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="79362-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79362-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="79362-104">Product Name</span></span>|<span data-ttu-id="79362-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="79362-105">SQL Server</span></span>|  
|<span data-ttu-id="79362-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="79362-106">Event ID</span></span>|<span data-ttu-id="79362-107">8689</span><span class="sxs-lookup"><span data-stu-id="79362-107">8689</span></span>|  
|<span data-ttu-id="79362-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="79362-108">Event Source</span></span>|<span data-ttu-id="79362-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="79362-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="79362-110">Componente</span><span class="sxs-lookup"><span data-stu-id="79362-110">Component</span></span>|<span data-ttu-id="79362-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="79362-111">SQLEngine</span></span>|  
|<span data-ttu-id="79362-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="79362-112">Symbolic Name</span></span>|<span data-ttu-id="79362-113">USEPLAN_ERR_NO_DB</span><span class="sxs-lookup"><span data-stu-id="79362-113">USEPLAN_ERR_NO_DB</span></span>|  
|<span data-ttu-id="79362-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="79362-114">Message Text</span></span>|<span data-ttu-id="79362-115">O banco de dados '%.\*ls', especificado na dica USE PLAN, não existe.</span><span class="sxs-lookup"><span data-stu-id="79362-115">Database '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="79362-116">Especifique um banco de dados existente.</span><span class="sxs-lookup"><span data-stu-id="79362-116">Specify an existing database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="79362-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="79362-117">Explanation</span></span>  
 <span data-ttu-id="79362-118">Um banco de dados especificado na dica USE PLAN não existe.</span><span class="sxs-lookup"><span data-stu-id="79362-118">A database that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79362-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="79362-119">User Action</span></span>  
 <span data-ttu-id="79362-120">Verifique se todos os bancos de dados que estão especificados na dica USE PLAN existem.</span><span class="sxs-lookup"><span data-stu-id="79362-120">Ensure all databases that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79362-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79362-121">See Also</span></span>  
 <span data-ttu-id="79362-122">[Dicas de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="79362-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="79362-123">Guias de plano</span><span class="sxs-lookup"><span data-stu-id="79362-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
