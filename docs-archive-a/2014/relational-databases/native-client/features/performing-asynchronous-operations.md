---
title: Realizar operações assíncronas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- initialization [SQL Server Native Client]
- database connections [SQL Server Native Client]
- data access [SQL Server Native Client], asynchronous operations
- connections [SQL Server Native Client]
- asynchronous operations [SQL Server Native Client]
- rowsets [SQL Server], initializing
- SQLNCLI, asynchronous operations
- SQL Server Native Client, asynchronous operations
ms.assetid: 8fbd84b4-69cb-4708-9f0f-bbdf69029bcc
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f7e8f4481923cd7da537f921248865d4fff7280
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679907"
---
# <a name="performing-asynchronous-operations"></a><span data-ttu-id="89d6e-102">Executando operações assíncronas</span><span class="sxs-lookup"><span data-stu-id="89d6e-102">Performing Asynchronous Operations</span></span>
  <span data-ttu-id="89d6e-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] permite que os aplicativos executem operações de banco de dados assíncronas.</span><span class="sxs-lookup"><span data-stu-id="89d6e-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] allows applications to perform asynchronous database operations.</span></span> <span data-ttu-id="89d6e-104">O processamento assíncrono permite que os métodos retornem imediatamente sem serem bloqueados no thread de chamada.</span><span class="sxs-lookup"><span data-stu-id="89d6e-104">Asynchronous processing enables methods to return immediately without blocking on the calling thread.</span></span> <span data-ttu-id="89d6e-105">Isto permite muito do poder e flexibilidade de multithreading, sem exigir que o desenvolvedor crie threads explicitamente ou controle a sincronização.</span><span class="sxs-lookup"><span data-stu-id="89d6e-105">This allows much of the power and flexibility of multithreading, without requiring the developer to explicitly create threads or handle synchronization.</span></span> <span data-ttu-id="89d6e-106">Os aplicativos solicitam processamento assíncrono ao inicializar uma conexão de banco de dados ou ao inicializar o resultado da execução de um comando.</span><span class="sxs-lookup"><span data-stu-id="89d6e-106">Applications request asynchronous processing when initializing a database connection, or when initializing the result from the execution of a command.</span></span>  
  
## <a name="opening-and-closing-a-database-connection"></a><span data-ttu-id="89d6e-107">Abrindo e fechando uma conexão de banco de dados</span><span class="sxs-lookup"><span data-stu-id="89d6e-107">Opening and Closing a Database Connection</span></span>  
 <span data-ttu-id="89d6e-108">Ao usar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, os aplicativos criados para inicializar um objeto de fonte de dados de forma assíncrona podem definir o DBPROPVAL_ASYNCH_INITIALIZE bit na propriedade DBPROP_INIT_ASYNCH antes de chamar **IDBInitialize:: Initialize**.</span><span class="sxs-lookup"><span data-stu-id="89d6e-108">When using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, applications designed to initialize a data source object asynchronously can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_INIT_ASYNCH property prior to calling **IDBInitialize::Initialize**.</span></span> <span data-ttu-id="89d6e-109">Quando essa propriedade estiver definida, o provedor será retornado imediatamente da chamada a **Initialize** com S_OK, caso a operação seja concluída imediatamente, ou com DB_S_ASYNCHRONOUS, caso a inicialização continue de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="89d6e-109">When this property is set, the provider returns immediately from the call to **Initialize** with either S_OK, if the operation has completed immediately, or DB_S_ASYNCHRONOUS, if the initialization is continuing asynchronously.</span></span> <span data-ttu-id="89d6e-110">Os aplicativos podem consultar a interface **IDBAsynchStatus** ou [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)no objeto de fonte de dados e, em seguida, chamar **IDBAsynchStatus:: GetStatus** ou[ISSAsynchStatus:: WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) para obter o status da inicialização.</span><span class="sxs-lookup"><span data-stu-id="89d6e-110">Applications can query for the **IDBAsynchStatus** or [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)interface on the data source object, and then call **IDBAsynchStatus::GetStatus** or[ISSAsynchStatus::WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) to get the status of the initialization.</span></span>  
  
 <span data-ttu-id="89d6e-111">Além disso, a propriedade SSPROP_ISSAsynchStatus foi adicionada ao conjunto de propriedades DBPROPSET_SQLSERVERROWSET.</span><span class="sxs-lookup"><span data-stu-id="89d6e-111">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="89d6e-112">Os provedores que dão suporte à interface **ISSAsynchStatus** precisam implementar essa propriedade com um valor de VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="89d6e-112">Providers that support the **ISSAsynchStatus** interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="89d6e-113">**IDBAsynchStatus::Abort** ou [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) pode ser chamado para cancelar a chamada assíncrona a **Initialize**.</span><span class="sxs-lookup"><span data-stu-id="89d6e-113">**IDBAsynchStatus::Abort** or [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) can be called to cancel the asynchronous **Initialize** call.</span></span> <span data-ttu-id="89d6e-114">O consumidor deve solicitar explicitamente a Inicialização Assíncrona da Fonte de Dados.</span><span class="sxs-lookup"><span data-stu-id="89d6e-114">The consumer must explicitly request Asynchronous Data Source Initialization.</span></span> <span data-ttu-id="89d6e-115">Caso contrário, **IDBInitialize::Initialize** não será retornado enquanto o objeto de fonte de dados não for completamente inicializado.</span><span class="sxs-lookup"><span data-stu-id="89d6e-115">Otherwise, **IDBInitialize::Initialize** does not return until the data source object is completely initialized.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89d6e-116">Os objetos de fonte de dados usados para o pool de conexões não podem chamar a interface **ISSAsynchStatus** no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="89d6e-116">Data source objects used for connection pooling cannot call the **ISSAsynchStatus** interface in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="89d6e-117">A interface **ISSAsynchStatus** não é exposta para objetos da fonte de dados em pool.</span><span class="sxs-lookup"><span data-stu-id="89d6e-117">The **ISSAsynchStatus** interface is not exposed for pooled data source objects.</span></span>  
