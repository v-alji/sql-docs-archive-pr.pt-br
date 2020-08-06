---
title: SqlToolsVSNativeHelpers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: d33cb556-0380-490a-9220-b74062dbd6d9
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 84f8a3a3408b68cb8c389b05b417f391a1f86c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686212"
---
# <a name="sqltoolsvsnativehelpers"></a><span data-ttu-id="84f86-102">SqlToolsVSNativeHelpers</span><span class="sxs-lookup"><span data-stu-id="84f86-102">SqlToolsVSNativeHelpers</span></span>
  <span data-ttu-id="84f86-103">Biblioteca que oferece suporte à funcionalidade do SQL Server no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="84f86-103">Library that supports SQL Server functionality in Visual Studio.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84f86-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="84f86-104">Syntax</span></span>  
  
```  
  
BOOL WINAPI DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID /*lpReserved*/)  
```  
  
## <a name="return-value"></a><span data-ttu-id="84f86-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="84f86-105">Return Value</span></span>  
 <span data-ttu-id="84f86-106">Um valor booliano `True` se o ponto de entrada da DLL for inicializado corretamente; do contrário, será `False`.</span><span class="sxs-lookup"><span data-stu-id="84f86-106">A Boolean value, `True` if the DLL entry point initialized properly, otherwise `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f86-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84f86-107">See Also</span></span>  
 [<span data-ttu-id="84f86-108">FrameWindowVisible</span><span class="sxs-lookup"><span data-stu-id="84f86-108">FrameWindowVisible</span></span>](sqltoolsvsnativehelpers-framewindowvisible.md)  
  
  
