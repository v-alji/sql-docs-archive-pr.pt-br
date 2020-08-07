---
title: Recuperando dados UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SqlDataReader object
- ADO.NET [CLR integration]
- binding UDTs [CLR integration]
- UDTs [CLR integration], ADO.NET
- assemblies [CLR integration], user-defined types
- query parameters [CLR integration]
- user-defined types [CLR integration], ADO.NET
- bytes [CLR integration]
ms.assetid: 6a98ac8c-0e69-4c03-83a4-2062cb782049
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9133ea45069f76e7590f6b74d3c1e1cb98c7bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575883"
---
# <a name="retrieving-udt-data"></a><span data-ttu-id="89c95-102">Recuperando dados UDT</span><span class="sxs-lookup"><span data-stu-id="89c95-102">Retrieving UDT Data</span></span>
  <span data-ttu-id="89c95-103">Para criar um tipo definido pelo usuário (UDT) no cliente, o assembly que foi registrado como UDT em um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve estar disponível para o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="89c95-103">In order to create a user-defined type (UDT) on the client, the assembly that was registered as a UDT in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database must be available to the client application.</span></span> <span data-ttu-id="89c95-104">O assembly UDT pode ser colocado no mesmo diretório que o aplicativo ou no Cache de Assembly Global (GAC).</span><span class="sxs-lookup"><span data-stu-id="89c95-104">The UDT assembly can be placed in the same directory with the application, or in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="89c95-105">Também é possível definir uma referência para o assembly em seu projeto.</span><span class="sxs-lookup"><span data-stu-id="89c95-105">You can also set a reference to the assembly in your project.</span></span>  
  
## <a name="requirements-for-using-udts-in-adonet"></a><span data-ttu-id="89c95-106">Requisitos para usar UDTs no ADO.NET</span><span class="sxs-lookup"><span data-stu-id="89c95-106">Requirements for Using UDTs in ADO.NET</span></span>  
 <span data-ttu-id="89c95-107">O assembly carregado no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o assembly no cliente devem ser compatíveis para que o UDT seja criado no cliente.</span><span class="sxs-lookup"><span data-stu-id="89c95-107">The assembly loaded in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the assembly on the client must be compatible in order for the UDT to be created on the client.</span></span> <span data-ttu-id="89c95-108">Para UDTs definidos com o formato de serialização do `Native`, os assemblies devem ser estruturalmente compatíveis.</span><span class="sxs-lookup"><span data-stu-id="89c95-108">For UDTs defined with the `Native` serialization format, the assemblies must be structurally compatible.</span></span> <span data-ttu-id="89c95-109">Para assemblies definidos com o formato `UserDefined`, os assembly devem estar disponível no cliente.</span><span class="sxs-lookup"><span data-stu-id="89c95-109">For assemblies defined with the `UserDefined` format, the assembly must be available on the client.</span></span>  
  
 <span data-ttu-id="89c95-110">Não é necessário ter uma cópia do assembly UDT no cliente para recuperar os dados raw de uma coluna UDT em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="89c95-110">You do not need a copy of the UDT assembly on the client in order to retrieve the raw data from a UDT column in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89c95-111">O **SqlClient** pode falhar ao carregar um UDT no caso de versões UDT incompatíveis ou outros problemas.</span><span class="sxs-lookup"><span data-stu-id="89c95-111">**SqlClient** may fail to load a UDT in the event of mismatched UDT versions or other problems.</span></span> <span data-ttu-id="89c95-112">Nesse caso, use os mecanismos de solução de problemas comuns para determinar porque o assembly que contém o UDT não pode ser localizado pelo aplicativo que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="89c95-112">In this case, use regular troubleshooting mechanisms to determine why the assembly containing the UDT cannot be found by the calling application.</span></span> <span data-ttu-id="89c95-113">Para obter mais informações, consulte o tópico "Diagnosticando erros com Assistentes para Depuração Gerenciada" na documentação do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="89c95-113">For more information, read the topic titled "Diagnosing Errors with Managed Debugging Assistants" in the .NET Framework documentation.</span></span>  
  
## <a name="accessing-udts-with-a-sqldatareader"></a><span data-ttu-id="89c95-114">Acessando UDTs com um SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="89c95-114">Accessing UDTs with a SqlDataReader</span></span>  
 <span data-ttu-id="89c95-115">Um `System.Data.SqlClient.SqlDataReader` pode ser usado no código do cliente para recuperar um conjunto de resultados que contém uma coluna UDT que está exposta como uma instância do objeto.</span><span class="sxs-lookup"><span data-stu-id="89c95-115">A `System.Data.SqlClient.SqlDataReader` can be used from client code to retrieve a result set that contains a UDT column, which is exposed as an instance of the object.</span></span>  
  