>   
>  <span data-ttu-id="89d6e-118">Se um aplicativo forçar explicitamente o uso do mecanismo de cursor, **IOpenRowset::OpenRowset** e **IMultipleResults::GetResult** não darão suporte ao processamento assíncrono.</span><span class="sxs-lookup"><span data-stu-id="89d6e-118">If an application explicitly forces use of the cursor engine, **IOpenRowset::OpenRowset** and **IMultipleResults::GetResult** will not support asynchronous processing.</span></span>  
>   
>  <span data-ttu-id="89d6e-119">Além disso, a DLL de proxy de comunicação remota/stub (no MDAC 2,8) não pode chamar a interface **ISSAsynchStatus** no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="89d6e-119">In addition, the remoting proxy/stub dll (in MDAC 2.8) cannot call the **ISSAsynchStatus** interface in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="89d6e-120">A interface **ISSAsynchStatus** não é exposta por comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="89d6e-120">The **ISSAsynchStatus** interface is not exposed through remoting.</span></span>  
>   
>  <span data-ttu-id="89d6e-121">Os Componentes de Serviço não dão suporte a **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="89d6e-121">Service Components do not support **ISSAsynchStatus**.</span></span>  
  
## <a name="execution-and-rowset-initialization"></a><span data-ttu-id="89d6e-122">Execução e inicialização de conjunto de linhas</span><span class="sxs-lookup"><span data-stu-id="89d6e-122">Execution and Rowset Initialization</span></span>  
 <span data-ttu-id="89d6e-123">Os aplicativos projetados para abrir assincronamente o resultado da execução de um comando podem definir o bit DBPROPVAL_ASYNCH_INITIALIZE na propriedade DBPROP_ROWSET_ASYNCH.</span><span class="sxs-lookup"><span data-stu-id="89d6e-123">Applications designed to asynchronously open the result from the execution of a command can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_ROWSET_ASYNCH property.</span></span> <span data-ttu-id="89d6e-124">Ao definir esse bit antes de chamar **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** ou **IMultipleResults::GetResult**, o argumento *riid* precisa ser definido como IID_IDBAsynchStatus, IID_ISSAsynchStatus ou IID_IUnknown.</span><span class="sxs-lookup"><span data-stu-id="89d6e-124">When setting this bit prior to calling **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** or **IMultipleResults::GetResult**, the *riid* argument must be set to IID_IDBAsynchStatus, IID_ISSAsynchStatus, or IID_IUnknown.</span></span>  
  
 <span data-ttu-id="89d6e-125">O método será retornado imediatamente com S_OK se a inicialização do conjunto de linhas for concluída imediatamente, ou com DB_S_ASYNCHRONOUS se o conjunto de linhas continuar sendo inicializado de forma assíncrona, com *ppRowset* definido como a interface solicitada no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="89d6e-125">The method returns immediately with S_OK if the rowset initialization completes immediately, or with DB_S_ASYNCHRONOUS if the rowset continues initializing asynchronously, with *ppRowset* set to the requested interface on the rowset.</span></span> <span data-ttu-id="89d6e-126">Para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, essa interface só pode ser **IDBAsynchStatus** ou **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="89d6e-126">For the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, this interface can only be **IDBAsynchStatus** or **ISSAsynchStatus**.</span></span> <span data-ttu-id="89d6e-127">Até o conjunto de linhas ser completamente inicializado, essa interface se comportará como se estivesse em um estado suspenso, e a chamada a **QueryInterface** para interfaces diferentes de **IID_IDBAsynchStatus** ou **IID_ISSAsynchStatus** poderá retornar E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="89d6e-127">Until the rowset is fully initialized, this interface behaves as if it were in a suspended state, and calling **QueryInterface** for interfaces other than **IID_IDBAsynchStatus** or **IID_ISSAsynchStatus** may return E_NOINTERFACE.</span></span> <span data-ttu-id="89d6e-128">A menos que o consumidor solicite processamento assíncrono explicitamente, o conjunto de linhas é inicializado sincronamente.</span><span class="sxs-lookup"><span data-stu-id="89d6e-128">Unless the consumer explicitly requests asynchronous processing, the rowset is initialized synchronously.</span></span> <span data-ttu-id="89d6e-129">Todas as interfaces solicitadas estão disponíveis quando **IDBAsynchStaus::GetStatus** ou **ISSAsynchStatus::WaitForAsynchCompletion** é retornado com a indicação de que a operação assíncrona foi concluída.</span><span class="sxs-lookup"><span data-stu-id="89d6e-129">All requested interfaces are available when **IDBAsynchStaus::GetStatus** or **ISSAsynchStatus::WaitForAsynchCompletion** returns with the indication that asynchronous operation is complete.</span></span> <span data-ttu-id="89d6e-130">Isto não significa necessariamente que todo o conjunto de linhas esteja preenchido, mas que está completo e totalmente funcional.</span><span class="sxs-lookup"><span data-stu-id="89d6e-130">This does not necessarily mean that the rowset is fully populated, but it is complete and fully functional.</span></span>  
  
 <span data-ttu-id="89d6e-131">Se o comando executado não retornar um conjunto de linhas, ele ainda será retornado imediatamente com um objeto que dá suporte a **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="89d6e-131">If the executed command does not return a rowset, it still returns immediately with an object that supports **IDBAsynchStatus**.</span></span>  
  
 <span data-ttu-id="89d6e-132">Se você precisar obter vários resultados da execução de comando assíncrona, deverá:</span><span class="sxs-lookup"><span data-stu-id="89d6e-132">If you need to get multiple results from asynchronous command execution, you should:</span></span>  
  
