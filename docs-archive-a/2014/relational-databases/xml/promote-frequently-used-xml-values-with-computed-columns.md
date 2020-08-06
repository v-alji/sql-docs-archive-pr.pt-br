---
title: Promover valores XML usados frequentemente com colunas computadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- promoting properties [XML in SQL Server]
- property promotion [XML in SQL Server]
ms.assetid: f5111896-c2fd-4209-b500-f2baa45489ad
author: rothja
ms.author: jroth
ms.openlocfilehash: bfb83b7772ffd92eab7087db11e4c3ffd96afa47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681451"
---
# <a name="promote-frequently-used-xml-values-with-computed-columns"></a><span data-ttu-id="1811c-102">Promover valores XML frequentemente usados com colunas computadas</span><span class="sxs-lookup"><span data-stu-id="1811c-102">Promote Frequently Used XML Values with Computed Columns</span></span>
  <span data-ttu-id="1811c-103">Se as consultas forem feitas principalmente em um pequeno número de valores de elementos e atributos, você poderá desejar promover essas quantidades em colunas relacionais.</span><span class="sxs-lookup"><span data-stu-id="1811c-103">If queries are made principally on a small number of element and attribute values, you may want to promote those quantities into relational columns.</span></span> <span data-ttu-id="1811c-104">Isso é útil quando consultas são emitidas em uma pequena parte dos dados XML enquanto toda a instância XML é recuperada.</span><span class="sxs-lookup"><span data-stu-id="1811c-104">This is helpful when queries are issued on a small part of the XML data while the whole XML instance is retrieved.</span></span> <span data-ttu-id="1811c-105">A criação de um índice XML na coluna XML não é necessária.</span><span class="sxs-lookup"><span data-stu-id="1811c-105">Creating an XML index on the XML column is not required.</span></span> <span data-ttu-id="1811c-106">Em vez disso, a coluna promovida pode ser indexada.</span><span class="sxs-lookup"><span data-stu-id="1811c-106">Instead, the promoted column can be indexed.</span></span> <span data-ttu-id="1811c-107">As consultas devem ser escritas para usar a coluna promovida.</span><span class="sxs-lookup"><span data-stu-id="1811c-107">Queries must be written to use the promoted column.</span></span> <span data-ttu-id="1811c-108">Isto é, o otimizador de consultas não destina consultas novamente na coluna XML para a coluna promovida.</span><span class="sxs-lookup"><span data-stu-id="1811c-108">That is, the query optimizer does not target again the queries on the XML column to the promoted column.</span></span>  
  
 <span data-ttu-id="1811c-109">A coluna promovida pode ser uma coluna computada na mesma tabela ou ser uma coluna separada, mantida pelo usuário em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="1811c-109">The promoted column can be a computed column in the same table or it can be a separate, user-maintained column in a table.</span></span> <span data-ttu-id="1811c-110">Isso é suficiente quando valores singleton são promovidos de cada instância XML.</span><span class="sxs-lookup"><span data-stu-id="1811c-110">This is sufficient when singleton values are promoted from each XML instance.</span></span> <span data-ttu-id="1811c-111">No entanto para propriedades com vários valores, é necessário criar uma tabela separada para a propriedade, conforme descrito na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="1811c-111">However, for multi-valued properties, you have to create a separate table for the property, as described in the following section.</span></span>  
  
## <a name="computed-column-based-on-the-xml-data-type"></a><span data-ttu-id="1811c-112">Coluna computada com base no tipo de dados xml</span><span class="sxs-lookup"><span data-stu-id="1811c-112">Computed Column Based on the xml Data Type</span></span>  
 <span data-ttu-id="1811c-113">Uma coluna computada pode ser criada usando uma função definida pelo usuário que invoca `xml` métodos de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="1811c-113">A computed column can be created by using a user-defined function that invokes `xml` data type methods.</span></span> <span data-ttu-id="1811c-114">O tipo da coluna computada pode ser qualquer tipo SQL, inclusive XML.</span><span class="sxs-lookup"><span data-stu-id="1811c-114">The type of the computed column can be any SQL type, including XML.</span></span> <span data-ttu-id="1811c-115">Isso é ilustrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="1811c-115">This is illustrated in the following example.</span></span>  
  
