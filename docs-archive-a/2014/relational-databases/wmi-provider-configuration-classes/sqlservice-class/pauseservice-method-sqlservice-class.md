---
title: Método PauseService (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PauseService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PauseService method
ms.assetid: 5c3a8feb-58b8-4385-b4c8-bf33cf4d276d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8286e123bbbc279ba461336c5716eeb208c5b238
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573846"
---
# <a name="pauseservice-method-sqlservice-class"></a><span data-ttu-id="8a2d9-102">Método PauseService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="8a2d9-102">PauseService Method (SqlService Class)</span></span>
  <span data-ttu-id="8a2d9-103">Tenta colocar o serviço no estado de pausado.</span><span class="sxs-lookup"><span data-stu-id="8a2d9-103">Attempts to place the service in the paused state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a2d9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8a2d9-104">Syntax</span></span>  
  
```  
  
object  
.PauseService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="8a2d9-105">Partes</span><span class="sxs-lookup"><span data-stu-id="8a2d9-105">Parts</span></span>  
 <span data-ttu-id="8a2d9-106">*object*</span><span class="sxs-lookup"><span data-stu-id="8a2d9-106">*object*</span></span>  
 <span data-ttu-id="8a2d9-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="8a2d9-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8a2d9-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="8a2d9-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="8a2d9-109">Um valor unit32, que é 0 se o serviço tiver sido interrompido com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="8a2d9-109">A uint32 value, which is 0 if the service was successfully stopped, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a2d9-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="8a2d9-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a2d9-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a2d9-111">See Also</span></span>  
 <span data-ttu-id="8a2d9-112">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8a2d9-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
