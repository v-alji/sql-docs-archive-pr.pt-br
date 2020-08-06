---
title: Propriedade State (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- State Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a7456113d9ec4444507d1057892a65adf241992f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681471"
---
# <a name="state-property-sqlservice-class"></a><span data-ttu-id="eef1e-102">Propriedade State (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="eef1e-102">State Property (SqlService Class)</span></span>
  <span data-ttu-id="eef1e-103">Obtém ou define o estado atual do serviço.</span><span class="sxs-lookup"><span data-stu-id="eef1e-103">Gets or sets the current state of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef1e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eef1e-104">Syntax</span></span>  
  
```  
  
object  
.State [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="eef1e-105">Partes</span><span class="sxs-lookup"><span data-stu-id="eef1e-105">Parts</span></span>  
 <span data-ttu-id="eef1e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="eef1e-106">*object*</span></span>  
 <span data-ttu-id="eef1e-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="eef1e-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="eef1e-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="eef1e-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="eef1e-109">Um valor uint32 que especifica o estado do serviço.</span><span class="sxs-lookup"><span data-stu-id="eef1e-109">A uint32 value that specifies the state of the service.</span></span>  
  
 <span data-ttu-id="eef1e-110">Pode conter um dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="eef1e-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="eef1e-111">1</span><span class="sxs-lookup"><span data-stu-id="eef1e-111">1</span></span>  
 <span data-ttu-id="eef1e-112">Stopped.</span><span class="sxs-lookup"><span data-stu-id="eef1e-112">Stopped.</span></span> <span data-ttu-id="eef1e-113">O serviço foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="eef1e-113">The service is stopped.</span></span>  
  
 <span data-ttu-id="eef1e-114">2</span><span class="sxs-lookup"><span data-stu-id="eef1e-114">2</span></span>  
 <span data-ttu-id="eef1e-115">Start Pending.</span><span class="sxs-lookup"><span data-stu-id="eef1e-115">Start Pending.</span></span> <span data-ttu-id="eef1e-116">O serviço está aguardando para iniciar.</span><span class="sxs-lookup"><span data-stu-id="eef1e-116">The service is waiting to start.</span></span>  
  
 <span data-ttu-id="eef1e-117">3</span><span class="sxs-lookup"><span data-stu-id="eef1e-117">3</span></span>  
 <span data-ttu-id="eef1e-118">Stop Pending.</span><span class="sxs-lookup"><span data-stu-id="eef1e-118">Stop Pending.</span></span> <span data-ttu-id="eef1e-119">O serviço está aguardando paras ser interrompido.</span><span class="sxs-lookup"><span data-stu-id="eef1e-119">The service is waiting to stop.</span></span>  
  
 <span data-ttu-id="eef1e-120">4</span><span class="sxs-lookup"><span data-stu-id="eef1e-120">4</span></span>  
 <span data-ttu-id="eef1e-121">Running.</span><span class="sxs-lookup"><span data-stu-id="eef1e-121">Running.</span></span> <span data-ttu-id="eef1e-122">O serviço está em execução.</span><span class="sxs-lookup"><span data-stu-id="eef1e-122">The service is running.</span></span>  
  
 <span data-ttu-id="eef1e-123">5</span><span class="sxs-lookup"><span data-stu-id="eef1e-123">5</span></span>  
 <span data-ttu-id="eef1e-124">Continue Pending.</span><span class="sxs-lookup"><span data-stu-id="eef1e-124">Continue Pending.</span></span> <span data-ttu-id="eef1e-125">O serviço está aguardando para prosseguir.</span><span class="sxs-lookup"><span data-stu-id="eef1e-125">The service is waiting to continue.</span></span>  
  
 <span data-ttu-id="eef1e-126">6</span><span class="sxs-lookup"><span data-stu-id="eef1e-126">6</span></span>  
 <span data-ttu-id="eef1e-127">Pause Pending.</span><span class="sxs-lookup"><span data-stu-id="eef1e-127">Pause Pending.</span></span> <span data-ttu-id="eef1e-128">O serviço está aguardando para ser pausado.</span><span class="sxs-lookup"><span data-stu-id="eef1e-128">The service is waiting to pause.</span></span>  
  
 <span data-ttu-id="eef1e-129">7</span><span class="sxs-lookup"><span data-stu-id="eef1e-129">7</span></span>  
 <span data-ttu-id="eef1e-130">Em pausa.</span><span class="sxs-lookup"><span data-stu-id="eef1e-130">Paused.</span></span> <span data-ttu-id="eef1e-131">O serviço está em pausa.</span><span class="sxs-lookup"><span data-stu-id="eef1e-131">The service is paused.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eef1e-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="eef1e-132">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef1e-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eef1e-133">See Also</span></span>  
 <span data-ttu-id="eef1e-134">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="eef1e-134">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
