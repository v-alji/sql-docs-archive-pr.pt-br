---
title: Criar um backup criptografado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: e29061d3-c2ab-4d98-b9be-8e90a11d17fe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d46cc686684d87fe393a5db7cfe01194ae917836
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684783"
---
# <a name="create-an-encrypted-backup"></a><span data-ttu-id="7454b-102">Criar um backup criptografado</span><span class="sxs-lookup"><span data-stu-id="7454b-102">Create an Encrypted Backup</span></span>
  <span data-ttu-id="7454b-103">Este tópico descreve as etapas necessárias para criar um backup criptografado usando Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="7454b-103">This topic describes the steps necessary to create an encrypted backup using Transact-SQL.</span></span>  
  
## <a name="backup-to-disk-with-encryption"></a><span data-ttu-id="7454b-104">Backup em disco com criptografia</span><span class="sxs-lookup"><span data-stu-id="7454b-104">Backup to Disk with Encryption</span></span>  
 <span data-ttu-id="7454b-105">**Pré-requisitos:**</span><span class="sxs-lookup"><span data-stu-id="7454b-105">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="7454b-106">Acesso a um disco local ou ao armazenamento com espaço suficiente para criar um backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7454b-106">Access to a local disk or to storage with adequate space to create a backup of the database.</span></span>  
  
-   <span data-ttu-id="7454b-107">Uma Chave Mestra do Banco de Dados para o banco de dados mestre, e um certificado ou uma chave assimétrica disponível na instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7454b-107">A Database Master Key for the master database, and a certificate or asymmetric key available on the instance of SQL Server.</span></span> <span data-ttu-id="7454b-108">Para requisitos e permissões de criptografia, consulte [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="7454b-108">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
 <span data-ttu-id="7454b-109">Use as etapas a seguir para criar um backup criptografado de um banco de dados em um disco local.</span><span class="sxs-lookup"><span data-stu-id="7454b-109">Use the following steps to create an encrypted backup of a database to a local disk.</span></span> <span data-ttu-id="7454b-110">Este exemplo usa um banco de dados de usuário chamado MyTestDB.</span><span class="sxs-lookup"><span data-stu-id="7454b-110">This example uses a user database called MyTestDB.</span></span>  
  
1.  <span data-ttu-id="7454b-111">**Crie uma Chave Mestra do Banco de Dados para o banco de dados mestre:** Escolha uma senha por criptografar a cópia da chave mestra que será armazenada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7454b-111">**Create a Database Master Key of the master database:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="7454b-112">Conecte-se ao mecanismo de banco de dados, inicie uma nova janela de consulta, copie e cole o exemplo a seguir e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7454b-112">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.   
    -- The key is encrypted using the password "<master key password>"  
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
2.  <span data-ttu-id="7454b-113">**Crie um Certificado de Backup:** Crie um certificado de backup no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="7454b-113">**Create a Backup Certificate:** Create a backup certificate in the master database.</span></span> <span data-ttu-id="7454b-114">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7454b-114">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
    ```  
    Use Master  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDB Backup Encryption Certificate';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="7454b-115">**Faça o backup do banco de dados:** especifique o algoritmo de criptografia e o certificado a ser usado.</span><span class="sxs-lookup"><span data-stu-id="7454b-115">**Backup the database:** Specify the encryption algorithm and certificate to use.</span></span> <span data-ttu-id="7454b-116">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7454b-116">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      COMPRESSION,  
      ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
 <span data-ttu-id="7454b-117">Para obter um exemplo de como criptografar um backup protegido por uma EKM, veja [Gerenciamento extensível de chaves usando o Cofre de Chaves do Azure &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7454b-117">For an example of encrypting a backup protected by an EKM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
### <a name="backup-to-azure-storage-with-encryption"></a><span data-ttu-id="7454b-118">Backup no Armazenamento do Microsoft Azure com criptografia</span><span class="sxs-lookup"><span data-stu-id="7454b-118">Backup to Azure Storage with Encryption</span></span>  
 <span data-ttu-id="7454b-119">Se você estiver criando um backup no armazenamento do Azure usando a opção de **Backup do SQL Server para URL**, as etapas de criptografia serão as mesmas, mas você deve usar a URL como destino e uma Credencial SQL a ser autenticada no armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="7454b-119">If you are creating a backup to Azure storage using the **SQL Server Backup to URL** option, the encryption steps are the same, but you must use URL as the destination and a SQL Credential to authenticate to the Azure storage.</span></span> <span data-ttu-id="7454b-120">Se você quiser configurar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] com opções de criptografia, consulte [configurando SQL Server Backup gerenciado no Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) e [Configurando SQL Server Backup gerenciado para o Azure para grupos de disponibilidade](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7454b-120">If you want to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with encryption options, see [Setting up SQL Server Managed Backup to Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 <span data-ttu-id="7454b-121">**Pré-requisitos:**</span><span class="sxs-lookup"><span data-stu-id="7454b-121">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="7454b-122">Uma conta de armazenamento do Windows e um contêiner.</span><span class="sxs-lookup"><span data-stu-id="7454b-122">A windows storage account and a container.</span></span> <span data-ttu-id="7454b-123">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="7454b-123">For more information, see.</span></span> <span data-ttu-id="7454b-124">[Lição 1: Criar objetos de Armazenamento do Azure](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span><span class="sxs-lookup"><span data-stu-id="7454b-124">[Lesson 1: Create Azure Storage Objects](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span></span>  
  
-   <span data-ttu-id="7454b-125">Uma Chave Mestra do Banco de Dados para o banco de dados mestre, e um certificado ou uma chave assimétrica na instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7454b-125">A Database Master Key for the master database, and a certificate or asymmetric key  on the instance of SQL Server.</span></span> <span data-ttu-id="7454b-126">Para requisitos e permissões de criptografia, consulte [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="7454b-126">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
1.  <span data-ttu-id="7454b-127">**Criar uma credencial do SQL Server:** para criar uma credencial do SQL Server, conecte-se ao Mecanismo de Banco de Dados, abra uma nova janela de consulta, copie e cole o exemplo a seguir e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7454b-127">**Create SQL Server Credential:** To create a SQL Server credential, connect to the Database Engine, open a new query window, and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account    
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account  
    ```  
  
2.  <span data-ttu-id="7454b-128">**Criar uma chave mestra de banco de dados:** Escolha uma senha por criptografar a cópia da chave mestra que será armazenada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7454b-128">**Create a Database Master Key:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="7454b-129">Conecte-se ao mecanismo de banco de dados, inicie uma nova janela de consulta, copie e cole o exemplo a seguir e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7454b-129">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.  
    -- The key is encrypted using the password "<master key password>"  
    USE Master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="7454b-130">**Crie um Certificado de Backup:** crie um Certificado de backup no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="7454b-130">**Create a Backup Certificate:** Create a Backup Certificate in the master database.</span></span> <span data-ttu-id="7454b-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7454b-131">Copy and paste the following example in the query window and click **Execute**</span></span>  
  
    ```  
    USE Master;  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDBBackupEncryptCert ';  
    GO  
  
    ```  
  
4.  <span data-ttu-id="7454b-132">**Faça o backup do banco de dados:** especifique o algoritmo de criptografia e o certificado a ser utilizado.</span><span class="sxs-lookup"><span data-stu-id="7454b-132">**Backup the database:** Specify the encryption algorithm and the certificate to use.</span></span> <span data-ttu-id="7454b-133">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7454b-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO URL = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      CREDENTIAL 'mycredential' - this is the name of the credential created in the first step.  
      ,COMPRESSION  
      ,ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
  
