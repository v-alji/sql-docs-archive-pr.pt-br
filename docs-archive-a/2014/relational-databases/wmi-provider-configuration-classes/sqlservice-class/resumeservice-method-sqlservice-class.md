---
title: Método ResumeService (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ResumeService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ResumeService method
ms.assetid: 0b0a5f08-b95e-4626-bf81-309da7a0aacd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 53d07c8697c6303bc371f442745e2d1864682e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572963"
---
# <a name="resumeservice-method-sqlservice-class"></a><span data-ttu-id="22bf5-102">Método ResumeService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="22bf5-102">ResumeService Method (SqlService Class)</span></span>
  <span data-ttu-id="22bf5-103">Tenta colocar o serviço no estado de reiniciado.</span><span class="sxs-lookup"><span data-stu-id="22bf5-103">Attempts to place the service in the resumed state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22bf5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="22bf5-104">Syntax</span></span>  
  
```  
  
object  
.ResumeService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="22bf5-105">Partes</span><span class="sxs-lookup"><span data-stu-id="22bf5-105">Parts</span></span>  
 <span data-ttu-id="22bf5-106">*object*</span><span class="sxs-lookup"><span data-stu-id="22bf5-106">*object*</span></span>  
 <span data-ttu-id="22bf5-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="22bf5-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="22bf5-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="22bf5-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="22bf5-109">Um valor uint32, que é 0 se a solicitação `ResumeService` tiver sido aceita, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="22bf5-109">A uint32 value, which is 0 if the `ResumeService` request was accepted, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22bf5-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="22bf5-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22bf5-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22bf5-111">See Also</span></span>  
 <span data-ttu-id="22bf5-112">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="22bf5-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  