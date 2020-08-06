---
title: Fazer failover manual de uma sessão de espelhamento de banco de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 36218d61-b5f5-4194-905a-608e0e903db4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c04ea4908ccbc4cfe4f6bb3606347dd444ef416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570198"
---
# <a name="manually-fail-over-a-database-mirroring-session-transact-sql"></a><span data-ttu-id="bc867-102">Executar failover manualmente em uma sessão de espelhamento de banco de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc867-102">Manually Fail Over a Database Mirroring Session (Transact-SQL)</span></span>
  <span data-ttu-id="bc867-103">Quando o banco de dados espelho for sincronizado (ou seja, quando o banco de dados estiver no estado SYNCHRONIZED), o proprietário do banco de dados poderá iniciar failover manual para o servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="bc867-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span> <span data-ttu-id="bc867-104">O failover manual só pode ser iniciado do servidor principal.</span><span class="sxs-lookup"><span data-stu-id="bc867-104">Manual failover can be initiated only from the principal server.</span></span>  
  
### <a name="to-manually-fail-over-a-database-mirroring-session"></a><span data-ttu-id="bc867-105">Para efetuar manualmente o failover de uma sessão de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="bc867-105">To manually fail over a database mirroring session</span></span>  
  
1.  <span data-ttu-id="bc867-106">Conecte-se ao servidor principal.</span><span class="sxs-lookup"><span data-stu-id="bc867-106">Connect to the principal server.</span></span>  
  
2.  <span data-ttu-id="bc867-107">Defina o contexto do banco de dados como o banco de dados **mestre** :</span><span class="sxs-lookup"><span data-stu-id="bc867-107">Set the database context to the **master** database:</span></span>  
  
     `USE master;`  
  
3.  <span data-ttu-id="bc867-108">Emita a seguinte instrução no servidor principal:</span><span class="sxs-lookup"><span data-stu-id="bc867-108">Issue the following statement on the principal server:</span></span>  
  
     <span data-ttu-id="bc867-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, em que *database_name* é o banco de dados espelhado.</span><span class="sxs-lookup"><span data-stu-id="bc867-109">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, where *database_name* is the mirrored database.</span></span>  
  
     <span data-ttu-id="bc867-110">Isso inicia uma transição imediata do servidor espelho para a função principal.</span><span class="sxs-lookup"><span data-stu-id="bc867-110">This initiates an immediate transition of the mirror server to the principal role.</span></span>  
  
 <span data-ttu-id="bc867-111">No principal anterior, clientes são desconectados do banco de dados e são revertidos em transações de voo.</span><span class="sxs-lookup"><span data-stu-id="bc867-111">On the former principal, clients are disconnected from the database and in-flight transactions are rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc867-112">As transações que forem preparadas usando o Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] , mas que ainda não estiverem confirmadas quando ocorrer um failover, serão consideradas anuladas depois da falha do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc867-112">Transactions that have been prepared by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator but are still not committed when a failover occurs are considered aborted after the database has failed over.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc867-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc867-113">See Also</span></span>  
 <span data-ttu-id="bc867-114">[Espelhamento de banco de dados ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="bc867-114">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="bc867-115">[Fazer failover manualmente de uma sessão de espelhamento de banco de dados &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="bc867-115">[Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="bc867-116">Troca de função durante uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bc867-116">Role Switching During a Database Mirroring Session &#40;SQL Server&#41;</span></span>](role-switching-during-a-database-mirroring-session-sql-server.md)  
  
  
