---
title: Usar a opção BINARY BASE64 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, BINARY BASE64 option
ms.assetid: 86a7bb85-7f83-412a-b775-d2c379702fe9
author: rothja
ms.author: jroth
ms.openlocfilehash: 090d6a91ee56707a4eb1d545aa5a05bc25999fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684099"
---
# <a name="use-the-binary-base64-option"></a><span data-ttu-id="9c1a1-102">Usar a opção BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="9c1a1-102">Use the BINARY BASE64 Option</span></span>
  <span data-ttu-id="9c1a1-103">A opção BINARY BASE64 é especificada na consulta. Os dados binários são retornados no formato de codificação na base64.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-103">If the BINARY BASE64 option is specified in the query, the binary data is returned in base64 encoding format.</span></span> <span data-ttu-id="9c1a1-104">Por padrão, se a opção BINARY BASE64 não for especificada, o modo AUTO oferecerá suporte à codificação de URL dos dados binários.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-104">By default, if the BINARY BASE64 option is not specified, AUTO mode supports URL encoding of binary data.</span></span> <span data-ttu-id="9c1a1-105">Isto é, em vez dos dados binários, uma referência a uma URL relativa à raiz virtual do banco de dados onde a consulta é executada é retornada.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-105">That is, instead of binary data, a reference to a relative URL to the virtual root of the database where the query was executed is returned.</span></span> <span data-ttu-id="9c1a1-106">Essa referência pode ser usada para acessar os dados binários reais em operações subsequentes usando a consulta dboject SQLXML ISAPI.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-106">This reference can be used to access the actual binary data in subsequent operations by using the SQLXML ISAPI dbobject query.</span></span> <span data-ttu-id="9c1a1-107">A consulta deve fornecer informações suficientes, como colunas de chave primária para identificar a imagem.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-107">The query must provide enough information, such as primary key columns, to identify the image.</span></span>  
  
 <span data-ttu-id="9c1a1-108">Para especificar uma consulta, se um alias for usado para a coluna binária da exibição, o alias será retornado na codificação de URL dos dados binários.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-108">In specifying a query, if an alias is used for the binary column of the view, the alias is returned in the URL encoding of the binary data.</span></span> <span data-ttu-id="9c1a1-109">Em operações subsequentes, o alias não tem sentido e a codificação de URL não pode ser usada para recuperar a imagem.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-109">In subsequent operations, the alias is meaningless, and the URL encoding cannot be used to retrieve the image.</span></span> <span data-ttu-id="9c1a1-110">Portanto não use alias ao consultar uma exibição usando o modo FOR XML AUTO.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-110">Therefore, do not use aliases when querying a view using FOR XML AUTO mode.</span></span>  
  
 <span data-ttu-id="9c1a1-111">Por exemplo, em uma consulta SELECT, a conversão de qualquer coluna em BLOB (objeto binário grande) o transforma em uma entidade temporária na qual ele perde o nome da tabela associada e o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-111">For example, in a SELECT query, casting any column to a binary large object (BLOB) makes it a temporary entity in that it loses its associated table name and column name.</span></span> <span data-ttu-id="9c1a1-112">Isso faz com que as consultas em modo AUTO gerem um erro porque ele não sabe onde colocar esse valor na hierarquia XML.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-112">This causes AUTO mode queries to generate an error, because it does not know where to put this value in the XML hierarchy.</span></span> <span data-ttu-id="9c1a1-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9c1a1-113">For example:</span></span>  
  
```  
CREATE TABLE MyTable (Col1 int PRIMARY KEY, Col2 binary)  
INSERT INTO MyTable VALUES (1, 0x7);  
```  
  
 <span data-ttu-id="9c1a1-114">Esta consulta produz um erro por causa da conversão em um BLOB (objeto binário grande):</span><span class="sxs-lookup"><span data-stu-id="9c1a1-114">This query produces an error, because of the casting to a binary large object (BLOB):</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="9c1a1-115">A solução é adicionar a opção BINARY BASE64 à cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="9c1a1-115">The solution is to add the BINARY BASE64 option to the FOR XML clause.</span></span> <span data-ttu-id="9c1a1-116">Se você remover a conversão, a consulta produzirá os resultados conforme esperado:</span><span class="sxs-lookup"><span data-stu-id="9c1a1-116">If you remove the casting, the query produces the results as expected:</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO, BINARY BASE64;  
```  
  
 <span data-ttu-id="9c1a1-117">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="9c1a1-117">This is the result:</span></span>  
  
```  
<MyTable Col1="1" Col2="Bw==" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c1a1-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c1a1-118">See Also</span></span>  
 [<span data-ttu-id="9c1a1-119">Usar o modo AUTO com FOR XML</span><span class="sxs-lookup"><span data-stu-id="9c1a1-119">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
