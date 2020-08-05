---
title: MSSQLSERVER_2814 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2814 (Database Engine error)
ms.assetid: 22800748-9be9-4511-9428-6b8b40e5bef9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26b1fae5b683ed72cb93c3f81981bd41e2f4ad4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574043"
---
# <a name="mssqlserver_2814"></a><span data-ttu-id="e5980-102">MSSQLSERVER_2814</span><span class="sxs-lookup"><span data-stu-id="e5980-102">MSSQLSERVER_2814</span></span>
    
## <a name="details"></a><span data-ttu-id="e5980-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e5980-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5980-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e5980-104">Product Name</span></span>|<span data-ttu-id="e5980-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5980-105">SQL Server</span></span>|  
|<span data-ttu-id="e5980-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e5980-106">Event ID</span></span>|<span data-ttu-id="e5980-107">2814</span><span class="sxs-lookup"><span data-stu-id="e5980-107">2814</span></span>|  
|<span data-ttu-id="e5980-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e5980-108">Event Source</span></span>|<span data-ttu-id="e5980-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e5980-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e5980-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e5980-110">Component</span></span>|<span data-ttu-id="e5980-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e5980-111">SQLEngine</span></span>|  
|<span data-ttu-id="e5980-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e5980-112">Symbolic Name</span></span>|<span data-ttu-id="e5980-113">PR_POSSIBLE_INFINITE_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="e5980-113">PR_POSSIBLE_INFINITE_RECOMPILE</span></span>|  
|<span data-ttu-id="e5980-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e5980-114">Message Text</span></span>|<span data-ttu-id="e5980-115">Uma possível recompilação infinita foi detectada para SQLHANDLE %hs, PlanHandle %hs, deslocamento inicial %d, deslocamento final %d.</span><span class="sxs-lookup"><span data-stu-id="e5980-115">A possible infinite recompile was detected for SQLHANDLE %hs, PlanHandle %hs, starting offset %d, ending offset %d.</span></span> <span data-ttu-id="e5980-116">O último motivo da recompilação foi %d.</span><span class="sxs-lookup"><span data-stu-id="e5980-116">The last recompile reason was %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e5980-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="e5980-117">Explanation</span></span>  
 <span data-ttu-id="e5980-118">Uma ou mais instruções fizeram com que o lote de consultas fosse recompilado pelo menos 50 vezes.</span><span class="sxs-lookup"><span data-stu-id="e5980-118">One or more statements caused the query batch to recompile at least 50 times.</span></span> <span data-ttu-id="e5980-119">A instrução especificada deve ser corrigida para evitar mais recompilações.</span><span class="sxs-lookup"><span data-stu-id="e5980-119">The specified statement should be corrected to avoid further recompilations.</span></span>  
  
 <span data-ttu-id="e5980-120">A tabela a seguir lista os motivos da recompilação.</span><span class="sxs-lookup"><span data-stu-id="e5980-120">The following table lists the reasons for recompilation.</span></span>  
  
|<span data-ttu-id="e5980-121">Código do motivo</span><span class="sxs-lookup"><span data-stu-id="e5980-121">Reason code</span></span>|<span data-ttu-id="e5980-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5980-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e5980-123">1</span><span class="sxs-lookup"><span data-stu-id="e5980-123">1</span></span>|<span data-ttu-id="e5980-124">Esquema alterado</span><span class="sxs-lookup"><span data-stu-id="e5980-124">Schema changed</span></span>|  
|<span data-ttu-id="e5980-125">2</span><span class="sxs-lookup"><span data-stu-id="e5980-125">2</span></span>|<span data-ttu-id="e5980-126">Estatísticas alteradas</span><span class="sxs-lookup"><span data-stu-id="e5980-126">Statistics changed</span></span>|  
|<span data-ttu-id="e5980-127">3</span><span class="sxs-lookup"><span data-stu-id="e5980-127">3</span></span>|<span data-ttu-id="e5980-128">Compilação adiada</span><span class="sxs-lookup"><span data-stu-id="e5980-128">Deferred compile</span></span>|  
|<span data-ttu-id="e5980-129">4</span><span class="sxs-lookup"><span data-stu-id="e5980-129">4</span></span>|<span data-ttu-id="e5980-130">Opção set alterada</span><span class="sxs-lookup"><span data-stu-id="e5980-130">Set option changed</span></span>|  
|<span data-ttu-id="e5980-131">5</span><span class="sxs-lookup"><span data-stu-id="e5980-131">5</span></span>|<span data-ttu-id="e5980-132">Tabela temp alterada</span><span class="sxs-lookup"><span data-stu-id="e5980-132">Temp table changed</span></span>|  
|<span data-ttu-id="e5980-133">6</span><span class="sxs-lookup"><span data-stu-id="e5980-133">6</span></span>|<span data-ttu-id="e5980-134">Conjunto de linhas remoto alterado</span><span class="sxs-lookup"><span data-stu-id="e5980-134">Remote rowset changed</span></span>|  
|<span data-ttu-id="e5980-135">7</span><span class="sxs-lookup"><span data-stu-id="e5980-135">7</span></span>|<span data-ttu-id="e5980-136">Permissões For Browse alteradas</span><span class="sxs-lookup"><span data-stu-id="e5980-136">For Browse permissions changed</span></span>|  
|<span data-ttu-id="e5980-137">8</span><span class="sxs-lookup"><span data-stu-id="e5980-137">8</span></span>|<span data-ttu-id="e5980-138">Ambiente de notificação de consulta alterado</span><span class="sxs-lookup"><span data-stu-id="e5980-138">Query notification environment changed</span></span>|  
|<span data-ttu-id="e5980-139">9</span><span class="sxs-lookup"><span data-stu-id="e5980-139">9</span></span>|<span data-ttu-id="e5980-140">Exibição de partição alterada</span><span class="sxs-lookup"><span data-stu-id="e5980-140">Partition view changed</span></span>|  
|<span data-ttu-id="e5980-141">10</span><span class="sxs-lookup"><span data-stu-id="e5980-141">10</span></span>|<span data-ttu-id="e5980-142">Opções de cursor alteradas</span><span class="sxs-lookup"><span data-stu-id="e5980-142">Cursor options changed</span></span>|  
|<span data-ttu-id="e5980-143">11</span><span class="sxs-lookup"><span data-stu-id="e5980-143">11</span></span>|<span data-ttu-id="e5980-144">Opção (recompilar) solicitada</span><span class="sxs-lookup"><span data-stu-id="e5980-144">Option (recompile) requested</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="e5980-145">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e5980-145">User Action</span></span>  
  
