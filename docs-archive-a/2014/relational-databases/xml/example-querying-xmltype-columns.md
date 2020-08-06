---
title: 'Exemplo: consultando colunas de tipo XML | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, querying XML example
ms.assetid: d9f3710d-7a2e-4abe-9c02-3e3c0df4d620
author: rothja
ms.author: jroth
ms.openlocfilehash: 0eedfa5a5a265f3715a76a6ca80d489bbec199bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569232"
---
# <a name="example-querying-xmltype-columns"></a><span data-ttu-id="2ec5d-102">Exemplo: consultando colunas XMLType</span><span class="sxs-lookup"><span data-stu-id="2ec5d-102">Example: Querying XMLType Columns</span></span>
  <span data-ttu-id="2ec5d-103">A consulta a seguir inclui colunas de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="2ec5d-103">The following query includes columns of `xml` type.</span></span> <span data-ttu-id="2ec5d-104">A consulta recupera a ID, nome e etapas de fabricação do modelo do produto no primeiro local da coluna `Instructions` de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="2ec5d-104">The query retrieves product model ID, name, and manufacturing steps at the first location from the `Instructions` column of the `xml` type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ec5d-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2ec5d-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
')   
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
GO  
```  
  
 <span data-ttu-id="2ec5d-106">O seguinte é o resultado.</span><span class="sxs-lookup"><span data-stu-id="2ec5d-106">The following is the result.</span></span> <span data-ttu-id="2ec5d-107">Observe que a tabela armazena instruções de fabricação para apenas alguns modelos do produto.</span><span class="sxs-lookup"><span data-stu-id="2ec5d-107">Note that the table stores manufacturing instructions for only some product models.</span></span> <span data-ttu-id="2ec5d-108">As etapas de fabricação são retornadas como subelementos do elemento <`ProductModelData`> no resultado.</span><span class="sxs-lookup"><span data-stu-id="2ec5d-108">The manufacturing steps are returned as subelements of the <`ProductModelData`> element in the result.</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
    <MI:step> ... </MI:step>  
    <MI:step> ... </MI:step>  
 </ProductModelData>  
```  
  
 <span data-ttu-id="2ec5d-109">Se a consulta especificar um nome de coluna para o XML retornado pelo XQuery, conforme especificado na instrução `SELECT` a seguir, as etapas de fabricação serão encapsuladas no elemento que tem o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="2ec5d-109">If the query specifies a column name for the XML returned by the XQuery, as specified in the following `SELECT` statement, the manufacturing steps are wrapped in the element that has the specified name.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
go  
```  
  
 <span data-ttu-id="2ec5d-110">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="2ec5d-110">This is the result:</span></span>  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
  <ManuSteps>  
    <MI:step ... </MI:step>  
    <MI:step ... </MI:step>  
  </ManuSteps>  
</ProductModelData>  
```  
  
 <span data-ttu-id="2ec5d-111">A consulta a seguir especifica a política `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="2ec5d-111">The following query specifies the `ELEMENTS` directive.</span></span> <span data-ttu-id="2ec5d-112">Portanto o resultado retornado é centrado em elemento.</span><span class="sxs-lookup"><span data-stu-id="2ec5d-112">Therefore, the result returned is element-centric.</span></span> <span data-ttu-id="2ec5d-113">A opção `XSINIL` especificada com a política `ELEMENTS` retorna os elementos <`ManuSteps`>, mesmo que a colunas correspondentes no conjunto de linhas sejam NULL.</span><span class="sxs-lookup"><span data-stu-id="2ec5d-113">The `XSINIL` option specified with the `ELEMENTS` directive returns the <`ManuSteps`> elements, even if the corresponding column in the rowset is NULL.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData'), root('MyRoot'), ELEMENTS XSINIL  
go  
```  
  
 <span data-ttu-id="2ec5d-114">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="2ec5d-114">This is the result:</span></span>  
  
```  
<MyRoot xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   ...  
  <ProductModelData>  
    <ProductModelID>6</ProductModelID>  
    <Name>HL Road Frame</Name>  
    <ManuSteps xsi:nil="true" />  
  </ProductModelData>  
  <ProductModelData>  
    <ProductModelID>7</ProductModelID>  
    <Name>HL Touring Frame</Name>  
    <ManuSteps>  
      <MI:step ... </MI:step>  
      <MI:step ...</MI:step>  
       ...  
    </ManuSteps>  
  </ProductModelData>  
</MyRoot>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ec5d-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ec5d-115">See Also</span></span>  
 [<span data-ttu-id="2ec5d-116">Usar o modo RAW com FOR XML</span><span class="sxs-lookup"><span data-stu-id="2ec5d-116">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
