---
title: Restaurar um banco de dados para o ponto de falha no modelo de recuperação completa (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- point of failure [SQL Server]
- restoring databases [SQL Server], point of failure
- database restores [SQL Server], point of failure
ms.assetid: 04106e18-bbf7-4a5e-a2e1-3d65319814d5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95b73660ebb44f4daffe6eaefd873699cfbbd8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573128"
---
# <a name="restore-a-database-to-the-point-of-failure-under-the-full-recovery-model-transact-sql"></a><span data-ttu-id="6c5d7-102">Restaurar um banco de dados até o ponto de falha no modelo de recuperação completa (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6c5d7-102">Restore a Database to the Point of Failure Under the Full Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="6c5d7-103">Este tópico explica como restaurar até o ponto de falha.</span><span class="sxs-lookup"><span data-stu-id="6c5d7-103">This topic explains how to restore to the point of failure.</span></span> <span data-ttu-id="6c5d7-104">O tópico é relevante apenas para bancos de dados que estejam usando modelos de recuperação completa ou com bulk-logged.</span><span class="sxs-lookup"><span data-stu-id="6c5d7-104">The topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
### <a name="to-restore-to-the-point-of-failure"></a><span data-ttu-id="6c5d7-105">Para restaurar até o ponto de falha</span><span class="sxs-lookup"><span data-stu-id="6c5d7-105">To restore to the point of failure</span></span>  
  
1.  <span data-ttu-id="6c5d7-106">Faça backup do final do log executando a seguinte instrução básica [BACKUP](/sql/t-sql/statements/backup-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="6c5d7-106">Back up the tail of the log by running the following basic [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
    ```  
    BACKUP LOG <database_name> TO <backup_device>   
       WITH NORECOVERY, NO_TRUNCATE;  
    ```  
  
2.  <span data-ttu-id="6c5d7-107">Restaure um backup de banco de dados completo executando a seguinte instrução básica [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="6c5d7-107">Restore a full database backup by running the following basic [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
3.  <span data-ttu-id="6c5d7-108">Opcionalmente, restaure um backup de banco de dados diferencial executando a seguinte instrução básica RESTORE DATABASE:</span><span class="sxs-lookup"><span data-stu-id="6c5d7-108">Optionally, restore a differential database backup by running the following basic RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
4.  <span data-ttu-id="6c5d7-109">Aplique cada log de transações, inclusive o backup do final do log criado na etapa 1, especificando WITH NORECOVERY na instrução RESTORE LOG:</span><span class="sxs-lookup"><span data-stu-id="6c5d7-109">Apply each transaction log, including the tail-log backup you created in step 1, by specifying WITH NORECOVERY in the RESTORE LOG statement:</span></span>  
  
    ```  
    RESTORE LOG <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
5.  <span data-ttu-id="6c5d7-110">Recupere o banco de dados executando a seguinte instrução RESTORE DATABASE:</span><span class="sxs-lookup"><span data-stu-id="6c5d7-110">Recover the database by running the following RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name>   
       WITH RECOVERY;  
    ```  
  
## <a name="example"></a><span data-ttu-id="6c5d7-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6c5d7-111">Example</span></span>  
 <span data-ttu-id="6c5d7-112">Antes de você poder executar o exemplo, é necessário completar as seguintes preparações:</span><span class="sxs-lookup"><span data-stu-id="6c5d7-112">Before you can run the example, you must complete the following preparations:</span></span>  
  
1.  <span data-ttu-id="6c5d7-113">O modelo padrão de recuperação da base de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] é o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="6c5d7-113">The default recovery model of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database is the simple recovery model.</span></span> <span data-ttu-id="6c5d7-114">Como esse modelo de recuperação não oferece suporte à restauração ao ponto de uma falha, defina [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] para usar o modelo de recuperação completa executando a seguinte instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="6c5d7-114">Because this recovery model does not support restoring to the point of a failure, set [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] to use the full recovery model by running the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
    ```  
  
2.  <span data-ttu-id="6c5d7-115">Crie um backup completo do banco de dados usando a seguinte instrução BACKUP:</span><span class="sxs-lookup"><span data-stu-id="6c5d7-115">Create a full database back of the database by using the following BACKUP statement:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Data.bck';  
    ```  
  
3.  <span data-ttu-id="6c5d7-116">Crie uma rotina de backup de log:</span><span class="sxs-lookup"><span data-stu-id="6c5d7-116">Create a routine log backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Log.bck';  
    ```  
  
 <span data-ttu-id="6c5d7-117">O exemplo a seguir restaura os backups criados anteriormente, depois de criar um backup do final do log do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6c5d7-117">The following example restores the backups that are created previously, after creating a tail-log backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="6c5d7-118">(Esta etapa supõe que o disco de log pode ser acessado).</span><span class="sxs-lookup"><span data-stu-id="6c5d7-118">(This step assumes that the log disk can be accessed.)</span></span>  
  
 <span data-ttu-id="6c5d7-119">Primeiro, o exemplo cria um backup do final do log que captura o log ativo e deixa o banco de dados no estado Restaurando.</span><span class="sxs-lookup"><span data-stu-id="6c5d7-119">First, the example creates a tail-log backup of the database that captures the active log and leaves the database in the Restoring state.</span></span> <span data-ttu-id="6c5d7-120">Em seguida, o exemplo restaura um backup de banco de dados, aplica o backup de log de rotina criado anteriormente, e aplica o backup do final do log.</span><span class="sxs-lookup"><span data-stu-id="6c5d7-120">Then, the example restores the database backup, applies the routine log backup created previously, and applies the tail-log backup.</span></span> <span data-ttu-id="6c5d7-121">Por fim, o exemplo recupera o banco de dados em uma etapa separada.</span><span class="sxs-lookup"><span data-stu-id="6c5d7-121">Finally, the example recovers the database in a separate step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c5d7-122">O comportamento padrão é recuperar um banco de dados como parte da instrução que restaura o backup final.</span><span class="sxs-lookup"><span data-stu-id="6c5d7-122">The default behavior is to recover a database as part of the statement that restores the final backup.</span></span>  
  
```  
/* Example of restoring a to the point of failure */  
-- Step 1: Create a tail-log backup by using WITH NORECOVERY.  
BACKUP LOG AdventureWorks2012  
   TO DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 2: Restore the full database backup.  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Data.bck'  
   WITH NORECOVERY;  
GO  
-- Step 3: Restore the first transaction log backup.  
RESTORE LOG AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 4: Restore the tail-log backup.  
RESTORE LOG AdventureWorks2012  
   FROM  DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 5: Recover the database.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c5d7-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6c5d7-123">See Also</span></span>  
 <span data-ttu-id="6c5d7-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6c5d7-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="6c5d7-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6c5d7-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
