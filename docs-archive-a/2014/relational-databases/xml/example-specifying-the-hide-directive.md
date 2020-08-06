---
title: 'Exemplo: especificando a diretiva HIDE | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- HIDE directive
ms.assetid: 87504d87-1cbd-412a-9041-47884b6efcec
author: rothja
ms.author: jroth
ms.openlocfilehash: 423ee36f679467c07a604b9754172f6e261971b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582341"
---
# <a name="example-specifying-the-hide-directive"></a><span data-ttu-id="a89ca-102">Exemplo: especificando a diretiva HIDE</span><span class="sxs-lookup"><span data-stu-id="a89ca-102">Example: Specifying the HIDE Directive</span></span>
  <span data-ttu-id="a89ca-103">Este exemplo ilustra o uso da diretiva **HIDE** .</span><span class="sxs-lookup"><span data-stu-id="a89ca-103">This example illustrates the use of the **HIDE** directive.</span></span> <span data-ttu-id="a89ca-104">Essa diretiva é útil quando você deseja que a consulta retorne um atributo para ordenar as linhas na tabela universal retornada pela consulta, mas não deseja esse atributo no documento XML resultante final.</span><span class="sxs-lookup"><span data-stu-id="a89ca-104">This directive is useful when you want the query to return an attribute for ordering the rows in the universal table that is returned by the query, but you do not want that attribute in the final resulting XML document.</span></span>  
  
 <span data-ttu-id="a89ca-105">Esta consulta constrói este XML:</span><span class="sxs-lookup"><span data-stu-id="a89ca-105">This query constructs this XML:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
           <Summary> element from XML stored in CatalogDescription column  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="a89ca-106">Essa consulta gera o XML desejado.</span><span class="sxs-lookup"><span data-stu-id="a89ca-106">This query generates the XML you want.</span></span> <span data-ttu-id="a89ca-107">A consulta identifica dois grupos de colunas que têm 1 e 2 como valores de Marca nos nomes das colunas.</span><span class="sxs-lookup"><span data-stu-id="a89ca-107">The query identifies two column groups having 1 and 2 as Tag values in the column names.</span></span>  
  
 <span data-ttu-id="a89ca-108">Essa consulta usa o [Método query() (tipo de dados xml)](/sql/t-sql/xml/query-method-xml-data-type) do tipo de dados **xml** para consultar a coluna CatalogDescription de tipo **xml** para recuperar a descrição resumida.</span><span class="sxs-lookup"><span data-stu-id="a89ca-108">This query uses the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) of the **xml** data type to query the CatalogDescription column of **xml** type in order to retrieve the summary description.</span></span> <span data-ttu-id="a89ca-109">A consulta também usa o [Método value() (tipo de dados xml)](/sql/t-sql/xml/value-method-xml-data-type) do tipo de dados **xml** para recuperar o valor de ProductModelID da coluna CatalogDescription.</span><span class="sxs-lookup"><span data-stu-id="a89ca-109">The query also uses the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) of the **xml** data type to retrieve the ProductModelID value from the CatalogDescription column.</span></span> <span data-ttu-id="a89ca-110">Esse valor não é necessário no XML resultante, mas é necessário ordenar o conjunto de linhas resultante.</span><span class="sxs-lookup"><span data-stu-id="a89ca-110">This value is not required in the resulting XML, but is required to sort the resulting rowset.</span></span> <span data-ttu-id="a89ca-111">Portanto o nome da coluna `[Summary!2!ProductModelID!HIDE]`inclui a diretiva **HIDE** .</span><span class="sxs-lookup"><span data-stu-id="a89ca-111">Therefore, the column name, `[Summary!2!ProductModelID!HIDE]`, includes the **HIDE** directive.</span></span> <span data-ttu-id="a89ca-112">Se essa coluna não estiver incluída na instrução SELECT, você precisará ordenar o conjunto de linhas por `[ProductModel!1!ProdModelID]` e `[Summary!2!SummaryDescription]` que é de tipo **xml** e usar a coluna de tipo **xml** em ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="a89ca-112">If this column is not included in the SELECT statement, you will have to sort the rowset by `[ProductModel!1!ProdModelID]` and `[Summary!2!SummaryDescription]` that is **xml** type and you cannot use the **xml** type column in ORDER BY.</span></span> <span data-ttu-id="a89ca-113">Portanto a coluna `[Summary!2!ProductModelID!HIDE]` adicional é adicionada e especificada na cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="a89ca-113">Therefore, the additional `[Summary!2!ProductModelID!HIDE]` column is added and is then specified in the ORDER BY clause.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID     as [ProductModel!1!ProdModelID],  
        Name               as [ProductModel!1!Name],  
        NULL               as [Summary!2!ProductModelID!hide],  
        NULL               as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
        CatalogDescription.value('  
         declare namespace PD="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
       (/PD:ProductDescription/@ProductModelID)[1]', 'int'),  
        CatalogDescription.query('  
         declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
         /pd:ProductDescription/pd:Summary')  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],[Summary!2!ProductModelID!hide]  
FOR XML EXPLICIT  
go  
```  
  
 <span data-ttu-id="a89ca-114">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="a89ca-114">This is the result:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <pd:Summary xmlns:pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription" xmlns="">  
        <p1:p xmlns:p1="http://www.w3.org/1999/xhtml">Our top-of-the-line competition mountain bike. Performance-enhancing options include the innovative HL Frame, super-smooth front suspension, and traction for all terrain. </p1:p>  
      </pd:Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a89ca-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a89ca-115">See Also</span></span>  
 [<span data-ttu-id="a89ca-116">Usar o modo EXPLICIT com FOR XML</span><span class="sxs-lookup"><span data-stu-id="a89ca-116">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
