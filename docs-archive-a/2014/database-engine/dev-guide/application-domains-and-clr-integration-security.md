---
title: Domínios de aplicativo e segurança de integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- application domains [CLR integration]
ms.assetid: 54ee904e-e21a-4ee7-b4ad-a6f6f71bd473
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85d6e66b1d51cc9d7c5829b8e83c510bea750e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571552"
---
# <a name="application-domains-and-clr-integration-security"></a><span data-ttu-id="00ea8-102">Domínios do aplicativo e segurança da integração CLR</span><span class="sxs-lookup"><span data-stu-id="00ea8-102">Application Domains and CLR Integration Security</span></span>
  <span data-ttu-id="00ea8-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] carrega assemblies que pertencem ao mesmo proprietário no mesmo domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="00ea8-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] loads assemblies belonging to the same owner in the same application domain.</span></span> <span data-ttu-id="00ea8-104">Em virtude de um conjunto de assemblies estar sendo executado no mesmo domínio de aplicativo, os assemblies podem descobrir uns aos outros durante a execução usando as interfaces de programação de aplicativo de reflexão do .NET Framework ou outros meios, e podem chamá-los em forma de associação tardia.</span><span class="sxs-lookup"><span data-stu-id="00ea8-104">By virtue of a set of assemblies running in the same application domain, assemblies are able to discover each other at execution time using the.NET Framework reflection application programming interfaces or other means, and can call into them in late-bound fashion.</span></span> <span data-ttu-id="00ea8-105">Pelo fato dessas chamadas estarem ocorrendo nos assemblies que pertencem ao mesmo proprietário, não há permissões de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verificadas para elas.</span><span class="sxs-lookup"><span data-stu-id="00ea8-105">Because such calls are occurring against assemblies belonging to the same owner, there are no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions checked for these calls.</span></span> <span data-ttu-id="00ea8-106">O esquema de posicionamento de assemblies em domínios de aplicativo é projetado principalmente para obter escalabilidade, segurança e isolamento, podendo ser alterado em versões futuras.</span><span class="sxs-lookup"><span data-stu-id="00ea8-106">The placement scheme of assemblies in application domains is designed primarily to achieve scalability, security, and isolation goals, and can potentially change in future releases.</span></span> <span data-ttu-id="00ea8-107">Consequentemente, você não deve confiar na localização de assemblies no mesmo domínio do aplicativo através de mecanismos de associação tardia.</span><span class="sxs-lookup"><span data-stu-id="00ea8-107">Hence, you should not rely on finding assemblies in the same application domain through late-bound mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ea8-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="00ea8-108">See Also</span></span>  
 [<span data-ttu-id="00ea8-109">Segurança da integração CLR</span><span class="sxs-lookup"><span data-stu-id="00ea8-109">CLR Integration Security</span></span>](../../relational-databases/clr-integration/security/clr-integration-security.md)  
  
  
