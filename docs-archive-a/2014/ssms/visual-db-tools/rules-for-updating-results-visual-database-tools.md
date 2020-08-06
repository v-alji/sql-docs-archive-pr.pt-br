---
title: Regras para atualização de resultados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- updating query results
- Query Designer [SQL Server], Results pane
- Results pane
ms.assetid: de131ef0-ccbd-446f-9400-b93c7b8fa537
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc6befc6571f29be95b176f8de6d7dcfaed9108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682050"
---
# <a name="rules-for-updating-results-visual-database-tools"></a><span data-ttu-id="7e254-102">Regras para atualização de resultados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7e254-102">Rules for Updating Results (Visual Database Tools)</span></span>
  <span data-ttu-id="7e254-103">Em muitos casos, você pode atualizar o conjunto de resultados exibido no [Painel de Resultados](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7e254-103">In many cases, you can update the result set displayed in the [Results Pane](visual-database-tools.md).</span></span> <span data-ttu-id="7e254-104">Porém, em alguns casos você não pode.</span><span class="sxs-lookup"><span data-stu-id="7e254-104">However, in some cases you cannot.</span></span>  
  
 <span data-ttu-id="7e254-105">No geral, para poder atualizar os resultados, o [Designer de Consulta e Exibição](query-and-view-designer-tools-visual-database-tools.md) deve ter informações suficientes para identificar exclusivamente a linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="7e254-105">In general, in order to update results, the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) must have sufficient information to uniquely identify the row in the table.</span></span> <span data-ttu-id="7e254-106">Um exemplo será se a consulta incluir uma chave primária na lista de saída.</span><span class="sxs-lookup"><span data-stu-id="7e254-106">An example is if the query includes a primary key in the output list.</span></span> <span data-ttu-id="7e254-107">Além disso, você deve ter permissão suficiente para atualizar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7e254-107">In addition, you must have sufficient permission to update the database.</span></span>  
  
 <span data-ttu-id="7e254-108">Se sua consulta for baseada em uma exibição, você poderá atualizá-la.</span><span class="sxs-lookup"><span data-stu-id="7e254-108">If your query is based on a view, you might be able to update it.</span></span> <span data-ttu-id="7e254-109">As mesmas diretrizes se aplicam, exceto que elas se aplicam às tabelas subjacentes na exibição, não somente à exibição em si.</span><span class="sxs-lookup"><span data-stu-id="7e254-109">The same guidelines apply, except that they apply to the underlying tables in the view, not just to the view itself.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e254-110">O Designer de Consulta e Exibição não pode determinar antecipadamente se você pode atualizar um conjunto de resultados baseado em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="7e254-110">The Query and View Designer cannot determine in advance whether you can update a result set based on a view.</span></span> <span data-ttu-id="7e254-111">Então, ele mostra todas as exibições, embora talvez você não possa atualizá-las.</span><span class="sxs-lookup"><span data-stu-id="7e254-111">Therefore, it displays all views, even though you might not be able to update them.</span></span>  
  
 <span data-ttu-id="7e254-112">A tabela seguinte resume instâncias específicas nas quais você poderá ou não atualizar os resultados de consulta no painel de Resultados.</span><span class="sxs-lookup"><span data-stu-id="7e254-112">The following table summarizes specific instances in which you might and might not be able to update query results in the Results pane.</span></span> <span data-ttu-id="7e254-113">Em muitos casos, o banco de dados que você está usando é quem determina se você pode atualizar os resultados de consulta ou não.</span><span class="sxs-lookup"><span data-stu-id="7e254-113">In many cases, the database you are using dictates whether you can update query results.</span></span>  
  