### <a name="example-computed-column-based-on-the-xml-data-type-method"></a><span data-ttu-id="1811c-116">Exemplo: Coluna computada com base no método do tipo de dados xml</span><span class="sxs-lookup"><span data-stu-id="1811c-116">Example: Computed Column Based on the xml Data Type Method</span></span>  
 <span data-ttu-id="1811c-117">Crie a função definida pelo usuário para um número ISBN de livro:</span><span class="sxs-lookup"><span data-stu-id="1811c-117">Create the user-defined function for a book ISBN number:</span></span>  
  
```  
CREATE FUNCTION udf_get_book_ISBN (@xData xml)  
RETURNS varchar(20)  
BEGIN  
   DECLARE @ISBN   varchar(20)  
   SELECT @ISBN = @xData.value('/book[1]/@ISBN', 'varchar(20)')  
   RETURN @ISBN   
END  
```  
  
 <span data-ttu-id="1811c-118">Adicione uma coluna computada à tabela para o ISBN:</span><span class="sxs-lookup"><span data-stu-id="1811c-118">Add a computed column to the table for the ISBN:</span></span>  
  
```  
ALTER TABLE      T  
ADD   ISBN AS dbo.udf_get_book_ISBN(xCol)  
```  
  
 <span data-ttu-id="1811c-119">A coluna computada pode ser indexada de maneira normal.</span><span class="sxs-lookup"><span data-stu-id="1811c-119">The computed column can be indexed in the usual way.</span></span>  
  
### <a name="example-queries-on-a-computed-column-based-on-xml-data-type-methods"></a><span data-ttu-id="1811c-120">Exemplo: Consultas em uma coluna computada com base em métodos de tipo de dados xml</span><span class="sxs-lookup"><span data-stu-id="1811c-120">Example: Queries on a Computed Column Based on xml Data Type Methods</span></span>  
 <span data-ttu-id="1811c-121">Para obter o <`book`> cujo ISBN é 0-7356-1588-2:</span><span class="sxs-lookup"><span data-stu-id="1811c-121">To obtain the <`book`> whose ISBN is 0-7356-1588-2:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  xCol.exist('/book/@ISBN[. = "0-7356-1588-2"]') = 1  
```  
  
 <span data-ttu-id="1811c-122">A consulta na coluna XML pode ser reescrita para usar a coluna computada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1811c-122">The query on the XML column can be rewritten to use the computed column as follows:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  ISBN = '0-7356-1588-2'  
```  
  
 <span data-ttu-id="1811c-123">Você pode criar uma função definida pelo usuário para retornar o `xml` tipo de dados e uma coluna computada usando a função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="1811c-123">You can create a user-defined function to return the `xml` data type and a computed column by using the user-defined function.</span></span> <span data-ttu-id="1811c-124">No entanto não é possível criar um índice XML na coluna XML computada.</span><span class="sxs-lookup"><span data-stu-id="1811c-124">However, you cannot create an XML index on the computed, XML column.</span></span>  
  
## <a name="creating-property-tables"></a><span data-ttu-id="1811c-125">Criando tabelas de propriedades</span><span class="sxs-lookup"><span data-stu-id="1811c-125">Creating Property Tables</span></span>  
 <span data-ttu-id="1811c-126">Você pode desejar promover algumas das propriedades com vários valores de seus dados XML em uma ou mais tabelas, criar índices nessas tabelas e destinar suas consultas novamente para usá-las.</span><span class="sxs-lookup"><span data-stu-id="1811c-126">You may want to promote some of the multivalued properties from your XML data into one or more tables, create indexes on those tables, and target again your queries to use them.</span></span> <span data-ttu-id="1811c-127">Um cenário típico é aquele em que um pequeno número propriedades cobre a maior parte da carga de trabalho das consultas.</span><span class="sxs-lookup"><span data-stu-id="1811c-127">A typical scenario is one in which a small number of properties covers most of your query workload.</span></span> <span data-ttu-id="1811c-128">É possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1811c-128">You can do the following:</span></span>  
  
