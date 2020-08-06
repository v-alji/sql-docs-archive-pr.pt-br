---
title: Formatação XML do lado do cliente (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- FOR XML clause, formatting
- middle tier XML formatting [SQLXML]
- client-side XML formatting
- client-side-xml attribute
ms.assetid: 9630a21d-a93b-4d3b-8a25-c4b32399f993
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4a680d79a25d24ebdf779b41fd3be5a5d6a605
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575713"
---
# <a name="client-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="6c145-102">Formatação XML do lado do cliente (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="6c145-102">Client-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="6c145-103">Este tópico fornece informações sobre formatação de XML do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c145-103">This topic provides information about client-side XML formatting.</span></span> <span data-ttu-id="6c145-104">A formatação do lado do cliente refere-se à formatação de XML na camada intermediária.</span><span class="sxs-lookup"><span data-stu-id="6c145-104">Client-side formatting refers to the formatting of XML on the middle tier.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c145-105">Este tópico fornece informações adicionais sobre como usar a cláusula FOR XML no lado do cliente e supõe que você já esteja familiarizado com a cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="6c145-105">This topic provides additional information about using the FOR XML clause on the client side, and assumes you are already familiar with the FOR XML clause.</span></span> <span data-ttu-id="6c145-106">Para obter mais informações sobre o FOR XML, consulte [construindo XML Using for XML](../../xml/for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6c145-106">For more information about FOR XML, see [Constructing XML Using FOR XML](../../xml/for-xml-sql-server.md).</span></span>  
  
 <span data-ttu-id="6c145-107">**Importante** Para usar a funcionalidade para XML do lado do cliente com o novo `xml` tipo de dados, os clientes sempre devem usar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de dados do Native Client (SQLNCLI11) em vez do provedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="6c145-107">**Important** To use client-side FOR XML functionality with the new `xml` data type, clients should always use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) data provider instead of the SQLOLEDB provider.</span></span> <span data-ttu-id="6c145-108">SQLNCLI11 é a última versão do provedor do SQL Server e compreende plenamente os tipos de dados introduzidos no [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c145-108">SQLNCLI11 is the latest version of the SQL Server provider and fully understands data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="6c145-109">O comportamento da cláusula FOR XML do lado do cliente com o provedor SQLOLEDB tratará os tipos de dados `xml` como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6c145-109">The behavior for client side FOR XML with the SQLOLEDB provider will treat `xml` data types as strings.</span></span>  
  
## <a name="formatting-xml-documents-on-the-client-side"></a><span data-ttu-id="6c145-110">Formatando documentos XML no lado do cliente</span><span class="sxs-lookup"><span data-stu-id="6c145-110">Formatting XML Documents on the Client Side</span></span>  
 <span data-ttu-id="6c145-111">Quando um aplicativo cliente executa a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="6c145-111">When a client application executes the following query:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
FOR XML RAW  
```  
  
 <span data-ttu-id="6c145-112">...só esta parte da consulta é enviada ao servidor:</span><span class="sxs-lookup"><span data-stu-id="6c145-112">...only this part of the query is sent to the server:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
```  
  
 <span data-ttu-id="6c145-113">O servidor executa a consulta e retorna um conjunto de linhas (que contém FirstName e LastNamecolumns) para o cliente.</span><span class="sxs-lookup"><span data-stu-id="6c145-113">The server executes the query and returns a rowset (which contains FirstName and LastNamecolumns) to the client.</span></span> <span data-ttu-id="6c145-114">A camada intermediária aplica as informações de FOR XML ao conjunto de linhas e retorna a formatação XML ao cliente.</span><span class="sxs-lookup"><span data-stu-id="6c145-114">The middle tier then applies the FOR XML transformation to the rowset and returns XML formatting to the client.</span></span>  
  
 <span data-ttu-id="6c145-115">De maneira similar, quando você executa uma consulta XPath, o servidor retorna o conjunto de linhas ao cliente e a transformação FOR XML EXPLICIT é aplicada ao conjunto de linhas no cliente, gerando a formatação XML desejada.</span><span class="sxs-lookup"><span data-stu-id="6c145-115">Similarly, when you execute an XPath query, the server returns the rowset to the client and the FOR XML EXPLICIT transformation is applied to the rowset on the client, generating the desired XML formatting.</span></span>  
  
 <span data-ttu-id="6c145-116">A tabela a seguir mostra os modos que você pode especificar com a cláusula FOR XML do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c145-116">The following table shows the modes you can specify with client-side FOR XML.</span></span>  
  
|<span data-ttu-id="6c145-117">Modo FOR XML do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="6c145-117">Client-side FOR XML mode</span></span>|<span data-ttu-id="6c145-118">Comentário</span><span class="sxs-lookup"><span data-stu-id="6c145-118">Comment</span></span>|  
|-------------------------------|-------------|  
|<span data-ttu-id="6c145-119">RAW</span><span class="sxs-lookup"><span data-stu-id="6c145-119">RAW</span></span>|<span data-ttu-id="6c145-120">Gera resultados idênticos quando especificado em FOR XML do lado do cliente ou do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="6c145-120">Produces identical results when specified in client-side or server-side FOR XML.</span></span>|  
|<span data-ttu-id="6c145-121">NESTED</span><span class="sxs-lookup"><span data-stu-id="6c145-121">NESTED</span></span>|<span data-ttu-id="6c145-122">É semelhante ao modo FOR XML AUTO no lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="6c145-122">Is similar to FOR XML AUTO mode on the server-side.</span></span>|  
|<span data-ttu-id="6c145-123">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="6c145-123">EXPLICIT</span></span>|<span data-ttu-id="6c145-124">É semelhante ao modo FOR XML EXPLICIT do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="6c145-124">Is similar to server-side FOR XML EXPLICIT mode.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="6c145-125">Se você especificar o modo AUTO e solicitar a formatação XML do lado do cliente, toda a consulta será enviada ao servidor, isto é, a formatação XML ocorrerá no servidor.</span><span class="sxs-lookup"><span data-stu-id="6c145-125">If you specify AUTO mode and request client-side XML formatting, the entire query is sent to the server; that is, XML formatting occurs on the server.</span></span> <span data-ttu-id="6c145-126">Isto será feito por conveniência, mas observe que o modo NESTED retorna os nomes das tabelas base como nomes de elemento no documento XML gerado.</span><span class="sxs-lookup"><span data-stu-id="6c145-126">This is done for convenience, but note that the NESTED mode returns base table names as element names in the XML document that is generated.</span></span> <span data-ttu-id="6c145-127">Alguns dos aplicativos que você grava podem exigir nomes de tabela base.</span><span class="sxs-lookup"><span data-stu-id="6c145-127">Some of the applications you write might require base table names.</span></span> <span data-ttu-id="6c145-128">Por exemplo, você pode executar um procedimento armazenado e carregar os dados resultantes em um Dataset (no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework) e gerar posteriormente um DiffGram para atualizar dados nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="6c145-128">For example, you might execute a stored procedure and load the resulting data in a Dataset (in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework), and then later generate a DiffGram to update data in the tables.</span></span> <span data-ttu-id="6c145-129">Em tal caso, você precisará das informações da tabela base e precisará usar o modo NESTED.</span><span class="sxs-lookup"><span data-stu-id="6c145-129">In such a case, you would need the base table information and you would have to use the NESTED mode.</span></span>  
  
## <a name="benefits-of-client-side-xml-formatting"></a><span data-ttu-id="6c145-130">Benefícios da formatação XML do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="6c145-130">Benefits of Client-side XML formatting</span></span>  
 <span data-ttu-id="6c145-131">A seguir, são descritos alguns benefícios da formatação XML no cliente.</span><span class="sxs-lookup"><span data-stu-id="6c145-131">The following are some benefits of formatting XML on the client.</span></span>  
  
### <a name="if-you-have-stored-procedures-on-the-server-that-return-a-single-rowset-you-can-request-client-side-for-xml-transformation-to-generate-an-xml"></a><span data-ttu-id="6c145-132">Se você tiver procedimentos armazenados no servidor que retornem um único conjunto de linhas, poderá solicitar que a transformação FOR XML do lado do cliente gere um XML.</span><span class="sxs-lookup"><span data-stu-id="6c145-132">If you have stored procedures on the server that return a single rowset, you can request client-side FOR XML transformation to generate an XML.</span></span>  
 <span data-ttu-id="6c145-133">Por exemplo, considere o procedimento armazenado a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c145-133">For example, consider the following stored procedure.</span></span> <span data-ttu-id="6c145-134">Esse procedimento retorna o nome e o sobrenome dos funcionários da tabela Person.Contact no banco de dados AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="6c145-134">This procedure returns the first and last names of employees from the Person.Contact table in the AdventureWorks database:</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects  
   WHERE name = 'GetContacts' AND type = 'P')  
   DROP PROCEDURE GetContacts  
