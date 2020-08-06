---
title: Usando o ADO com SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, ADO
- data access [SQL Server Native Client], ADO
- ADO [SQL Server Native Client]
- SQLNCLI, ADO
ms.assetid: 118a7cac-4c0d-44fd-b63e-3d542932d239
author: rothja
ms.author: jroth
ms.openlocfilehash: ccd14432aa3541572467a4c651c1f48b1ac957f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684158"
---
# <a name="using-ado-with-sql-server-native-client"></a><span data-ttu-id="d27a6-102">Usando o ADO com SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d27a6-102">Using ADO with SQL Server Native Client</span></span>
  <span data-ttu-id="d27a6-103">Para aproveitar os novos recursos introduzidos [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] como Mars (vários conjuntos de resultados ativos), as notificações de consulta, os UDTs (tipos definidos pelo usuário) ou o novo tipo de dados **XML** , os aplicativos existentes que usam o ActiveX Data Objects (ADO) devem usar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo como seu provedor de acesso a dados.</span><span class="sxs-lookup"><span data-stu-id="d27a6-103">In order to take advantage of new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] such as multiple active result sets (MARS), query notifications, user-defined types (UDTs), or the new **xml** data type, existing applications that use ActiveX Data Objects (ADO) should use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider as their data access provider.</span></span>  
  
 <span data-ttu-id="d27a6-104">Caso você não precise usar nenhum dos novos recursos introduzidos no [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], não há necessidade de usar o provedor de dados OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client. É possível continuar usando o provedor de acesso a dados atual, normalmente SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="d27a6-104">If you do not need to use any of the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], there is no need to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider; you can continue using your current data access provider, which is typically SQLOLEDB.</span></span> <span data-ttu-id="d27a6-105">Caso esteja aperfeiçoando um aplicativo existente e precise usar os novos recursos introduzidos no [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], você deve usar o provedor de dados OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d27a6-105">If you are enhancing an existing application and you need to use the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], you should use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d27a6-106">Caso você esteja desenvolvendo um novo aplicativo, é recomendável considerar o uso do ADO.NET e do provedor de dados .NET Framework do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], e não o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, para acessar todos os novos recursos de versões recentes do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d27a6-106">If you are developing a new application, it is recommended that you consider using ADO.NET and the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instead of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access all the new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d27a6-107">Para obter mais informações sobre o provedor de dados .NET Framework do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], consulte a documentação do SDK do .NET Framework referente ao ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d27a6-107">For more information about the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see the .NET Framework SDK documentation for ADO.NET.</span></span>  
  
 <span data-ttu-id="d27a6-108">Para permitir que o ADO use os novos recursos de versões recentes do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], foram feitas algumas melhorias no provedor de dados OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, que estende os principais recursos do OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d27a6-108">To enable ADO to use new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], some enhancements have been made to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider which extends the core features of OLE DB.</span></span> <span data-ttu-id="d27a6-109">Essas melhorias permitem que os aplicativos ADO usem recursos mais novos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e consumam dois tipos de dados introduzidos no [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml** e **udt**.</span><span class="sxs-lookup"><span data-stu-id="d27a6-109">These enhancements allow ADO applications to use newer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features and to consume two data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml** and **udt**.</span></span> <span data-ttu-id="d27a6-110">Essas melhorias também exploram as melhorias feitas nos tipos de dados **varchar**, **nvarchar** e **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="d27a6-110">These enhancements also exploit enhancements to the **varchar**, **nvarchar**, and **varbinary** data types.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="d27a6-111">O Native Client adiciona a propriedade de inicialização SSPROP_INIT_DATATYPECOMPATIBILITY ao conjunto de propriedades DBPROPSET_SQLSERVERDBINIT para uso por aplicativos ADO para que os novos tipos de dados sejam expostos de forma compatível com o ADO.</span><span class="sxs-lookup"><span data-stu-id="d27a6-111">Native Client adds the SSPROP_INIT_DATATYPECOMPATIBILITY initialization property to the DBPROPSET_SQLSERVERDBINIT property set for use by ADO applications so that the new data types are exposed in a way compatible with ADO.</span></span> <span data-ttu-id="d27a6-112">Além disso, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo também define uma nova palavra-chave de cadeia de conexão chamada `DataTypeCompatibility` que é definida na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="d27a6-112">In addition, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider also defines a new connection string keyword named `DataTypeCompatibility` that is set in the connection string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d27a6-113">Os aplicativos do ADO existentes podem acessar e atualizar valores de XML, UDT, de campo binário e de texto grandes usando o provedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="d27a6-113">Existing ADO applications can access and update XML, UDT, and large value text and binary field values using the SQLOLEDB provider.</span></span> <span data-ttu-id="d27a6-114">Os novos tipos de dados **varchar(max)** , **nvarchar(max)** e **varbinary(max)** maiores são retornados como tipos do ADO **adLongVarChar**, **adLongVarWChar** e **adLongVarBinary**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d27a6-114">The new larger **varchar(max)**, **nvarchar(max)**, and **varbinary(max)** data types are returned as the ADO types **adLongVarChar**, **adLongVarWChar** and **adLongVarBinary** respectively.</span></span> <span data-ttu-id="d27a6-115">As colunas XML são retornadas como **adLongVarChar**, e as colunas UDT, como **adVarBinary**.</span><span class="sxs-lookup"><span data-stu-id="d27a6-115">XML columns are returned as **adLongVarChar**, and UDT columns are returned as **adVarBinary**.</span></span> <span data-ttu-id="d27a6-116">No entanto, caso use o provedor de dados OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLNCLI11) em lugar do SQLOLEDB, você não pode se esquecer de definir a palavra-chave `DataTypeCompatibility` como "80" para que os novos tipos de dados sejam mapeados corretamente para os tipos de dados do ADO.</span><span class="sxs-lookup"><span data-stu-id="d27a6-116">However, if you use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider (SQLNCLI11) instead of SQLOLEDB, you need to make sure to set the `DataTypeCompatibility` keyword to "80" so that the new data types will map correctly to the ADO data types.</span></span>  
  
