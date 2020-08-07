---
title: Categoria de evento de desempenho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Performance event category
- Performance event category [SQL Server]
- event classes [SQL Server], Performance event category
ms.assetid: 708f3585-d8be-4980-bbff-672d7c59397e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b0c076a4132298797313ecbf0874d9d2d4e453cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575817"
---
# <a name="performance-event-category"></a><span data-ttu-id="0587a-102">Categoria de evento de desempenho</span><span class="sxs-lookup"><span data-stu-id="0587a-102">Performance Event Category</span></span>
  <span data-ttu-id="0587a-103">Use a categoria de evento **Performance** para monitorar as classes de evento **Showplan** e as que são produzidas pela execução dos operadores DML (linguagem de manipulação de dados) do SQL.</span><span class="sxs-lookup"><span data-stu-id="0587a-103">Use the **Performance** event category to monitor **Showplan** event classes and event classes that are produced from the execution of SQL data manipulation language (DML) operators.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0587a-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0587a-104">In This Section</span></span>  
  
|<span data-ttu-id="0587a-105">Tópico</span><span class="sxs-lookup"><span data-stu-id="0587a-105">Topic</span></span>|<span data-ttu-id="0587a-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0587a-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0587a-107">Classe de evento Auto Stats</span><span class="sxs-lookup"><span data-stu-id="0587a-107">Auto Stats Event Class</span></span>](auto-stats-event-class.md)|<span data-ttu-id="0587a-108">Indica que houve uma atualização automática de índice e estatísticas de coluna.</span><span class="sxs-lookup"><span data-stu-id="0587a-108">Indicates that an automatic updating of index and column statistics has occurred.</span></span>|  
|[<span data-ttu-id="0587a-109">Classe de evento Grau de Paralelismo &#40;7.0 Insert&#41;</span><span class="sxs-lookup"><span data-stu-id="0587a-109">Degree of Parallelism &#40;7.0 Insert&#41; Event Class</span></span>](degree-of-parallelism-7-0-insert-event-class.md)|<span data-ttu-id="0587a-110">Indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executou uma instrução  SELECT, INSERT, UPDATE ou DELETE usando um plano consecutivo ou paralelo.</span><span class="sxs-lookup"><span data-stu-id="0587a-110">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a SELECT, INSERT, UPDATE, or DELETE statement using either a serial or parallel plan.</span></span> <span data-ttu-id="0587a-111">O número de CPUs usado para executar a operação também é informado.</span><span class="sxs-lookup"><span data-stu-id="0587a-111">The number of CPUs used to perform the operation is also reported.</span></span>|  
|[<span data-ttu-id="0587a-112">Classe de evento Performance Statistics</span><span class="sxs-lookup"><span data-stu-id="0587a-112">Performance Statistics Event Class</span></span>](performance-statistics-event-class.md)|<span data-ttu-id="0587a-113">Monitora o desempenho das consultas que estão sendo executadas.</span><span class="sxs-lookup"><span data-stu-id="0587a-113">Monitors performance of the queries that are being executed.</span></span>|  
|[<span data-ttu-id="0587a-114">Classe de evento Showplan All</span><span class="sxs-lookup"><span data-stu-id="0587a-114">Showplan All Event Class</span></span>](showplan-all-event-class.md)|<span data-ttu-id="0587a-115">Identifica os operadores de **Plano de execução** em uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="0587a-115">Identifies **Showplan** operators within a SQL statement.</span></span>|  
|[<span data-ttu-id="0587a-116">Classe de evento Showplan All for Query Compile</span><span class="sxs-lookup"><span data-stu-id="0587a-116">Showplan All for Query Compile Event Class</span></span>](showplan-all-for-query-compile-event-class.md)|<span data-ttu-id="0587a-117">Exibe dados de tempo de compilação para operadores de **Plano de execução** .</span><span class="sxs-lookup"><span data-stu-id="0587a-117">Displays compile time data for **Showplan** operators.</span></span>|  
|[<span data-ttu-id="0587a-118">Classe de Evento Showplan Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="0587a-118">Showplan Statistics Profile Event Class</span></span>](showplan-statistics-profile-event-class.md)|<span data-ttu-id="0587a-119">Exibe o custo calculado de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="0587a-119">Displays the estimated cost of a query.</span></span>|  
|[<span data-ttu-id="0587a-120">Classe de evento Showplan XML</span><span class="sxs-lookup"><span data-stu-id="0587a-120">Showplan XML Event Class</span></span>](showplan-xml-event-class.md)|<span data-ttu-id="0587a-121">Identifica os operadores de **Plano de execução** em uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="0587a-121">Identifies the **Showplan** operators in a SQL statement.</span></span> <span data-ttu-id="0587a-122">A classe de evento armazena cada evento como um documento de XML bem definido.</span><span class="sxs-lookup"><span data-stu-id="0587a-122">The event class stores each event as a well defined XML document.</span></span>|  
|[<span data-ttu-id="0587a-123">Classe de evento Showplan XML for Query Compile</span><span class="sxs-lookup"><span data-stu-id="0587a-123">Showplan XML for Query Compile Event Class</span></span>](showplan-xml-for-query-compile-event-class.md)|<span data-ttu-id="0587a-124">Exibe dados de tempo de compilação para operadores de **Plano de execução** em formato de XML.</span><span class="sxs-lookup"><span data-stu-id="0587a-124">Displays compile time data for **Showplan** operators in XML format.</span></span>|  
|[<span data-ttu-id="0587a-125">Classe de evento Showplan XML Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="0587a-125">Showplan XML Statistics Profile Event Class</span></span>](showplan-xml-statistics-profile-event-class.md)|<span data-ttu-id="0587a-126">Identifica os operadores de **Plano de execução** associados com uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="0587a-126">Identifies the **Showplan** operators associated with a SQL statement.</span></span> <span data-ttu-id="0587a-127">A saída é um documento de XML.</span><span class="sxs-lookup"><span data-stu-id="0587a-127">The output is an XML document.</span></span>|  
|[<span data-ttu-id="0587a-128">Classe de evento SQL:FullTextQuery</span><span class="sxs-lookup"><span data-stu-id="0587a-128">SQL:FullTextQuery Event Class</span></span>](sql-fulltextquery-event-class.md)|<span data-ttu-id="0587a-129">Indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executou uma consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="0587a-129">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a full-text query.</span></span>|  
|[<span data-ttu-id="0587a-130">Classe de evento Plan Guide Successful</span><span class="sxs-lookup"><span data-stu-id="0587a-130">Plan Guide Successful Event Class</span></span>](plan-guide-successful-event-class.md)|<span data-ttu-id="0587a-131">Indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] produziu com sucesso um plano de execução para uma consulta ou lote, que continha uma guia de plano.</span><span class="sxs-lookup"><span data-stu-id="0587a-131">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] successfully produced an execution plan for a query or batch that contained a plan guide.</span></span>|  
|[<span data-ttu-id="0587a-132">Classe de evento Plan Guide Unsuccessful</span><span class="sxs-lookup"><span data-stu-id="0587a-132">Plan Guide Unsuccessful Event Class</span></span>](plan-guide-unsuccessful-event-class.md)|<span data-ttu-id="0587a-133">Indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pôde produzir um plano de execução, para uma consulta ou lote, que continha uma guia de plano.</span><span class="sxs-lookup"><span data-stu-id="0587a-133">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not produce an execution plan for a query or batch that contained a plan guide.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0587a-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0587a-134">See Also</span></span>  
 [<span data-ttu-id="0587a-135">Eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="0587a-135">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
