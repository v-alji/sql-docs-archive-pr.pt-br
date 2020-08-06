---
title: Propriedades de consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69636
- vdt.ppg.querydesigner.query
ms.assetid: 07495669-6ed5-4004-904e-aae1230be5e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3c8adfb50e15113228afe8b48218f341f19084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679616"
---
# <a name="query-properties-visual-database-tools"></a><span data-ttu-id="1f3f7-102">Propriedades de consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1f3f7-102">Query Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="1f3f7-103">Essas propriedades aparecem na janela Propriedades quando você tiver uma consulta aberta no Designer de Consulta e Exibição.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-103">These properties appear in the Properties window when you have a query open in Query and View Designer.</span></span> <span data-ttu-id="1f3f7-104">A menos que seja indicado o contrário, é possível editar essas propriedades na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-104">Unless otherwise noted, you can edit these properties in the Properties window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f3f7-105">As propriedades neste tópico são ordenadas por categoria e não por ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-105">The properties in this topic are ordered by category, rather than alphabetically.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f3f7-106">Opções</span><span class="sxs-lookup"><span data-stu-id="1f3f7-106">Options</span></span>  
 <span data-ttu-id="1f3f7-107">**Categoria de identidade**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-107">**Identity Category**</span></span>  
 <span data-ttu-id="1f3f7-108">Expanda para mostrar o **Nome** da propriedade.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-108">Expand to show the **Name** property.</span></span>  
  
 <span data-ttu-id="1f3f7-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-109">**Name**</span></span>  
 <span data-ttu-id="1f3f7-110">Mostra o nome da consulta atual.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-110">Shows the name of the current query.</span></span> <span data-ttu-id="1f3f7-111">Não pode ser alterado no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f3f7-111">Cannot be changed in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="1f3f7-112">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-112">**Database Name**</span></span>  
 <span data-ttu-id="1f3f7-113">Mostra o nome da fonte de dados para a tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-113">Shows the name of the data source for the selected table.</span></span>  
  
 <span data-ttu-id="1f3f7-114">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-114">**Server Name**</span></span>  
 <span data-ttu-id="1f3f7-115">Mostra o nome do servidor para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-115">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="1f3f7-116">**Categoria de Designer de Consulta**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-116">**Query Designer Category**</span></span>  
 <span data-ttu-id="1f3f7-117">Expande para mostrar as propriedades restantes.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-117">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="1f3f7-118">**Tabela de destino**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-118">**Destination table**</span></span>  
 <span data-ttu-id="1f3f7-119">Especifique o nome da tabela na qual você está inserindo dados.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-119">Specify the name of the table into which you are inserting data.</span></span> <span data-ttu-id="1f3f7-120">Essa lista será exibida se você estiver criando uma consulta de INSERT ou consulta de MAKE TABLE.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-120">This list appears if you are creating an INSERT query or MAKE TABLE query.</span></span> <span data-ttu-id="1f3f7-121">Para uma consulta de INSERT, selecione um nome de tabela da lista.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-121">For an INSERT query, select a table name from the list.</span></span>  
  
 <span data-ttu-id="1f3f7-122">Para uma consulta de MAKE TABLE, digite o novo nome de tabela.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-122">For a MAKE TABLE query, type the name of the new table.</span></span> <span data-ttu-id="1f3f7-123">Para criar uma tabela de destino em outra fonte de dados, especifique um nome de tabela totalmente qualificado, incluindo o nome da fonte de dados de destino, o proprietário (se necessário) e o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-123">To create a destination table in another data source, specify a fully qualified table name, including the name of the target data source, the owner (if required), and the name of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f3f7-124">O Designer de Consulta não verifica se o nome já está em uso ou se você tem permissão para criar a tabela.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-124">Query Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
 <span data-ttu-id="1f3f7-125">**Valores Distintos**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-125">**Distinct values**</span></span>  
 <span data-ttu-id="1f3f7-126">Especifique se a consulta filtrará duplicatas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-126">Specify that the query will filter out duplicates in the result set.</span></span> <span data-ttu-id="1f3f7-127">Essa opção é útil quando você estiver usando apenas algumas das colunas da tabela, ou tabelas, e essas colunas possam conter valores duplicados ou, quando o processo de junção de duas ou mais tabelas produz linhas duplicadas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-127">This option is useful when you are using only some of the columns from the table or tables and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="1f3f7-128">Escolhendo essa opção é equivalente para inserir a palavra DISTINCT na instrução no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-128">Choosing this option is equivalent to inserting the word DISTINCT into the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="1f3f7-129">**Extensão GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-129">**GROUP BY Extension**</span></span>  
 <span data-ttu-id="1f3f7-130">Especifique quais as opções adicionais de consultas com base nas consultas de agregação estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-130">Specify that additional options for queries based on aggregate queries are available.</span></span> <span data-ttu-id="1f3f7-131">(Aplica-se somente ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="1f3f7-131">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="1f3f7-132">**Todas as Colunas de Saída**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-132">**Output All Columns**</span></span>  
 <span data-ttu-id="1f3f7-133">Especifique que todas as colunas de todas as tabelas na consulta atual estarão no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-133">Specify that all columns from all tables in the current query will be in the result set.</span></span> <span data-ttu-id="1f3f7-134">Escolhendo essa opção é equivalente para especificar um asterisco (\*) em lugar de nomes de coluna individual depois da palavra-chave SELECT na instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-134">Choosing this option is equivalent to specifying an asterisk (\*) in place of individual column names after the SELECT keyword in the SQL statement.</span></span>  
  
 <span data-ttu-id="1f3f7-135">**Lista de Parâmetro de Consulta**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-135">**Query Parameter List**</span></span>  
 <span data-ttu-id="1f3f7-136">Mostra parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-136">Shows query parameters.</span></span> <span data-ttu-id="1f3f7-137">Para editar os parâmetros, clique na propriedade e, em seguida, clique nas reticências **(…)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-137">To edit the parameters click the property and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="1f3f7-138">(Aplica-se apenas ao OLE DB genérico.)</span><span class="sxs-lookup"><span data-stu-id="1f3f7-138">(Applies only to generic OLE DB.)</span></span>  
  
 <span data-ttu-id="1f3f7-139">**Comentário SQL**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-139">**SQL Comment**</span></span>  
 <span data-ttu-id="1f3f7-140">Mostra uma descrição das instruções SQL.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-140">Shows a description of the SQL statements.</span></span> <span data-ttu-id="1f3f7-141">Para ver a descrição inteira ou editá-la, clique na descrição e então clique nas reticências **(…)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-141">To see the entire description or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="1f3f7-142">Os comentários podem incluir informações como quem usa a consulta e quando são usadas.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-142">Your comments can include information such as who uses the query and when they use it.</span></span> <span data-ttu-id="1f3f7-143">(Aplica-se apenas aos bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 ou posteriores.)</span><span class="sxs-lookup"><span data-stu-id="1f3f7-143">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 databases or later.)</span></span>  
  
 <span data-ttu-id="1f3f7-144">**Categoria Especificação Top**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-144">**Top Specification Category**</span></span>  
 <span data-ttu-id="1f3f7-145">Expanda para mostrar as propriedades **Top**, **Percent**, **Expression**e **With Ties** .</span><span class="sxs-lookup"><span data-stu-id="1f3f7-145">Expand to show properties for the **Top**, **Percent**, **Expression**, and **With Ties** properties.</span></span>  
  
 <span data-ttu-id="1f3f7-146">**(Top)**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-146">**(Top)**</span></span>  
 <span data-ttu-id="1f3f7-147">Especifique que a consulta incluirá uma cláusula TOP, que retorna apenas as primeiras linhas *n* ou primeiro percentual *n* de linhas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-147">Specify hat the query will include a TOP clause, which returns only the first *n* rows or first *n* percentage of rows in the result set.</span></span> <span data-ttu-id="1f3f7-148">O padrão é que a consulta retorne as primeiras 10 linhas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-148">The default is that the query returns the first 10 rows in the result set.</span></span>  
  
 <span data-ttu-id="1f3f7-149">Use essa caixa para alterar o número de linhas para retornar ou especificar uma porcentagem diferente.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-149">Use this box to change the number of rows to return or to specify a different percentage.</span></span> <span data-ttu-id="1f3f7-150">(Aplica-se apenas para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou posterior.)</span><span class="sxs-lookup"><span data-stu-id="1f3f7-150">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later.)</span></span>  
  
 <span data-ttu-id="1f3f7-151">**Expression**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-151">**Expression**</span></span>  
 <span data-ttu-id="1f3f7-152">Especifique o número ou porcentagem de linhas que a consulta retornará.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-152">Specify the number or percentage of rows that the query will return.</span></span> <span data-ttu-id="1f3f7-153">Se você definir **Percentual** como Sim, esse número será a porcentagem de linhas que a consulta retornará; se você definir **Percentual** como Não, ele representará o número de linhas a serem retornadas.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-153">If you set **Percent** to Yes, this number is the percentage of rows the query will return; if you set **Percent** to No, it represents the number of rows to return.</span></span> <span data-ttu-id="1f3f7-154">(Aplica-se apenas para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versão 7.0 ou posterior.)</span><span class="sxs-lookup"><span data-stu-id="1f3f7-154">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="1f3f7-155">**Percent**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-155">**Percent**</span></span>  
 <span data-ttu-id="1f3f7-156">Especifique que a consulta retornará apenas os primeiros porcentuais de linhas *n* no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-156">Specify that the query will return only the first *n* percent of rows in the result set.</span></span> <span data-ttu-id="1f3f7-157">(Aplica-se apenas para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versão 7.0 ou posterior.)</span><span class="sxs-lookup"><span data-stu-id="1f3f7-157">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="1f3f7-158">**With Ties**</span><span class="sxs-lookup"><span data-stu-id="1f3f7-158">**With Ties**</span></span>  
 <span data-ttu-id="1f3f7-159">Especifique que a exibição incluirá uma cláusula WITH TIES.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-159">Specify that the view will include a WITH TIES clause.</span></span> <span data-ttu-id="1f3f7-160">O WITH TIES é útil se uma exibição incluir uma cláusula ORDER BY e uma cláusula TOP com base em porcentagem.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-160">WITH TIES is useful if a view includes an ORDER BY clause and a TOP clause based on percentage.</span></span> <span data-ttu-id="1f3f7-161">Se essa opção for determinada, e se a porcentagem de corte se encontrar no meio de um conjunto de linhas com valores idênticos na cláusula ORDER BY, a exibição será estendida para incluir todas as respectivas linhas.</span><span class="sxs-lookup"><span data-stu-id="1f3f7-161">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the ORDER BY clause, the view is extended to include all such rows.</span></span> <span data-ttu-id="1f3f7-162">(Aplica-se apenas para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versão 7.0 ou posterior.)</span><span class="sxs-lookup"><span data-stu-id="1f3f7-162">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f3f7-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1f3f7-163">See Also</span></span>  
 <span data-ttu-id="1f3f7-164">[Consultar com parâmetros &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1f3f7-164">[Query with Parameters &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1f3f7-165">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="1f3f7-165">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
