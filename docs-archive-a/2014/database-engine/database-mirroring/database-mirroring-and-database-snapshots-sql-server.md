---
title: Espelhamento de banco de dados e instantâneos do banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- snapshots [SQL Server database snapshots], database mirroring
- database snapshots [SQL Server], database mirroring
ms.assetid: 0bf1be90-7ce4-484c-aaa7-f8a782f57c5f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9df0b74270280bf2315c6a35a80d4b009b75a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571577"
---
# <a name="database-mirroring-and-database-snapshots-sql-server"></a><span data-ttu-id="00c36-102">Espelhamento de banco de dados e instantâneos de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="00c36-102">Database Mirroring and Database Snapshots (SQL Server)</span></span>
  <span data-ttu-id="00c36-103">Você pode tirar proveito de um banco de dados espelho que você está mantendo para fins de disponibilidade para descarregar relatórios.</span><span class="sxs-lookup"><span data-stu-id="00c36-103">You can take advantage of a mirror database that you are maintaining for availability purposes to offload reporting.</span></span> <span data-ttu-id="00c36-104">Para usar um banco de dados espelho para relatórios, você pode criar um instantâneo do banco de dados no banco de dados espelho e direcionar as solicitações de conexão de clientes para o instantâneo mais recente.</span><span class="sxs-lookup"><span data-stu-id="00c36-104">To use a mirror database for reporting, you can create a database snapshot on the mirror database and direct client connection requests to the most recent snapshot.</span></span> <span data-ttu-id="00c36-105">Um instantâneo do banco de dados é um instantâneo consistente de transações, estático e somente leitura de seu banco de dados de origem tal como ele estava no momento da criação do instantâneo.</span><span class="sxs-lookup"><span data-stu-id="00c36-105">A database snapshot is a static, read-only, transaction-consistent snapshot of its source database as it existed at the moment of the snapshot's creation.</span></span> <span data-ttu-id="00c36-106">Para criar um instantâneo do banco de dados em um banco de dados espelho, o banco de dados precisa estar no estado de espelhamento sincronizado.</span><span class="sxs-lookup"><span data-stu-id="00c36-106">To create a database snapshot on a mirror database, the database must be in the synchronized mirroring state.</span></span>  
  
 <span data-ttu-id="00c36-107">Ao contrário do próprio banco de dados espelho, um instantâneo do banco de dados está acessível aos clientes.</span><span class="sxs-lookup"><span data-stu-id="00c36-107">Unlike the mirror database itself, a database snapshot is accessible to clients.</span></span> <span data-ttu-id="00c36-108">Contanto que o servidor espelho esteja se comunicando com o servidor principal, você pode dirigir os clientes que estejam inserindo informações para que se conectem a um instantâneo.</span><span class="sxs-lookup"><span data-stu-id="00c36-108">As long as the mirror server is communicating with the principal server, you can direct reporting clients to connect to a snapshot.</span></span> <span data-ttu-id="00c36-109">Observe que devido ao fato de o instantâneo do banco de dados ser estático, os novos dados não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="00c36-109">Note that because a database snapshot is static, new data is not available.</span></span> <span data-ttu-id="00c36-110">Para tornar dados relativamente recentes disponíveis a seus usuários, você precisa criar periodicamente um novo instantâneo do banco de dados e fazer com que os aplicativos dirijam as conexões de entrada de clientes para o instantâneo mais recente.</span><span class="sxs-lookup"><span data-stu-id="00c36-110">To make relatively recent data available to your users, you must create a new database snapshot periodically and have applications direct incoming client connections to the newest snapshot.</span></span>  
  
 <span data-ttu-id="00c36-111">Um novo instantâneo do banco de dados está quase vazio, mas cresce com o tempo, conforme mais e mais páginas do banco de dados são atualizadas pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="00c36-111">A new database snapshot is almost empty, but it grows over time as more and more database pages are updated for the first time.</span></span> <span data-ttu-id="00c36-112">Como todo instantâneo em um banco de dados cresce incrementalmente desse modo, cada instantâneo do banco de dados consome os mesmos recursos que um banco de dados normal.</span><span class="sxs-lookup"><span data-stu-id="00c36-112">Because every snapshot on a database grows incrementally in this way, each database snapshot consumes as much resources as a normal database.</span></span> <span data-ttu-id="00c36-113">Dependendo das configurações do servidor espelho e do servidor principal, um número excessivo de instantâneos de banco de dados em um banco de dados espelho pode diminuir o desempenho no banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="00c36-113">Depending on the configurations of the mirror server and principal server, having an excessive number of database snapshots on a mirror database might decrease performance on the principal database.</span></span> <span data-ttu-id="00c36-114">Portanto, recomendamos que você mantenha só alguns instantâneos relativamente recentes em seus bancos de dados espelhos.</span><span class="sxs-lookup"><span data-stu-id="00c36-114">Therefore, we recommend that you keep only a few relatively recent snapshots on your mirror databases.</span></span> <span data-ttu-id="00c36-115">Geralmente, depois de criar um instantâneo de substituição, você deve redirecionar as entradas de consultas para o novo instantâneo e descartar o instantâneo mais antigo depois que as consultas atuais forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="00c36-115">Typically, after you create a replacement snapshot, you should redirect incoming queries to the new snapshot and drop the earlier snapshot after any current queries complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00c36-116">Para obter mais informações sobre instantâneos de banco de dados, consulte [Instantâneos de banco de dados &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="00c36-116">For more information about database snapshots, see [Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span></span>  
  
 <span data-ttu-id="00c36-117">Se houver troca de função, o banco de dados e seus instantâneos serão reinicializados, desconectando os usuários temporariamente.</span><span class="sxs-lookup"><span data-stu-id="00c36-117">If role switching occurs, the database and its snapshots are restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="00c36-118">Depois, os instantâneos do banco de dados permanecem na instância de servidor em que foram criados e que se tornou o novo banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="00c36-118">Afterwards, the database snapshots remain on the server instance where they were created, which has become the new principal database.</span></span> <span data-ttu-id="00c36-119">Os usuários podem continuar usando os instantâneos depois do failover.</span><span class="sxs-lookup"><span data-stu-id="00c36-119">Users can continue to use the snapshots after the failover.</span></span> <span data-ttu-id="00c36-120">Porém, isso coloca uma carga adicional no novo servidor principal.</span><span class="sxs-lookup"><span data-stu-id="00c36-120">However, this places an additional load on the new principal server.</span></span> <span data-ttu-id="00c36-121">Se o desempenho for uma preocupação em seu ambiente, recomendamos que você crie um instantâneo no novo banco de dados espelho quando ele se tornar disponível, redirecione os clientes ao novo instantâneo e descarte todos os instantâneos do banco de dados do antigo banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="00c36-121">If performance is a concern in your environment, we recommend that you create a snapshot on the new mirror database when it becomes available, redirect clients to the new snapshot, and drop all of the database snapshots from the former mirror database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00c36-122">Para uma solução de relatórios dedicada que seja bem dimensionável, pense em replicação.</span><span class="sxs-lookup"><span data-stu-id="00c36-122">For a dedicated reporting solution that scales out well, consider replication.</span></span> <span data-ttu-id="00c36-123">Para obter mais informações, consulte [Replicação do SQL Server](../install-windows/install-sql-server-replication.md).</span><span class="sxs-lookup"><span data-stu-id="00c36-123">For more information, see [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00c36-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="00c36-124">Example</span></span>  
 <span data-ttu-id="00c36-125">Esse exemplo cria instantâneos em um banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="00c36-125">This example creates snapshots on a mirrored database.</span></span>  
  
 <span data-ttu-id="00c36-126">Suponha que o banco de dados de uma sessão de espelhamento de banco de dados seja [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00c36-126">Assume that the database of a database mirroring session is [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="00c36-127">Esse exemplo cria três instantâneos do banco de dados na cópia espelhada do banco de dados `AdventureWorks` que está na unidade `F` .</span><span class="sxs-lookup"><span data-stu-id="00c36-127">This example creates three database snapshots on the mirror copy of the `AdventureWorks` database, which resides on the `F` drive.</span></span> <span data-ttu-id="00c36-128">Os instantâneos são nomeados `AdventureWorks_0600`, `AdventureWorks_1200`e `AdventureWorks_1800` para identificar seu horário aproximado de criação.</span><span class="sxs-lookup"><span data-stu-id="00c36-128">The snapshots are named `AdventureWorks_0600`, `AdventureWorks_1200`, and `AdventureWorks_1800` to identify their approximate creation times.</span></span>  
  
1.  <span data-ttu-id="00c36-129">Crie o primeiro instantâneo do banco de dados no espelho de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00c36-129">Create the first database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_0600  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_0600.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
2.  <span data-ttu-id="00c36-130">Crie o segundo instantâneo do banco de dados no espelho de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00c36-130">Create the second database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="00c36-131">Os usuários que ainda estejam usando o `AdventureWorks_0600` podem continuar a usá-lo.</span><span class="sxs-lookup"><span data-stu-id="00c36-131">Users who are still using `AdventureWorks_0600` can continue to use it.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1200  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1200.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="00c36-132">Neste ponto, novas conexões de cliente podem ser direcionadas programaticamente para o instantâneo mais recente.</span><span class="sxs-lookup"><span data-stu-id="00c36-132">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
3.  <span data-ttu-id="00c36-133">Crie o terceiro instantâneo do banco de dados no espelho [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00c36-133">Create the third snapshot on the mirror [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="00c36-134">Os usuários que ainda estejam usando o `AdventureWorks_0600` ou o `AdventureWorks_1200` podem continuar a usá-los.</span><span class="sxs-lookup"><span data-stu-id="00c36-134">Users who are still using `AdventureWorks_0600` or `AdventureWorks_1200` can continue to use them.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1800  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1800.SNP')  
        AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="00c36-135">Neste ponto, novas conexões de cliente podem ser direcionadas programaticamente para o instantâneo mais recente.</span><span class="sxs-lookup"><span data-stu-id="00c36-135">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="00c36-136">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="00c36-136">Related Tasks</span></span>  
  
-   [<span data-ttu-id="00c36-137">Criar um instantâneo de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="00c36-137">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="00c36-138">Exibir um instantâneo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00c36-138">View a Database Snapshot &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="00c36-139">Remover um instantâneo do banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="00c36-139">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md)  

  
## <a name="see-also"></a><span data-ttu-id="00c36-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="00c36-140">See Also</span></span>  
 <span data-ttu-id="00c36-141">[Instantâneos de banco de dados &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00c36-141">[Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span></span>  
 [<span data-ttu-id="00c36-142">Conectar clientes a uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00c36-142">Connect Clients to a Database Mirroring Session &#40;SQL Server&#41;</span></span>](connect-clients-to-a-database-mirroring-session-sql-server.md)  
  
  
