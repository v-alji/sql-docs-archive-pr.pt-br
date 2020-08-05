---
title: Gerenciando caches (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, cache
- XML for Analysis, cache
- clearing cache
- cache [Analysis Services]
ms.assetid: afad5c39-d4c3-4307-b3b9-a06617da0028
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdc5bcd2e0500749edfa298a871b6fec7243ddfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572777"
---
# <a name="managing-caches-xmla"></a><span data-ttu-id="9bbfe-102">Gerenciando caches (XMLA)</span><span class="sxs-lookup"><span data-stu-id="9bbfe-102">Managing Caches (XMLA)</span></span>
  <span data-ttu-id="9bbfe-103">Você pode usar o comando [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) no XML for Analysis (XMLA) para limpar o cache de uma dimensão ou partição especificada.</span><span class="sxs-lookup"><span data-stu-id="9bbfe-103">You can use the [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) command in XML for Analysis (XMLA) to clear the cache of a specified dimension or partition.</span></span> <span data-ttu-id="9bbfe-104">Limpar as forças de cache [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para recriar o cache para esse objeto.</span><span class="sxs-lookup"><span data-stu-id="9bbfe-104">Clearing the cache forces [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to rebuild the cache for that object.</span></span>  
  
## <a name="specifying-objects"></a><span data-ttu-id="9bbfe-105">Especificando objetos</span><span class="sxs-lookup"><span data-stu-id="9bbfe-105">Specifying Objects</span></span>  
 <span data-ttu-id="9bbfe-106">A propriedade [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) do `ClearCache` comando pode conter uma referência de objeto somente para um dos objetos a seguir.</span><span class="sxs-lookup"><span data-stu-id="9bbfe-106">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `ClearCache` command can contain an object reference only for one of the following objects.</span></span> <span data-ttu-id="9bbfe-107">Haverá um erro se uma referência de objeto for destinada a um objeto diferente de um dos seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="9bbfe-107">An error occurs if an object reference is for an object other than one of following objects:</span></span>  
  
 <span data-ttu-id="9bbfe-108">Banco de dados</span><span class="sxs-lookup"><span data-stu-id="9bbfe-108">Database</span></span>  
 <span data-ttu-id="9bbfe-109">Limpa o cache para todas as dimensões e partições contidas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9bbfe-109">Clears the cache for all dimensions and partitions contained in the database.</span></span>  
  
 <span data-ttu-id="9bbfe-110">Dimensão</span><span class="sxs-lookup"><span data-stu-id="9bbfe-110">Dimension</span></span>  
 <span data-ttu-id="9bbfe-111">Limpa o cache para a dimensão especificada.</span><span class="sxs-lookup"><span data-stu-id="9bbfe-111">Clears the cache for the specified dimension.</span></span>  
  
 <span data-ttu-id="9bbfe-112">Cubo</span><span class="sxs-lookup"><span data-stu-id="9bbfe-112">Cube</span></span>  
 <span data-ttu-id="9bbfe-113">Limpa o cache para todas as partições contidas nos grupos de medidas para o cubo.</span><span class="sxs-lookup"><span data-stu-id="9bbfe-113">Clears the cache for all partitions contained in the measure groups for the cube.</span></span>  
  
 <span data-ttu-id="9bbfe-114">Grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="9bbfe-114">Measure group</span></span>  
 <span data-ttu-id="9bbfe-115">Limpa o cache para todas as partições contidas no grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="9bbfe-115">Clears the cache for all partitions contained in the measure group.</span></span>  
  
 <span data-ttu-id="9bbfe-116">Partition</span><span class="sxs-lookup"><span data-stu-id="9bbfe-116">Partition</span></span>  
 <span data-ttu-id="9bbfe-117">Limpa o cache para a partição especificada.</span><span class="sxs-lookup"><span data-stu-id="9bbfe-117">Clears the cache for the specified partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbfe-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9bbfe-118">See Also</span></span>  
 [<span data-ttu-id="9bbfe-119">Desenvolvendo com XMLA no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9bbfe-119">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
