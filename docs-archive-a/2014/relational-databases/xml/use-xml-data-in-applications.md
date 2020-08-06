---
title: Usar dados XML em aplicativos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- parameters [XML in SQL Server]
- XML [SQL Server], ADO
- columns [XML in SQL Server], ADO.NET
- ADO [XML in SQL Server]
- columns [XML in SQL Server], SQL Server Native Client
- xml data type [SQL Server], ADO
- SQLNCLI, XML
- xml data type [SQL Server], SQL Server Native Client
- SQL Server Native Client, XML
- ADO.NET [XML in SQL Server]
- XML [SQL Server], ADO.NET
- columns [XML in SQL Server], ADO
- xml data type [SQL Server], ADO.NET
- XML [SQL Server], SQL Server Native Client
ms.assetid: 5dabf7e0-c6df-451d-a070-4661f84607fd
author: rothja
ms.author: jroth
ms.openlocfilehash: 79dd4f4d2ff3cd61bc33c632f499bfb8e8817f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678660"
---
# <a name="use-xml-data-in-applications"></a><span data-ttu-id="50de8-102">Usar dados XML em aplicativos</span><span class="sxs-lookup"><span data-stu-id="50de8-102">Use XML Data in Applications</span></span>
  <span data-ttu-id="50de8-103">Este tópico descreve as opções disponíveis para trabalhar com o tipo de dados `xml` em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="50de8-103">This topic describes the options that are available to you for working with the `xml` data type in your application.</span></span> <span data-ttu-id="50de8-104">O tópico contém informações sobre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="50de8-104">The topic includes information about the following:</span></span>  
  
-   <span data-ttu-id="50de8-105">Tratando XML de uma coluna de tipo `xml` usando o ADO e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="50de8-105">Handling XML from an `xml` type column by using ADO and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="50de8-106">Tratando XML de uma coluna de tipo `xml` usando o ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50de8-106">Handling XML from an `xml` type column by using ADO.NET</span></span>  
  
-   <span data-ttu-id="50de8-107">Tratando tipo `xml` em parâmetros usando o ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50de8-107">Handling `xml` type in parameters by using ADO.NET</span></span>  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-ado-and-sql-server-native-client"></a><span data-ttu-id="50de8-108">Tratando XML de uma coluna de tipo xml usando o ADO e o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="50de8-108">Handling XML from an xml Type Column by Using ADO and SQL Server Native Client</span></span>  
 <span data-ttu-id="50de8-109">Para usar componentes MDAC para acessar os tipos e recursos introduzidos no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a propriedade de inicialização DataTypeCompatibility deve estar definida na cadeia de conexão do ADO.</span><span class="sxs-lookup"><span data-stu-id="50de8-109">To use MDAC components to access the types and features that were introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must set the DataTypeCompatibility initialization property in the ADO connection string.</span></span>  
  
 <span data-ttu-id="50de8-110">Por exemplo, o exemplo a seguir do Visual Basic Scripting Edition (VBScript) mostra os resultados de uma consulta em uma coluna de tipo de dados `xml`, `Demographics`, na tabela `Sales.Store` do banco de dados `AdventureWorks2012` de exemplo.</span><span class="sxs-lookup"><span data-stu-id="50de8-110">For example, the following Visual Basic Scripting Edition (VBScript) sample shows the results of querying an `xml` data type column, `Demographics`, in the `Sales.Store` table of the `AdventureWorks2012` sample database.</span></span> <span data-ttu-id="50de8-111">Especificamente, a consulta procura o valor da instância dessa coluna para a linha em que o `CustomerID` é igual a `3`.</span><span class="sxs-lookup"><span data-stu-id="50de8-111">Specifically, the query looks for the instance value of this column for the row where the `CustomerID` is equal to `3`.</span></span>  
  
