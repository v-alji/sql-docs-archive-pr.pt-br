---
title: Restaurar um backup de banco de dados no modelo de recuperação simples (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- database restores [SQL Server], full backups
- backing up databases [SQL Server], full backups
- database backups [SQL Server], full backups
- restoring databases [SQL Server], full backups
ms.assetid: a928fa36-e285-476f-9a7b-6840a8bb7283
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e264dd380c3dff40dacc4eb576d34af5195dec01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679996"
---
# <a name="restore-a-database-backup-under-the-simple-recovery-model-transact-sql"></a><span data-ttu-id="3a230-102">Restaurar um backup de banco de dados no modelo de recuperação simples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3a230-102">Restore a Database Backup Under the Simple Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="3a230-103">Este tópico explica como restaurar um backup de banco de dados completo.</span><span class="sxs-lookup"><span data-stu-id="3a230-103">This topic explains how to restore a full database backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3a230-104">O administrador do sistema que restaura o backup de banco de dados completo deve ser a única pessoa a usar o banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="3a230-104">The system administrator restoring the full database backup must be the only person currently using the database to be restored.</span></span>  
  
## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="3a230-105">Pré-requisitos e recomendações</span><span class="sxs-lookup"><span data-stu-id="3a230-105">Prerequisites and Recommendations</span></span>  
  
-   <span data-ttu-id="3a230-106">Para restaurar um banco de dados criptografado, é necessário ter acesso ao certificado ou à chave assimétrica usada para criptografar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3a230-106">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="3a230-107">Sem o certificado ou a chave assimétrica, o banco de dados não pode ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="3a230-107">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="3a230-108">Como resultado, o certificado usado para criptografar a chave de criptografia do banco de dados deverá ser retido enquanto o backup for necessário.</span><span class="sxs-lookup"><span data-stu-id="3a230-108">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="3a230-109">Para obter mais informações, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="3a230-109">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
-   <span data-ttu-id="3a230-110">Por motivos de segurança, é recomendável não anexar ou restaurar bancos de dados de origens desconhecidas ou não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="3a230-110">For security purposes, we recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="3a230-111">Esses bancos de dados podem conter um código mal-intencionado que pode executar um código [!INCLUDE[tsql](../../includes/tsql-md.md)] inesperado ou provocar erros modificando o esquema ou a estrutura física do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3a230-111">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="3a230-112">Antes de usar um banco de dados de origem desconhecida ou não confiável, execute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no banco de dados, em um servidor que não seja de produção. Além disso, examine o código, como procedimentos armazenados ou outro código definido pelo usuário, no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3a230-112">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="database-compatibility-level-after-upgrade"></a><span data-ttu-id="3a230-113">Nível de compatibilidade do banco de dados após a atualização</span><span class="sxs-lookup"><span data-stu-id="3a230-113">Database Compatibility Level After Upgrade</span></span>  
 <span data-ttu-id="3a230-114">Os níveis de compatibilidade dos bancos de dados **tempdb**, **model**, **msdb** e **Resource** é definido para o nível de compatibilidade do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] após a atualização.</span><span class="sxs-lookup"><span data-stu-id="3a230-114">The compatibility levels of the **tempdb**, **model**, **msdb** and **Resource** databases are set to the compatibility level of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after upgrade.</span></span> <span data-ttu-id="3a230-115">O banco de dados do sistema **mestre** mantém o nível de compatibilidade que tinha antes da atualização, a menos que esse nível era inferior a 100.</span><span class="sxs-lookup"><span data-stu-id="3a230-115">The **master** system database retains the compatibility level it had before upgrade, unless that level was less than 100.</span></span> <span data-ttu-id="3a230-116">Se o nível de compatibilidade do **mestre** era inferior a 100 antes da atualização, ele será definido como 100 após a atualização.</span><span class="sxs-lookup"><span data-stu-id="3a230-116">If the compatibility level of **master** was less than 100 before upgrade, it is set to 100 after upgrade.</span></span>  
  
 <span data-ttu-id="3a230-117">Se o nível de compatibilidade de um banco de dados de usuário era 100 ou mais alto antes da atualização, ele permanecerá o mesmo depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="3a230-117">If the compatibility level of a user database was 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="3a230-118">Se o nível de compatibilidade era 90 antes da atualização, no banco de dados atualizado, o nível de compatibilidade será definido como 100, que é o nível de compatibilidade mais baixo com suporte no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a230-118">If the compatibility level was 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a230-119">Os novos bancos de dados de usuários herdam o nível de compatibilidade do banco de dados **model** .</span><span class="sxs-lookup"><span data-stu-id="3a230-119">New user databases will inherit the compatibility level of the **model** database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="3a230-120">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="3a230-120">Procedures</span></span>  
  
#### <a name="to-restore-a-full-database-backup"></a><span data-ttu-id="3a230-121">Para restaurar um backup de banco de dados completo</span><span class="sxs-lookup"><span data-stu-id="3a230-121">To restore a full database backup</span></span>  
  
