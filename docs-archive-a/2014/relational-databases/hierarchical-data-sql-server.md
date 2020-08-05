---
title: Dados hierárquicos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [SQL Server], tables to support
- hierarchyid [Database Engine], concepts
- hierarchical tables [Database Engine]
- SqlHierarchyId
- hierarchyid [Database Engine]
- hierarchical queries [SQL Server], using hierarchyid data type
ms.assetid: 19aefa9a-fbc2-4b22-92cf-67b8bb01671c
author: rothja
ms.author: jroth
ms.openlocfilehash: 351a5a4aa6bc1655b8da5fced3e51385dd498bdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573003"
---
# <a name="hierarchical-data-sql-server"></a><span data-ttu-id="da1a8-102">Dados hierárquicos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="da1a8-102">Hierarchical Data (SQL Server)</span></span>
  <span data-ttu-id="da1a8-103">O `hierarchyid` tipo de dados interno torna mais fácil armazenar e consultar dados hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="da1a8-103">The built-in `hierarchyid` data type makes it easier to store and query hierarchical data.</span></span> <span data-ttu-id="da1a8-104">`hierarchyid`é otimizado para representar árvores, que são o tipo mais comum de dados hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="da1a8-104">`hierarchyid` is optimized for representing trees, which are the most common type of hierarchical data.</span></span>  
  
 <span data-ttu-id="da1a8-105">Os dados hierárquicos são definidos como um conjunto de itens de dados mutuamente relacionados por relações hierárquicas.</span><span class="sxs-lookup"><span data-stu-id="da1a8-105">Hierarchical data is defined as a set of data items that are related to each other by hierarchical relationships.</span></span> <span data-ttu-id="da1a8-106">As relações hierárquicas existem onde um item de dados é o pai de outro item.</span><span class="sxs-lookup"><span data-stu-id="da1a8-106">Hierarchical relationships exist where one item of data is the parent of another item.</span></span> <span data-ttu-id="da1a8-107">Exemplos dos dados hierárquicos que geralmente são armazenados em bancos de dados incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="da1a8-107">Examples of the hierarchical data that is commonly stored in databases include the following:</span></span>  
  
-   <span data-ttu-id="da1a8-108">Uma estrutura organizacional</span><span class="sxs-lookup"><span data-stu-id="da1a8-108">An organizational structure</span></span>  
  
-   <span data-ttu-id="da1a8-109">Um sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="da1a8-109">A file system</span></span>  
  
-   <span data-ttu-id="da1a8-110">Um conjunto de tarefas em um projeto</span><span class="sxs-lookup"><span data-stu-id="da1a8-110">A set of tasks in a project</span></span>  
  
-   <span data-ttu-id="da1a8-111">Uma taxonomia de termos de linguagem</span><span class="sxs-lookup"><span data-stu-id="da1a8-111">A taxonomy of language terms</span></span>  
  
-   <span data-ttu-id="da1a8-112">Um gráfico de links entre páginas da Web</span><span class="sxs-lookup"><span data-stu-id="da1a8-112">A graph of links between Web pages</span></span>  
  
 <span data-ttu-id="da1a8-113">Use [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) como o tipo de dados para criar tabelas com uma estrutura hierárquica ou para descrever a estrutura hierárquica dos dados armazenados em outro local.</span><span class="sxs-lookup"><span data-stu-id="da1a8-113">Use [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) as a data type to create tables with a hierarchical structure, or to describe the hierarchical structure of data that is stored in another location.</span></span> <span data-ttu-id="da1a8-114">Use as [funções hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) no [!INCLUDE[tsql](../includes/tsql-md.md)] para consultar e gerenciar dados hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="da1a8-114">Use the [hierarchyid functions](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) in [!INCLUDE[tsql](../includes/tsql-md.md)] to query and manage hierarchical data.</span></span>  
  
##  <a name="key-properties-of-hierarchyid"></a><a name="keyprops"></a> <span data-ttu-id="da1a8-115">Propriedades chave de hierarchyid</span><span class="sxs-lookup"><span data-stu-id="da1a8-115">Key Properties of hierarchyid</span></span>  
 <span data-ttu-id="da1a8-116">Um valor do tipo de dados `hierarchyid` representa uma posição em uma hierarquia de árvore.</span><span class="sxs-lookup"><span data-stu-id="da1a8-116">A value of the `hierarchyid` data type represents a position in a tree hierarchy.</span></span> <span data-ttu-id="da1a8-117">Os valores para `hierarchyid` têm as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="da1a8-117">Values for `hierarchyid` have the following properties:</span></span>  
  
-   <span data-ttu-id="da1a8-118">Extremamente compacto</span><span class="sxs-lookup"><span data-stu-id="da1a8-118">Extremely compact</span></span>  
  
     <span data-ttu-id="da1a8-119">O número médio de bits necessários para representar um nó em uma árvore com *n* nós depende da média de fanout (o número médio de filhos de um nó).</span><span class="sxs-lookup"><span data-stu-id="da1a8-119">The average number of bits that are required to represent a node in a tree with *n* nodes depends on the average fanout (the average number of children of a node).</span></span> <span data-ttu-id="da1a8-120">Para fanouts pequenos, o tamanho (0-7) é de aproximadamente 6\*logA*n* bits, em que A é o fanout médio.</span><span class="sxs-lookup"><span data-stu-id="da1a8-120">For small fanouts, (0-7) the size is about 6\*logA*n* bits, where A is the average fanout.</span></span> <span data-ttu-id="da1a8-121">Um nó em uma hierarquia organizacional de 100.000 pessoas com um fanout médio de 6 níveis usa cerca de 38 bits.</span><span class="sxs-lookup"><span data-stu-id="da1a8-121">A node in an organizational hierarchy of 100,000 people with an average fanout of 6 levels takes about 38 bits.</span></span> <span data-ttu-id="da1a8-122">Isso é arredondado para 40 bits, ou 5 bytes, para armazenamento.</span><span class="sxs-lookup"><span data-stu-id="da1a8-122">This is rounded up to 40 bits, or 5 bytes, for storage.</span></span>  
  
-   <span data-ttu-id="da1a8-123">A comparação está na ordem de profundidade</span><span class="sxs-lookup"><span data-stu-id="da1a8-123">Comparison is in depth-first order</span></span>  
  
     <span data-ttu-id="da1a8-124">Considerando dois `hierarchyid` valores **a** e **b**, **um<b** significa que o vem antes de b em uma passagem de profundidade da árvore.</span><span class="sxs-lookup"><span data-stu-id="da1a8-124">Given two `hierarchyid` values **a** and **b**, **a<b** means a comes before b in a depth-first traversal of the tree.</span></span> <span data-ttu-id="da1a8-125">Índices em tipos de dados `hierarchyid` estão na ordem de profundidade e os nós que estão próximos um do outro são armazenados em uma passagem de profundidade próximos um do outro.</span><span class="sxs-lookup"><span data-stu-id="da1a8-125">Indexes on `hierarchyid` data types are in depth-first order, and nodes close to each other in a depth-first traversal are stored near each other.</span></span> <span data-ttu-id="da1a8-126">Por exemplo, os filhos de um registro são armazenados adjacentes àquele registro.</span><span class="sxs-lookup"><span data-stu-id="da1a8-126">For example, the children of a record are stored adjacent to that record.</span></span>  
  