-   <span data-ttu-id="89d6e-133">Definir o bit DBPROPVAL_ASYNCH_INITIALIZE da propriedade DBPROP_ROWSET_ASYNCH antes de executar o comando.</span><span class="sxs-lookup"><span data-stu-id="89d6e-133">Set the DBPROPVAL_ASYNCH_INITIALIZE bit of the DBPROP_ROWSET_ASYNCH property, before executing the command.</span></span>  
  
-   <span data-ttu-id="89d6e-134">Chamar **ICommand::Execute** e solicitar **IMultipleResults**.</span><span class="sxs-lookup"><span data-stu-id="89d6e-134">Call **ICommand::Execute**, and request **IMultipleResults**.</span></span>  
  
 <span data-ttu-id="89d6e-135">Em seguida, as interfaces **IDBAsynchStatus** e **ISSAsynchStatus** podem ser obtidas consultando a interface de vários resultados usando **QueryInterface**.</span><span class="sxs-lookup"><span data-stu-id="89d6e-135">The **IDBAsynchStatus** and **ISSAsynchStatus** interfaces can then be obtained by querying the multiple results interface using **QueryInterface**.</span></span>  
  
 <span data-ttu-id="89d6e-136">Quando o comando tiver concluído a execução, **IMultipleResults** poderá ser usado como normal, com uma exceção do caso síncrono: DB_S_ASYNCHRONOUS pode ser retornado; nesse caso, a interface **IDBAsynchStatus** ou **ISSAsynchStatus** pode ser usada para determinar quando a operação é concluída.</span><span class="sxs-lookup"><span data-stu-id="89d6e-136">When the command has finished executing, **IMultipleResults** can be used as normal, with one exception from the synchronous case: DB_S_ASYNCHRONOUS may be returned, in which case **IDBAsynchStatus** or **ISSAsynchStatus** can be used to determine when the operation is complete.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="89d6e-137">Exemplos</span><span class="sxs-lookup"><span data-stu-id="89d6e-137">Examples</span></span>  
 <span data-ttu-id="89d6e-138">No exemplo a seguir, o aplicativo chama um método sem-bloqueio, executa algum outro processamento e retorna para processar os resultados.</span><span class="sxs-lookup"><span data-stu-id="89d6e-138">In the following example, the application calls a non-blocking method, does some other processing, and then returns to process the results.</span></span> <span data-ttu-id="89d6e-139">**ISSAsynchStatus::WaitForAsynchCompletion** aguarda no objeto de evento interno até que a operação de execução assíncrona seja concluída ou que o tempo especificado por *dwMilisecTimeOut* tenha decorrido.</span><span class="sxs-lookup"><span data-stu-id="89d6e-139">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the amount of time specified by *dwMilisecTimeOut* is passed.</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
  
