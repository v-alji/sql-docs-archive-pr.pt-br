---
title: Sessões | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- sessions [OLE DB]
- SQL Server Native Client OLE DB provider, sessions
ms.assetid: 3a980816-675c-4fba-acc9-429297d85bbd
author: rothja
ms.author: jroth
ms.openlocfilehash: 545f301a9a73691dd19bb11476d005219b2f982f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584127"
---
# <a name="sessions"></a><span data-ttu-id="4e5e9-102">Sessões</span><span class="sxs-lookup"><span data-stu-id="4e5e9-102">Sessions</span></span>
  <span data-ttu-id="4e5e9-103">Uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sessão de provedor de OLE DB de cliente nativo representa uma única conexão a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e5e9-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session represents a single connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4e5e9-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo requer que as sessões delimitem o espaço de transação para uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requires that sessions delimit transaction space for a data source.</span></span> <span data-ttu-id="4e5e9-105">Todos os objetos de comando criados de um objeto de sessão específico participam da transação local ou distribuída do objeto de sessão.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-105">All command objects created from a specific session object participate in the local or distributed transaction of the session object.</span></span>  
  
 <span data-ttu-id="4e5e9-106">O primeiro objeto de sessão criado na fonte de dados inicializada recebe a conexão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estabelecida na inicialização.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-106">The first session object created on the initialized data source receives the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection established at initialization.</span></span> <span data-ttu-id="4e5e9-107">Quando todas as referências nas interfaces do objeto de sessão são liberadas, a conexão com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] torna-se disponível a outro objeto de sessão criado na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-107">When all references on the interfaces of the session object are released, the connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] becomes available to another session object created on the data source.</span></span>  
  
 <span data-ttu-id="4e5e9-108">Um objeto de sessão adicional criado na fonte de dados estabelece sua própria conexão com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conforme especificado pela fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-108">An additional session object created on the data source establishes its own connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as specified by the data source.</span></span> <span data-ttu-id="4e5e9-109">A conexão com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é cancelada quando o aplicativo libera todas as referências aos objetos criados naquela sessão.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-109">The connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is dropped when the application releases all references to objects created that session.</span></span>  
  
 <span data-ttu-id="4e5e9-110">O exemplo a seguir demonstra como usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo para se conectar a um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] banco de dados:</span><span class="sxs-lookup"><span data-stu-id="4e5e9-110">The following example demonstrates how to use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database:</span></span>  
  
