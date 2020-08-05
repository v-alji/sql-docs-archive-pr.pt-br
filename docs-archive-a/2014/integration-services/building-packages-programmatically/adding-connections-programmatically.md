---
title: Adicionar conexões programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- connection managers [Integration Services], packages
- Integration Services packages, connections
- connections [Integration Services], packages
- SSIS packages, connections
- packages [Integration Services], connections
- intrinsic properties [Integration Services]
- SQL Server Integration Services packages, connections
- ConnectionManager class
- SSIS connection managers
- adding package connections
ms.assetid: d90716d1-4c65-466c-b82c-4aabbee1e3e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5952221dbf2689d2328695baf965ce884dc07fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572656"
---
# <a name="adding-connections-programmatically"></a><span data-ttu-id="bb171-102">Adicionando conexões programaticamente</span><span class="sxs-lookup"><span data-stu-id="bb171-102">Adding Connections Programmatically</span></span>
  <span data-ttu-id="bb171-103">A classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> representa conexões físicas com fontes de dados externas.</span><span class="sxs-lookup"><span data-stu-id="bb171-103">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class represents physical connections to external data sources.</span></span> <span data-ttu-id="bb171-104">A classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> isola os detalhes de implementação da conexão do runtime.</span><span class="sxs-lookup"><span data-stu-id="bb171-104">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class isolates the implementation details of the connection from the runtime.</span></span> <span data-ttu-id="bb171-105">Isso permite que o runtime interaja com cada gerenciador de conexões de uma maneira consistente e previsível.</span><span class="sxs-lookup"><span data-stu-id="bb171-105">This enables the runtime to interact with each connection manager in a consistent and predictable manner.</span></span> <span data-ttu-id="bb171-106">Gerenciadores de conexões contêm um conjunto de propriedades de estoque que todas as conexões têm em comum, como <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="bb171-106">Connection managers contain a set of stock properties that all connections have in common, such as the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span></span> <span data-ttu-id="bb171-107">Porém, as propriedades <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> são, ordinariamente, as únicas propriedades necessárias para configurar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="bb171-107">However, the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> properties are ordinarily the only properties required to configure a connection manager.</span></span> <span data-ttu-id="bb171-108">Ao contrário de outros paradigmas de programação, em que as classes de conexão expõem métodos como `Open` ou `Connect` para estabelecer fisicamente uma conexão com a fonte de dados, o mecanismo de tempo de execução gerencia todas as conexões para o pacote enquanto ele é executado.</span><span class="sxs-lookup"><span data-stu-id="bb171-108">Unlike other programming paradigms, where connection classes expose methods such as `Open` or `Connect` to physically establish a connection to the data source, the run-time engine manages all the connections for the package while it runs.</span></span>  
  
 <span data-ttu-id="bb171-109">A classe <xref:Microsoft.SqlServer.Dts.Runtime.Connections> é uma coleção dos gerenciadores de conexões que foram adicionados ao pacote e estão disponíveis para uso em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="bb171-109">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> class is a collection of the connection managers that have been added to that package and are available for use at run time.</span></span> <span data-ttu-id="bb171-110">É possível adicionar mais gerenciadores de conexões à coleção usando o método <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> da coleção e fornecendo uma cadeia de caracteres que indica o tipo de gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="bb171-110">You can add more connection managers to the collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method of the collection, and supplying a string that indicates the connection manager type.</span></span> <span data-ttu-id="bb171-111">O método <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> retorna a instância <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> que foi acrescentada ao pacote.</span><span class="sxs-lookup"><span data-stu-id="bb171-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method returns the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> instance that was added to the package.</span></span>  
  