### <a name="example"></a><span data-ttu-id="89c95-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="89c95-116">Example</span></span>  
 <span data-ttu-id="89c95-117">Este exemplo mostra como usar o método `Main` para criar um novo objeto `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="89c95-117">This example shows how to use the `Main` method to create a new `SqlDataReader` object.</span></span> <span data-ttu-id="89c95-118">As ações a seguir ocorrem no exemplo de código:</span><span class="sxs-lookup"><span data-stu-id="89c95-118">The following actions occur within the code example:</span></span>  
  
1.  <span data-ttu-id="89c95-119">O método Main cria um novo objeto `SqlDataReader` e recupera os valores da tabela Points, que tem uma coluna de UDT denominada Point.</span><span class="sxs-lookup"><span data-stu-id="89c95-119">The Main method creates a new `SqlDataReader` object and retrieves the values from the Points table, which has a UDT column named Point.</span></span>  
  
2.  <span data-ttu-id="89c95-120">O UDT de Point expõe as coordenadas X e Y definidas como inteiros.</span><span class="sxs-lookup"><span data-stu-id="89c95-120">The Point UDT exposes X and Y coordinates defined as integers.</span></span>  
  
3.  <span data-ttu-id="89c95-121">O UDT define um método `Distance` e um método `GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="89c95-121">The UDT defines a `Distance` method and a `GetDistanceFromXY` method.</span></span>  
  
4.  <span data-ttu-id="89c95-122">O código de exemplo recupera os valores da chave primária e das colunas UDT para demonstrar os recursos do UDT.</span><span class="sxs-lookup"><span data-stu-id="89c95-122">The sample code retrieves the values of the primary key and UDT columns in order to demonstrate the capabilities of the UDT.</span></span>  
  
5.  <span data-ttu-id="89c95-123">O código de exemplo chama os métodos `Point.Distance` e `Point.GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="89c95-123">The sample code calls the `Point.Distance` and `Point.GetDistanceFromXY` methods.</span></span>  
  
6.  <span data-ttu-id="89c95-124">Os resultados são exibidos na janela do console.</span><span class="sxs-lookup"><span data-stu-id="89c95-124">The results are displayed in the console window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89c95-125">O aplicativo já deve ter uma referência para o assembly UDT.</span><span class="sxs-lookup"><span data-stu-id="89c95-125">The application must already have a reference to the UDT assembly.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module ReadPoints  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the value of the UDT  
                Dim pnt As Point = CType(rdr(1), Point)  
  
             ' You can also use GetSqlValue and GetValue  
             ' Dim pnt As Point = CType(rdr.GetSqlValue(1), Point)  
             ' Dim pnt As Point = CType(rdr.GetValue(1), Point)  
  
                ' Print values  
                Console.WriteLine( _  
                 "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}", _  
                  id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance())  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
         & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
namespace Microsoft.Samples.SqlServer  
{  
class ReadPoints  
{  
static void Main()  
{  
  string connectionString = GetConnectionString();  
  using (SqlConnection cnn = new SqlConnection(connectionString))  
  {  
    cnn.Open();  
    SqlCommand cmd = new SqlCommand(  
       "SELECT ID, Pnt FROM dbo.Points", cnn);  
    SqlDataReader rdr = cmd.ExecuteReader();  
  
    while (rdr.Read())  
    {  
      // Retrieve the value of the Primary Key column  
      int id = rdr.GetInt32(0);  
  
        // Retrieve the value of the UDT  
        Point pnt = (Point)rdr[1];  
  
        // You can also use GetSqlValue and GetValue  
        // Point pnt = (Point)rdr.GetSqlValue(1);  
        // Point pnt = (Point)rdr.GetValue(1);  
  
        Console.WriteLine(  
        "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}",   
        id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance());  
    }  
  rdr.Close();  
  Console.WriteLine("done");  
  }  
  static private string GetConnectionString()  
  {  
    // To avoid storing the connection string in your code,   
    // you can retrieve it from a configuration file.  
    return "Data Source=(local);Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="binding-udts-as-bytes"></a><span data-ttu-id="89c95-126">Associando UDTs como bytes</span><span class="sxs-lookup"><span data-stu-id="89c95-126">Binding UDTs as Bytes</span></span>  
 <span data-ttu-id="89c95-127">Em algumas situações, você pode desejar recuperar os dados raw da coluna UDT.</span><span class="sxs-lookup"><span data-stu-id="89c95-127">In some situations, you may want to retrieve the raw data from the UDT column.</span></span> <span data-ttu-id="89c95-128">Talvez o tipo não esteja disponível localmente ou você não queira instanciar uma instância uma instância do UDT.</span><span class="sxs-lookup"><span data-stu-id="89c95-128">Perhaps the type is not available locally, or you do not wish to instantiate an instance of the UDT.</span></span> <span data-ttu-id="89c95-129">Você pode ler os bytes brutos em uma matriz de bytes usando o método **GetBytes** de um `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="89c95-129">You can read the raw bytes into a byte array using the **GetBytes** method of a `SqlDataReader`.</span></span> <span data-ttu-id="89c95-130">Esse método lê um fluxo de bytes do deslocamento de coluna especificado no buffer de uma matriz, começando com um deslocamento de buffer especificado.</span><span class="sxs-lookup"><span data-stu-id="89c95-130">This method reads a stream of bytes from the specified column offset into the buffer of an array starting at a specified buffer offset.</span></span> <span data-ttu-id="89c95-131">Outra opção é usar um dos métodos **GetSqlBytes** ou **GetSqlBinary** e ler todo o conteúdo em uma única operação.</span><span class="sxs-lookup"><span data-stu-id="89c95-131">Another option is to use one of the **GetSqlBytes** or **GetSqlBinary** methods and read all of the contents in a single operation.</span></span> <span data-ttu-id="89c95-132">De qualquer maneira, o objeto UDT nunca é instanciado; assim, não é necessário definir uma referência para o UDT no assembly cliente.</span><span class="sxs-lookup"><span data-stu-id="89c95-132">In either case, the UDT object is never instantiated, so you do not need to set a reference to the UDT in the client assembly.</span></span>  
  
