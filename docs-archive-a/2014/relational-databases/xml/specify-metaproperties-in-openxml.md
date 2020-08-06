---
title: Especificar metapropriedades no OPENXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- overflow in XML document [SQL Server]
- metaproperties [XML in SQL Server]
- unconsumed data
- extracting information of XML nodes [SQL Server]
- OPENXML statement, metaproperties
ms.assetid: 29bfd1c6-3f9a-43c4-924a-53d438e442f4
author: rothja
ms.author: jroth
ms.openlocfilehash: c52d1162aa495deff8a0fde314fdcde0735d9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682187"
---
# <a name="specify-metaproperties-in-openxml"></a><span data-ttu-id="e4a1a-102">Especificar metapropriedades no OPENXML</span><span class="sxs-lookup"><span data-stu-id="e4a1a-102">Specify Metaproperties in OPENXML</span></span>
  <span data-ttu-id="e4a1a-103">Atributos de metapropriedades em um documento XML são atributos que descrevem as propriedades de um item XML, como elemento, atributo ou qualquer outro nó DOM.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-103">Metaproperty attributes in an XML document are attributes that describe the properties of an XML item, such as element, attribute, or any other DOM node.</span></span> <span data-ttu-id="e4a1a-104">Esses atributos não existem fisicamente no documento de texto XML.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-104">These attributes do not physically exist in the XML document text.</span></span> <span data-ttu-id="e4a1a-105">No entanto o OPENXML fornece essas metapropriedades para todos os itens XML.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-105">However, OPENXML provides these metaproperties for all the XML items.</span></span> <span data-ttu-id="e4a1a-106">Essas metapropriedades permitem extrair informações, como posicionamento local e informações de namespace, de nós XML.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-106">These metaproperties allow you to extract information, such as local positioning and namespace information, of XML nodes.</span></span> <span data-ttu-id="e4a1a-107">Essas informações fornecem mais detalhes do que os que estão aparentes na representação textual.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-107">This information provides you with more details than are apparent in the textual representation.</span></span>  
  
 <span data-ttu-id="e4a1a-108">Você pode mapear essas metapropriedades para as colunas do conjunto de linhas em uma instrução OPENXML usando o parâmetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="e4a1a-108">You can map these metaproperties to the rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span> <span data-ttu-id="e4a1a-109">As colunas conterão os valores das metapropriedades para as quais elas são mapeadas.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-109">The columns will contain the values of the metaproperties to which they are mapped.</span></span> <span data-ttu-id="e4a1a-110">Para obter mais informações sobre a sintaxe do OPENXML, consulte [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e4a1a-110">For more information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span>  
  
 <span data-ttu-id="e4a1a-111">Para acessar os atributos de metapropriedades, é fornecido um namespace que é específico ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-111">To access the metaproperty attributes, a namespace that is specific to SQL Server is provided.</span></span> <span data-ttu-id="e4a1a-112">Esse namespace **urn:schemas-microsoft-com:xml-metaprop** permite que o usuário acesse os atributos de metapropriedades.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-112">This namespace, **urn:schemas-microsoft-com:xml-metaprop** allows the user to access the metaproperty attributes.</span></span> <span data-ttu-id="e4a1a-113">Se o resultado de uma consulta OPENXML for retornado em uma formato de tabela de borda, a tabela de borda conterá uma coluna para cada atributo de metapropriedade, exceto a metapropriedade **xmltext** .</span><span class="sxs-lookup"><span data-stu-id="e4a1a-113">If the result of an OPENXML query is returned in an edge table format, the edge table contains one column for each metaproperty attribute, except the **xmltext** metaproperty.</span></span>  
  
 <span data-ttu-id="e4a1a-114">Alguns dos atributos de metapropriedade são usados para fins de processamento.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-114">Some of the metaproperty attributes are used for processing purposes.</span></span> <span data-ttu-id="e4a1a-115">Por exemplo, o atributo da metapropriedade **xmltext** é usado para manipulação de estouro.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-115">For example, the **xmltext** metaproperty attribute is used for overflow handling.</span></span> <span data-ttu-id="e4a1a-116">A manipulação de estouro faz referência a dados não consumidos e não processados no documento.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-116">Overflow handling refers to the unconsumed, unprocessed data in the document.</span></span> <span data-ttu-id="e4a1a-117">Uma das colunas no conjunto de linhas gerado por OPENXML pode ser identificada como a coluna de estouro.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-117">One of the columns in the rowset that is generated by OPENXML can be identified as the overflow column.</span></span> <span data-ttu-id="e4a1a-118">Isso é feito mapeando a coluna para a metapropriedade **xmltext** usando o parâmetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="e4a1a-118">You do this by mapping it to the **xmltext** metaproperty by using the *ColPattern* parameter.</span></span> <span data-ttu-id="e4a1a-119">A coluna então recebe os dados excedentes.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-119">The column then receives the overflow data.</span></span> <span data-ttu-id="e4a1a-120">O parâmetro *flags* determina se a coluna contém tudo ou apenas dados não consumidos.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-120">The *flags* parameter determines whether the column contains everything or only the unconsumed data.</span></span>  
  
 <span data-ttu-id="e4a1a-121">A tabela a seguir lista os atributos de metapropriedade que cada elemento XML analisado possui.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-121">The following table lists the metaproperty attributes that each parsed XML element possesses.</span></span> <span data-ttu-id="e4a1a-122">Esses atributos de metapropriedade podem ser acessados usando o namespace **urn:schemas-microsoft-com:xml-metaprop**.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-122">These metaproperty attributes can be accessed by using the namespace **urn:schemas-microsoft-com:xml-metaprop**.</span></span> <span data-ttu-id="e4a1a-123">Qualquer valor definido pelo usuário diretamente no documento XML usando essas metapropriedades é ignorado.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-123">Any value that the user sets directly in the XML document by using these metaproperties is ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4a1a-124">Não é possível fazer referência a essas metapropriedades em qualquer navegação XPath.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-124">You cannot reference these metaproperties in any XPath navigation.</span></span>  
  
