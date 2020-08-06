---
title: Manipulando eventos SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- events [SMO]
- SQL Server Management Objects, events
- SMO [SQL Server], events
- events [SMO], about events
ms.assetid: b4f120dd-ba78-46ff-99c5-e47effac8544
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7ea438142ac283c5ad19670fa827b5e248e80f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582938"
---
# <a name="handling-smo-events"></a><span data-ttu-id="f0e98-102">Manipulando eventos SMO</span><span class="sxs-lookup"><span data-stu-id="f0e98-102">Handling SMO Events</span></span>
  <span data-ttu-id="f0e98-103">Há tipos de eventos de servidor que podem ser assinados usando um manipulador de eventos e o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="f0e98-103">There are server event types that can be subscribed to by using an event handler and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
 <span data-ttu-id="f0e98-104">Muitas das classes de instância no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) podem disparar eventos quando ocorrem determinadas ações no servidor.</span><span class="sxs-lookup"><span data-stu-id="f0e98-104">Many of the instance classes in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) can trigger events when certain actions on the server occur.</span></span>  
  
 <span data-ttu-id="f0e98-105">Esses eventos podem ser tratados programaticamente através da configuração de um manipulador de eventos e da inscrição nos eventos associados.</span><span class="sxs-lookup"><span data-stu-id="f0e98-105">These events can be handled programmatically by setting up an event handler and subscribing to the associated events.</span></span> <span data-ttu-id="f0e98-106">Esse tipo de manipulação de eventos é transitório pois todas as assinaturas são removidas quando o programa cliente SMO é desativado.</span><span class="sxs-lookup"><span data-stu-id="f0e98-106">This type of event handling is transient because all the subscriptions are removed when the SMO client program exits.</span></span>  
  
## <a name="connectioncontext-event-handling"></a><span data-ttu-id="f0e98-107">Manipulação de eventos do ConnectionContext</span><span class="sxs-lookup"><span data-stu-id="f0e98-107">ConnectionContext Event Handling</span></span>  
 <span data-ttu-id="f0e98-108">O objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> dá suporte a vários tipos de eventos.</span><span class="sxs-lookup"><span data-stu-id="f0e98-108">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object supports several event types.</span></span> <span data-ttu-id="f0e98-109">A propriedade do evento deve ser definida como uma instância de um manipulador de eventos apropriado, e o objeto do manipulador de eventos deve ser definido como uma função protegida que manipula o evento.</span><span class="sxs-lookup"><span data-stu-id="f0e98-109">The event property must be set to an instance of an appropriate event handler, and the event handler object must be defined as a protected function that handles the event.</span></span>  
  
## <a name="event-subscription"></a><span data-ttu-id="f0e98-110">Assinatura do evento</span><span class="sxs-lookup"><span data-stu-id="f0e98-110">Event Subscription</span></span>  
 <span data-ttu-id="f0e98-111">Para manipular eventos, escreva uma classe de manipulador de evento, crie uma instância dela, atribua o manipulador de eventos ao objeto pai e faça a assinatura do evento.</span><span class="sxs-lookup"><span data-stu-id="f0e98-111">You handle events by writing an event handler class, creating an instance of it, assigning the event handler to the parent object, and then subscribing to the event.</span></span>  
  
 <span data-ttu-id="f0e98-112">Uma classe de manipulador de eventos deve ser escrita para manipular eventos.</span><span class="sxs-lookup"><span data-stu-id="f0e98-112">An event handler class must be written to handle events.</span></span> <span data-ttu-id="f0e98-113">A classe do manipulador de eventos pode conter mais de uma função de manipulador de eventos e deve ser instalada para os eventos a serem manipulados.</span><span class="sxs-lookup"><span data-stu-id="f0e98-113">The event handler class can contain more than one event handler function, and must be installed for the events to be handled.</span></span> <span data-ttu-id="f0e98-114">As funções do manipulador de eventos recebem informações sobre o evento do parâmetro *ServerEventNotificatificationArgs* que pode ser usado para relatar informações sobre o evento.</span><span class="sxs-lookup"><span data-stu-id="f0e98-114">The event handler functions receive information about the event from the *ServerEventNotificatificationArgs* parameter that can be used to report information about the event.</span></span>  
  
 <span data-ttu-id="f0e98-115">Os tipos de eventos de servidor e banco de dados que podem ser manipulados são listados na <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> classe e na <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet> classe.</span><span class="sxs-lookup"><span data-stu-id="f0e98-115">The types of database and server events that can be handled are listed in the <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> class and the <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet>class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0e98-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f0e98-116">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-basic"></a><span data-ttu-id="f0e98-117">Registrando manipuladores de eventos e assinando a manipulação de eventos no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0e98-117">Registering Event Handlers and Subscribing to Event Handling in Visual Basic</span></span>  
 <span data-ttu-id="f0e98-118">Este exemplo de código mostra como configurar o manipulador de eventos e como assinar os eventos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f0e98-118">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEvents1](SMO How to#SMO_VBEvents1)]  -->  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-c"></a><span data-ttu-id="f0e98-119">Registrando manipuladores de eventos e assinando a manipulação de eventos no Visual C#</span><span class="sxs-lookup"><span data-stu-id="f0e98-119">Registering Event Handlers and Subscribing to Event Handling in Visual C#</span></span>  
 <span data-ttu-id="f0e98-120">Este exemplo de código mostra como configurar o manipulador de eventos e como assinar os eventos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f0e98-120">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
```  
//Create an event handler subroutine that runs when a table is created.   
private void MyCreateEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been added to the AdventureWorks2012 database.");   
}   
//Create an event handler subroutine that runs when a table is deleted.   
private void MyDropEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been dropped from the AdventureWorks2012 database.");   
}   
public void Main()   
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Create a database event set that contains the CreateTable event only.   
DatabaseEventSet databaseCreateEventSet = new DatabaseEventSet();   
databaseCreateEventSet.CreateTable = true;   
//Create a server event handler and set it to the first event handler subroutine.   
ServerEventHandler serverCreateEventHandler;   
serverCreateEventHandler = new ServerEventHandler(MyCreateEventHandler);   
//Subscribe to the first server event handler when a CreateTable event occurs.   
db.Events.SubscribeToEvents(databaseCreateEventSet, serverCreateEventHandler);   
    //Create a database event set that contains the DropTable event only.   
DatabaseEventSet databaseDropEventSet = new DatabaseEventSet();   
databaseDropEventSet.DropTable = true;   
//Create a server event handler and set it to the second event handler subroutine.   
ServerEventHandler serverDropEventHandler;   
serverDropEventHandler = new ServerEventHandler(MyDropEventHandler);   
//Subscribe to the second server event handler when a DropTable event occurs.   
db.Events.SubscribeToEvents(databaseDropEventSet, serverDropEventHandler);   
//Start event handling.   
db.Events.StartEvents();   
//Create a table on the database.   
Table tb;   
tb = new Table(db, "Test_Table");   
Column mycol1;   
mycol1 = new Column(tb, "Name", DataType.NChar(50));   
mycol1.Collation = "Latin1_General_CI_AS";   
mycol1.Nullable = true;   
tb.Columns.Add(mycol1);   
tb.Create();   
//Remove the table.   
tb.Drop();   
//Wait until the events have occured.   
int x;   
int y;   
for (x = 1; x <= 1000000000; x++) {   
    y = x * 2;   
}   
//Stop event handling.   
db.Events.StopEvents();   
}  
```  
  
  
