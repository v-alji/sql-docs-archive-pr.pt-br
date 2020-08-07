---
title: Índices XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- deleting indexes
- secondary indexes [XML in SQL Server]
- xml data type [SQL Server], indexes
- dropping indexes
- PATH index
- DROP_EXISTING clause
- XML [SQL Server], indexes
- primary indexes [XML in SQL Server]
- indexes [SQL Server], XML
- XML indexes [SQL Server], secondary
- BLOBs, XML indexes
- disabling indexes
- XML indexes [SQL Server], modifying
- XML indexes [SQL Server]
- XML indexes [SQL Server], primary
- modifying indexes
- XML indexes [SQL Server], dropping
- VALUE index
- XML indexes [SQL Server], xml data type
- PROPERTY index
- XML indexes [SQL Server], creating
ms.assetid: f5c9209d-b3f3-4543-b30b-01365a5e7333
author: rothja
ms.author: jroth
ms.openlocfilehash: bf9a33bc18790bf8821d778746a708f78bbb3d8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575679"
---
# <a name="xml-indexes-sql-server"></a><span data-ttu-id="e9cf3-102">Índices XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e9cf3-102">XML Indexes (SQL Server)</span></span>
  <span data-ttu-id="e9cf3-103">Índices XML podem ser criados em colunas de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-103">XML indexes can be created on `xml` data type columns.</span></span> <span data-ttu-id="e9cf3-104">Eles indexam todas as marcas, valores e caminhos através das instâncias XML na coluna e se beneficiam do desempenho das consultas.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-104">They index all tags, values and paths over the XML instances in the column and benefit query performance.</span></span> <span data-ttu-id="e9cf3-105">Seu aplicativo pode se beneficiar de um índice XML nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-105">Your application may benefit from an XML index in the following situations:</span></span>  
  
-   <span data-ttu-id="e9cf3-106">Consultas em colunas XML são comuns em sua carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-106">Queries on XML columns are common in your workload.</span></span> <span data-ttu-id="e9cf3-107">O custo da manutenção de índices XML durante a modificação de dados deve ser considerado.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-107">XML index maintenance cost during data modification must be considered.</span></span>  
  
-   <span data-ttu-id="e9cf3-108">Seus valores XML são relativamente grandes e as partes recuperadas são relativamente pequenas.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-108">Your XML values are relatively large and the retrieved parts are relatively small.</span></span> <span data-ttu-id="e9cf3-109">A construção de índices evita a análise de todos os dados em tempo de execução e beneficia pesquisas de índice para processamento eficiente de consultas.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-109">Building the index avoids parsing the whole data at run time and benefits index lookups for efficient query processing.</span></span>  
  
 <span data-ttu-id="e9cf3-110">Índices XML se encaixam nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-110">XML indexes fall into the following categories:</span></span>  
  
-   <span data-ttu-id="e9cf3-111">Índice XML primário</span><span class="sxs-lookup"><span data-stu-id="e9cf3-111">Primary XML index</span></span>  
  
-   <span data-ttu-id="e9cf3-112">Índice XML secundário</span><span class="sxs-lookup"><span data-stu-id="e9cf3-112">Secondary XML index</span></span>  
  
 <span data-ttu-id="e9cf3-113">O primeiro índice na coluna de tipo `xml` deve ser o índice XML primário.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-113">The first index on the `xml` type column must be the primary XML index.</span></span> <span data-ttu-id="e9cf3-114">Usando o índice XML primário, os seguintes tipos de índices secundários são compatíveis: PATH, VALUE e PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-114">Using the primary XML index, the following types of secondary indexes are supported: PATH, VALUE, and PROPERTY.</span></span> <span data-ttu-id="e9cf3-115">Dependendo do tipo de consulta, esses índices secundários podem ajudar a melhorar o desempenho de consultas.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-115">Depending on the type of queries, these secondary indexes might help improve query performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9cf3-116">Não é possível criar ou modificar um índice XML a menos que as opções do banco de dados estejam definidas corretamente para trabalhar com o tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-116">You cannot create or modify an XML index unless the database options are set correctly for working with the `xml` data type.</span></span> <span data-ttu-id="e9cf3-117">Para obter mais informações, veja [Usar a pesquisa de texto completo com colunas XML](use-full-text-search-with-xml-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e9cf3-117">For more information, see [Use Full-Text Search with XML Columns](use-full-text-search-with-xml-columns.md).</span></span>  
  
 <span data-ttu-id="e9cf3-118">Instâncias XML são armazenadas em colunas de tipo `xml` como BLOBs (objetos binários grandes).</span><span class="sxs-lookup"><span data-stu-id="e9cf3-118">XML instances are stored in `xml` type columns as large binary objects (BLOBs).</span></span> <span data-ttu-id="e9cf3-119">Essas instâncias XML podem ser grandes e a representação binária armazenada de instâncias de tipo de dados `xml` pode ser de até 2 GB.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-119">These XML instances can be large, and the stored binary representation of `xml` data type instances can be up to 2 GB.</span></span> <span data-ttu-id="e9cf3-120">Sem um índice, esses objetos binários grandes são fragmentados em tempo de execução para avaliar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-120">Without an index, these binary large objects are shredded at run time to evaluate a query.</span></span> <span data-ttu-id="e9cf3-121">Essa fragmentação pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-121">This shredding can be time-consuming.</span></span> <span data-ttu-id="e9cf3-122">Por exemplo, considere a consulta abaixo:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-122">For example, consider the following query:</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS "PD")  
  
