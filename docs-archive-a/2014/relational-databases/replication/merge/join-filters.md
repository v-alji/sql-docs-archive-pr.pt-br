---
title: Filtros de junção | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server replication], join
- publications [SQL Server replication], join filters
- merge replication join filters [SQL Server replication]
- join filters
ms.assetid: dd78fd8f-56e3-4582-9abd-6bc25c91e075
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b97e7d7b53e6a3fdb242d1272e013bbd45f0ed17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568494"
---
# <a name="join-filters"></a><span data-ttu-id="29197-102">filtros de junção</span><span class="sxs-lookup"><span data-stu-id="29197-102">Join Filters</span></span>
  <span data-ttu-id="29197-103">Um filtro de junção permite que uma tabela seja filtrada com base na forma pela qual uma tabela relacionada é filtrada na publicação.</span><span class="sxs-lookup"><span data-stu-id="29197-103">A join filter allows a table to be filtered based on how a related table in the publication is filtered.</span></span> <span data-ttu-id="29197-104">Geralmente uma tabela pai é filtrada usando um filtro de linha com parâmetros; depois um ou mais filtros de junção são definidos da mesma forma que se define junções entre tabelas.</span><span class="sxs-lookup"><span data-stu-id="29197-104">Typically a parent table is filtered using a parameterized filter; then one or more join filters are defined in much the same way that you define a join between tables.</span></span> <span data-ttu-id="29197-105">Os filtros de junção estendem os filtros com parâmetros para que os dados nas tabelas relacionadas sejam replicados somente se corresponderem à cláusula do filtro de junção.</span><span class="sxs-lookup"><span data-stu-id="29197-105">The join filters extend the parameterized filter so that the data in the related tables is only replicated if it matches the join filter clause.</span></span>  
  
 <span data-ttu-id="29197-106">Os filtros de junção geralmente seguem as relações chave primária/chave estrangeira definidas para as tabelas nas quais são aplicados, mas não estão estritamente limitados a essas relações.</span><span class="sxs-lookup"><span data-stu-id="29197-106">Join filters typically follow the primary key/foreign key relationships defined for the tables to which they are applied, but they are not limited strictly to primary key/foreign key relationships.</span></span> <span data-ttu-id="29197-107">O filtro de junção pode ser baseado em qualquer lógica que compare dados relacionados em duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="29197-107">The join filter can be based on any logic that compares related data in two tables.</span></span>  
  
 <span data-ttu-id="29197-108">Considere as seguintes tabelas no banco de dados de exemplo [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] que estão relacionadas por chave primária para relações de chave estrangeira:</span><span class="sxs-lookup"><span data-stu-id="29197-108">Consider the following tables in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database, which are related through primary key to foreign key relationships:</span></span>  
  
-   <span data-ttu-id="29197-109">**HumanResources.Employee**</span><span class="sxs-lookup"><span data-stu-id="29197-109">**HumanResources.Employee**</span></span>  
  
-   <span data-ttu-id="29197-110">**Sales.SalesOrderHeader**</span><span class="sxs-lookup"><span data-stu-id="29197-110">**Sales.SalesOrderHeader**</span></span>  
  
-   <span data-ttu-id="29197-111">**Sales.SalesOrderDetail**</span><span class="sxs-lookup"><span data-stu-id="29197-111">**Sales.SalesOrderDetail**</span></span>  
  
 <span data-ttu-id="29197-112">Essas tabelas podem ser usadas em um aplicativo para fornecer suporte a uma força de vendas móvel, mas precisam ser filtradas para que cada vendedor na tabela **HumanResources.Employee** receba apenas os dados relevantes aos pedidos de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="29197-112">These tables could be used in an application to support a mobile sales force, but they must be filtered so that each sales person in the **HumanResources.Employee** table receives only the data relevant to their customers' orders.</span></span>  
  
 <span data-ttu-id="29197-113">A primeira etapa é definir um filtro com parâmetros na tabela pai que, neste exemplo, é a tabela **HumanResources.Employee** .</span><span class="sxs-lookup"><span data-stu-id="29197-113">The first step is to define a parameterized filter on the parent table, which in this example is the **HumanResources.Employee** table.</span></span> <span data-ttu-id="29197-114">Essa tabela inclui a coluna **LoginID**que contém o logon para cada funcionário no formulário *domain\login*.</span><span class="sxs-lookup"><span data-stu-id="29197-114">This table includes the column **LoginID**, which contains the login for each employee in the form *domain\login*.</span></span> <span data-ttu-id="29197-115">Para filtrar essa tabela de forma que cada funcionário receba apenas os dados relacionados a ele, especifique uma cláusula de filtro com parâmetros de:</span><span class="sxs-lookup"><span data-stu-id="29197-115">To filter this table so that each employee receives only the data related to them, specify a parameterized filter clause of:</span></span>  
  