## <a name="intrinsic-properties"></a><span data-ttu-id="bb171-112">Propriedades intrínsecas</span><span class="sxs-lookup"><span data-stu-id="bb171-112">Intrinsic Properties</span></span>  
 <span data-ttu-id="bb171-113">A classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> expõe um conjunto de propriedades que são comuns a todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="bb171-113">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class exposes a set of properties that are common to all connections.</span></span> <span data-ttu-id="bb171-114">Porém, às vezes você precisa de acesso a propriedades que são exclusivas ao tipo de conexão específico.</span><span class="sxs-lookup"><span data-stu-id="bb171-114">However, sometimes you need access to properties that are unique to the specific connection type.</span></span> <span data-ttu-id="bb171-115">A coleção <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> da classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> fornece acesso a essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="bb171-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class provides access to these properties.</span></span> <span data-ttu-id="bb171-116">As propriedades podem ser recuperadas da coleção usando o indexador ou o nome da propriedade e o método **GetValue**, sendo que os valores são definidos usando o método **SetValue**.</span><span class="sxs-lookup"><span data-stu-id="bb171-116">The properties can be retrieved from the collection using the indexer or the property name and the **GetValue** method, and the values are set using the **SetValue** method.</span></span> <span data-ttu-id="bb171-117">As propriedades das propriedades do objeto de conexão subjacente também podem ser definidas adquirindo-se uma instância real do objeto e definindo suas propriedades diretamente.</span><span class="sxs-lookup"><span data-stu-id="bb171-117">The properties of the underlying connection object properties can also be set by acquiring an actual instance of the object and setting its properties directly.</span></span> <span data-ttu-id="bb171-118">Para obter a conexão subjacente, use a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="bb171-118">To get the underlying connection, use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> property of the connection manager.</span></span> <span data-ttu-id="bb171-119">A linha de código seguinte mostra uma linha C# que cria um gerenciador de conexões ADO.NET que tem a classe subjacente <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span><span class="sxs-lookup"><span data-stu-id="bb171-119">The following line of code shows a C# line that creates an ADO.NET connection manager that has the underlying class, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span></span>  
  
 `ConnectionManagerAdoNetClass cmado = cm.InnerObject as ConnectionManagerAdoNet;`  
  
 <span data-ttu-id="bb171-120">Isso converte o objeto do gerenciador de conexões gerenciado em seu objeto de conexão subjacente.</span><span class="sxs-lookup"><span data-stu-id="bb171-120">This casts the managed connection manager object to its underlying connection object.</span></span> <span data-ttu-id="bb171-121">Se você estiver usando C++, o método `QueryInterface` do objeto <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> será chamado e a interface do objeto de conexão subjacente será requisitado.</span><span class="sxs-lookup"><span data-stu-id="bb171-121">If you are using C++, the `QueryInterface` method of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object is called and the interface of the underlying connection object is requested.</span></span>  
  
 <span data-ttu-id="bb171-122">A tabela a seguir lista os gerenciadores de conexão incluídos no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb171-122">The following table lists the connection managers included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="bb171-123">e a cadeia de caracteres que é usada na instrução `package.Connections.Add("xxx")`.</span><span class="sxs-lookup"><span data-stu-id="bb171-123">and the string that is used in the `package.Connections.Add("xxx")` statement.</span></span> <span data-ttu-id="bb171-124">Para saber mais sobre gerenciadores de conexões, consulte [Conexões do SSIS &#40;Integration Services&#41;](../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="bb171-124">For a list of all connection managers, see [Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
