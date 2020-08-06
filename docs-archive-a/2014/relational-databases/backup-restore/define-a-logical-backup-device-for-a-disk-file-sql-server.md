---
title: Definir um dispositivo de backup lógico para um arquivo de disco (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
ms.assetid: 86331d43-c738-4523-ae3d-7d6700348ed1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8aa92296da81f984f260deace887c15f13443b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685816"
---
# <a name="define-a-logical-backup-device-for-a-disk-file-sql-server"></a><span data-ttu-id="77b15-102">Definir um dispositivo de backup lógico para um arquivo de disco (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="77b15-102">Define a Logical Backup Device for a Disk File (SQL Server)</span></span>
  <span data-ttu-id="77b15-103">Este tópico descreve como definir um dispositivo de backup lógico para uma arquivo de disco no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77b15-103">This topic describes how to define a logical backup device for a disk file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="77b15-104">Um dispositivo lógico é um nome definido pelo usuário que aponta para um dispositivo de backup físico específico (um arquivo de disco ou uma unidade de fita).</span><span class="sxs-lookup"><span data-stu-id="77b15-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="77b15-105">A inicialização do dispositivo físico acontece depois, quando um backup é gravado no dispositivo de backups.</span><span class="sxs-lookup"><span data-stu-id="77b15-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
 <span data-ttu-id="77b15-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="77b15-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="77b15-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="77b15-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="77b15-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="77b15-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="77b15-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="77b15-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="77b15-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="77b15-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="77b15-111">**Para definir um dispositivo de backup lógico para um arquivo de disco, usando:**</span><span class="sxs-lookup"><span data-stu-id="77b15-111">**To define a logical backup device for a disk file, using:**</span></span>  
  
     [<span data-ttu-id="77b15-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77b15-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="77b15-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77b15-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="77b15-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="77b15-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="77b15-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="77b15-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="77b15-116">O nome de dispositivo lógico deve ser exclusivo entre todos os dispositivos de backup lógicos na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="77b15-116">The logical device name must be unique among all the logical backup devices on the server instance.</span></span> <span data-ttu-id="77b15-117">Para exibir os nomes de dispositivo lógicos existentes, consulte a exibição de catálogo [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="77b15-117">To view the existing logical device names, query the [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) catalog view.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="77b15-118">Recomendações</span><span class="sxs-lookup"><span data-stu-id="77b15-118">Recommendations</span></span>  
  
-   <span data-ttu-id="77b15-119">Nós recomendamos que um disco de backup seja diferente dos discos de banco de dados e de log.</span><span class="sxs-lookup"><span data-stu-id="77b15-119">We recommend that a backup disk be a different disk than the database data and log disks.</span></span> <span data-ttu-id="77b15-120">Isso é necessário para garantir que será possível acessar os backups se houver falha no disco de dados ou de log.</span><span class="sxs-lookup"><span data-stu-id="77b15-120">This is necessary to make sure that you can access the backups if the data or log disk fails.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="77b15-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="77b15-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="77b15-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="77b15-122">Permissions</span></span>  
 <span data-ttu-id="77b15-123">Requer associação na função de servidor fixa **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="77b15-123">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="77b15-124">Requer permissão para gravar no disco.</span><span class="sxs-lookup"><span data-stu-id="77b15-124">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="77b15-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77b15-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-disk-file"></a><span data-ttu-id="77b15-126">Para definir um dispositivo de backup lógico para um arquivo de disco</span><span class="sxs-lookup"><span data-stu-id="77b15-126">To define a logical backup device for a disk file</span></span>  
  
1.  <span data-ttu-id="77b15-127">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="77b15-127">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="77b15-128">Expanda **Objetos de Servidor**e clique com o botão direito do mouse em **Dispositivos de Backup**.</span><span class="sxs-lookup"><span data-stu-id="77b15-128">Expand **Server Objects**, and right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="77b15-129">Clique em **Novo Dispositivo de Backup**.</span><span class="sxs-lookup"><span data-stu-id="77b15-129">Click **New Backup Device**.</span></span> <span data-ttu-id="77b15-130">A caixa de diálogo **Dispositivo de Backup** é aberta.</span><span class="sxs-lookup"><span data-stu-id="77b15-130">The **Backup Device** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="77b15-131">Coloque um nome de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77b15-131">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="77b15-132">Para o destino, clique em **Arquivo** e especifique o caminho completo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="77b15-132">For the destination, click **File** and specify the full path of the file.</span></span>  
  
6.  <span data-ttu-id="77b15-133">Para definir o dispositivo novo, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="77b15-133">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="77b15-134">Para fazer backup neste novo dispositivo, adicione-o ao campo **Fazer backup em:** na caixa de diálogo **Backup de Banco de dados** (**Geral**).</span><span class="sxs-lookup"><span data-stu-id="77b15-134">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="77b15-135">Para obter mais informações, veja [Criar um backup completo de banco de dados &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="77b15-135">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="77b15-136">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77b15-136">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-for-a-disk-file"></a><span data-ttu-id="77b15-137">Para definir um backup lógico para um arquivo de disco</span><span class="sxs-lookup"><span data-stu-id="77b15-137">To define a logical backup for a disk file</span></span>  
  
1.  <span data-ttu-id="77b15-138">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77b15-138">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="77b15-139">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="77b15-139">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="77b15-140">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="77b15-140">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="77b15-141">Este exemplo mostra como usar [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) para definir um dispositivo de backup lógico para um arquivo de disco.</span><span class="sxs-lookup"><span data-stu-id="77b15-141">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a disk file.</span></span> <span data-ttu-id="77b15-142">O exemplo adiciona o dispositivo de backup em disco denominado `mydiskdump`, com o nome físico `c:\dump\dump1.bak`.</span><span class="sxs-lookup"><span data-stu-id="77b15-142">The example adds the disk backup device named `mydiskdump`, with the physical name `c:\dump\dump1.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mydiskdump', 'c:\dump\dump1.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="77b15-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77b15-143">See Also</span></span>  
 <span data-ttu-id="77b15-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77b15-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="77b15-145">[Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="77b15-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="77b15-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77b15-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="77b15-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77b15-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="77b15-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77b15-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="77b15-149">[Definir um dispositivo de backup lógico para uma unidade de fita &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="77b15-149">[Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span></span>  
 [<span data-ttu-id="77b15-150">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77b15-150">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
