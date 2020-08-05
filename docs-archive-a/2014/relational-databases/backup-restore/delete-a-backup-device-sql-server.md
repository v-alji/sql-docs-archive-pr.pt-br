---
title: Excluir um dispositivo de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], deleting devices
- backup devices [SQL Server], deleting
- deleting backup devices
- removing backup devices
- backing up databases [SQL Server], backup devices
ms.assetid: 7be62480-ed6a-4262-a071-1feba73b1c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8734e587a8ecde315fb17120511455a59e38901
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573141"
---
# <a name="delete-a-backup-device-sql-server"></a><span data-ttu-id="ec542-102">Excluir um dispositivo de backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ec542-102">Delete a Backup Device (SQL Server)</span></span>
  <span data-ttu-id="ec542-103">Este tópico descreve como excluir um dispositivo de backup no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec542-103">This topic describes how to delete a backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ec542-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ec542-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ec542-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ec542-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ec542-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="ec542-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ec542-107">**Para excluir um dispositivo de backup, usando:**</span><span class="sxs-lookup"><span data-stu-id="ec542-107">**To delete a backup device, using:**</span></span>  
  
     [<span data-ttu-id="ec542-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ec542-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ec542-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ec542-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ec542-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ec542-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ec542-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="ec542-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ec542-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="ec542-112">Permissions</span></span>  
 <span data-ttu-id="ec542-113">Requer associação na função de servidor fixa **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="ec542-113">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ec542-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ec542-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="ec542-115">Para excluir um dispositivo de backup</span><span class="sxs-lookup"><span data-stu-id="ec542-115">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="ec542-116">Depois de conectar-se à instância adequada do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], no Pesquisador de Objeto, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="ec542-116">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ec542-117">Expanda **Objetos de Servidor**e depois **Dispositivos de Backup**.</span><span class="sxs-lookup"><span data-stu-id="ec542-117">Expand **Server Objects**, and then expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="ec542-118">Clique com o botão direito do mouse no dispositivo desejado e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="ec542-118">Right-click the device you want, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="ec542-119">Na caixa de diálogo **Excluir Objeto** , verifique se o nome correto do dispositivo aparece na coluna **Nome do Objeto** .</span><span class="sxs-lookup"><span data-stu-id="ec542-119">In the **Delete Object** dialog box, verify that the correct device name appears in the **Object Name** column.</span></span>  
  
5.  <span data-ttu-id="ec542-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec542-120">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ec542-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ec542-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="ec542-122">Para excluir um dispositivo de backup</span><span class="sxs-lookup"><span data-stu-id="ec542-122">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="ec542-123">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec542-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ec542-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ec542-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ec542-125">Copie e cole o seguinte exemplo na consulta.</span><span class="sxs-lookup"><span data-stu-id="ec542-125">Copy and paste the following example into the query.</span></span> <span data-ttu-id="ec542-126">Este exemplo mostra como usar [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) para excluir um dispositivo de backup.</span><span class="sxs-lookup"><span data-stu-id="ec542-126">This example shows how to use [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) to delete a backup device.</span></span> <span data-ttu-id="ec542-127">Execute o primeiro exemplo para criar o dispositivo de backup `mybackupdisk` e o nome físico `c:\backup\backup1.bak`.</span><span class="sxs-lookup"><span data-stu-id="ec542-127">Execute the first example to create the `mybackupdisk` backup device and the physical name `c:\backup\backup1.bak`.</span></span> <span data-ttu-id="ec542-128">Execute `sp_dropdevice` para excluir o dispositivo de backup `mybackupdisk`.</span><span class="sxs-lookup"><span data-stu-id="ec542-128">Execute `sp_dropdevice` to delete the `mybackupdisk` backup device.</span></span> <span data-ttu-id="ec542-129">O parâmetro `delfile` exclui o nome físico.</span><span class="sxs-lookup"><span data-stu-id="ec542-129">The `delfile` parameter deletes the physical name.</span></span>  
  
```sql  
--Define a backup device and physical name.   
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mybackupdisk', 'c:\backup\backup1.bak' ;  
GO  
--Delete the backup device and the physical name.  
USE AdventureWorks2012 ;  
GO  
EXEC sp_dropdevice ' mybackupdisk ', 'delfile' ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec542-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec542-130">See Also</span></span>  
 <span data-ttu-id="ec542-131">[Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec542-131">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="ec542-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec542-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="ec542-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec542-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ec542-134">[Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec542-134">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="ec542-135">sp_addumpdevice &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec542-135">sp_addumpdevice &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)  
  
  