```  
int main()  
{  
    // Interfaces used in the example.  
    IDBInitialize*      pIDBInitialize      = NULL;  
    IDBCreateSession*   pIDBCreateSession   = NULL;  
    IDBCreateCommand*   pICreateCmd1        = NULL;  
    IDBCreateCommand*   pICreateCmd2        = NULL;  
    IDBCreateCommand*   pICreateCmd3        = NULL;  
  
    // Initialize COM.  
    if (FAILED(CoInitialize(NULL)))  
    {  
        // Display error from CoInitialize.  
        return (-1);  
    }  
  
    // Get the memory allocator for this task.  
    if (FAILED(CoGetMalloc(MEMCTX_TASK, &g_pIMalloc)))  
    {  
        // Display error from CoGetMalloc.  
        goto EXIT;  
    }  
  
    // Create an instance of the data source object.  
    if (FAILED(CoCreateInstance(CLSID_SQLNCLI10, NULL,  
        CLSCTX_INPROC_SERVER, IID_IDBInitialize, (void**)  
        &pIDBInitialize)))  
    {  
        // Display error from CoCreateInstance.  
        goto EXIT;  
    }  
  
    // The InitFromPersistedDS function   
    // performs IDBInitialize->Initialize() establishing  
    // the first application connection to the instance of SQL Server.  
    if (FAILED(InitFromPersistedDS(pIDBInitialize, L"MyDataSource",  
        NULL, NULL)))  
    {  
        goto EXIT;  
    }  
  
    // The IDBCreateSession interface is implemented on the data source  
    // object. Maintaining the reference received maintains the   
    // connection of the data source to the instance of SQL Server.  
    if (FAILED(pIDBInitialize->QueryInterface(IID_IDBCreateSession,  
        (void**) &pIDBCreateSession)))  
    {  
        // Display error from pIDBInitialize.  
        goto EXIT;  
    }  
  
    // Releasing this has no effect on the SQL Server connection  
    // of the data source object because of the reference maintained by  
    // pIDBCreateSession.  
    pIDBInitialize->Release();  
    pIDBInitialize = NULL;  
  
    // The session created next receives the SQL Server connection of  
    // the data source object. No new connection is established.  
    if (FAILED(pIDBCreateSession->CreateSession(NULL,  
        IID_IDBCreateCommand, (IUnknown**) &pICreateCmd1)))  
    {  
        // Display error from pIDBCreateSession.  
        goto EXIT;  
    }  
  
    // A new connection to the instance of SQL Server is established to support the  
    // next session object created. On successful completion, the  
    // application has two active connections on the SQL Server.  
    if (FAILED(pIDBCreateSession->CreateSession(NULL,  
        IID_IDBCreateCommand, (IUnknown**) &pICreateCmd2)))  
    {  
        // Display error from pIDBCreateSession.  
        goto EXIT;  
    }  
  
    // pICreateCmd1 has the data source connection. Because the  
    // reference on the IDBCreateSession interface of the data source  
    // has not been released, releasing the reference on the session  
    // object does not terminate a connection to the instance of SQL Server.  
    // However, the connection of the data source object is now   
    // available to another session object. After a successful call to   
    // Release, the application still has two active connections to the   
    // instance of SQL Server.  
    pICreateCmd1->Release();  
    pICreateCmd1 = NULL;  
  
    // The next session created gets the SQL Server connection  
    // of the data source object. The application has two active  
    // connections to the instance of SQL Server.  
    if (FAILED(pIDBCreateSession->CreateSession(NULL,  
        IID_IDBCreateCommand, (IUnknown**) &pICreateCmd3)))  
    {  
        // Display error from pIDBCreateSession.  
        goto EXIT;  
    }  
  
EXIT:  
    // Even on error, this does not terminate a SQL Server connection   
    // because pICreateCmd1 has the connection of the data source   
    // object.  
    if (pICreateCmd1 != NULL)  
        pICreateCmd1->Release();  
  
    // Releasing the reference on pICreateCmd2 terminates the SQL  
    // Server connection supporting the session object. The application  
    // now has only a single active connection on the instance of SQL Server.  
    if (pICreateCmd2 != NULL)  
        pICreateCmd2->Release();  
  
    // Even on error, this does not terminate a SQL Server connection   
    // because pICreateCmd3 has the connection of the   
    // data source object.  
    if (pICreateCmd3 != NULL)  
        pICreateCmd3->Release();  
  
    // On release of the last reference on a data source interface, the  
    // connection of the data source object to the instance of SQL Server is broken.  
    // The example application now has no SQL Server connections active.  
    if (pIDBCreateSession != NULL)  
        pIDBCreateSession->Release();  
  
    // Called only if an error occurred while attempting to get a   
    // reference on the IDBCreateSession interface of the data source.  
    // If so, the call to IDBInitialize::Uninitialize terminates the   
    // connection of the data source object to the instance of SQL Server.  
    if (pIDBInitialize != NULL)  
    {  
        if (FAILED(pIDBInitialize->Uninitialize()))  
        {  
            // Uninitialize is not required, but it fails if an  
            // interface has not been released. Use it for  
            // debugging.  
        }  
        pIDBInitialize->Release();  
    }  
  
    if (g_pIMalloc != NULL)  
        g_pIMalloc->Release();  
  
    CoUninitialize();  
  
    return (0);  
}  
```  
  
 <span data-ttu-id="4e5e9-111">Conectar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos de sessão de provedor de OLE DB de cliente nativo a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode gerar uma sobrecarga significativa para aplicativos que criam e liberam continuamente objetos de sessão.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-111">Connecting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session objects to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can generate significant overhead for applications that continually create and release session objects.</span></span> <span data-ttu-id="4e5e9-112">A sobrecarga pode ser minimizada Gerenciando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos de sessão de provedor de OLE DB de cliente nativo com eficiência.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-112">The overhead can be minimized by managing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session objects efficiently.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="4e5e9-113">Os aplicativos do provedor de OLE DB de clientes nativos podem manter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conexão de um objeto de sessão ativo mantendo uma referência em pelo menos uma interface do objeto.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-113">Native Client OLE DB provider applications can keep the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection of a session object active by maintaining a reference on at least one interface of the object.</span></span>  
  
 <span data-ttu-id="4e5e9-114">Por exemplo, manter um pool de referências a objeto de criação de comando mantém ativas as conexões a esses objetos de sessão no pool.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-114">For example, maintaining a pool of command creation object references keeps active connections for those session objects in the pool.</span></span> <span data-ttu-id="4e5e9-115">Como os objetos de sessão são necessários, o código de manutenção do pool passa um ponteiro de interface **IDBCreateCommand** válido para o método de aplicativo que solicita a sessão.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-115">As session objects are required, the pool maintenance code passes a valid **IDBCreateCommand** interface pointer to the application method requiring the session.</span></span> <span data-ttu-id="4e5e9-116">Quando o método do aplicativo não necessita mais da sessão, o método retorna o ponteiro de interface para o código de manutenção do pool em vez de liberar a referência do aplicativo ao objeto de criação de comando.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-116">When the application method no longer requires the session, the method returns the interface pointer back to the pool maintenance code rather than releasing the application's reference to the command creation object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e5e9-117">No exemplo anterior, a interface **IDBCreateCommand** é usada porque a interface **ICommand** implementa o método **GetDBSession**, o único método no escopo do comando ou do conjunto de linhas que permite que um objeto determine a sessão na qual ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-117">In the preceding example, the **IDBCreateCommand** interface is used because the **ICommand** interface implements the **GetDBSession** method, the only method in command or rowset scope that allows an object to determine the session on which it was created.</span></span> <span data-ttu-id="4e5e9-118">Portanto, um objeto de comando, e somente um objeto de comando, permite que um aplicativo recupere um ponteiro de objeto de fonte de dados a partir do qual outras sessões são criadas.</span><span class="sxs-lookup"><span data-stu-id="4e5e9-118">Therefore, a command object, and only a command object, allows an application to retrieve a data source object pointer from which additional sessions can be created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e5e9-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e5e9-119">See Also</span></span>  
 [<span data-ttu-id="4e5e9-120">Objetos de fonte de dados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="4e5e9-120">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
