---
title: Removendo o espelhamento de banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- stopping database mirroring [SQL Server]
- removing database mirroring [SQL Server]
ms.assetid: 40c72091-8f03-4037-8b55-5e95309fe145
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8044fcef9d9f9bfc1fb41c1faa17b76c827da5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681151"
---
# <a name="removing-database-mirroring-sql-server"></a><span data-ttu-id="c8df0-102">Removendo o espelhamento de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c8df0-102">Removing Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="c8df0-103">O proprietário do banco de dados pode interromper manualmente uma sessão de espelhamento de banco de dados a qualquer momento, em qualquer parceiro.</span><span class="sxs-lookup"><span data-stu-id="c8df0-103">The database owner can manually stop a database mirroring session at any time, at either partner.</span></span>  
  
## <a name="impact-of-removing-mirroring"></a><span data-ttu-id="c8df0-104">Impacto da remoção do espelhamento</span><span class="sxs-lookup"><span data-stu-id="c8df0-104">Impact of Removing Mirroring</span></span>  
 <span data-ttu-id="c8df0-105">Quando o espelhamento é removido, acontece o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c8df0-105">When mirroring is removed, the following occurs:</span></span>  
  
-   <span data-ttu-id="c8df0-106">A relação entre os parceiros e entre cada parceiro e a testemunha se rompe permanentemente, caso exista alguma relação.</span><span class="sxs-lookup"><span data-stu-id="c8df0-106">The relationship between the partners and between each partner and the witness breaks permanently, if any relationship exists.</span></span>  
  
     <span data-ttu-id="c8df0-107">Se os parceiros estiverem se comunicando entre si quando a sessão for interrompida, sua relação será imediatamente rompida em ambos os computadores.</span><span class="sxs-lookup"><span data-stu-id="c8df0-107">If the partners are communicating with each other when the session is stopped, their relationship is immediately broken on both computers.</span></span> <span data-ttu-id="c8df0-108">Se os parceiros não estiverem se comunicando (o banco de dados estiver em um estado DISCONNECTED no momento da interrupção), a relação será imediatamente interrompida no parceiro em que o espelhamento é interrompido; quando o outro parceiro tenta se reconectar, descobre que a sessão de espelhamento de banco de dados foi concluída.</span><span class="sxs-lookup"><span data-stu-id="c8df0-108">If the partners are not communicating (the database is in a DISCONNECTED state at the time of stopping), the relationship is broken immediately on the partner from which mirroring is stopped; when the other partner tries to reconnect, it discovers that the database mirroring session has ended.</span></span>  
  
-   <span data-ttu-id="c8df0-109">As informações sobre a sessão de espelhamento são descartadas, diferentemente de quando uma sessão é pausada.</span><span class="sxs-lookup"><span data-stu-id="c8df0-109">Information about the mirroring session is dropped, unlike when pausing a session.</span></span> <span data-ttu-id="c8df0-110">O espelhamento é removido do banco de dados principal e do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="c8df0-110">Mirroring is removed on both the principal database and the mirror database.</span></span> <span data-ttu-id="c8df0-111">No **sys.databases**, a coluna **mirroring_state** e todas as demais colunas de espelhamento são definidas como NULL.</span><span class="sxs-lookup"><span data-stu-id="c8df0-111">In **sys.databases**, the **mirroring_state** column and all other mirroring columns are set to NULL.</span></span> <span data-ttu-id="c8df0-112">Para obter mais informações, veja [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8df0-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
-   <span data-ttu-id="c8df0-113">Cada instância de servidor parceiro é deixada com uma cópia separada do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c8df0-113">Each partner server instance is left with a separate copy of the database.</span></span>  
  
-   <span data-ttu-id="c8df0-114">O banco de dados espelho é deixado em estado RESTORING (consulte a coluna **estado** do **sys.databases**), porque o banco de dados espelho foi criado usando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c8df0-114">The mirror database is left in the RESTORING state (see the **state** column of **sys.databases**), because the mirror database was created by using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="c8df0-115">Nesse momento, você pode descartar o banco de dados espelho anterior ou restaurá-lo usando WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c8df0-115">At this point, you can drop the former mirror database or restore it using WITH RECOVERY.</span></span> <span data-ttu-id="c8df0-116">Ao ser recuperado, o banco de dados diverge do banco de dados principal anterior porque a recuperação inicia uma nova bifurcação da recuperação.</span><span class="sxs-lookup"><span data-stu-id="c8df0-116">When you recover the database, it will have diverged from the former principal database because the recovery starts a new recovery fork.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8df0-117">Para continuar o espelhamento depois de interromper uma sessão, é preciso estabelecer uma nova sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c8df0-117">To continue mirroring after stopping a session, you must establish a new database mirroring session.</span></span> <span data-ttu-id="c8df0-118">Se você criar um backup de log depois de ter interrompido um espelhamento, deverá registrá-lo no banco de dados espelho antes reiniciar o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="c8df0-118">If you create a log backup after stopping mirroring, you must apply it to the mirror database before restarting mirroring.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c8df0-119">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="c8df0-119">Related Tasks</span></span>  
 <span data-ttu-id="c8df0-120">**Para remover o espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="c8df0-120">**To remove database mirroring**</span></span>  
  
-   [<span data-ttu-id="c8df0-121">Remover o espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c8df0-121">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
 <span data-ttu-id="c8df0-122">**Para inicializar o espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="c8df0-122">**To start database mirroring**</span></span>  
  
-   [<span data-ttu-id="c8df0-123">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c8df0-123">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="c8df0-124">Estabelecer uma sessão de espelhamento de banco de dados com a Autenticação do Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8df0-124">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="c8df0-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8df0-125">See Also</span></span>  
 <span data-ttu-id="c8df0-126">[Espelhamento de banco de dados ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="c8df0-126">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="c8df0-127">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8df0-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c8df0-128">[Pausando e retomando o espelhamento de banco de dados &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8df0-128">[Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="c8df0-129">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8df0-129">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
