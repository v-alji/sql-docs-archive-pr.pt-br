---
title: Objetos da fonte de dados (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], data source objects
- SQL Server Native Client, data source objects
- SQLNCLI, data source objects
- SQL Server Native Client OLE DB provider, data source objects
- OLE DB data source objects [SQL Server Native Client]
- data source objects [OLE DB]
- CLSID
ms.assetid: c1d4ed20-ad3b-4e33-a26b-38d7517237b7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cf3f0b0308d655b50149c174547c19966f550ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678730"
---
# <a name="data-source-objects-ole-db"></a><span data-ttu-id="0cd26-102">Objetos de fonte de dados (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0cd26-102">Data Source Objects (OLE DB)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="0cd26-103">O Native Client usa a fonte de dados do termo para o conjunto de interfaces OLE DB usadas para estabelecer um link para um armazenamento de dados, como [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cd26-103">Native Client uses the term data source for the set of OLE DB interfaces used to establish a link to a data store, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0cd26-104">A criação de uma instância do objeto de fonte de dados do provedor é a primeira tarefa de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="0cd26-104">Creating an instance of the data source object of the provider is the first task of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client consumer.</span></span>  
  
 <span data-ttu-id="0cd26-105">Todo provedor do OLE DB declara um identificador de classe (CLSID) para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="0cd26-105">Every OLE DB provider declares a class identifier (CLSID) for itself.</span></span> <span data-ttu-id="0cd26-106">O CLSID para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo é o CLSID_SQLNCLI10 de GUID C/C++ (o símbolo SQLNCLI_CLSID será resolvido para o ProgID correto no arquivo sqlncli. h que você referencia).</span><span class="sxs-lookup"><span data-stu-id="0cd26-106">The CLSID for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is the C/C++ GUID CLSID_SQLNCLI10 (the symbol SQLNCLI_CLSID will resolve to the correct progid in the sqlncli.h file that you reference).</span></span> <span data-ttu-id="0cd26-107">Com o CLSID, o consumidor usa a função **CoCreateInstance** do OLE para produzir uma instância do objeto de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0cd26-107">With the CLSID, the consumer uses the OLE **CoCreateInstance** function to manufacture an instance of the data source object.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="0cd26-108">O Native Client é um servidor em processo.</span><span class="sxs-lookup"><span data-stu-id="0cd26-108">Native Client is an in-process server.</span></span> <span data-ttu-id="0cd26-109">Instâncias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos do provedor de OLE DB de clientes nativos são criadas usando a macro CLSCTX_INPROC_SERVER para indicar o contexto do executável.</span><span class="sxs-lookup"><span data-stu-id="0cd26-109">Instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider objects are created using the CLSCTX_INPROC_SERVER macro to indicate the executable context.</span></span>  
  
 <span data-ttu-id="0cd26-110">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objeto de fonte de dados do provedor de OLE DB de cliente nativo expõe as interfaces de inicialização OLE DB que permitem que o consumidor se conecte a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bancos de dados existentes.</span><span class="sxs-lookup"><span data-stu-id="0cd26-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object exposes the OLE DB initialization interfaces that allow the consumer to connect to existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="0cd26-111">Todas as conexões feitas por meio do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo define essas opções automaticamente:</span><span class="sxs-lookup"><span data-stu-id="0cd26-111">Every connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets these options automatically:</span></span>  
  
-   <span data-ttu-id="0cd26-112">SET ANSI_WARNINGS ON</span><span class="sxs-lookup"><span data-stu-id="0cd26-112">SET ANSI_WARNINGS ON</span></span>  
  
-   <span data-ttu-id="0cd26-113">SET ANSI_NULLS ON</span><span class="sxs-lookup"><span data-stu-id="0cd26-113">SET ANSI_NULLS ON</span></span>  
  
-   <span data-ttu-id="0cd26-114">SET ANSI_PADDING ON</span><span class="sxs-lookup"><span data-stu-id="0cd26-114">SET ANSI_PADDING ON</span></span>  
  
-   <span data-ttu-id="0cd26-115">SET ANSI_NULL_DFLT_ON ON</span><span class="sxs-lookup"><span data-stu-id="0cd26-115">SET ANSI_NULL_DFLT_ON ON</span></span>  
  