```  
LoginID = SUSER_SNAME()  
```  
  
 <span data-ttu-id="29197-116">Esse filtro garante que a assinatura de cada funcionário só contenha os dados da tabela **HumanResources.Employee** que sejam relevantes para esse funcionário (que, neste caso, é uma linha simples).</span><span class="sxs-lookup"><span data-stu-id="29197-116">This filter ensures that each employee's subscription only contains data from the **HumanResources.Employee** table that is relevant to that employee (which in this case is a single row).</span></span> <span data-ttu-id="29197-117">Para obter mais informações, consulte [Filtros de linha com parâmetros](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="29197-117">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="29197-118">A próxima etapa é estender esse filtro a cada tabela relacionada, usando sintaxe similar à que foi usada para especificar uma junção entre as duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="29197-118">The next step is to extend this filter to each of the related tables, using syntax similar to that used to specify a join between two tables.</span></span> <span data-ttu-id="29197-119">A primeira cláusula de filtro de junção é:</span><span class="sxs-lookup"><span data-stu-id="29197-119">The first join filter clause is:</span></span>  
  
```  
Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
```  
  
 <span data-ttu-id="29197-120">Isso assegura que a assinatura contenha só os dados de pedido pertinentes a cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="29197-120">This ensures the subscription contains only the order data relevant to each sales person.</span></span> <span data-ttu-id="29197-121">A segunda cláusula de filtro de junção é:</span><span class="sxs-lookup"><span data-stu-id="29197-121">The second join filter clause is:</span></span>  
  