|<span data-ttu-id="e4a1a-125">Atributo de metapropriedade</span><span class="sxs-lookup"><span data-stu-id="e4a1a-125">Metaproperty attribute</span></span>|<span data-ttu-id="e4a1a-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="e4a1a-126">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="e4a1a-127">**\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-127">**\@mp:id**</span></span>|<span data-ttu-id="e4a1a-128">Fornece um identificador de todo o documento gerado pelo sistema do nó DOM.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-128">Provides a system-generated, document-wide identifier of the DOM node.</span></span> <span data-ttu-id="e4a1a-129">Desde que o documento não seja reanalisado, essa ID faz referência ao mesmo nó XML.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-129">As long as the document is not reparsed, this ID refers to the same XML node.</span></span><br /><br /> <span data-ttu-id="e4a1a-130">Uma ID de XML de **0** indica que o elemento é um elemento raiz.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-130">An XML ID of **0** indicates that the element is a root element.</span></span> <span data-ttu-id="e4a1a-131">A ID de XML de seu pai é NULL.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-131">Its parent XML ID is NULL.</span></span>|  
|<span data-ttu-id="e4a1a-132">**\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-132">**\@mp:localname**</span></span>|<span data-ttu-id="e4a1a-133">Armazena a parte local do nome do nó.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-133">Stores the local part of the name of the node.</span></span> <span data-ttu-id="e4a1a-134">Ele é usado com um URI de namespace e de prefixo para nomear nós de elementos ou atributos.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-134">It is used with a prefix and a namespace URI to name element or attribute nodes.</span></span>|  
|<span data-ttu-id="e4a1a-135">**\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-135">**\@mp:namespaceuri**</span></span>|<span data-ttu-id="e4a1a-136">Fornece o URI do namespace do elemento atual.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-136">Provides the namespace URI of the current element.</span></span> <span data-ttu-id="e4a1a-137">Se o valor desse atributo for NULL, nenhum namespace estará presente</span><span class="sxs-lookup"><span data-stu-id="e4a1a-137">If the value of this attribute is NULL, no namespace is present</span></span>|  
|<span data-ttu-id="e4a1a-138">**\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-138">**\@mp:prefix**</span></span>|<span data-ttu-id="e4a1a-139">Armazena o prefixo do namespace do nome do elemento atual.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-139">Stores the namespace prefix of the current element name.</span></span><br /><br /> <span data-ttu-id="e4a1a-140">Se nenhum prefixo estiver presente (NULL) e um URI for fornecido, ele indicará que o namespace identificado é o namespace padrão.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-140">If no prefix is present (NULL) and a URI is given, it indicates that the specified namespace is the default namespace.</span></span> <span data-ttu-id="e4a1a-141">Se nenhum URI for fornecido, nenhum namespace será anexado.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-141">If no URI is given, no namespace is attached.</span></span>|  
|<span data-ttu-id="e4a1a-142">**\@mp:prev**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-142">**\@mp:prev**</span></span>|<span data-ttu-id="e4a1a-143">Armazena o irmão anterior relativo a um nó.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-143">Stores the previous sibling relative to a node.</span></span> <span data-ttu-id="e4a1a-144">Isso fornece informações sobre a ordenação de elementos no documento.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-144">This provides information about the ordering of elements in the document.</span></span><br /><br /> <span data-ttu-id="e4a1a-145">**\@mp:prev** contém a ID de XML do irmão anterior que tem o mesmo elemento pai.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-145">**\@mp:prev** contains the XML ID of the previous sibling that has the same parent element.</span></span> <span data-ttu-id="e4a1a-146">Se um elemento estiver à frente da lista de irmãos, **\@mp:prev** será NULL.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-146">If an element is at the front of the sibling list, **\@mp:prev** is NULL.</span></span>|  
|<span data-ttu-id="e4a1a-147">**\@mp:xmltext**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-147">**\@mp:xmltext**</span></span>|<span data-ttu-id="e4a1a-148">Usado para fins de processamento.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-148">Used for processing purposes.</span></span> <span data-ttu-id="e4a1a-149">É a serialização textual do elemento e seus atributos e também dos subelementos, conforme usado na manipulação de estouro do OPENXML.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-149">It is the textual serialization of the element and its attributes, and also the subelements, as used in the overflow handling of OPENXML.</span></span>|  
  
 <span data-ttu-id="e4a1a-150">Essa tabela mostra as propriedades pai adicionais que são fornecidas e que permitem recuperar informações sobre a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-150">This table shows the additional parent properties that are provided and which allow you to retrieve information about the hierarchy.</span></span>  
  
