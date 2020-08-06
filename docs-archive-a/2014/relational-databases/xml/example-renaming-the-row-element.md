---
title: 'Exemplo: Renomeando o elemento &lt;row&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, renaming <row> example
ms.assetid: b042292a-0b6e-40a3-b254-71c06e626706
author: rothja
ms.author: jroth
ms.openlocfilehash: 39375fa125f451f21d936b3a6897b93928fa2f02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569231"
---
# <a name="example-renaming-the-ltrowgt-element"></a><span data-ttu-id="39a96-102">Exemplo: Renomeando o elemento &lt;row&gt;</span><span class="sxs-lookup"><span data-stu-id="39a96-102">Example: Renaming the &lt;row&gt; Element</span></span>
  <span data-ttu-id="39a96-103">Para cada linha no conjunto de resultados, o modo RAW gera um elemento `<row>`.</span><span class="sxs-lookup"><span data-stu-id="39a96-103">For each row in the result set, the RAW mode generates an element `<row>`.</span></span> <span data-ttu-id="39a96-104">Opcionalmente, é possível especificar outro nome para esse elemento especificando um argumento opcional para o modo RAW, conforme mostrado nesta consulta.</span><span class="sxs-lookup"><span data-stu-id="39a96-104">You can optionally specify another name for this element by specifying an optional argument to the RAW mode, as shown in this query.</span></span> <span data-ttu-id="39a96-105">A consulta retorna um elemento <`ProductModel`> para cada linha do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="39a96-105">The query returns a <`ProductModel`> element for each row in the rowset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39a96-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="39a96-106">Example</span></span>  
  
```  
SELECT ProductModelID, Name   
FROM Production.ProductModel  
WHERE ProductModelID=122  
FOR XML RAW ('ProductModel'), ELEMENTS  
GO  
```  
  
 <span data-ttu-id="39a96-107">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="39a96-107">This is the result.</span></span> <span data-ttu-id="39a96-108">Como a diretiva `ELEMENTS` é adicionada à consulta, o resultado é centrado em elemento.</span><span class="sxs-lookup"><span data-stu-id="39a96-108">Because the `ELEMENTS` directive is added in the query, the result is element-centric.</span></span>  
  
```  
<ProductModel>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</ProductModel>   
```  
  
## <a name="see-also"></a><span data-ttu-id="39a96-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39a96-109">See Also</span></span>  
 [<span data-ttu-id="39a96-110">Usar o modo RAW com FOR XML</span><span class="sxs-lookup"><span data-stu-id="39a96-110">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