1.  <span data-ttu-id="3a230-122">Execute a instrução RESTORE DATABASE para restaurar o backup de banco de dados completo, especificando:</span><span class="sxs-lookup"><span data-stu-id="3a230-122">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="3a230-123">O nome do banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="3a230-123">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="3a230-124">O dispositivo de backup a partir do qual o backup de banco de dados completo é restaurado.</span><span class="sxs-lookup"><span data-stu-id="3a230-124">The backup device from where the full database backup is restored.</span></span>  
  
    -   <span data-ttu-id="3a230-125">A cláusula NORECOVERY, se você tiver um log de transações ou backup de banco de dados diferencial para aplicar após restaurar o backup de banco de dados completo.</span><span class="sxs-lookup"><span data-stu-id="3a230-125">The NORECOVERY clause if you have a transaction log or differential database backup to apply after restoring the full database backup.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3a230-126">Para restaurar um banco de dados criptografado, é necessário ter acesso ao certificado ou à chave assimétrica usada para criptografar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3a230-126">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="3a230-127">Sem o certificado ou a chave assimétrica, o banco de dados não pode ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="3a230-127">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="3a230-128">Como resultado, o certificado usado para criptografar a chave de criptografia do banco de dados deverá ser retido enquanto o backup for necessário.</span><span class="sxs-lookup"><span data-stu-id="3a230-128">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="3a230-129">Para obter mais informações, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="3a230-129">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
2.  <span data-ttu-id="3a230-130">Opcionalmente, especifique:</span><span class="sxs-lookup"><span data-stu-id="3a230-130">Optionally, specify:</span></span>  
  
    -   <span data-ttu-id="3a230-131">A cláusula FILE para identificar o conjunto de backup no dispositivo de banco de dados a ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="3a230-131">The FILE clause to identify the backup set on the backup device to restore.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a230-132">Se você restaurar um banco de dados da versão anterior para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], o banco de dados será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a230-132">If you restore an earlier version database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database is automatically upgraded.</span></span> <span data-ttu-id="3a230-133">Normalmente, o banco de dados se torna disponível imediatamente.</span><span class="sxs-lookup"><span data-stu-id="3a230-133">Typically, the database becomes available immediately.</span></span> <span data-ttu-id="3a230-134">No entanto, se um banco de dados do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tiver índices de texto completo, o processo de atualização importará, redefinirá ou recriará esses índices, dependendo da configuração da propriedade de servidor  **upgrade_option** .</span><span class="sxs-lookup"><span data-stu-id="3a230-134">However, if a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the  **upgrade_option** server property.</span></span> <span data-ttu-id="3a230-135">Se a opção de atualização for definida como importar (**upgrade_option** = 2) ou recriar (**upgrade_option** = 0), os índices de texto completo permanecerão indisponíveis durante a atualização.</span><span class="sxs-lookup"><span data-stu-id="3a230-135">If the upgrade option is set to import (**upgrade_option** = 2) or rebuild (**upgrade_option** = 0), the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="3a230-136">Dependendo da quantidade de dados a serem indexados, a importação pode levar várias horas, e a recriação pode ser até dez vezes mais demorada.</span><span class="sxs-lookup"><span data-stu-id="3a230-136">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="3a230-137">Lembre-se também de que, quando a opção de atualização estiver definida para importar, os índices de texto completo associados serão recriados se um catálogo de texto completo não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="3a230-137">Note also that when the upgrade option is set to import, the associated full-text indexes are rebuilt if a full-text catalog is not available.</span></span> <span data-ttu-id="3a230-138">Para alterar a configuração da propriedade de servidor **upgrade_option** , use [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3a230-138">To change the setting of the **upgrade_option** server property, use [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a230-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3a230-139">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3a230-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="3a230-140">Description</span></span>  
 <span data-ttu-id="3a230-141">Este exemplo restaura o backup de banco de dados completo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] a partir da fita.</span><span class="sxs-lookup"><span data-stu-id="3a230-141">This example restores the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] full database backup from tape.</span></span>  
  
### <a name="example"></a><span data-ttu-id="3a230-142">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3a230-142">Example</span></span>  
  
```  
USE master;  
GO  
RESTORE DATABASE AdventureWorks2012  
   FROM TAPE = '\\.\Tape0';  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a230-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a230-143">See Also</span></span>  
 <span data-ttu-id="3a230-144">[Restaurações completas de banco de dados &#40;Modelo de recuperação completa&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="3a230-144">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="3a230-145">[Restaurações completas de banco de dados &#40;Modelo de recuperação simples#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="3a230-145">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="3a230-146">[Backups de bancos de dados completos &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a230-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="3a230-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a230-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="3a230-148">[Informações de histórico e cabeçalho de backup &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3a230-148">[Backup History and Header Information &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span></span>  
 [<span data-ttu-id="3a230-149">Recompilar bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="3a230-149">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
