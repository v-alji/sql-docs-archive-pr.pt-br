---
title: Criar consultas com parâmetros não nomeados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0ea53afd1fa4d44390f5805d6b28494428608b90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569002"
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a><span data-ttu-id="380e0-102">Criar consultas com parâmetros não nomeados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="380e0-102">Create Queries with Unnamed Parameters (Visual Database Tools)</span></span>
  <span data-ttu-id="380e0-103">Você pode criar uma consulta com um parâmetro não nomeado especificando um ponto de interrogação (?) com um espaço reservado para um valor literal.</span><span class="sxs-lookup"><span data-stu-id="380e0-103">You can create a query with an unnamed parameter by specifying a question mark (?) as a placeholder for a literal value.</span></span> <span data-ttu-id="380e0-104">O Designer de Consulta e Exibição lhe dará um nome temporário.</span><span class="sxs-lookup"><span data-stu-id="380e0-104">Query and View Designer will give it a temporary name.</span></span> <span data-ttu-id="380e0-105">É possível especificar vários parâmetros não nomeados na consulta, na medida do necessário.</span><span class="sxs-lookup"><span data-stu-id="380e0-105">You can specify as many unnamed parameters in the query as you need.</span></span>  
  
 <span data-ttu-id="380e0-106">Quando você executar a consulta no Designer de Consulta e Exibição, a caixa de diálogo Parâmetros de Consulta será exibida com o nome temporário.</span><span class="sxs-lookup"><span data-stu-id="380e0-106">When you run the query in the Query and View Designer, the Query Parameters Dialog Box is displayed with the temporary name.</span></span>  
  
### <a name="to-specify-an-unnamed-parameter"></a><span data-ttu-id="380e0-107">Para especificar um parâmetro não nomeado</span><span class="sxs-lookup"><span data-stu-id="380e0-107">To specify an unnamed parameter</span></span>  
  
1.  <span data-ttu-id="380e0-108">Adicione as colunas ou expressões que você deseja pesquisar no painel [Critérios](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="380e0-108">Add the columns or expressions that you want to search to the [Criteria pane](visual-database-tools.md).</span></span> <span data-ttu-id="380e0-109">Se você não quiser que as colunas ou expressões a ser pesquisadas apareçam na saída da consulta, remova-as como colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="380e0-109">If you do not want the search columns or expressions to appear in the query output, remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="380e0-110">Localize a linha contendo a expressão ou coluna de dados a ser pesquisada e, depois, na coluna de grade **Filtro** digite um ponto de interrogação (?).</span><span class="sxs-lookup"><span data-stu-id="380e0-110">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter a question mark (?).</span></span>  
  
     <span data-ttu-id="380e0-111">Por padrão, o Designer de Consulta e Exibição adiciona o operador "=".</span><span class="sxs-lookup"><span data-stu-id="380e0-111">By default, the Query and View Designer adds the "=" operator.</span></span> <span data-ttu-id="380e0-112">Porém, você poderá editar a célula para substituir ">", "<", ou qualquer outro operador de comparação de SQL.</span><span class="sxs-lookup"><span data-stu-id="380e0-112">However, you can edit the cell to substitute ">", "<", or any other SQL comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="380e0-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="380e0-113">See Also</span></span>  
 [<span data-ttu-id="380e0-114">Consultar com parâmetros &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="380e0-114">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
