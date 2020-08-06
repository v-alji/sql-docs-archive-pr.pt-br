---
title: Bancos de dados somente leitura não podem ser atualizados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- database cannot be upgraded
ms.assetid: 27964211-ea30-4390-b791-dcf225fb9ae7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ba48ed2bd80961a4949dc13f04fed0637ecc27ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581649"
---
# <a name="read-only-databases-cannot-be-upgraded"></a><span data-ttu-id="2dc8a-102">Bancos de dados somente leitura não podem ser atualizados</span><span class="sxs-lookup"><span data-stu-id="2dc8a-102">Read-only databases cannot be upgraded</span></span>
  <span data-ttu-id="2dc8a-103">O Supervisor de Atualização determinou que alguns bancos de dados nesta instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não podem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="2dc8a-103">Upgrade Advisor has determined that some databases on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be upgraded.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2dc8a-104">Componente</span><span class="sxs-lookup"><span data-stu-id="2dc8a-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="2dc8a-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="2dc8a-105">Description</span></span>  
 <span data-ttu-id="2dc8a-106">Um banco de dados somente leitura foi detectado.</span><span class="sxs-lookup"><span data-stu-id="2dc8a-106">A read-only database has been detected.</span></span> <span data-ttu-id="2dc8a-107">Para atualizar o banco de dados, a Instalação deve poder gravar no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2dc8a-107">To upgrade the database, Setup must be able to write to the database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2dc8a-108">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="2dc8a-108">Corrective Action</span></span>  
 <span data-ttu-id="2dc8a-109">Quando ninguém estiver usando o banco de dados, use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , ou a instrução ALTER DATABASE para alterar o banco de dados para leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="2dc8a-109">When no one is using the database, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or the ALTER DATABASE statement to change the database to read-write.</span></span> <span data-ttu-id="2dc8a-110">As instruções a seguir alteram o banco de dados para leitura e gravação:</span><span class="sxs-lookup"><span data-stu-id="2dc8a-110">The following statement changes the database to read-write.</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE <database name>  
SET READ_WRITE;  
GO  
```  
  
 <span data-ttu-id="2dc8a-111">Para obter mais informações sobre a instrução ALTER DATABASE, consulte o tópico ‘ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dc8a-111">For more information about the ALTER DATABASE statement, see the "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc8a-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2dc8a-112">See Also</span></span>  
 <span data-ttu-id="2dc8a-113">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2dc8a-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2dc8a-114">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="2dc8a-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
