---
title: Gerar elementos para valores NULL com o parâmetro XSINIL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, null values
- null values [SQL Server], XML
- ELEMENTS directive
- XSINIL parameter
ms.assetid: 2dbc4e48-1cae-4d83-b371-3265da9687cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 602de12b5aa9be8997fbd49a2f23e0b73444aac0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686177"
---
# <a name="generate-elements-for-null-values-with-the-xsinil-parameter"></a><span data-ttu-id="d60bf-102">Gerar elementos para valores NULL com o parâmetro XSINIL</span><span class="sxs-lookup"><span data-stu-id="d60bf-102">Generate Elements for NULL Values with the XSINIL Parameter</span></span>
  <span data-ttu-id="d60bf-103">A diretiva **ELEMENTS** constrói XML no qual cada valor de coluna é mapeado para um elemento no XML.</span><span class="sxs-lookup"><span data-stu-id="d60bf-103">The **ELEMENTS** directive constructs XML in which each column value maps to an element in the XML.</span></span> <span data-ttu-id="d60bf-104">Se o valor da coluna for NULL, nenhum elemento será adicionado.</span><span class="sxs-lookup"><span data-stu-id="d60bf-104">If the column value is NULL, no element is added.</span></span> <span data-ttu-id="d60bf-105">Especificando o parâmetro **XSINIL** opcional na diretiva ELEMENTS é possível solicitar que um elemento também seja criado para o valor NULL.</span><span class="sxs-lookup"><span data-stu-id="d60bf-105">By specifying the optional **XSINIL** parameter on the ELEMENTS directive, you can request that an element also be created for the NULL value.</span></span> <span data-ttu-id="d60bf-106">Nesse caso, um elemento que tenha o atributo **xsi:nil** definido como TRUE é retornado para cada valor NULL da coluna.</span><span class="sxs-lookup"><span data-stu-id="d60bf-106">In this case, an element that has the **xsi:nil** attribute set to TRUE is returned for each NULL column value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60bf-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d60bf-107">See Also</span></span>  
 [<span data-ttu-id="d60bf-108">Usar o modo RAW com FOR XML</span><span class="sxs-lookup"><span data-stu-id="d60bf-108">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
