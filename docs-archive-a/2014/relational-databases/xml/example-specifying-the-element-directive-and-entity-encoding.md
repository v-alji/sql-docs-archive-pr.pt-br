---
title: 'Exemplo: especificando a diretiva ELEMENT e a codificação de entidade | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
- entity encoding [XML]
ms.assetid: 50cda5c1-7293-4080-93b3-872e3b8d484e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ba4e419d31aa7c02cc2dc8f19a3350c233f042b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678672"
---
# <a name="example-specifying-the-element-directive-and-entity-encoding"></a><span data-ttu-id="3221a-102">Exemplo: Especificando a diretiva ELEMENT e codificação de entidade</span><span class="sxs-lookup"><span data-stu-id="3221a-102">Example: Specifying the ELEMENT Directive and Entity Encoding</span></span>
  <span data-ttu-id="3221a-103">Este exemplo ilustra a diferença entre as diretivas **ELEMENT** e **XML** .</span><span class="sxs-lookup"><span data-stu-id="3221a-103">This example illustrates the difference between the **ELEMENT** and **XML** directives.</span></span> <span data-ttu-id="3221a-104">A entidade dos dados é definida pela diretiva **ELEMENT** , mas não pela diretiva **XML** .</span><span class="sxs-lookup"><span data-stu-id="3221a-104">The **ELEMENT** directive entitizes the data, but the **XML** directive does not.</span></span> <span data-ttu-id="3221a-105">O elemento \<Summary> é atribuído como XML, `<Summary>This is summary description</Summary>`, na consulta.</span><span class="sxs-lookup"><span data-stu-id="3221a-105">The \<Summary> element is assigned XML, `<Summary>This is summary description</Summary>`, in the query.</span></span>  
  
 <span data-ttu-id="3221a-106">Considere esta consulta:</span><span class="sxs-lookup"><span data-stu-id="3221a-106">Consider this query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription!ELEMENT]  
FROM    Production.ProductModel  
WHERE   ProductModelID=19  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        NULL,  
       '<Summary>This is summary description</Summary>'  
FROM   Production.ProductModel  
WHERE  ProductModelID=19  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="3221a-107">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="3221a-107">This is the result.</span></span> <span data-ttu-id="3221a-108">A entidade da descrição resumida é definida no resultado.</span><span class="sxs-lookup"><span data-stu-id="3221a-108">The summary description is entitized in the result.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription><Summary>This is summary description</Summary></SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="3221a-109">Agora, se você especificar a diretiva **XML** no nome da coluna, `Summary!2!SummaryDescription!XML`, em vez da diretiva **ELEMENT** , receberá a descrição resumida sem definição de entidade.</span><span class="sxs-lookup"><span data-stu-id="3221a-109">Now, if you specify the **XML** directive in the column name, `Summary!2!SummaryDescription!XML`, instead of the **ELEMENT** directive, you will receive the summary description without entitization.</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
  <Summary>  
    <SummaryDescription>  
      <Summary>This is summary description</Summary>  
    </SummaryDescription>  
  </Summary>  
</ProductModel>  
```  
  
 <span data-ttu-id="3221a-110">Em vez de atribuir um valor de XML estático, a consulta a seguir usa o método **query()** do tipo **xml** para recuperar a descrição resumida do modelo do produto da coluna CatalogDescription de tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="3221a-110">Instead of assigning a static XML value, the following query uses the **query()** method of the **xml** type to retrieve the product model summary description from the CatalogDescription column of **xml** type.</span></span> <span data-ttu-id="3221a-111">Como se sabe que o resultado é de tipo **xml** , nenhuma definição de entidade é aplicada.</span><span class="sxs-lookup"><span data-stu-id="3221a-111">Because the result is known to be of **xml** type, no entitization is applied.</span></span>  
  
```  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        NULL            as [Summary!2!SummaryDescription]  
FROM    Production.ProductModel  
WHERE   CatalogDescription is not null  
UNION ALL  
SELECT  2 as Tag,  
        1 as Parent,  
        ProductModelID,  
        Name,  
       (SELECT CatalogDescription.query('  
            declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
          /pd:ProductDescription/pd:Summary'))  
FROM     Production.ProductModel  
WHERE    CatalogDescription is not null  
ORDER BY [ProductModel!1!ProdModelID],Tag  
FOR XML EXPLICIT  
```  
  
## <a name="see-also"></a><span data-ttu-id="3221a-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3221a-112">See Also</span></span>  
 [<span data-ttu-id="3221a-113">Usar o modo EXPLICIT com FOR XML</span><span class="sxs-lookup"><span data-stu-id="3221a-113">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
