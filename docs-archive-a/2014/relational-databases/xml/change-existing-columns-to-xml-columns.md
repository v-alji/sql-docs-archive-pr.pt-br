---
title: Alterar as colunas existentes para colunas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- tables [XML]
ms.assetid: 0d951424-9862-41fe-bd46-127f1c059bcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 32447851fcfe2a54143a028a94539532bba6708d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569247"
---
# <a name="change-existing-columns-to-xml-columns"></a><span data-ttu-id="fca71-102">Converter colunas existentes em colunas XML</span><span class="sxs-lookup"><span data-stu-id="fca71-102">Change Existing Columns to XML Columns</span></span>
  <span data-ttu-id="fca71-103">A instrução ALTER TABLE oferece suporte ao tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="fca71-103">The ALTER TABLE statement supports the `xml` data type.</span></span> <span data-ttu-id="fca71-104">Por exemplo, é possível alterar qualquer coluna de tipo cadeia de caracteres para o tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="fca71-104">For example, you can alter any string type column to the `xml` data type.</span></span> <span data-ttu-id="fca71-105">Observe que nesses casos os documentos contidos na coluna devem estar bem formados.</span><span class="sxs-lookup"><span data-stu-id="fca71-105">Note that in these cases, the documents contained in the column must be well formed.</span></span> <span data-ttu-id="fca71-106">Além disso, se você estiver alterando o tipo da coluna de cadeia de caracteres para xml com tipo, os documentos da coluna serão validados em relação aos esquemas XSD especificados.</span><span class="sxs-lookup"><span data-stu-id="fca71-106">Also, if you are changing the type of the column from string to typed xml, the documents in the column are validated against the specified XSD schemas.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 nvarchar(max))  
GO  
INSERT INTO T   
VALUES (1, '<Root><Product ProductID="1"/></Root>')  
GO  
ALTER TABLE T   
ALTER COLUMN Col2 xml  
GO  
```  
  
 <span data-ttu-id="fca71-107">É possível alterar uma coluna de tipo `xml` de XML sem-tipo para XML com tipo.</span><span class="sxs-lookup"><span data-stu-id="fca71-107">You can change an `xml` type column from untyped XML to typed XML.</span></span> <span data-ttu-id="fca71-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fca71-108">For example:</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T   
values (1, '<p1:ProductDescription ProductModelID="1"   
xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
            </p1:ProductDescription>')  
GO   
-- Make it a typed xml column by specifying a schema collection.  
ALTER TABLE T   
ALTER COLUMN Col2 xml (Production.ProductDescriptionSchemaCollection)  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="fca71-109">O script será executado no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] porque a coleção de esquema XML, `Production.ProductDescriptionSchemaCollection`, é criada como parte do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fca71-109">The script will run against [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, because the XML schema collection, `Production.ProductDescriptionSchemaCollection`, is created as part of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="fca71-110">No exemplo anterior, todas as instâncias armazenadas na coluna são validadas e classificadas nos esquemas XSD na coleção especificada.</span><span class="sxs-lookup"><span data-stu-id="fca71-110">In the previous example, all the instances stored in the column are validated and typed against the XSD schemas in the specified collection.</span></span> <span data-ttu-id="fca71-111">Se a coluna contiver uma ou mais instâncias XML inválidas em relação ao esquema especificado, haverá falha na instrução `ALTER TABLE` e você não poderá alterar a coluna de XML sem-tipo para XML com tipo.</span><span class="sxs-lookup"><span data-stu-id="fca71-111">If the column contains one or more XML instances that are invalid with regard to the specified schema, the `ALTER TABLE` statement will fail and you will not be able to change your untyped XML column into typed XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fca71-112">Se uma tabela for grande, a modificação de uma coluna de tipo `xml` poderá ser dispendiosa.</span><span class="sxs-lookup"><span data-stu-id="fca71-112">If a table is large, modifying an `xml` type column can be costly.</span></span> <span data-ttu-id="fca71-113">Isso ocorre porque a boa formação de cada documento deve ser verificada e o XML com tipo também deve ser validado.</span><span class="sxs-lookup"><span data-stu-id="fca71-113">This is because each document must be checked for being well formed and, for typed XML, must also be validated.</span></span>  
  
 <span data-ttu-id="fca71-114">Para obter mais informações sobre XML com tipo, consulte [Comparar XML com e sem tipo](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fca71-114">For more information about typed XML, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
  
