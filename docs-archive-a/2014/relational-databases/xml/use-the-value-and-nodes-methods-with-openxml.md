---
title: Usar os métodos value() e nodes() com OPENXML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- OpenXML method [XML in SQL Server]
- value method [XML in SQL Server]
- nodes method [XML in SQL Server]
ms.assetid: c73dbe55-d685-42eb-b0ee-9f3c5b9d97f3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5dccf5a7ef626d1f1a42d011d22ba77807b34eba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684097"
---
# <a name="use-the-value-and-nodes-methods-with-openxml"></a><span data-ttu-id="82d72-102">Usar os métodos value() e nodes() com OPENXML</span><span class="sxs-lookup"><span data-stu-id="82d72-102">Use the value() and nodes() Methods with OPENXML</span></span>
  <span data-ttu-id="82d72-103">Você pode usar vários métodos **Value ()** no `xml` tipo de dados em uma cláusula **Select** para gerar um conjunto de linhas de valores extraídos.</span><span class="sxs-lookup"><span data-stu-id="82d72-103">You can use multiple **value()** methods on `xml` data type in a **SELECT** clause to generate a rowset of extracted values.</span></span> <span data-ttu-id="82d72-104">O método **nodes()** produz uma referência interna para cada nó selecionado que pode ser usado para consulta adicional.</span><span class="sxs-lookup"><span data-stu-id="82d72-104">The **nodes()** method yields an internal reference for each selected node that can be used for additional query.</span></span> <span data-ttu-id="82d72-105">A combinação dos métodos **nodes()** e **value()** pode ser mais eficiente para gerar o conjunto de linhas quando ele tem várias colunas e, talvez, quando as expressões de caminho usadas em sua geração são complexas.</span><span class="sxs-lookup"><span data-stu-id="82d72-105">The combination of the **nodes()** and **value()** methods can be more efficient in generating the rowset when it has several columns and, perhaps, when the path expressions used in its generation are complex.</span></span>  
  
 <span data-ttu-id="82d72-106">O método **Nodes ()** produz instâncias de um `xml` tipo de dados especial, cada um com seu contexto definido como um nó selecionado diferente.</span><span class="sxs-lookup"><span data-stu-id="82d72-106">The **nodes()** method yields instances of a special `xml` data type, each of which has its context set to a different selected node.</span></span> <span data-ttu-id="82d72-107">Esse tipo de instância XML dá suporte aos métodos **query()** , **value()** , **nodes()** e **exist()** e pode ser usado em agregações **count(\*)** .</span><span class="sxs-lookup"><span data-stu-id="82d72-107">This kind of XML instance supports **query()**, **value()**, **nodes()**, and **exist()** methods and can be used in **count(\*)** aggregations.</span></span> <span data-ttu-id="82d72-108">Todos os outros usos provocam um erro.</span><span class="sxs-lookup"><span data-stu-id="82d72-108">All other uses cause an error.</span></span>  
  
## <a name="example-using-nodes"></a><span data-ttu-id="82d72-109">Exemplo: Usando nodes()</span><span class="sxs-lookup"><span data-stu-id="82d72-109">Example: Using nodes()</span></span>  
 <span data-ttu-id="82d72-110">Assuma que você deseja extrair os nomes e sobrenomes de autores e o nome não é "David".</span><span class="sxs-lookup"><span data-stu-id="82d72-110">Assume that you want to extract the first and last names of authors, and the first name is not "David".</span></span> <span data-ttu-id="82d72-111">Além disso, você deseja extrair essas informações como um conjunto de linhas que contém duas colunas, FirstName e LastName.</span><span class="sxs-lookup"><span data-stu-id="82d72-111">Additionally, you want to extract this information as a rowset that contains two columns, FirstName and LastName.</span></span> <span data-ttu-id="82d72-112">Usando os métodos **nodes()** e **value()** , isso pode ser feito da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="82d72-112">By using **nodes()** and **value()** methods, you can accomplish this as shown in the following:</span></span>  
  
```  
SELECT nref.value('(first-name/text())[1]', 'nvarchar(50)') FirstName,  
       nref.value('(last-name/text())[1]', 'nvarchar(50)') LastName  
FROM   T CROSS APPLY xCol.nodes('//author') AS R(nref)  
WHERE  nref.exist('first-name[. != "David"]') = 1  
```  
  
 <span data-ttu-id="82d72-113">Nesse exemplo, `nodes('//author')` produz um conjunto de linhas de referências a elementos `<author>` para cada instância XML.</span><span class="sxs-lookup"><span data-stu-id="82d72-113">In this example, `nodes('//author')` yields a rowset of references to `<author>` elements for each XML instance.</span></span> <span data-ttu-id="82d72-114">Os nomes e sobrenomes de autores são obtidos avaliando métodos **value()** em relação a essas referências.</span><span class="sxs-lookup"><span data-stu-id="82d72-114">The first and last names of authors are obtained by evaluating **value()** methods relative to those references.</span></span>  
  
 <span data-ttu-id="82d72-115">O SQL Server 2000 fornece a capacidade de gerar um conjunto de linhas de uma instância XML usando **OpenXml()** .</span><span class="sxs-lookup"><span data-stu-id="82d72-115">SQL Server 2000 provides the capability for generating a rowset from an XML instance by using **OpenXml()**.</span></span> <span data-ttu-id="82d72-116">É possível especificar o esquema relacional do conjunto de linhas e como valores dentro da instância XML mapeiam para colunas no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="82d72-116">You can specify the relational schema for the rowset and how values inside the XML instance map to columns in the rowset.</span></span>  
  
