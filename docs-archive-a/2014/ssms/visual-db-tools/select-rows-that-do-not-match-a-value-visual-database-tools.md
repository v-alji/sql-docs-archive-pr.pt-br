---
title: Selecionar linhas que não correspondem a um valor (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], rows not matching value
- row not matching value [SQL Server]
- NOT operator [Visual Database Tools]
- search criteria [SQL Server], rows not matching value
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 412ec93cbfedc87e92da9e86c7e4c7455919722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682043"
---
# <a name="select-rows-that-do-not-match-a-value-visual-database-tools"></a><span data-ttu-id="976dc-102">Selecionar linhas que não correspondem a um valor (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="976dc-102">Select Rows That Do Not Match a Value (Visual Database Tools)</span></span>
  <span data-ttu-id="976dc-103">Para localizar linhas que não correspondem a um valor, use o operador NOT.</span><span class="sxs-lookup"><span data-stu-id="976dc-103">To find rows that do not match a value, use the NOT operator.</span></span>  
  
### <a name="to-find-rows-that-do-not-match-a-value"></a><span data-ttu-id="976dc-104">Para localizar linhas que não correspondem a um valor</span><span class="sxs-lookup"><span data-stu-id="976dc-104">To find rows that do not match a value</span></span>  
  
1.  <span data-ttu-id="976dc-105">Se você ainda não o fez, adicione as colunas ou expressões que pretende usar nos critérios de pesquisa do [Painel Critérios](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="976dc-105">If you have not done so already, add the columns or expressions that you want to use within your search condition to the [Criteria pane](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="976dc-106">Localize a linha que contém a coluna de dados ou expressão a ser pesquisada e, em seguida, na coluna de grade **Filtro** , digite o operador NOT seguido de um valor de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="976dc-106">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the NOT operator followed by a search value.</span></span>  
  
 <span data-ttu-id="976dc-107">Por exemplo, para localizar todas as linhas em uma tabela de `products` em que os valores da coluna de código do produto começam com um caractere diferente de "A", você pode digitar um critério de pesquisa como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="976dc-107">For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:</span></span>  
  
```  
NOT LIKE 'A%'  
```  
  
## <a name="see-also"></a><span data-ttu-id="976dc-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="976dc-108">See Also</span></span>  
 <span data-ttu-id="976dc-109">[Regras para inserir valores de pesquisa &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="976dc-109">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="976dc-110">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="976dc-110">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
