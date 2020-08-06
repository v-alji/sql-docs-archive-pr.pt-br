---
title: 'Exemplo: Recuperando informações de funcionários | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- EXPLICIT mode
ms.assetid: 63cd6569-2600-485b-92b4-1f6ba09db219
author: rothja
ms.author: jroth
ms.openlocfilehash: ae4578aedb7dbcc63388d5ef797e3a0bf5d8c306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574570"
---
# <a name="example-retrieving-employee-information"></a><span data-ttu-id="fa0fb-102">Exemplo: Recuperando informações de funcionários</span><span class="sxs-lookup"><span data-stu-id="fa0fb-102">Example: Retrieving Employee Information</span></span>
  <span data-ttu-id="fa0fb-103">Este exemplo recupera uma ID e um nome de funcionário para cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-103">This example retrieves an employee ID and employee name for each employee.</span></span> <span data-ttu-id="fa0fb-104">No banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , a employeeID pode ser obtida na coluna BusinessEntityID da tabela Employee.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-104">In the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, the employeeID can be obtained from the BusinessEntityID column in the Employee table.</span></span> <span data-ttu-id="fa0fb-105">Nomes de funcionários podem ser obtidos da tabela Person.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-105">Employee names can be obtained from the Person table.</span></span> <span data-ttu-id="fa0fb-106">A coluna BusinessEntityID pode ser usada para unir as tabelas.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-106">The BusinessEntityID column can be used to join the tables.</span></span>  
  
 <span data-ttu-id="fa0fb-107">Digamos que você queira a transformação de FOR XML EXPLICIT para gerar XML, conforme mostrado aqui:</span><span class="sxs-lookup"><span data-stu-id="fa0fb-107">Assume that you want FOR XML EXPLICIT transformation to generate XML as shown in the following:</span></span>  
  
```  
<Employee EmpID="1" >  
  <Name FName="Ken" LName="S??nchez" />  
</Employee>  
...  
```  
  
 <span data-ttu-id="fa0fb-108">Como há dois níveis na hierarquia, você escreve duas consultas `SELECT` e aplica UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-108">Because there are two levels in the hierarchy, you would write two `SELECT` queries and apply UNION ALL.</span></span> <span data-ttu-id="fa0fb-109">Esta é a primeira consulta que recupera valores do elemento <`Employee`> e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-109">This is the first query that retrieves values for the <`Employee`> element and its attributes.</span></span> <span data-ttu-id="fa0fb-110">A consulta atribui `1` como o valor de `Tag` para o elemento <`Employee`> e NULL como `Parent`, pois ele é o elemento de nível superior.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-110">The query assigns `1` as `Tag` value for the <`Employee`> element and NULL as `Parent`, because it is the top-level element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID AS [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="fa0fb-111">Esta é a segunda consulta.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-111">This is the second query.</span></span> <span data-ttu-id="fa0fb-112">Ela recupera valores do elemento <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-112">It retrieves values for the <`Name`> element.</span></span> <span data-ttu-id="fa0fb-113">Ela atribui `2` como o valor `Tag` do elemento <`Name`> e `1` como o valor de marca `Parent` que identifica <`Employee`> como o pai.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-113">It assigns `2` as `Tag` value for the <`Name`> element and `1` as `Parent` tag value identifying <`Employee`> as the parent.</span></span>  
  