-   <span data-ttu-id="da1a8-127">Suporte a inserções e exclusões arbitrárias</span><span class="sxs-lookup"><span data-stu-id="da1a8-127">Support for arbitrary insertions and deletions</span></span>  
  
     <span data-ttu-id="da1a8-128">Usando o método [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) , é sempre possível gerar um irmão à direita de qualquer nó determinado, à esquerda de qualquer nó determinado ou entre dois irmãos.</span><span class="sxs-lookup"><span data-stu-id="da1a8-128">By using the [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) method, it is always possible to generate a sibling to the right of any given node, to the left of any given node, or between any two siblings.</span></span> <span data-ttu-id="da1a8-129">A propriedade de comparação é mantida quando um número arbitrário de nós é inserido ou excluído da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="da1a8-129">The comparison property is maintained when an arbitrary number of nodes is inserted or deleted from the hierarchy.</span></span> <span data-ttu-id="da1a8-130">A maioria das inserções e exclusões preserva a propriedade de densidade.</span><span class="sxs-lookup"><span data-stu-id="da1a8-130">Most insertions and deletions preserve the compactness property.</span></span> <span data-ttu-id="da1a8-131">Porém, inserções entre dois nós produzirão valores hierarchyid com uma representação ligeiramente menos compacta.</span><span class="sxs-lookup"><span data-stu-id="da1a8-131">However, insertions between two nodes will produce hierarchyid values with a slightly less compact representation.</span></span>  
  
  
##  <a name="limitations-of-hierarchyid"></a><a name="limits"></a> <span data-ttu-id="da1a8-132">Limitações de hierarchyid</span><span class="sxs-lookup"><span data-stu-id="da1a8-132">Limitations of hierarchyid</span></span>  
 <span data-ttu-id="da1a8-133">O `hierarchyid` tipo de dados tem as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="da1a8-133">The `hierarchyid` data type has the following limitations:</span></span>  
  
-   <span data-ttu-id="da1a8-134">Uma coluna de tipo `hierarchyid` não representa automaticamente uma árvore.</span><span class="sxs-lookup"><span data-stu-id="da1a8-134">A column of type `hierarchyid` does not automatically represent a tree.</span></span> <span data-ttu-id="da1a8-135">Depende do aplicativo gerar e atribuir valores `hierarchyid` de maneira que a relação desejada entre as linhas seja refletida nos valores.</span><span class="sxs-lookup"><span data-stu-id="da1a8-135">It is up to the application to generate and assign `hierarchyid` values in such a way that the desired relationship between rows is reflected in the values.</span></span> <span data-ttu-id="da1a8-136">Alguns aplicativos podem ter uma coluna do tipo `hierarchyid` que indica o local em uma hierarquia definida em outra tabela.</span><span class="sxs-lookup"><span data-stu-id="da1a8-136">Some applications might have a column of type `hierarchyid` that indicates the location in a hierarchy defined in another table.</span></span>  
  
-   <span data-ttu-id="da1a8-137">Depende de o aplicativo gerenciar a simultaneidade gerando e atribuindo valores `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-137">It is up to the application to manage concurrency in generating and assigning `hierarchyid` values.</span></span> <span data-ttu-id="da1a8-138">Não há nenhuma garantia que valores `hierarchyid` em uma coluna sejam exclusivos a menos que o aplicativo use uma restrição chave exclusiva ou force sua exclusividade em sua própria lógica.</span><span class="sxs-lookup"><span data-stu-id="da1a8-138">There is no guarantee that `hierarchyid` values in a column are unique unless the application uses a unique key constraint or enforces uniqueness itself through its own logic.</span></span>  
  
-   <span data-ttu-id="da1a8-139">Relações hierárquicas representadas por valores `hierarchyid` não são impostas como uma relação de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="da1a8-139">Hierarchical relationships represented by `hierarchyid` values are not enforced like a foreign key relationship.</span></span> <span data-ttu-id="da1a8-140">É possível e, às vezes, apropriado ter uma relação hierárquica onde A tem um filho B e, depois, A é excluído deixando B com uma relação para um registro inexistente.</span><span class="sxs-lookup"><span data-stu-id="da1a8-140">It is possible and sometimes appropriate to have a hierarchical relationship where A has a child B, and then A is deleted leaving B with a relationship to a nonexistent record.</span></span> <span data-ttu-id="da1a8-141">Se esse comportamento for inaceitável, o aplicativo deverá fazer a consulta por descendentes antes de excluir os pais.</span><span class="sxs-lookup"><span data-stu-id="da1a8-141">If this behavior is unacceptable, the application must query for descendants before deleting parents.</span></span>  
  
  
##  <a name="when-to-use-alternatives-to-hierarchyid"></a><a name="alternatives"></a> <span data-ttu-id="da1a8-142">Quando usar alternativas para hierarchyid</span><span class="sxs-lookup"><span data-stu-id="da1a8-142">When to Use Alternatives to hierarchyid</span></span>  
 <span data-ttu-id="da1a8-143">As duas alternativas para `hierarchyid` para representar dados hierárquicos são:</span><span class="sxs-lookup"><span data-stu-id="da1a8-143">Two alternatives to `hierarchyid` for representing hierarchical data are:</span></span>  
  
-   <span data-ttu-id="da1a8-144">Pai/filho</span><span class="sxs-lookup"><span data-stu-id="da1a8-144">Parent/Child</span></span>  
  
-   <span data-ttu-id="da1a8-145">XML</span><span class="sxs-lookup"><span data-stu-id="da1a8-145">XML</span></span>  
  
 <span data-ttu-id="da1a8-146">A`hierarchyid` é geralmente superior a essas alternativas.</span><span class="sxs-lookup"><span data-stu-id="da1a8-146">`hierarchyid` is generally superior to these alternatives.</span></span> <span data-ttu-id="da1a8-147">Porém, a seguir há situações específicas detalhadas em que as alternativas são provavelmente superiores.</span><span class="sxs-lookup"><span data-stu-id="da1a8-147">However, there are specific situations detailed below where the alternatives are likely superior.</span></span>  
  
### <a name="parentchild"></a><span data-ttu-id="da1a8-148">Pai/filho</span><span class="sxs-lookup"><span data-stu-id="da1a8-148">Parent/Child</span></span>  
 <span data-ttu-id="da1a8-149">Ao usar a abordagem Pai/Filho, cada linha contém uma referência ao pai.</span><span class="sxs-lookup"><span data-stu-id="da1a8-149">When using the Parent/Child approach, each row contains a reference to the parent.</span></span> <span data-ttu-id="da1a8-150">A tabela a seguir define uma tabela típica usada para conter as linhas pai e filho em uma relação Pai/Filho:</span><span class="sxs-lookup"><span data-stu-id="da1a8-150">The following table defines a typical table used to contain the parent and the child rows in a Parent/Child relationship:</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE TABLE ParentChildOrg  
   (  
    BusinessEntityID int PRIMARY KEY,  
    ManagerId int REFERENCES ParentChildOrg(BusinessEntityID),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
```  
  
 <span data-ttu-id="da1a8-151">Comparando pai/filho e `hierarchyid` em operações comuns</span><span class="sxs-lookup"><span data-stu-id="da1a8-151">Comparing Parent/Child and `hierarchyid` for Common Operations</span></span>  
  
