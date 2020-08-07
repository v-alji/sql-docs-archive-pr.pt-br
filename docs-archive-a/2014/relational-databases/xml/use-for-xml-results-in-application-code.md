---
title: Usar resultados de FOR XML no código do aplicativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, application code usage
- XML [SQL Server], FOR XML clause
- ASP.NET [SQL Server]
- .NET Framework [SQL Server], FOR XML data
- ADO [SQL Server]
- XML data islands [SQL Server]
- data islands [SQL Server]
ms.assetid: 41ae67bd-ece9-49ea-8062-c8d658ab4154
author: rothja
ms.author: jroth
ms.openlocfilehash: 3cabe7e65cb53a28a370615ed84e38ba2b8db44c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582332"
---
# <a name="use-for-xml-results-in-application-code"></a><span data-ttu-id="c7707-102">Usar resultados de FOR XML no código do aplicativo</span><span class="sxs-lookup"><span data-stu-id="c7707-102">Use FOR XML Results in Application Code</span></span>
  <span data-ttu-id="c7707-103">Usando cláusulas FOR XML com consultas SQL, é possível recuperar e até converter resultados de consultas como dados XML.</span><span class="sxs-lookup"><span data-stu-id="c7707-103">By using FOR XML clauses with SQL queries, you can retrieve and even cast query results as XML data.</span></span> <span data-ttu-id="c7707-104">Essa funcionalidade permite fazer o seguinte quando os resultados da consulta FOR XML podem ser usados no código do aplicativo XML:</span><span class="sxs-lookup"><span data-stu-id="c7707-104">This functionality allows you to do the following when FOR XML query results can be used in XML application code:</span></span>  
  
