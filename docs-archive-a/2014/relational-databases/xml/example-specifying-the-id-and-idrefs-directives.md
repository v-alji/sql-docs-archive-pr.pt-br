---
title: 'Exemplo: Especificando as diretivas ID e IDREFS | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- IDREFS directive
- ID directive
ms.assetid: 99b9f0d8-ecbb-4225-859f-881066c09785
author: rothja
ms.author: jroth
ms.openlocfilehash: c21ba1bd19691014f179801421322970a3dd6dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582338"
---
# <a name="example-specifying-the-id-and-idrefs-directives"></a><span data-ttu-id="65163-102">Exemplo: Especificando as diretivas ID e IDREFS</span><span class="sxs-lookup"><span data-stu-id="65163-102">Example: Specifying the ID and IDREFS Directives</span></span>
  <span data-ttu-id="65163-103">Um atributo de elemento pode ser especificado como um atributo de tipo `ID`, e o atributo `IDREFS` pode ser usado para se referir a ele.</span><span class="sxs-lookup"><span data-stu-id="65163-103">An element attribute can be specified as an `ID` type attribute, and the `IDREFS` attribute can then be used to refer to it.</span></span> <span data-ttu-id="65163-104">Isso habilita vínculos intradocumento e é semelhante às relações de chave primária e de chave estrangeira em bancos de dados relacionais.</span><span class="sxs-lookup"><span data-stu-id="65163-104">This enables intra-document links and is similar to the primary key and foreign key relationships in relational databases.</span></span>  
  
 <span data-ttu-id="65163-105">Este exemplo ilustra como as diretivas `ID` e `IDREFS` podem ser usadas para criar atributos de tipos `ID` e `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="65163-105">This example illustrates how the `ID` and `IDREFS` directives can be used to create attributes of `ID` and `IDREFS` types.</span></span> <span data-ttu-id="65163-106">Como os IDs não podem ser valores inteiros, os valores de ID neste exemplo são convertidos.</span><span class="sxs-lookup"><span data-stu-id="65163-106">Because IDs cannot be integer values, the ID values in this example are converted.</span></span> <span data-ttu-id="65163-107">Em outras palavras, seus tipos são convertidos.</span><span class="sxs-lookup"><span data-stu-id="65163-107">In other words, they are type casted.</span></span> <span data-ttu-id="65163-108">Prefixos são usados para os valores de ID.</span><span class="sxs-lookup"><span data-stu-id="65163-108">Prefixes are used for the ID values.</span></span>  
  
 <span data-ttu-id="65163-109">Assuma que você deseja construir XML, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="65163-109">Assume that you want to construct XML as shown in the following:</span></span>  
  
```  
<Customer CustomerID="C1" SalesOrderIDList=" O11 O22 O33..." >  
    <SalesOrder SalesOrderID="O11" OrderDate="..." />  
    <SalesOrder SalesOrderID="O22" OrderDate="..." />  
    <SalesOrder SalesOrderID="O33" OrderDate="..." />  
    ...  
</Customer>  
```  
  
 <span data-ttu-id="65163-110">O atributo `SalesOrderIDList` do elemento < `Customer` > é um atributo com vários valores que se refere ao atributo `SalesOrderID` do elemento < `SalesOrder` >.</span><span class="sxs-lookup"><span data-stu-id="65163-110">The `SalesOrderIDList` attribute of the < `Customer` > element is a multivalued attribute that refers to the `SalesOrderID` attribute of the < `SalesOrder` > element.</span></span> <span data-ttu-id="65163-111">Para estabelecer esse link, o atributo `SalesOrderID` deve ser declarado como sendo do tipo `ID` e o atributo `SalesOrderIDList` do elemento < `Customer`> deve ser declarado como sendo do tipo `IDREFS`.</span><span class="sxs-lookup"><span data-stu-id="65163-111">To establish this link, the `SalesOrderID` attribute must be declared of `ID` type, and the `SalesOrderIDList` attribute of the < `Customer`> element must be declared of `IDREFS` type.</span></span> <span data-ttu-id="65163-112">Como um cliente pode solicitar vários pedidos, o tipo `IDREFS` é usado.</span><span class="sxs-lookup"><span data-stu-id="65163-112">Because a customer can request several orders, the `IDREFS` type is used.</span></span>  
  
 <span data-ttu-id="65163-113">Os elementos do tipo `IDREFS` também têm mais de um valor.</span><span class="sxs-lookup"><span data-stu-id="65163-113">Elements of `IDREFS` type also have more than one value.</span></span> <span data-ttu-id="65163-114">Portanto você precisa usar uma cláusula select separada que reutilizará as mesmas informações de marca, pai e coluna de chave.</span><span class="sxs-lookup"><span data-stu-id="65163-114">Therefore, you have to use a separate select clause that will reuse the same tag, parent, and key column information.</span></span> <span data-ttu-id="65163-115">`ORDER BY` precisa garantir que a sequência de linhas que constituem os valores `IDREFS` sejam exibidas agrupadas em conjunto sob seu elemento pai.</span><span class="sxs-lookup"><span data-stu-id="65163-115">The `ORDER BY` then has to ensure that the sequence of rows that make up the `IDREFS` values appears grouped together under their parent element.</span></span>  
  
 <span data-ttu-id="65163-116">Esta é a consulta que produz o XML desejado.</span><span class="sxs-lookup"><span data-stu-id="65163-116">This is the query that produces the XML you want.</span></span> <span data-ttu-id="65163-117">A consulta usa as diretivas `ID` e `IDREFS` para substituir os tipos nos nomes das colunas (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span><span class="sxs-lookup"><span data-stu-id="65163-117">The query uses the `ID` and `IDREFS` directives to overwrite the types in the column names (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID       [Customer!1!CustomerID],  
        NULL               [Customer!1!SalesOrderIDList!IDREFS],  
        NULL               [SalesOrder!2!SalesOrderID!ID],  
        NULL               [SalesOrder!2!OrderDate]  
FROM   Sales.Customer C   
UNION ALL   
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID,  
        'O-'+CAST(SalesOrderID as varchar(10)),   
        NULL,  
        NULL  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
        C.CustomerID,  
        NULL,  
        'O-'+CAST(SalesOrderID as varchar(10)),  
        OrderDate  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerIDORDER BY [Customer!1!CustomerID] ,  
         [SalesOrder!2!SalesOrderID!ID],  
         [Customer!1!SalesOrderIDList!IDREFS]  
FOR XML EXPLICIT;  
```  
  
## <a name="see-also"></a><span data-ttu-id="65163-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65163-118">See Also</span></span>  
 [<span data-ttu-id="65163-119">Usar o modo EXPLICIT com FOR XML</span><span class="sxs-lookup"><span data-stu-id="65163-119">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
