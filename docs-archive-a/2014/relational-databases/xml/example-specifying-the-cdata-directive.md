---
title: 'Exemplo: Especificando a diretiva CDATA | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- CDATA directive
ms.assetid: 949071e6-787f-480d-bb86-3ac16a027af1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9b4f949ae1e9f309a13906efe44b329db2e47ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678675"
---
# <a name="example-specifying-the-cdata-directive"></a><span data-ttu-id="a044b-102">Exemplo: Especificando a diretiva CDATA</span><span class="sxs-lookup"><span data-stu-id="a044b-102">Example: Specifying the CDATA Directive</span></span>
  <span data-ttu-id="a044b-103">Se a diretiva for definida como **CDATA**, os dados contidos não serão codificados como entidade, mas colocados na seção CDATA.</span><span class="sxs-lookup"><span data-stu-id="a044b-103">If the directive is set to **CDATA**, the contained data is not entity encoded, but is put in the CDATA section.</span></span> <span data-ttu-id="a044b-104">Os atributos **CDATA** não devem ter nomes.</span><span class="sxs-lookup"><span data-stu-id="a044b-104">The **CDATA** attributes must be nameless.</span></span>  
  
 <span data-ttu-id="a044b-105">A seguinte consulta encapsula a descrição resumida do modelo do produto em uma seção CDATA.</span><span class="sxs-lookup"><span data-stu-id="a044b-105">The following query wraps the product model summary description in a CDATA section.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        ProductModelID  as [ProductModel!1!ProdModelID],  
        Name            as [ProductModel!1!Name],  
        '<Summary>This is summary description</Summary>'     
            as [ProductModel!1!!CDATA] -- no attribute name so ELEMENT assumed  
FROM    Production.ProductModel  
WHERE   ProductModelID=19  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="a044b-106">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="a044b-106">This is the result:</span></span>  
  
```  
<ProductModel ProdModelID="19" Name="Mountain-100">  
   <![CDATA[<Summary>This is summary description</Summary>]]>  
</ProductModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a044b-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a044b-107">See Also</span></span>  
 [<span data-ttu-id="a044b-108">Usar o modo EXPLICIT com FOR XML</span><span class="sxs-lookup"><span data-stu-id="a044b-108">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