|<span data-ttu-id="7e254-114">Consulta</span><span class="sxs-lookup"><span data-stu-id="7e254-114">Query</span></span>|<span data-ttu-id="7e254-115">Os resultados podem ser atualizados?</span><span class="sxs-lookup"><span data-stu-id="7e254-115">Can results be updated?</span></span>|  
|-----------|-----------------------------|  
|<span data-ttu-id="7e254-116">Consulta baseada em uma tabela com chave primária na lista de saída</span><span class="sxs-lookup"><span data-stu-id="7e254-116">Query based on one table with primary key in the output list</span></span>|<span data-ttu-id="7e254-117">Sim (exceto como listado abaixo).</span><span class="sxs-lookup"><span data-stu-id="7e254-117">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="7e254-118">Consulta baseada em uma tabela sem índice exclusivo e sem uma chave primária</span><span class="sxs-lookup"><span data-stu-id="7e254-118">Query based on a table with no unique index and without a primary key</span></span>|<span data-ttu-id="7e254-119">Depende da consulta e do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7e254-119">Depends on query and database.</span></span> <span data-ttu-id="7e254-120">Alguns bancos de dados permitem atualizações se informações suficiente estiverem disponíveis para identificar registros exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="7e254-120">Some databases allow updates if sufficient information is available to uniquely identify records.</span></span>|  
|<span data-ttu-id="7e254-121">Consulta baseada em tabelas múltiplas que não estão unidas</span><span class="sxs-lookup"><span data-stu-id="7e254-121">Query based on multiple tables which are not joined</span></span>|<span data-ttu-id="7e254-122">Não.</span><span class="sxs-lookup"><span data-stu-id="7e254-122">No.</span></span>|  
|<span data-ttu-id="7e254-123">Consulta baseada em dados marcados como somente de leitura no banco de dados</span><span class="sxs-lookup"><span data-stu-id="7e254-123">Query based on data marked as read-only in the database</span></span>|<span data-ttu-id="7e254-124">Não.</span><span class="sxs-lookup"><span data-stu-id="7e254-124">No.</span></span>|  
|<span data-ttu-id="7e254-125">Consulta baseada em uma exibição que envolve uma tabela sem restrições</span><span class="sxs-lookup"><span data-stu-id="7e254-125">Query based on a view that involves one table with no constraints</span></span>|<span data-ttu-id="7e254-126">Sim (exceto como listado abaixo).</span><span class="sxs-lookup"><span data-stu-id="7e254-126">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="7e254-127">Consulta baseada em tabelas unidas com uma relação um-para-um</span><span class="sxs-lookup"><span data-stu-id="7e254-127">Query based on tables joined with a one-to-one relationship</span></span>|<span data-ttu-id="7e254-128">Sim (exceto como listado abaixo).</span><span class="sxs-lookup"><span data-stu-id="7e254-128">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="7e254-129">Consulta baseada em tabelas unidas com uma relação um-para-um</span><span class="sxs-lookup"><span data-stu-id="7e254-129">Query based on tables joined with a one-to-many relationship</span></span>|<span data-ttu-id="7e254-130">Geralmente.</span><span class="sxs-lookup"><span data-stu-id="7e254-130">Usually.</span></span>|  
|<span data-ttu-id="7e254-131">Consulta baseada em três ou mais tabelas nas quais há uma relação muitos para muitos</span><span class="sxs-lookup"><span data-stu-id="7e254-131">Query based on three or more tables in which there is a many-to-many relationship</span></span>|<span data-ttu-id="7e254-132">Não.</span><span class="sxs-lookup"><span data-stu-id="7e254-132">No.</span></span>|  
|<span data-ttu-id="7e254-133">Consulta baseada em uma tabela para a qual não é concedida a permissão de atualização</span><span class="sxs-lookup"><span data-stu-id="7e254-133">Query based on a table for which update permission is not granted</span></span>|<span data-ttu-id="7e254-134">Pode excluir mas não atualizar.</span><span class="sxs-lookup"><span data-stu-id="7e254-134">Can delete but not update.</span></span>|  
|<span data-ttu-id="7e254-135">Consulta baseada em uma tabela para a qual não é concedida a permissão de exclusão</span><span class="sxs-lookup"><span data-stu-id="7e254-135">Query based on a table for which delete permission is not granted</span></span>|<span data-ttu-id="7e254-136">Pode atualizar mas não excluir.</span><span class="sxs-lookup"><span data-stu-id="7e254-136">Can update but not delete.</span></span>|  
|<span data-ttu-id="7e254-137">Consulta de agregação</span><span class="sxs-lookup"><span data-stu-id="7e254-137">Aggregate query</span></span>|<span data-ttu-id="7e254-138">Não.</span><span class="sxs-lookup"><span data-stu-id="7e254-138">No.</span></span>|  
|<span data-ttu-id="7e254-139">Consulta baseada em uma subconsulta que contém funções de agregação ou totais</span><span class="sxs-lookup"><span data-stu-id="7e254-139">Query based on a subquery that contains totals or aggregate functions</span></span>|<span data-ttu-id="7e254-140">Não.</span><span class="sxs-lookup"><span data-stu-id="7e254-140">No.</span></span>|  
|<span data-ttu-id="7e254-141">Consulta que inclui a palavra-chave DISTINCT para excluir filas duplicadas</span><span class="sxs-lookup"><span data-stu-id="7e254-141">Query that includes the DISTINCT keyword to exclude duplicate rows</span></span>|<span data-ttu-id="7e254-142">Não.</span><span class="sxs-lookup"><span data-stu-id="7e254-142">No.</span></span>|  
|<span data-ttu-id="7e254-143">Consulta cuja cláusula FROM inclui uma função definida pelo usuário que retorna uma tabela e a função definida pelo usuário contém múltiplas instruções select</span><span class="sxs-lookup"><span data-stu-id="7e254-143">Query whose FROM clause includes a user-defined function that returns a table and the user-defined function contains multiple select statements</span></span>|<span data-ttu-id="7e254-144">Não.</span><span class="sxs-lookup"><span data-stu-id="7e254-144">No.</span></span>|  
|<span data-ttu-id="7e254-145">Consulta cuja cláusula FROM inclui um função embutida definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="7e254-145">Query whose FROM clause includes an inline user-defined function</span></span>|<span data-ttu-id="7e254-146">Sim.</span><span class="sxs-lookup"><span data-stu-id="7e254-146">Yes.</span></span>|  
  
 <span data-ttu-id="7e254-147">Além disso, talvez você pode não possa atualizar colunas específicas no resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="7e254-147">In addition, you might not be able to update specific columns in the query results.</span></span> <span data-ttu-id="7e254-148">A lista seguinte resume os tipos específicos de colunas que você não pode atualizar no painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="7e254-148">The following list summarizes specific types of columns that you cannot update in the Results pane.</span></span>  
  
-   <span data-ttu-id="7e254-149">Colunas baseadas em expressões</span><span class="sxs-lookup"><span data-stu-id="7e254-149">Columns based on expressions</span></span>  
  
-   <span data-ttu-id="7e254-150">Colunas baseadas em funções escalares definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="7e254-150">Columns based on scalar user-defined functions</span></span>  
  
-   <span data-ttu-id="7e254-151">Filas ou colunas excluídas por outro usuário</span><span class="sxs-lookup"><span data-stu-id="7e254-151">Rows or columns deleted by another user</span></span>  
  
-   <span data-ttu-id="7e254-152">Filas ou colunas bloqueadas por outro usuário (normalmente filas bloqueadas podem ser atualizadas logo que sejam desbloqueadas)</span><span class="sxs-lookup"><span data-stu-id="7e254-152">Rows or columns locked by another user (locked rows can usually be updated as soon as they are unlocked)</span></span>  
  
-   <span data-ttu-id="7e254-153">Carimbo de data/hora ou colunas BLOB</span><span class="sxs-lookup"><span data-stu-id="7e254-153">Timestamp or BLOB columns</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e254-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e254-154">See Also</span></span>  
 [<span data-ttu-id="7e254-155">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7e254-155">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
