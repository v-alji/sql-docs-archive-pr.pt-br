---
title: Definir o grau máximo da opção de paralelismo para obter o desempenho ideal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: ec908006-67ae-4674-9a61-25ea741d6197
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3043a656cbe1ac1ec40f0d0a67b6eac057005af4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685070"
---
# <a name="set-the-max-degree-of-parallelism-option-for-optimal-performance"></a><span data-ttu-id="872c4-102">Definir o grau máximo da opção de paralelismo para obtenção do desempenho ideal</span><span class="sxs-lookup"><span data-stu-id="872c4-102">Set the Max Degree of Parallelism Option for Optimal Performance</span></span>
  <span data-ttu-id="872c4-103">Esta regra determina se a opção grau máximo de paralelismo (MAXDOP) pode obter um valor maior que 8.</span><span class="sxs-lookup"><span data-stu-id="872c4-103">This rule determines whether the max degree of parallelism (MAXDOP) option for a value greater than 8.</span></span> <span data-ttu-id="872c4-104">A configuração desta opção com um valor maior frequentemente causa o consumo indesejável de recursos e a degradação do desempenho.</span><span class="sxs-lookup"><span data-stu-id="872c4-104">Setting this option to a larger value often causes unwanted resource consumption and performance degradation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="872c4-105">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="872c4-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="872c4-106">Defina a opção grau máximo de paralelismo como 8 ou menos usando sp_configure.</span><span class="sxs-lookup"><span data-stu-id="872c4-106">Set the max degree of parallelism option to 8 or less by using sp_configure.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="872c4-107">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="872c4-107">For More Information</span></span>  
 [<span data-ttu-id="872c4-108">Artigo 329204 da Base de Dados de Conhecimento Microsoft</span><span class="sxs-lookup"><span data-stu-id="872c4-108">Microsoft Knowledge Base article 329204</span></span>](https://go.microsoft.com/fwlink/?linkid=117786)  
  
 [<span data-ttu-id="872c4-109">Configurar a opção de configuração de servidor max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="872c4-109">Configure the max degree of parallelism Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)  
  
 [<span data-ttu-id="872c4-110">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="872c4-110">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
