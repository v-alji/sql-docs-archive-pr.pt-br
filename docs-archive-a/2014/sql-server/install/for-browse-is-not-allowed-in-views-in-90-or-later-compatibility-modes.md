---
title: FOR BROWSE não é permitido em exibições nos modos de compatibilidade 90 ou posteriores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], FOR BROWSE clause
- FOR BROWSE clause
ms.assetid: 8f49b1c1-d877-4c46-b988-f8cdd8ac0925
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 251e0ae2ff6f19dfcff3b0f8056f6697c1bfc40d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576179"
---
# <a name="for-browse-is-not-allowed-in-views-in-90-or-later-compatibility-modes"></a><span data-ttu-id="4e69b-102">FOR BROWSE não é permitido em exibições nos modos de compatibilidade 90 ou posterior</span><span class="sxs-lookup"><span data-stu-id="4e69b-102">FOR BROWSE is not allowed in views in 90 or later compatibility modes</span></span>
  <span data-ttu-id="4e69b-103">O Supervisor de Atualização detectou o uso da cláusula FOR BROWSE em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="4e69b-103">Upgrade Advisor detected the use of the FOR BROWSE clause in a view.</span></span> <span data-ttu-id="4e69b-104">A cláusula FOR BROWSE é permitida (e ignorada) em exibições quando o modo de compatibilidade do banco de dados está definido como 80.</span><span class="sxs-lookup"><span data-stu-id="4e69b-104">The FOR BROWSE clause is allowed (and ignored) in views when the database compatibility mode is set to 80.</span></span> <span data-ttu-id="4e69b-105">Entretanto, essa cláusula não é permitida em exibições quando o modo de compatibilidade do banco de dados está definido como 90 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4e69b-105">The FOR BROWSE clause is not allowed in views when the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4e69b-106">Componente</span><span class="sxs-lookup"><span data-stu-id="4e69b-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="4e69b-107">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="4e69b-107">Corrective Action</span></span>  
 <span data-ttu-id="4e69b-108">Quando você faz a atualização, os bancos de dados de usuários mantêm seus modos de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="4e69b-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="4e69b-109">Antes de alterar o modo de compatibilidade do banco de dados para 90 ou posterior, remova a cláusula FOR BROWSE das definições de exibição.</span><span class="sxs-lookup"><span data-stu-id="4e69b-109">Before you change the database compatibility mode to 90 or later, remove the FOR BROWSE clause from view definitions.</span></span> <span data-ttu-id="4e69b-110">Para obter mais informações, consulte ‘sp_dbcmptlevel’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e69b-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e69b-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e69b-111">See Also</span></span>  
 <span data-ttu-id="4e69b-112">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4e69b-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4e69b-113">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="4e69b-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
