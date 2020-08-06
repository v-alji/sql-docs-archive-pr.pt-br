---
title: Remover operações DDL nas tabelas inseridas e excluídas dentro de gatilhos DML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- data definition language [SQL Server]
- DDL statements [SQL Server]
- DML triggers, removing DDL operations
ms.assetid: e49ba7d5-787f-4052-b985-b699195d982b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 61f7ab78b5ab6251b7f27401d36423ec27141c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683338"
---
# <a name="remove-ddl-operations-on-the-inserted-and-deleted-tables-inside-dml-triggers"></a><span data-ttu-id="3468a-102">Remover operações DDL de tabelas inseridas e excluídas em gatilhos DML</span><span class="sxs-lookup"><span data-stu-id="3468a-102">Remove DDL operations on the inserted and deleted tables inside DML triggers</span></span>
  <span data-ttu-id="3468a-103">Instruções DDL (linguagem de definição de dados), como CREATE INDEX, não podem ser executadas nas tabelas inseridas e excluídas dentro de gatilhos DML.</span><span class="sxs-lookup"><span data-stu-id="3468a-103">Data definition language (DDL) statements, such as CREATE INDEX, cannot be performed on the inserted and deleted tables inside DML triggers.</span></span> <span data-ttu-id="3468a-104">Algumas instruções DDL em tabelas inseridas e excluídas eram permitidas em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3468a-104">Some DDL statements on the inserted and deleted tables are permitted in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3468a-105">Para obter mais informações, consulte ‘Usando as tabelas inseridas e excluídas’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3468a-105">For more information, see "Using the inserted and deleted Tables" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3468a-106">Componente</span><span class="sxs-lookup"><span data-stu-id="3468a-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="3468a-107">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="3468a-107">Corrective Action</span></span>  
 <span data-ttu-id="3468a-108">Remova quaisquer operações DDL que são executadas nas tabelas inseridas e excluídas em gatilhos DML.</span><span class="sxs-lookup"><span data-stu-id="3468a-108">Remove any DDL operations that are performed on the inserted and deleted tables inside DML triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3468a-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3468a-109">See Also</span></span>  
 <span data-ttu-id="3468a-110">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3468a-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3468a-111">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="3468a-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