```  
Const DS = "MyServer"  
Const DB = "AdventureWorks2012"  
  
Set objConn = CreateObject("ADODB.Connection")  
Set objRs = CreateObject("ADODB.Recordset")  
  
CommandText = "SELECT Demographics" & _  
              " FROM Sales.Store" & _  
              " INNER JOIN Sales.Customer" & _  
              " ON Sales.Store.BusinessEntityID = sales.customer.StoreID" & _  
              " WHERE Sales.Customer.CustomerID = 3" & _  
              " OR Sales.Customer.CustomerID = 4"  
  
ConnectionString = "Provider=SQLNCLI11" & _  
                   ";Data Source=" & DS & _  
                   ";Initial Catalog=" & DB & _  
                   ";Integrated Security=SSPI;" & _  
                   "DataTypeCompatibility=80"  
  
'Connect to the data source.  
objConn.Open ConnectionString  
  
'Execute command through the connection and display  
Set objRs = objConn.Execute(CommandText)  
  
Dim rowcount  
rowcount = 0  
Do While Not objRs.EOF  
   rowcount = rowcount + 1  
   MsgBox "Row " & rowcount & _  
           vbCrLf & vbCrLf & objRs(0)  
   objRs.MoveNext  
Loop  
  
'Clean up.  
objRs.Close  
objConn.Close  
Set objRs = Nothing  
Set objConn = Nothing  
```  
  
 <span data-ttu-id="50de8-112">Esse exemplo mostra como definir a propriedade de compatibilidade de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="50de8-112">This example shows how to set the data type compatibility property.</span></span> <span data-ttu-id="50de8-113">Por padrão, isso é definido como 0 ao usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="50de8-113">By default, this is set to 0 when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="50de8-114">Se você definir o valor como 80, o provedor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fará com que as colunas de tipo `xml` e definidas pelo usuário sejam exibidas como tipos de dados do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50de8-114">If you set the value to 80, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider will make `xml` and user-defined type columns appear as [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] data types.</span></span> <span data-ttu-id="50de8-115">Esses tipos são DBTYPE_WSTR e DBTYPE_BYTES, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="50de8-115">This would be DBTYPE_WSTR and DBTYPE_BYTES, respectively.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="50de8-116">O Native Client também deve estar instalado no computador cliente e a cadeia de conexão deve especificá-lo para uso como o provedor de dados com "`Provider=SQLNCLI11;...`".</span><span class="sxs-lookup"><span data-stu-id="50de8-116">Native Client must also be installed on the client computer and the connection string must specify it for use as the data provider with "`Provider=SQLNCLI11;...`".</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="50de8-117">Para testar este exemplo</span><span class="sxs-lookup"><span data-stu-id="50de8-117">To test this example</span></span>  
  
1.  <span data-ttu-id="50de8-118">Verifique se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client está instalado e se o MDAC 2.6.0 ou posterior está disponível no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="50de8-118">Verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed and that MDAC 2.6.0or later is available on the client computer.</span></span>  
  
     <span data-ttu-id="50de8-119">Para obter mais informações, consulte [Programação do SQL Server Native Client](../native-client/sql-server-native-client-programming.md).</span><span class="sxs-lookup"><span data-stu-id="50de8-119">For more information, see [SQL Server Native Client Programming](../native-client/sql-server-native-client-programming.md).</span></span>  
  
2.  <span data-ttu-id="50de8-120">Verifique se o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] de exemplo no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="50de8-120">Verify that the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
     <span data-ttu-id="50de8-121">Esse exemplo requer o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] de exemplo.</span><span class="sxs-lookup"><span data-stu-id="50de8-121">This example requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
3.  <span data-ttu-id="50de8-122">Copie o código mostrado anteriormente neste tópico e cole-o em seu editor de texto ou de código.</span><span class="sxs-lookup"><span data-stu-id="50de8-122">Copy the code shown previously in this topic and paste the code into your text or code editor.</span></span> <span data-ttu-id="50de8-123">Salve o arquivo como HandlingXmlDataType.vbs.</span><span class="sxs-lookup"><span data-stu-id="50de8-123">Save the file as HandlingXmlDataType.vbs.</span></span>  
  
