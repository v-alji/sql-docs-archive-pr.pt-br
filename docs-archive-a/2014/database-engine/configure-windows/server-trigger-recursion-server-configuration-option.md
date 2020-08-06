---
title: Opção de configuração do servidor server trigger recursion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- recursive triggers [SQL Server]
- triggers [SQL Server], recursive
- server trigger recursion option
ms.assetid: da4c25f5-d04c-4951-a3db-409e71a1b468
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 23a4997bd1a6f8b2c04af34d5cdc3229575901a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684891"
---
# <a name="server-trigger-recursion-server-configuration-option"></a><span data-ttu-id="a101e-102">Opção de configuração de servidor server trigger recursion</span><span class="sxs-lookup"><span data-stu-id="a101e-102">server trigger recursion Server Configuration Option</span></span>
  <span data-ttu-id="a101e-103">Use a opção **server trigger recursion** para especificar se os gatilhos de nível de servidor podem ser acionados recursivamente.</span><span class="sxs-lookup"><span data-stu-id="a101e-103">Use the **server trigger recursion** option to specify whether to allow server-level triggers to fire recursively.</span></span> <span data-ttu-id="a101e-104">Quando esta opção for definida como 1 (ON), será permitido que os gatilhos de nível de servidor sejam acionados recursivamente.</span><span class="sxs-lookup"><span data-stu-id="a101e-104">When this option is set to 1 (ON), server-level triggers will be allowed to fire recursively.</span></span> <span data-ttu-id="a101e-105">Quando ela for definida como 0 (OFF), os gatilhos de nível de servidor não poderão ser acionados recursivamente.</span><span class="sxs-lookup"><span data-stu-id="a101e-105">When set to 0 (OFF), server-level triggers cannot be fired recursively.</span></span> <span data-ttu-id="a101e-106">Somente a recursão direta é evitada quando a opção server trigger recursion é definida como 0 (OFF).</span><span class="sxs-lookup"><span data-stu-id="a101e-106">Only direct recursion is prevented when the server trigger recursion option is set to 0 (OFF).</span></span> <span data-ttu-id="a101e-107">(Para desabilitar a recursão indireta, defina a opção **nested triggers** como 0.) O valor padrão desta opção é 1 (ON).</span><span class="sxs-lookup"><span data-stu-id="a101e-107">(To disable indirect recursion, set the **nested triggers** option to 0.) The default value for this option is 1 (ON).</span></span> <span data-ttu-id="a101e-108">A configuração entra em vigor imediatamente (sem a reinicialização do servidor).</span><span class="sxs-lookup"><span data-stu-id="a101e-108">The setting takes effect immediately (without a server restart).</span></span>  
  
 <span data-ttu-id="a101e-109">Para obter mais informações, consulte [Criar gatilhos aninhados](../../relational-databases/triggers/create-nested-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="a101e-109">For more information, see [Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a101e-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a101e-110">See Also</span></span>  
 <span data-ttu-id="a101e-111">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a101e-111">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a101e-112">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a101e-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="a101e-113">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a101e-113">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
