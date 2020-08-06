---
title: Gerar irmãos com uma consulta aninhada em modo AUTO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- queries [XML in SQL Server], nested AUTO mode
- nested AUTO mode query
ms.assetid: 748d9899-589d-4420-8048-1258e9e67c20
author: rothja
ms.author: jroth
ms.openlocfilehash: 20362942bdd0f7e7537433b664e5e63461ded499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686176"
---
# <a name="generate-siblings-with-a-nested-auto-mode-query"></a><span data-ttu-id="5b9a3-102">Gerar irmãos com uma consulta aninhada em modo AUTO</span><span class="sxs-lookup"><span data-stu-id="5b9a3-102">Generate Siblings with a Nested AUTO Mode Query</span></span>
  <span data-ttu-id="5b9a3-103">O exemplo a seguir mostra como gerar irmãos usando uma consulta aninhada em modo AUTO.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-103">The following example shows how to generate siblings by using a nested AUTO mode query.</span></span> <span data-ttu-id="5b9a3-104">A única outra maneira de gerar esse tipo de XML é usar o modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-104">The only other way to generate such XML is to use the EXPLICIT mode.</span></span> <span data-ttu-id="5b9a3-105">No entanto isso pode ser trabalhoso.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-105">However, this can be cumbersome.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b9a3-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5b9a3-106">Example</span></span>  
 <span data-ttu-id="5b9a3-107">Esta consulta constrói XML que fornece informações de pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-107">This query constructs XML that provides sales order information.</span></span> <span data-ttu-id="5b9a3-108">Isso inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5b9a3-108">This includes the following:</span></span>  
  
-   <span data-ttu-id="5b9a3-109">Informações de cabeçalho de ordem de venda, `SalesOrderID`, `SalesPersonID`e `OrderDate`.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-109">Sales order header information, `SalesOrderID`, `SalesPersonID`, and `OrderDate`.</span></span> [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="5b9a3-110">armazena essas informações na tabela `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="5b9a3-110">stores this information in the `SalesOrderHeader` table.</span></span>  
  
-   <span data-ttu-id="5b9a3-111">Informações sobre detalhes de pedidos de vendas.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-111">Sales order detail information.</span></span> <span data-ttu-id="5b9a3-112">Isso inclui um ou mais produtos pedidos, o preço unitário e a quantidade pedida.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-112">This includes one or more products ordered, the unit price, and the quantity ordered.</span></span> <span data-ttu-id="5b9a3-113">Essas informações são armazenadas na tabela `SalesOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="5b9a3-113">This information is stored in the `SalesOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="5b9a3-114">Informações sobre o vendedor.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-114">Sales person information.</span></span> <span data-ttu-id="5b9a3-115">Esse é o vendedor que obteve o pedido.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-115">This is the salesperson who took the order.</span></span> <span data-ttu-id="5b9a3-116">A tabela `SalesPerson` fornece o `SalesPersonID`.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-116">The `SalesPerson` table provides the `SalesPersonID`.</span></span> <span data-ttu-id="5b9a3-117">Para essa consulta, você precisa unir essa tabela com a tabela `Employee` para localizar o nome do vendedor.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-117">For this query, you have to join this table to the `Employee` table to find the name of the sales person.</span></span>  
  
 <span data-ttu-id="5b9a3-118">As duas consultas `SELECT` distintas a seguir geram XML com uma pequena diferença na forma.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-118">The two distinct `SELECT` queries that follow generate XML with a small difference in shape.</span></span>  
  
 <span data-ttu-id="5b9a3-119">A primeira consulta gera XML no qual <`SalesPerson`> e <`SalesOrderHeader`> aparecem como filhos irmãos de <`SalesOrder`>:</span><span class="sxs-lookup"><span data-stu-id="5b9a3-119">The first query generates XML in which <`SalesPerson`> and <`SalesOrderHeader`> appear as sibling children of <`SalesOrder`>:</span></span>  
  
