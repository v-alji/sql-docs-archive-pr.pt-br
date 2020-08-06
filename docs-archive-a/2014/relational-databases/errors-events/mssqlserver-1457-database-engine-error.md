---
title: MSSQLSERVER_1457 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1457 (Database Engine error)
ms.assetid: 28434ba1-b033-4866-ab41-111fccef45a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c30ee6149c95d93bdaf1d2877f5fe1871a575ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581904"
---
# <a name="mssqlserver_1457"></a><span data-ttu-id="e71ce-102">MSSQLSERVER_1457</span><span class="sxs-lookup"><span data-stu-id="e71ce-102">MSSQLSERVER_1457</span></span>
    
## <a name="details"></a><span data-ttu-id="e71ce-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e71ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e71ce-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e71ce-104">Product Name</span></span>|<span data-ttu-id="e71ce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e71ce-105">SQL Server</span></span>|  
|<span data-ttu-id="e71ce-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e71ce-106">Event ID</span></span>|<span data-ttu-id="e71ce-107">1457</span><span class="sxs-lookup"><span data-stu-id="e71ce-107">1457</span></span>|  
|<span data-ttu-id="e71ce-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e71ce-108">Event Source</span></span>|<span data-ttu-id="e71ce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e71ce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e71ce-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e71ce-110">Component</span></span>|<span data-ttu-id="e71ce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e71ce-111">SQLEngine</span></span>|  
|<span data-ttu-id="e71ce-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e71ce-112">Symbolic Name</span></span>|<span data-ttu-id="e71ce-113">DBM_PAGE_UNDO_PENDING</span><span class="sxs-lookup"><span data-stu-id="e71ce-113">DBM_PAGE_UNDO_PENDING</span></span>|  
|<span data-ttu-id="e71ce-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e71ce-114">Message Text</span></span>|<span data-ttu-id="e71ce-115">A sincronização do banco de dados espelho, '%.\* ls', foi interrompida, deixando o banco de dados em um estado inconsistente.</span><span class="sxs-lookup"><span data-stu-id="e71ce-115">Synchronization of the mirror database, '%.\*ls', was interrupted, leaving the database in an inconsistent state.</span></span> <span data-ttu-id="e71ce-116">Falha no comando ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="e71ce-116">The ALTER DATABASE command failed.</span></span> <span data-ttu-id="e71ce-117">Verifique se o banco de dados espelho voltou a funcionar e está online e reconecte a instância do servidor espelho para permitir que o banco de dados espelho termine a sincronização.</span><span class="sxs-lookup"><span data-stu-id="e71ce-117">Ensure that the mirror database is back up and online, and then reconnect the mirror server instance and allow the mirror database to finish synchronizing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e71ce-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="e71ce-118">Explanation</span></span>  
 <span data-ttu-id="e71ce-119">Essa mensagem indica que a instrução ALTER DATABASE *database_name* SET PARTNER OFF falhou.</span><span class="sxs-lookup"><span data-stu-id="e71ce-119">This messages indicates that the ALTER DATABASE *database_name* SET PARTNER OFF statement has failed.</span></span> <span data-ttu-id="e71ce-120">A falha na tentativa de remover o espelhamento de banco de dados interrompeu a sincronização do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="e71ce-120">The failed attempt to remove database mirroring interrupted synchronization of the mirror database.</span></span> <span data-ttu-id="e71ce-121">O banco de dados está em estado inconsistente.</span><span class="sxs-lookup"><span data-stu-id="e71ce-121">The database is in an inconsistent state.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e71ce-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e71ce-122">User Action</span></span>  
 <span data-ttu-id="e71ce-123">Para resolver esse erro, você pode realizar uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e71ce-123">To resolve this error, you can take either of the following actions:</span></span>  
  
-   <span data-ttu-id="e71ce-124">Restaure o contato entre o servidor espelho e o servidor principal para permitir a sincronização do banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="e71ce-124">Restore contact between the mirror server and the principal server to allow for the mirror database to synchronize.</span></span>  
  
-   <span data-ttu-id="e71ce-125">Descarte o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="e71ce-125">Drop the mirror database.</span></span>  
  
     <span data-ttu-id="e71ce-126">Depois de descartar o banco de dados espelho, você pode criar um banco de dados espelho a partir de backups.</span><span class="sxs-lookup"><span data-stu-id="e71ce-126">After you drop the mirror database, you can create a new mirror database from backups.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e71ce-127">Você só poderá descartar o banco de dados espelho quando o espelhamento ainda estiver habilitado após a falha de uma instrução SET PARTNER OFF.</span><span class="sxs-lookup"><span data-stu-id="e71ce-127">You can drop the mirror database when mirroring is still enabled only after a failed SET PARTNER OFF statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e71ce-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e71ce-128">See Also</span></span>  
 <span data-ttu-id="e71ce-129">[Espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e71ce-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="e71ce-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e71ce-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="e71ce-131">[Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e71ce-131">[Setting Up Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="e71ce-132">[Removendo o espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e71ce-132">[Removing Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="e71ce-133">Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e71ce-133">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
  