1.  <span data-ttu-id="e5980-146">Para exibir a instrução que causa a recompilação, execute a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="e5980-146">View the statement causing the recompilation by running the following query.</span></span> <span data-ttu-id="e5980-147">Substitua os espaços reservados *sql_handle*, *starting_offset*, *ending_offset* e *plan_handle* pelos valores especificados na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="e5980-147">Replace the *sql_handle*, *starting_offset*, *ending_offset*, and *plan_handle* placeholders with the values specified in the error message.</span></span> <span data-ttu-id="e5980-148">Observe que as colunas **database_name** e **object_name** serão NULL para instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc e preparadas.</span><span class="sxs-lookup"><span data-stu-id="e5980-148">Note that the **database_name** and **object_name** columns will be NULL for ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="e5980-149">SELECT DB_NAME(st.dbid) AS database_name</span><span class="sxs-lookup"><span data-stu-id="e5980-149">SELECT DB_NAME(st.dbid) AS database_name</span></span>  
  
     <span data-ttu-id="e5980-150">, OBJECT_NAME(st.objectid) AS object_name</span><span class="sxs-lookup"><span data-stu-id="e5980-150">, OBJECT_NAME(st.objectid) AS object_name</span></span>  
  
     <span data-ttu-id="e5980-151">, st.text</span><span class="sxs-lookup"><span data-stu-id="e5980-151">, st.text</span></span>  
  
     <span data-ttu-id="e5980-152">FROM sys.dm_exec_query_stats AS qs</span><span class="sxs-lookup"><span data-stu-id="e5980-152">FROM sys.dm_exec_query_stats AS qs</span></span>  
  
     <span data-ttu-id="e5980-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span><span class="sxs-lookup"><span data-stu-id="e5980-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span></span>  
  
     <span data-ttu-id="e5980-154">WHERE qs.statement_start_offset = *starting_offset*</span><span class="sxs-lookup"><span data-stu-id="e5980-154">WHERE qs.statement_start_offset = *starting_offset*</span></span>  
  
     <span data-ttu-id="e5980-155">AND qs.statement_end_offset = *ending_offset*</span><span class="sxs-lookup"><span data-stu-id="e5980-155">AND qs.statement_end_offset = *ending_offset*</span></span>  
  
     <span data-ttu-id="e5980-156">AND qs.plan_handle = *plan_handle*;</span><span class="sxs-lookup"><span data-stu-id="e5980-156">AND qs.plan_handle = *plan_handle*;</span></span>  
  
2.  <span data-ttu-id="e5980-157">Com base na descrição do código do motivo, modifique a instrução, o lote ou o procedimento para evitar recompilações.</span><span class="sxs-lookup"><span data-stu-id="e5980-157">Based on the reason code description, modify the statement, batch, or procedure to avoid recompilations.</span></span> <span data-ttu-id="e5980-158">Por exemplo, um procedimento armazenado pode conter uma ou mais instruções SET.</span><span class="sxs-lookup"><span data-stu-id="e5980-158">For example, a stored procedure may contain one or more SET statements.</span></span> <span data-ttu-id="e5980-159">Essas instruções devem ser removidas do procedimento.</span><span class="sxs-lookup"><span data-stu-id="e5980-159">These statements should be removed from the procedure.</span></span> <span data-ttu-id="e5980-160">Para obter mais exemplos dos motivos e das resoluções da recompilação, consulte [Problemas de compilação em lote, recompilação e cache de planos no SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="e5980-160">For additional examples of recompilation causes and resolutions, see [Batch Compilation, Recompilation, and Plan Caching Issues in SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span></span>  
  
3.  <span data-ttu-id="e5980-161">Se o problema persistir, contate os Serviços de Atendimento ao Cliente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5980-161">If the problem persists, contact Microsoft Customer Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5980-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5980-162">See Also</span></span>  
 [<span data-ttu-id="e5980-163">Classe de evento SQL:StmtRecompile</span><span class="sxs-lookup"><span data-stu-id="e5980-163">SQL:StmtRecompile Event Class</span></span>](../event-classes/sql-stmtrecompile-event-class.md)  
  
  