```  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="fa0fb-114">Você combina estas consultas com `UNION AL`L, aplica `FOR XML EXPLICIT`, e especifica a cláusula `ORDER BY` exigida.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-114">You combine these queries with `UNION AL`L, apply `FOR XML EXPLICIT`, and specify the required `ORDER BY` clause.</span></span> <span data-ttu-id="fa0fb-115">Você deve classificar o conjunto de linhas primeiro por `BusinessEntityID` e, em seguida, pelo nome para que os valores NULL no nome sejam exibidos primeiro.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-115">You must sort the rowset first by `BusinessEntityID` and then by name so that the NULL values in the name appear first.</span></span> <span data-ttu-id="fa0fb-116">Se você executar a consulta a seguir sem a cláusula FOR XML, poderá ver a tabela universal gerada.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-116">By executing the following query without the FOR XML clause, you can see the universal table generated.</span></span>  
  
 <span data-ttu-id="fa0fb-117">Esta é a consulta final:</span><span class="sxs-lookup"><span data-stu-id="fa0fb-117">This is the final query:</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
ORDER BY [Employee!1!EmpID],[Name!2!FName]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="fa0fb-118">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="fa0fb-118">This is the partial result:</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name FName="Ken" LName="S??nchez" />`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name FName="Terri" LName="Duffy" />`  
  
 `</Employee>`  
  
 `...`  
  
 <span data-ttu-id="fa0fb-119">O primeiro `SELECT` especifica nomes para as colunas no conjunto de linhas resultante.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-119">The first `SELECT` specifies names for columns in the resulting rowset.</span></span> <span data-ttu-id="fa0fb-120">Esses nomes formam dois grupos de colunas.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-120">These names form two column groups.</span></span> <span data-ttu-id="fa0fb-121">O grupo que tem o valor da `Tag``1` no nome da coluna identifica `Employee` como um elemento e `EmpID` como o atributo.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-121">The group that has `Tag` value `1` in the column name identifies `Employee` as an element and `EmpID` as the attribute.</span></span> <span data-ttu-id="fa0fb-122">O outro grupo de colunas tem o valor da `Tag``2` na coluna e identifica <`Name`> como o elemento e `FName` e `LName` como os atributos.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-122">The other column group has `Tag` value `2` in the column and identifies <`Name`> as the element and `FName` and `LName` as the attributes.</span></span>  
  
 <span data-ttu-id="fa0fb-123">Esta tabela mostra o conjunto de linhas parcial gerado pela consulta:</span><span class="sxs-lookup"><span data-stu-id="fa0fb-123">The following table shows the partial rowset generated by the query:</span></span>  
  
 `Tag Parent  Employee!1!EmpID Name!2!FName Name!2!LName`  
  
 `--- ------  ---------------- ------------ ------------`  
  
 `1   NULL    1                NULL         NULL`  
  
 `2   1       1                Ken          S??nchez`  
  
 `1   NULL    2                NULL         NULL`  
  
 `2   1       2                Terri        Duffy`  
  
 `1   NULL    3                NULL         NULL`  
  
 `2   1       3                Roberto      Tamburello`  
  
 `...`  
  
 <span data-ttu-id="fa0fb-124">É assim que as linhas na tabela universal são processadas para produzir a árvore XML resultante:</span><span class="sxs-lookup"><span data-stu-id="fa0fb-124">This is how the rows in the universal table are processed to produce the resulting XML tree:</span></span>  
  
 <span data-ttu-id="fa0fb-125">A primeira linha identifica o valor 1 da `Tag``1`.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-125">The first row identifies `Tag` value `1`.</span></span> <span data-ttu-id="fa0fb-126">Portanto, o grupo de colunas que tem o valor da `Tag``1` é identificado, `Employee!1!EmpID`.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-126">Therefore, the column group that has the `Tag` value `1` is identified, `Employee!1!EmpID`.</span></span> <span data-ttu-id="fa0fb-127">Essa coluna identifica `Employee` como o nome do elemento.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-127">This column identifies `Employee` as the element name.</span></span> <span data-ttu-id="fa0fb-128">Em seguida, é criado um elemento <`Employee`> que tem os atributos `EmpID`.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-128">An <`Employee`> element is then created that has `EmpID` attributes.</span></span> <span data-ttu-id="fa0fb-129">Os valores das colunas correspondentes são atribuídos a esses atributos.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-129">Corresponding column values are assigned to these attributes.</span></span>  
  
 <span data-ttu-id="fa0fb-130">A segunda linha tem o valor da `Tag``2`.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-130">The second row has the `Tag` value `2`.</span></span> <span data-ttu-id="fa0fb-131">Portanto, o grupo de colunas que tem o valor da `Tag``2` no nome da coluna, `Name!2!FName`, `Name!2!LName`, é identificado.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-131">Therefore, the column group that has the `Tag` value `2` in the column name, `Name!2!FName`, `Name!2!LName`, is identified.</span></span> <span data-ttu-id="fa0fb-132">Esses nomes de colunas identificam `Name` como o nome do elemento.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-132">These column names identify `Name` as element name.</span></span> <span data-ttu-id="fa0fb-133">É criado um elemento <`Name`> que tem os atributos `FName` e `LName`.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-133">A <`Name`> element is created that has `FName` and `LName` attributes.</span></span> <span data-ttu-id="fa0fb-134">Em seguida, os valores das colunas correspondentes são atribuídos a esses atributos.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-134">Corresponding column values are then assigned to these attributes.</span></span> <span data-ttu-id="fa0fb-135">Essa linha identifica `1` como `Parent`.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-135">This row identifies `1` as `Parent`.</span></span> <span data-ttu-id="fa0fb-136">Esse elemento filho é adicionado ao elemento <`Employee`> anterior.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-136">This element child is added to the previous <`Employee`> element.</span></span>  
  
 <span data-ttu-id="fa0fb-137">Esse processo é repetido para o restante das linhas do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-137">This process is repeated for rest of the rows in the rowset.</span></span> <span data-ttu-id="fa0fb-138">Observe a importância de ordenar as linhas na tabela universal de forma que FOR XML EXPLICIT possa processar o conjunto de linhas em ordem e gerar o XML desejado.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-138">Note the importance of ordering the rows in the universal table so that FOR XML EXPLICIT can process the rowset in order and generate the XML you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0fb-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa0fb-139">See Also</span></span>  
 [<span data-ttu-id="fa0fb-140">Usar o modo EXPLICIT com FOR XML</span><span class="sxs-lookup"><span data-stu-id="fa0fb-140">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
