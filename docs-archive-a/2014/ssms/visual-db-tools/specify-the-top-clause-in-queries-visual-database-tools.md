---
title: Especificar a cláusula TOP em consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- TOP clause, queries
- percentage of rows returned [SQL Server]
- number of rows
- search conditions [SQL Server], TOP clause
- restricting rows returned
- search criteria [SQL Server], limiting rows returned
- inspecting portion of results
- limiting rows returned
- search criteria [SQL Server], TOP clause
ms.assetid: ba7d7c10-9bb3-4d9b-90b0-5fa94ecae59b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8228779703b1bbe3753f1e2728e83b4b5c3a3d17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684970"
---
# <a name="specify-the-top-clause-in-queries-visual-database-tools"></a><span data-ttu-id="7d1a2-102">Especificar a cláusula TOP em consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7d1a2-102">Specify the TOP Clause in Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="7d1a2-103">A cláusula TOP retorna somente as primeiras linhas *n* ou *n percent* de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="7d1a2-103">The TOP clause returns only the first *n* or *n percent* rows from a query.</span></span> <span data-ttu-id="7d1a2-104">A cláusula TOP é útil quando se pretende inspecionar uma parte de seus resultados para descobrir se sua consulta faz o esperado sem despender os recursos necessários para retornar todos os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="7d1a2-104">The TOP clause is useful when you want to inspect a portion of your results to find out if your query does what you expect it to do, without taking the resources necessary to return all of the query results.</span></span>  
  
### <a name="to-specify-the-top-clause-in-queries"></a><span data-ttu-id="7d1a2-105">Para especificar a cláusula TOP em consultas</span><span class="sxs-lookup"><span data-stu-id="7d1a2-105">To specify the TOP clause in queries</span></span>  
  
1.  <span data-ttu-id="7d1a2-106">Abra uma consulta no Gerenciador de Soluções ou crie uma consulta nova.</span><span class="sxs-lookup"><span data-stu-id="7d1a2-106">Open a query from Solution Explorer or create a new one.</span></span>  
  
2.  <span data-ttu-id="7d1a2-107">No menu **Exibir** , clique em **Janela Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7d1a2-107">From the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="7d1a2-108">Na **Janela de Propriedades**, localize e expanda a propriedade **Especificação Top** .</span><span class="sxs-lookup"><span data-stu-id="7d1a2-108">In the **Properties Window**, locate and expand the **Top Specification** property.</span></span>  
  
4.  <span data-ttu-id="7d1a2-109">Clique na propriedade filho **(Top)** e defina-a como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="7d1a2-109">Click the **(Top)** child property and set it to **Yes**.</span></span>  
  
5.  <span data-ttu-id="7d1a2-110">Na propriedade filho **Expressão** , digite uma expressão com resultado numérico (por exemplo, "10" ou "2\*5").</span><span class="sxs-lookup"><span data-stu-id="7d1a2-110">In the **Expression** child property, type an expression that has a numeric result (for example, "10" or "2\*5").</span></span>  
  
6.  <span data-ttu-id="7d1a2-111">Clique na propriedade filho **Porcentagem** e indique se a propriedade **Expressão** deverá ser tratada como percentual de todas as linhas retornadas (Sim) ou como o número absoluto de linhas retornadas (Não).</span><span class="sxs-lookup"><span data-stu-id="7d1a2-111">Click the **Percent** child property and indicate whether or not to treat the **Expression** property as a percentage of all rows returned (Yes) or as the absolute number of rows returned (No).</span></span>  
  
7.  <span data-ttu-id="7d1a2-112">Se sua consulta usar a cláusula ORDER BY, clique na propriedade filho **Com Ligações** e escolha **Sim** para exibir todas as linhas de um grupo se apenas parte do grupo estiver incluída ou escolha **Não** para truncar as linhas.</span><span class="sxs-lookup"><span data-stu-id="7d1a2-112">If your query uses the ORDER BY clause, click the **With Ties** child property and choose **Yes** to display all rows in a group if only part of the group is included or **No** to truncate them.</span></span>  
  
 <span data-ttu-id="7d1a2-113">À medida que você trabalha com o procedimento precedente, observe que a cláusula TOP, exibida no painel SQL, altera-se para refletir as configurações atuais das propriedades.</span><span class="sxs-lookup"><span data-stu-id="7d1a2-113">As you work through the preceding procedure, notice that the TOP clause, displayed in the SQL pane, changes to reflect the current settings of the properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d1a2-114">Além disso, você pode alterar os valores das propriedades filho de **Especificação Top** editando a cláusula TOP no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="7d1a2-114">You can also change the values of the child properties of the **Top Specification** by editing the TOP clause in the SQL pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1a2-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d1a2-115">See Also</span></span>  
 <span data-ttu-id="7d1a2-116">[Tópicos de instruções sobre como criar consultas e exibições &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7d1a2-116">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7d1a2-117">Propriedades de consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7d1a2-117">Query Properties &#40;Visual Database Tools&#41;</span></span>](query-properties-visual-database-tools.md)  
  
  
