---
title: Colunas com um nome especificado como um caractere curinga | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: d9551df1-5bb4-4c0b-880a-5bb049834884
author: rothja
ms.author: jroth
ms.openlocfilehash: 4b363baf8792628c2e17b1a695c19a6a338f4fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573840"
---
# <a name="columns-with-a-name-specified-as-a-wildcard-character"></a><span data-ttu-id="3360b-102">Colunas com um nome especificado como um caractere curinga</span><span class="sxs-lookup"><span data-stu-id="3360b-102">Columns with a Name Specified as a Wildcard Character</span></span>
  <span data-ttu-id="3360b-103">Se o nome da coluna especificado for um caractere curinga (\*), o conteúdo dessa coluna será inserido como se não houvesse nenhum nome de coluna especificado.</span><span class="sxs-lookup"><span data-stu-id="3360b-103">If the column name specified is a wildcard character (\*), the content of that column is inserted as if there is no column name specified.</span></span> <span data-ttu-id="3360b-104">Se essa coluna não for do tipo `xml`, o conteúdo da coluna será inserido como um nó de texto, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="3360b-104">If this column is a non-`xml` type column, the column content is inserted as a text node, as shown in the following example:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
       FirstName "*",   
       MiddleName "*",   
       LastName "*"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
    ON E.BusinessEntityID = P.BusinessEntityID  
WHERE E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="3360b-105">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="3360b-105">This is the result:</span></span>  
  
 `<row EmpID="1">KenJS??nchez</row>`  
  
 <span data-ttu-id="3360b-106">Se a coluna for do tipo `xml`, a árvore XML correspondente será inserida.</span><span class="sxs-lookup"><span data-stu-id="3360b-106">If the column is of `xml` type, the corresponding XML tree is inserted.</span></span> <span data-ttu-id="3360b-107">Por exemplo, a coluna a seguir especifica "\*" para o nome da coluna que contém o XML retornado pelo XQuery em relação à coluna Instructions.</span><span class="sxs-lookup"><span data-stu-id="3360b-107">For example, the following query specifies "\*" for the column name that contains the XML returned by the XQuery against the Instructions column.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
                /MI:root/MI:Location   
              ') as "*"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH;   
GO  
```  
  
 <span data-ttu-id="3360b-108">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="3360b-108">This is the result.</span></span> <span data-ttu-id="3360b-109">O XML retornado por XQuery é inserido sem um elemento de encapsulamento.</span><span class="sxs-lookup"><span data-stu-id="3360b-109">The XML returned by XQuery is inserted without a wrapping element.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location LocationID="10">...</MI:Location>`  
  
 `<MI:Location LocationID="20">...</MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="3360b-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3360b-110">See Also</span></span>  
 [<span data-ttu-id="3360b-111">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="3360b-111">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
