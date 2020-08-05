---
title: MSSQLSERVER_2518 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2518 (Database Engine error)
ms.assetid: 54a13abc-4c33-43f0-b55d-e2e74a1381c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5f5517458c1014d7830c4813b95e1120bef452e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572091"
---
# <a name="mssqlserver_2518"></a><span data-ttu-id="9417f-102">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="9417f-102">MSSQLSERVER_2518</span></span>
    
## <a name="details"></a><span data-ttu-id="9417f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9417f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9417f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9417f-104">Product Name</span></span>|<span data-ttu-id="9417f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9417f-105">SQL Server</span></span>|  
|<span data-ttu-id="9417f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9417f-106">Event ID</span></span>|<span data-ttu-id="9417f-107">2518</span><span class="sxs-lookup"><span data-stu-id="9417f-107">2518</span></span>|  
|<span data-ttu-id="9417f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9417f-108">Event Source</span></span>|<span data-ttu-id="9417f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9417f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9417f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9417f-110">Component</span></span>|<span data-ttu-id="9417f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9417f-111">SQLEngine</span></span>|  
|<span data-ttu-id="9417f-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9417f-112">Symbolic Name</span></span>|<span data-ttu-id="9417f-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span><span class="sxs-lookup"><span data-stu-id="9417f-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span></span>|  
|<span data-ttu-id="9417f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9417f-114">Message Text</span></span>|<span data-ttu-id="9417f-115">ID de Objeto O_ID (objeto "O_NAME"): colunas computadas e tipos definidos pelo usuário não podem ser verificados quanto a este objeto porque o CLR (Common Language Runtime) está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="9417f-115">Object ID O_ID (object "O_NAME"): Computed columns and user-defined types cannot be checked for this object because the common language runtime (CLR) is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9417f-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="9417f-116">Explanation</span></span>  
 <span data-ttu-id="9417f-117">Essa mensagem informativa indica que o processador de consultas não pôde fornecer para DBCC um objeto interno que permita a avaliação de colunas computadas e de tipos CLR definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9417f-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for computed columns and common language runtime (CLR) user-defined types to be evaluated.</span></span> <span data-ttu-id="9417f-118">Esse problema ocorreu porque uma das colunas envolvia o CLR, mas ele não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="9417f-118">This problem occurred because one of the columns involved the CLR, but the CLR is not enabled.</span></span> <span data-ttu-id="9417f-119">O objeto interno abrange todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="9417f-119">The internal object covers all columns.</span></span> <span data-ttu-id="9417f-120">Por isso, a incapacidade de avaliar uma única coluna impede a criação do objeto interno.</span><span class="sxs-lookup"><span data-stu-id="9417f-120">Therefore, the inability to evaluate a single column prevents creating the internal object.</span></span> <span data-ttu-id="9417f-121">Isso significa que as colunas computadas não serão verificadas quanto à correção ou que não serão usadas quando DBCC verificar a consistência entre índices e tabelas base.</span><span class="sxs-lookup"><span data-stu-id="9417f-121">This means that computed columns will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9417f-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9417f-122">User Action</span></span>  
 <span data-ttu-id="9417f-123">Habilite o CLR e execute a instrução DBCC novamente.</span><span class="sxs-lookup"><span data-stu-id="9417f-123">Enable CLR and rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9417f-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9417f-124">See Also</span></span>  
 [<span data-ttu-id="9417f-125">Habilitando a integração CLR</span><span class="sxs-lookup"><span data-stu-id="9417f-125">Enabling CLR Integration</span></span>](../clr-integration/clr-integration-enabling.md)  
  
  
