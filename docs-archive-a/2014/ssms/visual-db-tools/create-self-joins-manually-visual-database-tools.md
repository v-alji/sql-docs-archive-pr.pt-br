---
title: Criar autojunções manualmente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- self-joins
- manual joins [SQL Server]
- joins [SQL Server], self
ms.assetid: 910ed516-cb84-481b-95d0-cba3e89afdba
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31e125fdfe0f7f285ea679cfe85356d1aa10353a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574998"
---
# <a name="create-self-joins-manually-visual-database-tools"></a><span data-ttu-id="085f5-102">Criar autojunções manualmente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="085f5-102">Create Self-Joins Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="085f5-103">A autojunção de uma tabela pode ser feita, mesmo se a tabela não tiver uma relação reflexiva no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="085f5-103">You can join a table to itself even if the table does not have a reflexive relationship in the database.</span></span> <span data-ttu-id="085f5-104">Por exemplo, você pode usar uma autojunção para encontrar pares de autores que moram na mesma cidade.</span><span class="sxs-lookup"><span data-stu-id="085f5-104">For example, you can use a self-join to find pairs of authors living in the same city.</span></span>  
  
 <span data-ttu-id="085f5-105">Como com qualquer junção, uma autojunção requer pelo menos duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="085f5-105">As with any join, a self-join requires at least two tables.</span></span> <span data-ttu-id="085f5-106">A diferença é que, em vez de acrescentar uma segunda tabela à consulta, você adicionar uma segunda instância da mesma tabela.</span><span class="sxs-lookup"><span data-stu-id="085f5-106">The difference is that, instead of adding a second table to the query, you add a second instance of the same table.</span></span> <span data-ttu-id="085f5-107">Dessa forma, você pode comparar uma coluna na primeira instância da tabela para a mesma coluna na segunda instância, o que permite comparar os valores em uma coluna entre si.</span><span class="sxs-lookup"><span data-stu-id="085f5-107">That way, you can compare a column in the first instance of the table to the same column in the second instance, which allows you to compare the values in a column to each other.</span></span> <span data-ttu-id="085f5-108">O [Designer de Consulta e Exibição](visual-database-tools.md) atribui um alias à segunda instância da tabela.</span><span class="sxs-lookup"><span data-stu-id="085f5-108">The [Query and View Designer](visual-database-tools.md) assigns an alias to the second instance of the table.</span></span>  
  
 <span data-ttu-id="085f5-109">Por exemplo, se você estiver criando uma autojunção para encontrar todos os pares de autores em Berkeley, você comparará a coluna `city` na primeira instância da tabela com a coluna `city` na segunda instância.</span><span class="sxs-lookup"><span data-stu-id="085f5-109">For example, if you are creating a self-join to find all pairs of authors within Berkeley, you compare the `city` column in the first instance of the table against the `city` column in the second instance.</span></span> <span data-ttu-id="085f5-110">A consulta resultante pode ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="085f5-110">The resulting query might look like the following:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="085f5-111">A criação de uma autojunção normalmente requer várias condições de junção.</span><span class="sxs-lookup"><span data-stu-id="085f5-111">Creating a self-join often requires multiple join conditions.</span></span> <span data-ttu-id="085f5-112">Para entender o porquê, considere o resultado da consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="085f5-112">To understand why, consider the result of the preceding query:</span></span>  
  
```  
Cheryl Carson       Cheryl Carson  
Abraham Bennet      Abraham Bennet  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="085f5-113">A primeira linha é inútil; indica que Cheryl Carson mora na mesma cidade de Cheryl Carson.</span><span class="sxs-lookup"><span data-stu-id="085f5-113">The first row is useless; it indicates that Cheryl Carson lives in the same city as Cheryl Carson.</span></span> <span data-ttu-id="085f5-114">A segunda linha é igualmente inútil.</span><span class="sxs-lookup"><span data-stu-id="085f5-114">The second row is equally useless.</span></span> <span data-ttu-id="085f5-115">Para eliminar esses dados inúteis, você adiciona outra condição que retém somente as linhas de resultado onde os nomes de dois autores descrevem autores diferentes.</span><span class="sxs-lookup"><span data-stu-id="085f5-115">To eliminate this useless data, you add another condition retaining only those result rows in which the two author names describe different authors.</span></span> <span data-ttu-id="085f5-116">A consulta resultante pode ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="085f5-116">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             <> authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="085f5-117">O conjunto de resultados é aprimorado.</span><span class="sxs-lookup"><span data-stu-id="085f5-117">The result set is improved:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="085f5-118">Mas as duas linhas de resultado são redundantes.</span><span class="sxs-lookup"><span data-stu-id="085f5-118">But the two result rows are redundant.</span></span> <span data-ttu-id="085f5-119">A primeira diz que Carson mora na mesma cidade de Bennet, e a segunda diz que Bennet mora na mesma cidade de Carson.</span><span class="sxs-lookup"><span data-stu-id="085f5-119">The first says Carson lives in the same city as Bennet, and the second says the Bennet lives in the same city as Carson.</span></span> <span data-ttu-id="085f5-120">Para eliminar essa redundância, você pode alterar a segunda condição de junção de “não igual” para “menor que”.</span><span class="sxs-lookup"><span data-stu-id="085f5-120">To eliminate this redundancy, you can alter the second join condition from "not equals" to "less than."</span></span> <span data-ttu-id="085f5-121">A consulta resultante pode ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="085f5-121">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             < authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="085f5-122">E o conjunto de resultados tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="085f5-122">And the result set looks like this:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
```  
  
