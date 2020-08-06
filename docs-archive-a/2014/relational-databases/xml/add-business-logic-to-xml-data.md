---
title: Adicionar lógica de negócios a dados XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- business logic [XML]
ms.assetid: 0877fb38-f1a2-43d8-86cf-4754be224dc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 5bf8e9edc36e9c420faa92f2db1a92c311194e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571879"
---
# <a name="add-business-logic-to-xml-data"></a><span data-ttu-id="dee98-102">Adicionar lógica de negócios a dados XML</span><span class="sxs-lookup"><span data-stu-id="dee98-102">Add Business Logic to XML Data</span></span>
  <span data-ttu-id="dee98-103">Sua lógica comercial pode ser adicionada a dados XML de vários modos:</span><span class="sxs-lookup"><span data-stu-id="dee98-103">Your business logic can be added to XML data in several ways:</span></span>  
  
-   <span data-ttu-id="dee98-104">Você pode gravar restrições de linha ou de coluna para impor restrições específicas ao domínio durante inserção e modificação de dados XML.</span><span class="sxs-lookup"><span data-stu-id="dee98-104">You can write row or column constraints to enforce domain-specific constraints during insertion and modification of XML data.</span></span>  
  
-   <span data-ttu-id="dee98-105">Você pode gravar um gatilho na coluna XML que seja disparado quando valores forem inseridos ou atualizados na coluna.</span><span class="sxs-lookup"><span data-stu-id="dee98-105">You can write a trigger on the XML column that fires when you insert or update values in the column.</span></span> <span data-ttu-id="dee98-106">O gatilho pode conter regras de validação específicas ao domínio ou popular tabelas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="dee98-106">The trigger can contain domain-specific validation rules or populate property tables.</span></span>  
  
-   <span data-ttu-id="dee98-107">O Mecanismo de Banco de Dados inclui a capacidade de executar código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="dee98-107">The Database Engine includes the ability execute managed code.</span></span> <span data-ttu-id="dee98-108">É possível usar essa integração de CLR (Common Language Runtime) para gravar funções em código gerenciado para as quais você passa valores XML, e usar recursos de processamento do XML fornecidos pelo namespace System.Xml.</span><span class="sxs-lookup"><span data-stu-id="dee98-108">You can use this common language runtime (CLR) integration to write functions in managed code to which you pass XML values, and use XML processing capabilities provided by the System.Xml namespace.</span></span> <span data-ttu-id="dee98-109">Um exemplo é aplicar a transformação XSL a dados XML.</span><span class="sxs-lookup"><span data-stu-id="dee98-109">An example is to apply XSL transformation to XML data.</span></span> <span data-ttu-id="dee98-110">Como alternativa, é possível desserializar o XML em uma ou mais classes gerenciadas e operar sobre elas usando código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="dee98-110">Alternatively, you can deserialize the XML into one or more managed classes and operate on them by using managed code.</span></span>  
  
-   <span data-ttu-id="dee98-111">É possível gravar funções e procedimentos armazenados Transact-SQL que começam o processamento na coluna XML para suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="dee98-111">You can write Transact-SQL stored procedures and functions that start the processing on the XML column for your business needs.</span></span>  
  
## <a name="example-applying-xsl-transformation"></a><span data-ttu-id="dee98-112">Exemplo: Aplicando a transformação XSL</span><span class="sxs-lookup"><span data-stu-id="dee98-112">Example: Applying XSL Transformation</span></span>  
 <span data-ttu-id="dee98-113">Considere uma função CLR **transformXML ()** que aceita uma `xml` instância de tipo de dados e uma transformação XSL armazenada em um arquivo, aplica a transformação aos dados XML e, em seguida, retorna o XML transformado no resultado.</span><span class="sxs-lookup"><span data-stu-id="dee98-113">Consider a CLR function **TransformXml()** that accepts an `xml` data type instance and an XSL transformation stored in a file, applies the transformation to the XML data, and then returns the transformed XML in the result.</span></span> <span data-ttu-id="dee98-114">O seguinte é um função em esqueleto escrita em C#:</span><span class="sxs-lookup"><span data-stu-id="dee98-114">Following is a skeleton function that is written in C#:</span></span>  
  
```  
public static SqlXml TransformXml (SqlXml XmlData, string xslPath) {  
   // Load XSL transformation  
   XslCompiledTransform xform = new XslCompiledTransform();  
   XPathDocument xslDoc = new XPathDocument (xslPath);  
   xform.Load(xslDoc);  
  
   // Load XML data   
   XPathDocument xDoc = new XPathDocument (XmlData.CreateReader());  
  
   // Return the transformed value  
   MemoryStream xsltResult = new MemoryStream();  
   xform.Transform(xDoc, null, xsltResult);  
   SqlXml retSqlXml = new SqlXml(xsltResult);  
   return (retSqlXml);  
}   
```  
  
 <span data-ttu-id="dee98-115">Após o assembly ser registrado e a função [!INCLUDE[tsql](../../includes/tsql-md.md)] definida pelo usuário ser criada, **SqlXslTransform()** correspondente a **TransformXml()** , a função pode ser invocada no Transact-SQL conforme mostrado na consulta a seguir:</span><span class="sxs-lookup"><span data-stu-id="dee98-115">After the assembly is registered and a user-defined [!INCLUDE[tsql](../../includes/tsql-md.md)] function is created, **SqlXslTransform()** corresponding to **TransformXml()**, the function can be invoked from Transact-SQL as shown in the following query:</span></span>  
  
```  
SELECT SqlXslTransform (xCol, 'C:\MyFile\xsltransform.xsl')  
FROM    T  
WHERE  xCol.exist('/book/title/text()[contains(.,"custom")]') =1;  
```  
  
 <span data-ttu-id="dee98-116">O resultado da consulta contém um conjunto de linhas do XML transformado.</span><span class="sxs-lookup"><span data-stu-id="dee98-116">The query result contains a rowset of the transformed XML.</span></span>  
  
 <span data-ttu-id="dee98-117">A integração CLR no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expande as possibilidades de decomposição de dados XML em tabelas ou promoção de propriedades e consultar dados XML usando classes gerenciadas no namespace System.Xml.</span><span class="sxs-lookup"><span data-stu-id="dee98-117">The CLR integration into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expands the possibilities for decomposing XML data into tables or property promotion, and querying XML data by using managed classes in the System.Xml namespace.</span></span> <span data-ttu-id="dee98-118">Para obter mais informações, veja [Dados XML &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dee98-118">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
  
