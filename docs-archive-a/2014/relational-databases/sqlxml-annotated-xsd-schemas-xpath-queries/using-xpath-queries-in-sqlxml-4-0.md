---
title: Usando consultas XPath no SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML]
- annotated XSD schemas, XPath queries
- queries [SQLXML], XPath
- XML views [SQLXML]
ms.assetid: 7814d099-81ec-4fb8-894a-729cdbb5015a
author: rothja
ms.author: jroth
ms.openlocfilehash: 80d82513b22d2a50aedb37955a210dd33746db86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575738"
---
# <a name="using-xpath-queries-in-sqlxml-40"></a><span data-ttu-id="7139e-102">Usando consultas XPath no SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="7139e-102">Using XPath Queries in SQLXML 4.0</span></span>
  <span data-ttu-id="7139e-103">O suporte do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a esquemas XSD anotados permite criar exibições XML dos dados relacionais armazenados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7139e-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support for annotated XSD schemas allows you to create XML views of the relational data stored in the database.</span></span> <span data-ttu-id="7139e-104">Você pode usar um subconjunto da linguagem XPath para consultar as exibições XML criadas por um esquema XSD anotado.</span><span class="sxs-lookup"><span data-stu-id="7139e-104">You can use a subset of the XPath language to query the XML views created by an annotated XSD schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7139e-105">Para entender as consultas XPath no SQLXML 4.0, é necessário estar familiarizado com as exibições XML e os conceitos relacionados, como modelos e esquemas de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="7139e-105">To understand XPath queries in SQLXML 4.0, you must be familiar with XML views and related concepts such as templates and mapping schema.</span></span> <span data-ttu-id="7139e-106">Para obter mais informações, consulte [introdução aos esquemas XSD anotados &#40;SQLXML 4,0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="7139e-106">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="7139e-107">Para obter mais informações sobre XPath, consulte o padrão XPath definido pelo World Wide Web Consortium (W3C) em http://www.w3.org/TR/xpath .</span><span class="sxs-lookup"><span data-stu-id="7139e-107">For more information about XPath, see the XPath standard defined by the World Wide Web Consortium (W3C) at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7139e-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7139e-108">In This Section</span></span>  
 [<span data-ttu-id="7139e-109">Introdução ao uso de consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7139e-109">Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;</span></span>](introduction-to-using-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7139e-110">Fornece informações de introdução sobre consultas XPath no SQLXML 4.0, incluindo as funcionalidade com e sem-suporte da especificação W3C XPath.</span><span class="sxs-lookup"><span data-stu-id="7139e-110">Provides introductory information about XPath queries in SQLXML 4.0, including supported and unsupported functionality from the W3C XPath specification.</span></span>  
  
 [<span data-ttu-id="7139e-111">Especificando um caminho de local &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7139e-111">Specifying a Location Path &#40;SQLXML 4.0&#41;</span></span>](location-path/specifying-a-location-path-sqlxml-4-0.md)  
 <span data-ttu-id="7139e-112">Descreve como especificar caminhos de local em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="7139e-112">Describes how to specify location paths in XPath queries.</span></span>  
  
 [<span data-ttu-id="7139e-113">Consultas XPath de exemplo &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7139e-113">Sample XPath Queries &#40;SQLXML 4.0&#41;</span></span>](samples/sample-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7139e-114">Fornece consultas XPath de exemplo para o SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="7139e-114">Provides sample XPath queries for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="7139e-115">Tipos de dados XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7139e-115">XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="7139e-116">Descreve tipos de dados Xpath, que são significativamente diferentes dos tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e XSD.</span><span class="sxs-lookup"><span data-stu-id="7139e-116">Describes XPath data types, which are significantly different from those of both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7139e-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7139e-117">See Also</span></span>  
 [<span data-ttu-id="7139e-118">Formatação XML do lado do cliente &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7139e-118">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
