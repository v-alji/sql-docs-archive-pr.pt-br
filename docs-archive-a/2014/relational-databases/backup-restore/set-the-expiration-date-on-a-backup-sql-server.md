---
title: Definir a data de expiração em um backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], expiration dates
- expiration [SQL Server]
- database backups [SQL Server], expiration dates
ms.assetid: 76e814df-6487-4893-9f09-7759f1863a5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9185222df93e0a1150256535526ba910c593cf6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572113"
---
# <a name="set-the-expiration-date-on-a-backup-sql-server"></a><span data-ttu-id="6faad-102">Definir a data de validade em um backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6faad-102">Set the Expiration Date on a Backup (SQL Server)</span></span>
  <span data-ttu-id="6faad-103">Este tópico descreve como definir a data de validade em um backup no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6faad-103">This topic describes how to set the expiration date on a backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6faad-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="6faad-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6faad-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6faad-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6faad-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="6faad-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6faad-107">**Para definir a data de validade em um backup usando:**</span><span class="sxs-lookup"><span data-stu-id="6faad-107">**To set the expiration date on a backup, using:**</span></span>  
  
     [<span data-ttu-id="6faad-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6faad-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6faad-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6faad-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6faad-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6faad-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6faad-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="6faad-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6faad-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="6faad-112">Permissions</span></span>  
 <span data-ttu-id="6faad-113">As permissões BACKUP DATABASE e BACKUP LOG usam como padrão os membros da função de servidor fixa **sysadmin** e as funções de banco de dados fixas **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="6faad-113">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="6faad-114">Os problemas de propriedade e permissão no arquivo físico do dispositivo de backup podem interferir em uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="6faad-114">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6faad-115">deve ser capaz de ler e gravar no dispositivo; a conta sob a qual o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executa deve ter permissões de gravação.</span><span class="sxs-lookup"><span data-stu-id="6faad-115">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="6faad-116">No entanto, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que adiciona uma entrada para um dispositivo de backup nas tabelas do sistema, não verifica permissões de acesso a arquivos.</span><span class="sxs-lookup"><span data-stu-id="6faad-116">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="6faad-117">Esses problemas no arquivo físico do dispositivo de backup podem não aparecer até que o recurso físico seja acessado quando o backup ou restauração é tentado.</span><span class="sxs-lookup"><span data-stu-id="6faad-117">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6faad-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6faad-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="6faad-119">Para definir a data de validade em um backup</span><span class="sxs-lookup"><span data-stu-id="6faad-119">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="6faad-120">Depois de se conectar à instância apropriada do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], em Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="6faad-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="6faad-121">Expanda **Bancos de Dados**e, dependendo do banco de dados, selecione um banco de dados de usuário ou expanda **Bancos de Dados do Sistema** e selecione um banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="6faad-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="6faad-122">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Backup**.</span><span class="sxs-lookup"><span data-stu-id="6faad-122">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="6faad-123">Será exibida a caixa de diálogo **Backup de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="6faad-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="6faad-124">Na página **Geral** , em **O conjunto de backup irá expirar**, especifique uma data de validade para indicar quando o conjunto de backup poderá ser substituído por outro backup:</span><span class="sxs-lookup"><span data-stu-id="6faad-124">On the **General** page, for **Backup set will expire**, specify an expiration date to indicate when the backup set can be overwritten by another backup:</span></span>  
  
    -   <span data-ttu-id="6faad-125">Para que o conjunto de backup expire depois de um número específico de dias, clique em **Depois** (a opção padrão) e digite quantos dias depois da criação do conjunto ele deve expirar.</span><span class="sxs-lookup"><span data-stu-id="6faad-125">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="6faad-126">Esse valor pode ser de 0 a 99999 dias; 0 dia significa que o conjunto de backup nunca vai expirar.</span><span class="sxs-lookup"><span data-stu-id="6faad-126">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="6faad-127">O valor padrão é definido na opção **Retenção de mídia de backup padrão (em dias)** da caixa de diálogo **Propriedades do Servidor** (página**Configurações do Banco de Dados** ).</span><span class="sxs-lookup"><span data-stu-id="6faad-127">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="6faad-128">Para acessar, clique com o botão direito do mouse no nome do servidor em Pesquisador de Objetos e selecione propriedades. Depois, selecione a página **Configurações de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="6faad-128">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="6faad-129">Para que o conjunto de backup expire em uma data específica, clique no campo **Em**e digite a data de expiração do conjunto.</span><span class="sxs-lookup"><span data-stu-id="6faad-129">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6faad-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6faad-130">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="6faad-131">Para definir a data de validade em um backup</span><span class="sxs-lookup"><span data-stu-id="6faad-131">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="6faad-132">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6faad-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6faad-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6faad-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6faad-134">Na instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql) , especifique a opção EXPIREDATE ou RETAINDAYS para determinar quando o [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] pode substituir o backup.</span><span class="sxs-lookup"><span data-stu-id="6faad-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify either the EXPIREDATE or RETAINDAYS option to determine when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] can overwrite the backup.</span></span> <span data-ttu-id="6faad-135">Se nenhuma opção estiver especificada, a data de validade será determinada pela definição da configuração de servidor de [retenção de mídia](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) .</span><span class="sxs-lookup"><span data-stu-id="6faad-135">If neither option is specified, the expiration date is determined by the [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) server configuration setting.</span></span> <span data-ttu-id="6faad-136">Este exemplo usa a opção `EXPIREDATE` para especificar a data de validade de 30 de junho de 2015 (`6/30/2015`).</span><span class="sxs-lookup"><span data-stu-id="6faad-136">This example uses the `EXPIREDATE` option to specify an expiration date of June 30, 2015 (`6/30/2015`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH EXPIREDATE = '6/30/2015' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6faad-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6faad-137">See Also</span></span>  
 <span data-ttu-id="6faad-138">[Criar um backup completo de banco de dados &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6faad-138">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="6faad-139">[Fazer backup de arquivos e de grupos de arquivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6faad-139">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="6faad-140">[Fazer backup de um log de transações &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6faad-140">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="6faad-141">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6faad-141">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
