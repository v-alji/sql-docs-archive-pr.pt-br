---
title: Dados XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML [SQL Server]
- XML [SQL Server], about XML
ms.assetid: 6a1793c9-9856-485c-aac5-88fda62f61a8
author: rothja
ms.author: jroth
ms.openlocfilehash: 48ddec1de8492c86aecfd80ea960c4a01673c24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570553"
---
# <a name="xml-data-sql-server"></a><span data-ttu-id="919c4-102">Dados XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="919c4-102">XML Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="919c4-103">fornece uma plataforma avançada para o desenvolvimento de aplicativos avançados para gerenciamento de dados semi-estruturados.</span><span class="sxs-lookup"><span data-stu-id="919c4-103">provides a powerful platform for developing rich applications for semi-structured data management.</span></span> <span data-ttu-id="919c4-104">O suporte para XML é integrado em todos os componentes no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="919c4-104">Support for XML is integrated into all the components in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and includes the following:</span></span>  
  
-   <span data-ttu-id="919c4-105">O tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="919c4-105">The `xml` data type.</span></span> <span data-ttu-id="919c4-106">Os valores XML podem ser armazenados de modo nativo em uma coluna de tipo de dados `xml` que pode ser classificada por tipo de acordo com uma coleção de esquemas XML ou deixada sem-tipo.</span><span class="sxs-lookup"><span data-stu-id="919c4-106">XML values can be stored natively in an `xml` data type column that can be typed according to a collection of XML schemas, or left untyped.</span></span> <span data-ttu-id="919c4-107">É possível indexar a coluna XML.</span><span class="sxs-lookup"><span data-stu-id="919c4-107">You can index the XML column.</span></span>  
  
-   <span data-ttu-id="919c4-108">A capacidade de especificar uma consulta XQuery em dados XML armazenados em colunas e variáveis do tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="919c4-108">The ability to specify an XQuery query against XML data stored in columns and variables of the `xml` type.</span></span>  
  
-   <span data-ttu-id="919c4-109">Aprimoramentos no OPENROWSET para permitir carregamento em massa de dados XML.</span><span class="sxs-lookup"><span data-stu-id="919c4-109">Enhancements to OPENROWSET to allow bulk loading of XML data.</span></span>  
  
-   <span data-ttu-id="919c4-110">A cláusula de FOR XML, para recuperar dados relacionais no formato XML.</span><span class="sxs-lookup"><span data-stu-id="919c4-110">The FOR XML clause, to retrieve relational data in XML format.</span></span>  
  
-   <span data-ttu-id="919c4-111">A função OPENXML, para recuperar dados XML no formato relacional.</span><span class="sxs-lookup"><span data-stu-id="919c4-111">The OPENXML function, to retrieve XML data in relational format.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="919c4-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="919c4-112">In This Section</span></span>  
 [<span data-ttu-id="919c4-113">Tipos e colunas de dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="919c4-113">XML Data Type and Columns &#40;SQL Server&#41;</span></span>](xml-data-type-and-columns-sql-server.md)  
 [<span data-ttu-id="919c4-114">Índices XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="919c4-114">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
 [<span data-ttu-id="919c4-115">Coleções de esquemas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="919c4-115">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
 [<span data-ttu-id="919c4-116">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="919c4-116">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
 [<span data-ttu-id="919c4-117">OPENXML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="919c4-117">OPENXML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openxml-transact-sql)  
  
## <a name="related-content"></a><span data-ttu-id="919c4-118">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="919c4-118">Related Content</span></span>  
 [<span data-ttu-id="919c4-119">Exemplos de importação e exportação em massa de documentos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="919c4-119">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
 [<span data-ttu-id="919c4-120">Referência de linguagem XQuery &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="919c4-120">XQuery Language Reference &#40;SQL Server&#41;</span></span>](/sql/xquery/xquery-language-reference-sql-server)  
  
