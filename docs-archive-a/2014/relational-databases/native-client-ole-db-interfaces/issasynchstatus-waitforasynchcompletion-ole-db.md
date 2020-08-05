---
title: ISSAsynchStatus::WaitForAsynchCompletion (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- WaitForAsynchCompletion method
ms.assetid: 9f65e9e7-eb93-47a1-bc42-acd4649fbd0e
author: rothja
ms.author: jroth
ms.openlocfilehash: f57211d1c62535828704dc971e345b412c284cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572043"
---
# <a name="issasynchstatuswaitforasynchcompletion-ole-db"></a><span data-ttu-id="ed9c0-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ed9c0-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span></span>
  <span data-ttu-id="ed9c0-103">Aguarda até que a operação com execução assíncrona seja concluída ou que um tempo limite seja atingido.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-103">Waits until the asynchronously executing operation is complete or until a time-out occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed9c0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ed9c0-104">Syntax</span></span>  
  
```  
  
HRESULT WaitForAsynchCompletion(   
  DWORD dwMillisecTimeOut);  
```  
  
## <a name="arguments"></a><span data-ttu-id="ed9c0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ed9c0-105">Arguments</span></span>  
 <span data-ttu-id="ed9c0-106">*dwMillisecTimeOut*[in]</span><span class="sxs-lookup"><span data-stu-id="ed9c0-106">*dwMillisecTimeOut*[in]</span></span>  
 <span data-ttu-id="ed9c0-107">Tempo limite em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-107">Time-out in milliseconds.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="ed9c0-108">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="ed9c0-108">Return Code Values</span></span>  
 <span data-ttu-id="ed9c0-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed9c0-109">S_OK</span></span>  
 <span data-ttu-id="ed9c0-110">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-110">The method succeeded.</span></span>  
  
 <span data-ttu-id="ed9c0-111">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="ed9c0-111">E_UNEXPECTED</span></span>  
 <span data-ttu-id="ed9c0-112">Um conjunto de linhas está em um estado não usado porque **ITransaction::Commit** ou **ITransaction::Abort** foi chamado ou o conjunto de linhas foi cancelado durante sua fase de inicialização.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-112">A rowset is in an unused state because **ITransaction::Commit** or **ITransaction::Abort** has been called or the rowset was cancelled during its initialization phase.</span></span>  
  
 <span data-ttu-id="ed9c0-113">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="ed9c0-113">DB_E_CANCELED</span></span>  
 <span data-ttu-id="ed9c0-114">O processamento assíncrono foi cancelado durante a população do conjunto de linhas ou a inicialização de objeto de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-114">Asynchronous processing was cancelled during rowset population or data source object initialization.</span></span>  
  
 <span data-ttu-id="ed9c0-115">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="ed9c0-115">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="ed9c0-116">A operação ainda não foi concluída, embora o tempo limite especificado tenha sido atingido.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-116">The operation has not yet completed even though specified time-out has been reached.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed9c0-117">Além dos valores de código de retorno listados anteriormente, o método **ISSAsynchStatus::WaitForAsynchCompletion** também dá suporte aos valores de código de retorno retornados pelos principais métodos **ICommand::Execute** e **IDBInitialize::Initialize** do OLE DB.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-117">In addition to the return code values listed above, the **ISSAsynchStatus::WaitForAsynchCompletion** method also supports the return code values returned by the core OLEDB **ICommand::Execute** and **IDBInitialize::Initialize** methods.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed9c0-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="ed9c0-118">Remarks</span></span>  
 <span data-ttu-id="ed9c0-119">O método **ISSAsynchStatus::WaitForAsynchCompletion** não será retornado enquanto o valor de tempo limite (em milissegundos) não se esgotar ou a operação pendente não for concluída.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-119">The **ISSAsynchStatus::WaitForAsynchCompletion** method will not return until the time-out value (in milliseconds) has passed or the pending operation is done.</span></span> <span data-ttu-id="ed9c0-120">O objeto **Command** tem uma propriedade **CommandTimeout** que controla o número de segundos que uma consulta será executada antes de atingir o tempo limite. A propriedade **CommandTimeout** será ignorada se usada em conjunto com o método **ISSAsynchStatus:: WaitForAsynchCompletion** .</span><span class="sxs-lookup"><span data-stu-id="ed9c0-120">The **Command** object has a **CommandTimeout** property that controls the number of seconds a query will run before timing out. The **CommandTimeout** property will be ignored if used in conjunction with **ISSAsynchStatus::WaitForAsynchCompletion** method.</span></span>  
  
 <span data-ttu-id="ed9c0-121">A propriedade de tempo limite é ignorada para operações assíncronas.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-121">The time-out property is ignored for asynchronous operations.</span></span> <span data-ttu-id="ed9c0-122">O parâmetro de tempo limite de **ISSAsynchStatus::WaitForAsynchCompletion** especifica o tempo máximo decorrido antes de o controle ser retornado ao chamador.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-122">The time-out parameter of **ISSAsynchStatus::WaitForAsynchCompletion** specifies the maximum amount of time that will elapse before control is returned to the caller.</span></span> <span data-ttu-id="ed9c0-123">Se esse tempo limite expirar, DB_S_ASYNCHRONOUS será retornado.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-123">If this time-out expires, DB_S_ASYNCHRONOUS will be returned.</span></span> <span data-ttu-id="ed9c0-124">Os tempos limite nunca cancelam operações assíncronas.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-124">Time-outs never cancel asynchronous operations.</span></span> <span data-ttu-id="ed9c0-125">Se o aplicativo precisar cancelar uma operação assíncrona que não tenha sido concluída dentro de um tempo limite, ele deverá aguardar o tempo limite e, em seguida, cancelar explicitamente a operação, caso DB_S_ASYNCHRONOUS seja retornado.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-125">If the application needs to cancel an asynchronous operation that does not complete within a time-out period, it must wait for the time-out and then explicitly cancel the operation if DB_S_ASYNCHRONOUS is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed9c0-126">Quando os Componentes de Serviço do OLE DB são usados, S_OK pode ser retornado quando DB_S_ASYNCHRONOUS é esperado; portanto, os aplicativos devem chamar [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) para verificar a conclusão quando S_OK ou DB_S_ASYNCHRONOUS é retornado.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-126">When the OLE DB Service Components are used, S_OK may be returned when DB_S_ASYNCHRONOUS is expected, so applications should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) to check for completion when S_OK or DB_S_ASYNCHRONOUS is returned.</span></span>  
  
 <span data-ttu-id="ed9c0-127">Se o valor de *dwMillisecTimeOut* for definido como INFINITE, o método **ISSAsynchStatus::WaitForAsynchCompletion** será bloqueado até a conclusão da operação.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-127">If the *dwMillisecTimeOut* value is set to INFINITE, the **ISSAsynchStatus::WaitForAsynchCompletion** method blocks until the operation is done.</span></span> <span data-ttu-id="ed9c0-128">Se o valor de *dwMillisecTimeOut* for definido como 0, o método será retornado imediatamente com o status da operação pendente.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-128">If the *dwMillisecTimeOut* value is set to 0, then the method will return immediately with the status of the pending operation.</span></span> <span data-ttu-id="ed9c0-129">Se o tempo limite expirar antes da conclusão da operação, DB_S_ASYNCHRONOUS será retornado.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-129">If the time-out expires before the operation is complete DB_S_ASYNCHRONOUS will be returned.</span></span>  
  
 <span data-ttu-id="ed9c0-130">Se a operação for concluída antes da expiração do tempo limite, o HRESULT retornado será o HRESULT retornado pela operação (o HRESULT retornado executou a operação de forma síncrona).</span><span class="sxs-lookup"><span data-stu-id="ed9c0-130">If the operation completes before the time-out expires, the returned HRESULT will be the HRESULT returned by the operation (the HRESULT that would have been returned had the operation been performed synchronously).</span></span>  
  
 <span data-ttu-id="ed9c0-131">Além disso, a propriedade SSPROP_ISSAsynchStatus foi adicionada ao conjunto de propriedades DBPROPSET_SQLSERVERROWSET.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-131">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="ed9c0-132">Os provedores que dão suporte à interface [ISSAsynchStatus](issasynchstatus-ole-db.md) precisam implementar essa propriedade com um valor de VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="ed9c0-132">Providers that support the [ISSAsynchStatus](issasynchstatus-ole-db.md) interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9c0-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ed9c0-133">See Also</span></span>  
 <span data-ttu-id="ed9c0-134">[Executando operações assíncronas](../native-client/features/performing-asynchronous-operations.md) </span><span class="sxs-lookup"><span data-stu-id="ed9c0-134">[Performing Asynchronous Operations](../native-client/features/performing-asynchronous-operations.md) </span></span>  
 [<span data-ttu-id="ed9c0-135">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed9c0-135">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-ole-db.md)  
  
  
