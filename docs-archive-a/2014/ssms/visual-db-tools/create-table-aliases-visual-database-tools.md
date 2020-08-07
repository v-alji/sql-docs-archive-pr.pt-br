---
title: Criar aliases de tabelas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table aliases [SQL Server]
- aliases [SQL Server], tables
ms.assetid: 49e61e85-8abf-4ca7-8c70-7e9f8f1078bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f9e6269fe6e24e8d98922094e799fbf4b5af584
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574995"
---
# <a name="create-table-aliases-visual-database-tools"></a><span data-ttu-id="647f6-102">Criar aliases de tabelas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="647f6-102">Create Table Aliases (Visual Database Tools)</span></span>
  <span data-ttu-id="647f6-103">Os aliases podem facilitar o trabalho com nomes de tabela.</span><span class="sxs-lookup"><span data-stu-id="647f6-103">Aliases can make it easier to work with table names.</span></span> <span data-ttu-id="647f6-104">Usar aliases é útil quando:</span><span class="sxs-lookup"><span data-stu-id="647f6-104">Using aliases is helpful when:</span></span>  
  
-   <span data-ttu-id="647f6-105">Você quer tornar a instrução no [Painel SQL](visual-database-tools.md) mais curta e fácil de ser lida.</span><span class="sxs-lookup"><span data-stu-id="647f6-105">You want to make the statement in the [SQL Pane](visual-database-tools.md) shorter and easier to read.</span></span>  
  
-   <span data-ttu-id="647f6-106">Você se refere frequentemente ao nome de tabela em sua consulta – como em nomes de coluna qualificados – e quer estar seguro de estar dentro de um limite de comprimento de caracteres específico na sua consulta.</span><span class="sxs-lookup"><span data-stu-id="647f6-106">You refer to the table name often in your query - such as in qualifying column names - and want to be sure you stay within a specific character-length limit for your query.</span></span> <span data-ttu-id="647f6-107">(alguns bancos de dados impõem um comprimento máximo para as consultas).</span><span class="sxs-lookup"><span data-stu-id="647f6-107">(Some databases impose a maximum length for queries.)</span></span>  
  
-   <span data-ttu-id="647f6-108">Você está trabalhando com várias instâncias da mesma tabela (como em uma autojunção) e precisa um modo para se referir a uma instância ou a outra.</span><span class="sxs-lookup"><span data-stu-id="647f6-108">You are working with multiple instances of the same table (such as in a self-join) and need a way to refer to one instance or the other.</span></span>  
  
 <span data-ttu-id="647f6-109">Por exemplo, você pode criar um alias `"e"` para um nome de tabela `employee`_`information`e então referir-se à tabela como `"e"` durante o resto da consulta.</span><span class="sxs-lookup"><span data-stu-id="647f6-109">For example, you can create an alias `"e"` for a table name `employee`_`information`, and then refer to the table as `"e"` throughout the rest of the query.</span></span>  
  
### <a name="to-create-an-alias-for-a-table-or-table-valued-object"></a><span data-ttu-id="647f6-110">Para criar um alias para uma tabela ou objeto com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="647f6-110">To create an alias for a table or table-valued object</span></span>  
  
1.  <span data-ttu-id="647f6-111">Adicione a tabela ou o objeto com valor de tabela à sua consulta.</span><span class="sxs-lookup"><span data-stu-id="647f6-111">Add the table or table-valued object to your query.</span></span>  
  
2.  <span data-ttu-id="647f6-112">No **Painel de Diagrama**, clique com o botão direito do mouse no objeto para o qual você deseja criar um alias e selecione **Propriedades** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="647f6-112">In the **Diagram Pane**, right-click the object for which you want to create an alias, then select **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="647f6-113">Na janela **Propriedades** , digite o alias no campo **Alias** .</span><span class="sxs-lookup"><span data-stu-id="647f6-113">In the **Properties** window, enter the alias in the **Alias** field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647f6-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="647f6-114">See Also</span></span>  
 <span data-ttu-id="647f6-115">[Adicionar tabelas a consultas &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="647f6-115">[Add Tables to Queries &#40;Visual Database Tools&#41;](add-tables-to-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="647f6-116">[Classificar e agrupar resultados de consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="647f6-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="647f6-117">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="647f6-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="647f6-118">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="647f6-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