-   <span data-ttu-id="da1a8-152">Consultas de subárvore são significativamente mais rápidas com `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-152">Subtree queries are significantly faster with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="da1a8-153">Consultas de descendente direto são ligeiramente mais lentas com `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-153">Direct descendant queries are slightly slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="da1a8-154">A movimentação de nós é mais lenta com `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-154">Moving non-leaf nodes is slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="da1a8-155">A inserção de nós não folha e a inserção ou a movimentação de nós folha têm a mesma complexidade com `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-155">Inserting non-leaf nodes and inserting or moving leaf nodes has the same complexity with `hierarchyid`.</span></span>  
  
 <span data-ttu-id="da1a8-156">Pai/Filho pode ser superior quando existem as seguintes:</span><span class="sxs-lookup"><span data-stu-id="da1a8-156">Parent/Child might be superior when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="da1a8-157">O tamanho da chave é crítico.</span><span class="sxs-lookup"><span data-stu-id="da1a8-157">The size of the key is critical.</span></span> <span data-ttu-id="da1a8-158">Para o mesmo número de nós, um valor `hierarchyid` é igual ou maior que um valor família inteiro (`smallint`, `int`, `bigint`).</span><span class="sxs-lookup"><span data-stu-id="da1a8-158">For the same number of nodes, a `hierarchyid` value is equal to or larger than an integer-family (`smallint`, `int`, `bigint`) value.</span></span> <span data-ttu-id="da1a8-159">Essa é a única razão para usar Pai/Filho em casos raros, porque `hierarchyid` tem localidade significativamente melhor de E/S e complexidade de CPU que as expressões de tabela comuns exigidas quando você está usando uma estrutura Pai/Filho.</span><span class="sxs-lookup"><span data-stu-id="da1a8-159">This is only a reason to use Parent/Child in rare cases, because `hierarchyid` has significantly better locality of I/O and CPU complexity than the common table expressions required when you are using a Parent/Child structure.</span></span>  
  
-   <span data-ttu-id="da1a8-160">Consultas raramente examinam por seções da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="da1a8-160">Queries rarely query across sections of the hierarchy.</span></span> <span data-ttu-id="da1a8-161">Em outras palavras, as consultas normalmente se dirigem apenas a um único ponto na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="da1a8-161">In other words, queries usually address only a single point in the hierarchy.</span></span> <span data-ttu-id="da1a8-162">Nesses casos, a colocação não é importante.</span><span class="sxs-lookup"><span data-stu-id="da1a8-162">In these cases co-location is not important.</span></span> <span data-ttu-id="da1a8-163">Por exemplo, Pai/Filho é superior quando a tabela de organização é usada somente para processar a folha de pagamento de funcionários individuais.</span><span class="sxs-lookup"><span data-stu-id="da1a8-163">For example, Parent/Child is superior when the organization table is only used to process payroll for individual employees.</span></span>  
  
-   <span data-ttu-id="da1a8-164">Subárvores de não folha mudam frequentemente e o desempenho é muito importante.</span><span class="sxs-lookup"><span data-stu-id="da1a8-164">Non-leaf subtrees move frequently and performance is very important.</span></span> <span data-ttu-id="da1a8-165">Em uma representação pai/filho, alterando o local de uma linha em uma hierarquia afeta uma linha única.</span><span class="sxs-lookup"><span data-stu-id="da1a8-165">In a parent/child representation changing the location of a row in a hierarchy affects a single row.</span></span> <span data-ttu-id="da1a8-166">Alterar o local de uma linha em um `hierarchyid` uso afeta *n* linhas, em que *n* é o número de nós na subárvore que está sendo movida.</span><span class="sxs-lookup"><span data-stu-id="da1a8-166">Changing the location of a row in a `hierarchyid` usage affects *n* rows, where *n* is number of nodes in the sub-tree being moved.</span></span>  
  
     <span data-ttu-id="da1a8-167">Se as subárvores sem folha mudarem frequentemente e o desempenho for importante, mas a maioria das mudanças estiver em um nível bem definido da hierarquia, considere dividir os níveis superiores e inferiores em duas hierarquias.</span><span class="sxs-lookup"><span data-stu-id="da1a8-167">If the non-leaf subtrees move frequently and performance is important, but most of the moves are at a well-defined level of the hierarchy, consider splitting the higher and lower levels into two hierarchies.</span></span> <span data-ttu-id="da1a8-168">Isso faz todas as mudanças em níveis de folha da hierarquia mais alta.</span><span class="sxs-lookup"><span data-stu-id="da1a8-168">This makes all moves into leaf-levels of the higher hierarchy.</span></span> <span data-ttu-id="da1a8-169">Por exemplo, considere uma hierarquia de sites hospedados por um serviço.</span><span class="sxs-lookup"><span data-stu-id="da1a8-169">For instance, consider a hierarchy of Web sites hosted by a service.</span></span> <span data-ttu-id="da1a8-170">Sites contêm muitas páginas organizadas de uma maneira hierárquica.</span><span class="sxs-lookup"><span data-stu-id="da1a8-170">Sites contain many pages arranged in a hierarchical manner.</span></span> <span data-ttu-id="da1a8-171">Sites hospedados poderiam ser movidos a outros locais na hierarquia do site, mas as páginas subordinadas raramente seriam reorganizadas.</span><span class="sxs-lookup"><span data-stu-id="da1a8-171">Hosted sites might be moved to other locations in the site hierarchy, but the subordinate pages are rarely re-arranged.</span></span> <span data-ttu-id="da1a8-172">Isso poderia ser representado por:</span><span class="sxs-lookup"><span data-stu-id="da1a8-172">This could be represented via:</span></span>  
  
    ```  
    CREATE TABLE HostedSites   
       (  
        SiteId hierarchyid, PageId hierarchyid  
       ) ;  
    GO  
    ```  
  
  
### <a name="xml"></a><span data-ttu-id="da1a8-173">XML</span><span class="sxs-lookup"><span data-stu-id="da1a8-173">XML</span></span>  
 <span data-ttu-id="da1a8-174">Um documento XML é uma árvore e, portanto, uma instância de tipo de dados XML única pode representar uma hierarquia completa.</span><span class="sxs-lookup"><span data-stu-id="da1a8-174">An XML document is a tree, and therefore a single XML data type instance can represent a complete hierarchy.</span></span> <span data-ttu-id="da1a8-175">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]Quando um índice XML é criado, `hierarchyid` os valores são usados internamente para representar a posição na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="da1a8-175">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when an XML index is created, `hierarchyid` values are used internally to represent the position in the hierarchy.</span></span>  
  
 <span data-ttu-id="da1a8-176">Usar um tipo de dados XML pode ser vantajoso quando todos os seguintes itens forem verdadeiros:</span><span class="sxs-lookup"><span data-stu-id="da1a8-176">Using XML data type can be superior when all the following are true:</span></span>  
  
-   <span data-ttu-id="da1a8-177">A hierarquia completa é sempre armazenada e recuperada.</span><span class="sxs-lookup"><span data-stu-id="da1a8-177">The complete hierarchy is always stored and retrieved.</span></span>  
  
-   <span data-ttu-id="da1a8-178">Os dados são consumidos no formato XML pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="da1a8-178">The data is consumed in XML format by the application.</span></span>  
  
-   <span data-ttu-id="da1a8-179">Pesquisas de predicado são extremamente limitadas e não têm de desempenho crítico.</span><span class="sxs-lookup"><span data-stu-id="da1a8-179">Predicate searches are extremely limited and not performance critical.</span></span>  
  
 <span data-ttu-id="da1a8-180">Por exemplo, se um aplicativo controla várias organizações, ele sempre armazena e recupera a hierarquia organizacional completa, e não faz a consulta em uma organização única, uma tabela do formulário a seguir faria sentido:</span><span class="sxs-lookup"><span data-stu-id="da1a8-180">For example, if an application tracks multiple organizations, always stores and retrieves the complete organizational hierarchy, and does not query into a single organization, a table of the following form might make sense:</span></span>  
  
```  
CREATE TABLE XMLOrg   
    (  
    Orgid int,  
    Orgdata xml  
    ) ;  
