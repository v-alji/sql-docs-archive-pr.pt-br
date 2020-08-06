---
title: Unir tabelas manualmente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- manual joins [SQL Server]
- joins [SQL Server], manual
- joins [SQL Server], creating
ms.assetid: 9c785356-646b-4c87-82d4-25efd6051d9d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 83f7615be3f5f18164dd3ca0f62ef6cbd9167be3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678497"
---
# <a name="join-tables-manually-visual-database-tools"></a><span data-ttu-id="2add4-102">Unir tabelas manualmente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2add4-102">Join Tables Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="2add4-103">Quando você adiciona duas (ou mais) tabelas a uma consulta, o [Designer de Consulta e Exibição](visual-database-tools.md) tenta uni-las com base em dados comuns ou em informações armazenadas no banco de dados sobre como as tabelas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2add4-103">When you add two (or more) tables to a query, the [Query and View Designer](visual-database-tools.md) attempts to join them based on common data or on information stored in the database about how tables are related.</span></span> <span data-ttu-id="2add4-104">Para obter detalhes, consulte [Unir tabelas automaticamente &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2add4-104">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md).</span></span> <span data-ttu-id="2add4-105">Entretanto, se o Designer de Consulta e Exibição não uniu as tabelas automaticamente, ou se você quiser criar outras condições de junção entre tabelas, será possível unir as tabelas manualmente.</span><span class="sxs-lookup"><span data-stu-id="2add4-105">However, if the Query and View Designer has not joined the tables automatically, or if you want to create additional join conditions between tables, you can join tables manually.</span></span>  
  
 <span data-ttu-id="2add4-106">Você pode criar junções com base em comparações entre duas colunas, não apenas colunas que contêm a mesma informação.</span><span class="sxs-lookup"><span data-stu-id="2add4-106">You can create joins based on comparisons between any two columns, not just columns that contain the same information.</span></span> <span data-ttu-id="2add4-107">Por exemplo, se seu banco de dados contiver duas tabelas, `titles` e `roysched`, você poderá comparar valores na coluna `ytd_sales` da tabela `titles` com as colunas `lorange` e `hirange` na tabela `roysched` .</span><span class="sxs-lookup"><span data-stu-id="2add4-107">For example, if your database contains two tables, `titles` and `roysched`, you can compare values in the `ytd_sales` column of the `titles` table against the `lorange` and `hirange` columns in the `roysched` table.</span></span> <span data-ttu-id="2add4-108">A criação dessa junção lhe permitiria encontrar títulos para pagamentos de royalty referentes a quedas de vendas acumuladas no ano entre os intervalos altos e baixos.</span><span class="sxs-lookup"><span data-stu-id="2add4-108">Creating this join would allow you to find titles for which the year-to-date sales falls between the low and high ranges for the royalty payments.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="2add4-109">A junção funciona de forma rápida quando as colunas na condição de junção são indexadas.</span><span class="sxs-lookup"><span data-stu-id="2add4-109">Joins work fastest if the columns in the join condition have been indexed.</span></span> <span data-ttu-id="2add4-110">Em alguns casos, a união de colunas não indexadas pode resultar em uma consulta lenta.</span><span class="sxs-lookup"><span data-stu-id="2add4-110">In some cases, joining on unindexed columns can result in a slow query.</span></span>  
  
### <a name="to-manually-join-tables-or-table-structured-objects"></a><span data-ttu-id="2add4-111">Para unir manualmente tabelas ou objetos estruturados por tabela</span><span class="sxs-lookup"><span data-stu-id="2add4-111">To manually join tables or table-structured objects</span></span>  
  
1.  <span data-ttu-id="2add4-112">Adicione ao [painel Diagrama](diagram-pane-visual-database-tools.md) os objetos que deseja unir.</span><span class="sxs-lookup"><span data-stu-id="2add4-112">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the objects you want to join.</span></span>  
  
2.  <span data-ttu-id="2add4-113">Arraste o nome da coluna de junção para a primeira tabela ou objeto estruturado por tabela e solte-o sobre a coluna relacionada na segunda tabela ou objeto estruturado por tabela.</span><span class="sxs-lookup"><span data-stu-id="2add4-113">Drag the name of the join column in the first table or table-structured object and drop it onto the related column in the second table or table-structured object.</span></span> <span data-ttu-id="2add4-114">Você não pode basear uma junção em colunas `text`, `ntext`ou i`mage`.</span><span class="sxs-lookup"><span data-stu-id="2add4-114">You cannot base a join on `text`, `ntext`, or i`mage` columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2add4-115">As colunas de junção devem ter os mesmos tipos de dados (ou compatíveis).</span><span class="sxs-lookup"><span data-stu-id="2add4-115">The join columns must be of the same (or compatible) data types.</span></span> <span data-ttu-id="2add4-116">Por exemplo, se a coluna de junção na primeira tabela for uma data, você deve relacionar isto a uma coluna de data na segunda tabela.</span><span class="sxs-lookup"><span data-stu-id="2add4-116">For example, if the join column in the first table is a date, you must relate it to a date column in the second table.</span></span> <span data-ttu-id="2add4-117">Por outro lado, se a primeira coluna de junção for um inteiro, a coluna de junção relacionada também deverá ser do tipo de dados inteiro, mas poderá ser de um tamanho diferente.</span><span class="sxs-lookup"><span data-stu-id="2add4-117">On the other hand, if the first join column is an integer, the related join column must also be of an integer data type, but it can be a different size.</span></span> <span data-ttu-id="2add4-118">O Designer de Consulta e Exibição não verificará os tipos de dados das colunas que você usa para criar uma junção, mas quando você executar a consulta, o banco de dados exibirá um erro se os tipos de dados não forem compatíveis.</span><span class="sxs-lookup"><span data-stu-id="2add4-118">The Query and View Designer will not check the data types of the columns you use to create a join, but when you execute the query, the database will display an error if the data types are not compatible.</span></span>  
  
3.  <span data-ttu-id="2add4-119">Se necessário, altere o operador de junção; por padrão, o operador é um sinal de igual (=).</span><span class="sxs-lookup"><span data-stu-id="2add4-119">If necessary, change the join operator; by default, the operator is an equal sign (=).</span></span> <span data-ttu-id="2add4-120">Para obter detalhes, consulte [Modificar operadores de junção &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2add4-120">For details, see [Modify Join Operators &#40;Visual Database Tools&#41;](modify-join-operators-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="2add4-121">O Designer de Consulta e Exibição adiciona uma cláusula INNER JOIN à instrução SQL no [painel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2add4-121">The Query and View Designer adds an INNER JOIN clause to the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="2add4-122">Você pode alterar o tipo por uma junção externa.</span><span class="sxs-lookup"><span data-stu-id="2add4-122">You can change the type to an outer join.</span></span> <span data-ttu-id="2add4-123">Para obter detalhes, veja [Criar junções externas &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2add4-123">For details see [Create Outer Joins &#40;Visual Database Tools&#41;](create-outer-joins-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2add4-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2add4-124">See Also</span></span>  
 [<span data-ttu-id="2add4-125">Consultar com junções &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2add4-125">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
