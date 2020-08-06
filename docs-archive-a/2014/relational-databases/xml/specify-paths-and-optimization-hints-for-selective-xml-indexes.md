---
title: Especificar caminhos e dicas de otimização para índices XML seletivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 486ee339-165b-4aeb-b760-d2ba023d7d0a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a9d683fe57d489fdb9922b53d2c5c6825835216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682183"
---
# <a name="specify-paths-and-optimization-hints-for-selective-xml-indexes"></a><span data-ttu-id="6909d-102">Especificar caminhos e dicas de otimização para índices XML seletivos</span><span class="sxs-lookup"><span data-stu-id="6909d-102">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>
  <span data-ttu-id="6909d-103">Este tópico descreve como especificar caminhos de nós a serem indexados e dicas de otimização de indexação ao criar ou alterar índices XML seletivos.</span><span class="sxs-lookup"><span data-stu-id="6909d-103">This topic describes how to specify node paths to index and optimization hints for indexing when you create or alter selective XML indexes.</span></span>  
  
 <span data-ttu-id="6909d-104">Especifique caminhos de nós e dicas de otimização ao mesmo tempo em uma das seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="6909d-104">You specify node paths and optimization hints at the same time in one of the following statements:</span></span>  
  
-   <span data-ttu-id="6909d-105">Na cláusula **FOR** de uma instrução **CREATE** .</span><span class="sxs-lookup"><span data-stu-id="6909d-105">In the **FOR** clause of a **CREATE** statement.</span></span> <span data-ttu-id="6909d-106">Para obter mais informações, veja [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6909d-106">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="6909d-107">Na cláusula **ADD** de uma instrução **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="6909d-107">In the **ADD** clause of an **ALTER** statement.</span></span> <span data-ttu-id="6909d-108">Para obter mais informações, veja [ALTER INDEX &#40;Índices XML Seletivos&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="6909d-108">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="6909d-109">Para obter mais informações sobre índices XML seletivos, veja [Índices XML Seletivos &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="6909d-109">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="understanding-xquery-and-sql-server-types-in-untyped-xml"></a><a name="untyped"></a> <span data-ttu-id="6909d-110">Noções básicas sobre tipos XQuery e tipos do SQL Server em XML não tipado</span><span class="sxs-lookup"><span data-stu-id="6909d-110">Understanding XQuery and SQL Server Types in Untyped XML</span></span>  
 <span data-ttu-id="6909d-111">Os índices XML seletivos dão suporte a dois sistemas de tipos: Tipos XQuery e tipos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6909d-111">Selective XML indexes support two type systems: XQuery types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="6909d-112">O caminho indexado pode ser usado para corresponder a uma expressão XQuery ou para corresponder ao tipo de retorno do método value() do tipo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="6909d-112">The indexed path can be used either to match an XQuery expression, or to match the return type of the value() method of the XML data type.</span></span>  
  
-   <span data-ttu-id="6909d-113">Quando um caminho a ser indexado não é anotado, ou é anotado com a palavra-chave XQUERY, o caminho corresponde a uma expressão XQuery.</span><span class="sxs-lookup"><span data-stu-id="6909d-113">When a path to index is not annotated, or is annotated with the XQUERY keyword, the path matches an XQuery expression.</span></span> <span data-ttu-id="6909d-114">Há duas variações para caminhos de nós anotados de XQUERY:</span><span class="sxs-lookup"><span data-stu-id="6909d-114">There are two variations for XQUERY-annotated node paths:</span></span>  
  
    -   <span data-ttu-id="6909d-115">Se você não especificar a palavra-chave XQUERY e o tipo de dados XQuery, os mapeamentos padrão serão usados.</span><span class="sxs-lookup"><span data-stu-id="6909d-115">If you do not specify the XQUERY keyword and the XQuery data type, then default mappings are used.</span></span> <span data-ttu-id="6909d-116">Normalmente, o desempenho e o armazenamento não são os ideais.</span><span class="sxs-lookup"><span data-stu-id="6909d-116">Typically performance and storage are not optimal.</span></span>  
  
    -   <span data-ttu-id="6909d-117">Se você especificar a palavra-chave XQUERY e o tipo de dados XQuery e, opcionalmente, outras dicas de otimização, poderá obter o melhor desempenho possível e um armazenamento o mais eficiente possível.</span><span class="sxs-lookup"><span data-stu-id="6909d-117">If you specify the XQUERY keyword and the XQuery data type, and optionally other optimization hints, then you can achieve the best possible performance and the most efficient possible storage.</span></span> <span data-ttu-id="6909d-118">Entretanto, uma conversão pode falhar.</span><span class="sxs-lookup"><span data-stu-id="6909d-118">However, a cast can fail.</span></span>  
  
-   <span data-ttu-id="6909d-119">Quando um caminho a ser indexado é anotado com a palavra-chave SQL, o caminho corresponde ao tipo de retorno do método value() do tipo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="6909d-119">When a path to index is annotated with the SQL keyword, the path matches the return type of the value() method of the XML data type.</span></span> <span data-ttu-id="6909d-120">Especifique o tipo de dados apropriado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que é o tipo de retorno esperado do método value().</span><span class="sxs-lookup"><span data-stu-id="6909d-120">Specify the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, which is the return type that you expect from the value() method.</span></span>  
  
 <span data-ttu-id="6909d-121">Há diferenças sutis entre o sistema de tipos XML de expressões XQuery e o sistema de tipos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aplicados ao método value() do tipo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="6909d-121">There are subtle differences between the XQuery expressions XML type system and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type system applied to the value() method of the XML data type.</span></span> <span data-ttu-id="6909d-122">As principais diferenças incluem:</span><span class="sxs-lookup"><span data-stu-id="6909d-122">These differences include the following:</span></span>  
  
-   <span data-ttu-id="6909d-123">O sistema de tipos XQuery reconhece os espaços à direita.</span><span class="sxs-lookup"><span data-stu-id="6909d-123">The XQuery type system is aware of trailing spaces.</span></span> <span data-ttu-id="6909d-124">Por exemplo, de acordo com a semântica do tipo XQuery, as cadeias de caracteres "abc" e "abc " não são iguais; já no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , essas cadeias são iguais.</span><span class="sxs-lookup"><span data-stu-id="6909d-124">For example, according to XQuery type semantics, the strings "abc" and "abc " are not equal, while in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] these strings are equal.</span></span>  
  
-   <span data-ttu-id="6909d-125">Os tipos de dados de ponto flutuante de XQuery dá suporte aos valores especiais +/- zero e +/- infinito.</span><span class="sxs-lookup"><span data-stu-id="6909d-125">XQuery floating point data types support special values of +/- zero and +/- infinity.</span></span> <span data-ttu-id="6909d-126">Esses valores especiais não têm suporte em tipos de dados de ponto flutuante do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6909d-126">These special values are not supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] floating point data types.</span></span>  
  