GO  
```  
  
  
##  <a name="indexing-strategies-for-hierarchical-data"></a><a name="indexing"></a> <span data-ttu-id="da1a8-181">Estratégias de indexação para dados hierárquicos</span><span class="sxs-lookup"><span data-stu-id="da1a8-181">Indexing Strategies for Hierarchical Data</span></span>  
 <span data-ttu-id="da1a8-182">Há duas estratégias para indexar dados hierárquicos:</span><span class="sxs-lookup"><span data-stu-id="da1a8-182">There are two strategies for indexing hierarchical data:</span></span>  
  
-   <span data-ttu-id="da1a8-183">**Profundidade**</span><span class="sxs-lookup"><span data-stu-id="da1a8-183">**Depth-first**</span></span>  
  
     <span data-ttu-id="da1a8-184">Um índice de profundidade armazena as linhas em uma subárvore próximas umas das outras.</span><span class="sxs-lookup"><span data-stu-id="da1a8-184">A depth-first index stores the rows in a subtree near each other.</span></span> <span data-ttu-id="da1a8-185">Por exemplo, todos os funcionários que se reportam a gerente são armazenados próximos do registro de seus gerentes.</span><span class="sxs-lookup"><span data-stu-id="da1a8-185">For example, all employees that report through a manager are stored near their managers' record.</span></span>  
  
     <span data-ttu-id="da1a8-186">Em um índice por profundidade, todos os nós na subárvore de um nó são colocados.</span><span class="sxs-lookup"><span data-stu-id="da1a8-186">In a depth-first index, all nodes in the subtree of a node are co-located.</span></span> <span data-ttu-id="da1a8-187">Índices por profundidade são portanto eficientes para responder consultas sobre subárvores, como "Localizar todos os arquivos nesta pasta e subpastas""""""""".</span><span class="sxs-lookup"><span data-stu-id="da1a8-187">Depth-first indexes are therefore efficient for answering queries about subtrees, such as "Find all files in this folder and its subfolders".</span></span>  
  
-   <span data-ttu-id="da1a8-188">**Amplitude**</span><span class="sxs-lookup"><span data-stu-id="da1a8-188">**Breadth-first**</span></span>  
  
     <span data-ttu-id="da1a8-189">Uma amplitude armazena as linhas de cada nível da hierarquia juntas.</span><span class="sxs-lookup"><span data-stu-id="da1a8-189">A breadth-first stores the rows each level of the hierarchy together.</span></span> <span data-ttu-id="da1a8-190">Por exemplo, os registros de funcionários que se reportam diretamente ao mesmo gerente são armazenados próximos um do outro.</span><span class="sxs-lookup"><span data-stu-id="da1a8-190">For example, the records of employees who directly report to the same manager are stored near each other.</span></span>  
  
     <span data-ttu-id="da1a8-191">Em um índice por amplitude todos os filhos diretos de um nós são colocados.</span><span class="sxs-lookup"><span data-stu-id="da1a8-191">In a breadth-first index all direct children of a node are co-located.</span></span> <span data-ttu-id="da1a8-192">Índices por amplitude são, portanto, eficientes para responder consultas sobre filhos diretos, como "Localizar todos os empregados que se reportam diretamente a esse gerente".</span><span class="sxs-lookup"><span data-stu-id="da1a8-192">Breadth-first indexes are therefore efficient for answering queries about immediate children, such as "Find all employees who report directly to this manager".</span></span>  
  
 <span data-ttu-id="da1a8-193">Ter opções por profundidade, por amplitude, ou ambas, e qual delas tornar a chave de clustering (se houver), depende da importância relativa dos tipos de consultas anteriores e da importância relativa de operações SELECT versus DML.</span><span class="sxs-lookup"><span data-stu-id="da1a8-193">Whether to have depth-first, breadth-first, or both, and which to make the clustering key (if any), depends on the relative importance of the above types of queries, and the relative importance of SELECT vs. DML operations.</span></span> <span data-ttu-id="da1a8-194">Para obter um exemplo detalhado de estratégias de indexação, consulte [Tutorial: Usando o tipo de dados HierarchyId](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="da1a8-194">For a detailed example of indexing strategies, see [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
### <a name="creating-indexes"></a><span data-ttu-id="da1a8-195">Criando índices</span><span class="sxs-lookup"><span data-stu-id="da1a8-195">Creating Indexes</span></span>  
 <span data-ttu-id="da1a8-196">O método GetLevel() pode ser usado para criar uma ordem por amplitude.</span><span class="sxs-lookup"><span data-stu-id="da1a8-196">The GetLevel() method can be used to create a breadth first ordering.</span></span> <span data-ttu-id="da1a8-197">No exemplo seguinte, são criados índices por amplitude e por profundidade:</span><span class="sxs-lookup"><span data-stu-id="da1a8-197">In the following example, both breadth-first and depth-first indexes are created:</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;   
GO  
  
CREATE TABLE Organization  
   (  
    BusinessEntityID hierarchyid,  
    OrgLevel as BusinessEntityID.GetLevel(),   
    EmployeeName nvarchar(50) NOT NULL  
   ) ;  
GO  
  
CREATE CLUSTERED INDEX Org_Breadth_First   
ON Organization(OrgLevel,BusinessEntityID) ;  
GO  
  
CREATE UNIQUE INDEX Org_Depth_First   
ON Organization(BusinessEntityID) ;  
GO  
```  
  
  
## <a name="examples"></a><span data-ttu-id="da1a8-198">Exemplos</span><span class="sxs-lookup"><span data-stu-id="da1a8-198">Examples</span></span>  
  
