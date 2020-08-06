---
title: SXI (índices XML seletivos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 598ecdcd-084b-4032-81b2-eed6ae9f5d44
author: rothja
ms.author: jroth
ms.openlocfilehash: 37dd72c5de2892672dc9f63066075ab5e770d758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583400"
---
# <a name="selective-xml-indexes-sxi"></a><span data-ttu-id="164c3-102">SXI (índices XML seletivos)</span><span class="sxs-lookup"><span data-stu-id="164c3-102">Selective XML Indexes (SXI)</span></span>
  <span data-ttu-id="164c3-103">Os índices XML seletivos são outro tipo de índice XML que está disponível para você além de índices XML comuns.</span><span class="sxs-lookup"><span data-stu-id="164c3-103">Selective XML indexes are another type of XML index that is available to you in addition to ordinary XML indexes.</span></span> <span data-ttu-id="164c3-104">Os objetivos do recurso de índice XML seletivo são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="164c3-104">The goals of the selective XML index feature are the following:</span></span>  
  
-   <span data-ttu-id="164c3-105">Melhorar o desempenho das consultas em dados XML armazenados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="164c3-105">To improve the performance of queries over XML data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="164c3-106">Dar suporte à indexação mais rápida de grandes cargas de trabalho de dados XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-106">To support faster indexing of large XML data workloads.</span></span>  
  
-   <span data-ttu-id="164c3-107">Melhorar a escalabilidade e reduzir os custos de armazenamento de índices XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-107">To improve scalability by reducing the storage costs of XML indexes.</span></span>  
  
 <span data-ttu-id="164c3-108">A principal limitação de índices XML comuns é que eles indexam todo o documento XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-108">The main limitation with ordinary XML indexes is that they index the entire XML document.</span></span> <span data-ttu-id="164c3-109">Isso apresenta várias desvantagens significativas, como menor desempenho durante as consultas e maior custo de manutenção do índice, relacionados principalmente aos custos de armazenamento do índice.</span><span class="sxs-lookup"><span data-stu-id="164c3-109">This leads to several significant drawbacks, such as decreased query performance and increased index maintenance cost, mostly related to the storage costs of the index.</span></span>  
  
 <span data-ttu-id="164c3-110">O recurso de índice XML seletivo permite promover somente alguns caminhos dos documentos XML a serem indexados.</span><span class="sxs-lookup"><span data-stu-id="164c3-110">The selective XML index feature lets you promote only certain paths from the XML documents to index.</span></span> <span data-ttu-id="164c3-111">No momento da criação do índice, esses caminhos são avaliados, e os nós para os quais eles apontam são fragmentados e armazenados em uma tabela relacional no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="164c3-111">At index creation time, these paths are evaluated, and the nodes that they point to are shredded and stored inside a relational table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="164c3-112">Esse recurso usa um algoritmo de mapeamento eficiente desenvolvido pela [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research em colaboração com a equipe do produto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="164c3-112">This feature uses an efficient mapping algorithm developed by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research in collaboration with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product team.</span></span> <span data-ttu-id="164c3-113">Esse algoritmo mapeia os nós XML para uma única tabela relacional, com desempenho exZip Codecional, exigindo espaço de armazenamento modesto.</span><span class="sxs-lookup"><span data-stu-id="164c3-113">This algorithm maps the XML nodes to a single relational table, and achieves exceptional performance while requiring only modest storage space.</span></span>  
  
 <span data-ttu-id="164c3-114">O recurso de índice XML seletivo também dá suporte a índices XML seletivos secundários em nós que foram indexados por um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="164c3-114">The selective XML index feature also supports secondary selective XML indexes over nodes that have been indexed by a selective XML index.</span></span> <span data-ttu-id="164c3-115">Esses índices seletivos secundários são mais eficientes e melhoram o desempenho das consultas.</span><span class="sxs-lookup"><span data-stu-id="164c3-115">These secondary selective indexes are efficient and further improve the performance of queries.</span></span>  
  
##  <a name="benefits-of-selective-xml-indexes"></a><a name="benefits"></a> <span data-ttu-id="164c3-116">Benefícios de índices XML seletivos</span><span class="sxs-lookup"><span data-stu-id="164c3-116">Benefits of Selective XML Indexes</span></span>  
 <span data-ttu-id="164c3-117">Os índices XML seletivos apresentam os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="164c3-117">Selective XML indexes provide the following benefits:</span></span>  
  
1.  <span data-ttu-id="164c3-118">Desempenho significativamente melhor em consultas no tipo de dados XML para cargas típicas de consulta.</span><span class="sxs-lookup"><span data-stu-id="164c3-118">Greatly improved query performance over the XML data type for typical query loads.</span></span>  
  
2.  <span data-ttu-id="164c3-119">Requisitos de armazenamento reduzidos em relação aos índices XML comuns.</span><span class="sxs-lookup"><span data-stu-id="164c3-119">Reduced storage requirements compared to ordinary XML indexes.</span></span>  
  
3.  <span data-ttu-id="164c3-120">Custos de manutenção de índice reduzidos em relação aos índices XML comuns.</span><span class="sxs-lookup"><span data-stu-id="164c3-120">Reduced index maintenance costs compared to ordinary XML indexes.</span></span>  
  
4.  <span data-ttu-id="164c3-121">Não há necessidade de atualizar aplicativos para se beneficiar dos índices XML seletivos.</span><span class="sxs-lookup"><span data-stu-id="164c3-121">No need to update applications to benefit from selective XML indexes.</span></span>  
  

  
##  <a name="selective-xml-indexes-and-primary-xml-indexes"></a><a name="compare"></a> <span data-ttu-id="164c3-122">Índices XML seletivos e índices XML primários</span><span class="sxs-lookup"><span data-stu-id="164c3-122">Selective XML Indexes and Primary XML Indexes</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="164c3-123">Na maioria das vezes, crie um índice XML seletivo, em vez de um índice XML comum, para obter melhor desempenho e um armazenamento mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="164c3-123">Create a selective XML index instead of an ordinary XML index in most cases for better performance and more efficient storage.</span></span>  
  
 <span data-ttu-id="164c3-124">Entretanto, um índice XML seletivo não é recomendado quando uma das seguintes condições é verdadeira:</span><span class="sxs-lookup"><span data-stu-id="164c3-124">However, a selective XML index is not recommended when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="164c3-125">Você mapeia um grande número de caminhos de nós.</span><span class="sxs-lookup"><span data-stu-id="164c3-125">You map a large number of node paths.</span></span>  
  
-   <span data-ttu-id="164c3-126">Você dá suporte a consultas de elementos desconhecidos ou de elementos em um local desconhecido na estrutura do documento.</span><span class="sxs-lookup"><span data-stu-id="164c3-126">You support queries for unknown elements or elements in an unknown location in the document structure.</span></span>  
  

  
##  <a name="simple-example-of-a-selective-xml-index"></a><a name="example"></a> <span data-ttu-id="164c3-127">Exemplo simples de índice XML seletivo</span><span class="sxs-lookup"><span data-stu-id="164c3-127">Simple Example of a Selective XML Index</span></span>  
 <span data-ttu-id="164c3-128">Considere o fragmento XML a seguir como um documento XML em uma tabela de aproximadamente 500.000 linhas:</span><span class="sxs-lookup"><span data-stu-id="164c3-128">Consider the following XML fragment as an XML document in a table of approximately 500,000 rows:</span></span>  
  
```xml  
<book>  
    <created>2004-03-01</created>   
    <authors>Various</authors>  
    <subjects>  
        <subject>English wit and humor -- Periodicals</subject>  
        <subject>AP</subject>   
    </subjects>  
    <title>Punch, or the London Charivari, Volume 156, April 2, 1919</title>  
    <id>etext11617</id>  
</book>  
```  
  
 <span data-ttu-id="164c3-129">A criação de índice XML primário em muitas linhas desse esquema simples demora muito.</span><span class="sxs-lookup"><span data-stu-id="164c3-129">Creating a primary XML index over so many rows of this simple schema takes a long time.</span></span> <span data-ttu-id="164c3-130">A consulta desses dados também é prejudicada porque um índice XML primário não dá suporte à indexação seletiva.</span><span class="sxs-lookup"><span data-stu-id="164c3-130">Querying this data also suffers from the fact that a primary XML index does not support selective indexing.</span></span>  
  
 <span data-ttu-id="164c3-131">Se você precisa consultar somente esses dados no caminho `/book/title` e no caminho `/book/subjects` , poderá criar o seguinte índice XML seletivo:</span><span class="sxs-lookup"><span data-stu-id="164c3-131">If you only need to query this data over the `/book/title` path and the `/book/subjects` path, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX SXI_index  
ON Tbl(xmlcol)  
FOR   
(  
    pathTitle = '/book/title/text()' AS XQUERY 'xs:string',   
    pathAuthors = '/book/authors' AS XQUERY 'node()',  
    pathId = '/book/id' AS SQL NVARCHAR(100)  
)  
```  
  
 <span data-ttu-id="164c3-132">A instrução anterior é um bom exemplo da sintaxe CREATE que você usa ao criar um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="164c3-132">The preceding statement is a good example of the CREATE syntax that you use when you create a selective XML index.</span></span> <span data-ttu-id="164c3-133">Na instrução CREATE, primeiro você fornece um nome para o índice e identifica a tabela e a coluna XML para indexação.</span><span class="sxs-lookup"><span data-stu-id="164c3-133">In the CREATE statement, first you provide a name for the index and identify the table and the XML column to index.</span></span> <span data-ttu-id="164c3-134">Em seguida, você fornece os caminhos a serem indexados.</span><span class="sxs-lookup"><span data-stu-id="164c3-134">Then you provide the paths to index.</span></span> <span data-ttu-id="164c3-135">Um caminho tem três partes:</span><span class="sxs-lookup"><span data-stu-id="164c3-135">A path has three parts:</span></span>  
  
1.  <span data-ttu-id="164c3-136">Um nome que identifica exclusivamente o caminho.</span><span class="sxs-lookup"><span data-stu-id="164c3-136">A name that uniquely identifies the path.</span></span>  
  
2.  <span data-ttu-id="164c3-137">Uma expressão XQuery que descreve o caminho.</span><span class="sxs-lookup"><span data-stu-id="164c3-137">An XQuery expression that describes the path.</span></span>  
  
3.  <span data-ttu-id="164c3-138">Dicas de otimização opcionais.</span><span class="sxs-lookup"><span data-stu-id="164c3-138">Optional optimization hints.</span></span>  
  
 <span data-ttu-id="164c3-139">Para obter mais informações sobre esses elementos, consulte [Tarefas relacionadas](#reltasks).</span><span class="sxs-lookup"><span data-stu-id="164c3-139">For more information about these elements, see [Related Tasks](#reltasks).</span></span>  
  

  
## <a name="supported-features-prerequisites-and-limitations"></a><span data-ttu-id="164c3-140">Recursos com suporte, pré-requisitos e limitações</span><span class="sxs-lookup"><span data-stu-id="164c3-140">Supported Features, Prerequisites, and Limitations</span></span>  
  
###  <a name="supported-xml-features"></a><a name="features"></a> <span data-ttu-id="164c3-141">Recursos XML com suporte</span><span class="sxs-lookup"><span data-stu-id="164c3-141">Supported XML Features</span></span>  
 <span data-ttu-id="164c3-142">Os índices XML seletivos dão suporte à XQuery com suporte no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nos métodos exist(), value() e nodes().</span><span class="sxs-lookup"><span data-stu-id="164c3-142">Selective XML indexes support the XQuery supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inside the exist(), value() and nodes() methods.</span></span>  
  
-   <span data-ttu-id="164c3-143">Para os métodos exist(), value() e nodes(), os índices XML seletivos contêm informações suficientes para transformar a expressão inteira.</span><span class="sxs-lookup"><span data-stu-id="164c3-143">For the exist(), value() and nodes() methods, selective XML indexes contain enough information to transform the entire expression.</span></span>  
  
-   <span data-ttu-id="164c3-144">Para os métodos query() e modify(), os índices XML seletivos podem ser usados somente para filtragem de nós.</span><span class="sxs-lookup"><span data-stu-id="164c3-144">For the query() and modify() methods, selective XML indexes may be used for node filtering only.</span></span>  
  
-   <span data-ttu-id="164c3-145">Para o método query(), os índices XML seletivos não são usados para recuperar resultados.</span><span class="sxs-lookup"><span data-stu-id="164c3-145">For the query() method, selective XML indexes are not used to retrieve results.</span></span>  
  
-   <span data-ttu-id="164c3-146">Para o método modify(), os índices XML seletivos não são usados para atualizar documentos XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-146">For the modify() method, selective XML indexes are not used to update XML documents.</span></span>  
  

  
###  <a name="unsupported-xml-features"></a><a name="unsupported"></a> <span data-ttu-id="164c3-147">Recursos XML sem suporte</span><span class="sxs-lookup"><span data-stu-id="164c3-147">Unsupported XML Features</span></span>  
 <span data-ttu-id="164c3-148">Os índices XML seletivos não dão suporte aos recursos a seguir que têm suporte na implementação de XML do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="164c3-148">Selective XML indexes do not support the following features that are supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementation of XML:</span></span>  
  
-   <span data-ttu-id="164c3-149">Indexação de nós com tipos XS complexos: tipos de união, tipos de sequência e tipos de lista.</span><span class="sxs-lookup"><span data-stu-id="164c3-149">Indexing of nodes with complex XS types: union types, sequence types, and list types.</span></span>  
  
-   <span data-ttu-id="164c3-150">Indexação de nós com tipos XS binários: por exemplo, base64Binary e hexBinary.</span><span class="sxs-lookup"><span data-stu-id="164c3-150">Indexing of nodes with binary XS types: for example, base64Binary and hexBinary.</span></span>  
  
-   <span data-ttu-id="164c3-151">Especificação dos nós a serem indexados com expressões XPath que contêm o caractere curinga `*` no final: Por exemplo, `/a/b/c/*`, `/a//b/*` ou `/a/b/*:c`.</span><span class="sxs-lookup"><span data-stu-id="164c3-151">Specifying the nodes to index with XPath expressions that contain the wildcard character `*` at the end: For example,  `/a/b/c/*`, `/a//b/*`, or `/a/b/*:c`.</span></span>  
  
-   <span data-ttu-id="164c3-152">Indexação de qualquer eixo que não seja o filho, o atributo ou o descendente.</span><span class="sxs-lookup"><span data-stu-id="164c3-152">Indexing any axis other than child, attribute, or descendant.</span></span> <span data-ttu-id="164c3-153">A ocorrência `//<step>` é permitida como um caso especial.</span><span class="sxs-lookup"><span data-stu-id="164c3-153">The `//<step>` case is allowed as a special case.</span></span>  
  
-   <span data-ttu-id="164c3-154">Indexação de instruções e comentários de processamento XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-154">Indexing of XML processing instructions and comments.</span></span>  
  
-   <span data-ttu-id="164c3-155">Especificação e recuperação do identificador de um nó usando a função id().</span><span class="sxs-lookup"><span data-stu-id="164c3-155">Specifying and retrieving the identifier for a node by using the id() function.</span></span>  
  

  
###  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="164c3-156">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="164c3-156">Prerequisites</span></span>  
 <span data-ttu-id="164c3-157">Os pré-requisitos a seguir devem existir para que se possa criar um índice XML seletivo em uma coluna XML em uma tabela de usuário:</span><span class="sxs-lookup"><span data-stu-id="164c3-157">The following prerequisites must exist before you can create a selective XML index over an XML column in a user table:</span></span>  
  
-   <span data-ttu-id="164c3-158">Um índice clusterizado deve existir na chave primária da tabela do usuário.</span><span class="sxs-lookup"><span data-stu-id="164c3-158">A clustered index must exist on the primary key of the user table.</span></span>  
  
-   <span data-ttu-id="164c3-159">A chave primária da tabela de usuário é limitada a um tamanho de 128 bytes quando usada com índices XML seletivos.</span><span class="sxs-lookup"><span data-stu-id="164c3-159">The primary key of the user table is limited to a size of 128 bytes when used with selective XML indexes.</span></span>  
  
-   <span data-ttu-id="164c3-160">A chave de clustering da tabela de usuário é limitada a 15 colunas quando usada com índices XML seletivos.</span><span class="sxs-lookup"><span data-stu-id="164c3-160">The clustering key of the user table is limited to 15 columns when used with selective XML indexes.</span></span>  
  

  
###  <a name="limitations"></a><a name="limits"></a> <span data-ttu-id="164c3-161">Limitações</span><span class="sxs-lookup"><span data-stu-id="164c3-161">Limitations</span></span>  
 <span data-ttu-id="164c3-162">**Requisitos e limitações gerais**</span><span class="sxs-lookup"><span data-stu-id="164c3-162">**General requirements and limitations**</span></span>  
  
-   <span data-ttu-id="164c3-163">Cada índice XML seletivo só pode ser criado em uma única coluna XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-163">Each selective XML index can only be created on a single XML column.</span></span>  
  
-   <span data-ttu-id="164c3-164">Não é possível criar um índice XML seletivo em uma coluna que não seja XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-164">You cannot create a selective XML index on a non-XML column.</span></span>  
  
-   <span data-ttu-id="164c3-165">Cada coluna XML em uma tabela só pode ter um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="164c3-165">Each XML column in a table can have only one selective XML index.</span></span>  
  
-   <span data-ttu-id="164c3-166">Cada tabela pode ter até 249 índices XML seletivos.</span><span class="sxs-lookup"><span data-stu-id="164c3-166">Each table can have up to 249 selective XML indexes.</span></span>  
  
 <span data-ttu-id="164c3-167">**Limitações em objetos com suporte**</span><span class="sxs-lookup"><span data-stu-id="164c3-167">**Limitations on supported objects**</span></span>  
  
 <span data-ttu-id="164c3-168">Não é possível criar índices XML seletivos nos seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="164c3-168">You cannot create selective XML indexes on the following objects:</span></span>  
  
1.  <span data-ttu-id="164c3-169">Colunas XML em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="164c3-169">XML columns in a view.</span></span>  
  
2.  <span data-ttu-id="164c3-170">Variável com valor de tabela com colunas XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-170">Table-valued variable with XML columns.</span></span>  
  
3.  <span data-ttu-id="164c3-171">Variáveis do tipo XML.</span><span class="sxs-lookup"><span data-stu-id="164c3-171">XML type variables.</span></span>  
  
4.  <span data-ttu-id="164c3-172">Colunas XML computadas.</span><span class="sxs-lookup"><span data-stu-id="164c3-172">Computed XML columns.</span></span>  
  
5.  <span data-ttu-id="164c3-173">Colunas XML com uma profundidade de mais de 128 nós aninhados.</span><span class="sxs-lookup"><span data-stu-id="164c3-173">XML columns with a depth of more than 128 nested nodes.</span></span>  
  
 <span data-ttu-id="164c3-174">**Limitações relacionadas ao armazenamento**</span><span class="sxs-lookup"><span data-stu-id="164c3-174">**Limitations related to storage**</span></span>  
  
 <span data-ttu-id="164c3-175">Há um limite finito no número de nós do documento XML que pode ser adicionado ao índice.</span><span class="sxs-lookup"><span data-stu-id="164c3-175">There is a finite limit on the number of nodes from the XML document that can be added to the index.</span></span> <span data-ttu-id="164c3-176">Um índice XML seletivo mapeia documentos XML para uma única tabela relacional.</span><span class="sxs-lookup"><span data-stu-id="164c3-176">A selective XML index maps XML documents to a single relational table.</span></span> <span data-ttu-id="164c3-177">Portanto, ele não pode ter mais de 1.024 colunas não nulas em nenhuma linha especificada da tabela.</span><span class="sxs-lookup"><span data-stu-id="164c3-177">Therefore it cannot have more than 1024 non-null columns in any given row of the table.</span></span> <span data-ttu-id="164c3-178">Além de isso, muitas das limitações de colunas esparsas também se aplicam a índices XML seletivos, porque os índices usam colunas esparsas para armazenamento.</span><span class="sxs-lookup"><span data-stu-id="164c3-178">Furthermore, many of the limitations of sparse columns also apply to selective XML indexes, because the indexes use sparse columns for storage.</span></span>  
  
 <span data-ttu-id="164c3-179">O número máximo de colunas não nulas com suporte em qualquer linha especificada depende do tamanho dos dados nas colunas:</span><span class="sxs-lookup"><span data-stu-id="164c3-179">The maximum number of non-null columns supported in any given row depends on the size of the data in the columns:</span></span>  
  
-   <span data-ttu-id="164c3-180">Na melhor das hipóteses, 1024 colunas não nulas têm suporte quando todas as colunas são do tipo **bit**.</span><span class="sxs-lookup"><span data-stu-id="164c3-180">In the best case, 1024 non-null columns are supported when all columns are of type **bit**.</span></span>  
  
-   <span data-ttu-id="164c3-181">Na pior das hipóteses, somente 236 colunas não nulas têm suporte quando todas as colunas são grandes objetos do tipo **varchar**.</span><span class="sxs-lookup"><span data-stu-id="164c3-181">In the worst case, only 236 non-null columns are supported when all columns are large objects of type **varchar**.</span></span>  
  
 <span data-ttu-id="164c3-182">Os índices XML seletivos usam de uma a quatro colunas internamente para cada caminho de nó que é indexado.</span><span class="sxs-lookup"><span data-stu-id="164c3-182">Selective XML indexes use from one to four columns internally for every node path that is indexed.</span></span> <span data-ttu-id="164c3-183">O número total de nós que pode ser indexado varia de 60 a várias centenas de nós, dependendo do tamanho real dos dados nos caminhos indexados.</span><span class="sxs-lookup"><span data-stu-id="164c3-183">The total number of nodes that can be indexed ranges from 60 to several hundred nodes, depending on the actual size of the data in the indexed paths.</span></span>  
  
-   <span data-ttu-id="164c3-184">Na pior das hipóteses, quando alguns ou todos os nós são mapeados usando `//` na definição do caminho de nó, o número máximo de nós indexados é 60.</span><span class="sxs-lookup"><span data-stu-id="164c3-184">In the worst case, when some or all nodes are mapped using `//` in the node path definition, the maximum number of indexed nodes is 60.</span></span>  
  
-   <span data-ttu-id="164c3-185">Na melhor das hipóteses, quando os nós são mapeados sem usar `//` na definição do caminho de nó, o número máximo de nós indexados é 200.</span><span class="sxs-lookup"><span data-stu-id="164c3-185">In the best case, when nodes are mapped without using `//` in the node path definition, the maximum number of indexed nodes is 200.</span></span>  
  
 <span data-ttu-id="164c3-186">**Os índices XML seletivos são recriados quando você usa a instrução CREATE ou ALTER no índice.**</span><span class="sxs-lookup"><span data-stu-id="164c3-186">**Selective XML indexes are rebuilt when you CREATE or ALTER the index.**</span></span>  
  
 <span data-ttu-id="164c3-187">Quando você usa a instrução CREATE ou ALTER em um índice XML seletivo, ele será recriado offline em um modo de thread único.</span><span class="sxs-lookup"><span data-stu-id="164c3-187">When you CREATE or ALTER a selective XML index, it is rebuilt in a single-threaded, offline mode.</span></span> <span data-ttu-id="164c3-188">Frequentemente, as instruções ALTER afetam negativamente o desempenho das consultas em documentos XML indexados.</span><span class="sxs-lookup"><span data-stu-id="164c3-188">Frequently ALTER statements negatively affect the performance of queries over the indexed XML documents.</span></span>  
  
 <span data-ttu-id="164c3-189">**Outras limitações**</span><span class="sxs-lookup"><span data-stu-id="164c3-189">**Other limitations**</span></span>  
  
-   <span data-ttu-id="164c3-190">Não há suporte para índices XML seletivos em dicas de consulta.</span><span class="sxs-lookup"><span data-stu-id="164c3-190">Selective XML indexes are not supported in query hints.</span></span>  
  
-   <span data-ttu-id="164c3-191">Não há suporte para índices XML seletivos e índices XML seletivos secundários no Orientador de Otimização de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="164c3-191">Selective XML indexes and secondary selective XML indexes are not supported in Database Tuning Advisor.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="164c3-192">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="164c3-192">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="164c3-193">**Tarefa**</span><span class="sxs-lookup"><span data-stu-id="164c3-193">**Task**</span></span>|<span data-ttu-id="164c3-194">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="164c3-194">**Topic**</span></span>|  
|<span data-ttu-id="164c3-195">Especifique os caminhos de nós que você deseja indexar e dicas de otimização opcionais ao criar ou alterar um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="164c3-195">Specify the node paths that you want to index and optional optimization hints when you create or alter a selective XML index.</span></span>|[<span data-ttu-id="164c3-196">Especificar caminhos e dicas de otimização para índices XML seletivos</span><span class="sxs-lookup"><span data-stu-id="164c3-196">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>](specify-paths-and-optimization-hints-for-selective-xml-indexes.md)|  
|<span data-ttu-id="164c3-197">Crie, altere ou remova um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="164c3-197">Create, alter, or drop a selective XML index.</span></span>|[<span data-ttu-id="164c3-198">Criar, alterar e remover índices XML seletivos</span><span class="sxs-lookup"><span data-stu-id="164c3-198">Create, Alter, and Drop Selective XML Indexes</span></span>](create-alter-and-drop-selective-xml-indexes.md)|  
|<span data-ttu-id="164c3-199">Crie, altere ou remova um índice XML seletivo secundário.</span><span class="sxs-lookup"><span data-stu-id="164c3-199">Create, alter, or drop a secondary selective XML index.</span></span>|[<span data-ttu-id="164c3-200">Criar, alterar e remover índices XML seletivos secundários</span><span class="sxs-lookup"><span data-stu-id="164c3-200">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>](create-alter-and-drop-secondary-selective-xml-indexes.md)|  
  

  
  