|<span data-ttu-id="e4a1a-151">Atributo de metapropriedade pai</span><span class="sxs-lookup"><span data-stu-id="e4a1a-151">Parent metaproperty attribute</span></span>|<span data-ttu-id="e4a1a-152">Descrição</span><span class="sxs-lookup"><span data-stu-id="e4a1a-152">Description</span></span>|  
|-----------------------------------|-----------------|  
|<span data-ttu-id="e4a1a-153">**\@mp:parentid**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-153">**\@mp:parentid**</span></span>|<span data-ttu-id="e4a1a-154">Corresponde a **../\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-154">Corresponds to **../\@mp:id**</span></span>|  
|<span data-ttu-id="e4a1a-155">**\@mp:parentlocalname**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-155">**\@mp:parentlocalname**</span></span>|<span data-ttu-id="e4a1a-156">Corresponde a **../\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-156">Corresponds to **../\@mp:localname**</span></span>|  
|<span data-ttu-id="e4a1a-157">**\@mp:parentnamespacerui**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-157">**\@mp:parentnamespacerui**</span></span>|<span data-ttu-id="e4a1a-158">Corresponde a **../\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-158">Corresponds to **../\@mp:namespaceuri**</span></span>|  
|<span data-ttu-id="e4a1a-159">**\@mp:parentprefix**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-159">**\@mp:parentprefix**</span></span>|<span data-ttu-id="e4a1a-160">Corresponde a **../\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="e4a1a-160">Corresponds to **../\@mp:prefix**</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="e4a1a-161">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e4a1a-161">Examples</span></span>  
 <span data-ttu-id="e4a1a-162">Os exemplos seguintes ilustram como o OPENXML é usado para criar exibições de conjunto de linhas diferentes.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-162">The following examples illustrate how OPENXML is used to create different rowset views.</span></span>  
  
