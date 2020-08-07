---
title: Como o designer de consulta e exibição representa junções (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL pane [Visual Database Tools]
- joins [SQL Server], Query and View Designer
- Diagram pane [Visual Database Tools]
ms.assetid: 20a99dcb-83bd-4aa6-9139-92e2e5ba4887
author: stevestein
ms.author: sstein
ms.openlocfilehash: 55fdea533436f9fa7c2a902667b3166085c27e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574982"
---
# <a name="how-the-query-and-view-designer-represents-joins-visual-database-tools"></a><span data-ttu-id="7837a-102">Como o Designer de Consulta e Exibição representa junções (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7837a-102">How the Query and View Designer Represents Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="7837a-103">Se as tabelas forem unidas, o [Designer de Consulta e Exibição](visual-database-tools.md) representará a junção graficamente no [painel Diagrama](diagram-pane-visual-database-tools.md) e pelo uso da sintaxe SQL no [painel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7837a-103">If tables are joined, the [Query and View Designer](visual-database-tools.md) represents the join graphically in the [Diagram pane](diagram-pane-visual-database-tools.md) and by using SQL syntax in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="diagram-pane"></a><span data-ttu-id="7837a-104">Painel Diagrama</span><span class="sxs-lookup"><span data-stu-id="7837a-104">Diagram Pane</span></span>  
 <span data-ttu-id="7837a-105">No painel Diagrama, o Designer de Consulta e Exibição exibe uma linha de junção entre as colunas de dados envolvidas na junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-105">In the Diagram pane the Query and View Designer displays a join line between the data columns involved in the join.</span></span> <span data-ttu-id="7837a-106">O Designer de Consulta e Exibição exibe uma linha de junção para cada condição de junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-106">The Query and View Designer displays one join line for each join condition.</span></span> <span data-ttu-id="7837a-107">Por exemplo, a ilustração seguinte mostra uma linha de junção entre duas tabelas unidas:</span><span class="sxs-lookup"><span data-stu-id="7837a-107">For example, the following illustration shows a join line between two tables that are joined:</span></span>  
  
 <span data-ttu-id="7837a-108">![A linha de junção mostra a relação entre duas tabelas](../../database-engine/media//dv3wbig.gif "A linha de junção mostra a relação entre duas tabelas")</span><span class="sxs-lookup"><span data-stu-id="7837a-108">![Join line shows relationship between two tables](../../database-engine/media//dv3wbig.gif "Join line shows relationship between two tables")</span></span>  
  
 <span data-ttu-id="7837a-109">Se as tabelas forem unidas usando mais de um critério de junção, o Designer de Consulta e Exibição exibirá várias linhas de junção, como no exemplo seguinte:</span><span class="sxs-lookup"><span data-stu-id="7837a-109">If tables are joined using more than one join condition, the Query and View Designer displays multiple join lines, as in the following example:</span></span>  
  
 <span data-ttu-id="7837a-110">![As tabelas foram unidas com mais de uma condição de junção](../../database-engine/media//dv3w9n1.gif "As tabelas foram unidas com mais de uma condição de junção")</span><span class="sxs-lookup"><span data-stu-id="7837a-110">![Tables joined using more than one join condition](../../database-engine/media//dv3w9n1.gif "Tables joined using more than one join condition")</span></span>  
  
 <span data-ttu-id="7837a-111">Se as colunas de dados unidas não forem exibidas (por exemplo, o retângulo que representa a tabela ou o objeto estruturado por tabela é minimizado ou a junção envolve uma expressão), o Designer de Consulta e Exibição colocará a linha de junção na barra de títulos do retângulo que representa a tabela ou objeto estruturado por tabela.</span><span class="sxs-lookup"><span data-stu-id="7837a-111">If the joined data columns are not displayed (for example, the rectangle representing the table or table-structured object is minimized or the join involves an expression), the Query and View Designer places the join line at the title bar of the rectangle representing the table or table-structured object.</span></span>  
  
 <span data-ttu-id="7837a-112">A forma do ícone no meio da linha de junção indica como são unidas as tabelas ou objetos com estrutura de tabela.</span><span class="sxs-lookup"><span data-stu-id="7837a-112">The shape of the icon in the middle of the join line indicates how the tables or table-structured objects are joined.</span></span> <span data-ttu-id="7837a-113">Se a cláusula de junção usar um operador diferente de igual (=), o operador aparecerá no ícone de linha de junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-113">If the join clause uses an operator other than equal (=), the operator appears in the join line icon.</span></span> <span data-ttu-id="7837a-114">A tabela a seguir lista os ícones que aparecem na linha de junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-114">The following table lists the icons that appear in the join line.</span></span>  
  
|<span data-ttu-id="7837a-115">**Ícone de linha de junção**</span><span class="sxs-lookup"><span data-stu-id="7837a-115">**Join line icon**</span></span>|<span data-ttu-id="7837a-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7837a-116">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="7837a-117">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbih.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="7837a-117">![Visual Database Tools icon](../../database-engine/media//dv3wbih.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="7837a-118">Junção interna (criada usando um sinal de igual).</span><span class="sxs-lookup"><span data-stu-id="7837a-118">Inner join (created using an equal sign).</span></span>|  
|<span data-ttu-id="7837a-119">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbii.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="7837a-119">![Visual Database Tools icon](../../database-engine/media//dv3wbii.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="7837a-120">Junção interna baseada no operador "maior que".</span><span class="sxs-lookup"><span data-stu-id="7837a-120">Inner join based on the "greater than" operator.</span></span>|  
|<span data-ttu-id="7837a-121">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbij.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="7837a-121">![Visual Database Tools icon](../../database-engine/media//dv3wbij.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="7837a-122">A junção externa em que todas as linhas da tabela representada à esquerda serão incluídas, mesmo se não tiverem correspondências na tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="7837a-122">Outer join in which all rows from the table represented on the left will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="7837a-123">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbik.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="7837a-123">![Visual Database Tools icon](../../database-engine/media//dv3wbik.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="7837a-124">A junção externa em que todas as linhas da tabela representada à direita serão incluídas, mesmo se não tiverem correspondências na tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="7837a-124">Outer join in which all rows from the table represented on the right will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="7837a-125">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbil.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="7837a-125">![Visual Database Tools icon](../../database-engine/media//dv3wbil.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="7837a-126">Junção externa completa na qual serão incluídas todas as linhas de ambas as tabelas, mesmo se elas não tiverem correspondências com a tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="7837a-126">Full outer join in which all rows from both tables will be included, even if they do not have matches in the related table.</span></span>|  
  
 <span data-ttu-id="7837a-127">Os símbolos no final da linha de junção indicam o tipo de junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-127">The symbols on the ends of the join line indicate the type of join.</span></span> <span data-ttu-id="7837a-128">A tabela a seguir lista os tipos de junções e os ícones exibidos no final da linha de junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-128">The following table lists the types of joins and the icons displayed on the ends of the join line.</span></span>  
  
|<span data-ttu-id="7837a-129">**Ícone nas extremidades da linha de junção**</span><span class="sxs-lookup"><span data-stu-id="7837a-129">**Icon on ends of join line**</span></span>|<span data-ttu-id="7837a-130">**Tipo de junção**</span><span class="sxs-lookup"><span data-stu-id="7837a-130">**Type of join**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="7837a-131">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbim.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="7837a-131">![Visual Database Tools icon](../../database-engine/media//dv3wbim.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="7837a-132">Junção uma a uma.</span><span class="sxs-lookup"><span data-stu-id="7837a-132">One-to-one join.</span></span>|  
|<span data-ttu-id="7837a-133">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbin.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="7837a-133">![Visual Database Tools icon](../../database-engine/media//dv3wbin.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="7837a-134">Junção uma para muitas.</span><span class="sxs-lookup"><span data-stu-id="7837a-134">One-to-many join.</span></span>|  
|<span data-ttu-id="7837a-135">![Ícone de Ferramentas de Banco de Dados Visual](../../database-engine/media//dv3wbio.gif "Ícone de Ferramentas de Banco de Dados Visual")</span><span class="sxs-lookup"><span data-stu-id="7837a-135">![Visual Database Tools icon](../../database-engine/media//dv3wbio.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="7837a-136">O Designer de Consulta e Exibição não pode determinar o tipo de junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-136">Query and View Designer cannot determine the join type.</span></span> <span data-ttu-id="7837a-137">Essa situação ocorre com mas frequência quando você cria uma junção manualmente.</span><span class="sxs-lookup"><span data-stu-id="7837a-137">This situation occurs most often when you have created a join manually.</span></span>|  
  
## <a name="sql-pane"></a><span data-ttu-id="7837a-138">painel SQL</span><span class="sxs-lookup"><span data-stu-id="7837a-138">SQL Pane</span></span>  
 <span data-ttu-id="7837a-139">Uma junção pode ser expressada de vários modos em uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="7837a-139">A join can be expressed in a number of ways in an SQL statement.</span></span> <span data-ttu-id="7837a-140">A sintaxe exata depende do banco de dados que você está usando e de como você definiu a junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-140">The exact syntax depends on the database you are using and on how you have defined the join.</span></span>  
  
 <span data-ttu-id="7837a-141">Opções de sintaxe para unir tabelas incluem:</span><span class="sxs-lookup"><span data-stu-id="7837a-141">Syntax options for joining tables include:</span></span>  
  
-   <span data-ttu-id="7837a-142">**Qualificador JOIN para a cláusula FROM**.</span><span class="sxs-lookup"><span data-stu-id="7837a-142">**JOIN qualifier for the FROM clause**.</span></span>   <span data-ttu-id="7837a-143">As palavras-chave INNER e OUTER especificam o tipo de junção.</span><span class="sxs-lookup"><span data-stu-id="7837a-143">The keywords INNER and OUTER specify the join type.</span></span> <span data-ttu-id="7837a-144">Essa sintaxe é o padrão para ANSI 92 SQL.</span><span class="sxs-lookup"><span data-stu-id="7837a-144">This syntax is standard for ANSI 92 SQL.</span></span>  
  
     <span data-ttu-id="7837a-145">Por exemplo, se você unir as tabelas `publishers` e `pub_info` baseadas na coluna `pub_id` em cada tabela, a instrução SQL resultante poderia se parecer com:</span><span class="sxs-lookup"><span data-stu-id="7837a-145">For example, if you join the `publishers` and `pub_info` tables based on the `pub_id` column in each table, the resulting SQL statement might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM publishers INNER JOIN pub_info ON  
       publishers.pub_id = pub_info.pub_id  
    ```  
  
     <span data-ttu-id="7837a-146">Se você criar uma junção externa, as palavras LEFT OUTER ou RIGHT OUTER serão exibidas em vez da palavra INNER.</span><span class="sxs-lookup"><span data-stu-id="7837a-146">If you create an outer join, the words LEFT OUTER or RIGHT OUTER appear in place of the word INNER.</span></span>  
  
-   <span data-ttu-id="7837a-147">**A cláusula WHERE compara as colunas em ambas as tabelas**.</span><span class="sxs-lookup"><span data-stu-id="7837a-147">**WHERE clause compares columns in both tables**.</span></span>   <span data-ttu-id="7837a-148">Uma cláusula WHERE será exibida se o banco de dados não oferecer suporte à sintaxe JOIN (ou se você mesmo a tiver inserido).</span><span class="sxs-lookup"><span data-stu-id="7837a-148">A WHERE clause appears if the database does not support the JOIN syntax (or if you entered it yourself).</span></span> <span data-ttu-id="7837a-149">Se a junção for criada na cláusula WHERE , ambos os nomes de tabela aparecerão na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="7837a-149">If the join is created in the WHERE clause, both table names appear in the FROM clause.</span></span>  
  
     <span data-ttu-id="7837a-150">Por exemplo, a instrução a seguir une as tabelas `publishers` e `pub_info` .</span><span class="sxs-lookup"><span data-stu-id="7837a-150">For example, the following statement joins the `publishers` and `pub_info` tables.</span></span>  
  
    ```  
    SELECT *  
    FROM publishers, pub_info  
    WHERE publishers.pub_id = pub_info.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7837a-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7837a-151">See Also</span></span>  
 <span data-ttu-id="7837a-152">[Consultar com junções &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7837a-152">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7837a-153">Caixa de diálogo Unir &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7837a-153">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