-   <span data-ttu-id="1811c-129">Crie uma ou mais tabelas para manter as propriedades com vários valores.</span><span class="sxs-lookup"><span data-stu-id="1811c-129">Create one or more tables to hold the multivalued properties.</span></span> <span data-ttu-id="1811c-130">Você pode descobrir que é conveniente armazenar uma propriedade por tabela e duplicar a chave primária da tabela base nas tabelas de propriedades para junção retroativa com a tabela base.</span><span class="sxs-lookup"><span data-stu-id="1811c-130">You may find it convenient to store one property per table and duplicate the primary key of the base table in the property tables for back joining with the base table.</span></span>  
  
-   <span data-ttu-id="1811c-131">Para manter a ordem relativa das propriedades, você precisa introduzir uma coluna separada para a ordem relativa.</span><span class="sxs-lookup"><span data-stu-id="1811c-131">If you want to maintain the relative order of the properties, you have to introduce a separate column for the relative order.</span></span>  
  
-   <span data-ttu-id="1811c-132">Crie gatilhos na coluna XML para manter as tabelas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="1811c-132">Create triggers on the XML column to maintain the property tables.</span></span> <span data-ttu-id="1811c-133">Dentro dos gatilhos, proceda de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="1811c-133">Within the triggers, do one of the following:</span></span>  
  
    -   <span data-ttu-id="1811c-134">Use `xml` métodos de tipo de dados, como **Nodes ()** e **Value ()**, para inserir e excluir linhas das tabelas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="1811c-134">Use `xml` data type methods, such as **nodes()** and **value()**, to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="1811c-135">Crie funções com valor de tabela de streaming no CLR (Common Language Runtime) para inserir e excluir linhas das tabelas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="1811c-135">Create streaming table-valued functions in the common language runtime (CLR) to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="1811c-136">Escreva consultas para acesso do SQL às tabelas de propriedades e para acesso do XML à coluna XML na tabela base, com junções entre as tabelas usando suas chaves primárias.</span><span class="sxs-lookup"><span data-stu-id="1811c-136">Write queries for SQL access to the property tables and for XML access to the XML column in the base table, with joins between the tables by using their primary key.</span></span>  
  
### <a name="example-create-a-property-table"></a><span data-ttu-id="1811c-137">Exemplo: Criar uma tabela de propriedades</span><span class="sxs-lookup"><span data-stu-id="1811c-137">Example: Create a Property Table</span></span>  
 <span data-ttu-id="1811c-138">Para ilustração, assuma que você quer promover o nome dos autores.</span><span class="sxs-lookup"><span data-stu-id="1811c-138">For illustration, assume that you want to promote the first name of the authors.</span></span> <span data-ttu-id="1811c-139">Os livros têm um ou mais autores, de forma que nome é uma propriedade com vários valores.</span><span class="sxs-lookup"><span data-stu-id="1811c-139">Books have one or more authors, so that first name is a multivalued property.</span></span> <span data-ttu-id="1811c-140">Cada nome é armazenado em uma linha separada de uma tabela de propriedades.</span><span class="sxs-lookup"><span data-stu-id="1811c-140">Each first name is stored in a separate row of a property table.</span></span> <span data-ttu-id="1811c-141">A chave primária da tabela base é duplicada na tabela de propriedades para junção retroativa.</span><span class="sxs-lookup"><span data-stu-id="1811c-141">The primary key of the base table is duplicated in the property table for back join.</span></span>  
  
```  
create table tblPropAuthor (propPK int, propAuthor varchar(max))  
```  
  
