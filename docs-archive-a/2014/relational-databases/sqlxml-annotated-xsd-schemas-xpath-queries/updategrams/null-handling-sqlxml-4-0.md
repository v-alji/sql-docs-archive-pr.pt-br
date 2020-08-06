---
title: Manipulação nula (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updg:nullvalue attribute
- updategrams [SQLXML], null values
- nullvalue attribute
- null values [SQLXML]
ms.assetid: 5e11eebb-d94e-4ce6-a6d0-870225706bc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 430643e8a6c9bd3dd00b2763990645c6a162ee40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575749"
---
# <a name="null-handling-sqlxml-40"></a><span data-ttu-id="b7c6f-102">Manipulação de NULL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b7c6f-102">NULL Handling (SQLXML 4.0)</span></span>
  <span data-ttu-id="b7c6f-103">A sintaxe XML indica NULL como uma ausência.</span><span class="sxs-lookup"><span data-stu-id="b7c6f-103">XML syntax denotes NULL as an absence.</span></span> <span data-ttu-id="b7c6f-104">(Por exemplo, se um atributo ou valor de elemento for nulo, esse atributo ou elemento estará ausente do documento XML.) No [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, o `updg:nullvalue` atributo habilita a especificação de NULL para um valor de elemento ou atributo.</span><span class="sxs-lookup"><span data-stu-id="b7c6f-104">(For example, if an attribute or element value is NULL, that attribute or element is absent from the XML document.) In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, the `updg:nullvalue` attribute enables specifying NULL for an element or attribute value.</span></span>  
  
 <span data-ttu-id="b7c6f-105">Por exemplo, o updategram a seguir garante que o valor de **título** de um contato com **contactid** de 64 seja NULL e, em seguida, atualiza o valor do **título** para "Mr".</span><span class="sxs-lookup"><span data-stu-id="b7c6f-105">For example, the following updategram ensures that the **Title** value for a contact with **ContactID** of 64 is NULL, and then updates the **Title** value to "Mr."</span></span> <span data-ttu-id="b7c6f-106">para este contato.</span><span class="sxs-lookup"><span data-stu-id="b7c6f-106">for this contact.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync updg:nullvalue="IsNULL"  >  
    <updg:before>  
       <Person.Contact ContactID="64" Title="IsNULL" />  
    </updg:before>  
    <updg:after>  
       <Person.Contact ContactID="64" Title="Mr." />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="b7c6f-107">Quando os parâmetros são passados para um diagrama de atualização, é possível passar NULL como o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b7c6f-107">When parameters are passed to an updategram, NULL can be passed as the parameter value.</span></span> <span data-ttu-id="b7c6f-108">Isto é feito especificando o atributo `nullvalue` no bloco `<updg:header>`.</span><span class="sxs-lookup"><span data-stu-id="b7c6f-108">This is done by specifying the `nullvalue` attribute in the `<updg:header>` block.</span></span> <span data-ttu-id="b7c6f-109">Para obter um exemplo, consulte [passando parâmetros para updategrams &#40;SQLXML 4,0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="b7c6f-109">For an example, see [Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c6f-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b7c6f-110">See Also</span></span>  
 [<span data-ttu-id="b7c6f-111">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b7c6f-111">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