### <a name="xquery-types-in-untyped-xml"></a><span data-ttu-id="6909d-127">Tipos XQuery em XML não tipado</span><span class="sxs-lookup"><span data-stu-id="6909d-127">XQuery Types in Untyped XML</span></span>  
  
-   <span data-ttu-id="6909d-128">Os tipos XQuery correspondem a expressões XQuery em todos os métodos do tipo de dados XML que inclui o método value().</span><span class="sxs-lookup"><span data-stu-id="6909d-128">XQuery types match XQuery expressions in all methods of the XML data type including the value() method.</span></span>  
  
-   <span data-ttu-id="6909d-129">Os tipos XQuery dão suporte a estas dicas de otimização: node(), SINGLETON, DATA TYPE e MAXLENGTH.</span><span class="sxs-lookup"><span data-stu-id="6909d-129">XQuery types support these optimization hints: node(), SINGLETON, DATA TYPE, and MAXLENGTH.</span></span>  
  
 <span data-ttu-id="6909d-130">Para expressões XQuery em XML não tipado, é possível escolher entre dois modos de operação:</span><span class="sxs-lookup"><span data-stu-id="6909d-130">For XQuery expressions over untyped XML, you can choose between two modes of operation:</span></span>  
  
-   <span data-ttu-id="6909d-131">**Modo de mapeamento padrão**.</span><span class="sxs-lookup"><span data-stu-id="6909d-131">**Default mapping mode**.</span></span> <span data-ttu-id="6909d-132">Nesse modo, você especifica somente o caminho ao criar um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="6909d-132">In this mode, you specify only the path when creating a selective XML index.</span></span>  
  
-   <span data-ttu-id="6909d-133">**Modo de mapeamento especificado pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="6909d-133">**User-specified mapping mode**.</span></span> <span data-ttu-id="6909d-134">Nesse modo, você especifica o caminho e as dicas de otimização opcionais.</span><span class="sxs-lookup"><span data-stu-id="6909d-134">In this mode, you specify both the path and optional optimization hints.</span></span>  
  
 <span data-ttu-id="6909d-135">O modo de mapeamento padrão usa uma opção de armazenamento conservadora, que é sempre segura e geral.</span><span class="sxs-lookup"><span data-stu-id="6909d-135">The default mapping mode uses a conservative storage option which is always safe and general.</span></span> <span data-ttu-id="6909d-136">Ela pode corresponder a qualquer tipo da expressão.</span><span class="sxs-lookup"><span data-stu-id="6909d-136">It can match any expression type.</span></span> <span data-ttu-id="6909d-137">Uma limitação do modo de mapeamento padrão é um desempenho abaixo do ideal, pois é necessário um maior número de conversões de runtime, e os índices secundários não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6909d-137">A limitation of the default mapping mode is less than optimal performance, because an increased number of runtime casts are required, and secondary indexes are not available.</span></span>  
  
 <span data-ttu-id="6909d-138">Veja aqui um exemplo de índice XML seletivo criado com mapeamentos padrão.</span><span class="sxs-lookup"><span data-stu-id="6909d-138">Here is an example of a selective XML index created with default mappings.</span></span> <span data-ttu-id="6909d-139">Para todos os três caminhos, o tipo de nó padrão (**xs:untypedAtomic**) e a cardinalidade são usados.</span><span class="sxs-lookup"><span data-stu-id="6909d-139">For all three paths, the default node type (**xs:untypedAtomic**) and cardinality are used.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_default  
ON Tbl(xmlcol)  
FOR  
(  
mypath01 =  '/a/b',  
mypath02 = '/a/b/c',  
mypath03 = '/a/b/d'  
)  
```  
  
 <span data-ttu-id="6909d-140">O modo de mapeamento especificado pelo usuário permite especificar um tipo e uma cardinalidade para que o nó obtenha melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="6909d-140">The user-specified mapping mode lets you specify a type and cardinality for the node to obtain better performance.</span></span> <span data-ttu-id="6909d-141">Entretanto, essa melhoria de desempenho é obtida abrindo mão da segurança, porque uma conversão pode falhar, bem como da generalidade, porque apenas o tipo especificado corresponde ao índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="6909d-141">However, this improved performance is achieved by giving up safety - because a cast can fail - and generality - because only the specified type is matched with the selective XML index.</span></span>  
  
 <span data-ttu-id="6909d-142">Os tipos XQuery com suporte para ocorrências XML não tipadas são:</span><span class="sxs-lookup"><span data-stu-id="6909d-142">The XQuery types supported for untyped XML case are:</span></span>  
  
-   <span data-ttu-id="6909d-143">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="6909d-143">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="6909d-144">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="6909d-144">**xs:double**</span></span>  
  
-   <span data-ttu-id="6909d-145">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="6909d-145">**xs:string**</span></span>  
  
-   <span data-ttu-id="6909d-146">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="6909d-146">**xs:date**</span></span>  
  
-   <span data-ttu-id="6909d-147">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="6909d-147">**xs:time**</span></span>  
  
-   <span data-ttu-id="6909d-148">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="6909d-148">**xs:dateTime**</span></span>  
  
 <span data-ttu-id="6909d-149">Se o tipo não for especificado, o nó será considerado do tipo de dados **xs:untypedAtomic** .</span><span class="sxs-lookup"><span data-stu-id="6909d-149">If the type is not specified, the node is assumed to be of the **xs:untypedAtomic** data type.</span></span>  
  
 <span data-ttu-id="6909d-150">É possível otimizar o índice XML seletivo mostrado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6909d-150">You can optimize the selective XML index shown in the following manner:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_optimized  
ON Tbl(xmlcol)  
FOR  
(  
mypath= '/a/b' as XQUERY 'node()',  
pathX = '/a/b/c' as XQUERY 'xs:double' SINGLETON,  
pathY = '/a/b/d' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
)  
-- mypath - Only the node value is needed; storage is saved.  
-- pathX - Performance is improved; secondary indexes are possible.  
-- pathY - Performance is improved; secondary indexes are possible; storage is saved.  
```  
  
### <a name="sql-server-types-in-untyped-xml"></a><span data-ttu-id="6909d-151">Tipos do SQL Server em XML não tipado</span><span class="sxs-lookup"><span data-stu-id="6909d-151">SQL Server Types in Untyped XML</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6909d-152">os tipos correspondem ao valor retornado do método value().</span><span class="sxs-lookup"><span data-stu-id="6909d-152">types match the return value of the value() method.</span></span>  
  