### <a name="a-mapping-the-openxml-rowset-columns-to-the-metaproperties"></a><span data-ttu-id="e4a1a-163">a.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-163">A.</span></span> <span data-ttu-id="e4a1a-164">Mapeando colunas do conjunto de linhas OPENXML para as metapropriedades</span><span class="sxs-lookup"><span data-stu-id="e4a1a-164">Mapping the OPENXML rowset columns to the metaproperties</span></span>  
 <span data-ttu-id="e4a1a-165">Este exemplo usa OPENXML para criar uma exibição do conjunto de linhas do documento XML de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-165">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="e4a1a-166">Especificamente, ele mostra como os vários atributos de metapropriedade podem ser mapeados para colunas do conjunto de linhas em uma instrução OPENXML usando o parâmetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="e4a1a-166">Specifically, it shows how the various metaproperty attributes can be mapped to rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="e4a1a-167">A instrução OPENXML ilustra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-167">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="e4a1a-168">A coluna **id** é mapeada ao atributo de metapropriedade **\@mp:id** e indica que a coluna contém a ID de XML exclusiva do elemento gerado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-168">The **id** column is mapped to the **\@mp:id** metaproperty attribute and indicates that the column contains the system-generated unique XML ID of the element.</span></span>  
  
-   <span data-ttu-id="e4a1a-169">A coluna **parent** é mapeada para o **\@@mp:parentid** e indica que a coluna contém a ID de XML do pai do elemento.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-169">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent of the element.</span></span>  
  
-   <span data-ttu-id="e4a1a-170">A coluna **parentLocalName** é mapeada para **\@mp:parentlocalname** e indica que a coluna contém o nome local do pai.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-170">The **parentLocalName** column is mapped to **\@mp:parentlocalname** and indicates that the column contains the local name of the parent.</span></span>  
  
 <span data-ttu-id="e4a1a-171">Em seguida, a instrução SELECT retorna o conjunto de linhas fornecido por OPENXML:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-171">The SELECT statement then returns the rowset that is provided by OPENXML:</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- Sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (id int '@mp:id',   
            oid char(5),   
            date datetime,   
            amount real,   
            parentIDNo int '@mp:parentid',   
            parentLocalName varchar(40) '@mp:parentlocalname')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="e4a1a-172">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-172">This is the result:</span></span>  
  
```  
id   oid         date                amount    parentIDNo  parentLocalName    
--- ------- ---------------------- ---------- ------------ ---------------  
6    O1    1996-01-20 00:00:00.000     3.5         2        Customer  
10   O2    1997-04-30 00:00:00.000     13.4        2        Customer  
19   O3    1999-07-14 00:00:00.000     100.0       15       Customer  
25   O4    1996-01-20 00:00:00.000     10000.0     15       Customer  
```  
  
### <a name="b-retrieving-the-whole-xml-document"></a><span data-ttu-id="e4a1a-173">B.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-173">B.</span></span> <span data-ttu-id="e4a1a-174">Recuperando o documento XML inteiro</span><span class="sxs-lookup"><span data-stu-id="e4a1a-174">Retrieving the whole XML document</span></span>  
 <span data-ttu-id="e4a1a-175">Neste exemplo, OPENXML é usado para criar a exibição do conjunto de linhas de uma coluna do documento XML de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-175">In this example, OPENXML is used to create a one-column rowset view of the sample XML document.</span></span> <span data-ttu-id="e4a1a-176">Esta coluna, **Col1**, é mapeada para a metapropriedade **xmltext** e se torna uma coluna de estouro.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-176">This column, **Col1**, is mapped to the **xmltext** metaproperty and becomes an overflow column.</span></span> <span data-ttu-id="e4a1a-177">Como resultado, a coluna recebe os dados não consumidos.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-177">As a result, the column receives the unconsumed data.</span></span> <span data-ttu-id="e4a1a-178">Nesse caso, o documento inteiro.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-178">In this case, it is the whole document.</span></span>  
  
 <span data-ttu-id="e4a1a-179">Em seguida, a instrução SELECT retorna o conjunto de linhas completo.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-179">The SELECT statement then returns the complete rowset.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
SET @doc = N'<?xml version="1.0"?>  
<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
     <MyTag>Testing to see if all the subelements are returned</MyTag>  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/')  
   WITH (Col1 ntext '@mp:xmltext')  
