---
title: Colunas com o nome de um teste de nó XPath | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
- XPath node test
ms.assetid: b48adccd-3b6b-486a-b326-20f57170186f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6555815d97308bed6e70d9fedb9858fc3abe7685
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679746"
---
# <a name="columns-with-the-name-of-an-xpath-node-test"></a><span data-ttu-id="7a1d5-102">Colunas com o nome de um teste de nó XPath</span><span class="sxs-lookup"><span data-stu-id="7a1d5-102">Columns with the Name of an XPath Node Test</span></span>
  <span data-ttu-id="7a1d5-103">Se o nome da coluna for um dos testes de nó XPath, o conteúdo será mapeado conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7a1d5-103">If the column name is one of the XPath node tests, the content is mapped as shown in the following table.</span></span> <span data-ttu-id="7a1d5-104">Quando o nome de coluna é um teste de nó XPath, o conteúdo é mapeado para o nó correspondente.</span><span class="sxs-lookup"><span data-stu-id="7a1d5-104">When the column name is an XPath node test, the content is mapped to the corresponding node.</span></span> <span data-ttu-id="7a1d5-105">Se o tipo SQL da coluna for `xml`, será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="7a1d5-105">If the SQL type of the column is `xml`, an error is returned.</span></span>  
  
|<span data-ttu-id="7a1d5-106">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="7a1d5-106">Column Name</span></span>|<span data-ttu-id="7a1d5-107">Comportamento</span><span class="sxs-lookup"><span data-stu-id="7a1d5-107">Behavior</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="7a1d5-108">text()</span><span class="sxs-lookup"><span data-stu-id="7a1d5-108">text()</span></span>|<span data-ttu-id="7a1d5-109">Para uma coluna com o nome de text(), o valor da cadeia de caracteres daquela coluna é adicionado a um nó de texto.</span><span class="sxs-lookup"><span data-stu-id="7a1d5-109">For a column with the name of text(), the string value in that column is added as a text node.</span></span>|  
|<span data-ttu-id="7a1d5-110">comment()</span><span class="sxs-lookup"><span data-stu-id="7a1d5-110">comment()</span></span>|<span data-ttu-id="7a1d5-111">Para uma coluna com o nome de comment(), o valor da cadeia de caracteres daquela coluna é adicionado a um nó de texto.</span><span class="sxs-lookup"><span data-stu-id="7a1d5-111">For a column with the name of comment(), the string value in that column is added as an XML comment.</span></span>|  
|<span data-ttu-id="7a1d5-112">node()</span><span class="sxs-lookup"><span data-stu-id="7a1d5-112">node()</span></span>|<span data-ttu-id="7a1d5-113">Para uma coluna com o nome de node(), o resultado é o mesmo que quando o nome da coluna é um caractere curinga (\*).</span><span class="sxs-lookup"><span data-stu-id="7a1d5-113">For a column with the name of node(), the result is the same as it is when the column name is a wildcard character (\*).</span></span>|  
|<span data-ttu-id="7a1d5-114">instrução-de-processamento(nome)</span><span class="sxs-lookup"><span data-stu-id="7a1d5-114">processing-instruction(name)</span></span>|<span data-ttu-id="7a1d5-115">Para uma coluna com o nome de uma instrução de processamento, o valor da cadeia de caracteres daquela coluna é adicionado como o valor de PI do nome de destino da instrução de processamento.</span><span class="sxs-lookup"><span data-stu-id="7a1d5-115">For a column with the name of a processing instruction, the string value in that column is added as the PI value for the processing instruction target name.</span></span>|  
  
 <span data-ttu-id="7a1d5-116">A consulta a seguir mostra o uso dos testes de nó como nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="7a1d5-116">The following query shows the use of the node tests as column names.</span></span> <span data-ttu-id="7a1d5-117">Ela adiciona nós de texto e comentários no XML resultante.</span><span class="sxs-lookup"><span data-stu-id="7a1d5-117">It adds text nodes and comments in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT E.BusinessEntityID "@EmpID",   
        'Example of using node tests such as text(), comment(), processing-instruction()'                as "comment()",  
        'Some PI'                   as "processing-instruction(PI)",  
        'Employee name and address data' as "text()",  
        'middle name is optional'        as "EmpName/text()",  
        FirstName                        as "EmpName/First",   
        MiddleName                       as "EmpName/Middle",   
        LastName                         as "EmpName/Last",  
        AddressLine1                     as "Address/AddrLine1",  
        AddressLine2                     as "Address/AddrLIne2",  
        City                             as "Address/City"  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P   
    ON P.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.BusinessEntityAddress AS BAE  
    ON BAE.BusinessEntityID = E.BusinessEntityID  
INNER JOIN Person.Address AS A  
    ON BAE.AddressID = A.AddressID  
WHERE  E.BusinessEntityID=1  
FOR XML PATH;  
```  
  
 <span data-ttu-id="7a1d5-118">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="7a1d5-118">This is the result:</span></span>  
  
 `<row EmpID="1">`  
  
 `<!--Example of using node tests such as text(), comment(), processing-instruction() -->`  
  
 `<?PI Some PI?>`  
  
 `Employee name and address data`  
  
 `<EmpName>middle name is optional`  
  
 `<First>Ken</First>`  
  
 `<Last>S??nchez</Last>`  
  
 `</EmpName>`  
  
 `<Address>`  
  
 `<AddrLine1>4350 Minute Dr.</AddrLine1>`  
  
 `<City>Minneapolis</City>`  
  
 `</Address>`  
  
 `</row>`  
  
## <a name="see-also"></a><span data-ttu-id="7a1d5-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7a1d5-119">See Also</span></span>  
 [<span data-ttu-id="7a1d5-120">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="7a1d5-120">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
