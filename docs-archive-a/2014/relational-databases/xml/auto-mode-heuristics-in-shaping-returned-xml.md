---
title: Heurística do modo AUTO na formação do XML retornado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, heuristics in shaping returned XML
ms.assetid: 6c5cb6c1-2921-4ba1-8100-0bf8074f9103
author: rothja
ms.author: jroth
ms.openlocfilehash: 7a64cda8989e1e45d4ad869f8883e1c9d65f4b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569252"
---
# <a name="auto-mode-heuristics-in-shaping-returned-xml"></a><span data-ttu-id="3ea63-102">Heurística de modo AUTO na formação do XML retornado</span><span class="sxs-lookup"><span data-stu-id="3ea63-102">AUTO Mode Heuristics in Shaping Returned XML</span></span>
  <span data-ttu-id="3ea63-103">O modo AUTO determina a forma do  XML retornado com base na consulta.</span><span class="sxs-lookup"><span data-stu-id="3ea63-103">AUTO mode determines the shape of returned XML based on the query.</span></span> <span data-ttu-id="3ea63-104">Para determinar como os elementos devem ser aninhados, a heurística do modo AUTO compara valores da coluna em linhas adjacentes.</span><span class="sxs-lookup"><span data-stu-id="3ea63-104">In determining how elements are to be nested, AUTO mode heuristics compare column values in adjacent rows.</span></span> <span data-ttu-id="3ea63-105">São comparadas colunas de todos os tipos, menos **ntext**, **text**, **image**e **xml**.</span><span class="sxs-lookup"><span data-stu-id="3ea63-105">Columns of all types, except **ntext**, **text**, **image**, and **xml**, are compared.</span></span> <span data-ttu-id="3ea63-106">São comparadas colunas do tipo **(n)varchar(max)** e **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="3ea63-106">Columns of type **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="3ea63-107">O exemplo seguinte ilustra a heurística do modo AUTO que determina a forma do XML resultante:</span><span class="sxs-lookup"><span data-stu-id="3ea63-107">The following example illustrates the AUTO mode heuristics that determine the shape of the resulting XML:</span></span>  
  
```  
SELECT T1.Id, T2.Id, T1.Name  
FROM   T1, T2  
WHERE ...  
FOR XML AUTO  
ORDER BY T1.Id  
```  
  
 <span data-ttu-id="3ea63-108">Para determinar o local em que um novo elemento <`T1`> começa, todos os valores de T1 da coluna, exceto **ntext**, **text**, **image** r **xml**, serão comparados se a chave na tabela T1 não for especificada.</span><span class="sxs-lookup"><span data-stu-id="3ea63-108">To determine where a new <`T1`> element starts, all column values of T1, except **ntext**, **text**, **image** and **xml**, are compared if the key on the table T1 is not specified.</span></span> <span data-ttu-id="3ea63-109">Em seguida, assuma que a coluna **Name** é **nvarchar(40)** e a instrução SELECT retornará este conjunto de linhas:</span><span class="sxs-lookup"><span data-stu-id="3ea63-109">Next, assume that the **Name** column is **nvarchar(40)** and the SELECT statement returns this rowset:</span></span>  
  
```  
T1.Id  T1.Name  T2.Id  
-----------------------  
1       Andrew    2  
1       Andrew    3  
1       Nancy     4  
```  
  
 <span data-ttu-id="3ea63-110">A heurística do modo AUTO compara todos os valores da tabela T1 e as colunas Name e Id.</span><span class="sxs-lookup"><span data-stu-id="3ea63-110">The AUTO mode heuristics compare all the values of table T1, the Id and Name columns.</span></span> <span data-ttu-id="3ea63-111">Como as duas primeiras linhas têm os mesmos valores para as colunas ID e Nome, um elemento \<T1> com dois elementos filho \<T2> é adicionado ao resultado.</span><span class="sxs-lookup"><span data-stu-id="3ea63-111">Because the first two rows have the same values for the Id and Name columns, one \<T1> element having two \<T2> child elements is added in the result.</span></span>  
  
 <span data-ttu-id="3ea63-112">O XML retornado é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3ea63-112">Following is the XML that is returned:</span></span>  
  
```  
<T1 Id="1" Name="Andrew">  
    <T2 Id="2" />  
    <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
      <T2 Id="4" />  
</T>  
```  
  
 <span data-ttu-id="3ea63-113">Agora assuma que a coluna Name é de tipo **text** .</span><span class="sxs-lookup"><span data-stu-id="3ea63-113">Now assume that the Name column is of **text** type.</span></span> <span data-ttu-id="3ea63-114">A heurística de modo AUTO não compara valores desse tipo.</span><span class="sxs-lookup"><span data-stu-id="3ea63-114">The AUTO mode heuristics do not compare the values for this type.</span></span> <span data-ttu-id="3ea63-115">Em vez disso, ela assume que os valores não são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="3ea63-115">Instead, it assumes that the values are not the same.</span></span> <span data-ttu-id="3ea63-116">Isso resulta em geração de XML conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="3ea63-116">This results in XML generation as shown in the following:</span></span>  
  
```  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="2" />  
</T1>  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
  <T2 Id="4" />  
</T1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ea63-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ea63-117">See Also</span></span>  
 [<span data-ttu-id="3ea63-118">Usar o modo AUTO com FOR XML</span><span class="sxs-lookup"><span data-stu-id="3ea63-118">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
