---
title: Dando suporte a transações distribuídas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- distributed transactions [OLE DB]
- MS DTC
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
- ITransactionJoin interface
- MS DTC, about distributed transaction support
ms.assetid: d250b43b-9260-4ea4-90cc-57d9a2f67ea7
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a30a44dc007852922aa71685728b26e5bb872c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684169"
---
# <a name="supporting-distributed-transactions"></a><span data-ttu-id="fb359-102">Dando suporte a transações distribuídas</span><span class="sxs-lookup"><span data-stu-id="fb359-102">Supporting Distributed Transactions</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="fb359-103">Os consumidores do provedor de OLE DB de cliente nativo podem usar o método **ITransactionJoin:: JoinTransaction** para participar de uma transação distribuída coordenada pelo Microsoft coordenador de transações distribuídas (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="fb359-103">Native Client OLE DB provider consumers can use the **ITransactionJoin::JoinTransaction** method to participate in a distributed transaction coordinated by Microsoft Distributed Transaction Coordinator (MS DTC).</span></span>  
  
 <span data-ttu-id="fb359-104">O MS DTC expõe objetos COM que permitem que os clientes iniciem e participem de transações coordenadas através de várias conexões com vários repositórios de dados.</span><span class="sxs-lookup"><span data-stu-id="fb359-104">MS DTC exposes COM objects that allow clients to initiate and participate in coordinated transactions across multiple connections to a variety of data stores.</span></span> <span data-ttu-id="fb359-105">Para iniciar uma transação, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor de OLE DB de cliente nativo usa a interface **ITRANSACTIONDISPENSER** do MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb359-105">To initiate a transaction, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses the MS DTC **ITransactionDispenser** interface.</span></span> <span data-ttu-id="fb359-106">O membro **BeginTransaction** de **ITransactionDispenser** retorna uma referência a um objeto de transação distribuída.</span><span class="sxs-lookup"><span data-stu-id="fb359-106">The **BeginTransaction** member of **ITransactionDispenser** returns a reference on a distributed transaction object.</span></span> <span data-ttu-id="fb359-107">Essa referência é passada para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo usando **JoinTransaction**.</span><span class="sxs-lookup"><span data-stu-id="fb359-107">This reference is passed to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider using **JoinTransaction**.</span></span>  
  
 <span data-ttu-id="fb359-108">O MS DTC dá suporte à confirmação e à anulação assíncronas de transações distribuídas.</span><span class="sxs-lookup"><span data-stu-id="fb359-108">MS DTC supports asynchronous commit and abort on distributed transactions.</span></span> <span data-ttu-id="fb359-109">Para obter a notificação do status da transação assíncrona, o consumidor implementa a interface **ITransactionOutcomeEvents** e a conecta a um objeto de transação do MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb359-109">For notification on asynchronous transaction status, the consumer implements the **ITransactionOutcomeEvents** interface and connects the interface to an MS DTC transaction object.</span></span>  
  
 <span data-ttu-id="fb359-110">Para transações distribuídas, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo implementa os parâmetros **ITransactionJoin:: JoinTransaction** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="fb359-110">For distributed transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransactionJoin::JoinTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="fb359-111">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="fb359-111">Parameter</span></span>|<span data-ttu-id="fb359-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="fb359-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb359-113">*punkTransactionCoord*</span><span class="sxs-lookup"><span data-stu-id="fb359-113">*punkTransactionCoord*</span></span>|<span data-ttu-id="fb359-114">Um ponteiro para um objeto de transação do MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb359-114">A pointer to an MS DTC transaction object.</span></span>|  
