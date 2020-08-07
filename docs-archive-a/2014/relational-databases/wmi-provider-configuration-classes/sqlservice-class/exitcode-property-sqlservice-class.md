---
title: Propriedade ExitCode (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ExitCode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ExitCode property
ms.assetid: e6b8bff2-946f-4abe-bd50-1f7bb11fdddf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f7f5414afd8507a1fc9c592d6b8226692e9683a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571883"
---
# <a name="exitcode-property-sqlservice-class"></a><span data-ttu-id="e92d0-102">Propriedade ExitCode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="e92d0-102">ExitCode Property (SqlService Class)</span></span>
  <span data-ttu-id="e92d0-103">Obtém ou define o código de erro Win32 do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] que define problemas encontrados quando o serviço é iniciado ou interrompido.</span><span class="sxs-lookup"><span data-stu-id="e92d0-103">Gets or sets the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 error code that defines problems encountered when starting and stopping the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e92d0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e92d0-104">Syntax</span></span>  
  
```  
  
object  
.ExitCode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="e92d0-105">Partes</span><span class="sxs-lookup"><span data-stu-id="e92d0-105">Parts</span></span>  
 <span data-ttu-id="e92d0-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e92d0-106">*object*</span></span>  
 <span data-ttu-id="e92d0-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="e92d0-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e92d0-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="e92d0-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="e92d0-109">Um valor `uint32` que especifica o código de saída.</span><span class="sxs-lookup"><span data-stu-id="e92d0-109">A `uint32` value that specifies the exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e92d0-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="e92d0-110">Remarks</span></span>  
 <span data-ttu-id="e92d0-111">Esta propriedade é definida como ERROR_SERVICE_SPECIFIC_ERROR (1066) quando o erro for exclusivo ao serviço representado por essa classe.</span><span class="sxs-lookup"><span data-stu-id="e92d0-111">This property is set to ERROR_SERVICE_SPECIFIC_ERROR (1066) when the error is unique to the service represented by this class.</span></span> <span data-ttu-id="e92d0-112">O serviço define esse valor como NO_ERROR (0) quando está sendo executado e novamente, no encerramento normal.</span><span class="sxs-lookup"><span data-stu-id="e92d0-112">The service sets this value to NO_ERROR when running, and again upon normal termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92d0-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e92d0-113">See Also</span></span>  
 <span data-ttu-id="e92d0-114">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e92d0-114">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
