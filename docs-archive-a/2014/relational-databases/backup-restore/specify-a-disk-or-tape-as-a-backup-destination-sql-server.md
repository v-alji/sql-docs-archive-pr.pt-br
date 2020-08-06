---
title: Especificar um disco ou fita como destino de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
- backups [SQL Server], creating
- tape backup devices, backing up
ms.assetid: e391f452-ed8c-4b40-b846-ac3881271b94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a0f8ec5d9741e42f3b7d8eda8ebdba23622982d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680482"
---
# <a name="specify-a-disk-or-tape-as-a-backup-destination-sql-server"></a><span data-ttu-id="af23e-102">Especificar um disco ou fita como destino de backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="af23e-102">Specify a Disk or Tape As a Backup Destination (SQL Server)</span></span>
  <span data-ttu-id="af23e-103">Este tópico descreve como especificar um disco ou uma fita como destino de backup no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af23e-103">This topic describes how to specify a disk or tape as a backup destination in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af23e-104">O suporte a dispositivos de backup em fita será removido em uma versão futura do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af23e-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="af23e-105">Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam.</span><span class="sxs-lookup"><span data-stu-id="af23e-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="af23e-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="af23e-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="af23e-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="af23e-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="af23e-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="af23e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="af23e-109">**Para especificar um disco ou uma fita como um destino de backup usando:**</span><span class="sxs-lookup"><span data-stu-id="af23e-109">**To specify a disk or tape as a backup destination, using:**</span></span>  
  
     [<span data-ttu-id="af23e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af23e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="af23e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af23e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="af23e-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="af23e-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="af23e-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="af23e-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="af23e-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="af23e-114">Permissions</span></span>  
 <span data-ttu-id="af23e-115">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="af23e-115">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="af23e-116">Os problemas de propriedade e permissão no arquivo físico do dispositivo de backup podem interferir em uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="af23e-116">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="af23e-117">deve ser capaz de ler e gravar no dispositivo; a conta sob a qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa deve ter permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="af23e-117">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="af23e-118">No entanto, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que adiciona uma entrada para um dispositivo de backup nas tabelas do sistema, não verifica permissões de acesso a arquivos.</span><span class="sxs-lookup"><span data-stu-id="af23e-118">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="af23e-119">Esses problemas no arquivo físico do dispositivo de backup podem não aparecer até que o recurso físico seja acessado quando o backup ou restauração é tentado.</span><span class="sxs-lookup"><span data-stu-id="af23e-119">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="af23e-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af23e-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="af23e-121">Para especificar um disco ou uma fita como um destino de backup</span><span class="sxs-lookup"><span data-stu-id="af23e-121">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="af23e-122">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="af23e-122">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="af23e-123">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="af23e-123">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="af23e-124">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Backup**.</span><span class="sxs-lookup"><span data-stu-id="af23e-124">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="af23e-125">Será exibida a caixa de diálogo **Backup de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="af23e-125">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="af23e-126">Na seção **Destino** da página **Geral** , clique em **Disco** ou **Fita**.</span><span class="sxs-lookup"><span data-stu-id="af23e-126">In the **Destination** section of the **General** page, click **Disk** or **Tape**.</span></span> <span data-ttu-id="af23e-127">Para selecionar os caminhos de até 64 unidades de disco ou fita que contêm um único conjunto de mídia, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="af23e-127">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span>  
  
     <span data-ttu-id="af23e-128">Para remover um destino de backup, selecione-o e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="af23e-128">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="af23e-129">Para exibir o conteúdo de um destino de backup, selecione-o e clique em **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="af23e-129">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="af23e-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af23e-130">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="af23e-131">Para especificar um disco ou uma fita como um destino de backup</span><span class="sxs-lookup"><span data-stu-id="af23e-131">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="af23e-132">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af23e-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="af23e-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="af23e-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="af23e-134">Na instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql) , especifique o arquivo ou dispositivo e seu nome físico.</span><span class="sxs-lookup"><span data-stu-id="af23e-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the file or device and its physical name.</span></span> <span data-ttu-id="af23e-135">Este exemplo executa o backup do banco de dados do `AdventureWorks2012` para o arquivo em disco `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span><span class="sxs-lookup"><span data-stu-id="af23e-135">This example backs up the `AdventureWorks2012` database to the disk file `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="af23e-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af23e-136">See Also</span></span>  
 <span data-ttu-id="af23e-137">[Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="af23e-137">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="af23e-138">[Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="af23e-138">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="af23e-139">[Definir um dispositivo de backup lógico para um arquivo de disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="af23e-139">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 <span data-ttu-id="af23e-140">[Criar um backup diferencial de banco de dados &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="af23e-140">[Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="af23e-141">Definir um dispositivo de backup lógico para uma unidade de fita &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="af23e-141">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
