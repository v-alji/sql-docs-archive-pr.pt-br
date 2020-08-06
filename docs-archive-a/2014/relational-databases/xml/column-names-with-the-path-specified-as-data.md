---
title: Nomes de coluna com o caminho especificado como data() | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: 0b738e44-6108-4417-a9a4-abeb7680d899
author: rothja
ms.author: jroth
ms.openlocfilehash: 61aa7f85c7ee2358ddcf99f81c87c1295fac8fb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569240"
---
# <a name="column-names-with-the-path-specified-as-data"></a><span data-ttu-id="a5407-102">Nomes de colunas com o caminho especificado como data()</span><span class="sxs-lookup"><span data-stu-id="a5407-102">Column Names with the Path Specified as data()</span></span>
  <span data-ttu-id="a5407-103">Se o caminho especificado como nome da coluna for "data()", o valor será tratado com um valor atômico no XML gerado.</span><span class="sxs-lookup"><span data-stu-id="a5407-103">If the path specified as column name is "data()", the value is treated as an atomic value in the generated XML.</span></span> <span data-ttu-id="a5407-104">Um caractere de espaço será adicionado ao XML se o próximo item na serialização também for um valor atômico.</span><span class="sxs-lookup"><span data-stu-id="a5407-104">A space character is added to the XML if the next item in the serialization is also an atomic value.</span></span> <span data-ttu-id="a5407-105">Isso é útil quando você está criando elemento de tipo lista e valores de atributos.</span><span class="sxs-lookup"><span data-stu-id="a5407-105">This is useful when you are creating list typed element and attribute values.</span></span> <span data-ttu-id="a5407-106">A consulta a seguir recupera a ID e o nome do modelo do produto e a lista de produtos naquele modelo do produto.</span><span class="sxs-lookup"><span data-stu-id="a5407-106">The following query retrieves the product model ID, name, and list of products in that product model.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID       AS "@ProductModelID",  
       Name                 AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
      FOR XML PATH (''))    AS "@ProductIDs"  
FROM  Production.ProductModel  
WHERE ProductModelID= 7   
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="a5407-107">O SELECT aninhado recupera uma lista de IDs de produtos.</span><span class="sxs-lookup"><span data-stu-id="a5407-107">The nested SELECT retrieves a list of product IDs.</span></span> <span data-ttu-id="a5407-108">Ele especifica "data()" como o nome da coluna para IDs de produtos.</span><span class="sxs-lookup"><span data-stu-id="a5407-108">It specifies "data()" as the column name for product IDs.</span></span> <span data-ttu-id="a5407-109">Como o modo PATH especifica uma cadeia de caracteres vazia para o nome do elemento de linha, não há nenhum elemento de linha gerado.</span><span class="sxs-lookup"><span data-stu-id="a5407-109">Because PATH mode specifies an empty string for the row element name, there is no row element generated.</span></span> <span data-ttu-id="a5407-110">Em vez disso, os valores são retornados conforme são atribuídos a um atributo ProductIDs do elemento de linha <`ProductModelData`> do SELECT pai.</span><span class="sxs-lookup"><span data-stu-id="a5407-110">Instead, the values are returned as assigned to a ProductIDs attribute of the <`ProductModelData`> row element of the parent SELECT.</span></span> <span data-ttu-id="a5407-111">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="a5407-111">This is the result:</span></span>  
  
 `<ProductModelData ProductModelID="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 888 889 890 891 892 893" />`  
  
## <a name="see-also"></a><span data-ttu-id="a5407-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5407-112">See Also</span></span>  
 [<span data-ttu-id="a5407-113">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="a5407-113">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
