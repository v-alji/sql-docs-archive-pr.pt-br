---
title: Facetas de enumeração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- enumeration facets
ms.assetid: dec23a79-ddd6-4701-9721-55a2c435a34d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e06598890d9b652879327e0351db5113cc17e6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569234"
---
# <a name="enumeration-facets"></a><span data-ttu-id="ed15c-102">facetas de enumeração</span><span class="sxs-lookup"><span data-stu-id="ed15c-102">Enumeration Facets</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ed15c-103">rejeita esquemas XML com tipos que têm facetas padrão ou enumerações que violam essas facetas.</span><span class="sxs-lookup"><span data-stu-id="ed15c-103">rejects XML schemas with types that have pattern facets or enumerations that violate those facets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed15c-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ed15c-104">Example</span></span>  
 <span data-ttu-id="ed15c-105">O esquema a seguir será rejeitado, porque o valor de enumeração apresentado inclui um valor em maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ed15c-105">The following schema would be rejected, because the featured enumeration value includes a mixed-case value.</span></span> <span data-ttu-id="ed15c-106">Também será rejeitado porque esse valor viola o valor padrão que limita valores a apenas letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ed15c-106">It would also be rejected because this value violates the pattern value that limits values to only lowercase letters.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MySampleCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns" xmlns:ns="http://ns">  
    <simpleType name="MyST">  
       <restriction base="string">  
          <pattern value="[a-z]*"/>  
       </restriction>  
    </simpleType>  
  
    <simpleType name="MyST2">  
       <restriction base="ns:MyST">  
           <enumeration value="mYstring"/>  
       </restriction>  
    </simpleType>  
</schema>'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed15c-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ed15c-107">See Also</span></span>  
 [<span data-ttu-id="ed15c-108">Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor</span><span class="sxs-lookup"><span data-stu-id="ed15c-108">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