```  
SELECT   
      (SELECT top 2 SalesOrderID, SalesPersonID, CustomerID,  
         (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
           from Sales.SalesOrderDetail  
            WHERE  SalesOrderDetail.SalesOrderID =   
                   SalesOrderHeader.SalesOrderID  
            FOR XML AUTO, TYPE)  
        FROM  Sales.SalesOrderHeader  
        WHERE SalesOrderHeader.SalesOrderID = SalesOrder.SalesOrderID  
        for xml auto, type),  
        (SELECT *   
         FROM  (SELECT SalesPersonID, EmployeeID  
              FROM Sales.SalesPerson, HumanResources.Employee  
              WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As   
                     SalesPerson  
         WHERE  SalesPerson.SalesPersonID = SalesOrder.SalesPersonID  
       FOR XML AUTO, TYPE)  
FROM (SELECT SalesOrderHeader.SalesOrderID, SalesOrderHeader.SalesPersonID  
      FROM Sales.SalesOrderHeader, Sales.SalesPerson  
      WHERE SalesOrderHeader.SalesPersonID = SalesPerson.SalesPersonID  
     ) as SalesOrder  
ORDER BY SalesOrder.SalesOrderID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="5b9a3-120">Na consulta anterior, a instrução `SELECT` mais externa faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5b9a3-120">In the previous query, the outermost `SELECT` statement does the following:</span></span>  
  
-   <span data-ttu-id="5b9a3-121">Consulta o conjunto de linhas, `SalesOrder`, especificado na cláusula `FROM`.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-121">Queries the rowset, `SalesOrder`, specified in the `FROM` clause.</span></span> <span data-ttu-id="5b9a3-122">O resultado é um XML com um ou mais elementos <`SalesOrder`>.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-122">The result is an XML with one or more <`SalesOrder`> elements.</span></span>  
  
-   <span data-ttu-id="5b9a3-123">Especifica o modo `AUTO` e a diretiva `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="5b9a3-123">Specifies `AUTO` mode and the `TYPE` directive.</span></span> <span data-ttu-id="5b9a3-124">`AUTO`o modo transforma o resultado da consulta em XML e a `TYPE` diretiva retorna o resultado como `xml` tipo.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-124">`AUTO` mode transforms the query result into XML, and the `TYPE` directive returns the result as `xml` type.</span></span>  
  
-   <span data-ttu-id="5b9a3-125">Inclui duas instruções `SELECT` aninhadas separadas por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-125">Includes two nested `SELECT` statements separated by a comma.</span></span> <span data-ttu-id="5b9a3-126">O primeiro `SELECT` aninhado recupera informações sobre pedidos de vendas, cabeçalho e detalhes, e o segundo `SELECT` aninhado recupera informações sobre o vendedor.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-126">The first nested `SELECT` retrieves sales order information, header and details, and the second nested `SELECT` statement retrieves salesperson information.</span></span>  
  
    -   <span data-ttu-id="5b9a3-127">A própria instrução `SELECT` que recupera `SalesOrderID`, `SalesPersonID`e `CustomerID` inclui outra instrução `SELECT ... FOR XML` aninhada (com modo `AUTO` e diretiva `TYPE` ) que retorna informações sobre detalhes do pedido de vendas.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-127">The `SELECT` statement that retrieves `SalesOrderID`, `SalesPersonID`, and `CustomerID` itself includes another nested `SELECT ... FOR XML` statement (with `AUTO` mode and `TYPE` directive) that returns sales order detail information.</span></span>  
  
 <span data-ttu-id="5b9a3-128">A instrução `SELECT` que recupera as informações do vendedor consulta um conjunto de linhas, `SalesPerson`, criado na cláusula `FROM` .</span><span class="sxs-lookup"><span data-stu-id="5b9a3-128">The `SELECT` statement that retrieves the sales person information queries a rowset, `SalesPerson`, created in the `FROM` clause.</span></span> <span data-ttu-id="5b9a3-129">Para que as consultas `FOR XML` funcionem, você deve fornecer um nome para o conjunto de linhas anônimo gerado na cláusula `FROM` .</span><span class="sxs-lookup"><span data-stu-id="5b9a3-129">For `FOR XML` queries to work, you must provide a name for the anonymous rowset generated in the `FROM` clause.</span></span> <span data-ttu-id="5b9a3-130">Nesse caso, o nome fornecido é `SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-130">In this case, the name provided is `SalesPerson`.</span></span>  
  
 <span data-ttu-id="5b9a3-131">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="5b9a3-131">This is the partial result:</span></span>  
  
```  
<SalesOrder>  
  <Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  </Sales.SalesOrderHeader>  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</SalesOrder>  