4.  <span data-ttu-id="50de8-124">Modifique o script conforme necessário para sua instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="50de8-124">Modify the script as required for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation and save your changes.</span></span>  
  
     <span data-ttu-id="50de8-125">Por exemplo, quando `MyServer` estiver especificado, ele deve ser substituído pelo nome `(local)` ou real do servidor no qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="50de8-125">For example, where `MyServer` is specified, you should replace it with either `(local)` or the actual name of the server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
5.  <span data-ttu-id="50de8-126">Execute HandlingXmlDataType.vbs e execute o script.</span><span class="sxs-lookup"><span data-stu-id="50de8-126">Run HandlingXmlDataType.vbs and execute the script.</span></span>  
  
 <span data-ttu-id="50de8-127">Os resultados devem ser semelhantes à seguinte saída de exemplo:</span><span class="sxs-lookup"><span data-stu-id="50de8-127">The results should be similar to the following sample output:</span></span>  
  
```  
Row 1  
  
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
  
Row 2  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>United Security</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1976</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>6000</SquareFeet>  
  <Brands>2</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>5</NumberEmployees>  
</StoreSurvey>  
```  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-adonet"></a><span data-ttu-id="50de8-128">Tratando XML de uma coluna de tipo xml usando o ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50de8-128">Handling XML from an xml Type Column by Using ADO.NET</span></span>  
 <span data-ttu-id="50de8-129">Para manipular XML de uma `xml` coluna de tipo de dados usando ADO.net e o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , você pode usar o comportamento padrão da `SqlCommand` classe.</span><span class="sxs-lookup"><span data-stu-id="50de8-129">To handle XML from an `xml` data type column by using ADO.NET and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] you can use the standard behavior of the `SqlCommand` class.</span></span> <span data-ttu-id="50de8-130">Por exemplo, uma coluna de tipo de dados `xml` e seus valores podem ser recuperados da mesma maneira como qualquer coluna SQL é recuperada usando um `SqlDataReader`. No entanto se você desejar trabalhar com o conteúdo de uma coluna de tipo de dados `xml` como XML, primeiro precisará atribuir o conteúdo a um tipo `XmlReader`.</span><span class="sxs-lookup"><span data-stu-id="50de8-130">For example, an `xml` data type column and its values can be retrieved in the same way any SQL column is retrieved by using a `SqlDataReader`.However, if you want to work with the contents of an `xml` data type column as XML, you will first have to assign the contents to an `XmlReader` type.</span></span>  
  
 <span data-ttu-id="50de8-131">Para obter mais informações e um código de exemplo, confira "Valores de coluna XML em um leitor de dados" na documentação do SDK do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50de8-131">For more information and example code, see "XML Column Values in a Data Reader" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="handling-an-xml-type-column-in-parameters-by-using-adonet"></a><span data-ttu-id="50de8-132">Tratando uma coluna de tipo xml em parâmetros usando o ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50de8-132">Handling an xml Type Column in Parameters by Using ADO.NET</span></span>  
 <span data-ttu-id="50de8-133">Para tratar um tipo de dados xml passado como um parâmetro no ADO.NET e no [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], é possível fornecer o valor como uma instância do tipo de dados `SqlXml`.</span><span class="sxs-lookup"><span data-stu-id="50de8-133">To handle an xml data type passed as a parameter in ADO.NET and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can supply the value as an instance of the `SqlXml` data type.</span></span> <span data-ttu-id="50de8-134">Nenhum tratamento especial está envolvido porque as colunas de tipo de dados `xml` no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem aceitar valores de parâmetros da mesma maneira que outras colunas e tipos de dados, como `string` ou `integer`.</span><span class="sxs-lookup"><span data-stu-id="50de8-134">No special handling is involved, because `xml` data type columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can accept parameter values in the same way as other columns and data types, such as `string` or `integer`.</span></span>  
  
 <span data-ttu-id="50de8-135">Para obter mais informações e um código de exemplo, confira "Valores XML como parâmetros de comando" na documentação do SDK do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50de8-135">For more information and example code, see "XML Values as Command Parameters" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50de8-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50de8-136">See Also</span></span>  
 [<span data-ttu-id="50de8-137">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="50de8-137">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
