---
title: Consulta XML FOR comparada com consulta XML FOR aninhada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], comparing query types
ms.assetid: 19225b4a-ee3f-47cf-8bcc-52699eeda32c
author: rothja
ms.author: jroth
ms.openlocfilehash: ca10060702d0c7e50f2be79310c55e177dca358d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686196"
---
# <a name="for-xml-query-compared-to-nested-for-xml-query"></a><span data-ttu-id="1a651-102">Consulta FOR XML comparada com consulta FOR XML aninhada</span><span class="sxs-lookup"><span data-stu-id="1a651-102">FOR XML Query Compared to Nested FOR XML Query</span></span>
  <span data-ttu-id="1a651-103">Este tópico compara uma consulta FOR XML de nível único com uma consulta FOR XML aninhada.</span><span class="sxs-lookup"><span data-stu-id="1a651-103">This topic compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="1a651-104">Um dos benefícios do uso de consultas FOR XML aninhadas é que é possível especificar uma combinação de XML centrado em atributo e em elemento para resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="1a651-104">One of the benefits of using nested FOR XML queries is that you can specify a combination of attribute-centric and element-centric XML for query results.</span></span> <span data-ttu-id="1a651-105">O exemplo demonstra isso.</span><span class="sxs-lookup"><span data-stu-id="1a651-105">The example demonstrates this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a651-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1a651-106">Example</span></span>  
 <span data-ttu-id="1a651-107">A consulta `SELECT` a seguir recupera informações de categoria e subcategoria de produtos no banco de dados do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a651-107">The following `SELECT` query retrieves product category and subcategory information in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="1a651-108">Não há FOR XML aninhado na consulta.</span><span class="sxs-lookup"><span data-stu-id="1a651-108">There is no nested FOR XML in the query.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   ProductCategory.ProductCategoryID,   
         ProductCategory.Name as CategoryName,  
         ProductSubCategory.ProductSubCategoryID,   
         ProductSubCategory.Name  
FROM     Production.ProductCategory, Production.ProductSubCategory  
WHERE    ProductCategory.ProductCategoryID = ProductSubCategory.ProductCategoryID  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
GO  
```  
  
 <span data-ttu-id="1a651-109">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="1a651-109">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory ProductSubCategoryID="1" Name="Mountain Bike"/>  
  <ProductSubCategory ProductSubCategoryID="2" Name="Road Bike"/>  
  <ProductSubCategory ProductSubCategoryID="3" Name="Touring Bike"/>  
</ProductCategory>  
...  
```  
  
 <span data-ttu-id="1a651-110">Se você especificar a política `ELEMENTS` na consulta, receberá um resultado centrado em elemento, conforme mostrado no seguinte fragmento de resultado:</span><span class="sxs-lookup"><span data-stu-id="1a651-110">If you specify the `ELEMENTS` directive in the query, you receive an element-centric result, as shown in the following result fragment:</span></span>  
  
```  
<ProductCategory>  
  <ProductCategoryID>1</ProductCategoryID>  
  <CategoryName>Bike</CategoryName>  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <Name>Mountain Bike</Name>  
  </ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  </ProductSubCategory>  
</ProductCategory>  
```  
  
 <span data-ttu-id="1a651-111">Em seguida, suponha que você queira gerar uma hierarquia XML que seja uma combinação de XML centrado em atributo e em elemento, conforme mostrado neste fragmento:</span><span class="sxs-lookup"><span data-stu-id="1a651-111">Next, assume that you want to generate an XML hierarchy that is a combination of attribute-centric and element-centric XML, as shown in the following fragment:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="1a651-112">No fragmento anterior, as informações da categoria de produtos como ID e nome da categoria são atributos.</span><span class="sxs-lookup"><span data-stu-id="1a651-112">In the previous fragment, product category information such as category ID and category name are attributes.</span></span> <span data-ttu-id="1a651-113">No entanto as informações de subcategoria são centradas em elemento.</span><span class="sxs-lookup"><span data-stu-id="1a651-113">However, the subcategory information is element-centric.</span></span> <span data-ttu-id="1a651-114">Para construir o elemento <`ProductCategory`>, você pode escrever uma consulta `FOR XML` conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="1a651-114">To construct the <`ProductCategory`> element, you can write a `FOR XML` query as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName  
FROM Production.ProductCategory ProdCat  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="1a651-115">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="1a651-115">This is the result:</span></span>  
  
```  
< ProdCat ProductCategoryID="1" CategoryName="Bikes" />  
< ProdCat ProductCategoryID="2" CategoryName="Components" />  
< ProdCat ProductCategoryID="3" CategoryName="Clothing" />  
< ProdCat ProductCategoryID="4" CategoryName="Accessories" />  
```  
  
 <span data-ttu-id="1a651-116">Para construir os elementos <`ProductSubCategory`> aninhados no XML desejado, adicione uma consulta `FOR XML` aninhada, conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="1a651-116">To construct the nested <`ProductSubCategory`> elements in the XML you want, you then add a nested `FOR XML` query, as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName  
        FROM   Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="1a651-117">Observe o seguinte na consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="1a651-117">Note the following in the previous query:</span></span>  
  
-   <span data-ttu-id="1a651-118">A consulta `FOR XML` interna recupera informações de subcategoria de produtos.</span><span class="sxs-lookup"><span data-stu-id="1a651-118">The inner `FOR XML` query retrieves product subcategory information.</span></span> <span data-ttu-id="1a651-119">A diretiva `ELEMENTS` é adicionada ao `FOR XML` interno para gerar XML centrado em elemento que é adicionado ao XML gerado pela consulta externa.</span><span class="sxs-lookup"><span data-stu-id="1a651-119">The `ELEMENTS` directive is added in the inner `FOR XML` to generate element-centric XML that is added to the XML generated by the outer query.</span></span> <span data-ttu-id="1a651-120">Por padrão, a consulta externa gera XML centrado em atributo.</span><span class="sxs-lookup"><span data-stu-id="1a651-120">By default, the outer query generates attribute-centric XML.</span></span>  
  