```  
SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
```  
  
 <span data-ttu-id="29197-122">Isso assegura que a assinatura contenha só os dados detalhados relativos aos dados de pedido de cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="29197-122">This ensures the subscription contains only the detail data related to the order data for each sales person.</span></span> <span data-ttu-id="29197-123">Esse exemplo mostra uma tabela única com junção em cada ponto; também é possível realizar junção em mais de uma tabela em cada ponto.</span><span class="sxs-lookup"><span data-stu-id="29197-123">This example shows a single table being joined at each point; it is also possible to join more than one table at each point.</span></span>  
  
 <span data-ttu-id="29197-124">Os filtros de junção podem ser adicionados um por vez por meio do Assistente para Nova Publicação e da caixa de diálogo **Propriedades da Publicação** , ou podem ser adicionados programaticamente.</span><span class="sxs-lookup"><span data-stu-id="29197-124">Join filters can be added one at a time through the New Publication Wizard and the **Publication Properties** dialog box, or they can be added programmatically.</span></span> <span data-ttu-id="29197-125">Eles também podem ser gerados automaticamente por meio do Assistente para Nova Publicação: você especifica um filtro de linha para uma tabela e os filtros de junção são aplicados a todas as tabelas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="29197-125">They can also be generated automatically through the New Publication Wizard: you specify a row filter for a table and join filters are applied to all related tables.</span></span> <span data-ttu-id="29197-126">Para obter mais informações, consulte [Definir e modificar um filtro de junção entre artigos de mesclagem](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Gerar automaticamente um conjunto de filtros de junção entre artigos de mesclagem &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md) e [Definir um artigo](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="29197-126">For more information, see [Define and Modify a Join Filter Between Merge Articles](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Automatically Generate a Set of Join Filters Between Merge Articles &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md), and [Define an Article](../publish/define-an-article.md).</span></span>  
  
## <a name="optimizing-join-filter-performance"></a><span data-ttu-id="29197-127">Aperfeiçoando o desempenho dos filtros de junção</span><span class="sxs-lookup"><span data-stu-id="29197-127">Optimizing Join Filter Performance</span></span>  
 <span data-ttu-id="29197-128">O desempenho dos filtros de junção pode ser otimizado seguindo-se estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="29197-128">Join filter performance can be optimized by following these guidelines:</span></span>  
  
-   <span data-ttu-id="29197-129">Limite o número de tabelas na hierarquia de filtro de junção.</span><span class="sxs-lookup"><span data-stu-id="29197-129">Limit the number of tables in the join filter hierarchy.</span></span>  
  
     <span data-ttu-id="29197-130">Os filtros de junção podem envolver um número ilimitado de tabelas, mas filtros com um grande número de tabelas podem ter um impacto significativo no desempenho durante o processo de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="29197-130">Join Filters can involve an unlimited number of tables, but filters with a large number of tables can significantly impact performance during merge processing.</span></span> <span data-ttu-id="29197-131">Se você estiver gerando filtros de junção de cinco ou mais tabelas, considere outras soluções: não filtre tabelas pequenas, que não estão sujeitas a alterações ou que sejam basicamente tabelas de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="29197-131">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="29197-132">Use filtros de junção somente entre tabelas que devem ser particionadas entre assinaturas.</span><span class="sxs-lookup"><span data-stu-id="29197-132">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="29197-133">Defina a opção **join unique key** como **Verdadeiro** onde apropriado.</span><span class="sxs-lookup"><span data-stu-id="29197-133">Set the **join unique key** option to **True** where appropriate.</span></span>  
  
     <span data-ttu-id="29197-134">O processo de mesclagem terá otimizações de desempenho especiais disponíveis se a coluna unida no pai for exclusiva.</span><span class="sxs-lookup"><span data-stu-id="29197-134">The merge process has special performance optimizations available if the joined column in the parent is unique.</span></span> <span data-ttu-id="29197-135">Se a condição de junção estiver baseada em uma coluna exclusiva, defina a opção **join unique key** para o filtro de junção.</span><span class="sxs-lookup"><span data-stu-id="29197-135">If the join condition is based on a unique column, set the **join unique key** option for the join filter.</span></span> <span data-ttu-id="29197-136">Para obter informações sobre como definir essa opção, consulte os tópicos de instruções listados na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="29197-136">For information about setting this option, see the how-to topics listed in the previous section.</span></span>  
  
-   <span data-ttu-id="29197-137">Certifique-se de que as colunas referenciadas nos filtros de junção estejam indexadas.</span><span class="sxs-lookup"><span data-stu-id="29197-137">Ensure that the columns referenced in join filters are indexed.</span></span>  
  
     <span data-ttu-id="29197-138">Se as colunas referenciadas no filtro estiverem indexadas, a replicação poderá processar os filtros de modo mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="29197-138">If the columns referenced in the filter are indexed, replication can process the filters more efficiently.</span></span>  
  
-   <span data-ttu-id="29197-139">Não crie filtros de linha que imitem filtros de junção.</span><span class="sxs-lookup"><span data-stu-id="29197-139">Do not create row filters that mimic join filters.</span></span>  
  
     <span data-ttu-id="29197-140">É possível criar filtros de linha que imitem filtros de junção por meio de uma subconsulta em uma cláusula WHERE, como:</span><span class="sxs-lookup"><span data-stu-id="29197-140">It is possible to create row filters that mimic join filters by using a subquery in a WHERE clause, such as:</span></span>  
  
    ```  
    WHERE Customer.SalesPersonID IN (SELECT EmployeeID FROM Employee WHERE LoginID = SUSER_SNAME())   
    ```  
  
     <span data-ttu-id="29197-141">É altamente recomendável que toda lógica desse tipo seja expressa em um filtro de junção em vez de em uma subconsulta.</span><span class="sxs-lookup"><span data-stu-id="29197-141">It is strongly recommended that all such logic be expressed in a join filter rather than a subquery.</span></span> <span data-ttu-id="29197-142">Se seu aplicativo requer que um filtro de linha use uma subconsulta, certifique-se de que a subconsulta só referencie dados de pesquisa que não sejam alterados.</span><span class="sxs-lookup"><span data-stu-id="29197-142">If your application requires a row filter to use a subsquery, ensure that the subquery only references lookup data that does not change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29197-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29197-143">See Also</span></span>  
 <span data-ttu-id="29197-144">[Filtrar dados publicados para a replicação de mesclagem](filter-published-data-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="29197-144">[Filter Published Data for Merge Replication](filter-published-data-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="29197-145">Parameterized Row Filters</span><span class="sxs-lookup"><span data-stu-id="29197-145">Parameterized Row Filters</span></span>](parameterized-filters-parameterized-row-filters.md)  
  
  