-   <span data-ttu-id="6909d-153">Os tipos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dão suporte a esta dica de otimização: SINGLETON.</span><span class="sxs-lookup"><span data-stu-id="6909d-153">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types support this optimization hint: SINGLETON.</span></span>  
  
 <span data-ttu-id="6909d-154">É obrigatório especificar um tipo para caminhos que retornam tipos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6909d-154">Specifying a type is mandatory for paths that return [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="6909d-155">Use o mesmo tipo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você usaria no método value().</span><span class="sxs-lookup"><span data-stu-id="6909d-155">Use the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type that you would use in the value() method.</span></span>  
  
 <span data-ttu-id="6909d-156">Considere a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="6909d-156">Consider the following query:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/d)[1]', 'NVARCHAR(200)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="6909d-157">A consulta especificada retorna um valor do caminho `/a/b/d` empacotado em um tipo de dados NVARCHAR(200); assim o tipo de dados a ser especificado para o nó é óbvio.</span><span class="sxs-lookup"><span data-stu-id="6909d-157">The specified query returns a value from the path `/a/b/d` packed into an NVARCHAR(200) data type, so the data type to specify for the node is obvious.</span></span> <span data-ttu-id="6909d-158">Entretanto, não há nenhum esquema para especificar a cardinalidade do nó em XML não tipado.</span><span class="sxs-lookup"><span data-stu-id="6909d-158">However there is no schema to specify the cardinality of the node in untyped XML.</span></span> <span data-ttu-id="6909d-159">Para especificar que o nó `d` aparece no máximo uma vez no nó pai `b`, crie um índice XML seletivo que use a dica de otimização SINGLETON da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6909d-159">To specify that node `d` appears at most once under its parent node `b`, create a selective XML index that uses the SINGLETON optimization hint as follows:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_US  
