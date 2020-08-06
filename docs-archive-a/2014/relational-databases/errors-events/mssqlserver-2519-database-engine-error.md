---
title: MSSQLSERVER_2519 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2519 (Database Engine error)
ms.assetid: 8dc6ad98-5db8-4c88-8dea-6d455e63b839
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8577b07586553f4b03714cd31451ac755faf824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569533"
---
# <a name="mssqlserver_2519"></a><span data-ttu-id="ee0d3-102">MSSQLSERVER_2519</span><span class="sxs-lookup"><span data-stu-id="ee0d3-102">MSSQLSERVER_2519</span></span>
    
## <a name="details"></a><span data-ttu-id="ee0d3-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ee0d3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee0d3-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ee0d3-104">Product Name</span></span>|<span data-ttu-id="ee0d3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ee0d3-105">SQL Server</span></span>|  
|<span data-ttu-id="ee0d3-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ee0d3-106">Event ID</span></span>|<span data-ttu-id="ee0d3-107">2519</span><span class="sxs-lookup"><span data-stu-id="ee0d3-107">2519</span></span>|  
|<span data-ttu-id="ee0d3-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ee0d3-108">Event Source</span></span>|<span data-ttu-id="ee0d3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ee0d3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ee0d3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ee0d3-110">Component</span></span>|<span data-ttu-id="ee0d3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ee0d3-111">SQLEngine</span></span>|  
|<span data-ttu-id="ee0d3-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ee0d3-112">Symbolic Name</span></span>|<span data-ttu-id="ee0d3-113">DBCC_NO_EXPRESSION_EVALUATOR</span><span class="sxs-lookup"><span data-stu-id="ee0d3-113">DBCC_NO_EXPRESSION_EVALUATOR</span></span>|  
|<span data-ttu-id="ee0d3-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ee0d3-114">Message Text</span></span>|<span data-ttu-id="ee0d3-115">Colunas computadas e tipos definidos pelo usuário não podem ter a ID do objeto O_ID (objeto "O_NAME") verificada porque o avaliador interno de expressões não pôde ser inicializado.</span><span class="sxs-lookup"><span data-stu-id="ee0d3-115">Computed columns and user-defined types cannot be checked for object ID O_ID (object "O_NAME") because the internal expression evaluator could not be initialized.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ee0d3-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="ee0d3-116">Explanation</span></span>  
 <span data-ttu-id="ee0d3-117">Essa mensagem informativa indica que o processador de consultas não pôde fornecer para DBCC um objeto interno que permita a avaliação de colunas computadas e de tipos CLR (Common Language Runtime) definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ee0d3-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for the evaluation of computed columns and common language runtime (CLR) user-defined types.</span></span> <span data-ttu-id="ee0d3-118">Isso significa que as colunas computadas e os tipos CLR definidos pelo usuário não serão verificados quanto à correção ou que não serão usados quando DBCC verificar a consistência entre índices e tabelas base.</span><span class="sxs-lookup"><span data-stu-id="ee0d3-118">This means that computed columns and CLR user-defined types will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ee0d3-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ee0d3-119">User Action</span></span>  
 <span data-ttu-id="ee0d3-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ee0d3-120">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0d3-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee0d3-121">See Also</span></span>  
 [<span data-ttu-id="ee0d3-122">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="ee0d3-122">MSSQLSERVER_2518</span></span>](mssqlserver-2518-database-engine-error.md)  
  
  