GO  
CREATE PROCEDURE GetContacts  
AS  
    SELECT   FirstName, LastName  
    FROM     Person.Contact  
```  
  
 <span data-ttu-id="6c145-135">O exemplo de modelo XML a seguir executa o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="6c145-135">The following sample XML template executes the stored procedure.</span></span> <span data-ttu-id="6c145-136">A cláusula FOR XML é especificada depois do nome de procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="6c145-136">The FOR XML clause is specified after the stored procedure name.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    EXEC GetContacts FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="6c145-137">Como o atributo **XML do lado do cliente** é definido como 1 (true) no modelo, o procedimento armazenado é executado no servidor e o conjunto de linhas de duas colunas que é retornado pelo servidor é transformado em XML na camada intermediária e retornado ao cliente.</span><span class="sxs-lookup"><span data-stu-id="6c145-137">Because the **client-side-xml** attribute is set to 1 (true) in the template, the stored procedure is executed on the server and the two-column rowset that is returned by the server is transformed into XML on the middle tier and returned to the client.</span></span> <span data-ttu-id="6c145-138">(Somente um resultado parcial é mostrado aqui.)</span><span class="sxs-lookup"><span data-stu-id="6c145-138">(Only a partial result is shown here.)</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact FirstName="Catherine" LastName="Abel" />  
</ROOT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="6c145-139">Quando estiver usando o Provedor SQLXMLOLEDB ou as Classes Gerenciadas por SQLXML, você poderá usar a propriedade `ClientSideXml` para solicitar a formatação XML do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c145-139">When you are using the SQLXMLOLEDB Provider or SQLXML Managed Classes, you can use the `ClientSideXml` property to request client-side XML formatting.</span></span>  
  
### <a name="the-workload-is-more-balanced"></a><span data-ttu-id="6c145-140">A carga de trabalho é mais equilibrada.</span><span class="sxs-lookup"><span data-stu-id="6c145-140">The workload is more balanced.</span></span>  
 <span data-ttu-id="6c145-141">Como o cliente executa a formatação XML, a carga de trabalho é equilibrada entre o servidor e o cliente, liberando o servidor para fazer outras coisas.</span><span class="sxs-lookup"><span data-stu-id="6c145-141">Because the client does the XML formatting, the workload is balanced between the server and client, freeing the server to do other things.</span></span>  
  
## <a name="supporting-client-side-xml-formatting"></a><span data-ttu-id="6c145-142">Dando suporte à formatação XML do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="6c145-142">Supporting Client-side XML Formatting</span></span>  
 <span data-ttu-id="6c145-143">Para dar suporte à funcionalidade de formatação XML do lado do cliente, o SQLXML fornece:</span><span class="sxs-lookup"><span data-stu-id="6c145-143">To support the client-side XML formatting functionality, SQLXML provides:</span></span>  
  
-   <span data-ttu-id="6c145-144">Provedor SQLXMLOLEDB</span><span class="sxs-lookup"><span data-stu-id="6c145-144">SQLXMLOLEDB Provider</span></span>  
  
-   <span data-ttu-id="6c145-145">Classes gerenciadas SQLXML</span><span class="sxs-lookup"><span data-stu-id="6c145-145">SQLXML Managed Classes</span></span>  
  
-   <span data-ttu-id="6c145-146">Suporte de modelo XML avançado</span><span class="sxs-lookup"><span data-stu-id="6c145-146">Enhanced XML template support</span></span>  
  
-   <span data-ttu-id="6c145-147">Propriedade SqlXmlCommand. ClientSideXml</span><span class="sxs-lookup"><span data-stu-id="6c145-147">SqlXmlCommand.ClientSideXml property</span></span>  
  
     <span data-ttu-id="6c145-148">Você pode especificar a formatação do lado do cliente definindo essa propriedade das classes gerenciadas SQLXML como true.</span><span class="sxs-lookup"><span data-stu-id="6c145-148">You can specify client-side formatting by setting this property of the SQLXML managed classes to true.</span></span>  
  
## <a name="enhanced-xml-template-support"></a><span data-ttu-id="6c145-149">Suporte a modelos XML aprimorados</span><span class="sxs-lookup"><span data-stu-id="6c145-149">Enhanced XML Template Support</span></span>  
 <span data-ttu-id="6c145-150">A partir do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] , o modelo XML no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] foi aprimorado com a adição do atributo **XML do lado do cliente** .</span><span class="sxs-lookup"><span data-stu-id="6c145-150">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the XML template in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been enhanced with the addition of the **client-side-xml** attribute.</span></span> <span data-ttu-id="6c145-151">Se esse atributo for definido como true, XML será formatado no cliente.</span><span class="sxs-lookup"><span data-stu-id="6c145-151">If this attribute is set to true, XML is formatted on the client.</span></span> <span data-ttu-id="6c145-152">Observe que esse atributo de modelo é idêntico em funcionalidade para a propriedade ClientSideXML específica do provedor SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="6c145-152">Note that this template attribute is identical in functionality to the SQLXMLOLEDB Provider-specific ClientSideXML property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c145-153">Se você executar um modelo XML em um aplicativo ADO que está usando o provedor SQLXMLOLEDB e especificar tanto o atributo **XML do lado do cliente** no modelo quanto a propriedade ClientSideXML do provedor, o valor especificado no modelo terá precedência.</span><span class="sxs-lookup"><span data-stu-id="6c145-153">If you execute an XML template in an ADO application that is using the SQLXMLOLEDB Provider, and you specify both the **client-side-xml** attribute in the template and the provider ClientSideXML property, the value specified in the template takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c145-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6c145-154">See Also</span></span>  
 <span data-ttu-id="6c145-155">[Arquitetura da formatação XML do lado do cliente e do servidor &#40;SQLXML 4,0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="6c145-155">[Architecture of Client-side and Server-side XML Formatting &#40;SQLXML 4.0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="6c145-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6c145-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span></span>  
 <span data-ttu-id="6c145-157">[Considerações sobre segurança de FOR XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="6c145-157">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="6c145-158">[Suporte a tipo de dados XML no SQLXML 4,0](../xml-data-type-support-in-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="6c145-158">[xml Data Type Support in SQLXML 4.0](../xml-data-type-support-in-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="6c145-159">[Classes gerenciadas SQLXML](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="6c145-159">[SQLXML Managed Classes](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 <span data-ttu-id="6c145-160">[Formatação XML do lado do cliente versus do servidor &#40;SQLXML 4,0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="6c145-160">[Client-side vs. Server-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="6c145-161">[Objeto SqlXmlCommand &#40;classes gerenciadas SQLXML&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span><span class="sxs-lookup"><span data-stu-id="6c145-161">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span></span>  
 [<span data-ttu-id="6c145-162">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6c145-162">XML Data &#40;SQL Server&#41;</span></span>](../../xml/xml-data-sql-server.md)  
  
  
