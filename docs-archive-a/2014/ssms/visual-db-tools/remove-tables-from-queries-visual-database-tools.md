---
title: Renomear tabelas de consultas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting tables
- removing tables
- dropping tables
- queries [SQL Server], tables
ms.assetid: 8fea0b4f-99b7-4050-8d6f-a97ffb839619
author: stevestein
ms.author: sstein
ms.openlocfilehash: fab5380e13742f3cd289ce17f26ad2e5fb9089ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573359"
---
# <a name="remove-tables-from-queries-visual-database-tools"></a><span data-ttu-id="427c3-102">Remover tabelas de consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="427c3-102">Remove Tables from Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="427c3-103">Você pode remover uma tabela ou qualquer objeto com valor de tabela da consulta.</span><span class="sxs-lookup"><span data-stu-id="427c3-103">You can remove a table - or any table-valued object - from the query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="427c3-104">Removendo uma tabela ou objeto com valor de tabela não exclui nada do banco de dados; só remove isto da consulta atual.</span><span class="sxs-lookup"><span data-stu-id="427c3-104">Removing a table or table-valued object does not delete anything from the database; it only removes it from the current query.</span></span> <span data-ttu-id="427c3-105">Para obter detalhes sobre como remover uma tabela de um banco de dados, consulte [excluir tabelas &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="427c3-105">For details about removing a table from a database, see [Delete Tables &#40;Database Engine&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span></span>  
  
### <a name="to-remove-a-table-or-table-structured-object"></a><span data-ttu-id="427c3-106">Para remover uma tabela ou objeto estruturado por tabela</span><span class="sxs-lookup"><span data-stu-id="427c3-106">To remove a table or table-structured object</span></span>  
  
-   <span data-ttu-id="427c3-107">No **Painel de Diagrama**, selecione a tabela, a exibição, a função definida pelo usuário, o sinônimo ou a consulta e, depois, pressione DELETE ou clique com o botão direito do mouse no objeto e escolha **Remover** na caixa de diálogo resultante.</span><span class="sxs-lookup"><span data-stu-id="427c3-107">In the **Diagram Pane**, select the table, view, user-defined function, synonym, or query, and then press DELETE, or right-click the object and then choose **Remove** in the resulting dialog box.</span></span> <span data-ttu-id="427c3-108">Você pode selecionar e remover vários objetos de uma vez.</span><span class="sxs-lookup"><span data-stu-id="427c3-108">You can select and remove multiple objects at one time.</span></span>  
  
     <span data-ttu-id="427c3-109">-ou-</span><span class="sxs-lookup"><span data-stu-id="427c3-109">-or-</span></span>  
  
-   <span data-ttu-id="427c3-110">Remova todas as referências ao objeto no **Painel SQL**.</span><span class="sxs-lookup"><span data-stu-id="427c3-110">Remove all references to the object in the **SQL Pane.**</span></span>  
  
 <span data-ttu-id="427c3-111">Quando você remover uma tabela ou objeto com valor de tabela, o Designer de Consulta e Exibição removerá automaticamente as junções que envolvem aquela tabela ou objeto com valor de tabela e removerá as referências às colunas do objeto no **Painel SQL** e no **Painel de Critérios**.</span><span class="sxs-lookup"><span data-stu-id="427c3-111">When you remove a table or table-valued object, the Query and View Designer automatically removes joins that involve that table or table-valued object and removes references to the object's columns in the **SQL Pane** and **Criteria Pane**.</span></span> <span data-ttu-id="427c3-112">Porém, se a consulta contiver expressões complexas que envolvam o objeto, o objeto não será removido automaticamente até que todas as referências a ele sejam removidas.</span><span class="sxs-lookup"><span data-stu-id="427c3-112">However, if the query contains complex expressions involving the object, the object is not automatically removed until all references to it are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427c3-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="427c3-113">See Also</span></span>  
 <span data-ttu-id="427c3-114">[Adicionar tabelas a consultas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="427c3-114">[Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="427c3-115">[Criar aliases de tabela &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="427c3-115">[Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span></span>  
 <span data-ttu-id="427c3-116">[Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="427c3-116">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="427c3-117">[Resumir os resultados da consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="427c3-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="427c3-118">Executar operações básicas com consultas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="427c3-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
