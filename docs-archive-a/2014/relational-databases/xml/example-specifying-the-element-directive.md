---
title: 'Exemplo: Especificando a diretiva ELEMENT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENT directive
ms.assetid: 80dd5d1f-fa90-4f97-a186-8fa3f460a7f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a03d1049fa9df23eff759634bcd74f88f842a8e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678667"
---
# <a name="example-specifying-the-element-directive"></a><span data-ttu-id="25c09-102">Exemplo: Especificando a diretiva ELEMENT</span><span class="sxs-lookup"><span data-stu-id="25c09-102">Example: Specifying the ELEMENT Directive</span></span>
  <span data-ttu-id="25c09-103">Isso recupera informações de funcionários e gera XML centrado em elemento conforme mostrado no seguinte:</span><span class="sxs-lookup"><span data-stu-id="25c09-103">This retrieves employee information and generates element-centric XML as shown in the following:</span></span>  
  
```  
<Employee EmpID=...>  
  <Name>  
    <FName>...</FName>  
    <LName>...</LName>  
  </Name>  
</Employee>  
```  
  
 <span data-ttu-id="25c09-104">A consulta permanece a mesma, exceto que você adiciona a diretiva `ELEMENT` nos nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="25c09-104">The query remains the same, except you add the `ELEMENT` directive in the column names.</span></span> <span data-ttu-id="25c09-105">Portanto em vez de atributos, os filhos do elemento <`FName`> e <`LName`> são adicionados ao elemento <`Name`>.</span><span class="sxs-lookup"><span data-stu-id="25c09-105">Therefore, instead of attributes, the <`FName`> and <`LName`> element children are added to the <`Name`> element.</span></span> <span data-ttu-id="25c09-106">Como a coluna `Employee!1!EmpID` não especifica a diretiva `ELEMENT`, `EmpID` é adicionado como o atributo do elemento <`Employee`>.</span><span class="sxs-lookup"><span data-stu-id="25c09-106">Because the `Employee!1!EmpID` column does not specify the `ELEMENT` directive, `EmpID` is added as the attribute of the <`Employee`> element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName!ELEMENT],  
       NULL       as [Name!2!LName!ELEMENT]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
ORDER BY [Employee!1!EmpID],[Name!2!FName!ELEMENT]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="25c09-107">Este é o resultado parcial.</span><span class="sxs-lookup"><span data-stu-id="25c09-107">This is the partial result.</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name>`  
  
 `<FName>Ken</FName>`  
  
 `<LName>S??nchez</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name>`  
  
 `<FName>Terri</FName>`  
  
 `<LName>Duffy</LName>`  
  
 `</Name>`  
  
 `</Employee>`  
  
 `...`  
  
## <a name="see-also"></a><span data-ttu-id="25c09-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25c09-108">See Also</span></span>  
 [<span data-ttu-id="25c09-109">Usar o modo EXPLICIT com FOR XML</span><span class="sxs-lookup"><span data-stu-id="25c09-109">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