DBPROPSET CmdPropset[1];  
DBPROP CmdProperties[1];  
  
CmdPropset[0].rgProperties = CmdProperties;  
CmdPropset[0].cProperties = 1;  
CmdPropset[0].guidPropertySet = DBPROPSET_ROWSET;  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
CmdProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
  
hr = pICommandProps->SetProperties(1, CmdPropset);  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if ( hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="89d6e-140">**ISSAsynchStatus::WaitForAsynchCompletion** aguarda no objeto de evento interno até que a operação de execução assíncrona seja concluída ou o valor de *dwMilisecTimeOut* seja passado.</span><span class="sxs-lookup"><span data-stu-id="89d6e-140">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the *dwMilisecTimeOut* value is passed.</span></span>  
  
 <span data-ttu-id="89d6e-141">O exemplo a seguir mostra processamento assíncrono com vários conjuntos de resultados:</span><span class="sxs-lookup"><span data-stu-id="89d6e-141">The following example shows asynchronous processing with multiple result sets:</span></span>  
  
```  
DBPROP CmdProperties[1];  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_IMultipleResults,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pIMultipleResults);  
  
// Use GetResults for ISSAsynchStatus.  
hr = pIMultipleResults->GetResult(IID_ISSAsynchStatus, (void **) &pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if (hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="89d6e-142">Para impedir o bloqueio, o cliente pode verificar o status de uma operação assíncrona em execução, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="89d6e-142">To prevent blocking, the client can check the status of a running asynchronous operation, as in the following example:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);   
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   do{  
      // Do some work...  
      hr = pISSAsynchStatus->GetStatus(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN, NULL, NULL, &ulAsynchPhase, NULL);  
   }while (DBASYNCHPHASE_COMPLETE != ulAsynchPhase)  
   if SUCCEEDED(hr)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
   }  
   pIDBAsynchStatus->Release();  
}  
```  
  
 <span data-ttu-id="89d6e-143">O exemplo a seguir demonstra como você pode cancelar a operação assíncrona atualmente em execução:</span><span class="sxs-lookup"><span data-stu-id="89d6e-143">The following example demonstrates how you can cancel the currently running asynchronous operation:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work...  
   hr = pISSAsynchStatus->Abort(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="89d6e-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89d6e-144">See Also</span></span>  
 <span data-ttu-id="89d6e-145">[Recursos do SQL Server Native Client](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="89d6e-145">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 <span data-ttu-id="89d6e-146">[Propriedades e comportamentos do conjunto de linhas](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="89d6e-146">[Rowset Properties and Behaviors](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 [<span data-ttu-id="89d6e-147">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="89d6e-147">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)  
  
  
