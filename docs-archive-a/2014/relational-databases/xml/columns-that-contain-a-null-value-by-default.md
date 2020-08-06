---
title: Colunas que contêm um valor nulo por padrão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- columns [XML in SQL Server], null default value
ms.assetid: 9381c07f-6887-4a62-9730-32661f9aa87c
author: rothja
ms.author: jroth
ms.openlocfilehash: 92ea51101f73695be2075a1b41deb62ca021f496
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569238"
---
# <a name="columns-that-contain-a-null-value-by-default"></a><span data-ttu-id="d7a5a-102">Colunas que contêm um valor nulo por padrão</span><span class="sxs-lookup"><span data-stu-id="d7a5a-102">Columns that Contain a Null Value By Default</span></span>
  <span data-ttu-id="d7a5a-103">Por padrão, um valor nulo em uma coluna é mapeado para a ausência do atributo, nó ou elemento.</span><span class="sxs-lookup"><span data-stu-id="d7a5a-103">By default, a null value in a column maps to the absence of the attribute, node, or element.</span></span> <span data-ttu-id="d7a5a-104">Esse comportamento padrão pode ser substituído solicitando XML centrado em elemento usando a diretiva ELEMENTS e especificando XSINIL para solicitar a adição de elementos para valores NULL, conforme mostrado na consulta a seguir:</span><span class="sxs-lookup"><span data-stu-id="d7a5a-104">This default behavior can be overwritten by requesting element-centric XML using the ELEMENTS directive and specifying XSINIL to request adding elements for NULL values, as shown in the following query:</span></span>  
  
```  
SELECT EmployeeID as "@EmpID",   
       FirstName  as "EmpName/First",   
       MiddleName as "EmpName/Middle",   
       LastName   as "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="d7a5a-105">O resultado é mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="d7a5a-105">The following shows the result.</span></span> <span data-ttu-id="d7a5a-106">Observe que se XSINIL não for especificado, o elemento <`Middle`> estará ausente.</span><span class="sxs-lookup"><span data-stu-id="d7a5a-106">Note that if XSINIL is not specified, the <`Middle`> element will be absent.</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7a5a-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7a5a-107">See Also</span></span>  
 [<span data-ttu-id="d7a5a-108">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="d7a5a-108">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
