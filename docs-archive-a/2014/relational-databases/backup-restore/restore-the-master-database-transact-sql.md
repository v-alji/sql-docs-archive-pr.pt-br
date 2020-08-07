---
title: Restaurar o banco de dados mestre (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- master database [SQL Server], restoring
ms.assetid: c83d802c-e84e-4458-b3ca-173d9ba32f73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c9cb078b7af60fc5e060bcb144fc9cbaee8ecf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581403"
---
# <a name="restore-the-master-database-transact-sql"></a><span data-ttu-id="e719a-102">Restaurar o banco de dados mestre (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e719a-102">Restore the master Database (Transact-SQL)</span></span>
  <span data-ttu-id="e719a-103">Este tópico explica como restaurar o banco de dados **master** com base em um backup de banco de dados completo.</span><span class="sxs-lookup"><span data-stu-id="e719a-103">This topic explains how to restore the **master** database from a full database backup.</span></span>  
  
### <a name="to-restore-the-master-database"></a><span data-ttu-id="e719a-104">Para restaurar o banco de dados mestre</span><span class="sxs-lookup"><span data-stu-id="e719a-104">To restore the master database</span></span>  
  
1.  <span data-ttu-id="e719a-105">Inicie uma instância de servidor no modo de usuário único.</span><span class="sxs-lookup"><span data-stu-id="e719a-105">Start the server instance in single-user mode.</span></span>  
  
     <span data-ttu-id="e719a-106">Para obter informações sobre como especificar o parâmetro de inicialização de usuário único ( **-m**), veja [Configurar opções de inicialização do servidor &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="e719a-106">For information about how to specify the single-user startup parameter (**-m**), see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
2.  <span data-ttu-id="e719a-107">Para restaurar um backup de banco de dados completo do **master**, use a seguinte instrução [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="e719a-107">To restore a full database backup of **master**, use the following [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="e719a-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span><span class="sxs-lookup"><span data-stu-id="e719a-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span></span>  
  
     <span data-ttu-id="e719a-109">A opção REPLACE instrui o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a restaurar o banco de dados especificado mesmo quando um banco de dados do mesmo nome já existir.</span><span class="sxs-lookup"><span data-stu-id="e719a-109">The REPLACE option instructs [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to restore the specified database even when a database of the same name already exists.</span></span> <span data-ttu-id="e719a-110">O banco de dados existente, se houver, será excluído.</span><span class="sxs-lookup"><span data-stu-id="e719a-110">The existing database, if any, is deleted.</span></span> <span data-ttu-id="e719a-111">Em modo de usuário único, é recomendável inserir a instrução RESTORE DATABASE no [utilitário sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e719a-111">In single-user mode, we recommend that you enter the RESTORE DATABASE statement in the [sqlcmd utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="e719a-112">Para obter mais informações, consulte [Usar o Utilitário sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e719a-112">For more information, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e719a-113">Depois que o **master** é restaurado, a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é encerrada e o processo **sqlcmd** é concluído.</span><span class="sxs-lookup"><span data-stu-id="e719a-113">After **master** is restored, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] shuts down and terminates the **sqlcmd** process.</span></span> <span data-ttu-id="e719a-114">Antes de reiniciar a instância do servidor, remova o parâmetro de inicialização de usuário único.</span><span class="sxs-lookup"><span data-stu-id="e719a-114">Before you restart the server instance, remove the single-user startup parameter.</span></span> <span data-ttu-id="e719a-115">Para obter mais informações, veja [Configurar opções de inicialização do servidor &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="e719a-115">For more information, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
3.  <span data-ttu-id="e719a-116">Reinicie a instância do servidor e continue outras etapas de recuperação, como restaurar outros bancos de dados, anexar bancos de dados e corrigir incompatibilidades de usuário.</span><span class="sxs-lookup"><span data-stu-id="e719a-116">Restart the server instance and continue other recovery steps such as restoring other databases, attaching databases, and correcting user mismatches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e719a-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e719a-117">Example</span></span>  
 <span data-ttu-id="e719a-118">O exemplo a seguir restaura o banco de dados `master` na instância do servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="e719a-118">The following example restores the `master` database on the default server instance.</span></span> <span data-ttu-id="e719a-119">O exemplo assume que a instância do servidor já está sendo executada no modo de usuário único.</span><span class="sxs-lookup"><span data-stu-id="e719a-119">The example assumes that the server instance is already running in single-user mode.</span></span> <span data-ttu-id="e719a-120">O exemplo inicia o `sqlcmd` e executa uma instrução `RESTORE DATABASE` que restaura um backup de banco de dados completo de `master` de um dispositivo de disco: `Z:\SQLServerBackups\master.bak`.</span><span class="sxs-lookup"><span data-stu-id="e719a-120">The example starts `sqlcmd` and executes a `RESTORE DATABASE` statement that restores a full database backup of `master` from a disk device: `Z:\SQLServerBackups\master.bak`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e719a-121">Para uma instância nomeada, o comando **sqlcmd** deve especificar a opção **-S** _\<ComputerName>_ \\ *\<InstanceName>* .</span><span class="sxs-lookup"><span data-stu-id="e719a-121">For a named instance, the **sqlcmd** command must specify the **-S**_\<ComputerName>_\\*\<InstanceName>* option.</span></span>  
  
```  
  
      C:\> sqlcmd  
1> RESTORE DATABASE master FROM DISK = 'Z:\SQLServerBackups\master.bak' WITH REPLACE;  
2> GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e719a-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e719a-122">See Also</span></span>  
 <span data-ttu-id="e719a-123">[Restaurações completas de banco de dados &#40;Modelo de recuperação simples#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="e719a-123">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="e719a-124">[Restaurações completas de banco de dados &#40;Modelo de recuperação completa&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="e719a-124">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="e719a-125">[Solução de problemas de usuários órfãos &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e719a-125">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 <span data-ttu-id="e719a-126">[Anexar e desanexar bancos de dados &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e719a-126">[Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="e719a-127">[Recriar bancos de dados do sistema](../databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="e719a-127">[Rebuild System Databases](../databases/system-databases.md) </span></span>  
 <span data-ttu-id="e719a-128">[Opções de inicialização do serviço Mecanismo de Banco de Dados](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span><span class="sxs-lookup"><span data-stu-id="e719a-128">[Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span></span>  
 <span data-ttu-id="e719a-129">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e719a-129">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="e719a-130">[Fazer backup e restaurar bancos de dados do sistema &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e719a-130">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="e719a-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e719a-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="e719a-132">Iniciar o SQL Server no modo de usuário único</span><span class="sxs-lookup"><span data-stu-id="e719a-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
