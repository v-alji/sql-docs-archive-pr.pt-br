---
title: ISSAsynchStatus::Abort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: 2a4bd312-839a-45a8-a299-fc8609be9a2a
author: rothja
ms.author: jroth
ms.openlocfilehash: 0fb352b6541240126dcd4c60521b93d57d6839f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681641"
---
# <a name="issasynchstatusabort-ole-db"></a><span data-ttu-id="b8be9-102">ISSAsynchStatus::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="b8be9-102">ISSAsynchStatus::Abort (OLE DB)</span></span>
  <span data-ttu-id="b8be9-103">Cancela uma operação que está sendo executada de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="b8be9-103">Cancels an asynchronously executing operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8be9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b8be9-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(  
  HCHAPTER hChapter,  
  DBASYNCHOP eOperation);  
```  
  
## <a name="arguments"></a><span data-ttu-id="b8be9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8be9-105">Arguments</span></span>  
 <span data-ttu-id="b8be9-106">*hChapter*[in]</span><span class="sxs-lookup"><span data-stu-id="b8be9-106">*hChapter*[in]</span></span>  
 <span data-ttu-id="b8be9-107">O identificador do capítulo que contém a operação a ser anulada.</span><span class="sxs-lookup"><span data-stu-id="b8be9-107">The handle of the chapter for which to abort the operation.</span></span> <span data-ttu-id="b8be9-108">Se o objeto que está sendo chamado não for um objeto de conjunto de linhas ou se a operação não se aplicar a um capítulo, o chamador deverá definir *hChapter* como DB_NULL_HCHAPTER.</span><span class="sxs-lookup"><span data-stu-id="b8be9-108">If the object being called is not a rowset object or the operation does not apply to a chapter, the caller must set *hChapter* to DB_NULL_HCHAPTER.</span></span>  
  
 <span data-ttu-id="b8be9-109">*eOperation*[in]</span><span class="sxs-lookup"><span data-stu-id="b8be9-109">*eOperation*[in]</span></span>  
 <span data-ttu-id="b8be9-110">A operação a ser anulada.</span><span class="sxs-lookup"><span data-stu-id="b8be9-110">The operation to abort.</span></span> <span data-ttu-id="b8be9-111">O valor desse argumento deveria ser o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8be9-111">This should be the following value:</span></span>  
  
 <span data-ttu-id="b8be9-112">DBASYNCHOP_OPEN – a solicitação de cancelamento se aplica à abertura ou população assíncrona de um conjunto de linhas ou à inicialização assíncrona de um objeto de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8be9-112">DBASYNCHOP_OPEN-The request to cancel applies to the asynchronous opening or population of a rowset or to the asynchronous initialization of a data source object.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="b8be9-113">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="b8be9-113">Return Code Values</span></span>  
 <span data-ttu-id="b8be9-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8be9-114">S_OK</span></span>  
 <span data-ttu-id="b8be9-115">A solicitação para cancelar a operação assíncrona foi processada.</span><span class="sxs-lookup"><span data-stu-id="b8be9-115">The request to cancel the asynchronous operation was processed.</span></span> <span data-ttu-id="b8be9-116">Isso não garante que a operação seja cancelada.</span><span class="sxs-lookup"><span data-stu-id="b8be9-116">This does not guarantee that the operation itself was canceled.</span></span> <span data-ttu-id="b8be9-117">Para determinar se a operação foi cancelada, o consumidor deve chamar [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) e verificar DB_E_CANCELED; no entanto, esse valor pode não ser retornado na chamada seguinte.</span><span class="sxs-lookup"><span data-stu-id="b8be9-117">To determine whether the operation was canceled, the consumer should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) and check for DB_E_CANCELED; however, it might not be returned in the very next call.</span></span>  
  
 <span data-ttu-id="b8be9-118">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="b8be9-118">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="b8be9-119">A operação assíncrona não pode ser cancelada.</span><span class="sxs-lookup"><span data-stu-id="b8be9-119">The asynchronous operation cannot be canceled.</span></span>  
  
 <span data-ttu-id="b8be9-120">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="b8be9-120">DB_E_CANCELED</span></span>  
 <span data-ttu-id="b8be9-121">A solicitação para anular a operação assíncrona foi cancelada durante notificações.</span><span class="sxs-lookup"><span data-stu-id="b8be9-121">The request to abort the asynchronous operation was canceled during notifications.</span></span> <span data-ttu-id="b8be9-122">A operação ainda está sendo executada de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="b8be9-122">The operation is still being executed asynchronously.</span></span>  
  
 <span data-ttu-id="b8be9-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8be9-123">E_FAIL</span></span>  
 <span data-ttu-id="b8be9-124">Ocorreu um erro específico de provedor.</span><span class="sxs-lookup"><span data-stu-id="b8be9-124">A provider-specific error occurred.</span></span>  
  
 <span data-ttu-id="b8be9-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b8be9-125">E_INVALIDARG</span></span>  
 <span data-ttu-id="b8be9-126">O parâmetro *hChapter* não é DB_NULL_HCHAPTER ou *eOperation* não é DBASYNCH_OPEN.</span><span class="sxs-lookup"><span data-stu-id="b8be9-126">The *hChapter* parameter is not DB_NULL_HCHAPTER or *eOperation* is not DBASYNCH_OPEN.</span></span>  
  
 <span data-ttu-id="b8be9-127">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="b8be9-127">E_UNEXPECTED</span></span>  
 <span data-ttu-id="b8be9-128">**ISSAsynchStatus::Abort** foi chamado em um objeto de fonte de dados no qual **IDBInitialize::Initialize** não foi chamado ou não foi concluído.</span><span class="sxs-lookup"><span data-stu-id="b8be9-128">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** has not been called, or has not completed.</span></span>  
  
 <span data-ttu-id="b8be9-129">**ISSAsynchStatus:: Abort** foi chamado em um objeto de fonte de dados no qual **IDBInitialize:: Initialize** foi chamado, mas subsequentemente cancelado antes da inicialização ou atingiu o tempo limite. O objeto de fonte de dados ainda não foi inicializado.</span><span class="sxs-lookup"><span data-stu-id="b8be9-129">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** was called but subsequently canceled before initialization, or has timed out. The data source object is still uninitialized.</span></span>  
  
 <span data-ttu-id="b8be9-130">**ISSAsynchStatus::Abort** foi chamado em um conjunto de linhas no qual **ITransaction::Commit** ou **ITransaction::Abort** foi chamado anteriormente, e o conjunto de linhas não sobreviveu à operação de confirmação ou anulação e está em um estado zumbi.</span><span class="sxs-lookup"><span data-stu-id="b8be9-130">**ISSAsynchStatus::Abort** was called on a rowset on which **ITransaction::Commit** or **ITransaction::Abort** was previously called, and the rowset did not survive the commit or abort and is in a zombie state.</span></span>  
  
 <span data-ttu-id="b8be9-131">**ISSAsynchStatus::Abort** foi chamado em um conjunto de linhas cancelado de forma assíncrona em sua fase de inicialização.</span><span class="sxs-lookup"><span data-stu-id="b8be9-131">**ISSAsynchStatus::Abort** was called on a rowset that was asynchronously canceled in its initialization phase.</span></span> <span data-ttu-id="b8be9-132">O conjunto de linhas está em um estado zumbi.</span><span class="sxs-lookup"><span data-stu-id="b8be9-132">The rowset is in a zombie state.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8be9-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="b8be9-133">Remarks</span></span>  
 <span data-ttu-id="b8be9-134">Anular a inicialização de um conjunto de linhas ou objeto de fonte de dados pode deixar o conjunto de linhas ou o objeto de fonte de dados em um estado zumbi, de modo que todos os métodos diferentes de **IUnknown** retornam E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="b8be9-134">Aborting the initialization of a rowset or data source object might leave the rowset or data source object in a zombie state, such that all methods other than **IUnknown** methods return E_UNEXPECTED.</span></span> <span data-ttu-id="b8be9-135">Quando isso acontece, a única ação possível para o consumidor é liberar o conjunto de linhas ou objeto de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8be9-135">When this happens, the only possible action for the consumer is to release the rowset or data source object.</span></span>  
  
 <span data-ttu-id="b8be9-136">Chamar **ISSAsynchStatus::Abort** e atribuir um valor a *eOperation* diferente de DBASYNCHOP_OPEN retorna S_OK.</span><span class="sxs-lookup"><span data-stu-id="b8be9-136">Calling **ISSAsynchStatus::Abort** and passing a value for *eOperation* other than DBASYNCHOP_OPEN returns S_OK.</span></span> <span data-ttu-id="b8be9-137">Isso não significa que a operação tenha sido concluída ou cancelada.</span><span class="sxs-lookup"><span data-stu-id="b8be9-137">This does not imply that the operation completed or was canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8be9-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b8be9-138">See Also</span></span>  
 [<span data-ttu-id="b8be9-139">Executando operações assíncronas</span><span class="sxs-lookup"><span data-stu-id="b8be9-139">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