## <a name="example-using-openxml-on-the-xml-data-type"></a><span data-ttu-id="82d72-117">Exemplo: Usando OpenXml() no tipo de dados xml</span><span class="sxs-lookup"><span data-stu-id="82d72-117">Example: Using OpenXml() on the xml Data Type</span></span>  
 <span data-ttu-id="82d72-118">A consulta do exemplo anterior pode ser reescrita usando **OpenXml()** conforme mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="82d72-118">The query can be rewritten from the previous example by using **OpenXml()** as shown in the following.</span></span> <span data-ttu-id="82d72-119">Isso é feito criando um cursor que lê cada instância XML em uma variável XML e, em seguida, aplica OpenXML a ela:</span><span class="sxs-lookup"><span data-stu-id="82d72-119">This is done by creating a cursor that reads each XML instance into an XML variable and then applies OpenXML to it:</span></span>  
  
```  
DECLARE name_cursor CURSOR  
FOR  
   SELECT xCol   
   FROM   T  
OPEN name_cursor  
DECLARE @xmlVal XML  
DECLARE @idoc int  
FETCH NEXT FROM name_cursor INTO @xmlVal  
  
WHILE (@@FETCH_STATUS = 0)  
BEGIN  
   EXEC sp_xml_preparedocument @idoc OUTPUT, @xmlVal  
   SELECT   *  
   FROM   OPENXML (@idoc, '//author')  
          WITH (FirstName  varchar(50) 'first-name',  
                LastName   varchar(50) 'last-name') R  
   WHERE  R.FirstName != 'David'  
  
   EXEC sp_xml_removedocument @idoc  
   FETCH NEXT FROM name_cursor INTO @xmlVal  
END  
CLOSE name_cursor  
DEALLOCATE name_cursor   
```  
  
 <span data-ttu-id="82d72-120">**OpenXml()** cria uma representação na memória e usa tabelas de trabalho em vez do processador de consultas.</span><span class="sxs-lookup"><span data-stu-id="82d72-120">**OpenXml()** creates an in-memory representation and uses work tables instead of the query processor.</span></span> <span data-ttu-id="82d72-121">Ele conta com o processador do XPath versão 1.0 do MSXML versão 3.0 em vez do mecanismo de XQuery.</span><span class="sxs-lookup"><span data-stu-id="82d72-121">It relies on the XPath version 1.0 processor of MSXML version 3.0 instead of the XQuery engine.</span></span> <span data-ttu-id="82d72-122">As tabelas de trabalho não são compartilhadas entre várias chamadas para **OpenXml()** , mesmo na mesma instância XML.</span><span class="sxs-lookup"><span data-stu-id="82d72-122">The work tables are not shared among multiple calls to **OpenXml()**, even on the same XML instance.</span></span> <span data-ttu-id="82d72-123">Isto limita sua escalabilidade.</span><span class="sxs-lookup"><span data-stu-id="82d72-123">This limits its scalability.</span></span> <span data-ttu-id="82d72-124">**OpenXml()** permite acessar um formato de tabela de borda para os dados XML quando a cláusula WITH não está especificada.</span><span class="sxs-lookup"><span data-stu-id="82d72-124">**OpenXml()** allows you to access an edge table format for the XML data when the WITH clause is not specified.</span></span> <span data-ttu-id="82d72-125">Além disso, ele permite usar o valor XML restante em uma coluna de "estouro" separada.</span><span class="sxs-lookup"><span data-stu-id="82d72-125">Also, it allows you to use the remaining XML value in a separate, "overflow" column.</span></span>  
  
 <span data-ttu-id="82d72-126">A combinação das funções **nodes()** e **value()** usa índices XML de maneira efetiva.</span><span class="sxs-lookup"><span data-stu-id="82d72-126">The combination of **nodes()** and **value()** functions uses XML indexes effectively.</span></span> <span data-ttu-id="82d72-127">Como resultado, essa combinação pode exibir mais escalabilidade que o **OpenXml**.</span><span class="sxs-lookup"><span data-stu-id="82d72-127">As a result, this combination can exhibit more scalability than **OpenXml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d72-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82d72-128">See Also</span></span>  
 [<span data-ttu-id="82d72-129">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="82d72-129">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
