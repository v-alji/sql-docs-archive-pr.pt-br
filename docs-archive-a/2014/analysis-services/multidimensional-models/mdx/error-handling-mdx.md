---
title: Tratamento de erro (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], exceptions
- exceptions [MDX]
ms.assetid: bc6ff0af-9fe6-44d6-bc3c-801d71ea41a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 357194b9f789fdeacfb65ce3c894d4747867eafb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581564"
---
# <a name="error-handling-mdx"></a><span data-ttu-id="6b0de-102">Tratamento de erros (MDX)</span><span class="sxs-lookup"><span data-stu-id="6b0de-102">Error Handling (MDX)</span></span>
  <span data-ttu-id="6b0de-103">Cada cubo pode controlar como são tratados os erros em um script MDX.</span><span class="sxs-lookup"><span data-stu-id="6b0de-103">Each cube can control how errors within a Multidimensional Expressions (MDX) script are handled.</span></span> <span data-ttu-id="6b0de-104">O tratamento de erro é feito pelo enumerador `ScriptErrorHandlingMode`.</span><span class="sxs-lookup"><span data-stu-id="6b0de-104">Error handling is done through the `ScriptErrorHandlingMode` enumerator.</span></span> <span data-ttu-id="6b0de-105">Os valores possíveis para esse enumerador são:</span><span class="sxs-lookup"><span data-stu-id="6b0de-105">The possible values for this enumerator are:</span></span>  
  
 `IgnoreNone`  
 <span data-ttu-id="6b0de-106">Faz com que o servidor gere um erro quando [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] encontra qualquer erro no script MDX.</span><span class="sxs-lookup"><span data-stu-id="6b0de-106">Causes the server to raise an error when [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] finds any error in the MDX script.</span></span>  
  
 `IgnoreAll`  
 <span data-ttu-id="6b0de-107">Faz com que o servidor ignore todos os comandos do script MDX que contém um erro, incluindo erros de sintaxe, de resolução de nomes, entre outros.</span><span class="sxs-lookup"><span data-stu-id="6b0de-107">Causes the server to ignore all commands in the MDX script that contain an error, including syntax errors, name resolution errors, and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b0de-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6b0de-108">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  
