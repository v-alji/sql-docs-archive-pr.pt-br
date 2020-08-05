---
title: Sintaxe de consulta XML para dados de relatório XML (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- namespaces [Reporting Services]
- data processing extensions [Reporting Services], data sources
- xmldp [Reporting Services]
- XML [Reporting Services], data retrieval
ms.assetid: d203886f-faa1-4a02-88f5-dd4c217181ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62dde2b3ab18b5edb5c3786d39173fea3a0854ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569109"
---
# <a name="xml-query-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="4c5b8-102">Sintaxe de consulta XML para dados de relatório XML (SSRS)</span><span class="sxs-lookup"><span data-stu-id="4c5b8-102">XML Query Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="4c5b8-103">No [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], é possível criar conjuntos de dados para fontes de dados XML.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can create datasets for XML data sources.</span></span> <span data-ttu-id="4c5b8-104">Após definir uma fonte de dados, crie uma consulta para o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-104">After you define a data source, you create a query for the dataset.</span></span> <span data-ttu-id="4c5b8-105">Dependendo do tipo de dados XML apontado pela fonte de dados, a consulta do conjunto de dados é criada incluindo uma `Query` XML ou um caminho de elemento.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-105">Depending on the type of XML data pointed to by the data source, you create the dataset query by including an XML `Query` or an element path.</span></span> <span data-ttu-id="4c5b8-106">Um XML `Query` começa com uma **\<Query>** marca e inclui namespaces e elementos XML que variam de acordo com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-106">An XML `Query` starts with a **\<Query>** tag and includes namespaces and XML elements that vary depending on the data source.</span></span> <span data-ttu-id="4c5b8-107">Um caminho de elemento não depende do namespace e especifica quais nós e atributos de nós devem ser usados nos dados XML subjacentes com uma sintaxe do tipo XPath.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-107">An element path is namespace-independent and specifies which nodes and node attributes to use from the underlying XML data with an XPath-like syntax.</span></span> <span data-ttu-id="4c5b8-108">Para obter mais informações sobre os caminhos de elemento, consulte [Sintaxe do caminho de elemento para dados de relatório XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4c5b8-108">For more information about element paths, see [Element Path Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="4c5b8-109">É possível criar uma fonte de dados XML para os seguintes tipos de dados XML:</span><span class="sxs-lookup"><span data-stu-id="4c5b8-109">You can create an XML data source for the following types of XML data:</span></span>  
  
-   <span data-ttu-id="4c5b8-110">Documentos Xml apontados por uma URL que usa protocolo http</span><span class="sxs-lookup"><span data-stu-id="4c5b8-110">Xml documents pointed to by a URL using http protocol</span></span>  
  
-   <span data-ttu-id="4c5b8-111">Pontos de extremidade do serviço Web que retornam dados XML</span><span class="sxs-lookup"><span data-stu-id="4c5b8-111">Web service endpoints that return XML data</span></span>  
  
-   <span data-ttu-id="4c5b8-112">Dados XML inseridos</span><span class="sxs-lookup"><span data-stu-id="4c5b8-112">Embedded XML data</span></span>  
  
 <span data-ttu-id="4c5b8-113">Como especificar uma `Query` XML ou um caminho de elemento no tipo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-113">How you specify an XML `Query` or an element path depends on the type of XML data.</span></span>  
  
 <span data-ttu-id="4c5b8-114">Para um documento XML, a `Query` XML é opcional.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-114">For an XML document, the XML `Query` is optional.</span></span> <span data-ttu-id="4c5b8-115">Se ela for incluída, poderá conter um `ElementPath` XML opcional.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-115">If it is included, it can contain an optional XML `ElementPath`.</span></span> <span data-ttu-id="4c5b8-116">O valor do `ElementPath` XML usa a sintaxe de caminho de elemento.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-116">The value of the XML `ElementPath` uses the element path syntax.</span></span> <span data-ttu-id="4c5b8-117">A `Query` XML e o `ElementPath` XML são incluídos para processar namespaces corretamente quando exigidos pelos dados XML da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-117">You include the XML `Query` and XML `ElementPath` to process namespaces correctly when it is needed by the XML data from the data source.</span></span>  
  
 <span data-ttu-id="4c5b8-118">Para um ponto de extremidade de serviço Web apontado por uma URL de cadeia de conexão, a `Query` XML define o método de serviço Web, a ação SOAP ou ambos.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-118">For a Web service endpoint pointed to by a connection string URL, the XML `Query` defines either the Web service method, the SOAP action, or both.</span></span> <span data-ttu-id="4c5b8-119">O provedor de dados XML cria uma solicitação de serviço Web que recupera dados XML a serem usados no relatório.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-119">The XML data provider creates a Web service request that retrieves XML data to use for the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c5b8-120">Quando um namespace de serviço Web inclui um caractere de barra (`/)`, inclua o método de serviço Web e a ação SOAP de modo que a extensão de processamento de dados XML possa derivar o namespace corretamente.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-120">When a Web service namespace includes a forward slash (`/)` character, include both the Web service method and the SOAP action so that the XML data processing extension can derive the namespace correctly.</span></span>  
  
 <span data-ttu-id="4c5b8-121">Para um documento XML inserido, a `Query` XML define os dados XML inseridos a serem usados, inclui espaços para nome opcionais e contém um `ElementPath` XML opcional.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-121">For an embedded XML document, the XML `Query` defines the embedded XML data to use, includes optional namespaces, and contains an optional XML `ElementPath`..</span></span>  
  
## <a name="specifying-query-parameters-for-xml-data"></a><span data-ttu-id="4c5b8-122">Especificando parâmetros de consulta para dados XML</span><span class="sxs-lookup"><span data-stu-id="4c5b8-122">Specifying Query Parameters for XML Data</span></span>  
 <span data-ttu-id="4c5b8-123">É possível especificar parâmetros de consulta para documentos XML.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-123">You can specify query parameters for XML documents.</span></span>  
  
-   <span data-ttu-id="4c5b8-124">Para solicitações de URL, os parâmetros de consulta são incluídos como parâmetros de URL padrão.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-124">For URL requests, the query parameters are included as standard URL parameters.</span></span>  
  
-   <span data-ttu-id="4c5b8-125">Para solicitações de serviço Web, os parâmetros de consulta são passados para o método de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-125">For Web service requests, query parameters are passed to the Web service method.</span></span> <span data-ttu-id="4c5b8-126">Para definir um parâmetro de consulta, use a página **Parâmetros** da caixa de diálogo **Propriedades do Conjunto de Dados** .</span><span class="sxs-lookup"><span data-stu-id="4c5b8-126">To define a query parameter, use the **Parameters** page of the **Dataset Properties** dialog box.</span></span> <span data-ttu-id="4c5b8-127">Para obter mais informações, consulte [Caixa de Diálogo Propriedades de Conjunto de Dados, Parâmetros](dataset-properties-dialog-box-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4c5b8-127">For more information, see [Dataset Properties Dialog Box, Parameters](dataset-properties-dialog-box-parameters.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="4c5b8-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4c5b8-128">Example</span></span>  
 <span data-ttu-id="4c5b8-129">Os exemplos na seguinte tabela ilustram como recuperar dados do serviço Web Servidor de Relatórios, de um documento XML e de dados XML inseridos.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-129">The examples in the following table illustrate how to retrieve data from the Report Server Web service, an XML document, and embedded XML data.</span></span>  
  
|<span data-ttu-id="4c5b8-130">Fonte de dados XML</span><span class="sxs-lookup"><span data-stu-id="4c5b8-130">XML data source</span></span>|<span data-ttu-id="4c5b8-131">Exemplo de consulta</span><span class="sxs-lookup"><span data-stu-id="4c5b8-131">Query example</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="4c5b8-132">Dados XML de serviço Web do método ListChildren .</span><span class="sxs-lookup"><span data-stu-id="4c5b8-132">Web service XML data from ListChildren method.</span></span>|`<Query>`<br /><br /> `<Method Name="ListChildren" Namespace="https://schemas.microsoft.com/sqlserver/2005/06/30/reporting/reportingservices" />`<br /><br /> `</Query>`|  
|<span data-ttu-id="4c5b8-133">Dados XML de serviço Web do SoapAction.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-133">Web service XML data from SoapAction.</span></span>|`<Query xmlns=namespace>`<br /><br /> `<SoapAction>http://schemas/microsoft.com/sqlserver/2005/03/23/reporting/reportingservices/ListChildren</SoapAction>`<br /><br /> `</Query>`|  
|<span data-ttu-id="4c5b8-134">Documento XML ou dados XML inseridos que usam namespaces.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-134">XML Document or embedded XML data that uses namespaces.</span></span><br /><br /> <span data-ttu-id="4c5b8-135">Elemento de consulta que especifica namespaces para um caminho de elemento.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-135">Query element specifying namespaces for an element path.</span></span>|`<Query xmlns:es="https://schemas.microsoft.com/StandardSchemas/ExtendedSales">`<br /><br /> `<ElementPath>/Customers/Customer/Orders/Order/es:LineItems/es:LineItem</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="4c5b8-136">Documento XML inserido.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-136">Embedded XML document.</span></span>|`<Query>`<br /><br /> `<XmlData>`<br /><br /> `<Customers>`<br /><br /> `<Customer ID="1">Bobby</Customer>`<br /><br /> `</Customers>`<br /><br /> `</XmlData>`<br /><br /> `<ElementPath>Customer {@}</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="4c5b8-137">Documento XML que usa padrão.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-137">XML document that uses default.</span></span>|<span data-ttu-id="4c5b8-138">*Nenhuma consulta*.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-138">*No query*.</span></span><br /><br /> <span data-ttu-id="4c5b8-139">O caminho de elemento deriva do próprio documento XML e independe do namespace.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-139">The element path is derived from the XML document itself and is namespace-independent.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="4c5b8-140">O primeiro exemplo de serviço Web lista o conteúdo do servidor de relatório que usa o método <xref:ReportService2006.ReportingService2006.ListChildren%2A> .</span><span class="sxs-lookup"><span data-stu-id="4c5b8-140">The first Web service example lists the contents of the report server that uses the <xref:ReportService2006.ReportingService2006.ListChildren%2A> method.</span></span> <span data-ttu-id="4c5b8-141">Para executar essa consulta, é necessário criar uma nova fonte de dados e definir a cadeia de conexão como http://localhost/reportserver/reportservice2006.asmx.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-141">To run this query, you must create a new data source and set the connection string to http://localhost/reportserver/reportservice2006.asmx.</span></span> <span data-ttu-id="4c5b8-142">O método <xref:ReportService2006.ReportingService2006.ListChildren%2A> utiliza dois parâmetros: `Item` e `Recursive`.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-142">The <xref:ReportService2006.ReportingService2006.ListChildren%2A> method takes two parameters: `Item` and `Recursive`.</span></span> <span data-ttu-id="4c5b8-143">Defina o valor padrão do `Item` como `/` e `Recursive` como `1`.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-143">Set the default value for `Item` to `/` and `Recursive` to `1`.</span></span>  
  
## <a name="specifying-namespaces"></a><span data-ttu-id="4c5b8-144">Especificando namespaces</span><span class="sxs-lookup"><span data-stu-id="4c5b8-144">Specifying Namespaces</span></span>  
 <span data-ttu-id="4c5b8-145">Use o elemento `Query` XML para especificar os namespaces usados nos dados XML da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-145">Use the XML `Query` element to specify the namespaces that are used in the XML data from the data source.</span></span> <span data-ttu-id="4c5b8-146">A seguinte consulta XML usa o namespace `sales`.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-146">The following XML query uses the namespace `sales`.</span></span> <span data-ttu-id="4c5b8-147">Os nós XML `ElementPath` para `sales:LineItems` e `sales:LineItem` usam o namespace `sales`.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-147">The XML `ElementPath` nodes for `sales:LineItems` and `sales:LineItem` use the namespace `sales`.</span></span>  
  
```  
<Query xmlns:sales=  
"https://schemas.microsoft.com/StandardSchemas/ExtendedSales">  
   <SoapAction>  
      https://schemas.microsoft.com/SalesWebService/ListOrders   
   </SoapAction>  
   <ElementPath>  
      Customers/Customer/Orders/Order/sales:LineItems/sales:LineItem  
   </ElementPath>  
</Query>  
```  
  
 <span data-ttu-id="4c5b8-148">Para especificar o namespace do provedor de dados para que o namespace padrão permaneça vazio, use `xmldp`.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-148">To specify the data provider namespace so that the default namespace remains empty, use `xmldp`.</span></span> <span data-ttu-id="4c5b8-149">Isso é mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-149">This is shown in the following example.</span></span>  
  
### <a name="example"></a><span data-ttu-id="4c5b8-150">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4c5b8-150">Example</span></span>  
 <span data-ttu-id="4c5b8-151">Os seguintes exemplos usam o documento XML DPNamespace.xml, fornecido para ilustração após a tabela.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-151">The following examples use the XML document DPNamespace.xml, which is provided for illustration after the table.</span></span> <span data-ttu-id="4c5b8-152">Essa tabela mostra dois exemplos de sintaxe de ElementPath XML que inclui prefixos de namespace.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-152">This table shows two examples of XML ElementPath syntax that includes namespace prefixes.</span></span>  
  
|<span data-ttu-id="4c5b8-153">Elemento de consulta XML</span><span class="sxs-lookup"><span data-stu-id="4c5b8-153">XML Query Element</span></span>|<span data-ttu-id="4c5b8-154">Campos resultantes no conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="4c5b8-154">Resulting fields in the dataset</span></span>|  
|-----------------------|-------------------------------------|  
|\<Query/>|<span data-ttu-id="4c5b8-155">Valor A: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="4c5b8-155">Value A: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="4c5b8-156">Valor B: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="4c5b8-156">Value B: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="4c5b8-157">Valor C: `https://schemas.microsoft.com/.` ..</span><span class="sxs-lookup"><span data-stu-id="4c5b8-157">Value C: `https://schemas.microsoft.com/.`..</span></span>|  
|\<xmldp:Query xmlns:xmldp="https://schemas.microsoft.com/sqlserver/2005/02/reporting/XmlDPQuery" xmlns:ns="https://schemas.microsoft.com/..."><br /><br /> <span data-ttu-id="4c5b8-158">\<xmldp:ElementPath>{}/Ns raiz: Element2/nó\</xmldp:ElementPath></span><span class="sxs-lookup"><span data-stu-id="4c5b8-158">\<xmldp:ElementPath>Root {}/ns:Element2/Node\</xmldp:ElementPath></span></span><br /><br /> \</xmldp:Query>|<span data-ttu-id="4c5b8-159">Valor D</span><span class="sxs-lookup"><span data-stu-id="4c5b8-159">Value D</span></span><br /><br /> <span data-ttu-id="4c5b8-160">Valor E</span><span class="sxs-lookup"><span data-stu-id="4c5b8-160">Value E</span></span><br /><br /> <span data-ttu-id="4c5b8-161">Valor F</span><span class="sxs-lookup"><span data-stu-id="4c5b8-161">Value F</span></span>|  
  
#### <a name="xml-document-dpnamespacexml"></a><span data-ttu-id="4c5b8-162">Documento XML: DPNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="4c5b8-162">XML document: DPNamespace.xml</span></span>  
 <span data-ttu-id="4c5b8-163">É possível copiar esse XML e salvá-lo em uma URL disponível do Designer de Relatórios a ser usado como uma fonte de dados XML: por exemplo, http://localhost/DPNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="4c5b8-163">You can copy this XML and save it to a URL available for Report Designer to use as an XML data source: for example, http://localhost/DPNamespace.xml.</span></span>  
  
```  
<Root xmlns:ns="https://schemas.microsoft.com/...">  
   <ns:Element1>  
      <Node>Value A</Node>  
      <Node>Value B</Node>  
      <Node>Value C</Node>  
   </ns:Element1>  
   <ns:Element2>  
      <Node>Value D</Node>  
      <Node>Value E</Node>  
      <Node>Value F</Node>  
   </ns:Element2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c5b8-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4c5b8-164">See Also</span></span>  
 <span data-ttu-id="4c5b8-165">[Tipo de conexão XML &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4c5b8-165">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="4c5b8-166">Tutoriais do Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4c5b8-166">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](../reporting-services-tutorials-ssrs.md)  
  
  
