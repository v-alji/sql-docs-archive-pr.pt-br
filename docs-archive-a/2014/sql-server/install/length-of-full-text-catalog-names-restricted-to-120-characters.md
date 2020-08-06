---
title: Comprimento de nomes de catálogo de texto completo restritos a 120 caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs names
ms.assetid: 50633373-83f6-4ed9-99b9-71f92479a14f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fa9b06fa6fe4acd79782c19a8814357721e59c24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583978"
---
# <a name="length-of-full-text-catalog-names-restricted-to-120-characters"></a><span data-ttu-id="5b1c7-102">Comprimento dos nomes de catálogo de texto completo restrito a 120 caracteres</span><span class="sxs-lookup"><span data-stu-id="5b1c7-102">Length of full-text catalog names restricted to 120 characters</span></span>
  <span data-ttu-id="5b1c7-103">O comprimento dos nomes de catálogo de texto completo está restrito a 120 caracteres em vez de 128 caracteres como nas versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b1c7-103">The length of full-text catalog names is restricted to 120 characters, reduced from the 128 character restriction in previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="description"></a><span data-ttu-id="5b1c7-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b1c7-104">Description</span></span>  
 <span data-ttu-id="5b1c7-105">Essa alteração não afeta os nomes de catálogos existentes. Entretanto, scripts que criarem catálogos de texto completo com nomes de mais de 120 caracteres causarão um erro. </span><span class="sxs-lookup"><span data-stu-id="5b1c7-105">This change does not affect existing catalog names; however, scripts that create full-text catalogs with names longer than 120 characters result in an error.</span></span> <span data-ttu-id="5b1c7-106">Os nomes de catálogo são usados para gerar nomes de arquivos lógicos que correspondam aos catálogos.</span><span class="sxs-lookup"><span data-stu-id="5b1c7-106">The catalog names are used to generate logical file names that correspond to catalogs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="5b1c7-107">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="5b1c7-107">Corrective Action</span></span>  
 <span data-ttu-id="5b1c7-108">Modifique todos os scripts que criam catálogos de texto completo para assegurar que eles restrinjam os nomes de catálogo a 120 caracteres.</span><span class="sxs-lookup"><span data-stu-id="5b1c7-108">Modify all scripts that create full-text catalogs to ensure that they restrict catalog names to 120 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b1c7-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5b1c7-109">See Also</span></span>  
 [<span data-ttu-id="5b1c7-110">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="5b1c7-110">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
