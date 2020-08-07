---
title: Dando suporte a transações locais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- autocommit mode
- transactions [OLE DB]
- ITransactionLocal interface
- SQL Server Native Client OLE DB provider, transactions
- local transactions [OLE DB]
ms.assetid: 78f2e5fc-b6fb-4eda-9f71-991a4d6c4902
author: rothja
ms.author: jroth
ms.openlocfilehash: a9bc11a038e56517aa42619117c371c1319b9ffe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581771"
---
# <a name="supporting-local-transactions"></a><span data-ttu-id="2e358-102">Dando suporte a transações locais</span><span class="sxs-lookup"><span data-stu-id="2e358-102">Supporting Local Transactions</span></span>
  <span data-ttu-id="2e358-103">Uma sessão delimita o escopo da transação para uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transação local do provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="2e358-103">A session delimits transaction scope for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider local transaction.</span></span> <span data-ttu-id="2e358-104">Quando, na direção de um consumidor, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo envia uma solicitação para uma instância conectada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a solicitação constitui uma unidade de trabalho para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="2e358-104">When, at the direction of a consumer, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider submits a request to a connected instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the request constitutes a unit of work for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="2e358-105">As transações locais sempre encapsulam uma ou mais unidades de trabalho em uma única [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sessão de provedor de OLE DB de cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="2e358-105">Local transactions always wrap one or more units of work on a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session.</span></span>  
  
 <span data-ttu-id="2e358-106">Usando o modo de confirmação automática do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo padrão, uma única unidade de trabalho é tratada como o escopo de uma transação local.</span><span class="sxs-lookup"><span data-stu-id="2e358-106">Using the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode, a single unit of work is treated as the scope of a local transaction.</span></span> <span data-ttu-id="2e358-107">Apenas uma unidade participa da transação local.</span><span class="sxs-lookup"><span data-stu-id="2e358-107">Only one unit participates in the local transaction.</span></span> <span data-ttu-id="2e358-108">Quando uma sessão é criada, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo inicia uma transação para a sessão.</span><span class="sxs-lookup"><span data-stu-id="2e358-108">When a session is created, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a transaction for the session.</span></span> <span data-ttu-id="2e358-109">Na conclusão bem-sucedida de uma unidade de trabalho, o trabalho é confirmado.</span><span class="sxs-lookup"><span data-stu-id="2e358-109">Upon successful completion of a work unit, the work is committed.</span></span> <span data-ttu-id="2e358-110">Em caso de falha, qualquer trabalho começado é revertido e o erro é relatado ao consumidor.</span><span class="sxs-lookup"><span data-stu-id="2e358-110">On failure, any work begun is rolled back and the error is reported to the consumer.</span></span> <span data-ttu-id="2e358-111">Em ambos os casos, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo inicia uma nova transação local para a sessão para que todo o trabalho seja realizado em uma transação.</span><span class="sxs-lookup"><span data-stu-id="2e358-111">In either case, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a new local transaction for the session so that all work is conducted within a transaction.</span></span>  
  
 <span data-ttu-id="2e358-112">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor de OLE DB de cliente nativo pode direcionar um controle mais preciso sobre o escopo da transação local usando a interface **ITransactionLocal** .</span><span class="sxs-lookup"><span data-stu-id="2e358-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer can direct more precise control over local transaction scope by using the **ITransactionLocal** interface.</span></span> <span data-ttu-id="2e358-113">Quando uma sessão do consumidor inicia uma transação, todas as unidades de trabalho da sessão entre o ponto inicial da transação e as eventuais chamadas do método **Commit** ou **Abort** são tratadas como uma unidade atômica.</span><span class="sxs-lookup"><span data-stu-id="2e358-113">When a consumer session initiates a transaction, all session work units between the transaction start point and the eventual **Commit** or **Abort** method calls are treated as an atomic unit.</span></span> <span data-ttu-id="2e358-114">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo inicia implicitamente uma transação quando instruído a fazer isso pelo consumidor.</span><span class="sxs-lookup"><span data-stu-id="2e358-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implicitly begins a transaction when directed to do so by the consumer.</span></span> <span data-ttu-id="2e358-115">Se o consumidor não solicitar retenção, a sessão reverterá para o comportamento pai em nível de transação, geralmente o modo de confirmação automática.</span><span class="sxs-lookup"><span data-stu-id="2e358-115">If the consumer does not request retention, the session reverts to parent transaction-level behavior, most commonly autocommit mode.</span></span>  
  
 <span data-ttu-id="2e358-116">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo oferece suporte aos parâmetros **ITransactionLocal:: StartTransaction** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="2e358-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ITransactionLocal::StartTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="2e358-117">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="2e358-117">Parameter</span></span>|<span data-ttu-id="2e358-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e358-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e358-119">*isoLevel*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-119">*isoLevel*[in]</span></span>|<span data-ttu-id="2e358-120">O nível de isolamento a ser usado com esta transação.</span><span class="sxs-lookup"><span data-stu-id="2e358-120">The isolation level to be used with this transaction.</span></span> <span data-ttu-id="2e358-121">Em transações locais, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="2e358-121">In local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the following:</span></span><br /><br /> <span data-ttu-id="2e358-122">-ISOLATIONLEVEL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="2e358-122">-   ISOLATIONLEVEL_UNSPECIFIED</span></span><br /><span data-ttu-id="2e358-123">-ISOLATIONLEVEL_CHAOS</span><span class="sxs-lookup"><span data-stu-id="2e358-123">-   ISOLATIONLEVEL_CHAOS</span></span><br /><span data-ttu-id="2e358-124">-ISOLATIONLEVEL_READUNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="2e358-124">-   ISOLATIONLEVEL_READUNCOMMITTED</span></span><br /><span data-ttu-id="2e358-125">-ISOLATIONLEVEL_READCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="2e358-125">-   ISOLATIONLEVEL_READCOMMITTED</span></span><br /><span data-ttu-id="2e358-126">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="2e358-126">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="2e358-127">-ISOLATIONLEVEL_CURSORSTABILITY</span><span class="sxs-lookup"><span data-stu-id="2e358-127">-   ISOLATIONLEVEL_CURSORSTABILITY</span></span><br /><span data-ttu-id="2e358-128">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="2e358-128">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="2e358-129">-ISOLATIONLEVEL_SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="2e358-129">-   ISOLATIONLEVEL_SERIALIZABLE</span></span><br /><span data-ttu-id="2e358-130">-ISOLATIONLEVEL_ISOLATED</span><span class="sxs-lookup"><span data-stu-id="2e358-130">-   ISOLATIONLEVEL_ISOLATED</span></span><br /><span data-ttu-id="2e358-131">-ISOLATIONLEVEL_SNAPSHOT **Observação:** começando com [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , ISOLATIONLEVEL_SNAPSHOT é válido para o argumento *isoLevel* se o controle de versão está habilitado ou não para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2e358-131">-   ISOLATIONLEVEL_SNAPSHOT **Note:**  Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ISOLATIONLEVEL_SNAPSHOT is valid for the *isoLevel* argument whether or not versioning is enabled for the database.</span></span> <span data-ttu-id="2e358-132">Porém, ocorrerá um erro se o usuário tentar executar uma instrução e o controle de versão não estiver habilitado e/ou o banco de dados não for somente leitura.</span><span class="sxs-lookup"><span data-stu-id="2e358-132">However, an error will occur if the user attempts to execute a statement and versioning is not enabled and/or the database is not read-only.</span></span> <span data-ttu-id="2e358-133">Além disso, o erro XACT_E_ISOLATIONLEVEL ocorrerá se ISOLATIONLEVEL_SNAPSHOT for especificado como o *isoLevel* quando conectado a uma versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anterior ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e358-133">In addition, the error XACT_E_ISOLATIONLEVEL will occur if ISOLATIONLEVEL_SNAPSHOT is specified as the *isoLevel* when connected to a version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>|  
|<span data-ttu-id="2e358-134">*isoFlags*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-134">*isoFlags*[in]</span></span>|<span data-ttu-id="2e358-135">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna um erro para qualquer valor diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="2e358-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns an error for any value other than zero.</span></span>|  
|<span data-ttu-id="2e358-136">*pOtherOptions*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-136">*pOtherOptions*[in]</span></span>|<span data-ttu-id="2e358-137">Se não for NULL, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo solicitará o objeto de opções da interface.</span><span class="sxs-lookup"><span data-stu-id="2e358-137">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="2e358-138">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna XACT_E_NOTIMEOUT se o membro *ulTimeout* do objeto de opções não for zero.</span><span class="sxs-lookup"><span data-stu-id="2e358-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="2e358-139">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo ignora o valor do membro *szDescription* .</span><span class="sxs-lookup"><span data-stu-id="2e358-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
|<span data-ttu-id="2e358-140">*pulTransactionLevel*[out]</span><span class="sxs-lookup"><span data-stu-id="2e358-140">*pulTransactionLevel*[out]</span></span>|<span data-ttu-id="2e358-141">Se não for NULL, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retornará o nível aninhado da transação.</span><span class="sxs-lookup"><span data-stu-id="2e358-141">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns the nested level of the transaction.</span></span>|  
  
 <span data-ttu-id="2e358-142">Para transações locais, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo implementa os parâmetros **ITransaction:: Abort** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="2e358-142">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Abort** parameters as follows.</span></span>  
  
|<span data-ttu-id="2e358-143">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="2e358-143">Parameter</span></span>|<span data-ttu-id="2e358-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e358-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e358-145">*pboidReason*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-145">*pboidReason*[in]</span></span>|<span data-ttu-id="2e358-146">Ignorado se definido.</span><span class="sxs-lookup"><span data-stu-id="2e358-146">Ignored if set.</span></span> <span data-ttu-id="2e358-147">Pode ser NULL com segurança.</span><span class="sxs-lookup"><span data-stu-id="2e358-147">Can safely be NULL.</span></span>|  
|<span data-ttu-id="2e358-148">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-148">*fRetaining*[in]</span></span>|<span data-ttu-id="2e358-149">Quando TRUE, uma nova transação é iniciada implicitamente para a sessão.</span><span class="sxs-lookup"><span data-stu-id="2e358-149">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="2e358-150">A transação deve ser confirmada ou encerrada pelo consumidor.</span><span class="sxs-lookup"><span data-stu-id="2e358-150">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="2e358-151">Quando for falso, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo será revertido para o modo de confirmação automática da sessão.</span><span class="sxs-lookup"><span data-stu-id="2e358-151">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="2e358-152">*fAsync*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-152">*fAsync*[in]</span></span>|<span data-ttu-id="2e358-153">O provedor de OLE DB de cliente nativo não dá suporte para anulação assíncrona [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e358-153">Asynchronous abort is not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="2e358-154">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retornará XACT_E_NOTSUPPORTED se o valor não for false.</span><span class="sxs-lookup"><span data-stu-id="2e358-154">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED if the value is not FALSE.</span></span>|  
  
 <span data-ttu-id="2e358-155">Para transações locais, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo implementa os parâmetros **ITransaction:: Commit** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="2e358-155">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Commit** parameters as follows.</span></span>  
  
|<span data-ttu-id="2e358-156">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="2e358-156">Parameter</span></span>|<span data-ttu-id="2e358-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e358-157">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e358-158">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-158">*fRetaining*[in]</span></span>|<span data-ttu-id="2e358-159">Quando TRUE, uma nova transação é iniciada implicitamente para a sessão.</span><span class="sxs-lookup"><span data-stu-id="2e358-159">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="2e358-160">A transação deve ser confirmada ou encerrada pelo consumidor.</span><span class="sxs-lookup"><span data-stu-id="2e358-160">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="2e358-161">Quando for falso, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo será revertido para o modo de confirmação automática da sessão.</span><span class="sxs-lookup"><span data-stu-id="2e358-161">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="2e358-162">*grfTC*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-162">*grfTC*[in]</span></span>|<span data-ttu-id="2e358-163">Os retornos assíncronos e da fase um não são suportados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB nativo do cliente.</span><span class="sxs-lookup"><span data-stu-id="2e358-163">Asynchronous and phase one returns are not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="2e358-164">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo retorna XACT_E_NOTSUPPORTED para qualquer valor diferente de XACTTC_SYNC.</span><span class="sxs-lookup"><span data-stu-id="2e358-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED for any value other than XACTTC_SYNC.</span></span>|  
|<span data-ttu-id="2e358-165">*grfRM*[in]</span><span class="sxs-lookup"><span data-stu-id="2e358-165">*grfRM*[in]</span></span>|<span data-ttu-id="2e358-166">Deve ser 0.</span><span class="sxs-lookup"><span data-stu-id="2e358-166">Must be 0.</span></span>|  
  
 <span data-ttu-id="2e358-167">Os conjuntos de linhas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo na sessão são preservados em uma operação de confirmação local ou de anulação com base nos valores das propriedades do conjunto de linhas DBPROP_ABORTPRESERVE e DBPROP_COMMITPRESERVE.</span><span class="sxs-lookup"><span data-stu-id="2e358-167">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are preserved on a local commit or abort operation based on the values of the rowset properties DBPROP_ABORTPRESERVE and DBPROP_COMMITPRESERVE.</span></span> <span data-ttu-id="2e358-168">Por padrão, essas propriedades são VARIANT_FALSE e todos os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de linhas do provedor de OLE DB do cliente nativo na sessão são perdidos após uma operação de anulação ou confirmação.</span><span class="sxs-lookup"><span data-stu-id="2e358-168">By default, these properties are both VARIANT_FALSE and all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are lost following an abort or commit operation.</span></span>  
  
 <span data-ttu-id="2e358-169">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não implementa a interface **ITransactionObject** .</span><span class="sxs-lookup"><span data-stu-id="2e358-169">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not implement the **ITransactionObject** interface.</span></span> <span data-ttu-id="2e358-170">Uma tentativa do consumidor de recuperar uma referência na interface retorna E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="2e358-170">A consumer attempt to retrieve a reference on the interface returns E_NOINTERFACE.</span></span>  
  
 <span data-ttu-id="2e358-171">Este exemplo usa **ITransactionLocal**.</span><span class="sxs-lookup"><span data-stu-id="2e358-171">This example uses **ITransactionLocal**.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*   pIDBCreateSession   = NULL;  
ITransaction*       pITransaction       = NULL;  
IDBCreateCommand*   pIDBCreateCommand   = NULL;  
IRowset*            pIRowset            = NULL;  
  
HRESULT             hr;  
  
// Get the command creation and local transaction interfaces for the  
// session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
if (FAILED(hr = pIDBCreateCommand->QueryInterface(IID_ITransactionLocal,  
    (void**) &pITransaction)))  
    {  
    // Process error. Release any references and return.  
    }  
  
// Start the local transaction.  
if (FAILED(hr = ((ITransactionLocal*) pITransaction)->StartTransaction(  
    ISOLATIONLEVEL_REPEATABLEREAD, 0, NULL, NULL)))  
    {  
    // Process error from StartTransaction. Release any references and  
    // return.  
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
    // Get error from update, then terminate.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, XACTTC_SYNC, 0)))  
        {  
        // Get error from failed commit.  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e358-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e358-172">See Also</span></span>  
 <span data-ttu-id="2e358-173">[Transações](transactions.md) </span><span class="sxs-lookup"><span data-stu-id="2e358-173">[Transactions](transactions.md) </span></span>  
 [<span data-ttu-id="2e358-174">Trabalhando com isolamento de instantâneo</span><span class="sxs-lookup"><span data-stu-id="2e358-174">Working with Snapshot Isolation</span></span>](../native-client/features/working-with-snapshot-isolation.md)  
  
  