|<span data-ttu-id="bb171-125">String</span><span class="sxs-lookup"><span data-stu-id="bb171-125">String</span></span>|<span data-ttu-id="bb171-126">Gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="bb171-126">Connection manager</span></span>|  
|------------|------------------------|  
|<span data-ttu-id="bb171-127">"OLEDB"</span><span class="sxs-lookup"><span data-stu-id="bb171-127">"OLEDB"</span></span>|<span data-ttu-id="bb171-128">Gerenciador de conexões para conexões OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bb171-128">Connection manager for OLE DB connections.</span></span>|  
|<span data-ttu-id="bb171-129">"ODBC"</span><span class="sxs-lookup"><span data-stu-id="bb171-129">"ODBC"</span></span>|<span data-ttu-id="bb171-130">Gerenciador de conexões para conexões ODBC.</span><span class="sxs-lookup"><span data-stu-id="bb171-130">Connection manager for ODBC connections.</span></span>|  
|<span data-ttu-id="bb171-131">"ADO"</span><span class="sxs-lookup"><span data-stu-id="bb171-131">"ADO"</span></span>|<span data-ttu-id="bb171-132">Gerenciador de conexões para conexões ADO.</span><span class="sxs-lookup"><span data-stu-id="bb171-132">Connection manager for ADO connections.</span></span>|  
|<span data-ttu-id="bb171-133">"ADO.NET:SQL"</span><span class="sxs-lookup"><span data-stu-id="bb171-133">"ADO.NET:SQL"</span></span>|<span data-ttu-id="bb171-134">Gerenciador de conexões para conexões ADO.NET (provedor de dados SQL).</span><span class="sxs-lookup"><span data-stu-id="bb171-134">Connection manager for ADO.NET (SQL data provider) connections.</span></span>|  
|<span data-ttu-id="bb171-135">"ADO.NET:OLEDB"</span><span class="sxs-lookup"><span data-stu-id="bb171-135">"ADO.NET:OLEDB"</span></span>|<span data-ttu-id="bb171-136">Gerenciador de conexões para conexões ADO.NET (provedor de dados OLE DB).</span><span class="sxs-lookup"><span data-stu-id="bb171-136">Connection manager for ADO.NET (OLE DB data provider) connections.</span></span>|  
|<span data-ttu-id="bb171-137">"FLATFILE"</span><span class="sxs-lookup"><span data-stu-id="bb171-137">"FLATFILE"</span></span>|<span data-ttu-id="bb171-138">Gerenciador de conexões para conexões de arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="bb171-138">Connection manager for flat file connections.</span></span>|  
|<span data-ttu-id="bb171-139">"FILE"</span><span class="sxs-lookup"><span data-stu-id="bb171-139">"FILE"</span></span>|<span data-ttu-id="bb171-140">Gerenciador de conexões para conexões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="bb171-140">Connection manager for file connections.</span></span>|  
|<span data-ttu-id="bb171-141">"MULTIFLATFILE"</span><span class="sxs-lookup"><span data-stu-id="bb171-141">"MULTIFLATFILE"</span></span>|<span data-ttu-id="bb171-142">Gerenciador de conexões para múltiplas conexões de arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="bb171-142">Connection manager for multiple flat file connections.</span></span>|  
|<span data-ttu-id="bb171-143">"MULTIFILE"</span><span class="sxs-lookup"><span data-stu-id="bb171-143">"MULTIFILE"</span></span>|<span data-ttu-id="bb171-144">Gerenciador de conexões para múltiplas conexões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="bb171-144">Connection manager for multiple file connections.</span></span>|  
|<span data-ttu-id="bb171-145">"SQLMOBILE"</span><span class="sxs-lookup"><span data-stu-id="bb171-145">"SQLMOBILE"</span></span>|<span data-ttu-id="bb171-146">Gerenciador de conexões para conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="bb171-146">Connection manager for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connections.</span></span>|  
|<span data-ttu-id="bb171-147">"MSOLAP100"</span><span class="sxs-lookup"><span data-stu-id="bb171-147">"MSOLAP100"</span></span>|<span data-ttu-id="bb171-148">Gerenciador de conexões para conexões [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb171-148">Connection manager for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connections.</span></span>|  
|<span data-ttu-id="bb171-149">"FTP"</span><span class="sxs-lookup"><span data-stu-id="bb171-149">"FTP"</span></span>|<span data-ttu-id="bb171-150">Gerenciador de conexões para conexões FTP.</span><span class="sxs-lookup"><span data-stu-id="bb171-150">Connection manager for FTP connections.</span></span>|  
|<span data-ttu-id="bb171-151">"HTTP"</span><span class="sxs-lookup"><span data-stu-id="bb171-151">"HTTP"</span></span>|<span data-ttu-id="bb171-152">Gerenciador de conexões para conexões HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb171-152">Connection manager for HTTP connections.</span></span>|  
|<span data-ttu-id="bb171-153">"MSMQ"</span><span class="sxs-lookup"><span data-stu-id="bb171-153">"MSMQ"</span></span>|<span data-ttu-id="bb171-154">Gerenciador de conexões para conexões do serviço de enfileiramento de mensagens (também conhecido como MSMQ).</span><span class="sxs-lookup"><span data-stu-id="bb171-154">Connection manager for Message Queuing (also known as MSMQ) connections.</span></span>|  
|<span data-ttu-id="bb171-155">"SMTP"</span><span class="sxs-lookup"><span data-stu-id="bb171-155">"SMTP"</span></span>|<span data-ttu-id="bb171-156">Gerenciador de conexões para conexões SMTP.</span><span class="sxs-lookup"><span data-stu-id="bb171-156">Connection manager for SMTP connections.</span></span>|  
|<span data-ttu-id="bb171-157">"WMI"</span><span class="sxs-lookup"><span data-stu-id="bb171-157">"WMI"</span></span>|<span data-ttu-id="bb171-158">Gerenciador de conexões para conexões do Microsoft Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="bb171-158">Connection manager for Microsoft Windows Management Instrumentation (WMI) connections.</span></span>|  
  
 <span data-ttu-id="bb171-159">O exemplo de código a seguir demonstra como adicionar uma conexão OLE DB e FILE à coleção <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> de um <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span><span class="sxs-lookup"><span data-stu-id="bb171-159">The following code example demonstrates adding an OLE DB and FILE connection to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> collection of a <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span></span> <span data-ttu-id="bb171-160">Em seguida, o exemplo define as propriedades <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="bb171-160">The example then sets the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> properties.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      // Create a package, and retrieve its connections.  
      Package pkg = new Package();  
      Connections pkgConns = pkg.Connections;  
  
      // Add an OLE DB connection to the package, using the   
      // method defined in the AddConnection class.  
      CreateConnection myOLEDBConn = new CreateConnection();  
      myOLEDBConn.CreateOLEDBConnection(pkg);  
  
      // View the new connection in the package.  
      Console.WriteLine("Connection description: {0}",  
         pkg.Connections["SSIS Connection Manager for OLE DB"].Description);  
  
      // Add a second connection to the package.  
      CreateConnection myFileConn = new CreateConnection();  
      myFileConn.CreateFileConnection(pkg);  
  
      // View the second connection in the package.  
      Console.WriteLine("Connection description: {0}",  
        pkg.Connections["SSIS Connection Manager for Files"].Description);  
  
      Console.WriteLine();  
      Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count);  
  
      Console.Read();  
    }  
  }  
  // <summary>  
  // This class contains the definitions for multiple  
  // connection managers.  
  // </summary>  
  public class CreateConnection  
  {  
    // Private data.  
    private ConnectionManager ConMgr;  
  
    // Class definition for OLE DB Provider.  
    public void CreateOLEDBConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("OLEDB");  
      ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" +  
        "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" +  
        "Data Source=(local);";  
      ConMgr.Name = "SSIS Connection Manager for OLE DB";  
      ConMgr.Description = "OLE DB connection to the AdventureWorks database.";  
    }  
    public void CreateFileConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("File");  
      ConMgr.ConnectionString = @"\\<yourserver>\<yourfolder>\books.xml";  
      ConMgr.Name = "SSIS Connection Manager for Files";  
      ConMgr.Description = "Flat File connection";  
    }  
  }  
  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    ' Create a package, and retrieve its connections.  
    Dim pkg As New Package()  
    Dim pkgConns As Connections = pkg.Connections  
  
    ' Add an OLE DB connection to the package, using the   
    ' method defined in the AddConnection class.  
    Dim myOLEDBConn As New CreateConnection()  
    myOLEDBConn.CreateOLEDBConnection(pkg)  
  
    ' View the new connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for OLE DB").Description)  
  
    ' Add a second connection to the package.  
    Dim myFileConn As New CreateConnection()  
    myFileConn.CreateFileConnection(pkg)  
  
    ' View the second connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for Files").Description)  
  
    Console.WriteLine()  
    Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