ON Tbl(xmlcol)  
FOR  
(  
node1223 = '/a/b/d' as SQL NVARCHAR(200) SINGLETON  
)  
```  
  

  
##  <a name="understanding-selective-xml-index-support-for-typed-xml"></a><a name="typed"></a> <span data-ttu-id="6909d-160">Noções básicas sobre suporte à índice XML seletivo para XML tipado</span><span class="sxs-lookup"><span data-stu-id="6909d-160">Understanding Selective XML Index support for typed XML</span></span>  
 <span data-ttu-id="6909d-161">O XML tipado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é um esquema associado a determinado documento XML.</span><span class="sxs-lookup"><span data-stu-id="6909d-161">Typed XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is a schema associated with a given XML document.</span></span> <span data-ttu-id="6909d-162">O esquema define a estrutura geral do documento e tipos de nós.</span><span class="sxs-lookup"><span data-stu-id="6909d-162">The schema defines overall document structure and types of nodes.</span></span> <span data-ttu-id="6909d-163">Se um esquema existe, o índice XML seletivo aplica a estrutura do esquema quando o usuário promove caminhos; assim, não há necessidade de especificar os tipos XQUERY para caminhos.</span><span class="sxs-lookup"><span data-stu-id="6909d-163">If a schema exists, Selective XML Index applies the schema structure when the user promotes paths, so there is no need to specify the XQUERY types for paths.</span></span>  
  
 <span data-ttu-id="6909d-164">O índice XML seletivo dá suporte aos seguintes tipos XSD:</span><span class="sxs-lookup"><span data-stu-id="6909d-164">Selective XML Index supports following XSD types:</span></span>  
  
-   <span data-ttu-id="6909d-165">**xs:anyUri**</span><span class="sxs-lookup"><span data-stu-id="6909d-165">**xs:anyUri**</span></span>  
  
-   <span data-ttu-id="6909d-166">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="6909d-166">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="6909d-167">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="6909d-167">**xs:date**</span></span>  
  
-   <span data-ttu-id="6909d-168">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="6909d-168">**xs:dateTime**</span></span>  
  
-   <span data-ttu-id="6909d-169">**xs:day**</span><span class="sxs-lookup"><span data-stu-id="6909d-169">**xs:day**</span></span>  
  
-   <span data-ttu-id="6909d-170">**xs:decimal**</span><span class="sxs-lookup"><span data-stu-id="6909d-170">**xs:decimal**</span></span>  
  
-   <span data-ttu-id="6909d-171">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="6909d-171">**xs:double**</span></span>  
  
-   <span data-ttu-id="6909d-172">**xs:float**</span><span class="sxs-lookup"><span data-stu-id="6909d-172">**xs:float**</span></span>  
  
-   <span data-ttu-id="6909d-173">**xs:int**</span><span class="sxs-lookup"><span data-stu-id="6909d-173">**xs:int**</span></span>  
  
-   <span data-ttu-id="6909d-174">**xs:integer**</span><span class="sxs-lookup"><span data-stu-id="6909d-174">**xs:integer**</span></span>  
  
-   <span data-ttu-id="6909d-175">**xs:language**</span><span class="sxs-lookup"><span data-stu-id="6909d-175">**xs:language**</span></span>  
  
-   <span data-ttu-id="6909d-176">**xs:long**</span><span class="sxs-lookup"><span data-stu-id="6909d-176">**xs:long**</span></span>  
  
-   <span data-ttu-id="6909d-177">**xs:name**</span><span class="sxs-lookup"><span data-stu-id="6909d-177">**xs:name**</span></span>  
  
-   <span data-ttu-id="6909d-178">**xs:NCName**</span><span class="sxs-lookup"><span data-stu-id="6909d-178">**xs:NCName**</span></span>  
  
-   <span data-ttu-id="6909d-179">**xs:negativeInteger**</span><span class="sxs-lookup"><span data-stu-id="6909d-179">**xs:negativeInteger**</span></span>  
  
-   <span data-ttu-id="6909d-180">**xs: nmtoken**</span><span class="sxs-lookup"><span data-stu-id="6909d-180">**xs:nmtoken**</span></span>  
  
-   <span data-ttu-id="6909d-181">**xs:nonNegativeInteger**</span><span class="sxs-lookup"><span data-stu-id="6909d-181">**xs:nonNegativeInteger**</span></span>  
  
-   <span data-ttu-id="6909d-182">**xs:nonPositiveInteger**</span><span class="sxs-lookup"><span data-stu-id="6909d-182">**xs:nonPositiveInteger**</span></span>  
  
-   <span data-ttu-id="6909d-183">**xs:positiveInteger**</span><span class="sxs-lookup"><span data-stu-id="6909d-183">**xs:positiveInteger**</span></span>  
  
-   <span data-ttu-id="6909d-184">**xs:qname**</span><span class="sxs-lookup"><span data-stu-id="6909d-184">**xs:qname**</span></span>  
  
-   <span data-ttu-id="6909d-185">**xs:short**</span><span class="sxs-lookup"><span data-stu-id="6909d-185">**xs:short**</span></span>  
  
-   <span data-ttu-id="6909d-186">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="6909d-186">**xs:string**</span></span>  
  
-   <span data-ttu-id="6909d-187">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="6909d-187">**xs:time**</span></span>  
  
-   <span data-ttu-id="6909d-188">**xs:token**</span><span class="sxs-lookup"><span data-stu-id="6909d-188">**xs:token**</span></span>  
  
-   <span data-ttu-id="6909d-189">**xs:unsignedByte**</span><span class="sxs-lookup"><span data-stu-id="6909d-189">**xs:unsignedByte**</span></span>  
  
-   <span data-ttu-id="6909d-190">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="6909d-190">**xs:unsignedInt**</span></span>  
  
-   <span data-ttu-id="6909d-191">**xs:unsignedLong**</span><span class="sxs-lookup"><span data-stu-id="6909d-191">**xs:unsignedLong**</span></span>  
  
-   <span data-ttu-id="6909d-192">**xs:unsignedShort**</span><span class="sxs-lookup"><span data-stu-id="6909d-192">**xs:unsignedShort**</span></span>  
  
 <span data-ttu-id="6909d-193">Quando o índice XML seletivo é criado em um documento que tem um esquema associado a ele, a especificação de um tipo XQUERY na criação ou alteração de índice retorna um erro.</span><span class="sxs-lookup"><span data-stu-id="6909d-193">When Selective XML Index is created over a document that has schema associated with it, specifying a XQUERY type at index creation or altering returns an error.</span></span> <span data-ttu-id="6909d-194">O usuário pode usar anotações do tipo SQL na parte de promoção de caminho.</span><span class="sxs-lookup"><span data-stu-id="6909d-194">The user can use SQL type annotations in the path promotion part.</span></span> <span data-ttu-id="6909d-195">O tipo SQL deve ser uma conversão válida do tipo XSD definido no esquema, ou um erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="6909d-195">The SQL type must be a valid conversion from the XSD type defined in the schema, or an error is thrown.</span></span> <span data-ttu-id="6909d-196">Todos os tipos SQL que têm representação adequada em XSD têm suporte, com exceção dos tipos de data/hora.</span><span class="sxs-lookup"><span data-stu-id="6909d-196">All SQL types that have adequate representation in XSD are supported, with an exception of date/time types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6909d-197">O índice seletivo será usado se o tipo especificado na promoção de caminho do índice XML seletivo for igual ao valor de retorno do método value().</span><span class="sxs-lookup"><span data-stu-id="6909d-197">The selective index is used if the type specified in the Selective XML Index path promotion is the same as the value() method return value.</span></span>  
  
 <span data-ttu-id="6909d-198">As seguintes dicas de otimização podem ser usadas com documentos XML tipados:</span><span class="sxs-lookup"><span data-stu-id="6909d-198">The following optimization hints can be used with typed XML documents:</span></span>  
  
-   <span data-ttu-id="6909d-199">Dica de otimização node().</span><span class="sxs-lookup"><span data-stu-id="6909d-199">node() optimization hint.</span></span>  
  
-   <span data-ttu-id="6909d-200">A dica de otimização MAXLENGTH pode ser usada com tipos xs:string para encurtar o valor indexado.</span><span class="sxs-lookup"><span data-stu-id="6909d-200">MAXLENGTH optimization hint can be used with xs:string types to shorten the indexed value.</span></span>  
  
 <span data-ttu-id="6909d-201">Para obter mais informações sobre dicas de otimização, consulte [Especificando dicas de otimização](#hints).</span><span class="sxs-lookup"><span data-stu-id="6909d-201">For more information about optimization hints, see [Specifying Optimization Hints](#hints).</span></span>  
  
##  <a name="specifying-paths"></a><a name="paths"></a> <span data-ttu-id="6909d-202">Especificando caminhos</span><span class="sxs-lookup"><span data-stu-id="6909d-202">Specifying Paths</span></span>  
 <span data-ttu-id="6909d-203">Um índice XML seletivo permite indexar somente um subconjunto de nós dos dados XML armazenados relevantes para as consultas que você pretende realizar.</span><span class="sxs-lookup"><span data-stu-id="6909d-203">A selective XML index lets you index only a subset of nodes from the stored XML data that are relevant for the queries that you expect to run.</span></span> <span data-ttu-id="6909d-204">Quando o subconjunto de nós relevantes é muito menor que o número total de nós no documento XML, o índice XML seletivo armazena somente os nós relevantes.</span><span class="sxs-lookup"><span data-stu-id="6909d-204">When the subset of relevant nodes is much smaller than the total number of nodes in the XML document, the selective XML index stores only the relevant nodes.</span></span> <span data-ttu-id="6909d-205">Para se beneficiar de um índice XML seletivo, identifique o subconjunto correto de nós para indexação.</span><span class="sxs-lookup"><span data-stu-id="6909d-205">To benefit from a selective XML index, identify the correct subset of nodes to index.</span></span>  
  
### <a name="choosing-the-nodes-to-index"></a><span data-ttu-id="6909d-206">Escolhendo os nós a serem indexados</span><span class="sxs-lookup"><span data-stu-id="6909d-206">Choosing the nodes to index</span></span>  
 <span data-ttu-id="6909d-207">É possível usar os dois princípios simples a seguir para identificar o subconjunto correto de nós a ser adicionado a um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="6909d-207">You can use the following two simple principles to identify the correct subset of nodes to add to a selective XML index.</span></span>  
  
1.  <span data-ttu-id="6909d-208">**Princípio 1**: Para avaliar determinada expressão XQuery, indexe todos os nós que você precisa examinar.</span><span class="sxs-lookup"><span data-stu-id="6909d-208">**Principle 1**: To evaluate a given XQuery expression, index all nodes that you need to examine.</span></span>  
  
    -   <span data-ttu-id="6909d-209">Indexe todos os nós cuja existência ou valor é usado na expressão XQuery.</span><span class="sxs-lookup"><span data-stu-id="6909d-209">Index all nodes whose existence or value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="6909d-210">Indexe todos os nós na expressão XQuery aos quais predicados XQuery são aplicados.</span><span class="sxs-lookup"><span data-stu-id="6909d-210">Index all nodes in the XQuery expression on which XQuery predicates are applied.</span></span>  
  
     <span data-ttu-id="6909d-211">Considere a seguinte consulta simples no [documento XML de exemplo](#sample) neste tópico:</span><span class="sxs-lookup"><span data-stu-id="6909d-211">Consider the following simple query over the [sample XML document](#sample) in this topic:</span></span>  
  
    ```sql  
    SELECT T.record FROM myXMLTable T  
    WHERE T.xmldata.exist('/a/b[./c = "43"]') = 1  
    ```  
  
     <span data-ttu-id="6909d-212">Para retornar as instâncias XML compatíveis com essa consulta, um índice XML seletivo precisa examinar dois nós em cada instância XML:</span><span class="sxs-lookup"><span data-stu-id="6909d-212">In order to return the XML instances that satisfy this query, a selective XML index needs to examine two nodes in every XML instance:</span></span>  
  
    -   <span data-ttu-id="6909d-213">Nó `c`, porque seu valor é usado na expressão XQuery.</span><span class="sxs-lookup"><span data-stu-id="6909d-213">Node `c`, because its value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="6909d-214">Nó `b`, porque um predicado é aplicado ao nó`b` na expressão XQuery.</span><span class="sxs-lookup"><span data-stu-id="6909d-214">Node `b`, because a predicate is applied over node`b` in the XQuery expression.</span></span>  
  
2.  <span data-ttu-id="6909d-215">**Princípio 2**: Para obter o melhor desempenho, indexe todos os nós necessários para avaliar determinada expressão XQuery.</span><span class="sxs-lookup"><span data-stu-id="6909d-215">**Principle 2**: For best performance, index all nodes that are required to evaluate a given XQuery expression.</span></span> <span data-ttu-id="6909d-216">Se você indexar apenas alguns dos nós, o índice XML seletivo melhorará somente a avaliação de subexpressões que incluam nós indexados.</span><span class="sxs-lookup"><span data-stu-id="6909d-216">If you index only some of the nodes, then the selective XML index improves the evaluation of sub-expressions that include only indexed nodes.</span></span>  
  
 <span data-ttu-id="6909d-217">Para melhorar o desempenho da instrução SELECT mostrada acima, é possível criar o seguinte índice XML seletivo:</span><span class="sxs-lookup"><span data-stu-id="6909d-217">To improve the performance of the SELECT statement shown above, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX simple_sxi  
ON Tbl(xmlcol)  
FOR  
(  
    path123 =  '/a/b',  
    path124 =  '/a/b/c'  
)  
```  
  