### <a name="to-create-a-self-join-manually"></a><span data-ttu-id="085f5-123">Para criar uma autojunção manualmente</span><span class="sxs-lookup"><span data-stu-id="085f5-123">To create a self-join manually</span></span>  
  
1.  <span data-ttu-id="085f5-124">Adicione ao painel [Diagrama](diagram-pane-visual-database-tools.md) a tabela ou o objeto com valor de tabela com os quais você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="085f5-124">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the table or table-valued object you want to work with.</span></span>  
  
2.  <span data-ttu-id="085f5-125">Adicione a mesma tabela novamente, de forma que o painel Diagrama exiba a mesma tabela ou o mesmo objeto com valor de tabela duas vezes no painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="085f5-125">Add the same table again, so that the Diagram pane shows the same table or table-valued object twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="085f5-126">O Designer de Consulta e Exibição atribui um alias à segunda instância adicionando um número sequencial ao nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="085f5-126">The Query and View Designer assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="085f5-127">Além disso, o Designer de Consulta e Exibição cria uma linha de junção entre as duas ocorrências da tabela ou do objeto com valor de tabela dentro do painel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="085f5-127">In addition, the Query and View Designer creates a join line between the two occurrences of the table or table-valued object within the Diagram pane.</span></span>  
  
3.  <span data-ttu-id="085f5-128">Clique com o botão direito do mouse na linha de junção e escolha **Propriedades** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="085f5-128">Right-click the join line and choose **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="085f5-129">Na janela Propriedades, clique em **Condição e Tipo de Junção** e clique nas **reticências (…)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="085f5-129">In the Properties window click **Join Condition and Type** and click the **ellipses (...)** to the right of the property.</span></span>  
  
5.  <span data-ttu-id="085f5-130">Na caixa de diálogo [Junção](join-dialog-box-visual-database-tools.md) , altere o operador de comparação entre as chaves primárias conforme requerido.</span><span class="sxs-lookup"><span data-stu-id="085f5-130">In the [Join Dialog Box](join-dialog-box-visual-database-tools.md) change the comparison operator between the primary keys as required.</span></span> <span data-ttu-id="085f5-131">Por exemplo, você pode alterar o operador para menor que (<).</span><span class="sxs-lookup"><span data-stu-id="085f5-131">For example, you might change the operator to less than (<).</span></span>  
  
6.  <span data-ttu-id="085f5-132">Crie a condição de junção adicional (por exemplo, authors.zip = authors1.zip) arrastando o nome da coluna de junção primária na primeira ocorrência da tabela ou objeto com valor de tabela, soltando na coluna correspondente na segunda ocorrência.</span><span class="sxs-lookup"><span data-stu-id="085f5-132">Create the additional join condition (for example, authors.zip = authors1.zip) by dragging the name of the primary join column in the first occurrence of the table or table-valued object and dropping it on the corresponding column in the second occurrence.</span></span>  
  
7.  <span data-ttu-id="085f5-133">Especifique outras opções para a consulta, como colunas de saída, critérios de pesquisa e ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="085f5-133">Specify other options for the query such as output columns, search conditions, and sort order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="085f5-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="085f5-134">See Also</span></span>  
 <span data-ttu-id="085f5-135">[Criar autojunções automaticamente &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="085f5-135">[Create Self-Joins Automatically &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="085f5-136">Consultar com junções &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="085f5-136">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