' This class contains the definitions for multiple  
' connection managers.  
  
Public Class CreateConnection  
  ' Private data.  
  Private ConMgr As ConnectionManager  
  
  ' Class definition for OLE DB provider.  
  Public Sub CreateOLEDBConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("OLEDB")  
    ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" & _  
      "Data Source=(local);"  
    ConMgr.Name = "SSIS Connection Manager for OLE DB"  
    ConMgr.Description = "OLE DB connection to the AdventureWorks database."  
  End Sub  
  
  Public Sub CreateFileConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("File")  
    ConMgr.ConnectionString = "\\<yourserver>\<yourfolder>\books.xml"  
    ConMgr.Name = "SSIS Connection Manager for Files"  
    ConMgr.Description = "Flat File connection"  
  End Sub  
  
End Class  
```  
  
 <span data-ttu-id="bb171-161">**Saída de exemplo:**</span><span class="sxs-lookup"><span data-stu-id="bb171-161">**Sample Output:**</span></span>  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Number of connections in package: 2`  
  
## <a name="external-resources"></a><span data-ttu-id="bb171-162">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="bb171-162">External Resources</span></span>  
 <span data-ttu-id="bb171-163">Artigo técnico, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743) (Cadeias de conexão), em carlprothman.</span><span class="sxs-lookup"><span data-stu-id="bb171-163">Technical article, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743), on carlprothman.net.</span></span>  
  
<span data-ttu-id="bb171-164">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="bb171-164">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bb171-165">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="bb171-165">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bb171-166">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="bb171-166">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bb171-167">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="bb171-167">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb171-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb171-168">See Also</span></span>  
 <span data-ttu-id="bb171-169">[Integration Services &#40;conexões&#41; SSIS](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="bb171-169">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="bb171-170">Criar gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="bb171-170">Create Connection Managers</span></span>](../create-connection-managers.md)  
  
  
