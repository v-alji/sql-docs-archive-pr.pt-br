---
title: Tipos de consulta com suporte (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Delete query
- queries [SQL Server], types
- Update query
- Query Designer [SQL Server], query types
- Criteria pane
- Insert Values query
- Select query
- Make Table query
- Insert Results query
- Diagram pane [Visual Database Tools]
- View Designer, query types
ms.assetid: 72b9116c-c128-4078-a78d-257a2955a3f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b00b7018fc6d0b631696811bd1870e09842b4162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683273"
---
# <a name="supported-query-types-visual-database-tools"></a><span data-ttu-id="2e0dc-102">Tipos de consulta permitidos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2e0dc-102">Supported Query Types (Visual Database Tools)</span></span>
  <span data-ttu-id="2e0dc-103">Você pode criar os seguintes tipos de consultas nos painéis de Diagrama e Critérios (os painéis gráficos) do [Designer de Consulta e Exibição](visual-database-tools.md):</span><span class="sxs-lookup"><span data-stu-id="2e0dc-103">You can create the following types of queries in the Diagram and Criteria panes (the graphical panes) of the [Query and View Designer](visual-database-tools.md):</span></span>  
  
-   <span data-ttu-id="2e0dc-104">**Consulta de seleção** Recupera dados de uma ou mais tabelas ou exibições.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-104">**Select query** Retrieves data from one or more tables or views.</span></span> <span data-ttu-id="2e0dc-105">Esse tipo de consulta cria uma instrução SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-105">This type of query creates an SQL SELECT statement.</span></span>  
  
-   <span data-ttu-id="2e0dc-106">**Inserir Resultados** Cria linhas novas copiando linhas existentes de uma tabela para outra, ou na mesma tabela como linhas novas.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-106">**Insert Results** Creates new rows by copying existing rows from one table into another, or into the same table as new rows.</span></span> <span data-ttu-id="2e0dc-107">Esse tipo de consulta cria uma instrução SQL INSERT INTO...SELECT.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-107">This type of query creates an SQL INSERT INTO...SELECT statement.</span></span>  
  
-   <span data-ttu-id="2e0dc-108">**Inserir Valores** Cria uma linha nova e insere valores em colunas especificadas.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-108">**Insert Values** Creates a new row and inserts values into specified columns.</span></span> <span data-ttu-id="2e0dc-109">Esse tipo de consulta cria uma instrução SQL INSERT INTO...VALUES.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-109">This type of query creates an SQL INSERT INTO...VALUES statement.</span></span>  
  
-   <span data-ttu-id="2e0dc-110">**Consulta de atualização** Altera os valores de colunas individuais em uma ou mais linhas existentes em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-110">**Update query** Changes the values of individual columns in one or more existing rows in a table.</span></span> <span data-ttu-id="2e0dc-111">Esse tipo de consulta cria uma instrução SQL UPDATE…SET.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-111">This type of query creates an SQL UPDATE...SET statement.</span></span>  
  
-   <span data-ttu-id="2e0dc-112">**Consulta de exclusão** Remove uma ou mais linhas de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-112">**Delete query** Removes one or more rows from a table.</span></span> <span data-ttu-id="2e0dc-113">Esse tipo de consulta cria uma instrução SQL DELETE.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-113">This type of query creates an SQL DELETE statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e0dc-114">Uma consulta DELETE remove linhas inteiras de tabelas.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-114">A Delete query removes entire rows from the table.</span></span> <span data-ttu-id="2e0dc-115">Se você quer excluir valores de colunas de dados individuais, use uma consulta UPDATE.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-115">If you want to delete values from individual data columns, use an Update query.</span></span>  
  
-   <span data-ttu-id="2e0dc-116">**Consulta Criar Tabela** Cria uma tabela nova e cria linhas na mesma copiando os resultados de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-116">**Make Table query** Creates a new table and creates rows in it by copying the results of a query into it.</span></span> <span data-ttu-id="2e0dc-117">Esse tipo de consulta cria uma instrução SQL SELECT....INTO</span><span class="sxs-lookup"><span data-stu-id="2e0dc-117">This type of query creates an SQL SELECT...INTO statement.</span></span>  
  
 <span data-ttu-id="2e0dc-118">Além das consultas, que você pode criar usando os painéis gráficos, pode inserir qualquer instrução SQL no painel de SQL, tais como consultas Union.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-118">In addition to the queries you can create using the graphical panes, you can enter any SQL statement into the SQL pane, such as Union queries.</span></span>  
  
 <span data-ttu-id="2e0dc-119">Quando você criar consultas que usam instruções SQL que não podem ser representadas nos painéis gráficos, o Designer de Consulta e Exibição escurece esses painéis para indicar que eles não refletem a consulta que você está criando.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-119">When you create queries using SQL statements that cannot be represented in the graphical panes, the Query and View Designer dims those panes to indicate that they do not reflect the query you are creating.</span></span> <span data-ttu-id="2e0dc-120">Porém, os painéis escurecidos ainda estão ativos e, em muitas casos, você pode fazer alterações na consulta nesses painéis.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-120">However, the dimmed panes are still active and, in many cases, you can make changes to the query in those panes.</span></span> <span data-ttu-id="2e0dc-121">Se as alterações que você fizer resultarem em uma consulta que pode ser representada nos painéis gráficos, esses painéis não são mais escurecidos.</span><span class="sxs-lookup"><span data-stu-id="2e0dc-121">If the changes you make result in a query that can be represented in the graphical panes, those panes are no longer dimmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0dc-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e0dc-122">See Also</span></span>  
 <span data-ttu-id="2e0dc-123">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2e0dc-123">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2e0dc-124">Tipos de consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2e0dc-124">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
