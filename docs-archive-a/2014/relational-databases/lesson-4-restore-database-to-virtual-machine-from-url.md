---
title: Lição 5. Adicional Criptografar seu banco de dados usando TDE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ba793c8f-665a-4c46-b68d-f558a37906b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 613b66c04a69364f3c9be1059f95021dd3eff595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575120"
---
# <a name="lesson-5-optional-encrypt-your-database-using-tde"></a><span data-ttu-id="6b70d-103">Lição 5.</span><span class="sxs-lookup"><span data-stu-id="6b70d-103">Lesson 5.</span></span> <span data-ttu-id="6b70d-104">(Opcional) Criptografar o banco de dados usando TDE</span><span class="sxs-lookup"><span data-stu-id="6b70d-104">(Optional) Encrypt your database using TDE</span></span>
  <span data-ttu-id="6b70d-105">Como etapa opcional, você pode criptografar o banco de dados recém-criado.</span><span class="sxs-lookup"><span data-stu-id="6b70d-105">As an optional step, you can encrypt the newly created database.</span></span> <span data-ttu-id="6b70d-106">A criptografia transparente de dados (TDE) executa criptografia de E/S em tempo real e a descriptografia de dados e arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="6b70d-106">Transparent data encryption (TDE) performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="6b70d-107">Esse tipo de criptografia usa uma DEK (chave de criptografia do banco de dados), que é armazenada no registro de inicialização do banco de dados para disponibilidade durante a recuperação.</span><span class="sxs-lookup"><span data-stu-id="6b70d-107">This kind of encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="6b70d-108">Para obter mais informações, consulte [Transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) e [mover um banco de dados protegido por TDE para outro SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6b70d-108">For more information, see [Transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) and [Move a TDE Protected Database to Another SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span></span>  
  
 <span data-ttu-id="6b70d-109">Esta lição supõe que você já concluiu as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6b70d-109">This lesson assumes you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="6b70d-110">Você tem uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="6b70d-110">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="6b70d-111">Você criou um contêiner em sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="6b70d-111">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="6b70d-112">Você criou uma política em um contêiner com direitos de leitura, gravação e lista.</span><span class="sxs-lookup"><span data-stu-id="6b70d-112">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="6b70d-113">Você também gerou uma chave de SAS.</span><span class="sxs-lookup"><span data-stu-id="6b70d-113">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="6b70d-114">Você criou uma credencial do SQL Server no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="6b70d-114">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="6b70d-115">Você criou um banco de dados seguindo as etapas descritas na lição 4.</span><span class="sxs-lookup"><span data-stu-id="6b70d-115">You have created a database by following the steps that are described in Lesson 4.</span></span>  
  
 <span data-ttu-id="6b70d-116">Se você quiser criptografar um banco de dados, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6b70d-116">If you want to encrypt a database, follow these steps:</span></span>  
  
1.  <span data-ttu-id="6b70d-117">Na máquina de origem, modifique e execute as seguintes instruções em uma janela de consulta:</span><span class="sxs-lookup"><span data-stu-id="6b70d-117">In the source machine, modify and run the following statements in a query window:</span></span>  
  
    ```  
  
    -- Create a master key and a server certificate   
    USE master   
    GO   
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01';   
    GO   
    CREATE CERTIFICATE MySQLCert WITH SUBJECT = 'SQL - Azure Storage Certification'   
    GO   
    -- Create a backup of the server certificate in the master database.   
    -- Store TDS certificates in the source machine locally.   
    BACKUP CERTIFICATE MySQLCert   
    TO FILE = 'C:\certs\MySQLCert.CER'   
    WITH PRIVATE KEY   
    (   
    FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
    ENCRYPTION BY PASSWORD = 'MySQLKey01'   
    );  
  
    ```  
  
2.  <span data-ttu-id="6b70d-118">Em seguida, criptografe o novo banco de dados no computador de origem seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6b70d-118">Then, encrypt your new database in the source machine by following these steps:</span></span>  
  
    ```  
  
    -- Switch to the new database.   
    -- Create a database encryption key, that is protected by the server certificate in the master database.    
    -- Alter the new database to encrypt the database using TDE.   
    USE TestDB1;   
    GO   
    -- Encrypt your database   
    CREATE DATABASE ENCRYPTION KEY   
    WITH ALGORITHM = AES_256   
    ENCRYPTION BY SERVER CERTIFICATE MySQLCert   
    GO   
  
    ALTER DATABASE TestDB1   
    SET ENCRYPTION ON   
    GO  
  
    ```  
  
 <span data-ttu-id="6b70d-119">Se você quiser saber o estado de criptografia de um banco de dados e suas chaves de criptografia de banco de dados associadas, execute a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="6b70d-119">If you want to learn the encryption state of a database and its associated database encryption keys, run the following statement:</span></span>  
  
```  
  
SELECT * FROM sys.dm_database_encryption_keys;   
GO  
  
```  
  
 <span data-ttu-id="6b70d-120">Para obter informações detalhadas sobre as instruções Transact-SQL que foram usadas nesta lição, consulte [criar banco de dados &#40;SQL Server&#41;Transact-SQL ](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [criar chave mestra &#40;Transact-sql&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [criar certificado &#40;transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql)e [Sys. dm_database_encryption_keys &#40;Transact-SQL ](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql)&#41;.</span><span class="sxs-lookup"><span data-stu-id="6b70d-120">For detailed information the Transact-SQL statements that have been used in this lesson, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql), and [sys.dm_database_encryption_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span></span>  
  
 <span data-ttu-id="6b70d-121">**Próxima lição:**</span><span class="sxs-lookup"><span data-stu-id="6b70d-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="6b70d-122">Lição 6: Migrar um banco de dados de um computador de origem no local para um computador de destino no Azure</span><span class="sxs-lookup"><span data-stu-id="6b70d-122">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>](lesson-5-backup-database-using-file-snapshot-backup.md)  
  
  
