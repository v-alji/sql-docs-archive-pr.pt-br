---
title: 'Exemplo: Especificando a diretiva XMLTEXT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XMLTEXT directive
ms.assetid: e78008ec-51e8-4fd1-b86f-1058a781de17
author: rothja
ms.author: jroth
ms.openlocfilehash: d14299ad3e989c6600434b857a650fbbddd7a590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582333"
---
# <a name="example-specifying-the-xmltext-directive"></a><span data-ttu-id="8c9ef-102">Exemplo: Especificando a diretiva XMLTEXT</span><span class="sxs-lookup"><span data-stu-id="8c9ef-102">Example: Specifying the XMLTEXT Directive</span></span>
  <span data-ttu-id="8c9ef-103">Este exemplo ilustra como dados na coluna de estouro são resolvidos usando a diretiva `XMLTEXT` em uma instrução `SELECT` no modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-103">This example illustrates how data in the overflow column is addressed by using the `XMLTEXT` directive in a `SELECT` statement using EXPLICIT mode.</span></span>  
  
 <span data-ttu-id="8c9ef-104">Considere a tabela `Person` .</span><span class="sxs-lookup"><span data-stu-id="8c9ef-104">Consider the `Person` table.</span></span> <span data-ttu-id="8c9ef-105">Esta tabela tem uma coluna `Overflow` que armazena a parte não consumida do documento XML.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-105">This table has an `Overflow` column that stores the unconsumed part of the XML document.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE TABLE Person(PersonID varchar(5), PersonName varchar(20), Overflow nvarchar(200));  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
   ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P">content</SomeTag>');  
```  
  
 <span data-ttu-id="8c9ef-106">Essa consulta recupera colunas da tabela `Person` .</span><span class="sxs-lookup"><span data-stu-id="8c9ef-106">This query retrieves columns from the `Person` table.</span></span> <span data-ttu-id="8c9ef-107">Para a coluna `Overflow` , *AttributeName* não é especificado, mas *directive* é definida como `XMLTEXT` , como parte do fornecimento de um nome de coluna da tabela universal.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-107">For the `Overflow` column, *AttributeName* is not specified, but *directive* is set to `XMLTEXT` as part of providing a universal table column name.</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEST] -- No AttributeName; XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="8c9ef-108">No documento XML resultante:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-108">In the resulting XML document:</span></span>  
  
-   <span data-ttu-id="8c9ef-109">Como *AttributeName* não está especificado para a coluna `Overflow` e a diretiva `xmltext` está especificada, os atributos no elemento <`overflow`> são acrescentados à lista de atributos do elemento <`Parent`> de fechamento.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-109">Because *AttributeName* is not specified for the `Overflow` column and the `xmltext` directive is specified, the attributes in the <`overflow`> element are appended to the attribute list of the enclosing <`Parent`> element.</span></span>  
  
-   <span data-ttu-id="8c9ef-110">Como o atributo `PersonID` no elemento <`xmltext`> entra em conflito com o atributo `PersonID` recuperado no mesmo nível de elemento, o atributo no elemento <`xmltext`> é ignorado, mesmo que `PersonID` seja NULL.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-110">Because the `PersonID`attribute in the <`xmltext`> element conflicts with the `PersonID` attribute retrieved on the same element level, the attribute in the <`xmltext`> element is ignored, even if `PersonID` is NULL.</span></span> <span data-ttu-id="8c9ef-111">Geralmente, um atributo substitui um atributo do mesmo nome no estouro.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-111">Generally, an attribute overrides an attribute of the same name in the overflow.</span></span>  
  
 <span data-ttu-id="8c9ef-112">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-112">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">content</Parent>`  
  
 <span data-ttu-id="8c9ef-113">Se os dados de estouro tiverem subelementos e a mesma consulta for especificada, os subelementos na coluna `Overflow` serão adicionados como os subelementos do elemento <`Parent`> de circunscrição.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-113">If the overflow data has subelements and the same query is specified, the subelements in the `Overflow` column are added as the subelements of the enclosing <`Parent`> element.</span></span>  
  
 <span data-ttu-id="8c9ef-114">Por exemplo, altere os dados na tabela `Person` para que a coluna `Overflow` agora tenha subelementos.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-114">For example, change the data in the `Person` table so that the `Overflow` column now has subelements.</span></span>  
  
