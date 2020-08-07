---
title: Mover um banco de dados utilizando Desanexar e Anexar (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database attaching [SQL Server]
- moving databases [SQL Server]
- database detaching [SQL Server]
- relocating databases [SQL Server]
- detaching databases [SQL Server]
- attaching databases [SQL Server]
ms.assetid: 6732a431-cdef-4f1e-9262-4ac3b77c275e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 768a70dfe94af6f8d65f7c76fa08d3dff650fe7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583611"
---
# <a name="move-a-database-using-detach-and-attach-transact-sql"></a><span data-ttu-id="3c7f4-102">Mover um banco de dados utilizando Desanexar e Anexar (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3c7f4-102">Move a Database Using Detach and Attach (Transact-SQL)</span></span>
  <span data-ttu-id="3c7f4-103">Este tópico descreve como mover um banco de dados desanexado para outro local e anexá-lo novamente à mesma instância de servidor ou a uma instância diferente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c7f4-103">This topic describes how to move a detached database to another location and re-attach it to the same or a different server instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="3c7f4-104">No entanto, recomendamos que você mova os bancos de dados utilizando o procedimento de realocação planejada ALTER DATABASE, em vez de utilizar desanexar e anexar.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-104">However, we recommend that you move databases by using the ALTER DATABASE planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="3c7f4-105">Para obter mais informações, veja [Mover bancos de dados de usuário](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="3c7f4-105">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3c7f4-106">Não é recomendável anexar ou restaurar bancos de dados de origem desconhecida ou não confiável.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-106">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="3c7f4-107">Esses bancos de dados podem conter um código mal-intencionado que pode executar um código [!INCLUDE[tsql](../../includes/tsql-md.md)] inesperado ou provocar erros modificando o esquema ou a estrutura física do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-107">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="3c7f4-108">Antes de usar um banco de dados de origem desconhecida ou não confiável, execute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no banco de dados, em um servidor que não seja de produção. Além disso, examine o código, como procedimentos armazenados ou outro código definido pelo usuário, no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-108">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="3c7f4-109">Procedimento</span><span class="sxs-lookup"><span data-stu-id="3c7f4-109">Procedure</span></span>  
  
#### <a name="to-move-a-database-by-using-detach-and-attach"></a><span data-ttu-id="3c7f4-110">Para mover um banco de dados usando anexar e desanexar</span><span class="sxs-lookup"><span data-stu-id="3c7f4-110">To move a database by using detach and attach</span></span>  
  
1.  <span data-ttu-id="3c7f4-111">Desanexe o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-111">Detach the database.</span></span> <span data-ttu-id="3c7f4-112">Para obter mais informações, veja [Desanexar um banco de dados](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="3c7f4-112">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
2.  <span data-ttu-id="3c7f4-113">Em uma janela do Windows Explorer ou do prompt de comando do Windows, mova os arquivos do banco de dados desanexado e os arquivos de log para o novo local.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-113">In a Windows Explorer or Windows Command Prompt window, move the detached database file or files and log file or files to the new location.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3c7f4-114">Para mover um banco de dados de um único arquivo, você poderá utilizar email se o tamanho do arquivo for pequeno o bastante para caber no email.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-114">To move a single-file database, you can use email if the file size is small enough for email to accommodate.</span></span>  
  
     <span data-ttu-id="3c7f4-115">Você deverá mover os arquivos de log, mesmo se pretender criar novos arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-115">You should move the log files even if you intend to create new log files.</span></span> <span data-ttu-id="3c7f4-116">Em alguns casos, reanexar um banco de dados exige seus arquivos de log existentes.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-116">In some cases, reattaching a database requires its existing log files.</span></span> <span data-ttu-id="3c7f4-117">Portanto, mantenha todos os arquivos de log desanexados até que o banco de dados seja anexado com êxito sem eles.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-117">Therefore, always keep all the detached log files until the database has been successfully attached without them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3c7f4-118">Se você tentar anexar o banco de dados sem especificar o arquivo de log, a operação de anexação procurará o arquivo de log em seu local original.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-118">If you try to attach the database without specifying the log file, the attach operation will look for the log file in its original location.</span></span> <span data-ttu-id="3c7f4-119">Se ainda existir uma cópia do log no local original, essa cópia será anexada.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-119">If a copy of the log still exists in the original location, that copy is attached.</span></span> <span data-ttu-id="3c7f4-120">Para evitar a utilização do arquivo de log original, especifique o caminho do novo arquivo de log ou remova a cópia original do arquivo de log (depois de copiá-la para o novo local).</span><span class="sxs-lookup"><span data-stu-id="3c7f4-120">To avoid using the original log file, either specify the path of the new log file or remove the original copy of the log file (after copying it to the new location).</span></span>  
  
3.  <span data-ttu-id="3c7f4-121">Anexe os arquivos copiados.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-121">Attach the copied files.</span></span> <span data-ttu-id="3c7f4-122">Para obter mais informações, consulte [Attach a Database](attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="3c7f4-122">For more information, see [Attach a Database](attach-a-database.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c7f4-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3c7f4-123">Example</span></span>  
 <span data-ttu-id="3c7f4-124">O exemplo a seguir cria uma cópia das [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] instruções que são executadas em uma janela do editor de consultas que está conectada à instância do servidor à qual está anexada.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-124">The following example creates a copy of the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements are executed in a Query Editor window that is connected to the server instance to which is attached.</span></span>  
  
1.  <span data-ttu-id="3c7f4-125">Desanexe as [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] instruções:</span><span class="sxs-lookup"><span data-stu-id="3c7f4-125">Detach the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sp_detach_db @dbname = N'AdventureWorks2012';  
    GO  
    ```  
  
2.  <span data-ttu-id="3c7f4-126">Utilizando o método de sua preferência, copie os arquivos de banco de dados (AdventureWorks208R2_Data.mdf e AdventureWorks208R2_log) para C:\MySQLServer\AdventureWorks208R2_Data.mdf e C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-126">Using the method of your choice, copy the database files (AdventureWorks208R2_Data.mdf and AdventureWorks208R2_log) to: C:\MySQLServer\AdventureWorks208R2_Data.mdf and C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectively.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3c7f4-127">Para um banco de dados de produção, coloque o banco de dados e o log de transações em discos separados.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-127">For a production database, place the database and transaction log on separate disks.</span></span>  
  
     <span data-ttu-id="3c7f4-128">Para copiar arquivos pela rede para um disco ou um computador remoto, utilize o nome UNC (Convenção Universal de Nomenclatura) do local remoto.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-128">To copy files over the network to a disk on a remote computer, use the universal naming convention (UNC) name of the remote location.</span></span> <span data-ttu-id="3c7f4-129">Um nome UNC possui o formato **\\\\** _Servername_ **\\** _Sharename_ **\\** _Path_ **\\** _Filename_.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-129">A UNC name takes the form **\\\\**_Servername_**\\**_Sharename_**\\**_Path_**\\**_Filename_.</span></span> <span data-ttu-id="3c7f4-130">Assim como ocorre com a gravação de arquivos no disco rígido local, deverão ser concedidas, à conta do usuário utilizada pela instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as permissões apropriadas exigidas para ler ou gravar em um arquivo no disco remoto.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-130">As with writing files to the local hard disk, the appropriate permissions that are required to read or write to a file on the remote disk must be granted to the user account used by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="3c7f4-131">Anexe o banco de dados movido e, opcionalmente, seu log executando as seguintes instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="3c7f4-131">Attach the moved database and, optionally, its log by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Data.mdf'),  
        (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Log.ldf')  
        FOR ATTACH;  
    GO  
    ```  
  
     <span data-ttu-id="3c7f4-132">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], um banco de dados anexado recentemente não fica imediatamente visível no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a newly attached database is not immediately visible in Object Explorer.</span></span> <span data-ttu-id="3c7f4-133">Para exibir o banco de dados, no Pesquisador de Objetos, clique em **Exibir** e depois em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-133">To view the database, in Object Explorer, click **View,** and then **Refresh**.</span></span> <span data-ttu-id="3c7f4-134">Quando o nó **Bancos de Dados** for expandido no Pesquisador de Objetos, o banco de dados recentemente anexado será exibido na lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3c7f4-134">When the **Databases** node is expanded in Object Explorer, the newly attached database now appears in the list of databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7f4-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3c7f4-135">See Also</span></span>  
 [<span data-ttu-id="3c7f4-136">Anexar e desanexar bancos de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3c7f4-136">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
