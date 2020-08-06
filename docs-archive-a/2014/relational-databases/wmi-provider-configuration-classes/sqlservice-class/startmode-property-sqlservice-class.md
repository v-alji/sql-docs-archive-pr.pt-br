---
title: Propriedade StartMode (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartMode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartMode property
ms.assetid: c0c2c7f8-d4ae-44f2-ad8e-aecfcb7c2878
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bafffcc3c8f82f69896d0a22e9b0a9060e04cd10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681477"
---
# <a name="startmode-property-sqlservice-class"></a><span data-ttu-id="69b86-102">Propriedade StartMode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="69b86-102">StartMode Property (SqlService Class)</span></span>
  <span data-ttu-id="69b86-103">Obtém o modo de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="69b86-103">Gets the start mode of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69b86-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="69b86-104">Syntax</span></span>  
  
```  
  
object  
.StartMode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="69b86-105">Partes</span><span class="sxs-lookup"><span data-stu-id="69b86-105">Parts</span></span>  
 <span data-ttu-id="69b86-106">*object*</span><span class="sxs-lookup"><span data-stu-id="69b86-106">*object*</span></span>  
 <span data-ttu-id="69b86-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="69b86-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="69b86-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="69b86-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="69b86-109">Um valor uint32 que especifica o modo do serviço.</span><span class="sxs-lookup"><span data-stu-id="69b86-109">A uint32 value that specifies the mode of the service.</span></span>  
  
 <span data-ttu-id="69b86-110">Pode conter um dos valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="69b86-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="69b86-111">Inicialização</span><span class="sxs-lookup"><span data-stu-id="69b86-111">Boot</span></span>  
 <span data-ttu-id="69b86-112">Valor = 0.</span><span class="sxs-lookup"><span data-stu-id="69b86-112">Value = 0.</span></span> <span data-ttu-id="69b86-113">Serviço iniciado pelo carregador do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="69b86-113">Service started by the operating system loader.</span></span> <span data-ttu-id="69b86-114">Esta opção só é válida para serviços de driver.</span><span class="sxs-lookup"><span data-stu-id="69b86-114">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="69b86-115">Sistema</span><span class="sxs-lookup"><span data-stu-id="69b86-115">System</span></span>  
 <span data-ttu-id="69b86-116">Valor = 1.</span><span class="sxs-lookup"><span data-stu-id="69b86-116">Value = 1.</span></span> <span data-ttu-id="69b86-117">Serviço iniciado pelo método `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="69b86-117">Service started by the `IoInitSystem` method.</span></span> <span data-ttu-id="69b86-118">Esta opção só é válida para serviços de driver.</span><span class="sxs-lookup"><span data-stu-id="69b86-118">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="69b86-119">Automática</span><span class="sxs-lookup"><span data-stu-id="69b86-119">Automatic</span></span>  
 <span data-ttu-id="69b86-120">Valor = 2.</span><span class="sxs-lookup"><span data-stu-id="69b86-120">Value = 2.</span></span> <span data-ttu-id="69b86-121">Serviço a ser iniciado automaticamente pelo gerenciador de controle de serviço durante a inicialização do sistema.</span><span class="sxs-lookup"><span data-stu-id="69b86-121">Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="69b86-122">Manual</span><span class="sxs-lookup"><span data-stu-id="69b86-122">Manual</span></span>  
 <span data-ttu-id="69b86-123">Valor = 3.</span><span class="sxs-lookup"><span data-stu-id="69b86-123">Value = 3.</span></span> <span data-ttu-id="69b86-124">Serviço a ser iniciado pelo Gerenciador de Computador quando um processo chamar o método `StartService`.</span><span class="sxs-lookup"><span data-stu-id="69b86-124">Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="69b86-125">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="69b86-125">Disabled</span></span>  
 <span data-ttu-id="69b86-126">Valor = 4.</span><span class="sxs-lookup"><span data-stu-id="69b86-126">Value = 4.</span></span> <span data-ttu-id="69b86-127">Serviço não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="69b86-127">Service cannot be started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69b86-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="69b86-128">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b86-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="69b86-129">See Also</span></span>  
 <span data-ttu-id="69b86-130">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="69b86-130">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
