---
title: As dicas de tabela nas definições de exibição indexada são ignoradas no modo de compatibilidade 80 e não são permitidas no modo 90 ou posterior | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- query hints [SQL Server]
- indexed views [SQL Server], query hints
ms.assetid: 405dfcff-a3a6-4e6d-a53a-ed77bbacdd13
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cf3cb2b06dc477d93c8fd42312b4835ded42afb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683303"
---
# <a name="table-hints-in-indexed-view-definitions-are-ignored-in-80-compatibility-mode-and-are-not-allowed-in-90-mode-or-later"></a><span data-ttu-id="00e91-102">Dicas de tabelas em definições de exibição indexada são ignoradas no modo de compatibilidade 80 e não são permitidas no modo de compatibilidade 90 ou posterior</span><span class="sxs-lookup"><span data-stu-id="00e91-102">Table hints in indexed view definitions are ignored in 80 compatibility mode and are not allowed in 90 mode or later</span></span>
  <span data-ttu-id="00e91-103">As dicas de tabelas presentes em definições de exibição indexadas não são permitidas no modo de compatibilidade 90 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="00e91-103">Table hints in the definitions of indexed views are not permitted in the compatibility mode of 90 or later.</span></span> <span data-ttu-id="00e91-104">Para obter mais informações, consulte os seguintes tópicos nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: ‘Projetando exibições indexadas’, ‘Criando exibições indexadas’ e ‘Dica de consulta ([!INCLUDE[tsql](../../includes/tsql-md.md)])’.</span><span class="sxs-lookup"><span data-stu-id="00e91-104">For more information, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online: "Designing Indexed Views," "Creating Indexed Views," and "Query Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])."</span></span>  
  
## <a name="component"></a><span data-ttu-id="00e91-105">Componente</span><span class="sxs-lookup"><span data-stu-id="00e91-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="00e91-106">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="00e91-106">Corrective Action</span></span>  
 <span data-ttu-id="00e91-107">As dicas de tabelas devem ser removidas das definições de exibição indexadas.</span><span class="sxs-lookup"><span data-stu-id="00e91-107">Table hints must be removed from the definitions of indexed views.</span></span> <span data-ttu-id="00e91-108">Independentemente do modo de compatibilidade usado, recomendamos que você teste o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="00e91-108">Regardless of which compatibility mode is used, we recommend that you test the application.</span></span> <span data-ttu-id="00e91-109">Ao fazer isso, você se certifica de que ele está executando de forma adequada durante a criação, a atualização e o acesso a exibições indexadas, inclusive quando há correspondência entre exibições indexadas e consultas.</span><span class="sxs-lookup"><span data-stu-id="00e91-109">By testing the application, you can make sure it performs as expected when indexed views are created, updated, and accessed, including when indexed views are matched to queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e91-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="00e91-110">See Also</span></span>  
 <span data-ttu-id="00e91-111">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="00e91-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="00e91-112">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="00e91-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