### <a name="example-create-a-user-defined-function-to-generate-a-rowset-from-an-xml-instance"></a><span data-ttu-id="1811c-142">Exemplo: Criar uma função definida pelo usuário para gerar um conjunto de linhas com base em uma instância XML</span><span class="sxs-lookup"><span data-stu-id="1811c-142">Example: Create a User-defined Function to Generate a Rowset from an XML Instance</span></span>  
 <span data-ttu-id="1811c-143">A função com valor de tabela a seguir, udf_XML2Table, aceita um valor de chave primária e uma instância XML.</span><span class="sxs-lookup"><span data-stu-id="1811c-143">The following table-valued function, udf_XML2Table, accepts a primary key value and an XML instance.</span></span> <span data-ttu-id="1811c-144">Ela recupera o nome de todos os autores dos elementos de <`book`> e retorna um conjunto de linhas de chave primária, primeiros pares de nomes.</span><span class="sxs-lookup"><span data-stu-id="1811c-144">It retrieves the first name of all authors of the <`book`> elements and returns a rowset of primary key, first name pairs.</span></span>  
  
```  
create function udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (propPK int, propAuthor varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
      select @pk, nref.value('.', 'varchar(max)')  
      from   @xCol.nodes('/book/author/first-name') R(nref)  
      return  
end  
```  
  
### <a name="example-create-triggers-to-populate-a-property-table"></a><span data-ttu-id="1811c-145">Exemplo: Criar gatilhos para popular uma tabela de propriedades</span><span class="sxs-lookup"><span data-stu-id="1811c-145">Example: Create Triggers to Populate a Property Table</span></span>  
 <span data-ttu-id="1811c-146">O gatilho de inserção insere linhas na tabela de propriedades:</span><span class="sxs-lookup"><span data-stu-id="1811c-146">The insert trigger inserts rows into the property table:</span></span>  
  
```  
create trigger trg_docs_INS on T for insert  
as  
      declare @wantedXML xml  
      declare @FK int  
      select @wantedXML = xCol from inserted  
      select @FK = PK from inserted  
  
   insert into tblPropAuthor  
   select * from dbo.udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="1811c-147">O gatilho de exclusão exclui as linhas da tabela de propriedades com base no valor da chave primária das linhas excluídas:</span><span class="sxs-lookup"><span data-stu-id="1811c-147">The delete trigger deletes the rows from the property table based on the primary key value of the deleted rows:</span></span>  
  
```  
create trigger trg_docs_DEL on T for delete  
as  
   declare @FK int  
   select @FK = PK from deleted  
   delete tblPropAuthor where propPK = @FK  
```  
  
 <span data-ttu-id="1811c-148">O gatilho de atualização exclui as linhas existentes da tabela de propriedades correspondentes à instância XML atualizada e insere novas linhas na tabela de propriedades:</span><span class="sxs-lookup"><span data-stu-id="1811c-148">The update trigger deletes the existing rows in the property table corresponding to the updated XML instance and inserts new rows into the property table:</span></span>  
  
```  
create trigger trg_docs_UPD  
on T  
for update  
as  
if update(xCol) or update(pk)  
begin  
      declare @FK int  
      declare @wantedXML xml  
      select @FK = PK from deleted  
      delete tblPropAuthor where propPK = @FK  
  
   select @wantedXML = xCol from inserted  
   select @FK = pk from inserted  
  
   insert into tblPropAuthor   
      select * from dbo.udf_XML2Table(@FK, @wantedXML)  
