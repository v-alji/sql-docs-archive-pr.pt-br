---
title: Outras anotações (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- url-encode annotation
- sql:key-fields
- use-cdata annotation
- sql:is-mapping-schema
- sql:url-encode
- sql:id-prefix
- sql:use-cdata
- key-fields annotation
- id-prefix annotation [SQLXML]
- is-mapping-schema annotation
ms.assetid: f7b4d37b-d6d3-4ac3-b2fd-a0b534a924e4
author: rothja
ms.author: jroth
ms.openlocfilehash: b654568c93df0a0c3e08cf6eaa615b7026a9c18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573891"
---
# <a name="other-annotations-sqlxml-40"></a><span data-ttu-id="78568-102">Outras anotações (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="78568-102">Other Annotations (SQLXML 4.0)</span></span>
  <span data-ttu-id="78568-103">Além das anotações discutidas nos tópicos anteriores nesta seção, o carregamento em massa de XML interpreta estas outras anotações:</span><span class="sxs-lookup"><span data-stu-id="78568-103">In addition to the annotations discussed in the previous topics in this section, XML Bulk Load interprets these other annotations, as follows:</span></span>  
  
 `sql:id-prefix`  
 <span data-ttu-id="78568-104">Se o esquema especificar prefixos aos dados XML, o carregamento em massa de XML removerá os prefixos antes de enviar os dados ao Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78568-104">If the schema specifies prefixes to the XML data, XML Bulk Load removes the prefixes before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:use-cdata`  
 <span data-ttu-id="78568-105">O carregamento em massa de XML lê o texto que é armazenado nas seções CDATA e os envia para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78568-105">XML Bulk Load reads the text that is stored in the CDATA sections and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:url-encode`  
 <span data-ttu-id="78568-106">O carregamento em massa de XML não dá suporte esta anotação.</span><span class="sxs-lookup"><span data-stu-id="78568-106">XML Bulk Load does not support this annotation.</span></span> <span data-ttu-id="78568-107">Por exemplo, você não pode especificar uma URL na entrada de dados XML e esperar que o carregamento em massa de XML leia os dados desse local para armazená-los no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="78568-107">For example, you cannot specify a URL in the XML data input and expect XML Bulk Load to read data from that location to store it in the database.</span></span>  
  
 `sql:is-mapping-schema`  
 <span data-ttu-id="78568-108">O carregamento em massa de XML não dá suporte esta anotação, nem dá suporte a `sql:id`.</span><span class="sxs-lookup"><span data-stu-id="78568-108">XML Bulk Load does not support this annotation, nor does it support `sql:id`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78568-109">O carregamento em massa de XML não dá suporte a esquemas de mapeamento embutidos.</span><span class="sxs-lookup"><span data-stu-id="78568-109">XML Bulk Load does not support inline mapping schemas.</span></span>  
  
 `sql:key-fields`  
 <span data-ttu-id="78568-110">O carregamento em massa de XML sempre ignora esta anotação.</span><span class="sxs-lookup"><span data-stu-id="78568-110">XML Bulk Load always ignores this annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78568-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="78568-111">See Also</span></span>  
 [<span data-ttu-id="78568-112">Interpretação de anotação &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="78568-112">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
  
  