### <a name="simple-example"></a><span data-ttu-id="da1a8-199">Exemplo simples</span><span class="sxs-lookup"><span data-stu-id="da1a8-199">Simple Example</span></span>  
 <span data-ttu-id="da1a8-200">O exemplo a seguir é intencionalmente simplificado para ajudá-lo a começar.</span><span class="sxs-lookup"><span data-stu-id="da1a8-200">The following example is intentionally simplistic to help you get started.</span></span> <span data-ttu-id="da1a8-201">Primeiro crie uma tabela para manter alguns dados geográficos.</span><span class="sxs-lookup"><span data-stu-id="da1a8-201">First create a table to hold some geography data.</span></span>  
  
```  
CREATE TABLE SimpleDemo  
(Level hierarchyid NOT NULL,  
Location nvarchar(30) NOT NULL,  
LocationType nvarchar(9) NULL);  
```  
  
 <span data-ttu-id="da1a8-202">Agora insira dados para alguns continentes, países, estados e cidades.</span><span class="sxs-lookup"><span data-stu-id="da1a8-202">Now insert data for some continents, countries, states, and cities.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES   
('/1/', 'Europe', 'Continent'),  
('/2/', 'South America', 'Continent'),  
('/1/1/', 'France', 'Country'),  
('/1/1/1/', 'Paris', 'City'),  
('/1/2/1/', 'Madrid', 'City'),  
('/1/2/', 'Spain', 'Country'),  
('/3/', 'Antarctica', 'Continent'),  
('/2/1/', 'Brazil', 'Country'),  
('/2/1/1/', 'Brasilia', 'City'),  
('/2/1/2/', 'Bahia', 'State'),  
('/2/1/2/1/', 'Salvador', 'City'),  
('/3/1/', 'McMurdo Station', 'City');  
```  
  
 <span data-ttu-id="da1a8-203">Selecione os dados, adicionando uma coluna que converta os dados de nível em um valor de texto de fácil compreensão.</span><span class="sxs-lookup"><span data-stu-id="da1a8-203">Select the data, adding a column that converts the Level data into a text value that is easy to understand.</span></span> <span data-ttu-id="da1a8-204">Essa consulta também ordena o resultado pelo tipo de dados `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-204">This query also orders the result by the `hierarchyid` data type.</span></span>  
  
```  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], *   
FROM SimpleDemo ORDER BY Level;  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
Converted Level  Level     Location         LocationType  
/1/              0x58      Europe           Continent  
/1/1/            0x5AC0    France           Country  
/1/1/1/          0x5AD6    Paris            City  
/1/2/            0x5B40    Spain            Country  
/1/2/1/          0x5B56    Madrid           City  
/2/              0x68      South America    Continent  
/2/1/            0x6AC0    Brazil           Country  
/2/1/1/          0x6AD6    Brasilia         City  
/2/1/2/          0x6ADA    Bahia            State  
/2/1/2/1/        0x6ADAB0  Salvador         City  
/3/              0x78      Antarctica       Continent  
/3/1/            0x7AC0    McMurdo Station  City  
```  
  
 <span data-ttu-id="da1a8-205">Observe que a hierarquia tem uma estrutura válida, embora ela não seja consistente internamente.</span><span class="sxs-lookup"><span data-stu-id="da1a8-205">Notice that the hierarchy is has a valid structure, even though it is not internally consistent.</span></span> <span data-ttu-id="da1a8-206">Bahia é o único estado.</span><span class="sxs-lookup"><span data-stu-id="da1a8-206">Bahia is the only state.</span></span> <span data-ttu-id="da1a8-207">Ele aparece na hierarquia como um par da cidade de Brasília.</span><span class="sxs-lookup"><span data-stu-id="da1a8-207">It appears in the hierarchy as a peer of the city Brasilia.</span></span> <span data-ttu-id="da1a8-208">Da mesma forma, a estação McMurdo não tem um país pai.</span><span class="sxs-lookup"><span data-stu-id="da1a8-208">Similarly, McMurdo Station does not have a parent country.</span></span> <span data-ttu-id="da1a8-209">Os usuários devem decidir se este tipo de hierarquia é apropriado para seu uso.</span><span class="sxs-lookup"><span data-stu-id="da1a8-209">Users must decide if this type of hierarchy is appropriate for their use.</span></span>  
  
 <span data-ttu-id="da1a8-210">Adicione outra linha e selecione os resultados.</span><span class="sxs-lookup"><span data-stu-id="da1a8-210">Add another row and select the results.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/1/3/1/', 'Kyoto', 'City'), ('/1/3/1/', 'London', 'City');  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], * FROM SimpleDemo ORDER BY Level;  
