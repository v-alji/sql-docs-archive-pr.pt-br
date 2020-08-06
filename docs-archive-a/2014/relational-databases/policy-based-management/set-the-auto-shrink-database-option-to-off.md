---
title: Definir a opção de banco de dados AUTO_SHRINK como OFF | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 16403850-d745-4754-b84f-5f01aaecd24e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 42d79ed13a691c3d39a28e7ab35a740a9f613fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685068"
---
# <a name="set-the-auto_shrink-database-option-to-off"></a><span data-ttu-id="20be0-102">Definir a opção do banco de dados AUTO_SHRINK como OFF</span><span class="sxs-lookup"><span data-stu-id="20be0-102">Set the AUTO_SHRINK Database Option to OFF</span></span>
  <span data-ttu-id="20be0-103">Esta regra verifica se a opção de banco de dados AUTO_SHRINK é definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="20be0-103">This rule checks whether the AUTO_SHRINK database option is set to OFF.</span></span> <span data-ttu-id="20be0-104">Reduzir e expandir um banco de dados com frequência pode causar a fragmentação física.</span><span class="sxs-lookup"><span data-stu-id="20be0-104">Frequently shrinking and expanding a database can lead to physical fragmentation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="20be0-105">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="20be0-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="20be0-106">Defina a opção do banco de dados AUTO_SHRINK como OFF.</span><span class="sxs-lookup"><span data-stu-id="20be0-106">Set the AUTO_SHRINK database option to OFF.</span></span> <span data-ttu-id="20be0-107">Se você souber que o espaço que está recuperando não será necessário no futuro, poderá recuperá-lo reduzindo o banco de dados manualmente.</span><span class="sxs-lookup"><span data-stu-id="20be0-107">If you know that the space that you are reclaiming will not be needed in the future, you can reclaim the space by manually shrinking the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="20be0-108">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="20be0-108">For More Information</span></span>  
 <span data-ttu-id="20be0-109">Artigo da Base de Conhecimentos Microsoft [315512](https://go.microsoft.com/fwlink/?linkid=117750)</span><span class="sxs-lookup"><span data-stu-id="20be0-109">Microsoft Knowledge Base article [315512](https://go.microsoft.com/fwlink/?linkid=117750)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20be0-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="20be0-110">See Also</span></span>  
 [<span data-ttu-id="20be0-111">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="20be0-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
