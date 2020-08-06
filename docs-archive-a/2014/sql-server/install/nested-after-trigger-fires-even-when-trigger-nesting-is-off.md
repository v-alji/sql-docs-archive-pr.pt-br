---
title: Gatilho AFTER é acionado mesmo quando o aninhamento de gatilho está desativado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, nested
- nested triggers option
- triggers [SQL Server], nested
ms.assetid: 94d72960-676e-40d9-81bc-08bffe778110
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f91c04e8d69880b451c1479e2907cd1910e8f9c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686054"
---
# <a name="nested-after-trigger-fires-even-when-trigger-nesting-is-off"></a><span data-ttu-id="46b6e-102">Gatilho AFTER aninhado dispara até mesmo quando aninhamento de gatilho está definido como OFF</span><span class="sxs-lookup"><span data-stu-id="46b6e-102">Nested AFTER trigger fires even when trigger nesting is OFF</span></span>
  <span data-ttu-id="46b6e-103">O Supervisor de Atualização detectou um gatilho AFTER aninhado dentro de um gatilho INSTEAD OF que está defino em uma ou mais tabelas.</span><span class="sxs-lookup"><span data-stu-id="46b6e-103">Upgrade Advisor detected an AFTER trigger nested inside an INSTEAD OF trigger that is defined on one or more tables.</span></span> <span data-ttu-id="46b6e-104">Gatilhos AFTER aninhados podem disparar quando a opção de configuração do servidor `nested triggers` está definida como 0.</span><span class="sxs-lookup"><span data-stu-id="46b6e-104">Nested AFTER triggers may fire even when the `nested triggers` server configuration option is set to 0.</span></span>  
  
## <a name="component"></a><span data-ttu-id="46b6e-105">Componente</span><span class="sxs-lookup"><span data-stu-id="46b6e-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="46b6e-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="46b6e-106">Description</span></span>  
 <span data-ttu-id="46b6e-107">O primeiro gatilho AFTER aninhado dentro de um gatilho INSTEAD OF é disparado mesmo se a opção de configuração do servidor `nested triggers` estiver definida como 0.</span><span class="sxs-lookup"><span data-stu-id="46b6e-107">The first AFTER trigger nested inside an INSTEAD OF trigger fires even if the `nested triggers` server configuration option is set to 0.</span></span> <span data-ttu-id="46b6e-108">Porém, nessa configuração, gatilhos AFTER subsequentes não disparam.</span><span class="sxs-lookup"><span data-stu-id="46b6e-108">However, under this setting, subsequent AFTER triggers do not fire.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="46b6e-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="46b6e-109">Corrective Action</span></span>  
 <span data-ttu-id="46b6e-110">Revise seus aplicativos para verificar se há gatilhos aninhados. Verifique se os aplicativos ainda estão de acordo com as regras de negócio com relação a esse novo comportamento quando a opção de configuração do servidor `nested triggers` está definida como 0 e faça as modificações apropriadas.</span><span class="sxs-lookup"><span data-stu-id="46b6e-110">Review your applications for nested triggers to determine whether the applications still comply with your business rules with regard to this new behavior when the `nested triggers` server configuration option is set to 0, and then make appropriate modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b6e-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46b6e-111">See Also</span></span>  
 <span data-ttu-id="46b6e-112">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="46b6e-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="46b6e-113">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="46b6e-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
