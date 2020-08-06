---
title: Usar o modo AUTO com FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, AUTO mode
- ELEMENTS option
- FOR XML AUTO mode
- AUTO FOR XML mode
ms.assetid: 7140d656-1d42-4f01-a533-5251429f4450
author: rothja
ms.author: jroth
ms.openlocfilehash: 232cc046667c6d31cb9657a7abdc862204507d23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574567"
---
# <a name="use-auto-mode-with-for-xml"></a><span data-ttu-id="33702-102">Usar o modo AUTO com FOR XML</span><span class="sxs-lookup"><span data-stu-id="33702-102">Use AUTO Mode with FOR XML</span></span>
  <span data-ttu-id="33702-103">Conforme descrito em [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), o modo AUTO retorna os resultados da consulta como elementos XML aninhados.</span><span class="sxs-lookup"><span data-stu-id="33702-103">As described in [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), AUTO mode returns query results as nested XML elements.</span></span> <span data-ttu-id="33702-104">Isso não fornece muito controle sobre a forma do XML gerado em um resultado de consulta.</span><span class="sxs-lookup"><span data-stu-id="33702-104">This does not provide much control over the shape of the XML generated from a query result.</span></span> <span data-ttu-id="33702-105">As consultas em modo AUTO são úteis para gerar hierarquias simples.</span><span class="sxs-lookup"><span data-stu-id="33702-105">The AUTO mode queries are useful if you want to generate simple hierarchies.</span></span> <span data-ttu-id="33702-106">No entanto, [Usar o modo EXPLICIT com FOR XML](use-explicit-mode-with-for-xml.md) e [Usar o modo PATH com FOR XML](use-path-mode-with-for-xml.md) fornecem mais controle e flexibilidade para decidir a forma do XML em um resultado de consulta.</span><span class="sxs-lookup"><span data-stu-id="33702-106">However, [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) and [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) provide more control and flexibility in deciding the shape of the XML from a query result.</span></span>  
  
 <span data-ttu-id="33702-107">Cada tabela na cláusula FROM, na qual pelo menos uma coluna esteja listada na cláusula SELECT, é representada como um elemento XML.</span><span class="sxs-lookup"><span data-stu-id="33702-107">Each table in the FROM clause, from which at least one column is listed in the SELECT clause, is represented as an XML element.</span></span> <span data-ttu-id="33702-108">As colunas listadas na cláusula SELECT serão mapeadas para atributos ou subelementos, se a opção ELEMENTS opcional estiver especificada na cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="33702-108">The columns listed in the SELECT clause are mapped to attributes or subelements, if the optional ELEMENTS option is specified in the FOR XML clause.</span></span>  
  
 <span data-ttu-id="33702-109">A hierarquia XML, o aninhamento dos elementos, no XML resultante é baseada na ordem das tabelas identificada pelas colunas especificadas na cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="33702-109">The XML hierarchy, nesting of the elements, in the resulting XML is based on the order of tables identified by the columns specified in the SELECT clause.</span></span> <span data-ttu-id="33702-110">Portanto a ordem na qual os nomes das colunas são especificados na cláusula SELECT é significativa.</span><span class="sxs-lookup"><span data-stu-id="33702-110">Therefore, the order in which column names are specified in the SELECT clause is significant.</span></span> <span data-ttu-id="33702-111">A primeira tabela da estrema esquerda identificada forma o elemento superior no documento XML resultante.</span><span class="sxs-lookup"><span data-stu-id="33702-111">The first, leftmost table that is identified forms the top element in the resulting XML document.</span></span> <span data-ttu-id="33702-112">A segunda tabela da extremidade esquerda, identificada pelas colunas na instrução SELECT, forma um subelemento dentro do elemento superior e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="33702-112">The second leftmost table, identified by columns in the SELECT statement, forms a subelement within the top element, and so on.</span></span>  
  
 <span data-ttu-id="33702-113">Se um nome de coluna listado na cláusula SELECT for de uma tabela que já está identificada por uma coluna especificada anteriormente na cláusula SELECT, a coluna será adicionada como um atributo do elemento já criado, em vez de abrir um novo nível de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="33702-113">If a column name listed in the SELECT clause is from a table that is already identified by a previously specified column in the SELECT clause, the column is added as an attribute of the element already created, instead of opening a new level of hierarchy.</span></span> <span data-ttu-id="33702-114">Se a opção ELEMENTS estiver especificada, a coluna será adicionada como um atributo.</span><span class="sxs-lookup"><span data-stu-id="33702-114">If the ELEMENTS option is specified, the column is added as an attribute.</span></span>  
  
 <span data-ttu-id="33702-115">Por exemplo, execute esta consulta:</span><span class="sxs-lookup"><span data-stu-id="33702-115">For example, execute this query:</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO  
