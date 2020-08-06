---
title: Componentes curinga e validação de conteúdo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- wildcard components [XML]
- content validation [XML]
ms.assetid: ffa7d974-3645-446c-8425-f0b22b6b060a
author: rothja
ms.author: jroth
ms.openlocfilehash: 76ff2b48efb8cff0b98827fe8522405682c294e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570555"
---
# <a name="wildcard-components-and-content-validation"></a><span data-ttu-id="9b44e-102">Componentes curinga e validação de conteúdo</span><span class="sxs-lookup"><span data-stu-id="9b44e-102">Wildcard Components and Content Validation</span></span>
  <span data-ttu-id="9b44e-103">Componentes curinga são usados para aumentar a flexibilidade do que é permitido aparecer em um modelo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9b44e-103">Wildcard components are used to increase flexibility in what is allowed to appear in a content model.</span></span> <span data-ttu-id="9b44e-104">Esses componentes têm suporte na linguagem XSD das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="9b44e-104">These components are supported in the XSD language in the following ways:</span></span>  
  
-   <span data-ttu-id="9b44e-105">Componentes curinga de elemento.</span><span class="sxs-lookup"><span data-stu-id="9b44e-105">Element wildcard components.</span></span> <span data-ttu-id="9b44e-106">Esses são representados pelo elemento **\<xsd:any>** .</span><span class="sxs-lookup"><span data-stu-id="9b44e-106">These are represented by the **\<xsd:any>** element.</span></span>  
  
-   <span data-ttu-id="9b44e-107">Componentes curinga de atributo.</span><span class="sxs-lookup"><span data-stu-id="9b44e-107">Attribute wildcard components.</span></span> <span data-ttu-id="9b44e-108">Esses são representados pelo elemento **\<xsd:anyAttribute>** .</span><span class="sxs-lookup"><span data-stu-id="9b44e-108">These are represented by the **\<xsd:anyAttribute>** element.</span></span>  
  
 <span data-ttu-id="9b44e-109">Os elementos de caractere curinga, **\<xsd:any>** e **\<xsd:anyAttribute>** , são compatíveis com o uso de um atributo **processContents**.</span><span class="sxs-lookup"><span data-stu-id="9b44e-109">Both wildcard character elements, **\<xsd:any>** and **\<xsd:anyAttribute>**, support the use of a **processContents** attribute.</span></span> <span data-ttu-id="9b44e-110">Isso permite especificar um valor que indica como aplicativos XML tratam a validação do conteúdo do documento associado a esses elementos de caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="9b44e-110">This lets you specify a value that indicates how XML applications handle the validation of document content associated with these wildcard character elements.</span></span> <span data-ttu-id="9b44e-111">Estes são os diferentes valores e seus efeitos:</span><span class="sxs-lookup"><span data-stu-id="9b44e-111">These are the different values and their effect:</span></span>  
  
-   <span data-ttu-id="9b44e-112">O valor **strict** especifica que o conteúdo é completamente validado.</span><span class="sxs-lookup"><span data-stu-id="9b44e-112">The **strict** value specifies that the contents are fully validated.</span></span>  
  
-   <span data-ttu-id="9b44e-113">O valor **skip** especifica que o conteúdo não é validado.</span><span class="sxs-lookup"><span data-stu-id="9b44e-113">The **skip** value specifies that the contents are not validated.</span></span>  
  
-   <span data-ttu-id="9b44e-114">O valor **lax** especifica que apenas elementos e atributos para os quais definições de esquema estão disponíveis são validados.</span><span class="sxs-lookup"><span data-stu-id="9b44e-114">The **lax** value specifies that only elements and attributes for which schema definitions are available are validated.</span></span>  
  
## <a name="lax-validation-and-xsanytype-elements"></a><span data-ttu-id="9b44e-115">Validação incerta e elementos xs:anyType</span><span class="sxs-lookup"><span data-stu-id="9b44e-115">Lax Validation and xs:anyType Elements</span></span>  
 <span data-ttu-id="9b44e-116">A especificação do Esquema XML usa validação **lax** para elementos do tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="9b44e-116">The XML Schema specification uses **lax** validation for elements of the **anyType** type.</span></span> <span data-ttu-id="9b44e-117">Como o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] não dá suporte à validação incerta, a validação estrita foi aplicada para elementos do **anyType**.</span><span class="sxs-lookup"><span data-stu-id="9b44e-117">Because [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] did not support lax validation, strict validation was applied for elements of the **anyType**.</span></span> <span data-ttu-id="9b44e-118">A partir do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], há suporte para a validação incerta.</span><span class="sxs-lookup"><span data-stu-id="9b44e-118">Beginning with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], lax validation is supported.</span></span> <span data-ttu-id="9b44e-119">Conteúdo de elementos do tipo **anyType** serão validados usando a validação incerta.</span><span class="sxs-lookup"><span data-stu-id="9b44e-119">Content of elements of type **anyType** will be validated using lax validation.</span></span>  
  
 <span data-ttu-id="9b44e-120">O exemplo a seguir ilustra a validação incerta.</span><span class="sxs-lookup"><span data-stu-id="9b44e-120">The following example illustrates the lax validation.</span></span> <span data-ttu-id="9b44e-121">O elemento do esquema `e` é do tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="9b44e-121">The schema element `e` is of the **anyType** type.</span></span> <span data-ttu-id="9b44e-122">O exemplo cria variáveis **xml** com tipo e ilustra a validação incerta do elemento do tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="9b44e-122">The example creates typed **xml** variables and illustrates the lax validation of the element of the **anyType** type.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="http://ns">  
   <element name="e" type="anyType"/>  
   <element name="a" type="byte"/>  
   <element name="b" type="string"/>  
 </schema>'  
GO  
```  
  
 <span data-ttu-id="9b44e-123">O exemplo a seguir tem êxito, porque a validação de `<e>` tem êxito:</span><span class="sxs-lookup"><span data-stu-id="9b44e-123">The following example succeeds, because the validation of `<e>` is successful:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="9b44e-124">O seguinte exemplo tem êxito.</span><span class="sxs-lookup"><span data-stu-id="9b44e-124">The following example succeeds.</span></span> <span data-ttu-id="9b44e-125">A instância é aceita, embora nenhum elemento `<c>` esteja definido no esquema:</span><span class="sxs-lookup"><span data-stu-id="9b44e-125">The instance is accepted, even though no element `<c>` is defined in the schema:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><c>Wrong</c><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="9b44e-126">A instância XML no exemplo a seguir é rejeitada, porque a definição do elemento `<a>` não permite um valor de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9b44e-126">The XML instance in the following example is rejected, because the definition of the `<a>` element does not allow a string value.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>Wrong</a><b>data</b></e>'  
SELECT @var  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b44e-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b44e-127">See Also</span></span>  
 [<span data-ttu-id="9b44e-128">Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor</span><span class="sxs-lookup"><span data-stu-id="9b44e-128">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
