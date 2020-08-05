---
title: MSSQLSERVER_926 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 926 (Database Engine error)
ms.assetid: 57e01668-883b-4be4-84a8-a111caaf0486
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae6796c9f4869d45223ab1283a68fc2bfe78aa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573044"
---
# <a name="mssqlserver_926"></a><span data-ttu-id="47660-102">MSSQLSERVER_926</span><span class="sxs-lookup"><span data-stu-id="47660-102">MSSQLSERVER_926</span></span>
    
## <a name="details"></a><span data-ttu-id="47660-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="47660-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47660-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="47660-104">Product Name</span></span>|<span data-ttu-id="47660-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="47660-105">SQL Server</span></span>|  
|<span data-ttu-id="47660-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="47660-106">Event ID</span></span>|<span data-ttu-id="47660-107">926</span><span class="sxs-lookup"><span data-stu-id="47660-107">926</span></span>|  
|<span data-ttu-id="47660-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="47660-108">Event Source</span></span>|<span data-ttu-id="47660-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="47660-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="47660-110">Componente</span><span class="sxs-lookup"><span data-stu-id="47660-110">Component</span></span>|<span data-ttu-id="47660-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="47660-111">SQLEngine</span></span>|  
|<span data-ttu-id="47660-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="47660-112">Symbolic Name</span></span>|<span data-ttu-id="47660-113">DB_SUSPECT</span><span class="sxs-lookup"><span data-stu-id="47660-113">DB_SUSPECT</span></span>|  
|<span data-ttu-id="47660-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="47660-114">Message Text</span></span>|<span data-ttu-id="47660-115">O banco de dados '%.\*ls' não pode ser aberto.</span><span class="sxs-lookup"><span data-stu-id="47660-115">Database '%.\*ls' cannot be opened.</span></span> <span data-ttu-id="47660-116">Ele foi marcado como SUSPECT pela recuperação.</span><span class="sxs-lookup"><span data-stu-id="47660-116">It has been marked SUSPECT by recovery.</span></span> <span data-ttu-id="47660-117">Consulte o log de erros do SQL Server para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="47660-117">See the SQL Server errorlog for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47660-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="47660-118">Explanation</span></span>  
 <span data-ttu-id="47660-119">O banco de dados foi marcado como suspeito porque houve falha no processo de recuperação que leva um banco de dados a um estado transacional consistente.</span><span class="sxs-lookup"><span data-stu-id="47660-119">The database is marked as suspect because it failed the recovery process that brings a database to a consistent transactional state.</span></span> <span data-ttu-id="47660-120">Isso pode acontecer durante as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="47660-120">This can occur during the following operations:</span></span>  
  
-   <span data-ttu-id="47660-121">Inicializando uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47660-121">Starting up an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="47660-122">Anexando um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="47660-122">Attaching a database.</span></span>  
  
-   <span data-ttu-id="47660-123">Usando os procedimentos de RESTORE LOG ou RESTORE para restaurar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="47660-123">Using the RESTORE database or RESTORE LOG procedures.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47660-124">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="47660-124">User Action</span></span>  
 <span data-ttu-id="47660-125">Inspecione o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e determine a causa do erro.</span><span class="sxs-lookup"><span data-stu-id="47660-125">Inspect the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and determine the cause of the error.</span></span> <span data-ttu-id="47660-126">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiver sido reiniciado desde a falha na recuperação, veja os logs de erros anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar a razão pela qual houve falha na recuperação.</span><span class="sxs-lookup"><span data-stu-id="47660-126">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been restarted since the failed recovery, look at previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs to see the reason why recovery failed.</span></span>  
  
 <span data-ttu-id="47660-127">Se a recuperação tiver apresentado falha devido a um erro persistente de E/S, uma página interrompida ou outro possível problema de hardware, resolva o problema de hardware subjacente e restaure o banco de dados usando um backup.</span><span class="sxs-lookup"><span data-stu-id="47660-127">If the recovery failed because of a persistent I/O error, a torn page, or other possible hardware problem, resolve the underlying hardware problem and restore the database by using a backup.</span></span> <span data-ttu-id="47660-128">Se nenhum backup estiver disponível, considere as opções de reparo de DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="47660-128">If no backups are available, consider the repair options of DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="47660-129">Se você não conseguir resolver esse problema, entre em contato com o provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="47660-129">If you are unable to resolve this problem, contact your primary support provider.</span></span> <span data-ttu-id="47660-130">Tenha o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponível para revisão.</span><span class="sxs-lookup"><span data-stu-id="47660-130">Have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log available for review.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47660-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47660-131">See Also</span></span>  
 <span data-ttu-id="47660-132">[Fazer backup e restaurar bancos de dados do SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="47660-132">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="47660-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47660-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="47660-134">[Bancos de dadossys.sys&#40;&#41;Transact-SQL](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47660-134">[sys.sysdatabases &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span></span>  
 [<span data-ttu-id="47660-135">Anexar e desanexar bancos de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="47660-135">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/database-detach-and-attach-sql-server.md)  
  
  
