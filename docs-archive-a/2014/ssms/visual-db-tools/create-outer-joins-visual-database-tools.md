---
title: Criar junções externas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- joins [SQL Server], outer
ms.assetid: 18de47b1-f936-427d-b852-fe6d20334f71
author: stevestein
ms.author: sstein
ms.openlocfilehash: f02c0be049e2e75e1a657bb3c027d20430d562cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685410"
---
# <a name="create-outer-joins-visual-database-tools"></a><span data-ttu-id="3ae6c-102">Criar junções externas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3ae6c-102">Create Outer Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="3ae6c-103">Por padrão, o [Designer de Consulta e Exibição](visual-database-tools.md) cria uma junção interna entre tabelas.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-103">By default, the [Query and View Designer](visual-database-tools.md) creates an inner join between tables.</span></span> <span data-ttu-id="3ae6c-104">As junções internas eliminam as linhas que não correspondem a uma linha da outra tabela.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-104">Inner joins eliminate the rows that do not match with a row from the other table.</span></span> <span data-ttu-id="3ae6c-105">Entretanto, as junções externas retornam todas as linhas de pelo menos uma das tabelas ou exibições mencionadas na cláusula FROM, contanto que essas linhas atendam algum critério de pesquisa WHERE ou HAVING.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-105">Outer joins, however, return all rows from at least one of the tables or views mentioned in the FROM clause, as long as those rows meet any WHERE or HAVING search conditions.</span></span> <span data-ttu-id="3ae6c-106">Se você quiser incluir linhas de dados no conjunto de resultados que não tenha uma correspondência na tabela unida, será possível criar uma junção externa.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-106">If you want to include data rows in the result set that do not have a match in the joined table, you can create an outer join.</span></span>  
  
 <span data-ttu-id="3ae6c-107">Quando você criar uma junção externa, a ordem em que as tabelas aparecem na instrução SQL (como refletido no painel SQL) é significante.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-107">When you create an outer join, the order in which tables appear in the SQL statement (as reflected in the SQL pane) is significant.</span></span> <span data-ttu-id="3ae6c-108">A primeira tabela que você adiciona se torna a tabela "esquerda" e a segunda se torna a tabela "direita."</span><span class="sxs-lookup"><span data-stu-id="3ae6c-108">The first table you add becomes the "left" table and the second table becomes the "right" table.</span></span> <span data-ttu-id="3ae6c-109">(A ordem real em que as tabelas aparecem no [painel Diagrama](diagram-pane-visual-database-tools.md) não é significativa.) Quando você especificar uma junção externa esquerda ou direita, estará se referindo à ordem na qual as tabelas foram adicionadas à consulta e à ordem na qual elas aparecem na instrução SQL no [painel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ae6c-109">(The actual order in which the tables appear in the [Diagram pane](diagram-pane-visual-database-tools.md) is not significant.) When you specify a left or right outer join, you are referring to the order in which the tables were added to the query and to the order in which they appear in the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-an-outer-join"></a><span data-ttu-id="3ae6c-110">Para criar uma junção externa</span><span class="sxs-lookup"><span data-stu-id="3ae6c-110">To create an outer join</span></span>  
  
1.  <span data-ttu-id="3ae6c-111">Crie a junção, automática ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-111">Create the join, either automatically or manually.</span></span> <span data-ttu-id="3ae6c-112">Para obter detalhes, consulte [Unir tabelas automaticamente &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) ou [Unir tabelas manualmente &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ae6c-112">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) or [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="3ae6c-113">Selecione a linha de junção no painel Diagrama e, depois, no menu **Designer de Consultas**, escolha **Selecionar Todas as Linhas de \<tablename>** , selecionando o comando que inclui a tabela com as linhas extras que você deseja incluir.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-113">Select the join line in the Diagram pane, and then from the **Query Designer** menu, choose **Select All Rows from \<tablename>**, selecting the command that includes the table whose extra rows you want to include.</span></span>  
  
    -   <span data-ttu-id="3ae6c-114">Escolha a primeira tabela para criar uma junção externa esquerda.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-114">Choose the first table to create a left outer join.</span></span>  
  
    -   <span data-ttu-id="3ae6c-115">Escolha a segunda tabela para criar uma junção externa direita.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-115">Choose the second table to create a right outer join.</span></span>  
  
    -   <span data-ttu-id="3ae6c-116">Escolha ambas as tabelas para criar uma junção externa completa.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-116">Choose both tables to create a full outer join.</span></span>  
  
 <span data-ttu-id="3ae6c-117">Quando você especificar uma junção externa, o Designer de Consulta e Exibição modificará a linha de junção para indicar uma junção externa.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-117">When you specify an outer join, the Query and View Designer modifies the join line to indicate an outer join.</span></span>  
  
 <span data-ttu-id="3ae6c-118">Além disso, o Designer de Consulta e Exibição modifica a instrução SQL no painel SQL para refletir a mudança em tipo de junção, conforme mostrado na seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="3ae6c-118">In addition, the Query and View Designer modifies the SQL statement in the SQL pane to reflect the change in join type, as shown in the following statement:</span></span>  
  
```  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
```  
  
 <span data-ttu-id="3ae6c-119">Como uma junção externa inclui linhas não correspondentes, você pode usá-la para encontrar linhas que violam as restrições de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-119">Because an outer join includes unmatched rows, you can use it to find rows that violate foreign key constraints.</span></span> <span data-ttu-id="3ae6c-120">Para fazer isso, crie uma junção externa e, depois, adicione um critério de pesquisa para encontrar linhas em que a coluna de chave primária da tabela mais à direita seja nula.</span><span class="sxs-lookup"><span data-stu-id="3ae6c-120">To do so, you create an outer join and then add a search condition to find rows in which the primary key column of the rightmost table is null.</span></span> <span data-ttu-id="3ae6c-121">Por exemplo, a seguinte junção externa encontra linhas na tabela `employee` que não têm linhas correspondentes na tabela `jobs` :</span><span class="sxs-lookup"><span data-stu-id="3ae6c-121">For example, the following outer join finds rows in the `employee` table that do not have corresponding rows in the `jobs` table:</span></span>  
  
```  
SELECT employee.emp_id, employee.job_id  
FROM employee LEFT OUTER JOIN jobs   
   ON employee.job_id = jobs.job_id  
WHERE (jobs.job_id IS NULL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ae6c-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ae6c-122">See Also</span></span>  
 <span data-ttu-id="3ae6c-123">[Consultar com junções &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3ae6c-123">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3ae6c-124">Caixa de diálogo Unir &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3ae6c-124">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
