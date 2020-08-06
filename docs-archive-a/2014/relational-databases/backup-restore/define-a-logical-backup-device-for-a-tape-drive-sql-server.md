---
title: Definir um dispositivo de backup lógico para uma unidade de fita (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- tape backup devices, creating
ms.assetid: 66f36e1d-0287-4fac-8a51-71f9f0d7ad5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8728df2cc0b5907e51da84ed9e77d897a1718d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685813"
---
# <a name="define-a-logical-backup-device-for-a-tape-drive-sql-server"></a><span data-ttu-id="8b62d-102">Definir um dispositivo de backup lógico para uma unidade de fita (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8b62d-102">Define a Logical Backup Device for a Tape Drive (SQL Server)</span></span>
  <span data-ttu-id="8b62d-103">Este tópico descreve como definir um dispositivo de backup lógico para uma unidade de fita no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b62d-103">This topic describes how to define a logical backup device for a tape drive in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8b62d-104">Um dispositivo lógico é um nome definido pelo usuário que aponta para um dispositivo de backup físico específico (um arquivo de disco ou uma unidade de fita).</span><span class="sxs-lookup"><span data-stu-id="8b62d-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="8b62d-105">A inicialização do dispositivo físico acontece depois, quando um backup é gravado no dispositivo de backups.</span><span class="sxs-lookup"><span data-stu-id="8b62d-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b62d-106">O suporte a dispositivos de backup em fita será removido em uma versão futura do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b62d-106">Support for tape backup devices will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8b62d-107">Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam.</span><span class="sxs-lookup"><span data-stu-id="8b62d-107">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="8b62d-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="8b62d-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8b62d-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="8b62d-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8b62d-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8b62d-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8b62d-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="8b62d-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8b62d-112">**Para definir um dispositivo de backup lógico para uma unidade de fita usando:**</span><span class="sxs-lookup"><span data-stu-id="8b62d-112">**To define a logical backup device for a tape drive, using:**</span></span>  
  
     [<span data-ttu-id="8b62d-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8b62d-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8b62d-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8b62d-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8b62d-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8b62d-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8b62d-116">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="8b62d-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8b62d-117">A unidade ou as unidades de fita devem ter o suporte do sistema operacional Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="8b62d-117">The tape drive or drives must be supported by the Microsoft Windows operating system.</span></span>  
  
-   <span data-ttu-id="8b62d-118">O dispositivo de fita deve estar conectado fisicamente ao computador que está executando uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b62d-118">The tape device must be connected physically to the computer that is running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8b62d-119">O backup em dispositivos de fita remotos não é suportado.</span><span class="sxs-lookup"><span data-stu-id="8b62d-119">Backing up to remote tape devices is not supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8b62d-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="8b62d-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8b62d-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="8b62d-121">Permissions</span></span>  
 <span data-ttu-id="8b62d-122">Requer associação na função de servidor fixa **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="8b62d-122">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="8b62d-123">Requer permissão para gravar no disco.</span><span class="sxs-lookup"><span data-stu-id="8b62d-123">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8b62d-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8b62d-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="8b62d-125">Para definir um dispositivo de backup lógico para uma unidade de fita</span><span class="sxs-lookup"><span data-stu-id="8b62d-125">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="8b62d-126">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="8b62d-126">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="8b62d-127">Expanda **Objetos de Servidor**e clique com o botão direito do mouse em **Dispositivos de Backup**.</span><span class="sxs-lookup"><span data-stu-id="8b62d-127">Expand **Server Objects**, and then right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="8b62d-128">Clique em **Novo Dispositivo de Backup**, que abre a caixa de diálogo **Dispositivo de Backup** .</span><span class="sxs-lookup"><span data-stu-id="8b62d-128">Click **New Backup Device**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="8b62d-129">Coloque um nome de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b62d-129">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="8b62d-130">Para o destino, clique em **Fita** e selecione uma unidade de fita que ainda não esteja associada a outro dispositivo de backup.</span><span class="sxs-lookup"><span data-stu-id="8b62d-130">For the destination, click **Tape** and select a tape drive that is not already associated with another backup device.</span></span> <span data-ttu-id="8b62d-131">Se nenhuma das unidade de fita estiver disponível, a opção **Fita** estará inativa.</span><span class="sxs-lookup"><span data-stu-id="8b62d-131">If no such tape drives are available, the **Tape** option is inactive.</span></span>  
  
6.  <span data-ttu-id="8b62d-132">Para definir o dispositivo novo, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b62d-132">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="8b62d-133">Para fazer backup neste novo dispositivo, adicione-o ao campo **Fazer backup em:** na caixa de diálogo **Backup de Banco de dados** (**Geral**).</span><span class="sxs-lookup"><span data-stu-id="8b62d-133">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="8b62d-134">Para obter mais informações, veja [Criar um backup completo de banco de dados &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8b62d-134">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8b62d-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8b62d-135">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="8b62d-136">Para definir um dispositivo de backup lógico para uma unidade de fita</span><span class="sxs-lookup"><span data-stu-id="8b62d-136">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="8b62d-137">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b62d-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8b62d-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8b62d-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8b62d-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8b62d-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8b62d-140">Este exemplo mostra como usar [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) para definir um dispositivo de backup lógico para uma fita.</span><span class="sxs-lookup"><span data-stu-id="8b62d-140">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a tape.</span></span> <span data-ttu-id="8b62d-141">O exemplo adiciona o dispositivo de backup em fita denominado `tapedump1`, com o nome físico `\\.\tape0`.</span><span class="sxs-lookup"><span data-stu-id="8b62d-141">The example adds the tape backup device named `tapedump1`, with the physical name `\\.\tape0`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'tape', 'tapedump1', '\\.\tape0' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b62d-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b62d-142">See Also</span></span>  
 <span data-ttu-id="8b62d-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b62d-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="8b62d-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b62d-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="8b62d-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b62d-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="8b62d-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b62d-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="8b62d-147">[Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8b62d-147">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="8b62d-148">[Definir um dispositivo de backup lógico para um arquivo de disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8b62d-148">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="8b62d-149">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b62d-149">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