### <a name="indexing-identical-paths"></a><span data-ttu-id="6909d-218">Indexando caminhos idênticos</span><span class="sxs-lookup"><span data-stu-id="6909d-218">Indexing identical paths</span></span>  
 <span data-ttu-id="6909d-219">Não é possível promover caminhos idênticos ao mesmo tipo de dados em nomes de caminho diferentes.</span><span class="sxs-lookup"><span data-stu-id="6909d-219">You cannot promote identical paths as the same data type under different path names.</span></span> <span data-ttu-id="6909d-220">Por exemplo, a consulta a seguir gera um erro, porque `pathOne` e `pathTwo` são idênticos:</span><span class="sxs-lookup"><span data-stu-id="6909d-220">For example, the following query raises an error, because `pathOne` and `pathTwo` are identical:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:string',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
 <span data-ttu-id="6909d-221">Entretanto, é possível promover caminhos idênticos como tipos de dados diferentes com nomes diferentes.</span><span class="sxs-lookup"><span data-stu-id="6909d-221">However, you can promote identical paths as different data types with different names.</span></span> <span data-ttu-id="6909d-222">Por exemplo, agora a consulta a seguir é aceitável, porque os tipos de dados são diferentes:</span><span class="sxs-lookup"><span data-stu-id="6909d-222">For example, the following query is now acceptable, because the data types are different:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:double',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
### <a name="examples"></a><span data-ttu-id="6909d-223">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6909d-223">Examples</span></span>  
 <span data-ttu-id="6909d-224">Veja alguns exemplos adicionais de seleção de nós corretos a serem indexados para diferentes tipos XQuery.</span><span class="sxs-lookup"><span data-stu-id="6909d-224">Here are some additional examples of selecting the correct nodes to index for different XQuery types.</span></span>  
  
 <span data-ttu-id="6909d-225">**Exemplo 1**</span><span class="sxs-lookup"><span data-stu-id="6909d-225">**Example 1**</span></span>  
  
 <span data-ttu-id="6909d-226">Esta é uma XQuery simples que usa o método exist():</span><span class="sxs-lookup"><span data-stu-id="6909d-226">Here is a simple XQuery that uses the exist() method:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e/h') = 1  
```  
  
 <span data-ttu-id="6909d-227">A tabela a seguir mostra os nós que devem ser indexados para permitir que essa consulta use o índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="6909d-227">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="6909d-228">Nó a ser incluído no índice</span><span class="sxs-lookup"><span data-stu-id="6909d-228">Node to include in the index</span></span>|<span data-ttu-id="6909d-229">Motivo para indexar este nó</span><span class="sxs-lookup"><span data-stu-id="6909d-229">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="6909d-230">**/a/b/c/d/e/h**</span><span class="sxs-lookup"><span data-stu-id="6909d-230">**/a/b/c/d/e/h**</span></span>|<span data-ttu-id="6909d-231">A existência do nó `h` é avaliada no método exist().</span><span class="sxs-lookup"><span data-stu-id="6909d-231">The existence of node `h` is evaluated in the exist() method.</span></span>|  
  
 <span data-ttu-id="6909d-232">**Exemplo 2**</span><span class="sxs-lookup"><span data-stu-id="6909d-232">**Example 2**</span></span>  
  
 <span data-ttu-id="6909d-233">Esta é uma variação mais complexa da XQuery anterior, com um predicado aplicado:</span><span class="sxs-lookup"><span data-stu-id="6909d-233">Here is a more complex variation of the previous XQuery, with a predicate applied:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e[./f = "SQL"]') = 1  
```  
  
 <span data-ttu-id="6909d-234">A tabela a seguir mostra os nós que devem ser indexados para permitir que essa consulta use o índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="6909d-234">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="6909d-235">Nó a ser incluído no índice</span><span class="sxs-lookup"><span data-stu-id="6909d-235">Node to include in the index</span></span>|<span data-ttu-id="6909d-236">Motivo para indexar este nó</span><span class="sxs-lookup"><span data-stu-id="6909d-236">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="6909d-237">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="6909d-237">**/a/b/c/d/e**</span></span>|<span data-ttu-id="6909d-238">Um predicado é aplicado ao nó `e`.</span><span class="sxs-lookup"><span data-stu-id="6909d-238">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="6909d-239">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="6909d-239">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="6909d-240">O valor do nó `f` é avaliado no predicado.</span><span class="sxs-lookup"><span data-stu-id="6909d-240">The value of node `f` is evaluated inside the predicate.</span></span>|  
  
 <span data-ttu-id="6909d-241">**Exemplo 3**</span><span class="sxs-lookup"><span data-stu-id="6909d-241">**Example 3**</span></span>  
  
 <span data-ttu-id="6909d-242">Esta é uma consulta mais complexa com uma cláusula value():</span><span class="sxs-lookup"><span data-stu-id="6909d-242">Here is a more complex query with a value() clause:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/c/d/e[./f = "SQL"]/g)[1]', 'nvarchar(100)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="6909d-243">A tabela a seguir mostra os nós que devem ser indexados para permitir que essa consulta use o índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="6909d-243">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="6909d-244">Nó a ser incluído no índice</span><span class="sxs-lookup"><span data-stu-id="6909d-244">Node to include in the index</span></span>|<span data-ttu-id="6909d-245">Motivo para indexar este nó</span><span class="sxs-lookup"><span data-stu-id="6909d-245">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="6909d-246">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="6909d-246">**/a/b/c/d/e**</span></span>|<span data-ttu-id="6909d-247">Um predicado é aplicado ao nó `e`.</span><span class="sxs-lookup"><span data-stu-id="6909d-247">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="6909d-248">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="6909d-248">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="6909d-249">O valor do nó `f` é avaliado no predicado.</span><span class="sxs-lookup"><span data-stu-id="6909d-249">The value of node `f` is evaluated inside the predicate.</span></span>|  