```  
  
 <span data-ttu-id="e4a1a-180">Para recuperar o documento inteiro sem a declaração XML, a consulta pode ser especificada conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-180">To retrieve the whole document without the XML declaration, the query can be specified as shown in the following:</span></span>  
  
```  
SELECT *  
FROM OPENXML (@idoc, '/root')  
   WITH (Col1 ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="e4a1a-181">A consulta retorna o elemento raiz que tem a raiz do nome e os dados contidos pelo elemento raiz.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-181">The query returns the root element that has the name root and the data that is contained by the root element</span></span>  
  
### <a name="c-specifying-the-xmltext-metaproperty-to-retrieve-the-unconsumed-data-in-a-column"></a><span data-ttu-id="e4a1a-182">C.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-182">C.</span></span> <span data-ttu-id="e4a1a-183">Especificando a metapropriedade xmltext para recuperar os dados não consumidos em uma coluna</span><span class="sxs-lookup"><span data-stu-id="e4a1a-183">Specifying the xmltext metaproperty to retrieve the unconsumed data in a column</span></span>  
 <span data-ttu-id="e4a1a-184">Este exemplo usa OPENXML para criar uma exibição do conjunto de linhas do documento XML de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-184">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="e4a1a-185">O exemplo mostra como recuperar os dados XML não consumidos mapeamento o atributo de metapropriedade **xmltext** para uma coluna do conjunto de linhas no OPENXML.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-185">The example shows how to retrieve unconsumed XML data by mapping the **xmltext** metaproperty attribute to a rowset column in OPENXML.</span></span>  
  
 <span data-ttu-id="e4a1a-186">A coluna **comment** é identificada como a coluna de estouro mapeando-a para a metapropriedade **\@mp:xmltext**.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-186">The **comment** column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span> <span data-ttu-id="e4a1a-187">O parâmetro *flags* é definido como **9** (XML_ATTRIBUTE e XML_NOCOPY).</span><span class="sxs-lookup"><span data-stu-id="e4a1a-187">The *flags* parameter is set to **9** (XML_ATTRIBUTE and XML_NOCOPY).</span></span> <span data-ttu-id="e4a1a-188">Isso indica mapeamento **centrado em atributo** e indica que apenas os dados não consumidos devem ser copiados para a coluna de estouro.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-188">This indicates **attribute-centric** mapping and indicates that only the unconsumed data should be copied to the overflow column.</span></span>  
  
 <span data-ttu-id="e4a1a-189">Em seguida, a instrução SELECT retorna o conjunto de linhas fornecido por OPENXML:</span><span class="sxs-lookup"><span data-stu-id="e4a1a-189">The SELECT statement then returns the rowset provided by OPENXML.</span></span>  
  
 <span data-ttu-id="e4a1a-190">Neste exemplo, a metapropriedade **\@mp:parentlocalname** é definida para uma coluna, **ParentLocalName**, no conjunto de linhas gerado por OPENXML.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-190">In this example, the **\@mp:parentlocalname** metaproperty is set for a column, **ParentLocalName**, in the rowset generated by OPENXML.</span></span> <span data-ttu-id="e4a1a-191">Como resultado, essa coluna contém o nome local do elemento pai.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-191">As a result, this column contains the local name of the parent element.</span></span>  
  
 <span data-ttu-id="e4a1a-192">São especificadas duas colunas adicionais no conjunto de linhas, **parent** e **comment**.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-192">Two additional columns are specified in the rowset, **parent** and **comment**.</span></span> <span data-ttu-id="e4a1a-193">A coluna **parent** é mapeada para **\@mp:parentid** e indica que a coluna contém a ID de XML do elemento pai do elemento.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-193">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent element of the element.</span></span> <span data-ttu-id="e4a1a-194">A coluna comment é identificada como a coluna de estouro mapeando-a para a metapropriedade **\@mp:xmltext**.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-194">The comment column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>  
'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (oid char(5),   
            date datetime,  
            comment ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="e4a1a-195">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-195">This is the result.</span></span> <span data-ttu-id="e4a1a-196">Como as colunas oid e date já estão consumidas, elas não são exibidas na coluna de estouro.</span><span class="sxs-lookup"><span data-stu-id="e4a1a-196">Because the oid columns and date columns are already consumed, they do not appear in the overflow column.</span></span>  
  
```  
oid   date                        comment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
----- --------------------------- ----------------------------------------  
O1    1996-01-20 00:00:00.000     <Order amount="3.5"/>  
O2    1997-04-30 00:00:00.000     <Order amount="13.4">Customer was very   
                                   satisfied</Order>  
O3    1999-07-14 00:00:00.000     <Order amount="100" note="Wrap it blue   
                                   white red"><Urgency>   
                                   Important</Urgency></Order>  
O4    1996-01-20 00:00:00.000     <Order amount="10000"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4a1a-197">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e4a1a-197">See Also</span></span>  
 <span data-ttu-id="e4a1a-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e4a1a-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="e4a1a-199">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e4a1a-199">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
