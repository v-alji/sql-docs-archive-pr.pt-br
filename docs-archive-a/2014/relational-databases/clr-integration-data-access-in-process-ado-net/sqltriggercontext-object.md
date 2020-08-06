---
title: Objeto SqlTriggerContext | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlTriggerContext object
- triggers [CLR integration]
- context [CLR integration]
ms.assetid: 472a2d0b-64ae-4877-8f11-a5620aa698b7
author: rothja
ms.author: jroth
ms.openlocfilehash: f7eae3d290a70bedee0ed9badf9e6d0503caa2bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685801"
---
# <a name="sqltriggercontext-object"></a><span data-ttu-id="113e0-102">Objeto SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="113e0-102">SqlTriggerContext Object</span></span>
  <span data-ttu-id="113e0-103">A classe `SqlTriggerContext` fornece informações de contexto sobre o gatilho.</span><span class="sxs-lookup"><span data-stu-id="113e0-103">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="113e0-104">Essas informações contextuais incluem o tipo de ação que causou o acionamento do gatilho, as colunas que foram modificadas em uma operação UPDATE, e, no caso de um gatilho DDL (data definition language), uma estrutura XML `EventData` que descreve a operação de gatilho.</span><span class="sxs-lookup"><span data-stu-id="113e0-104">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a data definition language (DDL) trigger, an XML `EventData` structure that describes the triggering operation.</span></span> <span data-ttu-id="113e0-105">Para obter mais informações e exemplos de como usar a `SqlTriggerContext` classe, consulte [gatilhos CLR](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="113e0-105">For more information and examples of how to use the `SqlTriggerContext` class, see [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span>  
  
 <span data-ttu-id="113e0-106">Para obter mais informações, consulte a documentação sobre referência de classe do `Microsoft.SqlServer.Server.SqlTriggerContext` no .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="113e0-106">For more information, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the .NET Framework SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113e0-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="113e0-107">See Also</span></span>  
 <span data-ttu-id="113e0-108">[Gatilhos CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="113e0-108">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="113e0-109">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="113e0-109">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
