---
title: Desconectando de uma instância do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, disconnecting
- SMO [SQL Server], disconnecting
- instances of SQL Server, disconnecting
- disconnecting [SMO]
ms.assetid: 4ca7f7eb-6b3f-4c73-ac63-88afa8570b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3514fce8fb8f1ccc8bd1b54acfa27825eaebbd34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582942"
---
# <a name="disconnecting-from-an-instance-of-sql-server"></a><span data-ttu-id="2df93-102">Desconectando de uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="2df93-102">Disconnecting from an Instance of SQL Server</span></span>
  <span data-ttu-id="2df93-103">O fechamento e a desconexão manuais do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] SMO (SQL Management Objects) não são necessários.</span><span class="sxs-lookup"><span data-stu-id="2df93-103">Manually closing and disconnecting [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects is not required.</span></span> <span data-ttu-id="2df93-104">As conexões são abertas e fechadas, conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="2df93-104">Connections are opened and closed as required.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="2df93-105">Pool de conexões</span><span class="sxs-lookup"><span data-stu-id="2df93-105">Connection Pooling</span></span>  
 <span data-ttu-id="2df93-106">Quando o método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> é chamado, a conexão não é liberada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2df93-106">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not automatically released.</span></span> <span data-ttu-id="2df93-107">O método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> deve ser chamado explicitamente para liberar a conexão com o pool de conexões.</span><span class="sxs-lookup"><span data-stu-id="2df93-107">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method must be called explicitly to release the connection to the connection pool.</span></span> <span data-ttu-id="2df93-108">Você também pode solicitar uma conexão não inserida no pool.</span><span class="sxs-lookup"><span data-stu-id="2df93-108">Also, you can request a non-pooled connection.</span></span> <span data-ttu-id="2df93-109">Para isso, defina a propriedade <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> da propriedade <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> que faz referência ao objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="2df93-109">You do this by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property that references the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="disconnecting-from-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="2df93-110">Desconectando de uma instância do SQL Server para RMO</span><span class="sxs-lookup"><span data-stu-id="2df93-110">Disconnecting from an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="2df93-111">O fechamento de conexões de servidor quando você está programando com RMO é um pouco diferente do que quando a programação é feita com SMO.</span><span class="sxs-lookup"><span data-stu-id="2df93-111">Closing server connections when you are programming with RMO works slightly different from SMO.</span></span>  
  
 <span data-ttu-id="2df93-112">Como a conexão do servidor para um objeto RMO é mantida pelo <xref:Microsoft.SqlServer.Management.Common.ServerConnection> objeto, esse objeto também é usado ao desconectar-se de uma instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando você programa usando o RMO.</span><span class="sxs-lookup"><span data-stu-id="2df93-112">Because the server connection for an RMO object is maintained by the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, this object is also used when disconnecting from an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when you program by using RMO.</span></span> <span data-ttu-id="2df93-113">Para fechar uma conexão usando o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, chame o método <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> do objeto RMO.</span><span class="sxs-lookup"><span data-stu-id="2df93-113">To close a connection by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method of the RMO object.</span></span> <span data-ttu-id="2df93-114">Depois que a conexão tiver sido fechada, os objetos RMO não poderão ser usados.</span><span class="sxs-lookup"><span data-stu-id="2df93-114">After the connection has been closed, RMO objects cannot be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2df93-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2df93-115">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-basic"></a><span data-ttu-id="2df93-116">Fechando e desconectando um objeto SMO no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2df93-116">Closing and Disconnecting an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="2df93-117">Este exemplo de código mostra como solicitar uma conexão não agrupada definindo a propriedade <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> da propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="2df93-117">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB4](SMO How to#SMO_VB4)]  -->  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-c"></a><span data-ttu-id="2df93-118">Fechando e desconectando um objeto SMO no Visual C#</span><span class="sxs-lookup"><span data-stu-id="2df93-118">Closing and Disconnecting an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="2df93-119">Este exemplo de código mostra como solicitar uma conexão não agrupada definindo a propriedade <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> da propriedade de objeto <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="2df93-119">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
//Disable automatic disconnection.   
srv.ConnectionContext.AutoDisconnectMode = AutoDisconnectMode.NoAutoDisconnect;   
//Connect to the local, default instance of SQL Server.   
srv.ConnectionContext.Connect();   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
//Disconnect explicitly.   
srv.ConnectionContext.Disconnect();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2df93-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2df93-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
