---
title: Usando as classes gerenciadas SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXML Managed Classes, sample applications
- examples [SQLXML], managed classes
- Managed Classes [SQLXML], samples
ms.assetid: 3f021290-00ee-44e1-af4b-33d3ba8c6302
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 634a0e4110b13931201edd026ee95028cb94e859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681112"
---
# <a name="using-the-sqlxml-managed-classes"></a><span data-ttu-id="0b2cd-102">Usando as classes gerenciadas do SQLXML</span><span class="sxs-lookup"><span data-stu-id="0b2cd-102">Using the SQLXML Managed Classes</span></span>
  <span data-ttu-id="0b2cd-103">Esta seção fornece aplicativos de exemplo que demonstram como usar as classes gerenciadas do [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML.</span><span class="sxs-lookup"><span data-stu-id="0b2cd-103">This section provides sample applications that demonstrate how to use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML Managed Classes.</span></span>  
  
 <span data-ttu-id="0b2cd-104">Para obter informações sobre como acessar e modificar dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dentro do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework e sobre como usar DiffGrams para atualizar dados em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabelas, consulte [acessando a funcionalidade SQLXML no ambiente .net](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0b2cd-104">For information about accessing and modifying data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] within the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, and about using DiffGrams to update data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, see [Accessing SQLXML Functionality in the .NET Environment](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b2cd-105">Você também pode gravar aplicativos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio para o carregamento em massa de documentos XML usando o recurso XML Bulk Load.</span><span class="sxs-lookup"><span data-stu-id="0b2cd-105">You can also write [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio applications to bulk load XML documents by using XML Bulk Load.</span></span> <span data-ttu-id="0b2cd-106">Para obter mais informações, consulte [executando o carregamento em massa de dados XML &#40;SQLXML 4,0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="0b2cd-106">For more information, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span> <span data-ttu-id="0b2cd-107">Você deve adicionar uma referência à DLL do XML Bulk Load (Xblkld4.dll) ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0b2cd-107">You must add a reference to the XML Bulk Load DLL (Xblkld4.dll) in your application.</span></span> <span data-ttu-id="0b2cd-108">Esta é uma DLL COM para a qual o Visual Studio .NET cria automaticamente a biblioteca wrapper.</span><span class="sxs-lookup"><span data-stu-id="0b2cd-108">This is a COM DLL for which Visual Studio .NET automatically creates the wrapper library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b2cd-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0b2cd-109">In This Section</span></span>  
 [<span data-ttu-id="0b2cd-110">Executando consultas SQL &#40;classes gerenciadas SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="0b2cd-110">Executing SQL Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
  [<span data-ttu-id="0b2cd-111">Executando consultas SQL usando o método ExecuteXMLReader</span><span class="sxs-lookup"><span data-stu-id="0b2cd-111">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-sql-queries-by-using-the-executexmlreader-method.md)  
  [<span data-ttu-id="0b2cd-112">Processando XML no lado do cliente &#40;classes gerenciadas SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="0b2cd-112">Processing XML on the Client Side &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/processing-xml-on-the-client-side-sqlxml-managed-classes.md)  
  [<span data-ttu-id="0b2cd-113">Executando consultas XPath &#40;classes gerenciadas SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="0b2cd-113">Executing XPath Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-sqlxml-managed-classes.md)  
  [<span data-ttu-id="0b2cd-114">Executando consultas XPath com namespaces &#40;classes gerenciadas SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="0b2cd-114">Executing XPath Queries with Namespaces &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-with-namespaces-sqlxml-managed-classes.md)  
  [<span data-ttu-id="0b2cd-115">Executando os arquivos de modelo usando a propriedade CommandText</span><span class="sxs-lookup"><span data-stu-id="0b2cd-115">Executing Template Files by Using the CommandText Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandtext-property.md)  
  [<span data-ttu-id="0b2cd-116">Executando os arquivos de modelo usando a propriedade CommandStream</span><span class="sxs-lookup"><span data-stu-id="0b2cd-116">Executing Template Files by Using the CommandStream Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandstream-property.md)  
  [<span data-ttu-id="0b2cd-117">Aplicando um XSL Transformation &#40;classes gerenciadas SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="0b2cd-117">Applying an XSL Transformation &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/applying-an-xsl-transformation-sqlxml-managed-classes.md)  
  
