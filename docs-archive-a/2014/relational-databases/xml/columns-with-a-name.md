---
title: Colunas com um nome | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: c994e089-4cfc-4e9b-b7fc-e74f6014b51a
author: rothja
ms.author: jroth
ms.openlocfilehash: 32cfe617b80ed216374249961b85eae401011a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679200"
---
# <a name="columns-with-a-name"></a><span data-ttu-id="e7d0a-102">Colunas com um nome</span><span class="sxs-lookup"><span data-stu-id="e7d0a-102">Columns with a Name</span></span>
  <span data-ttu-id="e7d0a-103">As seguintes são as condições específicas nas quais colunas de conjunto de linhas com um nome são mapeadas, diferenciando maiúsculas e minúsculas, para o XML resultante:</span><span class="sxs-lookup"><span data-stu-id="e7d0a-103">The following are the specific conditions in which rowset columns with a name are mapped, case-sensitive, to the resulting XML:</span></span>  
  
-   <span data-ttu-id="e7d0a-104">O nome da coluna começa com uma arroba (\@).</span><span class="sxs-lookup"><span data-stu-id="e7d0a-104">The column name starts with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="e7d0a-105">O nome da coluna não começa com uma arroba (\@).</span><span class="sxs-lookup"><span data-stu-id="e7d0a-105">The column name does not start with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="e7d0a-106">O nome da coluna não começa com uma arroba \@ e contém uma barra (/).</span><span class="sxs-lookup"><span data-stu-id="e7d0a-106">The column name does not start with an at sign\@ and contains a slash mark (/).</span></span>  
  
-   <span data-ttu-id="e7d0a-107">Várias colunas compartilham o mesmo prefixo.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-107">Several columns share the same prefix.</span></span>  
  
-   <span data-ttu-id="e7d0a-108">Uma coluna tem um nome diferente.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-108">One column has a different name.</span></span>  
  
## <a name="column-name-starts-with-an-at-sign-"></a><span data-ttu-id="e7d0a-109">O nome da coluna começa com uma arroba (\@)</span><span class="sxs-lookup"><span data-stu-id="e7d0a-109">Column Name Starts with an At Sign (\@)</span></span>  
 <span data-ttu-id="e7d0a-110">Se o nome da coluna começar com um sinal de arroba ( \@ ) e não contiver uma barra (/), um atributo do <`row` elemento> que tenha o valor da coluna correspondente será criado.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-110">If the column name starts with an at sign (\@) and does not contain a slash mark (/), an attribute of the <`row`> element that has the corresponding column value is created.</span></span> <span data-ttu-id="e7d0a-111">Por exemplo, a consulta a seguir retorna um conjunto de linhas de duas colunas (\@PmId, Name).</span><span class="sxs-lookup"><span data-stu-id="e7d0a-111">For example, the following query returns a two-column (\@PmId, Name) rowset.</span></span> <span data-ttu-id="e7d0a-112">No XML resultante, um atributo **PmId** é adicionado ao elemento <`row`> correspondente e um valor de ProductModelID é atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-112">In the resulting XML, a **PmId** attribute is added to the corresponding <`row`> element and a value of ProductModelID is assigned to it.</span></span>  
  
```  
  
SELECT ProductModelID as "@PmId",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
  
```  
  
 <span data-ttu-id="e7d0a-113">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="e7d0a-113">This is the result:</span></span>  
  
```  
<row PmId="7">  
  <Name>HL Touring Frame</Name>  
</row>  
```  
  
 <span data-ttu-id="e7d0a-114">Observe que os atributos devem vir antes de quaisquer outros tipos de nós, como nós de elemento e nós de texto, no mesmo nível.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-114">Note that attributes must come before any other node types, such as element nodes and text nodes, in the same level.</span></span> <span data-ttu-id="e7d0a-115">A consulta a seguir retornará um erro:</span><span class="sxs-lookup"><span data-stu-id="e7d0a-115">The following query will return an error:</span></span>  
  
```  
SELECT Name,  
       ProductModelID as "@PmId"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign-"></a><span data-ttu-id="e7d0a-116">O nome da coluna não começa com uma arroba (\@)</span><span class="sxs-lookup"><span data-stu-id="e7d0a-116">Column Name Does Not Start with an At Sign (\@)</span></span>  
 <span data-ttu-id="e7d0a-117">Se o nome da coluna não começar com um sinal de arroba ( \@ ), não for um dos testes de nó XPath e não contiver uma barra (/), um elemento XML que é um subelemento do elemento Row, <>, `row` por padrão, será criado.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-117">If the column name does not start with an at sign (\@), is not one of the XPath node tests, and does not contain a slash mark (/), an XML element that is a subelement of the row element, <`row`> by default, is created.</span></span>  
  
 <span data-ttu-id="e7d0a-118">A consulta a seguir especifica o nome da coluna, o resultado.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-118">The following query specifies the column name, the result.</span></span> <span data-ttu-id="e7d0a-119">Portanto um filho do elemento <`result`> é adicionado ao elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-119">Therefore, a <`result`> element child is added to the <`row`> element.</span></span>  
  
```  
SELECT 2+2 as result  
for xml PATH  
```  
  
 <span data-ttu-id="e7d0a-120">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="e7d0a-120">This is the result:</span></span>  
  
```  
<row>  
  <result>4</result>  