SELECT CatalogDescription.query('  
  /PD:ProductDescription/PD:Summary  
') as Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist ('/PD:ProductDescription/@ProductModelID[.="19"]') = 1  
```  
  
 <span data-ttu-id="e9cf3-123">Para selecionar as instâncias XML que atendem à condição na cláusula `WHERE` , o BLOB (objeto binário grande) XML em cada linha da tabela `Production.ProductModel` é fragmentado em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-123">To select the XML instances that satisfy the condition in the `WHERE` clause, the XML binary large object (BLOB) in each row of table `Production.ProductModel` is shredded at run time.</span></span> <span data-ttu-id="e9cf3-124">Em seguida, a expressão `(/PD:ProductDescription/@ProductModelID[.="19"]`) no método `exist()` é avaliada.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-124">Then, the expression `(/PD:ProductDescription/@ProductModelID[.="19"]`) in the `exist()` method is evaluated.</span></span> <span data-ttu-id="e9cf3-125">Essa fragmentação em tempo de execução pode ser dispendiosa dependendo do tamanho e do número de instâncias armazenadas na coluna.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-125">This run-time shredding can be costly, depending on the size and number of instances stored in the column.</span></span>  
  
 <span data-ttu-id="e9cf3-126">Se a consulta de BLOBs XML for comum no ambiente do seu aplicativo, a indexação de colunas de tipo `xml` ajudará.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-126">If querying XML binary large objects (BLOBs) is common in your application environment, it helps to index the `xml` type columns.</span></span> <span data-ttu-id="e9cf3-127">No entanto há um custo associado à manutenção do índice durante a modificação de dados.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-127">However, there is a cost associated with maintaining the index during data modification.</span></span>  
  
## <a name="primary-xml-index"></a><span data-ttu-id="e9cf3-128">Índice XML primário</span><span class="sxs-lookup"><span data-stu-id="e9cf3-128">Primary XML Index</span></span>  
 <span data-ttu-id="e9cf3-129">O índice XML primário indexa todos os valores, marcas e caminhos dentro das instâncias XML em uma coluna XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-129">The primary XML index indexes all tags, values, and paths within the XML instances in an XML column.</span></span> <span data-ttu-id="e9cf3-130">Para criar um índice XML, a tabela que contém a coluna XML deve ter um índice clusterizado na chave primária da tabela.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-130">To create a primary XML index, the table in which the XML column occurs must have a clustered index on the primary key of the table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e9cf3-131">usa essa chave primária para correlacionar linhas no índice XML primário com linhas na tabela que contém a coluna XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-131">uses this primary key to correlate rows in the primary XML index with rows in the table that contains the XML column.</span></span>  
  
 <span data-ttu-id="e9cf3-132">Um índice XML primário é uma representação fragmentada e persistente dos BLOBs XML na coluna de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-132">The primary XML index is a shredded and persisted representation of the XML BLOBs in the `xml` data type column.</span></span> <span data-ttu-id="e9cf3-133">Para cada BLOB (objeto binário grande) XML na coluna, o índice cria várias linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-133">For each XML binary large object (BLOB) in the column, the index creates several rows of data.</span></span> <span data-ttu-id="e9cf3-134">O número de linhas no índice é aproximadamente igual ao número de nós no objeto binário grande XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-134">The number of rows in the index is approximately equal to the number of nodes in the XML binary large object.</span></span> <span data-ttu-id="e9cf3-135">Quando uma consulta recupera a instância XML completa, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece a instância da coluna XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-135">When a query retrieves the full XML instance, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the instance from the XML column.</span></span> <span data-ttu-id="e9cf3-136">As consultas dentro de instâncias XML usam o índice XML primário e podem retornar valores escalares ou subárvores XML usando o próprio índice.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-136">Queries within XML instances use the primary XML index, and can return scalar values or XML subtrees by using the index itself.</span></span>  
  
 <span data-ttu-id="e9cf3-137">Cada linha armazena as seguintes informações de nó:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-137">Each row stores the following node information:</span></span>  
  
-   <span data-ttu-id="e9cf3-138">Nome da marca, como um nome de atributo ou elemento.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-138">Tag name such as an element or attribute name.</span></span>  
  
-   <span data-ttu-id="e9cf3-139">Valor do nó.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-139">Node value.</span></span>  
  
-   <span data-ttu-id="e9cf3-140">Tipo de nó, como um nó de elemento, nó de atributo ou nó de texto.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-140">Node type such as an element node, attribute node, or text node.</span></span>  
  
-   <span data-ttu-id="e9cf3-141">Informações de ordem do documento representada por um identificador de nó interno.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-141">Document order information, represented by an internal node identifier.</span></span>  
  
-   <span data-ttu-id="e9cf3-142">Caminho de cada nó para a raiz da árvore XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-142">Path from each node to the root of the XML tree.</span></span> <span data-ttu-id="e9cf3-143">Essa coluna é pesquisada para expressões de caminho na consulta.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-143">This column is searched for path expressions in the query.</span></span>  
  
-   <span data-ttu-id="e9cf3-144">Chave primária da tabela base.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-144">Primary key of the base table.</span></span> <span data-ttu-id="e9cf3-145">A chave primária da tabela base é duplicada no índice XML primário para uma junção retroativa com a tabela base, e o número máximo de colunas na chave primária da tabela base é limitado a 15.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-145">The primary key of the base table is duplicated in the primary XML index for a back join with the base table, and the maximum number of columns in the primary key of the base table is limited to 15.</span></span>  
  
 <span data-ttu-id="e9cf3-146">Essas informações de nó são usadas para avaliar e construir resultados XML para uma consulta especificada.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-146">This node information is used to evaluate and construct XML results for a specified query.</span></span> <span data-ttu-id="e9cf3-147">Para fins de otimização, as informações de nome da marca e de tipo de nó são codificadas como valores inteiros e a coluna Path usa a mesma codificação.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-147">For optimization purposes, the tag name and the node type information are encoded as integer values, and the Path column uses the same encoding.</span></span> <span data-ttu-id="e9cf3-148">Além disso, caminhos são armazenados em ordem inversa para permitir correspondência de caminhos quando apenas o sufixo do caminho é conhecido.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-148">Also, paths are stored in reverse order to allow matching paths when only the path suffix is known.</span></span> <span data-ttu-id="e9cf3-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-149">For example:</span></span>  
  
-   <span data-ttu-id="e9cf3-150">`//ContactRecord/PhoneNumber` em que apenas as duas últimas etapas são conhecidas</span><span class="sxs-lookup"><span data-stu-id="e9cf3-150">`//ContactRecord/PhoneNumber` where only the last two steps are known</span></span>  
  
 <span data-ttu-id="e9cf3-151">OU</span><span class="sxs-lookup"><span data-stu-id="e9cf3-151">OR</span></span>  
  
-   <span data-ttu-id="e9cf3-152">`/Book/*/Title` em que o caractere curinga (`*`) é especificado no meio da expressão.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-152">`/Book/*/Title` where the wildcard character (`*`) is specified in the middle of the expression.</span></span>  
  
 <span data-ttu-id="e9cf3-153">O processador de consultas usa índice XML primário para consultas que envolvem [Métodos de tipo de dados xml](/sql/t-sql/xml/xml-data-type-methods) e retorna valores escalares ou as subárvores XML do próprio índice primário.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-153">The query processor uses the primary XML index for queries that involve [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) and returns either scalar values or the XML subtrees from the primary index itself.</span></span> <span data-ttu-id="e9cf3-154">(Esse índice armazena todas as informações necessárias para reconstruir a instância XML.)</span><span class="sxs-lookup"><span data-stu-id="e9cf3-154">(This index stores all the necessary information to reconstruct the XML instance.)</span></span>  
  
 <span data-ttu-id="e9cf3-155">Por exemplo, a consulta a seguir retorna informações resumidas armazenadas na `CatalogDescription``xml` coluna Type da `ProductModel` tabela.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-155">For example, the following query returns summary information stored in the `CatalogDescription``xml` type column in the `ProductModel` table.</span></span> <span data-ttu-id="e9cf3-156">A consulta retorna informações de <`Summary`> apenas para modelos de produto cuja descrição de catálogo também armazena a descrição de <`Features`>.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-156">The query returns <`Summary`> information only for product models whose catalog description also stores the <`Features`> description.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS "PD")SELECT CatalogDescription.query('  /PD:ProductDescription/PD:Summary') as ResultFROM Production.ProductModelWHERE CatalogDescription.exist ('/PD:ProductDescription/PD:Features') = 1  
```  
  
 <span data-ttu-id="e9cf3-157">Com relação ao índice XML primário, em vez de fragmentar cada instância de objeto binário grande XML na tabela base, as linhas no índice que correspondem a cada objeto binário grande XML são pesquisadas sequencialmente para a expressão especificada no método `exist()` .</span><span class="sxs-lookup"><span data-stu-id="e9cf3-157">With regard to the primary XML index, instead of shredding each XML binary large object instance in the base table, the rows in the index that correspond to each XML binary large object are searched sequentially for the expression specified in the `exist()` method.</span></span> <span data-ttu-id="e9cf3-158">Se o caminho for encontrado na coluna Path no índice, o elemento <`Summary`> juntamente com suas subárvores será recuperado do índice XML primário e convertido em um objeto binário grande XML como o resultado do método `query()`.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-158">If the path is found in the Path column in the index, the <`Summary`> element together with its subtrees is retrieved from the primary XML index and converted into an XML binary large object as the result of the `query()` method.</span></span>  
  
 <span data-ttu-id="e9cf3-159">Observe que o índice XML primário não é usado ao recuperar uma instância XML completa.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-159">Note that the primary XML index is not used when retrieving a full XML instance.</span></span> <span data-ttu-id="e9cf3-160">Por exemplo, a consulta a seguir recupera da tabela toda a instância XML que descreve as instruções de fabricação para um modelo de produto específico.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-160">For example, the following query retrieves from the table the whole XML instance that describes the manufacturing instructions for a specific product model.</span></span>  
  
```  
USE AdventureWorks2012;SELECT InstructionsFROM Production.ProductModel WHERE ProductModelID=7;  
```  
  
## <a name="secondary-xml-indexes"></a><span data-ttu-id="e9cf3-161">Índices XML secundários</span><span class="sxs-lookup"><span data-stu-id="e9cf3-161">Secondary XML Indexes</span></span>  
 <span data-ttu-id="e9cf3-162">Para melhorar o desempenho da pesquisa, você pode criar índices XML secundários.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-162">To enhance search performance, you can create secondary XML indexes.</span></span> <span data-ttu-id="e9cf3-163">Um índice XML primário deve existir para que seja possível criar índices secundários.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-163">A primary XML index must first exist before you can create secondary indexes.</span></span> <span data-ttu-id="e9cf3-164">Estes são os tipos:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-164">These are the types:</span></span>  
  
-   <span data-ttu-id="e9cf3-165">Índice XML secundário PATH</span><span class="sxs-lookup"><span data-stu-id="e9cf3-165">PATH secondary XML index</span></span>  
  
-   <span data-ttu-id="e9cf3-166">Índice XML secundário VALUE</span><span class="sxs-lookup"><span data-stu-id="e9cf3-166">VALUE secondary XML index</span></span>  
  
-   <span data-ttu-id="e9cf3-167">Índice XML secundário PROPERTY</span><span class="sxs-lookup"><span data-stu-id="e9cf3-167">PROPERTY secondary XML index</span></span>  
  
 <span data-ttu-id="e9cf3-168">A seguir estão algumas diretrizes para criação de um ou mais índices secundários:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-168">Following are some guidelines for creating one or more secondary indexes:</span></span>  
  
-   <span data-ttu-id="e9cf3-169">Se sua carga de trabalho usar expressões de caminho significativamente em colunas XML, o índice XML secundário PATH provavelmente acelerará sua carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-169">If your workload uses path expressions significantly on XML columns, the PATH secondary XML index is likely to speed up your workload.</span></span> <span data-ttu-id="e9cf3-170">O caso mais comum é o uso do método **exist()** em colunas XML na cláusula WHERE do Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-170">The most common case is the use of the **exist()** method on XML columns in the WHERE clause of Transact-SQL.</span></span>  
  
-   <span data-ttu-id="e9cf3-171">Se sua carga de trabalho recuperar vários valores de instâncias XML individuais usando expressões de caminho, caminhos de clustering dentro de cada instância XML no índice PROPERTY poderão ser úteis.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-171">If your workload retrieves multiple values from individual XML instances by using path expressions, clustering paths within each XML instance in the PROPERTY index may be helpful.</span></span> <span data-ttu-id="e9cf3-172">Isso normalmente ocorre em um cenário de recipiente de propriedades quando as propriedades de um objeto são buscadas e seu valor de chave primária é conhecido.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-172">This scenario typically occurs in a property bag scenario when properties of an object are fetched and its primary key value is known.</span></span>  
  
-   <span data-ttu-id="e9cf3-173">Se sua carga de trabalho envolver consulta de valores dentro de instâncias XML sem conhecer os nomes de elementos ou de atributos que contêm esses valores, você poderá desejar criar o índice VALUE.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-173">If your workload involves querying for values within XML instances without knowing the element or attribute names that contain those values, you may want to create the VALUE index.</span></span> <span data-ttu-id="e9cf3-174">Normalmente, isso ocorre com pesquisas de eixos descendentes, como //author[last-name="Howard"], em que elementos \<author> podem ocorrer em qualquer nível da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-174">This typically occurs with descendant axes lookups, such as //author[last-name="Howard"], where \<author> elements can occur at any level of the hierarchy.</span></span> <span data-ttu-id="e9cf3-175">Isso também ocorre em consultas com curinga, como /book [@\* = "novel"], em que a consulta procura por elementos \<book> que têm algum atributo com o valor "novel".</span><span class="sxs-lookup"><span data-stu-id="e9cf3-175">It also occurs in wildcard queries, such as /book [@\* = "novel"], where the query looks for \<book> elements that have some attribute having the value "novel".</span></span>  
  
### <a name="path-secondary-xml-index"></a><span data-ttu-id="e9cf3-176">Índice XML secundário PATH</span><span class="sxs-lookup"><span data-stu-id="e9cf3-176">PATH Secondary XML Index</span></span>  
 <span data-ttu-id="e9cf3-177">Se suas consultas normalmente especificarem expressões de caminho em colunas de tipo `xml`, um índice secundário PATH poderá acelerar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-177">If your queries generally specify path expressions on `xml` type columns, a PATH secondary index may be able to speed up the search.</span></span> <span data-ttu-id="e9cf3-178">Conforme descrito anteriormente neste tópico, o índice primário é útil quando você tem consultas que especificam o método **exist()** na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-178">As described earlier in this topic, the primary index is helpful when you have queries that specify **exist()** method in the WHERE clause.</span></span> <span data-ttu-id="e9cf3-179">Se você adicionar um índice secundário PATH, poderá também melhorar o desempenho da pesquisa nessas consultas.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-179">If you add a PATH secondary index, you may also improve the search performance in such queries.</span></span>  
  
 <span data-ttu-id="e9cf3-180">Embora um índice XML primário evite precisar fragmentar objetos binários grandes XML em tempo de execução, ele pode fornecer o melhor desempenho para consultas baseadas em expressões de caminho.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-180">Although a primary XML index avoids having to shred the XML binary large objects at run time, it may not provide the best performance for queries based on path expressions.</span></span> <span data-ttu-id="e9cf3-181">Como todas as linhas no índice XML primário correspondentes a um objeto binário grande são pesquisadas sequencialmente para grandes instâncias XML, a pesquisa sequencial pode ser lenta.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-181">Because all rows in the primary XML index corresponding to an XML binary large object are searched sequentially for large XML instances, the sequential search may be slow.</span></span> <span data-ttu-id="e9cf3-182">Nesse caso, ter um índice secundário construído nos valores de caminho e valores de nós no índice primário pode acelerar significativamente a pesquisa do índice.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-182">In this case, having a secondary index built on the path values and node values in the primary index can significantly speed up the index search.</span></span> <span data-ttu-id="e9cf3-183">No índice secundário PATH, o valores de caminhos e de nós são colunas de chave que permitem buscas mais eficientes ao pesquisar caminhos.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-183">In the PATH secondary index, the path and node values are key columns that allow for more efficient seeks when searching for paths.</span></span> <span data-ttu-id="e9cf3-184">O otimizador de consulta pode usar o índice PATH para expressões como as mostradas no seguinte:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-184">The query optimizer may use the PATH index for expressions such as those shown in the following:</span></span>  
  
-   <span data-ttu-id="e9cf3-185">`/root/Location` que especifica apenas um caminho</span><span class="sxs-lookup"><span data-stu-id="e9cf3-185">`/root/Location` which specify only a path</span></span>  
  
 <span data-ttu-id="e9cf3-186">OU</span><span class="sxs-lookup"><span data-stu-id="e9cf3-186">OR</span></span>  
  
-   <span data-ttu-id="e9cf3-187">`/root/Location/@LocationID[.="10"]` em que o caminho e o valor do nó são especificados.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-187">`/root/Location/@LocationID[.="10"]` where both the path and the node value are specified.</span></span>  
  
 <span data-ttu-id="e9cf3-188">A consulta seguinte mostra onde o índice PATH é útil:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-188">The following query shows where the PATH index is helpful:</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS "PD")  
  
SELECT CatalogDescription.query('  
  /PD:ProductDescription/PD:Summary  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist ('/PD:ProductDescription/@ProductModelID[.="19"]') = 1  
```  
  
 <span data-ttu-id="e9cf3-189">Na consulta, a expressão de caminho `/PD:ProductDescription/@ProductModelID` e o valor `"19"` no método `exist()` correspondem aos campos de chave do índice PATH.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-189">In the query, the path expression `/PD:ProductDescription/@ProductModelID` and value `"19"` in the `exist()` method correspond to the key fields of the PATH index.</span></span> <span data-ttu-id="e9cf3-190">Isso permite busca direta no índice PATH e fornece desempenho melhor de pesquisa do que a pesquisa sequencial de valores de caminho no índice primário.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-190">This allows for direct seek in the PATH index and provides better search performance than the sequential search for path values in the primary index.</span></span>  
  
### <a name="value-secondary-xml-index"></a><span data-ttu-id="e9cf3-191">Índice XML secundário VALUE</span><span class="sxs-lookup"><span data-stu-id="e9cf3-191">VALUE Secondary XML Index</span></span>  
 <span data-ttu-id="e9cf3-192">Se as consultas forem baseadas em valor, por exemplo, `/Root/ProductDescription/@*[. = "Mountain Bike"]` ou `//ProductDescription[@Name = "Mountain Bike"]`e o caminho não for especificado completamente ou se incluir um caractere curinga, você poderá obter resultados mais rápidos construindo um índice XML secundário construído sobre valores de nós no índice XML primário.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-192">If queries are value based, for example, `/Root/ProductDescription/@*[. = "Mountain Bike"]` or `//ProductDescription[@Name = "Mountain Bike"]`, and the path is not fully specified or it includes a wildcard, you might obtain faster results by building a secondary XML index that is built on node values in the primary XML index.</span></span>  
  
 <span data-ttu-id="e9cf3-193">As colunas de chave do índice VALUE são (valor de nó e caminho) do índice XML primário.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-193">The key columns of the VALUE index are (node value and path) of the primary XML index.</span></span> <span data-ttu-id="e9cf3-194">Se sua carga de trabalho envolver consulta de valores de instâncias XML sem conhecer os nomes de elementos ou de atributos que contêm os valores, um índice VALUE poderá ser útil.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-194">If your workload involves querying for values from XML instances without knowing the element or attribute names that contain the values, a VALUE index may be useful.</span></span> <span data-ttu-id="e9cf3-195">Por exemplo, a expressão a seguir se beneficiará da existência de um índice VALUE:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-195">For example, the following expression will benefit from having a VALUE index:</span></span>  
  
-   <span data-ttu-id="e9cf3-196">`//author[LastName="someName"]` onde você sabe o valor do elemento <`LastName`>, mas o pai de <`author`> pode ocorrer em qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-196">`//author[LastName="someName"]` where you know the value of the <`LastName`> element, but the <`author`> parent can occur anywhere.</span></span>  
  
-   <span data-ttu-id="e9cf3-197">`/book[@* = "someValue"]` onde a consulta procura o elemento <`book`> que tem algum atributo contendo o valor `"someValue"`.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-197">`/book[@* = "someValue"]` where the query looks for the <`book`> element that has some attribute having the value `"someValue"`.</span></span>  
  
 <span data-ttu-id="e9cf3-198">A consulta a seguir retorna `ContactID` da tabela `Contact` .</span><span class="sxs-lookup"><span data-stu-id="e9cf3-198">The following query returns `ContactID` from the `Contact` table.</span></span> <span data-ttu-id="e9cf3-199">A `WHERE` cláusula Especifica um filtro que procura valores na `AdditionalContactInfo``xml` coluna tipo.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-199">The `WHERE` clause specifies a filter that looks for values in the `AdditionalContactInfo``xml` type column.</span></span> <span data-ttu-id="e9cf3-200">As IDs de contato serão retornadas apenas se o objeto binário grande XML das informações de contato adicionais correspondentes incluírem um número de telefone específico.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-200">The contact IDs are returned only if the corresponding additional contact information XML binary large object includes a specific telephone number.</span></span> <span data-ttu-id="e9cf3-201">Como o elemento <`telephoneNumber`> pode aparecer em qualquer lugar no XML, a expressão de caminho especifica o eixo descendente ou independente.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-201">Because the <`telephoneNumber`> element may appear anywhere in the XML, the path expression specifies the descendent-or-self axis.</span></span>  
  
```  
WITH XMLNAMESPACES (  
  'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo' AS CI,  
  'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes' AS ACT)  
  
SELECT ContactID   
FROM   Person.Contact  
WHERE  AdditionalContactInfo.exist('//ACT:telephoneNumber/ACT:number[.="111-111-1111"]') = 1  
```  
  
 <span data-ttu-id="e9cf3-202">Nessa situação, o valor da pesquisa de <`number`> é conhecido, mas ele pode aparecer em qualquer lugar na instância XML como um filho do elemento <`telephoneNumber`>.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-202">In this situation, the search value for <`number`> is known, but it can appear anywhere in the XML instance as a child of the <`telephoneNumber`> element.</span></span> <span data-ttu-id="e9cf3-203">Esse tipo de consulta pode se beneficiar de um índice de pesquisa baseado em um valor específico.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-203">This kind of query might benefit from an index lookup based on a specific value.</span></span>  
  
### <a name="property-secondary-index"></a><span data-ttu-id="e9cf3-204">Índice XML secundário PROPERTY</span><span class="sxs-lookup"><span data-stu-id="e9cf3-204">PROPERTY Secondary Index</span></span>  
 <span data-ttu-id="e9cf3-205">Consultas que recuperam um ou mais valores de instâncias XML individuais podem se beneficiar de um índice PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-205">Queries that retrieve one or more values from individual XML instances might benefit from a PROPERTY index.</span></span> <span data-ttu-id="e9cf3-206">Esse cenário ocorre quando você recupera propriedades de objeto usando o método **Value ()** do `xml` tipo e quando o valor da chave primária do objeto é conhecido.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-206">This scenario occurs when you retrieve object properties by using the **value()** method of the `xml` type and when the primary key value of the object is known.</span></span>  
  
 <span data-ttu-id="e9cf3-207">O índice PROPERTY é construído nas colunas (PK, Caminho e valor do nó) do índice XML primário, em que PK é a chave primária da tabela base.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-207">The PROPERTY index is built on columns (PK, Path and node value) of the primary XML index where PK is the primary key of the base table.</span></span>  
  
 <span data-ttu-id="e9cf3-208">Por exemplo, para obter o modelo do produto `19`, a consulta a seguir recupera o `ProductModelID` e os valores do atributo `ProductModelName` usando o método `value()` .</span><span class="sxs-lookup"><span data-stu-id="e9cf3-208">For example, for product model `19`, the following query retrieves the `ProductModelID` and `ProductModelName` attribute values using the `value()` method.</span></span> <span data-ttu-id="e9cf3-209">Em vez de usar o índice XML primário ou os outros índices XML secundários, o índice PROPERTY pode fornecer execução mais rápida.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-209">Instead of using the primary XML index or the other secondary XML indexes, the PROPERTY index may provide faster execution.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS "PD")  
  
SELECT CatalogDescription.value('(/PD:ProductDescription/@ProductModelID)[1]', 'int') as ModelID,  
       CatalogDescription.value('(/PD:ProductDescription/@ProductModelName)[1]', 'varchar(30)') as ModelName          
FROM Production.ProductModel     
WHERE ProductModelID = 19  
```  
  
 <span data-ttu-id="e9cf3-210">Exceto pelas diferenças descritas posteriormente neste tópico, a criação de um índice XML em uma `xml` coluna de tipo é semelhante à criação de um índice em uma coluna que não seja de `xml` tipo.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-210">Except for the differences described later in this topic, creating an XML index on an`xml` type column is similar to creating an index on a non-`xml` type column.</span></span> <span data-ttu-id="e9cf3-211">As instruções DDL do [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir podem ser usadas para criar e gerenciar índices XML:</span><span class="sxs-lookup"><span data-stu-id="e9cf3-211">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statements can be used to create and manage XML indexes:</span></span>  
  
-   [<span data-ttu-id="e9cf3-212">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e9cf3-212">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
-   [<span data-ttu-id="e9cf3-213">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e9cf3-213">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
-   [<span data-ttu-id="e9cf3-214">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e9cf3-214">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
## <a name="getting-information-about-xml-indexes"></a><span data-ttu-id="e9cf3-215">Obtendo informações sobre índices XML</span><span class="sxs-lookup"><span data-stu-id="e9cf3-215">Getting Information about XML Indexes</span></span>  
 <span data-ttu-id="e9cf3-216">As entradas de índice XML são exibidas na exibição do catálogo, sys.indexes, com o índice "tipo" 3.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-216">XML index entries appear in the catalog view, sys.indexes, with the index "type" 3.</span></span> <span data-ttu-id="e9cf3-217">A coluna de nome contém o nome do índice XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-217">The name column contains the name of the XML index.</span></span>  
  
 <span data-ttu-id="e9cf3-218">Também são registrados índices de XML na exibição do catálogo, sys.xml_indexes.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-218">XML indexes are also recorded in the catalog view, sys.xml_indexes.</span></span> <span data-ttu-id="e9cf3-219">Essa exibição contém todas as colunas de sys.indexes e algumas específicas que são úteis para índices XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-219">This contains all the columns of sys.indexes and some specific ones that are useful for XML indexes.</span></span> <span data-ttu-id="e9cf3-220">O valor NULL na coluna secondary_type indica um índice XML primário, os valores 'P', 'R' e 'V' representam os índices XML secundários PATH, PROPERTY e VALUE, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-220">The value NULL in the column, secondary_type, indicates a primary XML index; the values 'P', 'R' and 'V' stand for PATH, PROPERTY, and VALUE secondary XML indexes, respectively.</span></span>  
  
 <span data-ttu-id="e9cf3-221">O uso espacial de índices XML pode ser localizado na função com valor de tabela [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9cf3-221">The space use of XML indexes can be found in the table-valued function [sys.dm_db_index_physical_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span></span> <span data-ttu-id="e9cf3-222">Ela fornece informações, como o número de páginas ocupadas no disco, tamanho médio das linhas em bytes e o número de registros para todos os tipos de índices.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-222">It provides information, such as the number of disk pages occupied, average row size in bytes, and number of records, for all index types..</span></span> <span data-ttu-id="e9cf3-223">Isso também inclui índices XML.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-223">This also includes XML indexes.</span></span> <span data-ttu-id="e9cf3-224">Essas informações estão disponíveis para cada partição do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-224">This information is available for each database partition.</span></span> <span data-ttu-id="e9cf3-225">Índices XML usam o mesmo esquema e função de particionamento da tabela base.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-225">XML indexes use the same partitioning scheme and partitioning function of the base table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cf3-226">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9cf3-226">See Also</span></span>  
 <span data-ttu-id="e9cf3-227">[sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e9cf3-227">[sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) </span></span>  
 [<span data-ttu-id="e9cf3-228">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e9cf3-228">XML Data &#40;SQL Server&#41;</span></span>](../xml/xml-data-sql-server.md)  
  
  
