---
title: Inicializar uma assinatura transacional de um backup (Programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: d0637fc4-27cc-4046-98ea-dc86b7a3bd75
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1563d58f2d54f77680781e22a162112ade1658e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569882"
---
# <a name="initialize-a-transactional-subscription-from-a-backup-replication-transact-sql-programming"></a><span data-ttu-id="60b97-102">Inicializar uma assinatura transacional de um backup (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="60b97-102">Initialize a Transactional Subscription from a Backup (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="60b97-103">Embora uma assinatura a uma publicação transacional seja geralmente inicializada com um instantâneo, é possível inicializar uma assinatura de backup usando procedimentos de replicação armazenados.</span><span class="sxs-lookup"><span data-stu-id="60b97-103">Although a subscription to a transactional publication is typically initialized with a snapshot, a subscription can be initialized from a backup using replication stored procedures.</span></span> <span data-ttu-id="60b97-104">Para obter mais informações, consulte [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="60b97-104">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
### <a name="to-initialize-a-transactional-subscriber-from-a-backup"></a><span data-ttu-id="60b97-105">Para inicializar um assinante transacional a partir de backup</span><span class="sxs-lookup"><span data-stu-id="60b97-105">To initialize a transactional subscriber from a backup</span></span>  
  
1.  <span data-ttu-id="60b97-106">Para uma publicação existente, certifique-se de que a publicação dê suporte à capacidade de inicializar do backup, executando [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) no Publicador no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="60b97-106">For an existing publication, ensure that the publication supports the ability to initialize from backup by executing [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="60b97-107">Observe o valor de **allow_initialize_from_backup** no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="60b97-107">Note the value of **allow_initialize_from_backup** in the result set.</span></span>  
  
    -   <span data-ttu-id="60b97-108">Se o valor for **1**, a publicação oferece suporte a essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="60b97-108">If the value is **1**, the publication supports this functionality.</span></span>  
  
    -   <span data-ttu-id="60b97-109">Se o valor for **0**, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) no Publicador do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="60b97-109">If the value is **0**, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="60b97-110">Especifique um valor de **allow_initialize_from_backup** para \*\* \@ Propriedade\*\* e um valor de `true` para \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="60b97-110">Specify a value of **allow_initialize_from_backup** for **\@property** and a value of `true` for **\@value**.</span></span>  
  
2.  <span data-ttu-id="60b97-111">Para uma nova publicação, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) no Publicador do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="60b97-111">For a new publication, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="60b97-112">Especifique um valor de `true` para **allow_initialize_from_backup**.</span><span class="sxs-lookup"><span data-stu-id="60b97-112">Specify a value of `true` for **allow_initialize_from_backup**.</span></span> <span data-ttu-id="60b97-113">Para obter mais informações, consulte [Criar uma assinatura](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="60b97-113">For more information, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="60b97-114">Para evitar perder dados do assinante, ao usar **sp_addpublication** com `@allow_initialize_from_backup = N'true'`, sempre use `@immediate_sync = N'true'`.</span><span class="sxs-lookup"><span data-stu-id="60b97-114">To avoid missing subscriber data, when using **sp_addpublication** with `@allow_initialize_from_backup = N'true'`, always use `@immediate_sync = N'true'`.</span></span>  
  
3.  <span data-ttu-id="60b97-115">Crie um backup do banco de dados de publicação usando a instrução [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60b97-115">Create a backup of the publication database using the [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
4.  <span data-ttu-id="60b97-116">Restaure o backup no Assinante usando a instrução [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60b97-116">Restore the backup on the Subscriber using the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement.</span></span>  
  
5.  <span data-ttu-id="60b97-117">No Publicador no banco de dados de publicação, execute o procedimento armazenado [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60b97-117">At the Publisher on the publication database, execute the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="60b97-118">Especifique os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="60b97-118">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="60b97-119">\*\* \@ sync_type\*\* -um valor de **inicializar com backup**.</span><span class="sxs-lookup"><span data-stu-id="60b97-119">**\@sync_type** - a value of **initialize with backup**.</span></span>  
  
    -   <span data-ttu-id="60b97-120">\*\* \@ backupdevicetype\*\* -o tipo de dispositivo de backup: **lógico** (padrão), **disco**ou **fita**.</span><span class="sxs-lookup"><span data-stu-id="60b97-120">**\@backupdevicetype** - the type of backup device: **logical** (default), **disk**, or **tape**.</span></span>  
  
    -   <span data-ttu-id="60b97-121">\*\* \@ BackupDeviceName\*\* -o dispositivo de backup lógico ou físico a ser usado para a restauração.</span><span class="sxs-lookup"><span data-stu-id="60b97-121">**\@backupdevicename** - the logical or physical backup device to use for the restore.</span></span>  
  
         <span data-ttu-id="60b97-122">Para um dispositivo lógico, especifique o nome do dispositivo de backup especificado quando **sp_addumpdevice** foi usado para criar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60b97-122">For a logical device, specify the name of the backup device specified when **sp_addumpdevice** was used to create the device.</span></span>  
  
         <span data-ttu-id="60b97-123">Para um dispositivo físico, especifique um caminho completo e nome de arquivo, como `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` ou `TAPE = '\\.\TAPE0'`.</span><span class="sxs-lookup"><span data-stu-id="60b97-123">For a physical device, specify a complete path and file name, such as `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` or `TAPE = '\\.\TAPE0'`.</span></span>  
  
    -   <span data-ttu-id="60b97-124">Adicional \*\* \@ senha\*\* -uma senha que foi fornecida quando o conjunto de backup foi criado.</span><span class="sxs-lookup"><span data-stu-id="60b97-124">(Optional) **\@password** - a password that was provided when the backup set was created.</span></span>  
  
    -   <span data-ttu-id="60b97-125">Adicional \*\* \@ MEDIAPASSWORD\*\* -uma senha que foi fornecida quando o conjunto de mídias foi formatado.</span><span class="sxs-lookup"><span data-stu-id="60b97-125">(Optional) **\@mediapassword** - a password that was provided when the media set was formatted.</span></span>  
  
    -   <span data-ttu-id="60b97-126">Adicional \*\* \@ fileidhint\*\* -identificador para o conjunto de backup a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="60b97-126">(Optional) **\@fileidhint** - identifier for the backup set to be restored.</span></span> <span data-ttu-id="60b97-127">Por exemplo, especificar **1** indica o primeiro conjunto de backup na mídia de backup e **2** indica o segundo conjunto de backup.</span><span class="sxs-lookup"><span data-stu-id="60b97-127">For example, specifying **1** indicates the first backup set on the backup medium and **2** indicates the second backup set.</span></span>  
  
    -   <span data-ttu-id="60b97-128">(Opcional para dispositivos de fita) \*\* \@ Unload\*\* – especifique um valor de **1** (padrão) se a fita deve ser descarregada da unidade após a conclusão da restauração e **0** se ela não deve ser descarregada.</span><span class="sxs-lookup"><span data-stu-id="60b97-128">(Optional for tape devices) **\@unload** - specify a value of **1** (default) if the tape should be unloaded from the drive after the restore is complete and **0** if it should not be unloaded.</span></span>  
  
6.  <span data-ttu-id="60b97-129">(Opcional) Para uma assinatura pull, execute [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) e [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) no Assinante no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="60b97-129">(Optional) For a pull subscription, execute [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) and [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="60b97-130">Para obter mais informações, consulte [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="60b97-130">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
7.  <span data-ttu-id="60b97-131">(Opcional) Iniciar o Distribution Agent.</span><span class="sxs-lookup"><span data-stu-id="60b97-131">(Optional) Start the Distribution Agent.</span></span> <span data-ttu-id="60b97-132">Para obter mais informações, consulte [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) ou [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="60b97-132">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) or [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b97-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60b97-133">See Also</span></span>  
 <span data-ttu-id="60b97-134">[Copiar bancos de dados com backup e restauração](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="60b97-134">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="60b97-135">Fazer backup e restaurar bancos de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="60b97-135">Back Up and Restore of SQL Server Databases</span></span>](../backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
  
