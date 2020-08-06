---
title: Remover índices XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- dropping indexes
- XML indexes [SQL Server], dropping
ms.assetid: 7591ebea-34af-4925-8553-b2adb5b487c2
author: rothja
ms.author: jroth
ms.openlocfilehash: b7d4621cf2182b4587b12665a1cfe10ddbe0db3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569236"
---
# <a name="drop-xml-indexes"></a><span data-ttu-id="05525-102">Descartar índices XML</span><span class="sxs-lookup"><span data-stu-id="05525-102">Drop XML Indexes</span></span>
  <span data-ttu-id="05525-103">A instrução [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] pode ser usada para remover índices primários ou secundários XML e não XML existentes.</span><span class="sxs-lookup"><span data-stu-id="05525-103">The [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be used to drop existing primary or secondary XML and non-XML indexes.</span></span> <span data-ttu-id="05525-104">No entanto nenhuma opção de DROP INDEX se aplica a índices XML.</span><span class="sxs-lookup"><span data-stu-id="05525-104">However, no options of DROP INDEX apply to XML indexes.</span></span> <span data-ttu-id="05525-105">Se você descartar o índice XML primário, qualquer índice secundário que estiver presente também será excluído.</span><span class="sxs-lookup"><span data-stu-id="05525-105">If you drop the primary XML index, any secondary indexes that are present are also deleted.</span></span>  
  
 <span data-ttu-id="05525-106">A sintaxe de DROP com *TableName.IndexName* está sendo desativada e não tem suporte para índices XML.</span><span class="sxs-lookup"><span data-stu-id="05525-106">The DROP syntax with *TableName.IndexName* is being phased out and is not supported for XML indexes.</span></span>  
  
## <a name="example-creating-and-dropping-a-primary-xml-index"></a><span data-ttu-id="05525-107">Exemplo: Criando e descartando um índice XML primário</span><span class="sxs-lookup"><span data-stu-id="05525-107">Example: Creating and Dropping a Primary XML Index</span></span>  
 <span data-ttu-id="05525-108">No exemplo a seguir, um índice XML é criado em um tipo de coluna `xml`.</span><span class="sxs-lookup"><span data-stu-id="05525-108">In the following example, an XML index is created on an `xml` type column.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create Primary XML index   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Verify the index creation.   
-- Note index type is 3 for xml indexes.  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'   
-- Drop the index.  
DROP INDEX PIdx_T_XmlCol ON T  
```  
  
 <span data-ttu-id="05525-109">Quando uma tabela é descartada, todos os índices XML que ela contém também são descartados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="05525-109">When a table is dropped, all the XML indexes on it are also automatically dropped.</span></span> <span data-ttu-id="05525-110">No entanto uma coluna XML não poderá ser descartada de uma tabela se existir um índice XML na coluna.</span><span class="sxs-lookup"><span data-stu-id="05525-110">However, an XML column cannot be dropped from a table if an XML index exists on the column.</span></span>  
  
 <span data-ttu-id="05525-111">No exemplo a seguir, um índice XML é criado em um tipo de coluna `xml`.</span><span class="sxs-lookup"><span data-stu-id="05525-111">In the following example, an XML index is created on an `xml` type column.</span></span> <span data-ttu-id="05525-112">Para obter mais informações, consulte [Comparar XML digitado com XML não digitado](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="05525-112">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
```  
CREATE TABLE TestTable(  
 Col1 int primary key,   
 Col2 xml (Production.ProductDescriptionSchemaCollection))   
GO  
```  
  
 <span data-ttu-id="05525-113">Agora, é possível criar um índice de XML primário na `Co12`.</span><span class="sxs-lookup"><span data-stu-id="05525-113">Now, you can create a primary XML index on `Co12`.</span></span>  
  
```  
CREATE PRIMARY XML INDEX PIdx_TestTable_Col2   
ON TestTable(Col2)  
GO  
```  
  
## <a name="example-creating-an-xml-index-by-using-the-drop_existing-index-option"></a><span data-ttu-id="05525-114">Exemplo: Criando um índice XML usando a opção de índice DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="05525-114">Example: Creating an XML Index by Using the DROP_EXISTING Index Option</span></span>  
 <span data-ttu-id="05525-115">No exemplo a seguir, um índice XML é criado em uma coluna (`XmlColx`).</span><span class="sxs-lookup"><span data-stu-id="05525-115">In the following example, an XML index is created on a column (`XmlColx`).</span></span> <span data-ttu-id="05525-116">Em seguida, outro índice XML com o mesmo nome é criado em uma coluna diferente (`XmlColy`).</span><span class="sxs-lookup"><span data-stu-id="05525-116">Then, another XML index with the same name is created on a different column, (`XmlColy`).</span></span> <span data-ttu-id="05525-117">Como a opção `DROP_EXISTING` está especificada, o índice XML existente em (`XmlColx)` ) é descartado e um novo índice XML em (`XmlColy`) é criado.</span><span class="sxs-lookup"><span data-stu-id="05525-117">Because the `DROP_EXISTING` option is specified, the existing XML index on (`XmlColx)` is dropped and a new XML index on (`XmlColy`) is created.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T(Col1 int primary key, XmlColx xml, XmlColy xml)  
GO  
-- Create XML index on XmlColx.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColx)  
GO  
-- Create same name XML index on XmlColy.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColy)   
WITH (DROP_EXISTING = ON)  
-- Verify the index is created on XmlColy.d.  
SELECT sc.name   
FROM   sys.xml_indexes si inner join sys.index_columns sic   
ON     sic.object_id=si.object_id and sic.index_id=si.index_id  
INNER  join sys.columns sc on sc.object_id=sic.object_id   
AND    sc.column_id=sic.column_id  
WHERE  si.name='PIdx_T_XmlCol'   
AND    si.object_id=object_id('T')  
```  
  
 <span data-ttu-id="05525-118">Essa consulta retorna o nome da coluna na qual o índice XML especificado é criado.</span><span class="sxs-lookup"><span data-stu-id="05525-118">This query returns the column name on which the specified XML index is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05525-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05525-119">See Also</span></span>  
 [<span data-ttu-id="05525-120">Índices XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="05525-120">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
