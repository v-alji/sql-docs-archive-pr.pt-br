---
title: Considerações de segurança para FOR XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- client-side XML formatting
- FOR XML clause, security
- server-side XML formatting
- AUTO mode
- security [SQLXML], FOR XML
ms.assetid: facba279-df93-475b-ad43-0043dc5bae03
author: rothja
ms.author: jroth
ms.openlocfilehash: 9a64fa61848e4b5435b2aa944c53953a8c083ab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581725"
---
# <a name="for-xml-security-considerations-sqlxml-40"></a><span data-ttu-id="01d8a-102">Considerações de segurança de FOR XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="01d8a-102">FOR XML Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="01d8a-103">O modo FOR XML AUTO gera uma hierarquia de XML na qual os nomes de elemento mapeiam para nomes de tabela e nomes de atributo mapeiam para nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="01d8a-103">The FOR XML AUTO mode generates an XML hierarchy in which element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="01d8a-104">Dessa forma, a tabela e as informações de coluna do banco de dados são expostas.</span><span class="sxs-lookup"><span data-stu-id="01d8a-104">This exposes the database table and column information.</span></span> <span data-ttu-id="01d8a-105">Você pode ocultar as informações do banco de dados quando usar modo AUTO (formatação no lado de servidor) especificando aliases de coluna e da tabela na consulta.</span><span class="sxs-lookup"><span data-stu-id="01d8a-105">You can hide the database information when you use AUTO mode (server-side formatting) by specifying table and column aliases in the query.</span></span> <span data-ttu-id="01d8a-106">Esses aliases são retornados no documento XML resultante como nomes de elemento e atributos.</span><span class="sxs-lookup"><span data-stu-id="01d8a-106">These aliases are returned in the resulting XML document as element and attribute names.</span></span>  
  
 <span data-ttu-id="01d8a-107">Por exemplo, a seguinte consulta especifica o modo de AUTO; portanto, a formatação XML é feita no servidor:</span><span class="sxs-lookup"><span data-stu-id="01d8a-107">For example, the following query specifies AUTO mode; therefore, the XML formatting is done on the server:</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="01d8a-108">No documento XML resultante, os aliases são usados para nomes do elemento e do atributo:</span><span class="sxs-lookup"><span data-stu-id="01d8a-108">In the resulting XML document, the aliases are used for element and attribute names:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <C F="Nancy" L="Fuller" />   
  <CE F="Andrew" L="Peacock" />   
  <C F="Janet" L="Leverling" />   
  ...  
</root>  
```  
  
 <span data-ttu-id="01d8a-109">Quando você usar modo NESTED (formatação no lado do cliente), só são retornados aliases para atributos no documento XML resultante.</span><span class="sxs-lookup"><span data-stu-id="01d8a-109">When you use NESTED mode (client-side formatting), aliases are returned only for attributes in the resulting XML document.</span></span> <span data-ttu-id="01d8a-110">Os nomes das tabelas base são sempre retornados como nomes de elemento.</span><span class="sxs-lookup"><span data-stu-id="01d8a-110">The names of the base tables are always returned as element names.</span></span> <span data-ttu-id="01d8a-111">Por exemplo, a seguinte consulta especifica o modo NESTED:</span><span class="sxs-lookup"><span data-stu-id="01d8a-111">For example, the following query specifies NESTED mode.</span></span>  
  
```  
SELECT C.FirstName as F,C.LastName as L   
FROM Person.Contact C   
FOR XML AUTO  
```  
  
 <span data-ttu-id="01d8a-112">No documento XML resultante, os nomes das tabelas base são retornados como nomes de elemento, e os aliases da tabela não são usados:</span><span class="sxs-lookup"><span data-stu-id="01d8a-112">In the resulting XML document, the names of the base tables are returned as element names and table aliases are not used:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Person.Contact F="Nancy" L="Fuller" />   
  <Person.Contact F="Andrew" L="Peacock" />   
  <Person.Contact F="Janet" L="Leverling" />   
       ...  
</root>  
```  
  
  