```  
  
 <span data-ttu-id="33702-116">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="33702-116">This is the partial result:</span></span>  
  
```  
<Cust CustomerID="1" CustomerType="S">  
  <OrderHeader CustomerID="1" SalesOrderID="43860" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="44501" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="45283" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="46042" Status="5" />  
</Cust>  
...  
```  
  
 <span data-ttu-id="33702-117">Observe o seguinte na cláusula SELECT:</span><span class="sxs-lookup"><span data-stu-id="33702-117">Note the following in the SELECT clause:</span></span>  
  
-   <span data-ttu-id="33702-118">CustomerID faz referência à tabela Cust.</span><span class="sxs-lookup"><span data-stu-id="33702-118">The CustomerID references the Cust table.</span></span> <span data-ttu-id="33702-119">Portanto um elemento <`Cust`> é criado e CustomerID é adicionado como seu atributo.</span><span class="sxs-lookup"><span data-stu-id="33702-119">Therefore, a <`Cust`> element is created and CustomerID is added as its attribute.</span></span>  
  
-   <span data-ttu-id="33702-120">Em seguida, três colunas, OrderHeader.CustomerID, OrderHeader.SaleOrderID e OrderHeader.Status, fazem referência à tabela OrderHeader.</span><span class="sxs-lookup"><span data-stu-id="33702-120">Next, three columns, OrderHeader.CustomerID, OrderHeader.SaleOrderID, and OrderHeader.Status, reference the OrderHeader table.</span></span> <span data-ttu-id="33702-121">Portanto um elemento <`OrderHeader`> é adicionado como um subelemento do elemento <`Cust`> e as três colunas são adicionadas como atributos de <`OrderHeader`>.</span><span class="sxs-lookup"><span data-stu-id="33702-121">Therefore, an <`OrderHeader`> element is added as a subelement of the <`Cust`> element and the three columns are added as attributes of <`OrderHeader`>.</span></span>  
  
-   <span data-ttu-id="33702-122">Em seguida, a coluna Cust.CustomerType faz referência novamente à tabela Cust que já foi identificada pela coluna Cust.CustomerID.</span><span class="sxs-lookup"><span data-stu-id="33702-122">Next, the Cust.CustomerType column again references the Cust table that was already identified by the Cust.CustomerID column.</span></span> <span data-ttu-id="33702-123">Portanto  nenhum elemento novo é criado.</span><span class="sxs-lookup"><span data-stu-id="33702-123">Therefore, no new element is created.</span></span> <span data-ttu-id="33702-124">Em vez disso, o atributo CustomerType é adicionado ao elemento <`Cust`> que foi criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="33702-124">Instead, the CustomerType attribute is added to the <`Cust`> element that was previously created.</span></span>  
  
-   <span data-ttu-id="33702-125">A consulta especifica alias para os nomes das tabelas.</span><span class="sxs-lookup"><span data-stu-id="33702-125">The query specifies aliases for the table names.</span></span> <span data-ttu-id="33702-126">Esses alias aparecem como nomes de elementos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="33702-126">These aliases appear as corresponding element names.</span></span>  
  
-   <span data-ttu-id="33702-127">ORDER BY é necessário para agrupar todos os filhos sob um pai.</span><span class="sxs-lookup"><span data-stu-id="33702-127">ORDER BY is required to group all children under one parent.</span></span>  
  
 <span data-ttu-id="33702-128">Esta consulta é semelhante a anterior, exceto que a cláusula SELECT especifica colunas na tabela OrderHeader antes das colunas na tabela Cust.</span><span class="sxs-lookup"><span data-stu-id="33702-128">This query is similar to the previous one, except the SELECT clause specifies columns in the OrderHeader table before the columns in the Cust table.</span></span> <span data-ttu-id="33702-129">Portanto o primeiro elemento <`OrderHeader`> é criado e, em seguida, o elemento filho <`Cust`> é adicionado a ele.</span><span class="sxs-lookup"><span data-stu-id="33702-129">Therefore, first <`OrderHeader`> element is created and then the <`Cust`> child element is added to it.</span></span>  
  
```  
select OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerID,   
       Cust.CustomerType  
from Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
where Cust.CustomerID = OrderHeader.CustomerID  
for xml auto  
```  
  
 <span data-ttu-id="33702-130">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="33702-130">This is the partial result:</span></span>  
  
```  
<OrderHeader CustomerID="1" SalesOrderID="43860" Status="5">  
  <Cust CustomerID="1" CustomerType="S" />  
</OrderHeader>  
...  
```  
  
 <span data-ttu-id="33702-131">Se a opção ELEMENTS for adicionada à cláusula FOR XML, XML centrado em elemento será retornado.</span><span class="sxs-lookup"><span data-stu-id="33702-131">If the ELEMENTS option is added in the FOR XML clause, element-centric XML is returned.</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="33702-132">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="33702-132">This is the partial result:</span></span>  
  
```  
<Cust>  
  <CustomerID>1</CustomerID>  
  <CustomerType>S</CustomerType>  
  <OrderHeader>  
    <CustomerID>1</CustomerID>  
    <SalesOrderID>43860</SalesOrderID>  
    <Status>5</Status>  
  </OrderHeader>  
   ...  
