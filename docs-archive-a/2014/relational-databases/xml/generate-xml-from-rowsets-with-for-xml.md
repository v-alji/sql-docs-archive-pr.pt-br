---
title: Gerar XML de conjuntos de linhas com FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, generating XML from rowsets
ms.assetid: d061c0f1-3de9-4ad1-bbca-ce45d064b6c8
author: rothja
ms.author: jroth
ms.openlocfilehash: dcf9feb4dab9ad1149ab433c9d9b4999c96c1cdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686175"
---
# <a name="generate-xml-from-rowsets-with-for-xml"></a><span data-ttu-id="32918-102">Gerar XML de conjuntos de linhas com FOR XML</span><span class="sxs-lookup"><span data-stu-id="32918-102">Generate XML from Rowsets with FOR XML</span></span>
  <span data-ttu-id="32918-103">Você pode gerar uma `xml` instância de tipo de dados por meio de um conjunto de linhas usando for XML com a nova diretiva de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="32918-103">You can generate an `xml` data type instance from a rowset by using FOR XML with the new **TYPE** directive.</span></span>  
  
 <span data-ttu-id="32918-104">O resultado pode ser atribuído a uma `xml` coluna, variável ou parâmetro de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="32918-104">The result can be assigned to an `xml` data type column, variable, or parameter.</span></span> <span data-ttu-id="32918-105">Além disso, o FOR XML pode ser aninhado para gerar qualquer estrutura hierárquica.</span><span class="sxs-lookup"><span data-stu-id="32918-105">Also, FOR XML can be nested to generate any hierarchical structure.</span></span> <span data-ttu-id="32918-106">Isso torna o FOR XML aninhado muito mais conveniente de escrever do que o FOR XML EXPLICIT, mas ele pode não executar tão bem para hierarquias profundas.</span><span class="sxs-lookup"><span data-stu-id="32918-106">This makes nested FOR XML much more convenient to write than FOR XML EXPLICIT, but it may not perform as well for deep hierarchies.</span></span> <span data-ttu-id="32918-107">O FOR XML também introduz um modo de PATH novo.</span><span class="sxs-lookup"><span data-stu-id="32918-107">FOR XML also introduces a new PATH mode.</span></span> <span data-ttu-id="32918-108">Esse novo modo especifica o caminho na árvore XML onde o valor de uma coluna aparece.</span><span class="sxs-lookup"><span data-stu-id="32918-108">This new mode specifies the path in the XML tree where a column's value appears.</span></span>  
  
 <span data-ttu-id="32918-109">A nova diretiva **FOR XML TYPE** pode ser usada para definir exibições XML de somente leitura sobre dados relacionais com sintaxe SQL.</span><span class="sxs-lookup"><span data-stu-id="32918-109">The new **FOR XML TYPE** directive can be used to define read-only XML views over relational data with SQL syntax.</span></span> <span data-ttu-id="32918-110">A exibição pode ser consultada com instruções SQL e XQuery inserido, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="32918-110">The view can be queried with SQL statements and embedded XQuery, as shown in the following example.</span></span> <span data-ttu-id="32918-111">Também é possível fazer referência a essas exibições SQL em procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="32918-111">You can also refer to these SQL views in stored procedures.</span></span>  
  
## <a name="example-sql-view-returning-generated-xml-data-type"></a><span data-ttu-id="32918-112">Exemplo: Modo SQL que retorna o tipo de dados xml gerado</span><span class="sxs-lookup"><span data-stu-id="32918-112">Example: SQL View Returning Generated xml Data Type</span></span>  
 <span data-ttu-id="32918-113">A definição da exibição SQL a seguir cria uma exibição XML sobre uma coluna relacional, pk, e autores de livros recuperados de uma coluna XML:</span><span class="sxs-lookup"><span data-stu-id="32918-113">The following SQL view definition creates an XML view over a relational column, pk, and book authors retrieved from an XML column:</span></span>  
  
```  
CREATE VIEW V (xmlVal) AS  
SELECT pk, xCol.query('/book/author')  
FROM   T  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="32918-114">A exibição V contém uma única linha com um único columnxmlVal do tipo XML `.` que pode ser consultado como uma `xml` instância de tipo de dados regular.</span><span class="sxs-lookup"><span data-stu-id="32918-114">The V view contains a single row with a single columnxmlVal of XML type`.` It can be queried like a regular `xml` data type instance.</span></span> <span data-ttu-id="32918-115">Por exemplo, a consulta a seguir retorna o autor cujo primeiro nome é "David":</span><span class="sxs-lookup"><span data-stu-id="32918-115">For example, the following query returns the author whose first name is "David":</span></span>  
  
```  
SELECT xmlVal.query('//author[first-name = "David"]')  
FROM   V  
```  
  
 <span data-ttu-id="32918-116">As definições da exibição SQL são um pouco semelhantes a exibições XML que são criadas usando esquemas anotados.</span><span class="sxs-lookup"><span data-stu-id="32918-116">SQL view definitions are somewhat similar to XML views that are created by using annotated schemas.</span></span> <span data-ttu-id="32918-117">No entanto há diferenças importantes.</span><span class="sxs-lookup"><span data-stu-id="32918-117">However, there are important differences.</span></span> <span data-ttu-id="32918-118">A definição da exibição SQL é somente leitura e deve ser manipulada com XQuery inserido.</span><span class="sxs-lookup"><span data-stu-id="32918-118">The SQL view definition is read-only and must be manipulated with embedded XQuery.</span></span> <span data-ttu-id="32918-119">As exibições XML são criadas usando esquema anotado.</span><span class="sxs-lookup"><span data-stu-id="32918-119">The XML views are created by using annotated schema.</span></span> <span data-ttu-id="32918-120">Além disso, a exibição SQL materializa o resultado XML antes de aplicar a expressão XQuery, enquanto as consultas XPath nas exibições XML avaliam consultas SQL nas tabelas subjacentes.</span><span class="sxs-lookup"><span data-stu-id="32918-120">Additionally, the SQL view materializes the XML result before applying the XQuery expression, while the XPath queries on XML views evaluate SQL queries on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32918-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32918-121">See Also</span></span>  
 [<span data-ttu-id="32918-122">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="32918-122">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