|<span data-ttu-id="fb359-115">*IsoLevel*</span><span class="sxs-lookup"><span data-stu-id="fb359-115">*IsoLevel*</span></span>|<span data-ttu-id="fb359-116">Ignorado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="fb359-116">Ignored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="fb359-117">O nível de isolamento para transações coordenadas pelo MS DTC é determinado quando o consumidor faz a aquisição de um objeto de transação do MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb359-117">The isolation level for MS DTC-coordinated transactions is determined when the consumer acquires a transaction object from MS DTC.</span></span>|  
|<span data-ttu-id="fb359-118">*IsoFlags*</span><span class="sxs-lookup"><span data-stu-id="fb359-118">*IsoFlags*</span></span>|<span data-ttu-id="fb359-119">Deve ser 0.</span><span class="sxs-lookup"><span data-stu-id="fb359-119">Must be 0.</span></span> <span data-ttu-id="fb359-120">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna XACT_E_NOISORETAIN se qualquer outro valor for especificado pelo consumidor.</span><span class="sxs-lookup"><span data-stu-id="fb359-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOISORETAIN if any other value is specified by the consumer.</span></span>|  
|<span data-ttu-id="fb359-121">*POtherOptions*</span><span class="sxs-lookup"><span data-stu-id="fb359-121">*POtherOptions*</span></span>|<span data-ttu-id="fb359-122">Se não for NULL, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo solicitará o objeto de opções da interface.</span><span class="sxs-lookup"><span data-stu-id="fb359-122">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="fb359-123">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna XACT_E_NOTIMEOUT se o membro *ulTimeout* do objeto de opções não for zero.</span><span class="sxs-lookup"><span data-stu-id="fb359-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="fb359-124">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo ignora o valor do membro *szDescription* .</span><span class="sxs-lookup"><span data-stu-id="fb359-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
  
 <span data-ttu-id="fb359-125">Este exemplo coordena a transação usando o MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb359-125">This example coordinates transaction by using MS DTC.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*       pIDBCreateSession   = NULL;  
ITransactionJoin*       pITransactionJoin   = NULL;  
IDBCreateCommand*       pIDBCreateCommand   = NULL;  
IRowset*                pIRowset            = NULL;  
  
// Transaction dispenser and transaction from MS DTC.  
ITransactionDispenser*  pITransactionDispenser = NULL;  
ITransaction*           pITransaction       = NULL;  
  
    HRESULT             hr;  
  
// Get the command creation interface for the session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
// Get a transaction dispenser object from MS DTC and  
// start a transaction.  
if (FAILED(hr = DtcGetTransactionManager(NULL, NULL,  
    IID_ITransactionDispenser, 0, 0, NULL,  
    (void**) &pITransactionDispenser)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
if (FAILED(hr = pITransactionDispenser->BeginTransaction(  
    NULL, ISOLATIONLEVEL_READCOMMITTED, ISOFLAG_RETAIN_DONTCARE,  
    NULL, &pITransaction)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
  
// Join the transaction.  
if (FAILED(pIDBCreateCommand->QueryInterface(IID_ITransactionJoin,  
    (void**) &pITransactionJoin)))  
    {  
    // Process failure to get an interface, release any references, and  
    // then return.  
    }  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) pITransaction, 0, 0, NULL)))  
    {  
    // Process join failure, release any references, and then return.  
    }  
  
// Get data into a rowset, then update the data. Functions are not  
// illustrated in this example.  
if (FAILED(hr = ExecuteCommand(pIDBCreateCommand, &pIRowset)))  
    {  
    // Release any references and return.  
    }  
  
// If rowset data update fails, then terminate the transaction, else  
// commit. The example doesn't retain the rowset.  
if (FAILED(hr = UpdateDataInRowset(pIRowset, bDelayedUpdate)))  
    {  
    // Get error from update, then abort.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, 0, 0)))  
        {  
        // Get error from failed commit.  
        //  
        // If a distributed commit fails, application logic could  
        // analyze failure and retry. In this example, terminate. The   
        // consumer must resolve this somehow.  
        pITransaction->Abort(NULL, FALSE, FALSE);  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Un-enlist from the distributed transaction by setting   
// the transaction object pointer to NULL.  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) NULL, 0, 0, NULL)))  
    {  
    // Process failure, and then return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb359-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb359-126">See Also</span></span>  
 [<span data-ttu-id="fb359-127">Transações</span><span class="sxs-lookup"><span data-stu-id="fb359-127">Transactions</span></span>](transactions.md)  
  
  