</row>  
```  
  
 <span data-ttu-id="e7d0a-121">O exemplo a seguir especifica o nome da coluna, ManuWorkCenterInformation, para o XML retornado pelo XQuery especificado em relação à coluna Instructions de tipo **xml**.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-121">The following query specifies the column name, ManuWorkCenterInformation, for the XML returned by the XQuery specified against Instructions column of **xml** type.</span></span> <span data-ttu-id="e7d0a-122">Portanto um elemento <`ManuWorkCenterInformation`> é adicionado como um filho ao elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-122">Therefore, a <`ManuWorkCenterInformation`> element is added as a child of the <`row`> element.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') as ManuWorkCenterInformation  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
 <span data-ttu-id="e7d0a-123">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="e7d0a-123">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>7</ProductModelID>  
  <Name>HL Touring Frame</Name>  
  <ManuWorkCenterInformation>  
    <MI:Location ...LocationID="10" ...></MI:Location>  
    <MI:Location ...LocationID="20" ...></MI:Location>  
     ...  
  </ManuWorkCenterInformation>  
</row>  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign--and-contains-a-slash-mark-"></a><span data-ttu-id="e7d0a-124">O nome da coluna não começa com uma arroba \@ e contém uma barra (/)</span><span class="sxs-lookup"><span data-stu-id="e7d0a-124">Column Name Does Not Start with an At Sign (\@) and Contains a Slash Mark (/)</span></span>  
 <span data-ttu-id="e7d0a-125">Se o nome da coluna não começar com uma arroba (\@), mas contiver uma barra (/), o nome da coluna indicará uma hierarquia XML.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-125">If the column name does not start with an at sign (\@), but contains a slash mark (/), the column name indicates an XML hierarchy.</span></span> <span data-ttu-id="e7d0a-126">Por exemplo, se o nome da coluna for “Name1/Name2/Name3.../Name***n*** ”, cada Name***i*** representará um nome do elemento que está aninhado no elemento da linha atual (para i=1) ou que está sob o elemento que tem o nome Name***i-1***.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-126">For example, if the column name is "Name1/Name2/Name3.../Name***n*** ", each Name***i*** represents an element name that is nested in the current row element (for i=1) or that is under the element that has the name Name***i-1***.</span></span> <span data-ttu-id="e7d0a-127">Se Name***n*** começar com "\@", ele será mapeado para um atributo de elemento Name ***n-1***.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-127">If Name***n*** starts with '\@', it is mapped to an attribute of Name***n-1*** element.</span></span>  
  
 <span data-ttu-id="e7d0a-128">Por exemplo, a consulta a seguir retorna a ID e o nome de um funcionário que são representados como um elemento complexo EmpName que contém um Nome, Segundo nome e Sobrenome.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-128">For example, the following query returns an employee ID and name that are represented as a complex element EmpName that contains a First, Middle, and Last name.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="e7d0a-129">Os nomes de colunas são usados como um caminho para construir XML no modo PATH.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-129">The column names are used as a path in constructing XML in the PATH mode.</span></span> <span data-ttu-id="e7d0a-130">O nome da coluna que contém valores de ID de funcionário começa com ' \@ '. Portanto, um atributo, **empid**, é adicionado ao elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-130">The column name that contains employee ID values, starts with '\@'.Therefore, an attribute, **EmpID**, is added to the <`row`> element.</span></span> <span data-ttu-id="e7d0a-131">Todas as outras colunas incluem uma barra ('/') no nome da coluna que indica hierarquia.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-131">All other columns include a slash mark ('/') in the column name that indicates hierarchy.</span></span> <span data-ttu-id="e7d0a-132">O XML resultante terá o filho de <`EmpName`> sob o elemento <`row`> e o filho de <`EmpName`> terá os filhos dos elementos <`First`>, <`Middle`> e <`Last`>.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-132">The resulting XML will have the <`EmpName`> child under the <`row`> element, and the <`EmpName`> child will have <`First`>, <`Middle`> and <`Last`> element children.</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="e7d0a-133">O segundo nome do funcionário é nulo e, por padrão, o valor nulo é mapeado para a ausência do elemento ou atributo.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-133">The employee middle name is null and, by default, the null value maps to the absence of the element or attribute.</span></span> <span data-ttu-id="e7d0a-134">Se você quiser elementos gerados para os valores NULL, poderá especificar a diretiva ELEMENTS com XSINIL conforme mostrado nesta consulta.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-134">If you want elements generated for the NULL values, you can specify the ELEMENTS directive with XSINIL as shown in this query.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="e7d0a-135">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="e7d0a-135">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
      EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="e7d0a-136">Por padrão, o modo PATH gera XML centrado em elemento.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-136">By default, the PATH mode generates element-centric XML.</span></span> <span data-ttu-id="e7d0a-137">Portanto especificar a diretiva ELEMENTS em uma consulta em modo PATH não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-137">Therefore, specifying the ELEMENTS directive in a PATH mode query has no effect.</span></span> <span data-ttu-id="e7d0a-138">No entanto, conforme mostrado no exemplo anterior, a diretiva ELEMENTS é útil com XSINIL para gerar elementos para valores nulos.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-138">However, as shown in the previous example, the ELEMENTS directive is useful with XSINIL to generate elements for null values.</span></span>  
  
 <span data-ttu-id="e7d0a-139">Além da ID e do nome, a consulta a seguir recupera um endereço de funcionário.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-139">Besides the ID and name, the following query retrieves an employee address.</span></span> <span data-ttu-id="e7d0a-140">De acordo com o caminho nos nomes das colunas de endereço, um filho do elemento <`Address`> é adicionado ao elemento <`row`> e os detalhes do endereço são adicionados como filhos do elemento <`Address`>.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-140">As per the path in the column names for address columns, an <`Address`> element child is added to the <`row`> element and the address details are added as element children of the <`Address`> element.</span></span>  
  
```  
SELECT EmployeeID   "@EmpID",   
       FirstName    "EmpName/First",   
       MiddleName   "EmpName/Middle",   
       LastName     "EmpName/Last",  
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City         "Address/City"  
FROM   HumanResources.Employee E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="e7d0a-141">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="e7d0a-141">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
</row>  
```  
  
## <a name="several-columns-share-the-same-path-prefix"></a><span data-ttu-id="e7d0a-142">Várias colunas compartilham o mesmo prefixo</span><span class="sxs-lookup"><span data-stu-id="e7d0a-142">Several Columns Share the Same Path Prefix</span></span>  
 <span data-ttu-id="e7d0a-143">Se várias colunas subsequentes compartilharem o mesmo prefixo de caminho, elas serão agrupadas sob o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-143">If several subsequent columns share the same path prefix, they are grouped together under the same name.</span></span> <span data-ttu-id="e7d0a-144">Se diferentes prefixos de namespace estiverem sendo usados, mesmo que estejam associados ao mesmo namespace, um caminho será considerado diferente.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-144">If different namespace prefixes are being used even if they are bound to the same namespace, a path is considered different.</span></span> <span data-ttu-id="e7d0a-145">Na consulta anterior, as colunas FirstName, MiddleName e LastName compartilham o memo prefixo EmpName. Portanto elas são adicionadas como filhas do elemento <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-145">In the previous query, the FirstName, MiddleName, and LastName columns share the same EmpName prefix.Therefore, they are added as children of the <`EmpName`> element.</span></span> <span data-ttu-id="e7d0a-146">Esse também é o caso quando o elemento <`Address`> foi criado no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-146">This is also the case when you were creating the <`Address`> element in the previous example.</span></span>  
  
## <a name="one-column-has-a-different-name"></a><span data-ttu-id="e7d0a-147">Uma coluna tem um nome diferente</span><span class="sxs-lookup"><span data-stu-id="e7d0a-147">One Column Has a Different Name</span></span>  
 <span data-ttu-id="e7d0a-148">Se uma coluna com um nome diferente aparecer no meio, ela quebrará o agrupamento, conforme mostrado na seguinte consulta modificada.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-148">If a column with a different name appears in between, it will break the grouping, as shown in the following modified query.</span></span> <span data-ttu-id="e7d0a-149">A consulta quebra o agrupamento de FirstName, MiddleName e LastName, conforme especificado na consulta anterior, adicionando colunas de endereço no meio das colunas FirstName e MiddleName.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-149">The query breaks the grouping of FirstName, MiddleName, and LastName, as specified in the previous query, by adding address columns in between the FirstName and MiddleName columns.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName "EmpName/First",   
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City "Address/City",  
       MiddleName "EmpName/Middle",   
       LastName "EmpName/Last"  
FROM   HumanResources.EmployeeAddress E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="e7d0a-150">Como resultado, a consulta cria dois elementos <`EmpName`>.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-150">As a result, the query creates two <`EmpName`> elements.</span></span> <span data-ttu-id="e7d0a-151">O primeiro elemento <`EmpName`> tem o filho do elemento <`FirstName`> e o segundo elemento <`EmpName`> tem os filhos dos elementos <`MiddleName`> e <`LastName`>.</span><span class="sxs-lookup"><span data-stu-id="e7d0a-151">The first <`EmpName`> element has the <`FirstName`> element child and the second <`EmpName`> element has the <`MiddleName`> and <`LastName`> element children.</span></span>  
  
 <span data-ttu-id="e7d0a-152">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="e7d0a-152">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
  <EmpName>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7d0a-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7d0a-153">See Also</span></span>  
 [<span data-ttu-id="e7d0a-154">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="e7d0a-154">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
