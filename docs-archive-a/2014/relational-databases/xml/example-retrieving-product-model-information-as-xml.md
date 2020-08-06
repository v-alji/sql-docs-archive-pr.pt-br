---
title: 'Exemplo: Recuperando informações de modelo do produto como XML | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, retrieving XML information example
ms.assetid: 3828b4ca-3ab2-444f-9c58-8be6e7f064a6
author: rothja
ms.author: jroth
ms.openlocfilehash: d580f53c4b5185a8b1b1467c75a08fc6929bdcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574578"
---
# <a name="example-retrieving-product-model-information-as-xml"></a><span data-ttu-id="4bb91-102">Exemplo: Recuperando informações de modelo de produto como XML</span><span class="sxs-lookup"><span data-stu-id="4bb91-102">Example: Retrieving Product Model Information as XML</span></span>
  <span data-ttu-id="4bb91-103">A consulta a seguir retorna informações sobre modelos de produtos.</span><span class="sxs-lookup"><span data-stu-id="4bb91-103">The following query returns product model information.</span></span> <span data-ttu-id="4bb91-104">`RAW` O modo é especificado na cláusula `FOR XML` .</span><span class="sxs-lookup"><span data-stu-id="4bb91-104">`RAW` mode is specified in the `FOR XML` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bb91-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4bb91-105">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW;  
GO  
```  
  
 <span data-ttu-id="4bb91-106">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="4bb91-106">This is the partial result:</span></span>  
  
 `<row ProductModelID="122" Name="All-Purpose Bike Stand" />`  
  
 `<row ProductModelID="119" Name="Bike Wash" />`  
  
 <span data-ttu-id="4bb91-107">É possível recuperar XML centrado em elemento especificando a política `ELEMENTS` .</span><span class="sxs-lookup"><span data-stu-id="4bb91-107">You can retrieve element-centric XML by specifying the `ELEMENTS` directive.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, ELEMENTS;  
GO  
```  
  
 <span data-ttu-id="4bb91-108">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="4bb91-108">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>122</ProductModelID>  
  <Name>All-Purpose Bike Stand</Name>  
</row>  
<row>  
  <ProductModelID>119</ProductModelID>  
  <Name>Bike Wash</Name>  
</row>  
```  
  
 <span data-ttu-id="4bb91-109">Opcionalmente, é possível especificar a política `TYPE` para recuperar os resultados como tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="4bb91-109">You can optionally specify the `TYPE` directive to retrieve the results as `xml` type.</span></span> <span data-ttu-id="4bb91-110">A política `TYPE` não altera o conteúdo dos resultados.</span><span class="sxs-lookup"><span data-stu-id="4bb91-110">The `TYPE` directive does not change the content of the results.</span></span> <span data-ttu-id="4bb91-111">Apenas o tipo de dados dos resultados é afetado.</span><span class="sxs-lookup"><span data-stu-id="4bb91-111">Only the data type of the results is affected.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, TYPE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bb91-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4bb91-112">See Also</span></span>  
 [<span data-ttu-id="4bb91-113">Usar o modo RAW com FOR XML</span><span class="sxs-lookup"><span data-stu-id="4bb91-113">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