...  
```  
  
 <span data-ttu-id="5b9a3-132">A consulta a seguir gera as mesmas informações sobre pedidos de vendas, exceto que no XML resultante, o <`SalesPerson`> aparece como irmão de <`SalesOrderDetail`>:</span><span class="sxs-lookup"><span data-stu-id="5b9a3-132">The following query generates the same sales order information, except that in the resulting XML, the <`SalesPerson`> appears as a sibling of <`SalesOrderDetail`>:</span></span>  
  
```  
<SalesOrder>  
    <SalesOrderHeader ...>  
          <SalesOrderDetail .../>  
          <SalesOrderDetail .../>  
          ...  
          <SalesPerson .../>  
    </SalesOrderHeader>  
  
</SalesOrder>  
<SalesOrder>  
  ...  
</SalesOrder>  
```  
  
 <span data-ttu-id="5b9a3-133">Esta é a consulta:</span><span class="sxs-lookup"><span data-stu-id="5b9a3-133">This is the query:</span></span>  
  
```  
SELECT SalesOrderID, SalesPersonID, CustomerID,  
             (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
              from Sales.SalesOrderDetail  
              WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
              FOR XML AUTO, TYPE),  
              (SELECT *   
               FROM  (SELECT SalesPersonID, EmployeeID  
                    FROM Sales.SalesPerson, HumanResources.Employee  
                    WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
               WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
         FOR XML AUTO, TYPE)  
FROM Sales.SalesOrderHeader  
WHERE SalesOrderID=43659 or SalesOrderID=43660  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="5b9a3-134">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="5b9a3-134">This is the result:</span></span>  
  
```  
<Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
<Sales.SalesOrderHeader SalesOrderID="43660" SalesPersonID="279" CustomerID="117">  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="762" OrderQty="1" UnitPrice="419.4589" />  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="758" OrderQty="1" UnitPrice="874.7940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
```  
  
 <span data-ttu-id="5b9a3-135">Como a diretiva `TYPE` retorna um resultado de consulta como tipo `xml`, é possível consultar o XML resultante usando vários métodos de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-135">Because the `TYPE` directive returns a query result as `xml` type, you can query the resulting XML by using various `xml` data type methods.</span></span> <span data-ttu-id="5b9a3-136">Para obter mais informações, veja [Métodos do tipo de dados xml](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="5b9a3-136">For more information, see [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span> <span data-ttu-id="5b9a3-137">Na consulta a seguir, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5b9a3-137">In the following query, note the following:</span></span>  
  
-   <span data-ttu-id="5b9a3-138">A consulta anterior é adicionada na cláusula `FROM` .</span><span class="sxs-lookup"><span data-stu-id="5b9a3-138">The previous query is added in the `FROM` clause.</span></span> <span data-ttu-id="5b9a3-139">O resultado da consulta é retornado como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-139">The query result is returned as a table.</span></span> <span data-ttu-id="5b9a3-140">Observe o alias de `XmlCol` que é adicionado.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-140">Note the `XmlCol` alias that is added.</span></span>  
  
-   <span data-ttu-id="5b9a3-141">A cláusula `SELECT` especifica um XQuery em relação à `XmlCol` retornada na cláusula `FROM` .</span><span class="sxs-lookup"><span data-stu-id="5b9a3-141">The `SELECT` clause specifies an XQuery against the `XmlCol` returned in the `FROM` clause.</span></span> <span data-ttu-id="5b9a3-142">O método `query()` do tipo de dados `xml` é usado para especificar o XQuery.</span><span class="sxs-lookup"><span data-stu-id="5b9a3-142">The `query()` method of the `xml` data type is used in specifying the XQuery.</span></span> <span data-ttu-id="5b9a3-143">Para obter mais informações, veja [Método query&#40;&#41; &#40;tipo de dados xml&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="5b9a3-143">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
    ```  
    SELECT XmlCol.query('<Root> { /* } </Root>')  
    FROM (  
    SELECT SalesOrderID, SalesPersonID, CustomerID,  
                 (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
                  from Sales.SalesOrderDetail  
                  WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
                  FOR XML AUTO, TYPE),  
                  (SELECT *   
                   FROM  (SELECT SalesPersonID, EmployeeID  
                        FROM Sales.SalesPerson, HumanResources.Employee  
                        WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
                   WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
             FOR XML AUTO, TYPE)  
    FROM Sales.SalesOrderHeader  
    WHERE SalesOrderID='43659' or SalesOrderID='43660'  
    FOR XML AUTO, TYPE ) as T(XmlCol)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5b9a3-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5b9a3-144">See Also</span></span>  
 [<span data-ttu-id="5b9a3-145">Usar consultas FOR XML aninhadas</span><span class="sxs-lookup"><span data-stu-id="5b9a3-145">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
