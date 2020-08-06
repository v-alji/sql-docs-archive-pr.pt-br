---
title: Método setstart (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStartMode Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStartMode method
ms.assetid: f6f198b4-f9a4-468c-8977-76462ef06e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a9b7310623f526d7b106485ed9681df3aa100129
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569255"
---
# <a name="setstartmode-method-sqlservice-class"></a><span data-ttu-id="92761-102">Método SetStartMode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="92761-102">SetStartMode Method (SqlService Class)</span></span>
  <span data-ttu-id="92761-103">Modifica o modo de início da instância do serviço.</span><span class="sxs-lookup"><span data-stu-id="92761-103">Modifies the start mode of the service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92761-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92761-104">Syntax</span></span>  
  
```  
  
object  
.SetStartMode(  
StartMode  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="92761-105">Partes</span><span class="sxs-lookup"><span data-stu-id="92761-105">Parts</span></span>  
 <span data-ttu-id="92761-106">*object*</span><span class="sxs-lookup"><span data-stu-id="92761-106">*object*</span></span>  
 <span data-ttu-id="92761-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="92761-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="92761-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="92761-108">Parameters</span></span>  
 <span data-ttu-id="92761-109">*StartMode*</span><span class="sxs-lookup"><span data-stu-id="92761-109">*StartMode*</span></span>  
 <span data-ttu-id="92761-110">Um valor `uint32` que especifica o modo de início da instância do serviço.</span><span class="sxs-lookup"><span data-stu-id="92761-110">A `uint32` value that specifies the start mode of the service instance.</span></span>  
  
 <span data-ttu-id="92761-111">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="92761-111">The valid values are as follows:</span></span>  
  
 <span data-ttu-id="92761-112">Valor = 0.</span><span class="sxs-lookup"><span data-stu-id="92761-112">Value = 0.</span></span> <span data-ttu-id="92761-113">Inicializar – o driver do dispositivo é iniciado pelo carregador do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="92761-113">Boot - Device driver started by the operating system loader.</span></span> <span data-ttu-id="92761-114">Esse valor só é válido para serviços do driver.</span><span class="sxs-lookup"><span data-stu-id="92761-114">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="92761-115">Valor = 1.</span><span class="sxs-lookup"><span data-stu-id="92761-115">Value = 1.</span></span> <span data-ttu-id="92761-116">Sistema - driver de dispositivo iniciado pelo método `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="92761-116">System - Device driver started by the `IoInitSystem` method.</span></span> <span data-ttu-id="92761-117">Esse valor só é válido para serviços do driver.</span><span class="sxs-lookup"><span data-stu-id="92761-117">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="92761-118">Valor = 2.</span><span class="sxs-lookup"><span data-stu-id="92761-118">Value = 2.</span></span> <span data-ttu-id="92761-119">Automático - serviço a ser iniciado automaticamente pelo gerenciador de controle de serviço durante a inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="92761-119">Automatic - Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="92761-120">Valor = 3.</span><span class="sxs-lookup"><span data-stu-id="92761-120">Value = 3.</span></span> <span data-ttu-id="92761-121">Manual - serviço a ser iniciado pelo Gerenciador de Computador quando um processo chamar o método `StartService`.</span><span class="sxs-lookup"><span data-stu-id="92761-121">Manual - Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="92761-122">Valor = 4.</span><span class="sxs-lookup"><span data-stu-id="92761-122">Value = 4.</span></span> <span data-ttu-id="92761-123">Desabilitado - serviço não pode mais ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="92761-123">Disabled - Service can no longer be started.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="92761-124">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="92761-124">Property Value/Return Value</span></span>  
 <span data-ttu-id="92761-125">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito ou 1 se a solicitação não tiver suporte.</span><span class="sxs-lookup"><span data-stu-id="92761-125">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="92761-126">Qualquer outro número indica um erro.</span><span class="sxs-lookup"><span data-stu-id="92761-126">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92761-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="92761-127">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92761-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92761-128">See Also</span></span>  
 <span data-ttu-id="92761-129">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="92761-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