</Cust>  
...  
```  
  
 <span data-ttu-id="33702-133">Nessa consulta, os valores de CustomerID são comparados de uma linha à seguinte, para criar os elementos \<Cust>, pois CustomerID é a chave primária da tabela.</span><span class="sxs-lookup"><span data-stu-id="33702-133">In this query, the CustomerID values are compared from one row to the next in creating the \<Cust> elements, because CustomerID is the primary key of the table.</span></span> <span data-ttu-id="33702-134">Se CustomerID não for identificado como a chave primária da tabela, todos os valores das colunas (CustomerID e CustomerType nessa consulta) serão comparados de uma linha para a seguinte;</span><span class="sxs-lookup"><span data-stu-id="33702-134">If CustomerID is not identified as the primary key for the table, all the column values (CustomerID, CustomerType in this query) are compared from one row to the next.</span></span> <span data-ttu-id="33702-135">Se os valores forem diferentes, um novo elemento \<Cust> será adicionado ao XML.</span><span class="sxs-lookup"><span data-stu-id="33702-135">If the values differ, a new \<Cust> element is added to the XML.</span></span>  
  
 <span data-ttu-id="33702-136">Ao comparar esses valores de colunas, se qualquer uma das colunas a serem comparadas for do tipo **text**, **ntext**, **image**ou **xml**, FOR XML assumirá que os valores são diferentes e não comparados, embora possam parecer os mesmos.</span><span class="sxs-lookup"><span data-stu-id="33702-136">When comparing these column values, if any of the columns to be compared are of type **text**, **ntext**, **image**, or **xml**, FOR XML assumes that the values are different and not compared, even though they may be the same.</span></span> <span data-ttu-id="33702-137">Isso é porque a comparação de objetos grandes não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="33702-137">This is because comparing large objects is not supported.</span></span> <span data-ttu-id="33702-138">Os elementos são adicionados ao resultado de cada linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="33702-138">Elements are added to the result for each row selected.</span></span> <span data-ttu-id="33702-139">Observe que as colunas **(n)varchar(max)** e **varbinary(max)** são comparadas.</span><span class="sxs-lookup"><span data-stu-id="33702-139">Note that columns of **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="33702-140">Quando uma coluna na cláusula SELECT não puder ser associada a qualquer uma das tabelas identificadas na cláusula FROM, como no caso de uma coluna de agregação ou computada, a coluna será adicionada ao documento XML no nível de aninhamento mais profundo em vigor quando ela for encontrada na lista.</span><span class="sxs-lookup"><span data-stu-id="33702-140">When a column in the SELECT clause cannot be associated with any of the tables identified in the FROM clause, as in the case of an aggregate column or computed column, the column is added in the XML document in the deepest nesting level in place when it is encountered in the list.</span></span> <span data-ttu-id="33702-141">Se ela aparecer como a primeira coluna na cláusula SELECT, a coluna será adicionada ao elemento superior.</span><span class="sxs-lookup"><span data-stu-id="33702-141">If such a column appears as the first column in the SELECT clause, the column is added to the top element.</span></span>  
  
 <span data-ttu-id="33702-142">Se o caractere curinga asterisco (\*) for especificado na cláusula SELECT, o aninhamento será determinado da mesma maneira como descrito anteriormente, com base na ordem em que as linhas são retornadas pelo mecanismo de consulta.</span><span class="sxs-lookup"><span data-stu-id="33702-142">If the asterisk (\*) wildcard character is specified in the SELECT clause, the nesting is determined in the same way as previously described, based on the order that the rows are returned by the query engine.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33702-143">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="33702-143">In This Section</span></span>  
 <span data-ttu-id="33702-144">Os seguintes tópicos fornecem mais informações sobre o modo AUTO:</span><span class="sxs-lookup"><span data-stu-id="33702-144">The following topics provide more information about AUTO mode:</span></span>  
  
-   [<span data-ttu-id="33702-145">Usar a opção BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="33702-145">Use the BINARY BASE64 Option</span></span>](use-the-binary-base64-option.md)  
  
-   [<span data-ttu-id="33702-146">Heurística de modo AUTO na formação do XML retornado</span><span class="sxs-lookup"><span data-stu-id="33702-146">AUTO Mode Heuristics in Shaping Returned XML</span></span>](auto-mode-heuristics-in-shaping-returned-xml.md)  
  
-   [<span data-ttu-id="33702-147">Exemplos: Usando o modo AUTO</span><span class="sxs-lookup"><span data-stu-id="33702-147">Examples: Using AUTO Mode</span></span>](examples-using-auto-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="33702-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33702-148">See Also</span></span>  
 <span data-ttu-id="33702-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="33702-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="33702-150">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="33702-150">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