-   <span data-ttu-id="c7707-105">Consultar tabelas SQL para instâncias de valores de [Dados XML &#40;SQL Server&#41;](xml-data-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="c7707-105">Query SQL tables for instances of [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) values</span></span>  
  
-   <span data-ttu-id="c7707-106">Aplicar a [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) para retornar o resultado de consultas que contêm dados de tipo texto ou imagem como XML.</span><span class="sxs-lookup"><span data-stu-id="c7707-106">Apply the [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) to return the result of queries that contain text or image typed data as XML</span></span>  
  
 <span data-ttu-id="c7707-107">Este tópico fornece exemplos que demonstram essas aproximações.</span><span class="sxs-lookup"><span data-stu-id="c7707-107">This topic provides examples that demonstrate these approaches.</span></span>  
  
## <a name="retrieving-for-xml-data-with-ado-and-xml-data-islands"></a><span data-ttu-id="c7707-108">Recuperando dados FOR XML com ilhas de dados ADO e XML</span><span class="sxs-lookup"><span data-stu-id="c7707-108">Retrieving FOR XML Data with ADO and XML Data Islands</span></span>  
 <span data-ttu-id="c7707-109">O objeto `Stream` do ADO ou outros objetos que oferecem suporte à interface `IStream` COM, como objetos `Request` e `Response` do Active Server Pages (ASP), pode ser usado para conter os resultados quando você está trabalhando com consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="c7707-109">The ADO `Stream` object or other objects that support the COM `IStream` interface, such as the Active Server Pages (ASP) `Request` and `Response` objects, can be used to contain the results when you are working with FOR XML queries.</span></span>  
  
 <span data-ttu-id="c7707-110">Por exemplo, o código ASP a seguir mostra os resultados de consulta a uma coluna de tipo de dados `xml`, Demographics, na tabela Sales.Store do banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c7707-110">For example, the following ASP code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="c7707-111">Especificamente, a consulta procura o valor da instância dessa coluna da linha em que o CustomerID é igual a 3.</span><span class="sxs-lookup"><span data-stu-id="c7707-111">Specifically, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
```  
<!-- BeginRecordAndStreamVBS -->  
<%@ LANGUAGE = VBScript %>  
<!-- %  Option Explicit      % -->  
<!-- 'Request.ServerVariables("SERVER_NAME") & ";" & _ -->  
<HTML>  
<HEAD>  
<META NAME="GENERATOR" Content="Microsoft Developer Studio"/>  
<META HTTP-EQUIV="Content-Type" content="text/html"; charset="iso-8859-1">  
<TITLE>FOR XML Query Example</TITLE>  
<STYLE>  
   BODY  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
   H3  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
</STYLE>  
  
<!-- #include file="adovbs.inc" -->  
<%  
   Response.Write "<H3>Server-side processing</H3>"  
   Response.Write "Page Generated @ " & Now() & "<BR/>"  
   Dim adoConn  
   Set adoConn = Server.CreateObject("ADODB.Connection")  
   Dim sConn  
   sConn = "Provider=SQLOLEDB;Data Source=(local);" & _  
            "Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
   Response.write "Connect String = " & sConn & "<BR/>"  
   adoConn.ConnectionString = sConn  
   adoConn.CursorLocation = adUseClient  
   adoConn.Open  
   Response.write "ADO Version = " & adoConn.Version & "<BR/>"  
   Response.write "adoConn.State = " & adoConn.State & "<BR/>"  
   Dim adoCmd  
   Set adoCmd = Server.CreateObject("ADODB.Command")  
   Set adoCmd.ActiveConnection = adoConn  
   Dim sQuery  
   sQuery = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'><sql:query>SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</sql:query></ROOT>"  
   Response.write "Query String = " & sQuery & "<BR/>"  
   Dim adoStreamQuery  
   Set adoStreamQuery = Server.CreateObject("ADODB.Stream")  
   adoStreamQuery.Open  
   adoStreamQuery.WriteText sQuery, adWriteChar  
   adoStreamQuery.Position = 0  
   adoCmd.CommandStream = adoStreamQuery  
   adoCmd.Dialect = "{5D531CB2-E6Ed-11D2-B252-00C04F681B71}"  
   Response.write "Pushing XML to client for processing "  & "<BR/>"  
   adoCmd.Properties("Output Stream") = Response  
   Response.write "<XML ID='MyDataIsle'>"  
   adoCmd.Execute , , 1024  
   Response.write "</XML>"  
%>  
<SCRIPT language="VBScript" For="window" Event="onload">  
   Dim xmlDoc  
   Set xmlDoc = MyDataIsle.XMLDocument  
   Dim root  
   Set root = xmlDoc.documentElement.childNodes.Item(0).childNodes.Item(0).childNodes.Item(0)  
   For each child in root.childNodes  
      dim OutputXML  
      OutputXML = document.all("log").innerHTML  
      document.all("log").innerHTML = OutputXML & "<LI><B>" & child.nodeName &  ":</B>  " & child.Text  & "</LI>"  
   Next  
   MsgBox xmlDoc.xml  
</SCRIPT>  
</HEAD>  
<BODY>  
   <H3>Client-side processing of XML Document MyDataIsle</H3>  
   <UL id=log>  
   </UL>  
</BODY>  
</HTML>  
<!-- EndRecordAndStreamVBS -->  
```  
  
 <span data-ttu-id="c7707-112">Essa página ASP de exemplo contém VBScript do lado do servidor que usa ADO para executar a consulta FOR XML e retorna os resultados XML em uma ilha de dados XML, MyDataIsle.</span><span class="sxs-lookup"><span data-stu-id="c7707-112">This example ASP page contains server-side VBScript that uses ADO to execute the FOR XML query and return the XML results in an XML data island, MyDataIsle.</span></span> <span data-ttu-id="c7707-113">Em seguida, essa ilha de dados XML é retornada no navegador para processamento adicional no lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="c7707-113">This XML data island is then returned in the browser for additional client-side processing.</span></span> <span data-ttu-id="c7707-114">Código VBScript adicional no lado do cliente é usado para processar o conteúdo da ilha de dados XML.</span><span class="sxs-lookup"><span data-stu-id="c7707-114">Additional client-side VBScript code is then used to process the contents of the XML data island.</span></span> <span data-ttu-id="c7707-115">Esse processo é executado antes da exibição do conteúdo como parte do DHTML resultante e da abertura de uma caixa de mensagem para mostrar o conteúdo pré-processado da ilha de dados XML.</span><span class="sxs-lookup"><span data-stu-id="c7707-115">This process is performed before displaying the contents as part of the resultant DHTML and opening a message box to show the preprocessed contents of the XML data island.</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="c7707-116">Para testar este exemplo</span><span class="sxs-lookup"><span data-stu-id="c7707-116">To test this example</span></span>  
  
1.  <span data-ttu-id="c7707-117">Verifique se o IIS está instalado e se o banco de dados de exemplo do AdventureWorks para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi instalado.</span><span class="sxs-lookup"><span data-stu-id="c7707-117">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="c7707-118">Este exemplo requer que o Serviços de Informações da Internet (IIS) versão 5.0 ou posterior, esteja instalado com suporte do ASP habilitado.</span><span class="sxs-lookup"><span data-stu-id="c7707-118">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP support enabled.</span></span> <span data-ttu-id="c7707-119">Além disso, o banco de dados de exemplo do AdventureWorks precisa estar instalado.</span><span class="sxs-lookup"><span data-stu-id="c7707-119">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="c7707-120">Copiar o exemplo de código fornecido anteriormente e colá-lo no XML ou no editor de texto usado.</span><span class="sxs-lookup"><span data-stu-id="c7707-120">Copy the code example that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="c7707-121">Salvar o arquivo como RetrieveResults.asp no diretório raiz usado para o IIS.</span><span class="sxs-lookup"><span data-stu-id="c7707-121">Save the file as RetrieveResults.asp in the root directory that is used for IIS.</span></span> <span data-ttu-id="c7707-122">Normalmente, o diretório é C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="c7707-122">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="c7707-123">Abra a página ASP em uma janela do navegador usando a seguinte URL.</span><span class="sxs-lookup"><span data-stu-id="c7707-123">Open the ASP page in a browser window by using the following URL.</span></span> <span data-ttu-id="c7707-124">Primeiro, substitua 'MyServer' por "localhost" ou pelo nome real do servidor onde o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o IIS estão instalados.</span><span class="sxs-lookup"><span data-stu-id="c7707-124">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.asp  
    ```  
  
 <span data-ttu-id="c7707-125">Os resultados da página HTML gerada exibidos são semelhantes à seguinte saída de exemplo:</span><span class="sxs-lookup"><span data-stu-id="c7707-125">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="c7707-126">Processamento no lado do servidor</span><span class="sxs-lookup"><span data-stu-id="c7707-126">Server-side processing</span></span>  
 <span data-ttu-id="c7707-127">Page Generated \@ 3/11/2006 3:36:02 PM</span><span class="sxs-lookup"><span data-stu-id="c7707-127">Page Generated \@ 3/11/2006 3:36:02 PM</span></span>  
  
 <span data-ttu-id="c7707-128">Cadeia de Conexão = Provedor=SQLOLEDB;Fonte de Dados=MyServer;Catálogo Inicial=AdventureWorks;Segurança Integrada=SSPI;</span><span class="sxs-lookup"><span data-stu-id="c7707-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span></span>  
  
 <span data-ttu-id="c7707-129">Versão do ADO = 2.8</span><span class="sxs-lookup"><span data-stu-id="c7707-129">ADO Version = 2.8</span></span>  
  
 <span data-ttu-id="c7707-130">adoConn.State = 1</span><span class="sxs-lookup"><span data-stu-id="c7707-130">adoConn.State = 1</span></span>  
  
 <span data-ttu-id="c7707-131">Cadeia de Caracteres da Consulta = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span><span class="sxs-lookup"><span data-stu-id="c7707-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span></span>  
  
 <span data-ttu-id="c7707-132">Enviando XML por push ao cliente para processamento</span><span class="sxs-lookup"><span data-stu-id="c7707-132">Pushing XML to client for processing</span></span>  
  
##### <a name="client-side-processing-of-xml-document-mydataisle"></a><span data-ttu-id="c7707-133">Processamento do lado do cliente do documento XML MyDataIsle</span><span class="sxs-lookup"><span data-stu-id="c7707-133">Client-side processing of XML Document MyDataIsle</span></span>  
  
-   <span data-ttu-id="c7707-134">**AnnualSales:** 1.500.000</span><span class="sxs-lookup"><span data-stu-id="c7707-134">**AnnualSales:** 1500000</span></span>  
  
-   <span data-ttu-id="c7707-135">**AnnualRevenue:** 150.000</span><span class="sxs-lookup"><span data-stu-id="c7707-135">**AnnualRevenue:** 150000</span></span>  
  
-   <span data-ttu-id="c7707-136">**BankName:** Primary International</span><span class="sxs-lookup"><span data-stu-id="c7707-136">**BankName:** Primary International</span></span>  
  
-   <span data-ttu-id="c7707-137">**BusinessType:** Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="c7707-137">**BusinessType:** OS</span></span>  
  
-   <span data-ttu-id="c7707-138">**YearOpened:** 1974</span><span class="sxs-lookup"><span data-stu-id="c7707-138">**YearOpened:** 1974</span></span>  
  
-   <span data-ttu-id="c7707-139">**Specialty:** Rodoviário</span><span class="sxs-lookup"><span data-stu-id="c7707-139">**Specialty:** Road</span></span>  
  
-   <span data-ttu-id="c7707-140">**SquareFeet:** 38.000</span><span class="sxs-lookup"><span data-stu-id="c7707-140">**SquareFeet:** 38000</span></span>  
  
-   <span data-ttu-id="c7707-141">**Brands:** 3</span><span class="sxs-lookup"><span data-stu-id="c7707-141">**Brands:** 3</span></span>  
  
-   <span data-ttu-id="c7707-142">**Internet:** DSL</span><span class="sxs-lookup"><span data-stu-id="c7707-142">**Internet:** DSL</span></span>  
  
-   <span data-ttu-id="c7707-143">**NumberEmployees:** 40</span><span class="sxs-lookup"><span data-stu-id="c7707-143">**NumberEmployees:** 40</span></span>  
  
 <span data-ttu-id="c7707-144">Em seguida, a caixa de mensagem do VBScript exibirá o seguinte conteúdo da ilha de dados XML original não filtrada que foi retornada pelos resultados da consulta XML.</span><span class="sxs-lookup"><span data-stu-id="c7707-144">The VBScript message box will then show the following original, unfiltered XML data island contents that were returned by the FOR XML query results.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Sales.Store>  
    <Demographics>  
      <StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
        <AnnualSales>1500000</AnnualSales>  
        <AnnualRevenue>150000</AnnualRevenue>  
        <BankName>Primary International</BankName>  
        <BusinessType>OS</BusinessType>  
        <YearOpened>1974</YearOpened>  
        <Specialty>Road</Specialty>  
        <SquareFeet>38000</SquareFeet>  
        <Brands>3</Brands>  
        <Internet>DSL</Internet>  
        <NumberEmployees>40</NumberEmployees>  
      </StoreSurvey>  
    </Demographics>  
  </Sales.Store>  
</ROOT>  
```  
  
## <a name="retrieving-for-xml-data-with-aspnet-and-the-net-framework"></a><span data-ttu-id="c7707-145">Recuperando dados FOR XML com o ASP.NET e o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c7707-145">Retrieving FOR XML Data with ASP.NET and the .NET Framework</span></span>  
 <span data-ttu-id="c7707-146">Como no exemplo anterior, o seguinte código ASP.NET mostra os resultados da consulta de uma coluna de tipo de dados `xml`, Demographics, na tabela Sales.Store do banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c7707-146">As in the previous example, the following ASP.NET code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="c7707-147">Como no exemplo anterior, a consulta procura o valor da instância dessa coluna para a linha em que o CustomerID é igual a 3.</span><span class="sxs-lookup"><span data-stu-id="c7707-147">As in the previous example, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
 <span data-ttu-id="c7707-148">Neste exemplo, as seguintes APIs gerenciadas do Microsoft .NET Framework são usadas para executar o retorno e a renderização dos resultados de consultas FOR XML:</span><span class="sxs-lookup"><span data-stu-id="c7707-148">In this example, the following Microsoft .NET Framework managed APIs are used to accomplish the return and rendering of the FOR XML query results:</span></span>  
  
1.  <span data-ttu-id="c7707-149">O `SqlConnection` é usado para abrir uma conexão ao SQL Server com base no conteúdo de uma variável da cadeia conexão especificada, strConn.</span><span class="sxs-lookup"><span data-stu-id="c7707-149">`SqlConnection` is used to open a connection to SQL Server, based on the contents of a specified connection string variable, strConn.</span></span>  
  
2.  <span data-ttu-id="c7707-150">Em seguida, o `SqlDataAdapter` é usado como o adaptador de dados e usa a conexão SQL e a cadeia de caracteres de uma consulta SQL especificada para executar a consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="c7707-150">`SqlDataAdapter` is then used as the data adapter and it uses the SQL connection and a specified SQL query string to execute the FOR XML query.</span></span>  
  
3.  <span data-ttu-id="c7707-151">Depois da execução da consulta, o método `SqlDataAdapter.Fill` é chamado e uma instância de um `DataSet,` MyDataSet, é passada para preencher o conjunto de dados com a saída da consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="c7707-151">After the query has executed, the `SqlDataAdapter.Fill` method is then called and passed an instance of a `DataSet,` MyDataSet, in order to fill the data set with the output of the FOR XML query.</span></span>  
  
4.  <span data-ttu-id="c7707-152">Em seguida, o método `DataSet.GetXml` é chamado para retornar os resultados da consulta como uma cadeia de caracteres que pode ser exibida na página HTML gerada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="c7707-152">The `DataSet.GetXml` method is then called to return the query results as a string that can be displayed in the server-generated HTML page.</span></span>  
  
    ```  
    <%@ Page Language="VB" %>  
    <HTML>  
    <HEAD>  
    <TITLE>FOR XML Query Example</TITLE>  
    <STYLE>  
       BODY  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
       H3  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
    </STYLE>  
    </HEAD>  
    <BODY>  
    <%  
    Dim s as String  
    s = "<H3>Server-side processing</H3>" & _  
        "Page Generated @ " & Now() & "<BR/>"  
  
    Dim SQL As String   
    SQL = "SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO"  
  
    Dim strConn As String   
    strConn = "Server=(local);Database=AdventureWorks;Integrated Security=SSPI;"  
  
    Dim MySqlConn As New System.Data.SqlClient.SqlConnection(strConn)  
    Dim MySqlAdapter As New System.Data.SqlClient.SqlDataAdapter(SQL,MySqlConn)  
    Dim MyDataSet As New System.Data.DataSet  
  
    MySqlConn.Open()  
    s = s & "<P>SqlConnection opened.</P>"   
  
    MySqlAdapter.Fill(MyDataSet)  
    s = s & "<P>" & MyDataSet.GetXml  & "</P>"  
  
    MySqlConn.Close()  
    s = s & "<P>SqlConnection closed.</P>"   
  
    Message.InnerHtml=s  
    %>  
    <SPAN id="Message" runat=server />  
    </BODY>  
    </HTML>  
    ```  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="c7707-153">Para testar este exemplo</span><span class="sxs-lookup"><span data-stu-id="c7707-153">To test this example</span></span>  
  
1.  <span data-ttu-id="c7707-154">Verifique se o IIS está instalado e se o banco de dados de exemplo do AdventureWorks para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi instalado.</span><span class="sxs-lookup"><span data-stu-id="c7707-154">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="c7707-155">Este exemplo requer que o Serviços de Informações da Internet (IIS) versão 5.0 ou posterior, esteja instalado com o suporte ao ASP.NET habilitado.</span><span class="sxs-lookup"><span data-stu-id="c7707-155">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP.NET support enabled.</span></span> <span data-ttu-id="c7707-156">Além disso, o banco de dados de exemplo do AdventureWorks precisa estar instalado.</span><span class="sxs-lookup"><span data-stu-id="c7707-156">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="c7707-157">Copiar o código fornecido anteriormente e colá-lo no XML ou no editor de texto usado.</span><span class="sxs-lookup"><span data-stu-id="c7707-157">Copy the code that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="c7707-158">Salvar o arquivo como RetrieveResults.aspx no diretório raiz usado para o IIS.</span><span class="sxs-lookup"><span data-stu-id="c7707-158">Save the file as RetrieveResults.aspx in the root directory used for IIS.</span></span> <span data-ttu-id="c7707-159">Normalmente, o diretório é C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="c7707-159">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="c7707-160">Abra a página ASP.NET em uma janela de navegador usando a seguinte URL.</span><span class="sxs-lookup"><span data-stu-id="c7707-160">Open the ASP.NET page in a browser window using the following URL.</span></span> <span data-ttu-id="c7707-161">Primeiro, substitua 'MyServer' por "localhost" ou pelo nome real do servidor onde o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o IIS estão instalados.</span><span class="sxs-lookup"><span data-stu-id="c7707-161">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.aspx  
    ```  
  
 <span data-ttu-id="c7707-162">Os resultados da página HTML gerada exibidos são semelhantes à seguinte saída de exemplo:</span><span class="sxs-lookup"><span data-stu-id="c7707-162">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="c7707-163">Processamento no lado do servidor</span><span class="sxs-lookup"><span data-stu-id="c7707-163">Server-side processing</span></span>  
  
```  
Page Generated @ 3/11/2006 3:36:02 PM  
  
SqlConnection opened.  
  
<Sales.Store><Demographics><StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey"><AnnualSales>1500000</AnnualSales><AnnualRevenue>150000</AnnualRevenue><BankName>Primary International</BankName><BusinessType>OS</BusinessType><YearOpened>1974</YearOpened><Specialty>Road</Specialty><SquareFeet>38000</SquareFeet><Brands>3</Brands><Internet>DSL</Internet><NumberEmployees>40</NumberEmployees></StoreSurvey></Demographics></Sales.Store>  
  
SqlConnection closed.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c7707-164">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `xml` suporte ao tipo de dados permite que você solicite que o resultado de uma consulta for XML seja retornado como `xml` tipo de dados, em vez de dados de cadeia de caracteres ou tipos de imagem, especificando a [diretiva de tipo](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c7707-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`xml` data type support lets you request that the result of a FOR XML query be returned as `xml` data type, instead of as string or image typed data, by specifying the [TYPE directive](type-directive-in-for-xml-queries.md).</span></span> <span data-ttu-id="c7707-165">Quando a diretiva TYPE é usada em consultas FOR XML, ela fornece acesso programático aos resultados de FOR XML de maneira semelhante à mostrada em [Usar dados XML em aplicativos](use-xml-data-in-applications.md).</span><span class="sxs-lookup"><span data-stu-id="c7707-165">When the TYPE directive is used in FOR XML queries, it provides programmatic access to the FOR XML results similar to that shown in [Use XML Data in Applications](use-xml-data-in-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7707-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7707-166">See Also</span></span>  
 [<span data-ttu-id="c7707-167">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c7707-167">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
