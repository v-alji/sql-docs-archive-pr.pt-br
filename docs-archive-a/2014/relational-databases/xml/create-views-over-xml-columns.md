---
title: Criar exibições sobre colunas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- views [XML in SQL Server]
ms.assetid: eb5f0439-1f69-49c2-8759-e59bda1633b7
author: rothja
ms.author: jroth
ms.openlocfilehash: bf06f1107cbf4875eb63fe6747775b5c5c04810c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684113"
---
# <a name="create-views-over-xml-columns"></a><span data-ttu-id="02dbd-102">Criar exibições sobre colunas XML</span><span class="sxs-lookup"><span data-stu-id="02dbd-102">Create Views over XML Columns</span></span>
  <span data-ttu-id="02dbd-103">É possível usar uma coluna de tipo `xml` para criar exibições.</span><span class="sxs-lookup"><span data-stu-id="02dbd-103">You can use an `xml` type column to create views.</span></span> <span data-ttu-id="02dbd-104">O exemplo a seguir cria uma exibição na qual o valor de uma coluna de tipo `xml` é recuperada usando o método `value()` do tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="02dbd-104">The following example creates a view in which the value from an `xml` type column is retrieved using the `value()` method of the `xml` data type.</span></span>  
  
```  
-- Create the table.  
CREATE TABLE T (  
    ProductID          int primary key,   
    CatalogDescription xml)  
GO  
-- Insert sample data.  
INSERT INTO T values(1,'<ProductDescription ProductID="1" ProductName="SomeName" />')  
GO  
-- Create view (note the value() method used to retrieve ProductName   
-- attribute value from the XML).  
CREATE VIEW MyView AS   
  SELECT ProductID,  
         CatalogDescription.value('(/ProductDescription/@ProductName)[1]', 'varchar(40)') AS PName  
  FROM T  
GO   
```  
  
 <span data-ttu-id="02dbd-105">Execute a consulta a seguir em relação à exibição:</span><span class="sxs-lookup"><span data-stu-id="02dbd-105">Execute the following query against the view:</span></span>  
  
```  
SELECT *   
FROM   MyView  
```  
  
 <span data-ttu-id="02dbd-106">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="02dbd-106">This is the result:</span></span>  
  
```  
ProductID   PName        
----------- ------------  
1           SomeName   
```  
  
 <span data-ttu-id="02dbd-107">Observe os seguintes pontos sobre o uso do tipo de dados `xml` para criar exibições:</span><span class="sxs-lookup"><span data-stu-id="02dbd-107">Note the following points about using the `xml` data type to create views:</span></span>  
  
-   <span data-ttu-id="02dbd-108">O tipo de dados xml pode ser criado em uma exibição materializada.</span><span class="sxs-lookup"><span data-stu-id="02dbd-108">The xml data type can be created in a materialized view.</span></span> <span data-ttu-id="02dbd-109">A exibição materializada não pode ser baseada em um método de tipo de dados xml.</span><span class="sxs-lookup"><span data-stu-id="02dbd-109">The materialized view cannot be based on an xml data type method.</span></span> <span data-ttu-id="02dbd-110">No entanto ela pode ser convertida em uma coleção de esquema XML diferente da coluna de tipo xml na tabela base.</span><span class="sxs-lookup"><span data-stu-id="02dbd-110">However, it can be cast to an XML schema collection that is different from the xml type column in the base table.</span></span>  
  
-   <span data-ttu-id="02dbd-111">O tipo de dados `xml` não pode ser usado em Exibições Particionadas Distribuídas.</span><span class="sxs-lookup"><span data-stu-id="02dbd-111">The `xml` data type cannot be used in Distributed Partitioned Views.</span></span>  
  
-   <span data-ttu-id="02dbd-112">Predicados SQL que são executados em relação à exibição não serão enviados por push para o XQuery da definição da exibição.</span><span class="sxs-lookup"><span data-stu-id="02dbd-112">SQL predicates running against the view will not be pushed into the XQuery of the view definition.</span></span>  
  
-   <span data-ttu-id="02dbd-113">Métodos de tipo de dados XML em uma exibição não são atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="02dbd-113">XML data type methods in a view are not updatable.</span></span>  
  
  