-   <span data-ttu-id="0cd26-116">SET QUOTED_IDENTIFIER ON</span><span class="sxs-lookup"><span data-stu-id="0cd26-116">SET QUOTED_IDENTIFIER ON</span></span>  
  
-   <span data-ttu-id="0cd26-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span><span class="sxs-lookup"><span data-stu-id="0cd26-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span></span>  
  
 <span data-ttu-id="0cd26-118">Este exemplo usa a macro identificador de classe para criar um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objeto de fonte de dados de provedor de OLE DB de cliente nativo e obter uma referência para sua interface **IDBInitialize** .</span><span class="sxs-lookup"><span data-stu-id="0cd26-118">This example uses the class identifier macro to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object and get a reference to its **IDBInitialize** interface.</span></span>  
  
```  
IDBInitialize*   pIDBInitialize;  
HRESULT          hr;  
  
hr = CoCreateInstance(CLSID_SQLNCLI10, NULL, CLSCTX_INPROC_SERVER,  
    IID_IDBInitialize, (void**) &pIDBInitialize);  
  
if (SUCCEEDED(hr))  
{  
    //  Perform necessary processing with the interface.  
    pIDBInitialize->Uninitialize();  
    pIDBInitialize->Release();  
}  
else  
{  
    // Display error from CoCreateInstance.  
}  
```  
  
 <span data-ttu-id="0cd26-119">Com a criação bem-sucedida de uma instância de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objeto de fonte de dados de provedor de OLE DB de cliente nativo, o aplicativo de consumidor pode continuar inicializando a fonte de dados e criando sessões.</span><span class="sxs-lookup"><span data-stu-id="0cd26-119">With successful creation of an instance of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object, the consumer application can continue by initializing the data source and creating sessions.</span></span> <span data-ttu-id="0cd26-120">As sessões de OLE DB apresentam as interfaces que permitem acesso e manipulação de dados.</span><span class="sxs-lookup"><span data-stu-id="0cd26-120">OLE DB sessions present the interfaces that allow data access and manipulation.</span></span>  
  
 <span data-ttu-id="0cd26-121">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo faz sua primeira conexão com uma instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como parte de uma inicialização de fonte de dados bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="0cd26-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider makes its first connection to a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as part of a successful data source initialization.</span></span> <span data-ttu-id="0cd26-122">A conexão é mantida, desde que uma referência seja mantida em qualquer interface de inicialização de fonte de dados, ou até que o método **IDBInitialize::Uninitialize** seja chamado.</span><span class="sxs-lookup"><span data-stu-id="0cd26-122">The connection is maintained as long as a reference is maintained on any data source initialization interface, or until the **IDBInitialize::Uninitialize** method is called.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0cd26-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0cd26-123">In This Section</span></span>  
  
-   [<span data-ttu-id="0cd26-124">Propriedades de fonte de dados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="0cd26-124">Data Source Properties &#40;OLE DB&#41;</span></span>](data-source-properties-ole-db.md)  
  
-   [<span data-ttu-id="0cd26-125">Propriedades de informações da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="0cd26-125">Data Source Information Properties</span></span>](data-source-information-properties.md)  
  
-   [<span data-ttu-id="0cd26-126">Propriedades de inicialização e autorização</span><span class="sxs-lookup"><span data-stu-id="0cd26-126">Initialization and Authorization Properties</span></span>](initialization-and-authorization-properties.md)  
  
-   [<span data-ttu-id="0cd26-127">Sessões</span><span class="sxs-lookup"><span data-stu-id="0cd26-127">Sessions</span></span>](sessions.md)  
  
-   [<span data-ttu-id="0cd26-128">Propriedades da sessão</span><span class="sxs-lookup"><span data-stu-id="0cd26-128">Session Properties</span></span>](session-properties-sql-server-native-client-ole-db-provider.md)  
  
-   [<span data-ttu-id="0cd26-129">Objetos persistidos da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="0cd26-129">Persisted Data Source Objects</span></span>](persisted-data-source-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="0cd26-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0cd26-130">See Also</span></span>  
 [<span data-ttu-id="0cd26-131">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="0cd26-131">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
