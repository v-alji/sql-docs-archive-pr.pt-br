---
title: FORE_COLOR e conteúdo de BACK_COLOR (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- FORE_COLOR contents
- backgrounds [MDX]
- cells [MDX]
- colors [MDX]
- storing cell color information
- cell backgrounds
- BACK_COLOR contents
ms.assetid: ff8f40cb-2ac4-4fc2-9761-7f1b14c17c8c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 748754ec3c90bb44392d7acb7de8f815be24086e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683768"
---
# <a name="fore_color-and-back_color-contents-mdx"></a><span data-ttu-id="b0afd-102">Conteúdo de FORE_COLOR e BACK_COLOR (MDX)</span><span class="sxs-lookup"><span data-stu-id="b0afd-102">FORE_COLOR and BACK_COLOR Contents (MDX)</span></span>
  <span data-ttu-id="b0afd-103">As propriedades de célula `FORE_COLOR` e `BACK_COLOR` armazenam informações sobre a cor do texto e do plano de fundo de uma célula, respectivamente, no formato RGB (vermelho, verde e azul) do sistema operacional Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b0afd-103">The `FORE_COLOR` and `BACK_COLOR` cell properties store color information for the text and the background of a cell, respectively, in the Microsoft Windows operating system red-green-blue (RGB) format.</span></span>  
  
 <span data-ttu-id="b0afd-104">O intervalo válido para uma cor RGB comum vai de zero (0) a 16.777.215 (&H00FFFFFF).</span><span class="sxs-lookup"><span data-stu-id="b0afd-104">The valid range for an ordinary RGB color is zero (0) to 16,777,215 (&H00FFFFFF).</span></span> <span data-ttu-id="b0afd-105">O byte mais elevado de um número desse intervalo é sempre igual a 0; os 3 bytes mais baixos, do menos importante para o mais importante, determinam o valor de vermelho, verde e azul, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b0afd-105">The high byte of a number in this range always equals 0; the lower 3 bytes, from least to most significant byte, determine the amount of red, green, and blue, respectively.</span></span> <span data-ttu-id="b0afd-106">Cada um dos componentes vermelho, verde e azul é representado por um número entre 0 e 255 (&HFF).</span><span class="sxs-lookup"><span data-stu-id="b0afd-106">The red, green, and blue components are each represented by a number between 0 and 255 (&HFF).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0afd-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0afd-107">See Also</span></span>  
 [<span data-ttu-id="b0afd-108">Usando propriedades da célula &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="b0afd-108">Using Cell Properties &#40;MDX&#41;</span></span>](mdx-cell-properties-using-cell-properties.md)  
  
  