```  
  
 <span data-ttu-id="da1a8-211">Isso demonstra mais problemas em potencial.</span><span class="sxs-lookup"><span data-stu-id="da1a8-211">This demonstrates more possible problems.</span></span> <span data-ttu-id="da1a8-212">Kyoto pode ser inserido como o nível `/1/3/1/` , embora não exista um nível pai `/1/3/`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-212">Kyoto can be inserted as level `/1/3/1/` even though there is no parent level `/1/3/`.</span></span> <span data-ttu-id="da1a8-213">Londres e Kyoto têm o mesmo valor para `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-213">And both London and Kyoto have the same value for the `hierarchyid`.</span></span> <span data-ttu-id="da1a8-214">Além disso, os usuários devem decidir se este tipo de hierarquia é apropriado para seu uso, e os valores do bloco que são inválidos para seu uso.</span><span class="sxs-lookup"><span data-stu-id="da1a8-214">Again, users must decide if this type of hierarchy is appropriate for their use, and block values that are invalid for their usage.</span></span>  
  
 <span data-ttu-id="da1a8-215">Além disso, essa tabela não usou a parte superior da hierarquia `'/'`.</span><span class="sxs-lookup"><span data-stu-id="da1a8-215">Also, this table did not use the top of the hierarchy `'/'`.</span></span> <span data-ttu-id="da1a8-216">Ela foi omitida pois não há um pai comum de todos os continentes.</span><span class="sxs-lookup"><span data-stu-id="da1a8-216">It was omitted because there is no common parent of all the continents.</span></span> <span data-ttu-id="da1a8-217">Para adicionar um, adicione o planeta inteiro.</span><span class="sxs-lookup"><span data-stu-id="da1a8-217">You can add one by adding the whole planet.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/', 'Earth', 'Planet');  
```  
  
##  <a name="related-tasks"></a><a name="tasks"></a> <span data-ttu-id="da1a8-218">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="da1a8-218">Related Tasks</span></span>  
  
###  <a name="migrating-from-parentchild-to-hierarchyid"></a><a name="migrating"></a> <span data-ttu-id="da1a8-219">Migrando de Pai/Filho para hierarchyid</span><span class="sxs-lookup"><span data-stu-id="da1a8-219">Migrating from Parent/Child to hierarchyid</span></span>  
 <span data-ttu-id="da1a8-220">A maioria das árvores é representada usando Pai/Filho.</span><span class="sxs-lookup"><span data-stu-id="da1a8-220">Most trees are represented using Parent/Child.</span></span> <span data-ttu-id="da1a8-221">O modo mais fácil de migrar de uma estrutura Pai/Filho para uma tabela usando `hierarchyid` é usar uma coluna ou uma tabela temporária para manter o controle do número de nós em cada nível da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="da1a8-221">The easiest way to migrate from a Parent/Child structure to a table using `hierarchyid` is to use a temporary column or a temporary table to keep track of the number of nodes at each level of the hierarchy.</span></span> <span data-ttu-id="da1a8-222">Para obter um exemplo de migração de uma tabela Pai/Filho, consulte a lição 1 do [Tutorial: Usando o tipo de dados HierarchyId](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="da1a8-222">For an example of migrating a Parent/Child table, see lesson 1 of [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
###  <a name="managing-a-tree-using-hierarchyid"></a><a name="BKMK_ManagingTrees"></a> <span data-ttu-id="da1a8-223">Gerenciando uma árvore com hierarchyid</span><span class="sxs-lookup"><span data-stu-id="da1a8-223">Managing a Tree Using hierarchyid</span></span>  
 <span data-ttu-id="da1a8-224">Embora uma coluna `hierarchyid` não represente necessariamente uma árvore, um aplicativo pode garantir facilmente que essa representação ocorra.</span><span class="sxs-lookup"><span data-stu-id="da1a8-224">Although a `hierarchyid` column does not necessarily represent a tree, an application can easily ensure that it does.</span></span>  
  
-   <span data-ttu-id="da1a8-225">Para gerar novos valores, execute uma das ações abaixo:</span><span class="sxs-lookup"><span data-stu-id="da1a8-225">When generating new values, do one of the following:</span></span>  
  
    -   <span data-ttu-id="da1a8-226">Mantenha registro do último número filho da linha pai.</span><span class="sxs-lookup"><span data-stu-id="da1a8-226">Keep track of the last child number in the parent row.</span></span>  
  
    -   <span data-ttu-id="da1a8-227">Compute o último filho.</span><span class="sxs-lookup"><span data-stu-id="da1a8-227">Compute the last child.</span></span> <span data-ttu-id="da1a8-228">Para executar esse procedimento com eficácia, é necessário um índice de primeira amplitude.</span><span class="sxs-lookup"><span data-stu-id="da1a8-228">Doing this efficiently requires a breadth-first index.</span></span>  
  
-   <span data-ttu-id="da1a8-229">Imponha a exclusividade criando um índice exclusivo na coluna, talvez como parte de uma chave de clustering.</span><span class="sxs-lookup"><span data-stu-id="da1a8-229">Enforce uniqueness by creating a unique index on the column, perhaps as part of a clustering key.</span></span> <span data-ttu-id="da1a8-230">Para assegurar a inserção de valores únicos, execute uma das ações a seguir:</span><span class="sxs-lookup"><span data-stu-id="da1a8-230">To ensure that unique values are inserted, do one of the following:</span></span>  
  
    -   <span data-ttu-id="da1a8-231">Detecte as falhas de violação de chave exclusiva e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="da1a8-231">Detect unique key violation failures and retry.</span></span>  
  
    -   <span data-ttu-id="da1a8-232">Determine a exclusividade de cada novo nó filho e insira-o como parte de uma transação serializável.</span><span class="sxs-lookup"><span data-stu-id="da1a8-232">Determine the uniqueness of each new child node, and insert it as part of a serializable transaction.</span></span>  
  
  
#### <a name="example-using-error-detection"></a><span data-ttu-id="da1a8-233">Exemplo utilizando detecção de erro</span><span class="sxs-lookup"><span data-stu-id="da1a8-233">Example Using Error Detection</span></span>  
 <span data-ttu-id="da1a8-234">No exemplo a seguir, o código de exemplo computa o novo valor filho de **EmployeeId** detectando depois quaisquer violações de chave para retorná-las ao marcador **INS_EMP** para computar novamente o valor de **EmployeeId** na nova linha:</span><span class="sxs-lookup"><span data-stu-id="da1a8-234">In the following example, the sample code computes the new child **EmployeeId** value, and then detects any key violation and returns to **INS_EMP** marker to recompute the **EmployeeId** value for the new row:</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
CREATE TABLE Org_T1  
   (  
    EmployeeId hierarchyid PRIMARY KEY,  
    OrgLevel AS EmployeeId.GetLevel(),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
  
CREATE INDEX Org_BreadthFirst ON Org_T1(OrgLevel, EmployeeId)  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50) )   
AS  
BEGIN  
    DECLARE @last_child hierarchyid  
INS_EMP:   
    SELECT @last_child = MAX(EmployeeId) FROM Org_T1   
    WHERE EmployeeId.GetAncestor(1) = @mgrid  
INSERT Org_T1 (EmployeeId, EmployeeName)  
SELECT @mgrid.GetDescendant(@last_child, NULL), @EmpName   
-- On error, return to INS_EMP to recompute @last_child  
IF @@error <> 0 GOTO INS_EMP   
END ;  
GO  
```  
  
  
#### <a name="example-using-a-serializable-transaction"></a><span data-ttu-id="da1a8-235">Exemplo utilizando uma transação serializável</span><span class="sxs-lookup"><span data-stu-id="da1a8-235">Example Using a Serializable Transaction</span></span>  
 <span data-ttu-id="da1a8-236">O tipo de dados **Org_BreadthFirst** assegura que a determinação de **@last_child** use uma busca de intervalo.</span><span class="sxs-lookup"><span data-stu-id="da1a8-236">The **Org_BreadthFirst** index ensures that determining **@last_child** uses a range seek.</span></span> <span data-ttu-id="da1a8-237">Além de outros casos de erro, um aplicativo pode querer verificar, uma violação de chave duplicada após a inserção indica uma tentativa de adicionar vários funcionários com a mesma ID e, portanto, **@last_child** deve ser recomputado.</span><span class="sxs-lookup"><span data-stu-id="da1a8-237">In addition to other error cases an application might want to check, a duplicate key violation after the insert indicates an attempt to add multiple employees with the same id, and therefore **@last_child** must be recomputed.</span></span> <span data-ttu-id="da1a8-238">O código a seguir usa uma transação serializável e um índice de primeira amplitude para computar o valor do novo nó:</span><span class="sxs-lookup"><span data-stu-id="da1a8-238">The following code uses a serializable transaction and a breadth-first index to compute the new node value:</span></span>  
  
