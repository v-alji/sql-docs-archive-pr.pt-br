---
title: ISSAbort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- ISSAbort interface
ms.assetid: 7c4df482-4a83-4da0-802b-3637b507693a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7195311fefe3f0f1b7b4d6d789aa8d8487bc3bfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685889"
---
# <a name="issabort-ole-db"></a><span data-ttu-id="ae516-102">ISSAbort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ae516-102">ISSAbort (OLE DB)</span></span>
  <span data-ttu-id="ae516-103">A interface **ISSAbort** , que é exposta no provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, fornece o método [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) que é usado para cancelar o conjunto de linhas atual, além de todos os comandos executados em lotes com o comando que gerou inicialmente o conjunto de linhas e cuja execução ainda não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="ae516-103">The **ISSAbort** interface, which is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, provides the [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) method that is used to cancel the current rowset plus any commands batched with the command that initially generated the rowset, and that have not yet completed execution.</span></span>  
  
 <span data-ttu-id="ae516-104">O**ISSAbout** é uma interface específica do provedou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client disponível pou meio da utilização de **QueryInterface** no objeto **IMultipleResults** retounado pou **ICommand::Execute** ou **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="ae516-104">**ISSAbort** is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider-specific interface available by using **QueryInterface** on the **IMultipleResults** object returned by **ICommand::Execute** or **IOpenRowset::OpenRowset**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae516-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ae516-105">In This Section</span></span>  
  
|<span data-ttu-id="ae516-106">Método</span><span class="sxs-lookup"><span data-stu-id="ae516-106">Method</span></span>|<span data-ttu-id="ae516-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="ae516-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae516-108">ISSAbort:: Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ae516-108">ISSAbort::Abort &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md)|<span data-ttu-id="ae516-109">Cancela o conjunto de linhas atual, além de todos os comandos em lote associados ao comando atual.</span><span class="sxs-lookup"><span data-stu-id="ae516-109">Cancels the current rowset plus any batched commands associated with the current command.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae516-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae516-110">See Also</span></span>  
 [<span data-ttu-id="ae516-111">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ae516-111">Interfaces &#40;OLE DB&#41;</span></span>](../../../2014/database-engine/dev-guide/interfaces-ole-db.md)  
  
  
