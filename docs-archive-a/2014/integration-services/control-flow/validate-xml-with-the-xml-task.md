---
title: Validar XML com a Tarefa XML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- XML validation
- XML, validating
ms.assetid: 224fc025-c21f-4d43-aa9d-5ffac337f9b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 633a269f53c85353c956b33bff8fd3af518dad56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568708"
---
# <a name="validate-xml-with-the-xml-task"></a><span data-ttu-id="488f2-102">Validate XML with the XML Task</span><span class="sxs-lookup"><span data-stu-id="488f2-102">Validate XML with the XML Task</span></span>
  <span data-ttu-id="488f2-103">Valide documentos XML e obtenha saída de erros completa habilitando a propriedade `ValidationDetails` da tarefa XML.</span><span class="sxs-lookup"><span data-stu-id="488f2-103">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span>

 <span data-ttu-id="488f2-104">A captura de tela a seguir mostra o **Editor da Tarefa XML** com as configurações necessárias para a validação de XML com a saída de erros.</span><span class="sxs-lookup"><span data-stu-id="488f2-104">The following screen shot shows the **XML Task Editor** with the settings required for XML validation with rich error output.</span></span>

 <span data-ttu-id="488f2-105">![Propriedades da tarefa XML no Editor da Tarefa XML](../media/xmltaskproperties.jpg "Propriedades da tarefa XML no Editor da Tarefa XML")</span><span class="sxs-lookup"><span data-stu-id="488f2-105">![XML task properties in the XML Task Editor](../media/xmltaskproperties.jpg "XML task properties in the XML Task Editor")</span></span>

 <span data-ttu-id="488f2-106">Antes da disponibilidade da propriedade `ValidationDetails`, a validação do XML pela tarefa XML retornava apenas um resultado true ou false, sem informações sobre erros ou suas localizações.</span><span class="sxs-lookup"><span data-stu-id="488f2-106">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="488f2-107">Agora, quando você define `ValidationDetails` como true, o arquivo de saída contém informações detalhadas sobre cada erro, incluindo o número de linha e a posição.</span><span class="sxs-lookup"><span data-stu-id="488f2-107">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="488f2-108">Você pode usar essas informações para entender, localizar e corrigir erros em documentos XML.</span><span class="sxs-lookup"><span data-stu-id="488f2-108">You can use this information to understand, locate, and fix errors in XML documents.</span></span>

 <span data-ttu-id="488f2-109">A funcionalidade de validação de XML é facilmente dimensionada para documentos XML e grandes números de erros.</span><span class="sxs-lookup"><span data-stu-id="488f2-109">The XML validation functionality scales easily for large XML documents and large numbers of errors.</span></span> <span data-ttu-id="488f2-110">Como o arquivo de saída é em formato XML, você pode consultar e analisar a saída.</span><span class="sxs-lookup"><span data-stu-id="488f2-110">Since the output file itself is in XML format, you can query and analyze the output.</span></span> <span data-ttu-id="488f2-111">Por exemplo, se a saída contiver um grande número de erros, você poderá agrupar os erros usando uma consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] , conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="488f2-111">For example, if the output contains a large number of errors, you can group the errors by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, as described in this topic.</span></span>

> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="488f2-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) introduziu a `ValidationDetails` propriedade no [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="488f2-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="488f2-113">A propriedade também está disponível no [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] e no SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="488f2-113">The property is also available in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>

## <a name="sample-output-for-xml-thats-valid"></a><span data-ttu-id="488f2-114">Exemplo de saída de XML válida</span><span class="sxs-lookup"><span data-stu-id="488f2-114">Sample output for XML that's valid</span></span>
 <span data-ttu-id="488f2-115">Veja um arquivo de saída de exemplo com os resultados da validação para um arquivo XML válido.</span><span class="sxs-lookup"><span data-stu-id="488f2-115">Here is a sample output file with validation results for a valid XML file.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>true</result>
        <errors>0</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:27:22.087</startTime>
        <endTime>2015-05-28T10:29:07.007</endTime>
        <xmlFile>d:\Temp\TestData.xml</xmlFile>
        <xsdFile>d:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages />
</root>
```

## <a name="sample-output-for-xml-thats-not-valid"></a><span data-ttu-id="488f2-116">Exemplo de saída de XML que não é válido</span><span class="sxs-lookup"><span data-stu-id="488f2-116">Sample output for XML that's not valid</span></span>
 <span data-ttu-id="488f2-117">Veja um arquivo de saída de exemplo com os resultados de validação para um arquivo XML que contém um pequeno número de erros.</span><span class="sxs-lookup"><span data-stu-id="488f2-117">Here is a sample output file with validation results for an XML file that contains a small number of errors.</span></span> <span data-ttu-id="488f2-118">O texto dos elementos \<error> foi encapsulado para facilitar a leitura.</span><span class="sxs-lookup"><span data-stu-id="488f2-118">The text of the \<error> elements has been wrapped for readability.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>false</result>
        <errors>2</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:45:09.538</startTime>
        <endTime>2015-05-28T10:45:09.558</endTime>
        <xmlFile>C:\Temp\TestData.xml</xmlFile>
        <xsdFile>C:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages>
        <error line="5" position="26">The 'ApplicantRole' element is invalid - The value 'wer3' is invalid
    according to its datatype 'ApplicantRoleType' - The Enumeration constraint failed.</error>
        <error line="16" position="28">The 'Phone' element is invalid - The value 'we3056666666' is invalid
     according to its datatype 'phone' - The Pattern constraint failed.</error>
    </messages>
</root>
```

## <a name="analyze-xml-validation-output-with-a-transact-sql-query"></a><span data-ttu-id="488f2-119">Analisar a saída de validação de XML com uma consulta Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="488f2-119">Analyze XML validation output with a Transact-SQL query</span></span>
 <span data-ttu-id="488f2-120">Se o resultado da validação do XML contiver um grande número de erros, você poderá usar uma consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] para carregar a saída no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="488f2-120">If the output of XML validation contains a large number of errors, you can use a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query to load the output in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="488f2-121">Em seguida, você pode analisar a lista de erros com todos os recursos da linguagem T-SQL, incluindo WHERE, GROUP BY, ORDER BY, JOIN e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="488f2-121">Then you can analyze the error list with all the capabilities of the T-SQL language including WHERE, GROUP BY, ORDER BY, JOIN, and so forth.</span></span>

```sql
DECLARE @xml XML;

SELECT @xml = XmlDoc   
FROM OPENROWSET (BULK N'C:\Temp\XMLValidation_2016-02-212T10-41-00.xml', SINGLE_BLOB) AS Tab(XmlDoc);

-- Query # 1, flat list of errors
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT * FROM rs;
-- WHERE error LIKE '%whatever_string%'

-- Query # 2, count of errors grouped by the error message
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT COALESCE(error,'Total # of errors:') AS [error], COUNT(*) AS [counter]
FROM rs
GROUP BY GROUPING SETS ((error), ())
ORDER BY 2 DESC, COALESCE(error, 'Z');

```

 <span data-ttu-id="488f2-122">Veja o resultado no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] da consulta do segundo exemplo mostrada no texto anterior.</span><span class="sxs-lookup"><span data-stu-id="488f2-122">Here is the result in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] of the second sample query shown in the preceding text.</span></span>

 <span data-ttu-id="488f2-123">![Consulta para agrupar erros de XML no Management Studio](../media/queryforxmlerrors.jpg "Consulta para agrupar erros de XML no Management Studio")</span><span class="sxs-lookup"><span data-stu-id="488f2-123">![Query to group XML errors in Management Studio](../media/queryforxmlerrors.jpg "Query to group XML errors in Management Studio")</span></span>

## <a name="see-also"></a><span data-ttu-id="488f2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="488f2-124">See Also</span></span>
 <span data-ttu-id="488f2-125">[XML Task](xml-task.md) [Editor da tarefa XML da tarefa XML &#40;página Geral&#41;](../xml-task-editor-general-page.md)</span><span class="sxs-lookup"><span data-stu-id="488f2-125">[XML Task](xml-task.md) [XML Task Editor &#40;General Page&#41;](../xml-task-editor-general-page.md)</span></span>