end  
```  
  
### <a name="example-find-xml-instances-whose-authors-have-the-same-first-name"></a><span data-ttu-id="1811c-149">Exemplo: Localizar instâncias XML cujos autores têm o mesmo nome</span><span class="sxs-lookup"><span data-stu-id="1811c-149">Example: Find XML Instances Whose Authors Have the Same First Name</span></span>  
 <span data-ttu-id="1811c-150">A consulta pode ser formada na coluna XML.</span><span class="sxs-lookup"><span data-stu-id="1811c-150">The query can be formed on the XML column.</span></span> <span data-ttu-id="1811c-151">Como alternativa, é possível pesquisar o nome "David" na tabela de propriedades e executar uma junção retroativa com a tabela base para retornar a instância XML.</span><span class="sxs-lookup"><span data-stu-id="1811c-151">Alternatively, it can search the property table for first name "David" and perform a back join with the base table to return the XML instance.</span></span> <span data-ttu-id="1811c-152">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1811c-152">For example:</span></span>  
  
```  
SELECT xCol   
FROM     T JOIN tblPropAuthor ON T.pk = tblPropAuthor.propPK  
WHERE    tblPropAuthor.propAuthor = 'David'  
```  
  
### <a name="example-solution-using-the-clr-streaming-table-valued-function"></a><span data-ttu-id="1811c-153">Exemplo: Solução usando a função com valor de tabela de streaming de CLR</span><span class="sxs-lookup"><span data-stu-id="1811c-153">Example: Solution Using the CLR Streaming Table-valued Function</span></span>  
 <span data-ttu-id="1811c-154">Esta solução é composta das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="1811c-154">This solution is made up of the following steps:</span></span>  
  
1.  <span data-ttu-id="1811c-155">Definir uma classe CLR, SqlReaderBase, que implementa ISqlReader e gera um streaming, saída com valor de tabela, aplicando uma expressão de caminho em uma instância XML.</span><span class="sxs-lookup"><span data-stu-id="1811c-155">Define a CLR class, SqlReaderBase, that implements ISqlReader and generates a streaming, table-valued output by applying a path expression on an XML instance.</span></span>  
  
2.  <span data-ttu-id="1811c-156">Crie um assembly e uma função definida pelo usuário de Transact-SQL para iniciar a classe CLR.</span><span class="sxs-lookup"><span data-stu-id="1811c-156">Create an assembly and a Transact-SQL user-defined function to start the CLR class.</span></span>  
  
3.  <span data-ttu-id="1811c-157">Defina os gatilhos de inserção, atualização e exclusão usando a função definida pelo usuário para manter uma tabela de propriedades.</span><span class="sxs-lookup"><span data-stu-id="1811c-157">Define the insert, update, and delete triggers by using the user-defined function to maintain a property tables.</span></span>  
  
 <span data-ttu-id="1811c-158">Para fazer isso, primeiro crie a função CLR de streaming.</span><span class="sxs-lookup"><span data-stu-id="1811c-158">To do this, you first create the streaming CLR function.</span></span> <span data-ttu-id="1811c-159">O `xml` tipo de dados é exposto como um SQLXML de classe gerenciada em ADO.net e dá suporte ao método **CreateReader ()** que retorna um XmlReader.</span><span class="sxs-lookup"><span data-stu-id="1811c-159">The `xml` data type is exposed as a managed class SqlXml in ADO.NET and supports the **CreateReader()** method that returns an XmlReader.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1811c-160">O código de exemplo nesta seção usa XPathDocument e XPathNavigator.</span><span class="sxs-lookup"><span data-stu-id="1811c-160">The example code in this section uses XPathDocument and XPathNavigator.</span></span> <span data-ttu-id="1811c-161">Isso força você a carregar todos os documentos XML na memória.</span><span class="sxs-lookup"><span data-stu-id="1811c-161">These force you to load all the XML documents into memory.</span></span> <span data-ttu-id="1811c-162">Se estiver usando código semelhante em seu aplicativo para processar vários documentos XML grandes, esse código não será escalável.</span><span class="sxs-lookup"><span data-stu-id="1811c-162">If you are using similar code in your application to process several large XML documents, this code is not scalable.</span></span> <span data-ttu-id="1811c-163">Em vez disso, mantenha as alocações de memória pequenas e use interfaces de streaming sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="1811c-163">Instead, keep memory allocations small and use streaming interfaces whenever possible.</span></span> <span data-ttu-id="1811c-164">Para obter mais informações sobre o desempenho, veja [Arquitetura da integração CLR](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span><span class="sxs-lookup"><span data-stu-id="1811c-164">For more information about performance, see [Architecture of CLR Integration](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span></span>  
  
```  
public class c_streaming_xml_tvf {  
   public static ISqlReader streaming_xml_tvf   
(SqlXml xmlDoc, string pathExpression) {  
      return (new TestSqlReaderBase (xmlDoc, pathExpression));  
   }  
}  
  
