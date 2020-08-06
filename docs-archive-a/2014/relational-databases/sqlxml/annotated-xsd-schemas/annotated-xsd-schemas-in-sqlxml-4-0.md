---
title: Esquemas XSD anotados no SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas
- SQLXML, annotated XSD schemas
- mapping schema [SQLXML]
- XSD schemas [SQLXML]
- XSD schemas [SQLXML], annotations
- schemas [SQLXML]
ms.assetid: eecd0d5f-d3dd-4d20-9586-19820410ad47
author: rothja
ms.author: jroth
ms.openlocfilehash: f97e01b0ade98edc432869c8772fbd4720df9a08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575729"
---
# <a name="annotated-xsd-schemas-in-sqlxml-40"></a><span data-ttu-id="d7217-102">Esquemas XSD anotados em SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="d7217-102">Annotated XSD Schemas in SQLXML 4.0</span></span>
  <span data-ttu-id="d7217-103">Esta seção fornece informações sobre como usar esquemas XSD anotados no SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="d7217-103">This section provides information about using annotated XSD schemas in SQLXML 4.0.</span></span> <span data-ttu-id="d7217-104">Em versões anteriores de SQLXML, uma funcionalidade semelhante era fornecida com os esquemas XDR (Dados XML reduzidos).</span><span class="sxs-lookup"><span data-stu-id="d7217-104">In previous versions of SQLXML, similar functionality was provided with XML-Data Reduced (XDR) schemas.</span></span> <span data-ttu-id="d7217-105">Esta seção também apresenta informações sobre XDR para aplicativos herdados.</span><span class="sxs-lookup"><span data-stu-id="d7217-105">This section also provides XDR information for legacy applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7217-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d7217-106">In This Section</span></span>  
 [<span data-ttu-id="d7217-107">Introdução aos esquemas XSD anotados &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d7217-107">Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](introduction-to-annotated-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="d7217-108">Fornece uma visão geral de esquemas XSD anotados em SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="d7217-108">Provides an overview of annotated XSD schemas in SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="d7217-109">Usando anotações em esquemas XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d7217-109">Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="d7217-110">Descreve como usar anotações em esquemas XSD em vários cenários e fornece exemplos.</span><span class="sxs-lookup"><span data-stu-id="d7217-110">Describes how to use annotations in XSD schemas in numerous scenarios, and provides examples.</span></span>  
  
 [<span data-ttu-id="d7217-111">Usando esquemas XSD anotados em consultas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d7217-111">Using Annotated XSD Schemas in Queries &#40;SQLXML 4.0&#41;</span></span>](using-annotated-xsd-schemas-in-queries-sqlxml-4-0.md)  
 <span data-ttu-id="d7217-112">Descreve como usar esquemas XSD anotados em consultas.</span><span class="sxs-lookup"><span data-stu-id="d7217-112">Describes how to use annotated XSD schemas in queries.</span></span>  
  
 [<span data-ttu-id="d7217-113">Convertendo esquemas XDR anotados em esquemas XSD equivalentes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d7217-113">Converting Annotated XDR Schemas to Equivalent XSD Schemas &#40;SQLXML 4.0&#41;</span></span>](converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="d7217-114">Descreve como converter esquemas XDR aos esquemas XSD equivalentes para SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="d7217-114">Describes how to convert XDR schemas to the equivalent XSD schemas for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="d7217-115">Esquemas XDR anotados &#40;preteridos no SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d7217-115">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
 <span data-ttu-id="d7217-116">Versões anteriores do SQLXML ofereciam suporte a anotações em esquemas XDR.</span><span class="sxs-lookup"><span data-stu-id="d7217-116">Previous versions of SQLXML supported annotations in XDR schemas.</span></span> <span data-ttu-id="d7217-117">Os esquemas XDR são substituídos no SQLXML 4.0, mas esta seção é fornecida como referência para aplicativos herdados.</span><span class="sxs-lookup"><span data-stu-id="d7217-117">Annotated XDR schemas are deprecated in SQLXML 4.0, but this section is provided as a reference for legacy applications.</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="d7217-118">Outros recursos</span><span class="sxs-lookup"><span data-stu-id="d7217-118">Other Resources</span></span>  
 <span data-ttu-id="d7217-119">Você pode encontrar mais informações sobre as linguagens XSD (XML Schema Definition), XPath (XML Path) e XSLT (Linguagem XSL Transformations) nos seguintes sites:</span><span class="sxs-lookup"><span data-stu-id="d7217-119">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="d7217-120">Esquema XML parte 0: Primer, recomendação do W3C (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="d7217-120">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="d7217-121">Esquema XML parte 1: estruturas, recomendação do W3C (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="d7217-121">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="d7217-122">Esquema XML parte 2: tipos de texto, recomendação do W3C (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="d7217-122">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="d7217-123">Linguagem de caminho XML (XPath) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="d7217-123">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="d7217-124">Transformações XSL (XSLT) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="d7217-124">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
  