```  
CREATE TABLE Org_T2  
    (  
    EmployeeId hierarchyid PRIMARY KEY,  
    LastChild hierarchyid,   
    EmployeeName nvarchar(50)   
    ) ;  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50))   
AS  
BEGIN  
DECLARE @last_child hierarchyid  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION   
  
UPDATE Org_T2   
SET @last_child = LastChild = EmployeeId.GetDescendant(LastChild,NULL)  
WHERE EmployeeId = @mgrid  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(@last_child, @EmpName)  
COMMIT  
END ;  
```  
  
 <span data-ttu-id="da1a8-239">O código a seguir popula a tabela com três linhas e retorna os resultados:</span><span class="sxs-lookup"><span data-stu-id="da1a8-239">The following code populates the table with three rows and returns the results:</span></span>  
  
```  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(hierarchyid::GetRoot(), 'David') ;  
GO  
AddEmp 0x , 'Sariya'  
GO  
AddEmp 0x58 , 'Mary'  
GO  
SELECT * FROM Org_T2  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
EmployeeId LastChild EmployeeName  
---------- --------- ------------  
0x        0x58       David  
0x58      0x5AC0     Sariya  
0x5AC0    NULL       Mary  
```  
  
  
###  <a name="enforcing-a-tree"></a><a name="BKMK_EnforcingTrees"></a> <span data-ttu-id="da1a8-240">Aplicando uma árvore</span><span class="sxs-lookup"><span data-stu-id="da1a8-240">Enforcing a tree</span></span>  
 <span data-ttu-id="da1a8-241">Os exemplos anteriores ilustram como um aplicativo pode assegurar a manutenção de uma árvore.</span><span class="sxs-lookup"><span data-stu-id="da1a8-241">The above examples illustrate how an application can ensure that a tree is maintained.</span></span> <span data-ttu-id="da1a8-242">Para impor uma árvore usando restrições, uma coluna computada que define o pai de cada nó pode ser criada com uma restrição de chave estrangeira na ID de chave primária.</span><span class="sxs-lookup"><span data-stu-id="da1a8-242">To enforce a tree by using constraints, a computed column that defines the parent of each node can be created with a foreign key constraint back to the primary key id.</span></span>  
  
```  
CREATE TABLE Org_T3  
(  
   EmployeeId hierarchyid PRIMARY KEY,  
   ParentId AS EmployeeId.GetAncestor(1) PERSISTED    
      REFERENCES Org_T3(EmployeeId),  
   LastChild hierarchyid,   
   EmployeeName nvarchar(50)  
)  
GO  
```  
  
 <span data-ttu-id="da1a8-243">O método de impor uma relação é preferido quando o código que não é confiável para manter a árvore hierárquica tiver acesso DML direto à tabela.</span><span class="sxs-lookup"><span data-stu-id="da1a8-243">This method of enforcing a relationship is preferred when code that is not trusted to maintain the hierarchical tree has direct DML access to the table.</span></span> <span data-ttu-id="da1a8-244">No entanto, esse método pode reduzir o desempenho porque a restrição deve ser verificada em todas as operações DML.</span><span class="sxs-lookup"><span data-stu-id="da1a8-244">However this method might reduce performance because the constraint must be checked on every DML operation.</span></span>  
  
  
###  <a name="finding-ancestors-by-using-the-clr"></a><a name="findclr"></a> <span data-ttu-id="da1a8-245">Localizando ancestrais usando o CLR</span><span class="sxs-lookup"><span data-stu-id="da1a8-245">Finding Ancestors by Using the CLR</span></span>  
 <span data-ttu-id="da1a8-246">Uma operação comum que envolve dois nós em uma hierarquia é encontrar o mais baixo ancestral comum.</span><span class="sxs-lookup"><span data-stu-id="da1a8-246">A common operation involving two nodes in a hierarchy is to find the lowest common ancestor.</span></span> <span data-ttu-id="da1a8-247">Isso pode ser escrito em um [!INCLUDE[tsql](../includes/tsql-md.md)] ou CLR, pois o `hierarchyid` tipo está disponível em ambos.</span><span class="sxs-lookup"><span data-stu-id="da1a8-247">This can be written in either [!INCLUDE[tsql](../includes/tsql-md.md)] or CLR, because the `hierarchyid` type is available in both.</span></span> <span data-ttu-id="da1a8-248">CLR é recomendado porque o desempenho será mais rápido.</span><span class="sxs-lookup"><span data-stu-id="da1a8-248">CLR is recommended because performance will be faster.</span></span>  
  
 <span data-ttu-id="da1a8-249">Use o código CLR a seguir para listar os ancestrais e localizar o ancestral comum mais baixo:</span><span class="sxs-lookup"><span data-stu-id="da1a8-249">Use the following CLR code to list ancestors and to find the lowest common ancestor:</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Text;  
using Microsoft.SqlServer.Server;  
using Microsoft.SqlServer.Types;  
  
public partial class HierarchyId_Operations  
{  
    [SqlFunction(FillRowMethodName = "FillRow_ListAncestors")]  
    public static IEnumerable ListAncestors(SqlHierarchyId h)  
    {  
        while (!h.IsNull)  
        {  
            yield return (h);  
            h = h.GetAncestor(1);  
        }  
    }  
    public static void FillRow_ListAncestors(Object obj, out SqlHierarchyId ancestor)  
    {  
        ancestor = (SqlHierarchyId)obj;  
    }  
  
