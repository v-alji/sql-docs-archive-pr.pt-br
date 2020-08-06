---
title: Conectar-se a fontes de dados na Tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- connections [Integration Services], scripts
- Integration Services packages, connections
- connection managers [Integration Services], scripts
- scripts [Integration Services], connections
- SSIS packages, connections
- packages [Integration Services], connections
- Script task [Integration Services], connections
- Connections property
- SQL Server Integration Services packages, connections
- SSIS Script task, connections
ms.assetid: 9c008380-715b-455b-9da7-22572d67c388
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c8374271c7972498361a83e4bbe87ad12265827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680570"
---
# <a name="connecting-to-data-sources-in-the-script-task"></a><span data-ttu-id="178df-102">Conectando a fontes de dados na tarefa Script</span><span class="sxs-lookup"><span data-stu-id="178df-102">Connecting to Data Sources in the Script Task</span></span>
  <span data-ttu-id="178df-103">Gerenciadores de conexões fornecem acesso a fontes de dados que foram configuradas no pacote.</span><span class="sxs-lookup"><span data-stu-id="178df-103">Connection managers provide access to data sources that have been configured in the package.</span></span> <span data-ttu-id="178df-104">Para obter mais informações, consulte [Integration Services &#40;SSIS&#41; Conexões](../../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="178df-104">For more information, see [Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
 <span data-ttu-id="178df-105">A tarefa Script pode acessar esses gerenciadores de conexões pela propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> do objeto **Dts**.</span><span class="sxs-lookup"><span data-stu-id="178df-105">The Script task can access these connection managers through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property of the **Dts** object.</span></span> <span data-ttu-id="178df-106">Cada gerenciador de conexões na coleção <xref:Microsoft.SqlServer.Dts.Runtime.Connections> armazena informações sobre como conectar-se à fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="178df-106">Each connection manager in the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection stores information about how to connect to the underlying data source.</span></span>  
  
 <span data-ttu-id="178df-107">Quando você chama o método <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> de um gerenciador de conexões, este se conecta à fonte de dados, se já não estiver conectado, e retorna a conexão apropriada ou as informações da conexão para você utilizar no código da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="178df-107">When you call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a connection manager, the connection manager connects to the data source, if it is not already connected, and returns the appropriate connection or connection information for you to use in your Script task code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="178df-108">Você deve saber o tipo de conexão retornado pelo Gerenciador de conexões antes de chamar `AcquireConnection` .</span><span class="sxs-lookup"><span data-stu-id="178df-108">You must know the type of connection returned by the connection manager before calling `AcquireConnection`.</span></span> <span data-ttu-id="178df-109">Como a tarefa Script tem `Option Strict` habilitada, você deve converter a conexão, que é retornada como tipo `Object`, para o tipo de conexão adequado antes de poder usá-lo.</span><span class="sxs-lookup"><span data-stu-id="178df-109">Because the Script task has `Option Strict` enabled, you must cast the connection, which is returned as type `Object`, to the appropriate connection type before you can use it.</span></span>  
  
 <span data-ttu-id="178df-110">É possível usar o método <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> da coleção <xref:Microsoft.SqlServer.Dts.Runtime.Connections> retornada pela propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> para procurar uma conexão existente antes de usá-la no seu código.</span><span class="sxs-lookup"><span data-stu-id="178df-110">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property to look for an existing connection before using the connection in your code.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="178df-111">Você não pode chamar o método AcquireConnection de gerenciadores de conexões que retornam objetos não gerenciados, tais como o gerenciador de conexões OLE DB e o Excel, no código gerenciado de uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="178df-111">You cannot call the AcquireConnection method of connection managers that return unmanaged objects, such as the OLE DB connection manager and the Excel connection manager, in the managed code of a Script task.</span></span> <span data-ttu-id="178df-112">No entanto, você pode ler a propriedade ConnectionString desses gerenciadores de conexões e conectar-se à fonte de dados diretamente em seu código usando a cadeia de conexão com um `OledbConnection` do namespace **System. Data. OleDb** .</span><span class="sxs-lookup"><span data-stu-id="178df-112">However, you can read the ConnectionString property of these connection managers, and connect to the data source directly in your code by using the connection string with an `OledbConnection` from the **System.Data.OleDb** namespace.</span></span>  
>   
>  <span data-ttu-id="178df-113">Se você deve chamar o método AcquireConnection de um gerenciador de conexões que retorna um objeto não gerenciado, use um gerenciador de conexões [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="178df-113">If you must call the AcquireConnection method of a connection manager that returns an unmanaged object, use an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager.</span></span> <span data-ttu-id="178df-114">Quando você configura o gerenciador de conexões [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] para usar um provedor OLE DB, ele se conecta usando o Provedor de Dados [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] para OLE DB.</span><span class="sxs-lookup"><span data-stu-id="178df-114">When you configure the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager to use an OLE DB provider, it connects by using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB.</span></span> <span data-ttu-id="178df-115">Nesse caso, o método AcquireConnection retorna um `System.Data.OleDb.OleDbConnection` em vez de um objeto não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="178df-115">In this case, the AcquireConnection method returns a `System.Data.OleDb.OleDbConnection` instead of an unmanaged object.</span></span> <span data-ttu-id="178df-116">Para configurar um gerenciador de conexões [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] para usar com uma fonte de dados Excel, selecione o OLE DB Provider for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Jet, especifique um arquivo em Excel e insira `Excel 8.0` (para Excel 97 e mais recente) como valor de **Propriedades Estendidas** na página **Todas** da caixa de diálogo **Gerenciador de Conexões**.</span><span class="sxs-lookup"><span data-stu-id="178df-116">To configure an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager for use with an Excel data source, select the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB Provider for Jet, specify an Excel file, and enter `Excel 8.0` (for Excel 97 and later) as the value of **Extended Properties** on the **All** page of the **Connection Manager** dialog box.</span></span>  
  
## <a name="connections-example"></a><span data-ttu-id="178df-117">Exemplo de conexões</span><span class="sxs-lookup"><span data-stu-id="178df-117">Connections Example</span></span>  
 <span data-ttu-id="178df-118">O exemplo seguinte demonstra como acessar gerenciadores de conexões da tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="178df-118">The following example demonstrates how to access connection managers from within the Script task.</span></span> <span data-ttu-id="178df-119">A amostra supõe que você criou e configurou um gerenciador de conexões [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] chamado denominado **Testar Conexão ADO.NET** e um gerenciador de conexões de arquivo simples denominado **Testar Conexão de Arquivo Simples**.</span><span class="sxs-lookup"><span data-stu-id="178df-119">The sample assumes that you have created and configured an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager named **Test ADO.NET Connection** and a Flat File connection manager named **Test Flat File Connection**.</span></span> <span data-ttu-id="178df-120">Observe que o gerenciador de conexões [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] retorna um objeto `SqlConnection` que você pode usar para se conectar à fonte de dados imediatamente.</span><span class="sxs-lookup"><span data-stu-id="178df-120">Note that the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager returns a `SqlConnection` object that you can use immediately to connect to the data source.</span></span> <span data-ttu-id="178df-121">Por outro lado, o gerenciador de conexões de arquivo simples retorna só uma cadeia de caracteres que contém o caminho e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="178df-121">The Flat File connection manager, on the other hand, returns only a string that contains the path and file name.</span></span> <span data-ttu-id="178df-122">Você deve usar métodos do namespace `System.IO` para abrir e funcionar com o arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="178df-122">You must use methods from the `System.IO` namespace to open and work with the flat file.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myADONETConnection As SqlClient.SqlConnection  
    myADONETConnection = _  
        DirectCast(Dts.Connections("Test ADO.NET Connection").AcquireConnection(Dts.Transaction), _  
        SqlClient.SqlConnection)  
    MsgBox(myADONETConnection.ConnectionString, _  
        MsgBoxStyle.Information, "ADO.NET Connection")  
  
    Dim myFlatFileConnection As String  
    myFlatFileConnection = _  
        DirectCast(Dts.Connections("Test Flat File Connection").AcquireConnection(Dts.Transaction), _  
        String)  
    MsgBox(myFlatFileConnection, MsgBoxStyle.Information, "Flat File Connection")  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
  
public class ScriptMain  
{  
  
        public void Main()  
        {  
            SqlConnection myADONETConnection = new SqlConnection();  
            myADONETConnection = (SqlConnection)(Dts.Connections["Test ADO.NET Connection"].AcquireConnection(Dts.Transaction)as SqlConnection);  
            MessageBox.Show(myADONETConnection.ConnectionString, "ADO.NET Connection");  
  
            string myFlatFileConnection;  
            myFlatFileConnection = (string)(Dts.Connections["Test Flat File Connection"].AcquireConnection(Dts.Transaction) as String);  
            MessageBox.Show(myFlatFileConnection, "Flat File Connection");  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
  
```  
  
<span data-ttu-id="178df-123">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="178df-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="178df-124">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="178df-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="178df-125">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="178df-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="178df-126">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="178df-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="178df-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="178df-127">See Also</span></span>  
 <span data-ttu-id="178df-128">[Integration Services &#40;conexões&#41; SSIS](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="178df-128">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="178df-129">Criar gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="178df-129">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
