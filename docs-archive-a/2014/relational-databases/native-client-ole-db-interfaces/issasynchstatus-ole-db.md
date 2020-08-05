---
title: ISSAsynchStatus (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSAsynchStatus interface
ms.assetid: c643f09f-9ccc-4d8b-9243-3cde86c2bd46
author: rothja
ms.author: jroth
ms.openlocfilehash: 4489f9d1ad576d49d885842f6969f9b61065791c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572044"
---
# <a name="issasynchstatus-ole-db"></a><span data-ttu-id="68674-102">ISSAsynchStatus (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="68674-102">ISSAsynchStatus (OLE DB)</span></span>
  <span data-ttu-id="68674-103">**ISSAsynchStatus** expõe o suporte a operações assíncronas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68674-103">**ISSAsynchStatus** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asynchronous operations.</span></span> <span data-ttu-id="68674-104">Esta é uma interface opcional herdada da interface OLE DB central **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="68674-104">This is an optional interface that inherits from the core OLE DB interface **IDBAsynchStatus**.</span></span> <span data-ttu-id="68674-105">Além dos métodos **Abort** e **GetStatus** herdados de **IDBAsynchStatus**, **ISSAsynchStatus** fornece um novo método usado para aguardar até que uma operação assíncrona tenha sido concluída ou um tempo limite tenha sido atingido.</span><span class="sxs-lookup"><span data-stu-id="68674-105">In addition to the **Abort** and **GetStatus** methods inherited from **IDBAsynchStatus**, **ISSAsynchStatus** provides one new method that is used to wait until an asynchronous operation has completed or a time-out occurs.</span></span>  
  
|<span data-ttu-id="68674-106">Método</span><span class="sxs-lookup"><span data-stu-id="68674-106">Method</span></span>|<span data-ttu-id="68674-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="68674-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68674-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="68674-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span></span>](issasynchstatus-abort-ole-db.md)|<span data-ttu-id="68674-109">Cancela uma operação que está sendo executada de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="68674-109">Cancels an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="68674-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="68674-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-getstatus-ole-db.md)|<span data-ttu-id="68674-111">Retorna o status de uma operação que está sendo executada de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="68674-111">Returns the status of an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="68674-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="68674-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span></span>](issasynchstatus-waitforasynchcompletion-ole-db.md)|<span data-ttu-id="68674-113">Aguarda até que a operação com execução assíncrona seja concluída ou um tempo limite seja atingido.</span><span class="sxs-lookup"><span data-stu-id="68674-113">Waits until the asynchronously executing operation is complete or a time-out occurs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68674-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="68674-114">Remarks</span></span>  
 <span data-ttu-id="68674-115">A implementação de **ISSAsynchStatus** do método **ISSAsynchStatus::GetStatus** é a mesma do método **IDBAsynchStatus::GetStatus** , com exceção de que, se a inicialização de um objeto de fonte de dados for anulada, E_UNEXPECTED será retornado, em vez de DB_E_CANCELED (apesar de que **ISSAsynchStatus::WaitForAsynchCompletion** retorna DB_E_CANCELED).</span><span class="sxs-lookup"><span data-stu-id="68674-115">The **ISSAsynchStatus** implementation of the **ISSAsynchStatus::GetStatus** method is the same as the **IDBAsynchStatus::GetStatus** method except that if the initialization of a data source object is aborted, E_UNEXPECTED is returned rather than DB_E_CANCELED (although **ISSAsynchStatus::WaitForAsynchCompletion** returns DB_E_CANCELED).</span></span> <span data-ttu-id="68674-116">Isso ocorre porque o objeto de fonte de dados não é deixado no estado normal após uma operação de anulação, para que possa haver outras tentativas de operações de inicialização.</span><span class="sxs-lookup"><span data-stu-id="68674-116">This is because the data source object is not left in the usual state following an abort operation, so that further initialization operations may be attempted.</span></span>  
  
 <span data-ttu-id="68674-117">Os métodos a seguir suportam o uso da execução assíncrona no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="68674-117">The following methods support the use of asynchronous execution in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="68674-118">**ICommand::Execute**</span><span class="sxs-lookup"><span data-stu-id="68674-118">**ICommand::Execute**</span></span>  
  
-   <span data-ttu-id="68674-119">**IOpenRowset::OpenRowset**</span><span class="sxs-lookup"><span data-stu-id="68674-119">**IOpenRowset::OpenRowset**</span></span>  
  
-   <span data-ttu-id="68674-120">**IMultipleResults::GetResult**</span><span class="sxs-lookup"><span data-stu-id="68674-120">**IMultipleResults::GetResult**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68674-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68674-121">See Also</span></span>  
 <span data-ttu-id="68674-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="68674-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 [<span data-ttu-id="68674-123">Executando operações assíncronas</span><span class="sxs-lookup"><span data-stu-id="68674-123">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
