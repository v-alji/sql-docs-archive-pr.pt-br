---
title: Exibir o conteúdo de um arquivo ou fita de backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- displaying backup content
- viewing backup content
- tape backup devices, viewing contents
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
ms.assetid: cd6674a2-ca55-4b5a-a971-878ba001821e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 044519b64d41fbbdfc9302ce24369ab282727f67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681705"
---
# <a name="view-the-contents-of-a-backup-tape-or-file-sql-server"></a><span data-ttu-id="3021e-102">Exibir o conteúdo de um arquivo ou fita de backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3021e-102">View the Contents of a Backup Tape or File (SQL Server)</span></span>
  <span data-ttu-id="3021e-103">Este tópico descreve como exibir o conteúdo de uma fita ou arquivo de backup no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3021e-103">This topic describes how to view the content of a backup tape or file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3021e-104">O suporte a dispositivos de backup em fita será removido em uma versão futura do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3021e-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="3021e-105">Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam.</span><span class="sxs-lookup"><span data-stu-id="3021e-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="3021e-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3021e-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3021e-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3021e-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3021e-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="3021e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3021e-109">**Para exibir o conteúdo de um arquivo ou fita de backup, usando:**</span><span class="sxs-lookup"><span data-stu-id="3021e-109">**To view the content of a backup tape or file, using:**</span></span>  
  
     [<span data-ttu-id="3021e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3021e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3021e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3021e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3021e-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3021e-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3021e-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="3021e-113">Security</span></span>  
 <span data-ttu-id="3021e-114">Para obter informações sobre segurança, veja [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3021e-114">For information about security, see [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3021e-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="3021e-115">Permissions</span></span>  
 <span data-ttu-id="3021e-116">No [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e em versões posteriores, a obtenção de informações sobre um conjunto ou dispositivo de backup exige a permissão CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3021e-116">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="3021e-117">Para obter mais informações, veja [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3021e-117">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3021e-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3021e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="3021e-119">Para exibir o conteúdo de um arquivo ou fita de backup</span><span class="sxs-lookup"><span data-stu-id="3021e-119">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="3021e-120">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="3021e-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3021e-121">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="3021e-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="3021e-122">Clique com o botão direito do mouse no banco de dados do qual deseja fazer backup, aponte para **Tarefas**e clique em **Fazer Backup**.</span><span class="sxs-lookup"><span data-stu-id="3021e-122">Right-click the database you want to backup, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="3021e-123">Será exibida a caixa de diálogo **Backup de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="3021e-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="3021e-124">Na seção **Destino** da página **Geral** , clique em **Disco** ou **Fita**.</span><span class="sxs-lookup"><span data-stu-id="3021e-124">In the **Destination** section of the **General** page, click either **Disk** or **Tape**.</span></span> <span data-ttu-id="3021e-125">Na caixa de listagem **Backup para** , procure o arquivo em disco ou fita que deseja.</span><span class="sxs-lookup"><span data-stu-id="3021e-125">In the **Back up to** list box, look for the disk file or tape you want.</span></span>  
  
     <span data-ttu-id="3021e-126">Se o arquivo em disco ou fita não for exibido na caixa de listagem, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3021e-126">If the disk file or tape is not displayed in the list-box, click **Add**.</span></span> <span data-ttu-id="3021e-127">Selecione um nome de arquivo ou unidade de fita.</span><span class="sxs-lookup"><span data-stu-id="3021e-127">Select a file name or tape drive.</span></span> <span data-ttu-id="3021e-128">Para adicioná-lo à caixa de listagem **Fazer backup em** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3021e-128">To add it to the **Back up to** list-box, click **OK**.</span></span>  
  
5.  <span data-ttu-id="3021e-129">Na caixa de listagem **Fazer backup em** , selecione o caminho do disco ou da unidade de fita que você deseja exibir e clique em **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="3021e-129">In the **Back up to** list-box, select the path of the disk or tape drive you want to view, and click **Contents**.</span></span> <span data-ttu-id="3021e-130">Essa ação abre a caixa de diálogo **Conteúdos do dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="3021e-130">This opens the **Device Contents** dialog box.</span></span>  
  
6.  <span data-ttu-id="3021e-131">O painel direito exibe informações sobre o conjunto de mídias definido e conjuntos de backup no arquivo ou fita selecionado.</span><span class="sxs-lookup"><span data-stu-id="3021e-131">The right-hand pane displays information about the media set and backup sets on the selected tape or file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3021e-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3021e-132">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="3021e-133">Para exibir o conteúdo de um arquivo ou fita de backup</span><span class="sxs-lookup"><span data-stu-id="3021e-133">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="3021e-134">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3021e-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3021e-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3021e-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3021e-136">Use instrução [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3021e-136">Use the [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) statement.</span></span> <span data-ttu-id="3021e-137">Este exemplo retorna informações sobre o arquivo chamado `AdventureWorks2012-FullBackup.bak`:</span><span class="sxs-lookup"><span data-stu-id="3021e-137">This example returns information about the file named `AdventureWorks2012-FullBackup.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
RESTORE HEADERONLY   
FROM DISK = N'C:\AdventureWorks2012-FullBackup.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3021e-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3021e-138">See Also</span></span>  
 <span data-ttu-id="3021e-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3021e-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="3021e-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3021e-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="3021e-141">[conjunto de backup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3021e-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="3021e-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3021e-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="3021e-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3021e-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="3021e-144">[Dispositivos de backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3021e-144">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="3021e-145">[Definir um dispositivo de backup lógico para um arquivo de disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3021e-145">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="3021e-146">Definir um dispositivo de backup lógico para uma unidade de fita &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3021e-146">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
