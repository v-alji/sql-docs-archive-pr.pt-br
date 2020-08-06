---
title: Verificar se todos os grupos de filesão graváveis durante o processo de atualização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filegroups [SQL Server], writeable
- writeable filegroups [SQL Server]
ms.assetid: 2985efc1-4b14-46c3-abbd-a656b159f23c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8146efb876bf97c36c549a2b58d104592df611e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686020"
---
# <a name="verify-all-filegroups-are-writeable-during-the-upgrade-process"></a><span data-ttu-id="02b5a-102">Verificar se todos os grupos de arquivos podem ser gravados durante o processo de atualização</span><span class="sxs-lookup"><span data-stu-id="02b5a-102">Verify all filegroups are writeable during the upgrade process</span></span>
  <span data-ttu-id="02b5a-103">O Supervisor de Atualização detectou um banco de dados que tem um ou mais grupos de arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="02b5a-103">Upgrade Advisor detected a database that has one or more read-only filegroups.</span></span> <span data-ttu-id="02b5a-104">Todos os bancos de dados na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devem ter os grupos de arquivos definidos como READ_WRITE antes de atualizar.</span><span class="sxs-lookup"><span data-stu-id="02b5a-104">All databases in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must have filegroups set to READ_WRITE before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="02b5a-105">Componente</span><span class="sxs-lookup"><span data-stu-id="02b5a-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="02b5a-106">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="02b5a-106">Corrective Action</span></span>  
 <span data-ttu-id="02b5a-107">Use ALTER DATABASE para definir o grupo de arquivos como READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="02b5a-107">Use ALTER DATABASE to set the filegroup to READ_WRITE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b5a-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="02b5a-108">See Also</span></span>  
 <span data-ttu-id="02b5a-109">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="02b5a-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="02b5a-110">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="02b5a-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
