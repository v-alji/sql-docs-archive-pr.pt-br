---
title: Definir propriedades de hierarquia de cubo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], multilevel
- hierarchies [Analysis Services], cubes
ms.assetid: 819d0a4e-7815-4332-a605-b07ca2ade6ac
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8903a49754357aad9cf24ee63fffa45fbf120e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679060"
---
# <a name="define-cube-hierarchy-properties"></a><span data-ttu-id="5675f-102">Definir propriedades de hierarquia de cubo</span><span class="sxs-lookup"><span data-stu-id="5675f-102">Define Cube Hierarchy Properties</span></span>
  <span data-ttu-id="5675f-103">As propriedades de hierarquia de cubo permitem a especificação de configurações exclusivas para hierarquias definidas pelo usuário em dimensões de cubo com base na mesma dimensão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5675f-103">Cube hierarchy properties enable you to specify unique settings for user-defined hierarchies in cube dimensions based on the same database dimension.</span></span> <span data-ttu-id="5675f-104">A tabela a seguir descreve as propriedades de uma hierarquia de cubo.</span><span class="sxs-lookup"><span data-stu-id="5675f-104">The following table describes the properties of a cube hierarchy.</span></span>  
  
|<span data-ttu-id="5675f-105">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5675f-105">Property</span></span>|<span data-ttu-id="5675f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="5675f-106">Description</span></span>|  
|--------------|-----------------|  
|`Enabled`|<span data-ttu-id="5675f-107">Determina se a hierarquia está habilitada para a dimensão de cubo.</span><span class="sxs-lookup"><span data-stu-id="5675f-107">Determines whether the hierarchy is enabled for the cube dimension.</span></span>|  
|`HierarchyID`|<span data-ttu-id="5675f-108">Contém o identificador exclusivo (ID) da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="5675f-108">Contains the unique identifier (ID) of the hierarchy.</span></span>|  
|`OptimizedState`|<span data-ttu-id="5675f-109">Determina o nível de otimização aplicado à hierarquia.</span><span class="sxs-lookup"><span data-stu-id="5675f-109">Determines the level of optimization that is applied to the hierarchy.</span></span> <span data-ttu-id="5675f-110">Essa propriedade pode ter os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5675f-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="5675f-111">`FullyOptimized`: a instância cria índices para a hierarquia a fim de melhorar o desempenho das consultas.</span><span class="sxs-lookup"><span data-stu-id="5675f-111">`FullyOptimized`: The instance builds indexes for the hierarchy to improve query performance.</span></span> <span data-ttu-id="5675f-112">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="5675f-112">This is the default value.</span></span><br /><br /> <span data-ttu-id="5675f-113">`NotOptimized`: a instância não compila índices adicionais.</span><span class="sxs-lookup"><span data-stu-id="5675f-113">`NotOptimized`: The instance does not build additional indexes.</span></span>|  
|`Visible`|<span data-ttu-id="5675f-114">Determina a visibilidade da hierarquia de cubo.</span><span class="sxs-lookup"><span data-stu-id="5675f-114">Determines the visibility of the cube hierarchy.</span></span> <span data-ttu-id="5675f-115">O valor padrão é `True`.</span><span class="sxs-lookup"><span data-stu-id="5675f-115">The default value is `True`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5675f-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5675f-116">See Also</span></span>  
 [<span data-ttu-id="5675f-117">Hierarquias do usuário</span><span class="sxs-lookup"><span data-stu-id="5675f-117">User Hierarchies</span></span>](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md)  
  
  
