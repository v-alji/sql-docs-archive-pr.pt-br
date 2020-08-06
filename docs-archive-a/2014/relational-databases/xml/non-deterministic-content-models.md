---
title: Modelos de conteúdo não determinístico | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- non-deterministic content models
- content models [XML in SQL Server]
ms.assetid: 9d4513e7-dd19-4491-b7c7-28bc7c2f8589
author: rothja
ms.author: jroth
ms.openlocfilehash: 6182ff4a5ee0c9c109f6880c7d3337fb6dd20749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679191"
---
# <a name="non-deterministic-content-models"></a><span data-ttu-id="d661c-102">modelos de conteúdo não determinístico</span><span class="sxs-lookup"><span data-stu-id="d661c-102">Non-Deterministic Content Models</span></span>
  <span data-ttu-id="d661c-103">Antes do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejeitava esquemas XML que tinham modelos de conteúdo não determinístico.</span><span class="sxs-lookup"><span data-stu-id="d661c-103">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejected XML schemas that had non-deterministic content models.</span></span>  
  
 <span data-ttu-id="d661c-104">No entanto, a partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1 os modelos de conteúdo não determinístico serão aceitos se as restrições de ocorrência forem 0,1 ou não associadas.</span><span class="sxs-lookup"><span data-stu-id="d661c-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, however, non-deterministic content models are accepted if the occurrence constraints are 0,1, or unbounded.</span></span>  
  
## <a name="example-non-deterministic-content-model-rejected"></a><span data-ttu-id="d661c-105">Exemplo: Modelo de conteúdo não determinístico rejeitado</span><span class="sxs-lookup"><span data-stu-id="d661c-105">Example: Non-deterministic content model rejected</span></span>  
 <span data-ttu-id="d661c-106">O exemplo a seguir tenta criar um esquema XML com um modelo de conteúdo não determinístico.</span><span class="sxs-lookup"><span data-stu-id="d661c-106">The following example attempts to create an XML schema with a non-deterministic content model.</span></span> <span data-ttu-id="d661c-107">Há falha no código porque não está claro se o elemento `<root>` deve ter uma sequência de dois elementos `<a>` ou se o elemento `<root>` deve ter duas sequências, cada uma com um elemento `<a>` .</span><span class="sxs-lookup"><span data-stu-id="d661c-107">The code fails because it is not clear whether the `<root>` element should have a sequence of two `<a>` elements or if the `<root>` element should have two sequences, each with an `<a>` element.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="1" maxOccurs="2">  
                <element name="a" type="string" minOccurs="1" maxOccurs="2"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
 <span data-ttu-id="d661c-108">O esquema pode ser fixado movendo a restrição de ocorrência para um local exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d661c-108">The schema can be fixed by moving the occurrence constraint to a unique location.</span></span> <span data-ttu-id="d661c-109">Por exemplo, a restrição pode ser movida para a partícula da sequência de contenção:</span><span class="sxs-lookup"><span data-stu-id="d661c-109">For example, the constraint can be moved to the containing sequence particle:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="4">  
    <element name="a" type="string" minOccurs="1" maxOccurs="1"/>  
</sequence>  
```  
  
 <span data-ttu-id="d661c-110">Ou a restrição pode ser movida para o elemento contido:</span><span class="sxs-lookup"><span data-stu-id="d661c-110">Or the constraint can be moved to the contained element:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="1">  
     <element name="a" type="string" minOccurs="1" maxOccurs="4"/>  
</sequence>  
```  
  
## <a name="example-non-deterministic-content-model-accepted"></a><span data-ttu-id="d661c-111">Exemplo: Modelo de conteúdo não determinístico aceito</span><span class="sxs-lookup"><span data-stu-id="d661c-111">Example: Non-deterministic content model accepted</span></span>  
 <span data-ttu-id="d661c-112">O esquema a seguir deve ser rejeitado em versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="d661c-112">The following schema would be rejected in versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="0" maxOccurs="unbounded">  
                <element name="a" type="string" minOccurs="0" maxOccurs="1"/>  
                <element name="b" type="string" minOccurs="1" maxOccurs="unbounded"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d661c-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d661c-113">See Also</span></span>  
 [<span data-ttu-id="d661c-114">Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor</span><span class="sxs-lookup"><span data-stu-id="d661c-114">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
