---
title: ISSAbort::Abort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAbort::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: a5bca169-694b-4895-84ac-e8fba491e479
author: rothja
ms.author: jroth
ms.openlocfilehash: 3daad53087c876af8dc46bccc9c4bf7952976067
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681643"
---
# <a name="issabortabort-ole-db"></a><span data-ttu-id="cc5ae-102">ISSAbort::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="cc5ae-102">ISSAbort::Abort (OLE DB)</span></span>
  <span data-ttu-id="cc5ae-103">Cancela o conjunto de linhas atual, além de todos os comandos em lote associados ao comando atual.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-103">Cancels the current rowset plus any batched commands associated with the current command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc5ae-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc5ae-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="cc5ae-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="cc5ae-105">Remarks</span></span>  
 <span data-ttu-id="cc5ae-106">Se o comando que está sendo anulado está em um procedimento armazenado, a execução deste (e de quaisquer procedimentos armazenados que chamaram esse procedimento) será encerrada, bem como o lote de comandos que contém a chamada de procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-106">If the command being aborted is in a stored procedure, execution of the stored procedure (and any procedures which had called that procedure) will be terminated as well as the command batch which contains the stored procedure call.</span></span> <span data-ttu-id="cc5ae-107">Se o servidor estiver no processo de transferir um conjunto de resultados para o cliente, ele será interrompido.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-107">If the server is in the process of transferring a result set to the client, this will be stopped.</span></span> <span data-ttu-id="cc5ae-108">Se o cliente não desejar consumir um conjunto de resultados, chamar **ISSAbort::Abort** antes de liberar o conjunto de linhas agilizará a liberação do conjunto de resultados, mas se houver uma transação aberta e XACT_ABORT estiver ON, a transação será revertida quando **ISSAbort::Abort** for chamado.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-108">If the client does not want to consume a result set, calling **ISSAbort::Abort** before releasing the rowset will speed up the rowset release, but if there is an open transaction and XACT_ABORT is ON, the transaction will be rolled back when **ISSAbort::Abort** is called</span></span>  
  
 <span data-ttu-id="cc5ae-109">Depois que **ISSAbort::Abort** retornar S_OK, a interface **IMultipleResults** associada entrará em um estado inutilizável e retornará DB_E_CANCELED para todas as chamadas de método (com exceção dos métodos definidos pela interface **IUnknown** ) até que seja liberada.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-109">After **ISSAbort::Abort** returns S_OK, the associated **IMultipleResults** interface enters a unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface) until it is released.</span></span> <span data-ttu-id="cc5ae-110">Se um **IRowset** foi obtido de **IMultipleResults** antes de uma chamada para **Abort**, também entrará em um estado inutilizável e retornará DB_E_CANCELED para todas as chamadas de método (com exceção dos métodos definidos pela interface **IUnknown** e **IRowset::ReleaseRows**) até que seja liberado após uma chamada bem-sucedida para **ISSAbort::Abort**.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-110">If an **IRowset** had been obtained from **IMultipleResults** prior to a call to **Abort**, it also enters an unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface and **IRowset::ReleaseRows**) until it is released after a successful call to **ISSAbort::Abort**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc5ae-111">Do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] em diante, se o estado XACT_ABORT do servidor for ON, a execução de **ISSAbort::Abort** será encerrada e reverterá qualquer transação implícita ou explícita atual quando conectada ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc5ae-111">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if the server XACT_ABORT state is ON, executing **ISSAbort::Abort** will terminate and roll back any current implicit or explicit transaction when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cc5ae-112">Versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não anularão a transação atual.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-112">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not abort the current transaction.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="cc5ae-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cc5ae-113">Arguments</span></span>  
 <span data-ttu-id="cc5ae-114">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-114">None.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="cc5ae-115">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="cc5ae-115">Return Code Values</span></span>  
 <span data-ttu-id="cc5ae-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc5ae-116">S_OK</span></span>  
 <span data-ttu-id="cc5ae-117">O método **ISSAbort::Abort** retorna S_OK se o lote foi cancelado e DB_E_CANTCANCEL em caso contrário.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-117">The **ISSAbort::Abort** method returns S_OK if the batch was canceled and DB_E_CANTCANCEL otherwise.</span></span> <span data-ttu-id="cc5ae-118">Se o lote já foi cancelado, DB_E_CANCELED será retornado.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-118">If the batch has already been canceled, DB_E_CANCELED is returned.</span></span>  
  
 <span data-ttu-id="cc5ae-119">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="cc5ae-119">DB_E_CANCELED</span></span>  
 <span data-ttu-id="cc5ae-120">O lote já foi cancelado.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-120">The batch has already been canceled.</span></span>  
  
 <span data-ttu-id="cc5ae-121">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="cc5ae-121">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="cc5ae-122">O lote não foi cancelado.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-122">The batch was not canceled.</span></span>  
  
 <span data-ttu-id="cc5ae-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc5ae-123">E_FAIL</span></span>  
 <span data-ttu-id="cc5ae-124">Ocorreu um erro específico do provedor; para obter informações detalhadas, use a interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="cc5ae-124">A provider specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="cc5ae-125">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="cc5ae-125">E_UNEXPECTED</span></span>  
 <span data-ttu-id="cc5ae-126">A chamada para o método era inesperada.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-126">The call to the method was unexpected.</span></span> <span data-ttu-id="cc5ae-127">Por exemplo, o objeto está em um estado de zumbi porque **ISSAbort::Abort** já foi chamado.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-127">For example, the object is in a zombie state because **ISSAbort::Abort** has already been called.</span></span>  
  
 <span data-ttu-id="cc5ae-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cc5ae-128">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="cc5ae-129">Erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="cc5ae-129">Out of memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5ae-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc5ae-130">See Also</span></span>  
 [<span data-ttu-id="cc5ae-131">ISSAbort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cc5ae-131">ISSAbort &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/issabort-ole-db.md)  
  
  