```  
USE tempdb;  
GO  
TRUNCATE TABLE Person;  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
    ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P"><name>PersonName</name></SomeTag>');  
```  
  
 <span data-ttu-id="8c9ef-115">Se a mesma consulta for executada, os subelementos no elemento <`xmltext`> serão adicionados como subelementos do elemento <`Parent`> de circunscrição:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-115">If the same query is executed, the subelements in the <`xmltext`> element are added as subelements of the enclosing <`Parent`> element:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEXT] -- no AttributeName, XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="8c9ef-116">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-116">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `</Parent>`  
  
 <span data-ttu-id="8c9ef-117">Se *AttributeName* for especificado com a diretiva `xmltext`, os atributos do elemento <`overflow`> serão adicionados como atributos dos subelementos do elemento <`Parent`> de circunscrição.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-117">If *AttributeName* is specified with the `xmltext` directive, the attributes of the <`overflow`> element are added as attributes of the subelements of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="8c9ef-118">O nome especificado para *AttributeName* torna-se o nome do subelemento.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-118">The name specified for *AttributeName* becomes the name of the subelement.</span></span>  
  
 <span data-ttu-id="8c9ef-119">Nesta consulta, *AttributeName*, <`overflow`>, é especificado junto com a `xmltext` diretiva:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-119">In this query, *AttributeName*, <`overflow`>, is specified together with the `xmltext` directive:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!overflow!XMLTEXT] -- Overflow is AttributeName  
                      -- XMLTEXT is a directive  
FROM Person  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="8c9ef-120">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-120">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe">`  
  
 `<overflow attr1="data">content</overflow>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe">`  
  
 `<overflow attr2="data" />`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe">`  
  
 `<overflow attr3="data" PersonID="P">`  
  
 `<name>PersonName</name>`  
  
 `</overflow>`  
  
 `</Parent>`  
  
 <span data-ttu-id="8c9ef-121">Neste elemento de consulta, *directive* está especificada para o atributo `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="8c9ef-121">In this query element, *directive* is specified for `PersonName` attribute.</span></span> <span data-ttu-id="8c9ef-122">Isso resulta na adição de `PersonName` como um subelemento do elemento <`Parent`> de circunscrição.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-122">This results in `PersonName` being added as a subelement of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="8c9ef-123">Os atributos do <`xmltext`> ainda estão anexados ao elemento <`Parent`> de circunscrição.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-123">The attributes of the <`xmltext`> are still appended to the enclosing <`Parent`> element.</span></span> <span data-ttu-id="8c9ef-124">O conteúdo do elemento e subelementos de <`overflow`> são pré-anexados a outros subelementos dos elementos <`Parent`> de circunscrição.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-124">The contents of the <`overflow`> element, subelements, are prepended to the other subelements of the enclosing <`Parent`> elements.</span></span>  
  
```  
SELECT 1      AS Tag, NULL as parent,  
       PersonID   AS [Parent!1!PersonID],  
       PersonName AS [Parent!1!PersonName!element], -- element directive  
       Overflow   AS [Parent!1!!XMLTEXT]  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="8c9ef-125">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-125">This is the result:</span></span>  
  
 `<Parent PersonID="P1" attr1="data">content<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" attr2="data">`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 <span data-ttu-id="8c9ef-126">Se os dados da coluna `XMLTEXT` contiverem atributos no elemento raiz, esses atributos não serão mostrados no esquema de dados XML e o analisador MSXML não validará o fragmento do documento XML resultante.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-126">If the `XMLTEXT` column data contains attributes on the root element, these attributes are not shown in the XML data schema and the MSXML parser does not validate the resulting XML document fragment.</span></span> <span data-ttu-id="8c9ef-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-127">For example:</span></span>  
  
```  
SELECT 1 AS Tag,  
       0 ASParent,  
       N'<overflow a="1"/>' AS 'overflow!1!!xmltext'  
FOR XML EXPLICIT, xmldata;  
```  
  
 <span data-ttu-id="8c9ef-128">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="8c9ef-128">This is the result.</span></span> <span data-ttu-id="8c9ef-129">Observe que no esquema retornado, o atributo de estouro `a` não será encontrado no esquema:</span><span class="sxs-lookup"><span data-stu-id="8c9ef-129">Note that in the returned schema, the overflow attribute `a` is missing from the schema:</span></span>  
  
 `<Schema name="Schema2"`  
  
 `xmlns="urn:schemas-microsoft-com:xml-data"`  
  
 `xmlns:dt="urn:schemas-microsoft-com:datatypes">`  
  
 `<ElementType name="overflow" content="mixed" model="open">`  
  
 `</ElementType>`  
  
 `</Schema>`  
  
 `<overflow xmlns="x-schema:#Schema2" a="1">`  
  
 `</overflow>`  
  
## <a name="see-also"></a><span data-ttu-id="8c9ef-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8c9ef-130">See Also</span></span>  
 [<span data-ttu-id="8c9ef-131">Usar o modo EXPLICIT com FOR XML</span><span class="sxs-lookup"><span data-stu-id="8c9ef-131">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
