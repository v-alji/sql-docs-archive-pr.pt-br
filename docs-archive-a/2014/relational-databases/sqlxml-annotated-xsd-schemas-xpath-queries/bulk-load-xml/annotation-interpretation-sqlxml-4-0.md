---
title: Interpretação de anotação (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, XML Bulk Load
- XML Bulk Load [SQLXML], annotation intepretations
- annotations [SQLXML]
- bulk load [SQLXML], annotation interpretations
- annotated XDR schemas, XML Bulk Load
ms.assetid: 1c46bdb6-2812-4a13-b60b-7101c04b299f
author: rothja
ms.author: jroth
ms.openlocfilehash: c31d56f7dd577b4b5a5b582eb0e3b1db312109a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575758"
---
# <a name="annotation-interpretation-sqlxml-40"></a><span data-ttu-id="e7458-102">Interpretação de anotação (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e7458-102">Annotation Interpretation (SQLXML 4.0)</span></span>
  <span data-ttu-id="e7458-103">Os tópicos desta seção descrevem como o Carregamento em Massa de XML interpreta as anotações no esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="e7458-103">The topics in this section describe how XML Bulk Load interprets annotations in the XSD schema.</span></span> <span data-ttu-id="e7458-104">O comportamento descrito aqui também se aplica às anotações no esquema XDR.</span><span class="sxs-lookup"><span data-stu-id="e7458-104">The behavior described here also applies to the annotations in the XDR schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7458-105">As informações nesses tópicos descrevem apenas as anotações usadas pelo Carregamento em Massa de XML em seu processamento.</span><span class="sxs-lookup"><span data-stu-id="e7458-105">The information in these topics describes only the annotations used by XML Bulk Load in its processing.</span></span> <span data-ttu-id="e7458-106">Para obter uma lista completa de anotações para o esquema XSD que têm suporte do SQLXML 4,0, consulte [usando anotações em esquemas xsd &#40;sqlxml 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e7458-106">For a complete list of annotations for the XSD schema that are supported by SQLXML 4.0, see [Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="e7458-107">Para obter uma lista de anotações com suporte para esquemas XDR, consulte [esquemas XDR anotados &#40;preteridos no SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e7458-107">For a list of supported annotations for XDR schemas, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7458-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e7458-108">In This Section</span></span>  
 [<span data-ttu-id="e7458-109">SQL: relação e a regra de ordenação de chave &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e7458-109">sql:relationship and the Key Ordering Rule &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-relationship-and-key-ordering-rule.md)  
 <span data-ttu-id="e7458-110">Descreve como a anotação `sql:relationship` é interpretada no Carregamento em Massa de XML.</span><span class="sxs-lookup"><span data-stu-id="e7458-110">Describes how the `sql:relationship` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="e7458-111">SQL: mapeado &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e7458-111">sql:mapped &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-mapped.md)  
 <span data-ttu-id="e7458-112">Descreve como a anotação `sql:mapped` é interpretada no Carregamento em Massa de XML.</span><span class="sxs-lookup"><span data-stu-id="e7458-112">Describes how the `sql:mapped` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="e7458-113">SQL: limit-field e SQL: limit-value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e7458-113">sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="e7458-114">Descreve como as anotações `sql:limit-field` e `sql:limit-value` são interpretadas no Carregamento em Massa de XML.</span><span class="sxs-lookup"><span data-stu-id="e7458-114">Describes how the `sql:limit-field` and `sql:limit-value` annotations are interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="e7458-115">SQL: overflow-field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e7458-115">sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="e7458-116">Descreve como a anotação `sql:overflow` é interpretada no Carregamento em Massa de XML.</span><span class="sxs-lookup"><span data-stu-id="e7458-116">Describes how the `sql:overflow` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="e7458-117">Outras anotações &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e7458-117">Other Annotations &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-other-annotations.md)  
 <span data-ttu-id="e7458-118">Descreve como as anotações a seguir são interpretadas no Carregamento em Massa de XML: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="e7458-118">Describes how the following annotations are interpreted in XML Bulk Load: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span></span>  
  
  