## <a name="enabling-sql-server-native-client-from-ado"></a><span data-ttu-id="d27a6-117">Habilitando o SQL Server Native Client no ADO</span><span class="sxs-lookup"><span data-stu-id="d27a6-117">Enabling SQL Server Native Client from ADO</span></span>  
 <span data-ttu-id="d27a6-118">Para habilitar o uso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cliente nativo, os aplicativos ADO precisarão implementar as seguintes palavras-chave em suas cadeias de conexão:</span><span class="sxs-lookup"><span data-stu-id="d27a6-118">To enable the usage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, ADO applications will need to implement the following keywords in their connection strings:</span></span>  
  
-   `Provider=SQLNCLI11`  
  
-   `DataTypeCompatibility=80`  
  
 <span data-ttu-id="d27a6-119">Para obter mais informações sobre as palavras-chave de cadeia de caracteres de conexões ADO com suporte no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, consulte [usando palavras-chave de cadeia de conexão com SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d27a6-119">For more information about the ADO connections string keywords supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="d27a6-120">Veja a seguir um exemplo de como estabelecer uma cadeia de conexão ADO totalmente habilitada para trabalhar com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, incluindo a habilitação do recurso Mars:</span><span class="sxs-lookup"><span data-stu-id="d27a6-120">The following is an example of establishing an ADO connection string that is fully enabled to work with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, including the enabling of the MARS feature:</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
```  
  
## <a name="examples"></a><span data-ttu-id="d27a6-121">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d27a6-121">Examples</span></span>  
 <span data-ttu-id="d27a6-122">As seções a seguir fornecem exemplos de como você pode usar o ADO com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="d27a6-122">The following sections provide examples of how you can use ADO with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
### <a name="retrieving-xml-column-data"></a><span data-ttu-id="d27a6-123">Recuperando dados da coluna XML</span><span class="sxs-lookup"><span data-stu-id="d27a6-123">Retrieving XML Column Data</span></span>  
 <span data-ttu-id="d27a6-124">Neste exemplo, um conjunto de registros é usado para recuperar e exibir os dados de uma coluna XML no banco de dados de exemplo **AdventureWorks** do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d27a6-124">In this example, a recordset is used to retrieve and display the data from an XML column in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **AdventureWorks** sample database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim rst As New ADODB.Recordset  
Dim sXMLResult As String  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _   
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the xml data as a recordset.  
Set rst.ActiveConnection = con  
rst.Source = "SELECT AdditionalContactInfo FROM Person.Contact " _  
   & "WHERE AdditionalContactInfo IS NOT NULL"  
rst.Open  
  
' Display the data in the recordset.  
While (Not rst.EOF)  
   sXMLResult = rst.Fields("AdditionalContactInfo").Value  
   Debug.Print (sXMLResult)  
   rst.MoveNext  
End While  
  
con.Close  
Set con = Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d27a6-125">Não há suporte para a filtragem do conjunto de registros com colunas XML.</span><span class="sxs-lookup"><span data-stu-id="d27a6-125">Recordset filtering is not supported with XML columns.</span></span> <span data-ttu-id="d27a6-126">Se ela for usada, será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="d27a6-126">If used, an error will be returned.</span></span>  
  
### <a name="retrieving-udt-column-data"></a><span data-ttu-id="d27a6-127">Recuperando dados da coluna UDT</span><span class="sxs-lookup"><span data-stu-id="d27a6-127">Retrieving UDT Column Data</span></span>  
 <span data-ttu-id="d27a6-128">Neste exemplo, um objeto **Command** é usado para executar uma consulta SQL que retorna um UDT, os dados UDT são atualizados e, em seguida, os novos dados são inseridos novamente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d27a6-128">In this example, a **Command** object is used to execute a SQL query that returns a UDT, the UDT data is updated, and then the new data is inserted back into the database.</span></span> <span data-ttu-id="d27a6-129">Este exemplo supõe que o UDT **Point** já foi registrado no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d27a6-129">This example assumes that the **Point** UDT has already been registered in the database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim cmd As New ADODB.Command  
Dim rst As New ADODB.Recordset  
Dim strOldUDT As String  
Dim strNewUDT As String  
Dim aryTempUDT() As String  
Dim strTempID As String  
Dim i As Integer  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the UDT value.  
Set cmd.ActiveConnection = con  
cmd.CommandText = "SELECT ID, Pnt FROM dbo.Points.ToString()"  
Set rst = cmd.Execute  
strTempID = rst.Fields(0).Value  
strOldUDT = rst.Fields(1).Value  
  
' Do something with the UDT by adding i to each point.  
arytempUDT = Split(strOldUDT, ",")  
i = 3  
strNewUDT = LTrim(Str(Int(aryTempUDT(0)) + i)) + "," + _  
   LTrim(Str(Int(aryTempUDT(1)) + i))  
  
' Insert the new value back into the database.  
cmd.CommandText = "UPDATE dbo.Points SET Pnt = '" + strNewUDT + _  
   "' WHERE ID = '" + strTempID + "'"  
cmd.Execute  
  
con.Close  
Set con = Nothing  
```  
  
### <a name="enabling-and-using-mars"></a><span data-ttu-id="d27a6-130">Habilitando e usando MARS</span><span class="sxs-lookup"><span data-stu-id="d27a6-130">Enabling and Using MARS</span></span>  
 <span data-ttu-id="d27a6-131">Neste exemplo, a cadeia de conexão é construída para habilitar MARS por meio do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo e, em seguida, dois objetos Recordset são criados para serem executados usando a mesma conexão.</span><span class="sxs-lookup"><span data-stu-id="d27a6-131">In this example, the connection string is constructed to enable MARS through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, and then two recordset objects are created to execute using the same connection.</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
  
Dim recordset1 As New ADODB.Recordset  
Dim recordset2 As New ADODB.Recordset  
  
Dim recordsaffected As Integer  
Set recordset1 =  con.Execute("SELECT * FROM Table1", recordsaffected, adCmdText)  
Set recordset2 =  con.Execute("SELECT * FROM Table2", recordsaffected, adCmdText)  
  
con.Close  
Set con = Nothing  
```  
  
 <span data-ttu-id="d27a6-132">Em versões anteriores do provedor OLE DB, esse código faria com que uma conexão implícita fosse criada na segunda execução porque apenas um conjunto de resultados ativo podia ser aberto por conexão.</span><span class="sxs-lookup"><span data-stu-id="d27a6-132">In prior versions of the OLE DB provider, this code would cause an implicit connection to be created on the second execution because only one active set of results could be opened per a single connection.</span></span> <span data-ttu-id="d27a6-133">Como a conexão implícita não foi agrupada no pool de conexões OLE DB, isso causaria uma sobrecarga adicional.</span><span class="sxs-lookup"><span data-stu-id="d27a6-133">Because the implicit connection was not pooled in the OLE DB connection pool this would cause additional overhead.</span></span> <span data-ttu-id="d27a6-134">Com o recurso MARS exposto pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, você obtém vários resultados ativos em uma conexão.</span><span class="sxs-lookup"><span data-stu-id="d27a6-134">With the MARS feature exposed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, you get multiple active results on the one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27a6-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d27a6-135">See Also</span></span>  
 [<span data-ttu-id="d27a6-136">Criando aplicativos com o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d27a6-136">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