    public static HierarchyId CommonAncestor(SqlHierarchyId h1, HierarchyId h2)  
    {  
        while (!h1.IsDescendant(h2))  
            h1 = h1.GetAncestor(1);  
  
        return h1;  
    }  
}  
```  
  
 <span data-ttu-id="da1a8-250">Para usar os métodos **ListAncestor** e **CommonAncestor** nos exemplos [!INCLUDE[tsql](../includes/tsql-md.md)] a seguir, construa a DLL e crie o assembly **HierarchyId_Operations** em [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] executando um código semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="da1a8-250">To use the **ListAncestor** and **CommonAncestor** methods in the following [!INCLUDE[tsql](../includes/tsql-md.md)] examples, build the DLL and create the **HierarchyId_Operations** assembly in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by executing code similar to the following:</span></span>  
  
```  
CREATE ASSEMBLY HierarchyId_Operations   
FROM '<path to DLL>\ListAncestors.dll'  
GO  
```  
  
  
###  <a name="listing-ancestors"></a><a name="ancestors"></a> <span data-ttu-id="da1a8-251">Listando os ancestrais</span><span class="sxs-lookup"><span data-stu-id="da1a8-251">Listing Ancestors</span></span>  
 <span data-ttu-id="da1a8-252">A criação de uma lista de ancestrais de um nó é uma operação comum; por exemplo, para mostrar a posição em uma organização.</span><span class="sxs-lookup"><span data-stu-id="da1a8-252">Creating a list of ancestors of a node is a common operation, for instance to show position in an organization.</span></span> <span data-ttu-id="da1a8-253">Uma das formas de fazer isso é usar uma função com valor de tabela usando a classe **HierarchyId_Operations** definida acima:</span><span class="sxs-lookup"><span data-stu-id="da1a8-253">One way of doing this is by using a table-valued-function using the **HierarchyId_Operations** class defined above:</span></span>  
  
 <span data-ttu-id="da1a8-254">Usando [!INCLUDE[tsql](../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="da1a8-254">Using [!INCLUDE[tsql](../includes/tsql-md.md)]:</span></span>  
  
```  
CREATE FUNCTION ListAncestors (@node hierarchyid)  
RETURNS TABLE (node hierarchyid)  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.ListAncestors  
GO  
```  
  
 <span data-ttu-id="da1a8-255">Exemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="da1a8-255">Example of usage:</span></span>  
  
```  
DECLARE @h hierarchyid  
SELECT @h = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- /1/1/5/2/  
  
SELECT LoginID, OrgNode.ToString() AS LogicalNode  
FROM HumanResources.EmployeeDemo AS ED  
JOIN ListAncestors(@h) AS A   
   ON ED.OrgNode = A.Node  
GO  
```  
  
  
###  <a name="finding-the-lowest-common-ancestor"></a><a name="lowestcommon"></a> <span data-ttu-id="da1a8-256">Localizando o mais baixo ancestral comum</span><span class="sxs-lookup"><span data-stu-id="da1a8-256">Finding the Lowest Common Ancestor</span></span>  
 <span data-ttu-id="da1a8-257">Usando a classe **HierarchyId_Operations** definida acima, crie a seguinte função [!INCLUDE[tsql](../includes/tsql-md.md)] para localizar o mais baixo ancestral comum que envolva dois nós em uma hierarquia:</span><span class="sxs-lookup"><span data-stu-id="da1a8-257">Using the **HierarchyId_Operations** class defined above, create the following [!INCLUDE[tsql](../includes/tsql-md.md)] function to find the lowest common ancestor involving two nodes in a hierarchy:</span></span>  
  
```  
CREATE FUNCTION CommonAncestor (@node1 hierarchyid, @node2 hierarchyid)  
RETURNS hierarchyid  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.CommonAncestor  
GO  
```  
  
 <span data-ttu-id="da1a8-258">Exemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="da1a8-258">Example of usage:</span></span>  
  
```  
DECLARE @h1 hierarchyid, @h2 hierarchyid  
  
SELECT @h1 = OrgNode   
FROM  HumanResources.EmployeeDemo   
WHERE LoginID = 'adventure-works\jossef0' -- Node is /1/1/3/  
  
SELECT @h2 = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- Node is /1/1/5/2/  
  
SELECT OrgNode.ToString() AS LogicalNode, LoginID   
FROM HumanResources.EmployeeDemo    
WHERE OrgNode = dbo.CommonAncestor(@h1, @h2) ;  
```  
  
 <span data-ttu-id="da1a8-259">O nó resultante é /1/1/</span><span class="sxs-lookup"><span data-stu-id="da1a8-259">The resultant node is /1/1/</span></span>  
  
  
###  <a name="moving-subtrees"></a><a name="BKMK_MovingSubtrees"></a> <span data-ttu-id="da1a8-260">Movendo subárvores</span><span class="sxs-lookup"><span data-stu-id="da1a8-260">Moving Subtrees</span></span>  
 <span data-ttu-id="da1a8-261">Outra operação comum é mover subárvores.</span><span class="sxs-lookup"><span data-stu-id="da1a8-261">Another common operation is moving subtrees.</span></span> <span data-ttu-id="da1a8-262">O procedimento a seguir usa a subárvore de **@oldMgr** e a torna (incluindo **@oldMgr** ) uma subárvore de **@newMgr** .</span><span class="sxs-lookup"><span data-stu-id="da1a8-262">The procedure below takes the subtree of **@oldMgr** and makes it (including **@oldMgr**) a subtree of **@newMgr**.</span></span>  
  
```  
CREATE PROCEDURE MoveOrg(@oldMgr nvarchar(256), @newMgr nvarchar(256) )  
AS  
BEGIN  
DECLARE @nold hierarchyid, @nnew hierarchyid  
SELECT @nold = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @oldMgr ;  
  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION  
SELECT @nnew = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @newMgr ;  
  
SELECT @nnew = @nnew.GetDescendant(max(OrgNode), NULL)   
FROM HumanResources.EmployeeDemo WHERE OrgNode.GetAncestor(1)=@nnew ;  
  
UPDATE HumanResources.EmployeeDemo    
SET OrgNode = OrgNode.GetReparentedValue(@nold, @nnew)  
WHERE OrgNode.IsDescendantOf(@nold) = 1 ;  
  
COMMIT TRANSACTION  
END ;  
GO  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="da1a8-263">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da1a8-263">See Also</span></span>  
 <span data-ttu-id="da1a8-264">[Referência de método de tipo de dados hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="da1a8-264">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="da1a8-265">[Tutorial: Usando o tipo de dados HierarchyId](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="da1a8-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span></span>  
 [<span data-ttu-id="da1a8-266">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="da1a8-266">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