### <a name="example"></a><span data-ttu-id="89c95-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="89c95-133">Example</span></span>  
 <span data-ttu-id="89c95-134">Este exemplo mostra como recuperar os dados do **ponto** como bytes brutos em uma matriz de bytes usando um `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="89c95-134">This example shows how to retrieve the **Point** data as raw bytes into a byte array using a `SqlDataReader`.</span></span> <span data-ttu-id="89c95-135">O código usa um `System.Text.StringBuilder` para converter os bytes brutos em uma representação de cadeia de caracteres a ser exibida na janela do console.</span><span class="sxs-lookup"><span data-stu-id="89c95-135">The code uses a `System.Text.StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the raw bytes into a byte array  
                Dim buffer(31) As Byte  
                Dim byteCount As Integer = _  
                 CInt(rdr.GetBytes(1, 0, buffer, 0, 31))  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", buffer(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
        string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand("SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Retrieve the raw bytes into a byte array  
                byte[] buffer = new byte[32];  
                long byteCount = rdr.GetBytes(1, 0, buffer, 0, 32);  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", buffer[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
### <a name="example-using-getsqlbytes"></a><span data-ttu-id="89c95-136">Exemplo de uso de GetSqlBytes</span><span class="sxs-lookup"><span data-stu-id="89c95-136">Example Using GetSqlBytes</span></span>  
 <span data-ttu-id="89c95-137">Este exemplo mostra como recuperar os dados do **ponto** como bytes brutos em uma única operação usando o método **GetSqlBytes** .</span><span class="sxs-lookup"><span data-stu-id="89c95-137">This example shows how to retrieve the **Point** data as raw bytes in a single operation using the **GetSqlBytes** method.</span></span> <span data-ttu-id="89c95-138">O código usa um `StringBuilder` para converter os bytes brutos em uma representação de cadeia de caracteres a ser exibida na janela do console.</span><span class="sxs-lookup"><span data-stu-id="89c95-138">The code uses a `StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Use SqlBytes to retrieve raw bytes  
                Dim sb As SqlBytes = rdr.GetSqlBytes(1)  
                Dim byteCount As Long = sb.Length  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", sb(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
         string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Use SqlBytes to retrieve raw bytes  
                SqlBytes sb = rdr.GetSqlBytes(1);  
                long byteCount = sb.Length;  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", sb[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="working-with-udt-parameters"></a><span data-ttu-id="89c95-139">Trabalhando com parâmetros UDT</span><span class="sxs-lookup"><span data-stu-id="89c95-139">Working with UDT Parameters</span></span>  
 <span data-ttu-id="89c95-140">Os UDTs podem ser usados como parâmetros de entrada e de saída no código do ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="89c95-140">UDTs can be used as both input and output parameters in your ADO.NET code.</span></span>  
  
## <a name="using-udts-in-query-parameters"></a><span data-ttu-id="89c95-141">Usando UDTs em parâmetros de consulta</span><span class="sxs-lookup"><span data-stu-id="89c95-141">Using UDTs in Query Parameters</span></span>  
 <span data-ttu-id="89c95-142">Os UDTs podem ser usados como valores de parâmetros ao configurar um `SqlParameter` para um objeto `System.Data.SqlClient.SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="89c95-142">UDTs can be used as parameter values when setting up a `SqlParameter` for a `System.Data.SqlClient.SqlCommand` object.</span></span> <span data-ttu-id="89c95-143">A enumeração `SqlDbType.Udt` de um objeto `SqlParameter` é usada para indicar que o parâmetro é um UDT ao chamar o método `Add` para a coleção `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="89c95-143">The `SqlDbType.Udt` enumeration of a `SqlParameter` object is used to indicate that the parameter is a UDT when calling the `Add` method to the `Parameters` collection.</span></span> <span data-ttu-id="89c95-144">A `UdtTypeName` propriedade de um `SqlCommand` objeto é usada para especificar o nome totalmente qualificado do UDT no banco de dados usando a sintaxe *Database. schema_name. object_name* .</span><span class="sxs-lookup"><span data-stu-id="89c95-144">The `UdtTypeName` property of a `SqlCommand` object is used to specify the fully qualified name of the UDT in the database using the *database.schema_name.object_name* syntax.</span></span> <span data-ttu-id="89c95-145">Embora não seja necessário, o uso do nome totalmente qualificado elimina a ambiguidade do código.</span><span class="sxs-lookup"><span data-stu-id="89c95-145">Although it is not required, using the fully qualified name removes ambiguity from your code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89c95-146">Uma cópia local do assembly UDT deve estar disponível para o projeto cliente.</span><span class="sxs-lookup"><span data-stu-id="89c95-146">A local copy of the UDT assembly must be available to the client project.</span></span>  
  
### <a name="example"></a><span data-ttu-id="89c95-147">Exemplo</span><span class="sxs-lookup"><span data-stu-id="89c95-147">Example</span></span>  
 <span data-ttu-id="89c95-148">O código neste exemplo cria objetos `SqlCommand` e `SqlParameter` para inserir dados em uma coluna UDT em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="89c95-148">The code in this example creates `SqlCommand` and `SqlParameter` objects to insert data into a UDT column in a table.</span></span> <span data-ttu-id="89c95-149">O código usa a enumeração `SqlDbType.Udt` para especificar o tipo de dados e a propriedade `UdtTypeName` do objeto `SqlParameter` para especificar o nome totalmente qualificado do UDT no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="89c95-149">The code uses the `SqlDbType.Udt` enumeration to specify the data type, and the `UdtTypeName` property of the `SqlParameter` object to specify the fully qualified name of the UDT in the database.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports system.Data  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim ConnectionString As String = GetConnectionString()  
    Dim cnn As New SqlConnection(ConnectionString)  
    Using cnn  
      Dim cmd As SqlCommand = cnn.CreateCommand()  
      cmd.CommandText = "INSERT INTO dbo.Points (Pnt) VALUES (@Point)"  
      cmd.CommandType = CommandType.Text  
  
      Dim param As New SqlParameter("@Point", SqlDbType.Udt)      param.UdtTypeName = "TestPoint.dbo.Point"      param.Direction = ParameterDirection.Input      param.Value = New Point(5, 6)      cmd.Parameters.Add(param)  
  
      cnn.Open()  
      cmd.ExecuteNonQuery()  
      Console.WriteLine("done")  
    End Using  
  End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
class Class1  
{  
static void Main()  
{  
  string ConnectionString = GetConnectionString();  
     using (SqlConnection cnn = new SqlConnection(ConnectionString))  
     {  
       SqlCommand cmd = cnn.CreateCommand();  
       cmd.CommandText =   
         "INSERT INTO dbo.Points (Pnt) VALUES (@Point)";  
       cmd.CommandType = CommandType.Text;  
  
       SqlParameter param = new SqlParameter("@Point", SqlDbType.Udt);       param.UdtTypeName = "TestPoint.dbo.Point";       param.Direction = ParameterDirection.Input;       param.Value = new Point(5, 6);       cmd.Parameters.Add(param);  
  
       cnn.Open();  
       cmd.ExecuteNonQuery();  
       Console.WriteLine("done");  
     }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="89c95-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89c95-150">See Also</span></span>  
 [<span data-ttu-id="89c95-151">Acessando tipos definidos pelo usuário no ADO.NET</span><span class="sxs-lookup"><span data-stu-id="89c95-151">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