|<span data-ttu-id="6909d-250">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="6909d-250">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="6909d-251">O valor do nó `g` é retornado pelo método value().</span><span class="sxs-lookup"><span data-stu-id="6909d-251">The value of node `g` is returned by the value() method.</span></span>|  
  
 <span data-ttu-id="6909d-252">**Exemplo 4**</span><span class="sxs-lookup"><span data-stu-id="6909d-252">**Example 4**</span></span>  
  
 <span data-ttu-id="6909d-253">Veja aqui uma consulta que usa uma cláusula FLWOR em uma cláusula exist().</span><span class="sxs-lookup"><span data-stu-id="6909d-253">Here is a query that uses a FLWOR clause inside an exist() clause.</span></span> <span data-ttu-id="6909d-254">(O nome FLWOR vem das cinco cláusulas que podem formar uma expressão XQuery FLWOR: for, let, where, order by e return.)</span><span class="sxs-lookup"><span data-stu-id="6909d-254">(The name FLWOR comes from the five clauses that can make up an XQuery FLWOR expression: for, let, where, order by, and return.)</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('  
  For $x in /a/b/c/d/e  
  Where $x/f = "SQL"  
  Return $x/g  
') = 1  
```  
  
 <span data-ttu-id="6909d-255">A tabela a seguir mostra os nós que devem ser indexados para permitir que essa consulta use o índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="6909d-255">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="6909d-256">Nó a ser incluído no índice</span><span class="sxs-lookup"><span data-stu-id="6909d-256">Node to include in the index</span></span>|<span data-ttu-id="6909d-257">Motivo para indexar este nó</span><span class="sxs-lookup"><span data-stu-id="6909d-257">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="6909d-258">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="6909d-258">**/a/b/c/d/e**</span></span>|<span data-ttu-id="6909d-259">A existência do nó `e` é avaliada na cláusula FLWOR.</span><span class="sxs-lookup"><span data-stu-id="6909d-259">The existence of node `e` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="6909d-260">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="6909d-260">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="6909d-261">O valor do nó `f` é avaliado na cláusula FLWOR.</span><span class="sxs-lookup"><span data-stu-id="6909d-261">The value of node `f` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="6909d-262">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="6909d-262">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="6909d-263">A existência do nó `g` é avaliada pelo método exist().</span><span class="sxs-lookup"><span data-stu-id="6909d-263">The existence of node `g` is evaluated by the exist() method.</span></span>|  
  

  
##  <a name="specifying-optimization-hints"></a><a name="hints"></a> <span data-ttu-id="6909d-264">Especificando dicas de otimização</span><span class="sxs-lookup"><span data-stu-id="6909d-264">Specifying Optimization Hints</span></span>  
 <span data-ttu-id="6909d-265">Você pode usar dicas de otimização opcionais para especificar detalhes adicionais de mapeamento para um nó indexado por um índice XML seletivo.</span><span class="sxs-lookup"><span data-stu-id="6909d-265">You can use optional optimization hints to specify additional mapping details for a node indexed by a selective XML index.</span></span> <span data-ttu-id="6909d-266">Por exemplo, você pode especificar o tipo de dados e a cardinalidade de um nó, bem como certas informações sobre a estrutura dos dados.</span><span class="sxs-lookup"><span data-stu-id="6909d-266">For example, you can specify the data type and cardinality of the node, and certain information about the structure of the data.</span></span> <span data-ttu-id="6909d-267">Essas informações adicionais dão suporte a um melhor mapeamento.</span><span class="sxs-lookup"><span data-stu-id="6909d-267">This additional information supports better mapping.</span></span> <span data-ttu-id="6909d-268">Também resultam em melhorias no desempenho ou economia no armazenamento, ou ambas.</span><span class="sxs-lookup"><span data-stu-id="6909d-268">It also results in improvements in performance or savings in storage, or both.</span></span>  
  
 <span data-ttu-id="6909d-269">O uso de dicas de otimização é opcional.</span><span class="sxs-lookup"><span data-stu-id="6909d-269">The use of optimization hints is optional.</span></span> <span data-ttu-id="6909d-270">Sempre é possível aceitar os mapeamentos padrão, que são confiáveis, mas que podem não proporcionar um desempenho e um armazenamento ideais.</span><span class="sxs-lookup"><span data-stu-id="6909d-270">You can always accept the default mappings, which are reliable but may not provide optimal performance and storage.</span></span>  
  
 <span data-ttu-id="6909d-271">Algumas dicas de otimização, como a dica SINGLETON, apresentam restrições aos dados.</span><span class="sxs-lookup"><span data-stu-id="6909d-271">Some optimization hints - for example, the SINGLETON hint - introduce constraints over your data.</span></span> <span data-ttu-id="6909d-272">Em alguns casos, erros podem ser gerados quando essas restrições não são atendidas.</span><span class="sxs-lookup"><span data-stu-id="6909d-272">In some cases, errors may be raised when those constraints are not met.</span></span>  
  
### <a name="benefits-of-optimization-hints"></a><span data-ttu-id="6909d-273">Benefícios de dicas de otimização</span><span class="sxs-lookup"><span data-stu-id="6909d-273">Benefits of Optimization Hints</span></span>  
 <span data-ttu-id="6909d-274">A tabela a seguir identifica as dicas de otimização que dão suporte a um armazenamento mais eficiente ou a um melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="6909d-274">The following table identifies the optimization hints that support more efficient storage or improved performance.</span></span>  
  
|<span data-ttu-id="6909d-275">Dica de otimização</span><span class="sxs-lookup"><span data-stu-id="6909d-275">Optimization hint</span></span>|<span data-ttu-id="6909d-276">Armazenamento mais eficiente</span><span class="sxs-lookup"><span data-stu-id="6909d-276">More efficient storage</span></span>|<span data-ttu-id="6909d-277">desempenho aprimorado</span><span class="sxs-lookup"><span data-stu-id="6909d-277">Improved performance</span></span>|  
|-----------------------|----------------------------|--------------------------|  
|<span data-ttu-id="6909d-278">**node()**</span><span class="sxs-lookup"><span data-stu-id="6909d-278">**node()**</span></span>|<span data-ttu-id="6909d-279">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-279">Yes</span></span>|<span data-ttu-id="6909d-280">Não</span><span class="sxs-lookup"><span data-stu-id="6909d-280">No</span></span>|  
|<span data-ttu-id="6909d-281">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="6909d-281">**SINGLETON**</span></span>|<span data-ttu-id="6909d-282">Não</span><span class="sxs-lookup"><span data-stu-id="6909d-282">No</span></span>|<span data-ttu-id="6909d-283">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-283">Yes</span></span>|  
|<span data-ttu-id="6909d-284">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="6909d-284">**DATA TYPE**</span></span>|<span data-ttu-id="6909d-285">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-285">Yes</span></span>|<span data-ttu-id="6909d-286">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-286">Yes</span></span>|  
|<span data-ttu-id="6909d-287">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="6909d-287">**MAXLENGTH**</span></span>|<span data-ttu-id="6909d-288">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-288">Yes</span></span>|<span data-ttu-id="6909d-289">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-289">Yes</span></span>|  
  
### <a name="optimization-hints-and-data-types"></a><span data-ttu-id="6909d-290">Dicas e tipos de dados de otimização</span><span class="sxs-lookup"><span data-stu-id="6909d-290">Optimization Hints and Data Types</span></span>  
 <span data-ttu-id="6909d-291">É possível indexar nós como tipos de dados XQuery ou como tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6909d-291">You can index nodes as XQuery data types or as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="6909d-292">A tabela a seguir mostra as dicas de otimização com suporte para cada tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="6909d-292">The following table shows which optimization hints are supported with each data type.</span></span>  
  
|<span data-ttu-id="6909d-293">Dica de otimização</span><span class="sxs-lookup"><span data-stu-id="6909d-293">Optimization hint</span></span>|<span data-ttu-id="6909d-294">Tipos de dados XQuery</span><span class="sxs-lookup"><span data-stu-id="6909d-294">XQuery data types</span></span>|<span data-ttu-id="6909d-295">Tipos de dados SQL</span><span class="sxs-lookup"><span data-stu-id="6909d-295">SQL data types</span></span>|  
|-----------------------|-----------------------|--------------------|  
|<span data-ttu-id="6909d-296">**node()**</span><span class="sxs-lookup"><span data-stu-id="6909d-296">**node()**</span></span>|<span data-ttu-id="6909d-297">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-297">Yes</span></span>|<span data-ttu-id="6909d-298">Não</span><span class="sxs-lookup"><span data-stu-id="6909d-298">No</span></span>|  
|<span data-ttu-id="6909d-299">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="6909d-299">**SINGLETON**</span></span>|<span data-ttu-id="6909d-300">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-300">Yes</span></span>|<span data-ttu-id="6909d-301">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-301">Yes</span></span>|  
|<span data-ttu-id="6909d-302">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="6909d-302">**DATA TYPE**</span></span>|<span data-ttu-id="6909d-303">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-303">Yes</span></span>|<span data-ttu-id="6909d-304">Não</span><span class="sxs-lookup"><span data-stu-id="6909d-304">No</span></span>|  
|<span data-ttu-id="6909d-305">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="6909d-305">**MAXLENGTH**</span></span>|<span data-ttu-id="6909d-306">Sim</span><span class="sxs-lookup"><span data-stu-id="6909d-306">Yes</span></span>|<span data-ttu-id="6909d-307">Não</span><span class="sxs-lookup"><span data-stu-id="6909d-307">No</span></span>|  
  
### <a name="node-optimization-hint"></a><span data-ttu-id="6909d-308">Dica de otimização node()</span><span class="sxs-lookup"><span data-stu-id="6909d-308">node() optimization hint</span></span>  
 <span data-ttu-id="6909d-309">Aplica-se a: Tipos de dados XQuery</span><span class="sxs-lookup"><span data-stu-id="6909d-309">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="6909d-310">Você pode usar a otimização node() para especificar um nó cujo valor não seja obrigatório para avaliar a consulta típica.</span><span class="sxs-lookup"><span data-stu-id="6909d-310">You can use the node() optimization to specify a node whose value is not required to evaluate the typical query.</span></span> <span data-ttu-id="6909d-311">Essa dica reduz os requisitos de armazenamento quando a consulta típica só precisa avaliar a existência do nó.</span><span class="sxs-lookup"><span data-stu-id="6909d-311">This hint reduces storage requirements when the typical query only has to evaluate the existence of the node.</span></span> <span data-ttu-id="6909d-312">(Por padrão, um índice XML seletivo armazena o valor de todos os nós promovidos, exceto de tipos de nós complexos.)</span><span class="sxs-lookup"><span data-stu-id="6909d-312">(By default, a selective XML index stores the value for all promoted nodes, except complex node types.)</span></span>  
  
 <span data-ttu-id="6909d-313">Considere o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="6909d-313">Consider the following example:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b[./c=5]') = 1  
```  
  
 <span data-ttu-id="6909d-314">Para usar um índice XML seletivo para avaliar essa consulta, promova os nós `b` e `c`.</span><span class="sxs-lookup"><span data-stu-id="6909d-314">To use a selective XML index to evaluate this query, promote nodes `b` and `c`.</span></span> <span data-ttu-id="6909d-315">Entretanto, como o valor do nó `b` não é obrigatório, você pode usar a dica node() com a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="6909d-315">However, since the value of node `b` is not required, you can use the node() hint with the following syntax:</span></span>  
  
 `/a/b/ as node()`  
  
 <span data-ttu-id="6909d-316">Se uma consulta exigir o valor de um nó que tenha sido indexado com a dica node(), o índice XML seletivo não poderá ser usado.</span><span class="sxs-lookup"><span data-stu-id="6909d-316">If a query requires the value of a node that has been indexed with the node() hint, then the selective XML index cannot be used.</span></span>  
  
### <a name="singleton-optimization-hint"></a><span data-ttu-id="6909d-317">Dica de otimização SINGLETON</span><span class="sxs-lookup"><span data-stu-id="6909d-317">SINGLETON optimization hint</span></span>  
 <span data-ttu-id="6909d-318">Aplica-se a: XQuery ou tipos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6909d-318">Applies to: XQuery or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types</span></span>  
  
 <span data-ttu-id="6909d-319">A dica de otimização SINGLETON especifica a cardinalidade de um nó.</span><span class="sxs-lookup"><span data-stu-id="6909d-319">The SINGLETON optimization hint specifies the cardinality of a node.</span></span> <span data-ttu-id="6909d-320">Essa dica melhora o desempenho da consulta, pois sabe-se antecipadamente que um nó é exibido no máximo uma vez em seu pai ou ancestral.</span><span class="sxs-lookup"><span data-stu-id="6909d-320">This hint improves query performance since it is known in advance that a node appears at most one time within its parent or ancestor.</span></span>  
  
 <span data-ttu-id="6909d-321">Considere o [documento XML de exemplo](#sample) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6909d-321">Consider the [sample XML document](#sample) in this topic.</span></span>  
  
 <span data-ttu-id="6909d-322">Para usar um índice XML seletivo para consultar este documento, você pode especificar a dica SINGLETON para o nó `d` , pois ele aparece no máximo uma vez em seu pai.</span><span class="sxs-lookup"><span data-stu-id="6909d-322">To use a selective XML index to query this document, you can specify the SINGLETON hint for node `d` since it appears at most one time within its parent.</span></span>  
  
 <span data-ttu-id="6909d-323">Se a dica SINGLETON for especificada, mas um nó aparecer mais de uma vez em seu pai ou ancestral, um erro será gerado quando o índice for criado (de dados existentes) ou quando uma consulta for executada (de novos dados).</span><span class="sxs-lookup"><span data-stu-id="6909d-323">If the SINGLETON hint has been specified, but a node appears more than one time within its parent or ancestor, then an error is raised when you create the index (for existing data) or when you run a query (for new data).</span></span>  
  
### <a name="data-type-optimization-hint"></a><span data-ttu-id="6909d-324">Dica de otimização DATA TYPE</span><span class="sxs-lookup"><span data-stu-id="6909d-324">DATA TYPE optimization hint</span></span>  
 <span data-ttu-id="6909d-325">Aplica-se a: Tipos de dados XQuery</span><span class="sxs-lookup"><span data-stu-id="6909d-325">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="6909d-326">A dica de otimização CREATE DATABASE permite especificar um tipo de dados XQuery ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o nó indexado.</span><span class="sxs-lookup"><span data-stu-id="6909d-326">The DATA TYPE optimization hint lets you specify an XQuery or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for the indexed node.</span></span> <span data-ttu-id="6909d-327">O tipo de dados é usado para a coluna na tabela de dados do índice XML seletivo que corresponde ao nó indexado.</span><span class="sxs-lookup"><span data-stu-id="6909d-327">The data type is used for the column in the data table of the selective XML index that corresponds to the indexed node.</span></span>  
  
 <span data-ttu-id="6909d-328">Quando a conversão de um valor existente no tipo de dados especificado falha, a operação de inserção (no índice) não falha; entretanto, um valor nulo é inserido na tabela de dados do índice.</span><span class="sxs-lookup"><span data-stu-id="6909d-328">When casting an existing value to the specified data type fails, the insert operation (into the index) does not fail; however, a null value is inserted into the data table of the index.</span></span>  
  
### <a name="maxlength-optimization-hint"></a><span data-ttu-id="6909d-329">Dica de otimização MAXLENGTH</span><span class="sxs-lookup"><span data-stu-id="6909d-329">MAXLENGTH optimization hint</span></span>  
 <span data-ttu-id="6909d-330">Aplica-se a: Tipos de dados XQuery</span><span class="sxs-lookup"><span data-stu-id="6909d-330">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="6909d-331">A dica de otimização MAXLENGTH permite limitar o comprimento dos dados xs:string.</span><span class="sxs-lookup"><span data-stu-id="6909d-331">The MAXLENGTH optimization hint lets you limit the length of xs:string data.</span></span> <span data-ttu-id="6909d-332">MAXLENGTH não é relevante para tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , desde que você especifique o comprimento quando especificar os tipos de dados VARCHAR ou NVARCHAR.</span><span class="sxs-lookup"><span data-stu-id="6909d-332">MAXLENGTH is not relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types since you specify the length when you specify the VARCHAR or NVARCHAR date types.</span></span>  
  
 <span data-ttu-id="6909d-333">Quando uma cadeia de caracteres existente é maior que MAXLENGTH especificado, a inserção desse valor no índice falha.</span><span class="sxs-lookup"><span data-stu-id="6909d-333">When an existing string is longer than the specified MAXLENGTH, then inserting that value into the index fails.</span></span>  
  

  
##  <a name="sample-xml-document-for-examples"></a><a name="sample"></a> <span data-ttu-id="6909d-334">Documento XML de exemplo</span><span class="sxs-lookup"><span data-stu-id="6909d-334">Sample XML Document for Examples</span></span>  
 <span data-ttu-id="6909d-335">O documento XML de exemplo a seguir é referenciado nos exemplos deste tópico:</span><span class="sxs-lookup"><span data-stu-id="6909d-335">The following sample XML document is referenced in the examples in this topic:</span></span>  
  
```xml  
<a>  
    <b>  
         <c atc="aa">10</c>  
         <c atc="bb">15</c>  
         <d atd1="dd" atd2="ddd">md </d>  
    </b>  
     <b>  
        <c></c>  
        <c atc="">117</c>  
     </b>  
</a>  
```  
  

  
## <a name="see-also"></a><span data-ttu-id="6909d-336">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6909d-336">See Also</span></span>  
 <span data-ttu-id="6909d-337">[Índices XML Seletivos &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span><span class="sxs-lookup"><span data-stu-id="6909d-337">[Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span></span>  
 [<span data-ttu-id="6909d-338">Criar, alterar e remover índices XML seletivos</span><span class="sxs-lookup"><span data-stu-id="6909d-338">Create, Alter, and Drop Selective XML Indexes</span></span>](../xml/create-alter-and-drop-selective-xml-indexes.md)  
  
  