-   <span data-ttu-id="1a651-121">Na consulta interna, a diretiva `TYPE` é especificada de forma que o resultado seja do tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="1a651-121">In the inner query, the `TYPE` directive is specified so the result is of **xml** type.</span></span> <span data-ttu-id="1a651-122">Se `TYPE` não for especificado, o resultado será retornado como tipo `nvarchar(max)` e os dados XML serão retornados como entidades.</span><span class="sxs-lookup"><span data-stu-id="1a651-122">If `TYPE` is not specified, the result is returned as `nvarchar(max)` type and the XML data is returned as entities.</span></span>  
  
-   <span data-ttu-id="1a651-123">A consulta externa também especifica a diretiva `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="1a651-123">The outer query also specifies the `TYPE` directive.</span></span> <span data-ttu-id="1a651-124">Portanto o resultado dessa consulta é retornado ao cliente como tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="1a651-124">Therefore, the result of this query is returned to the client as **xml** type.</span></span>  
  
 <span data-ttu-id="1a651-125">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="1a651-125">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="1a651-126">A consulta a seguir é apenas uma extensão da consulta anterior.</span><span class="sxs-lookup"><span data-stu-id="1a651-126">The following query is just an extension of the previous query.</span></span> <span data-ttu-id="1a651-127">Ela mostra a hierarquia completa de produtos no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a651-127">It shows the full product hierarchy in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="1a651-128">Isso inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1a651-128">This includes the following:</span></span>  
  
-   <span data-ttu-id="1a651-129">Categorias de produtos</span><span class="sxs-lookup"><span data-stu-id="1a651-129">Product categories</span></span>  
  
-   <span data-ttu-id="1a651-130">Subcategorias de produtos em cada categoria</span><span class="sxs-lookup"><span data-stu-id="1a651-130">Product subcategories in each category</span></span>  
  
-   <span data-ttu-id="1a651-131">Modelos de produtos em cada subcategoria</span><span class="sxs-lookup"><span data-stu-id="1a651-131">Product models in each subcategory</span></span>  
  
-   <span data-ttu-id="1a651-132">Produtos em cada modelo</span><span class="sxs-lookup"><span data-stu-id="1a651-132">Products in each model</span></span>  
  
 <span data-ttu-id="1a651-133">A consulta a seguir pode ser útil para entender o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="1a651-133">You might find the following query useful in understanding the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName,  
               (SELECT ProductModel.ProductModelID,   
                       ProductModel.Name as ModelName,  
                       (SELECT ProductID, Name as ProductName, Color  
                        FROM   Production.Product  
                        WHERE  Product.ProductModelID =   
                               ProductModel.ProductModelID  
                        FOR XML AUTO, TYPE)  
                FROM   (SELECT distinct ProductModel.ProductModelID,   
                               ProductModel.Name  
                        FROM   Production.ProductModel,   
                               Production.Product  
                        WHERE  ProductModel.ProductModelID =   
                               Product.ProductModelID  
                        AND    Product.ProductSubCategoryID =   
                               ProductSubCategory.ProductSubCategoryID)   
                                  ProductModel  
                FOR XML AUTO, type  
               )  
        FROM Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="1a651-134">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="1a651-134">This is the partial result:</span></span>  
  
```  
<Production.ProductCategory ProductCategoryID="1" CategoryName="Bikes">  
  <Production.ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bikes</SubCategoryName>  
    <ProductModel ProductModelID="19" ModelName="Mountain-100">  
      <Production.Product ProductID="771"   
                ProductName="Mountain-100 Silver, 38" Color="Silver" />  
      <Production.Product ProductID="772"   
                ProductName="Mountain-100 Silver, 42" Color="Silver" />  
      <Production.Product ProductID="773"   
                ProductName="Mountain-100 Silver, 44" Color="Silver" />  
        ...  
    </ProductModel>  
     ...  
```  
  
 <span data-ttu-id="1a651-135">Se você remover a diretiva `ELEMENTS` da consulta `FOR XML` aninhada que gera subcategorias de produtos, todo o resultado será centrado em atributo.</span><span class="sxs-lookup"><span data-stu-id="1a651-135">If you remove the `ELEMENTS` directive from the nested `FOR XML` query that generates product subcategories, the whole result is attribute-centric.</span></span> <span data-ttu-id="1a651-136">Em seguida, você pode escrever esta consulta sem aninhamento.</span><span class="sxs-lookup"><span data-stu-id="1a651-136">You can then write this query without nesting.</span></span> <span data-ttu-id="1a651-137">A adição de resultados de `ELEMENTS` em um XML que é parcialmente centrado em atributo e em elemento.</span><span class="sxs-lookup"><span data-stu-id="1a651-137">The addition of `ELEMENTS` results in an XML that is partly attribute-centric and partly element-centric.</span></span> <span data-ttu-id="1a651-138">Esse resultado não pode ser gerado por uma consulta FOR XML de nível único.</span><span class="sxs-lookup"><span data-stu-id="1a651-138">This result cannot be generated by a single-level, FOR XML query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a651-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a651-139">See Also</span></span>  
 [<span data-ttu-id="1a651-140">Usar consultas FOR XML aninhadas</span><span class="sxs-lookup"><span data-stu-id="1a651-140">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
