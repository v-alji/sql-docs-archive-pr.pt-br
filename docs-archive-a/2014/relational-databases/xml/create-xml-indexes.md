---
title: Criar índices XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- indexes [XML in SQL Server]
- XML indexes [SQL Server], creating
ms.assetid: 6ecac598-355d-4408-baf7-1b2e8d4cf7c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9e7800193222b8c9060fee1b247cc5585654cde4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684107"
---
# <a name="create-xml-indexes"></a><span data-ttu-id="d1e9b-102">Criar índices XML</span><span class="sxs-lookup"><span data-stu-id="d1e9b-102">Create XML Indexes</span></span>
  <span data-ttu-id="d1e9b-103">Este tópico descreve como criar índices XML primários e secundários.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-103">This topic describes how to create primary and secondary XML indexes.</span></span>  
  
## <a name="creating-a-primary-xml-index"></a><span data-ttu-id="d1e9b-104">Criando um índice XML primário</span><span class="sxs-lookup"><span data-stu-id="d1e9b-104">Creating a Primary XML Index</span></span>  
 <span data-ttu-id="d1e9b-105">Para criar um índice XML primário, use a instrução DDL [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1e9b-105">To create a primary XML index, use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement.</span></span> <span data-ttu-id="d1e9b-106">Nem todas as opções disponíveis para índices não XML têm suporte em índices XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-106">Not all options available for non-XML indexes are supported on XML indexes.</span></span>  
  
 <span data-ttu-id="d1e9b-107">Observe o seguinte ao criar um índice XML:</span><span class="sxs-lookup"><span data-stu-id="d1e9b-107">Note the following when you are creating an XML index:</span></span>  
  
-   <span data-ttu-id="d1e9b-108">Para criar um índice XML, a tabela que contém a coluna XML que está sendo indexada, chamada de tabela base, deve ter um índice clusterizado na chave primária.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-108">To create a primary XML index, the table that contains the XML column being indexed, called the base table, must have a clustered index on the primary key.</span></span> <span data-ttu-id="d1e9b-109">Isso garante que se a tabela base estiver particionada, o índice XML primário poderá ser particionado usando o mesmo esquema e função de particionamento.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-109">This makes sure that if the base table is partitioned, the primary XML index can be partitioned by using the same partitioning scheme and partitioning function.</span></span>  
  
-   <span data-ttu-id="d1e9b-110">Se existir um índice XML, a chave primária clusterizada da tabela não poderá ser modificada.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-110">If an XML index exists, the clustered, primary key of the table cannot be modified.</span></span> <span data-ttu-id="d1e9b-111">É necessário descartar todos os índices XML da tabela para modificar a chave primária.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-111">You will have to drop all XML indexes on the table before modifying the primary key.</span></span>  
  
-   <span data-ttu-id="d1e9b-112">Um índice XML primário pode ser criado em uma única coluna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-112">A primary XML index can be created on a single `xml` type column.</span></span> <span data-ttu-id="d1e9b-113">Não é possível criar nenhum outro tipo de índice com a coluna de tipo XML como uma coluna de chave.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-113">You cannot create any other type of index with the XML type column as a key column.</span></span> <span data-ttu-id="d1e9b-114">No entanto, é possível incluir a coluna de tipo `xml` L em um índice não XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-114">However, you can include the `xml` L type column in a non-XML index.</span></span> <span data-ttu-id="d1e9b-115">Cada coluna de tipo `xml` em uma tabela pode ter seu próprio índice XML primário.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-115">Each `xml` type column in a table can have its own primary XML index.</span></span> <span data-ttu-id="d1e9b-116">Porém, apenas um índice XML primário por coluna de tipo `xml` é permitido.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-116">However, only one primary XML index per `xml` type column is permitted.</span></span>  
  
-   <span data-ttu-id="d1e9b-117">Índices XML existem no mesmo namespace que índices não XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-117">XML indexes exist in the same namespace as non-XML indexes.</span></span> <span data-ttu-id="d1e9b-118">Portanto, não é possível ter um índice XML e um índice não XML na mesma tabela com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-118">Therefore, you cannot have an XML index and a non-XML index on the same table with the same name.</span></span>  
  
-   <span data-ttu-id="d1e9b-119">As opções IGNORE_DUP_KEY e ONLINE sempre estão definidas como OFF para índices XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-119">IGNORE_DUP_KEY and ONLINE options of are always set to OFF for XML indexes.</span></span> <span data-ttu-id="d1e9b-120">Essas opções podem ser especificadas com um valor de OFF.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-120">You can specify these options with a value of OFF.</span></span>  
  
-   <span data-ttu-id="d1e9b-121">As informações de particionamento ou de grupo de arquivos da tabela do usuário são aplicadas ao índice XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-121">The filegroup or partitioning information of the user table is applied to the XML index.</span></span> <span data-ttu-id="d1e9b-122">Usuários não podem especificá-las separadamente em um índice XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-122">Users cannot specify these separately on an XML index.</span></span>  
  
-   <span data-ttu-id="d1e9b-123">A opção de índice DROP_EXISTING pode descartar um índice XML primário e criar um novo índice XML primário ou descartar um índice XML secundário e criar um novo índice XML secundário.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-123">The DROP_EXISTING index option can drop a primary XML index and create a new primary XML index, or drop a secondary XML index and create a new secondary XML index.</span></span> <span data-ttu-id="d1e9b-124">No entanto, essa opção não pode descartar um índice XML secundário para criar um índice XML primário novo ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-124">However, this option cannot drop a secondary XML index to create a new primary XML index or vice versa.</span></span>  
  
-   <span data-ttu-id="d1e9b-125">Nomes de índice XML primário têm as mesmas restrições que nomes de exibição.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-125">Primary XML index names have the same restrictions as view names.</span></span>  
  
 <span data-ttu-id="d1e9b-126">Você não pode criar um índice XML em uma `xml` coluna de tipo em uma exibição, em uma variável com valor de **tabela** com `xml` colunas de tipo ou `xml` variáveis de tipo.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-126">You cannot create an XML index on an `xml` type column in a view, on a **table** valued variable with `xml` type columns, or `xml` type variables.</span></span>  
  
-   <span data-ttu-id="d1e9b-127">Para alterar uma coluna de tipo `xml` de XML sem-tipo para XML com tipo ou vice-versa, usando a opção ALTER TABLE ALTER COLUMN, nenhum índice XML deve existir na coluna.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-127">To change an `xml` type column from untyped to typed XML, or vice versa, by using the ALTER TABLE ALTER COLUMN option, no XML index on the column should exist.</span></span> <span data-ttu-id="d1e9b-128">Se existir um índice, ele deve ser descartado antes da tentativa de alterar o tipo de coluna.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-128">If one does exist, it must be dropped before the column type change is tried.</span></span>  
  
-   <span data-ttu-id="d1e9b-129">A opção ARITHABORT deve ser definida como ON quando um índice XML é criado.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-129">The option ARITHABORT must be set to ON when an XML index is created.</span></span> <span data-ttu-id="d1e9b-130">Para consultar, inserir, excluir ou atualizar valores na coluna XML usando métodos de tipo de dados XML, a mesma opção deve ser definida na conexão.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-130">To query, insert, delete, or update values in the XML column using XML data type methods, the same option must be set on the connection.</span></span> <span data-ttu-id="d1e9b-131">Caso contrário, haverá falha nos métodos de tipo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-131">If it is not, the XML data type methods will fail.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d1e9b-132">Informações sobre um índice XML podem ser localizadas em exibições do catálogo.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-132">Information about an XML index can be found in catalog views.</span></span> <span data-ttu-id="d1e9b-133">No entanto, não há suporte para **sp_helpindex** .</span><span class="sxs-lookup"><span data-stu-id="d1e9b-133">However, **sp_helpindex** is not supported.</span></span> <span data-ttu-id="d1e9b-134">Os exemplos fornecidos mais adiante neste tópico mostram como consultar as exibições do catálogo para localizar informações sobre índices XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-134">Examples provided later in this topic show how to query the catalog views to find XML index information.</span></span>  
  
 <span data-ttu-id="d1e9b-135">Ao criar ou recriar um índice XML primário em uma coluna de tipo de dados XML que contém valores de tipos de Esquema XML **xs:date** ou **xs:dateTime** (ou quaisquer subtipos desses tipos) que têm um ano menor que 1, haverá falha na criação do índice no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-135">When creating or recreating a primary XML index on an XML data type column that contains values of the XML Schema types **xs:date** or **xs:dateTime** (or any subtypes of these types) that have a year of less than 1, the index creation will fail in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="d1e9b-136">permitiu esses valores; portanto, este problema pode ocorrer durante a criação de índices em um banco de dados gerado no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1e9b-136">allowed these values, so this problem can occur when creating indexes in a database generated in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="d1e9b-137">Para obter mais informações, consulte [Comparar XML digitado com XML não digitado](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d1e9b-137">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
### <a name="example-creating-a-primary-xml-index"></a><span data-ttu-id="d1e9b-138">Exemplo: Criando um índice XML primário</span><span class="sxs-lookup"><span data-stu-id="d1e9b-138">Example: Creating a Primary XML Index</span></span>  
 <span data-ttu-id="d1e9b-139">A tabela T (pk INT PRIMARY KEY, xCol XML) com uma coluna XML sem-tipo é usada na maioria dos exemplos.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-139">Table T (pk INT PRIMARY KEY, xCol XML) with an untyped XML column is used in most of the examples.</span></span> <span data-ttu-id="d1e9b-140">Esses podem ser estendidos para XML com tipo de uma maneira direta.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-140">These can be extended to typed XML in a straightforward way.</span></span> <span data-ttu-id="d1e9b-141">Para simplificar, as consultas são descritas para instâncias de dados XML, conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="d1e9b-141">For simplicity, queries are described for XML data instances as shown in the following:</span></span>  
  
```  
<book genre="security" publicationdate="2002" ISBN="0-7356-1588-2">  
   <title>Writing Secure Code</title>  
   <author>  
      <first-name>Michael</first-name>  
      <last-name>Howard</last-name>  
   </author>  
   <author>  
      <first-name>David</first-name>  
      <last-name>LeBlanc</last-name>  
   </author>  
   <price>39.99</price>  
</book>  
```  
  
 <span data-ttu-id="d1e9b-142">A instrução a seguir cria um índice XML, chamado idx_xCol, na coluna XML xCol da tabela T:</span><span class="sxs-lookup"><span data-stu-id="d1e9b-142">The following statement creates an XML index, called idx_xCol, on the XML column xCol of table T:</span></span>  
  
```  
CREATE PRIMARY XML INDEX idx_xCol on T (xCol)  
```  
  
## <a name="creating-a-secondary-xml-index"></a><span data-ttu-id="d1e9b-143">Criando um índice XML secundário</span><span class="sxs-lookup"><span data-stu-id="d1e9b-143">Creating a Secondary XML Index</span></span>  
 <span data-ttu-id="d1e9b-144">Use a instrução DDL [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] para criar índices XML secundários e especificar o tipo do índice XML secundário desejado.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-144">Use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement to create secondary XML indexes and specify the type of the secondary XML index that you want.</span></span>  
  
 <span data-ttu-id="d1e9b-145">Observe o seguinte ao criar índices XML secundários:</span><span class="sxs-lookup"><span data-stu-id="d1e9b-145">Note the following when you are creating secondary XML indexes:</span></span>  
  
-   <span data-ttu-id="d1e9b-146">São permitidas todas as opções de indexação que se aplicam a um índice não clusterizado, exceto IGNORE_DUP_KEY e ONLINE, em índices XML secundários.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-146">All indexing options that apply to a nonclustered index, except IGNORE_DUP_KEY and ONLINE, are permitted on secondary XML indexes.</span></span> <span data-ttu-id="d1e9b-147">As duas opções sempre devem ser definidas como OFF para índices XML secundários.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-147">The two options must always be set to OFF for secondary XML indexes.</span></span>  
  
-   <span data-ttu-id="d1e9b-148">Os índices secundários são particionados exatamente como o índice XML primário.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-148">The secondary indexes are partitioned just like the primary XML index.</span></span>  
  
-   <span data-ttu-id="d1e9b-149">DROP_EXISTING pode descartar um índice secundário e criar outro índice secundário na tabela de usuário.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-149">DROP_EXISTING can drop a secondary index on the user table and create another secondary index on the user table.</span></span>  
  
 <span data-ttu-id="d1e9b-150">É possível consultar a exibição de catálogo **sys.xml_indexes** para recuperar informações do índice XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-150">You can query the **sys.xml_indexes** catalog view to retrieve XML index information.</span></span> <span data-ttu-id="d1e9b-151">Observe que a coluna **secondary_type_desc** na exibição de catálogo **sys.xml_indexes** fornece o tipo de índice secundário:</span><span class="sxs-lookup"><span data-stu-id="d1e9b-151">Note that the **secondary_type_desc** column in the **sys.xml_indexes** catalog view provides the type of secondary index:</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="d1e9b-152">Os valores retornados na coluna **secondary_type_desc** podem ser NULL, PATH, VALUE ou PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-152">The values returned in the **secondary_type_desc** column can be NULL, PATH, VALUE, or PROPERTY.</span></span> <span data-ttu-id="d1e9b-153">Para o índice XML primário, o valor retornado é NULL.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-153">For the primary XML index, the value returned is NULL.</span></span>  
  
### <a name="example-creating-secondary-xml-indexes"></a><span data-ttu-id="d1e9b-154">Exemplo: Criando índices XML secundários</span><span class="sxs-lookup"><span data-stu-id="d1e9b-154">Example: Creating Secondary XML Indexes</span></span>  
 <span data-ttu-id="d1e9b-155">O exemplo a seguir ilustra como são criados índices XML secundários.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-155">The following example illustrates how secondary XML indexes are created.</span></span> <span data-ttu-id="d1e9b-156">O exemplo também mostra informações sobre os índices XML criados.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-156">The example also shows information about the XML indexes that you created.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML);  
GO  
-- Create primary index.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol);  
GO  
-- Create secondary indexes (PATH, VALUE, PROPERTY).  
CREATE XML INDEX PIdx_T_XmlCol_PATH ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PATH;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_VALUE ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR VALUE;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_PROPERTY ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PROPERTY;  
GO  
```  
  
 <span data-ttu-id="d1e9b-157">É possível consultar o `sys.xml_indexes` para recuperar informações de índices XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-157">You can query the `sys.xml_indexes` to retrieve XML indexes information.</span></span> <span data-ttu-id="d1e9b-158">A coluna `secondary_type_desc` fornece o tipo de índice secundário.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-158">The `secondary_type_desc` column provides the secondary index type.</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="d1e9b-159">Também é possível consultar a exibição do catálogo para obter informações de índice.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-159">You can also query the catalog view for index information.</span></span>  
  
```  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T');  
```  
  
 <span data-ttu-id="d1e9b-160">É possível adicionar dados de exemplo e revisar as informações do índice XML.</span><span class="sxs-lookup"><span data-stu-id="d1e9b-160">You can add sample data and then review the XML index information.</span></span>  
  
```  
INSERT INTO T VALUES (1,  
'<doc id="123">  
<sections>  
<section num="2">  
<heading>Background</heading>  
</section>  
<section num="3">  
<heading>Sort</heading>  
</section>  
<section num="4">  
<heading>Search</heading>  
</section>  
</sections>  
</doc>');  
GO  
-- Check XML index information.  
SELECT *  
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, NULL, 'DETAILED');  
GO  
-- Space usage of primary XML index  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id  
FROM    sys.xml_indexes i   
WHERE   i.name = 'PIdx_T_XmlCol' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
--- Space usage of secondary XML index (for example PATH secondary index)  PIdx_T_XmlCol_PATH  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id   
FROM    sys.xml_indexes i   
WHERE  i.name = 'PIdx_T_XmlCol_PATH' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
  
-- Space usage of all secondary XML indexes for a particular table  
SELECT i.name, object_name(i.object_id), stats.*   
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, DEFAULT, 'DETAILED') stats  
JOIN sys.xml_indexes i ON (stats.object_id = i.object_id and stats.index_id = i.index_id)  
WHERE secondary_type is not null;  
-- Drop secondary indexes.  
DROP INDEX PIdx_T_XmlCol_PATH ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_VALUE ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_PROPERTY ON T;  
GO  
-- Drop primary index.  
DROP INDEX PIdx_T_XmlCol ON T;  
-- Drop table T.  
DROP TABLE T;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1e9b-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1e9b-161">See Also</span></span>  
 <span data-ttu-id="d1e9b-162">[Índices XML &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d1e9b-162">[XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span></span>  
 [<span data-ttu-id="d1e9b-163">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d1e9b-163">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