// Class that implements ISqlReader  
public class TestSqlReaderBase : ISqlReader {  
XPathNodeIterator m_iterator;           
   public SqlChars FirstName;  
// Metadata for current resultset  
private SqlMetaData[] m_rgSqlMetaData;        
  
   public TestSqlReaderBase (SqlXml xmlDoc, string pathExpression) {     
      // Variables for XPath navigation  
      XPathDocument xDoc;  
      XPathNavigator xNav;  
      XPathExpression xPath;  
  
      // Set sql metadata  
      m_rgSqlMetaData = new SqlMetaData[1];  
      m_rgSqlMetaData[0] = new SqlMetaData ("FirstName",    
SqlDbType.NVarChar,50);     
  
      //Set up the Navigator  
      if (!xmlDoc.IsNull)  
          xDoc = new XPathDocument (xmlDoc.CreateReader());  
      else  
          xDoc = new XPathDocument ();  
      xNav = xDoc.CreateNavigator();  
      xPath = xNav.Compile (pathExpression);  
      m_iterator = xNav.Select(xPath);  
   }  
   public bool Read() {  
      bool moreRows = true;  
      if (moreRows = m_iterator.MoveNext())  
         FirstName = new SqlChars (m_iterator.Current.Value);  
      return moreRows;  
   }  
}  
```  
  
 <span data-ttu-id="1811c-165">Em seguida, crie um assembly e uma função definida pelo usuário [!INCLUDE[tsql](../../includes/tsql-md.md)] , SQL_streaming_xml_tvf (não mostrada), que corresponda à função CLR, streaming_xml_tvf.</span><span class="sxs-lookup"><span data-stu-id="1811c-165">Next, create an assembly and a [!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined function, SQL_streaming_xml_tvf (not shown), that corresponds to the CLR function, streaming_xml_tvf.</span></span> <span data-ttu-id="1811c-166">A função definida pelo usuário é usada para definir a função com valor de tabela, CLR_udf_XML2Table, para geração do conjunto de linhas:</span><span class="sxs-lookup"><span data-stu-id="1811c-166">The user-defined function is used to define the table-valued function, CLR_udf_XML2Table, for rowset generation:</span></span>  
  
```  
create function CLR_udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (FK int, FirstName varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
   select @pk, FirstName   
   FROM   SQL_streaming_xml_tvf (@xCol, '/book/author/first-name')  
      return  
end  
```  
  
 <span data-ttu-id="1811c-167">Finalmente, defina gatilhos conforme mostrado no exemplo "Crie gatilhos para popular uma tabela de propriedades", mas substitua a função udf_XML2Table pela CLR_udf_XML2Table.</span><span class="sxs-lookup"><span data-stu-id="1811c-167">Finally, define triggers as shown in the example, "Create triggers to populate a property table", but replace udf_XML2Table with the CLR_udf_XML2Table function.</span></span> <span data-ttu-id="1811c-168">O gatilho de inserção é mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="1811c-168">The insert trigger is shown in the following example:</span></span>  
  
```  
create trigger CLR_trg_docs_INS on T for insert  
as  
   declare @wantedXML xml  
   declare @FK int  
   select @wantedXML = xCol from inserted  
   select @FK = PK from inserted  
  
   insert into tblPropAuthor  
      select *  
   from    dbo.CLR_udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="1811c-169">O gatilho de inserção é idêntico à versão de não CLR.</span><span class="sxs-lookup"><span data-stu-id="1811c-169">The delete trigger is identical to the non-CLR version.</span></span> <span data-ttu-id="1811c-170">No entanto o gatilho de atualização apenas substitui a função udf_XML2Table() pela CLR_udf_XML2Table().</span><span class="sxs-lookup"><span data-stu-id="1811c-170">However, the update trigger just replaces the function udf_XML2Table() with CLR_udf_XML2Table().</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1811c-171">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1811c-171">See Also</span></span>  
 [<span data-ttu-id="1811c-172">Usar XML em colunas computadas</span><span class="sxs-lookup"><span data-stu-id="1811c-172">Use XML in Computed Columns</span></span>](use-xml-in-computed-columns.md)  
  
  
