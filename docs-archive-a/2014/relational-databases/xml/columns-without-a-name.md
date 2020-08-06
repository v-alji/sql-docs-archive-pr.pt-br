---
title: Colunas sem nome | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns without
ms.assetid: 440de44e-3a56-4531-b4e4-1533ca933cac
author: rothja
ms.author: jroth
ms.openlocfilehash: 43d1cbce816e4666e6dab52fdffe5850e65740e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679745"
---
# <a name="columns-without-a-name"></a><span data-ttu-id="f3386-102">Colunas sem um nome</span><span class="sxs-lookup"><span data-stu-id="f3386-102">Columns without a Name</span></span>
  <span data-ttu-id="f3386-103">Qualquer coluna sem um nome será embutida.</span><span class="sxs-lookup"><span data-stu-id="f3386-103">Any column without a name will be inlined.</span></span> <span data-ttu-id="f3386-104">Por exemplo, colunas computadas ou consultas escalares aninhadas que não especificam o alias de coluna gerarão colunas sem nome.</span><span class="sxs-lookup"><span data-stu-id="f3386-104">For example, computed columns or nested scalar queries that do not specify column alias will generate columns without any name.</span></span> <span data-ttu-id="f3386-105">Se a coluna for de tipo `xml`, o conteúdo dessa instância de tipo de dados será inserido.</span><span class="sxs-lookup"><span data-stu-id="f3386-105">If the column is of `xml` type, the content of that data type instance is inserted.</span></span> <span data-ttu-id="f3386-106">Caso contrário, o conteúdo da coluna será inserido como um nó de texto.</span><span class="sxs-lookup"><span data-stu-id="f3386-106">Otherwise, the column content is inserted as a text node.</span></span>  
  
```  
SELECT 2+2  
FOR XML PATH  
```  
  
 <span data-ttu-id="f3386-107">Produza este XML.</span><span class="sxs-lookup"><span data-stu-id="f3386-107">Produce this XML.</span></span> <span data-ttu-id="f3386-108">Por padrão, para cada linha no conjunto de linhas, um elemento <`row`> é gerado no XML resultante.</span><span class="sxs-lookup"><span data-stu-id="f3386-108">By default, for each row in the rowset, a <`row`> element is generated in the resulting XML.</span></span> <span data-ttu-id="f3386-109">Isso é o mesmo que o modo RAW.</span><span class="sxs-lookup"><span data-stu-id="f3386-109">This is the same as RAW mode.</span></span>  
  
 `<row>4</row>`  
  
 <span data-ttu-id="f3386-110">A consulta a seguir retorna um conjunto de linhas de três colunas.</span><span class="sxs-lookup"><span data-stu-id="f3386-110">The following query returns a three-column rowset.</span></span> <span data-ttu-id="f3386-111">A terceira coluna sem um nome tem dados XML.</span><span class="sxs-lookup"><span data-stu-id="f3386-111">The third column without a name has XML data.</span></span> <span data-ttu-id="f3386-112">O modo PATH insere uma instância de tipo xml.</span><span class="sxs-lookup"><span data-stu-id="f3386-112">The PATH mode inserts an instance of the xml type.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ;  
GO  
```  
  
 <span data-ttu-id="f3386-113">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="f3386-113">This is the partial result:</span></span>  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location ...LocationID="10" ...></MI:Location>`  
  
 `<MI:Location ...LocationID="20" ...></MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="f3386-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f3386-114">See Also</span></span>  
 [<span data-ttu-id="f3386-115">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="f3386-115">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
