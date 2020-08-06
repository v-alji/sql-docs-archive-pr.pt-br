---
title: Propriedade ErrorControl (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ErrorControl Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ErrorControl property
ms.assetid: cbb1e0fa-5bfc-4b1b-a6ed-f7d5cfad4d73
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73c726af514f2880484cf927282fc0e007f07e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684122"
---
# <a name="errorcontrol-property-sqlservice-class"></a><span data-ttu-id="1e42b-102">Propriedade ErrorControl (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="1e42b-102">ErrorControl Property (SqlService Class)</span></span>
  <span data-ttu-id="1e42b-103">Obtém ou define a gravidade do erro se o serviço não for iniciado durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="1e42b-103">Gets or sets the severity of the error if the service fails to start during startup.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e42b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1e42b-104">Syntax</span></span>  
  
```  
  
object  
.ErrorControl [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="1e42b-105">Partes</span><span class="sxs-lookup"><span data-stu-id="1e42b-105">Parts</span></span>  
 <span data-ttu-id="1e42b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1e42b-106">*object*</span></span>  
 <span data-ttu-id="1e42b-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="1e42b-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1e42b-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="1e42b-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="1e42b-109">Um valor da cadeia de caracteres que especifica a gravidade de erro informada se o serviço falhar durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="1e42b-109">A string value that specifies the error severity reported if the service fails during startup.</span></span> <span data-ttu-id="1e42b-110">A tabela a seguir mostra os valores possíveis.</span><span class="sxs-lookup"><span data-stu-id="1e42b-110">The following table shows the possible values.</span></span>  
  
 <span data-ttu-id="1e42b-111">Ignorar</span><span class="sxs-lookup"><span data-stu-id="1e42b-111">Ignore</span></span>  
 <span data-ttu-id="1e42b-112">O usuário não é notificado.</span><span class="sxs-lookup"><span data-stu-id="1e42b-112">User is not notified.</span></span>  
  
 <span data-ttu-id="1e42b-113">Normal</span><span class="sxs-lookup"><span data-stu-id="1e42b-113">Normal</span></span>  
 <span data-ttu-id="1e42b-114">O usuário é notificado.</span><span class="sxs-lookup"><span data-stu-id="1e42b-114">User is notified.</span></span>  
  
 <span data-ttu-id="1e42b-115">Severo</span><span class="sxs-lookup"><span data-stu-id="1e42b-115">Severe</span></span>  
 <span data-ttu-id="1e42b-116">Sistema é reiniciado com a última configuração bem-sucedida conhecida.</span><span class="sxs-lookup"><span data-stu-id="1e42b-116">System is restarted with the last-known-good configuration.</span></span>  
  
 <span data-ttu-id="1e42b-117">Crítico</span><span class="sxs-lookup"><span data-stu-id="1e42b-117">Critical</span></span>  
 <span data-ttu-id="1e42b-118">O sistema tenta reiniciar com uma configuração adequada.</span><span class="sxs-lookup"><span data-stu-id="1e42b-118">System attempts to restart with a good configuration.</span></span>  
  
 <span data-ttu-id="1e42b-119">Unknown (desconhecido)</span><span class="sxs-lookup"><span data-stu-id="1e42b-119">Unknown</span></span>  
 <span data-ttu-id="1e42b-120">A gravidade é desconhecida.</span><span class="sxs-lookup"><span data-stu-id="1e42b-120">The severity is unknown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e42b-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="1e42b-121">Remarks</span></span>  
 <span data-ttu-id="1e42b-122">O valor indicará a ação tomada pelo programa de inicialização se ocorrer uma falha.</span><span class="sxs-lookup"><span data-stu-id="1e42b-122">The value indicates the action taken by the startup program if a failure occurs.</span></span> <span data-ttu-id="1e42b-123">Todos os erros são anotados pelo sistema de computador.</span><span class="sxs-lookup"><span data-stu-id="1e42b-123">All errors are logged by the computer system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e42b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e42b-124">See Also</span></span>  
 <span data-ttu-id="1e42b-125">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1e42b-125">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
