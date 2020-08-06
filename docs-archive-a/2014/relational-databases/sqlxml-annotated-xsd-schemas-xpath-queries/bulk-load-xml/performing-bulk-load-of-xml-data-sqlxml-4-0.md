---
title: Executando o carregamento em massa de dados XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML]
- bulk load [SQLXML]
- data insertions [SQLXML]
- SQLXML, bulk loading
- XSD schemas [SQLXML], XML Bulk Load
- XDR schemas [SQLXML], XML Bulk Load
- inserting data
ms.assetid: 3708b493-322e-4f3c-9b27-441d0c0ee346
author: rothja
ms.author: jroth
ms.openlocfilehash: ec540ff082b02fa43b9abd9f294752073eb68d5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678687"
---
# <a name="performing-bulk-load-of-xml-data-sqlxml-40"></a><span data-ttu-id="d8bc0-102">Executando o carregamento em massa de dados XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d8bc0-102">Performing Bulk Load of XML Data (SQLXML 4.0)</span></span>
  <span data-ttu-id="d8bc0-103">XML Bulk Load é um objeto COM autônomo que lhe permite carregar dados XML semiestruturados em tabelas do Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8bc0-103">XML Bulk Load is a standalone COM object that allows you to load semistructured XML data into Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8bc0-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d8bc0-104">In This Section</span></span>  
 [<span data-ttu-id="d8bc0-105">Introdução ao carregamento em massa XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d8bc0-105">Introduction to XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](introduction-to-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="d8bc0-106">Fornece informações gerais sobre o carregamento em massa de dados XML e o utilitário XML Bulk Load.</span><span class="sxs-lookup"><span data-stu-id="d8bc0-106">Provides general information about bulk loading XML data with the XML Bulk Load utility.</span></span> <span data-ttu-id="d8bc0-107">Os tópicos incluem streaming de dados XML e operações de carregamento em massa transacionadas e não transacionadas.</span><span class="sxs-lookup"><span data-stu-id="d8bc0-107">Topics include XML data streaming and transacted vs. nontransacted bulk load operations.</span></span>  
  
 [<span data-ttu-id="d8bc0-108">Processo de geração de registro &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d8bc0-108">Record Generation Process &#40;SQLXML 4.0&#41;</span></span>](record-generation-process-sqlxml-4-0.md)  
 <span data-ttu-id="d8bc0-109">Descreve o processo e as regras que geram os registros para o XML Bulk Load.</span><span class="sxs-lookup"><span data-stu-id="d8bc0-109">Describes the process and rules by which records are generated for XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="d8bc0-110">Interpretação de anotação &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d8bc0-110">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
 <span data-ttu-id="d8bc0-111">Descreve como o XML Bulk Load interpreta as anotações em esquemas XSD e XDR.</span><span class="sxs-lookup"><span data-stu-id="d8bc0-111">Describes how XML Bulk Load interprets annotations in XSD and XDR schemas.</span></span>  
  
 [<span data-ttu-id="d8bc0-112">SQL Server modelo de objeto de carregamento em massa XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d8bc0-112">SQL Server XML Bulk Load Object Model &#40;SQLXML 4.0&#41;</span></span>](sql-server-xml-bulk-load-object-model-sqlxml-4-0.md)  
 <span data-ttu-id="d8bc0-113">Descreve o objeto SQLXMLBulkLoad e seus métodos e propriedades.</span><span class="sxs-lookup"><span data-stu-id="d8bc0-113">Describes the SQLXMLBulkLoad object and its methods and properties.</span></span>  
  
 [<span data-ttu-id="d8bc0-114">Exemplos de carregamento em massa de XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d8bc0-114">XML Bulk Load Examples &#40;SQLXML 4.0&#41;</span></span>](xml-bulk-load-examples-sqlxml-4-0.md)  
 <span data-ttu-id="d8bc0-115">Fornece código de exemplo que usa o XML Bulk Load.</span><span class="sxs-lookup"><span data-stu-id="d8bc0-115">Provides example code that uses XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="d8bc0-116">Tipos de dados e comportamento de carregamento em massa XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d8bc0-116">Data Types and XML Bulk Load Behavior &#40;SQLXML 4.0&#41;</span></span>](data-types-and-xml-bulk-load-behavior-sqlxml-4-0.md)  
 <span data-ttu-id="d8bc0-117">Descreve o comportamento do XML Bulk Load com tipos diferentes no XSD e XDR.</span><span class="sxs-lookup"><span data-stu-id="d8bc0-117">Describes XML Bulk Load Behavior with different types in XSD and XDR.</span></span>  
  
 [<span data-ttu-id="d8bc0-118">Diretrizes e limitações do carregamento em massa XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d8bc0-118">Guidelines and Limitations of XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="d8bc0-119">Lista algumas questões às quais se deve estar atento ao se trabalhar com o XML Bulk Load.</span><span class="sxs-lookup"><span data-stu-id="d8bc0-119">Lists some issues to be aware of when working with XML Bulk Load.</span></span>  
  
  
