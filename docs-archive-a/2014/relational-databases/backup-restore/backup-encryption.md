---
title: Criptografia de backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 334b95a8-6061-4fe0-9e34-b32c9f1706ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6a78ae4969982fbfe5295ee4219855f48ac60793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686315"
---
# <a name="backup-encryption"></a><span data-ttu-id="79305-102">Criptografia de backup</span><span class="sxs-lookup"><span data-stu-id="79305-102">Backup Encryption</span></span>
  <span data-ttu-id="79305-103">Este tópico fornece uma visão geral das opções de criptografia para backups do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79305-103">This topic provides an overview of the encryption options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="79305-104">Ele inclui detalhes do uso, benefícios e práticas recomendadas para criptografia durante o backup.</span><span class="sxs-lookup"><span data-stu-id="79305-104">It includes details of the usage, benefits, and recommended practices for encrypting during backup.</span></span>  
  
  
##  <a name="overview"></a><a name="Overview"></a> <span data-ttu-id="79305-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="79305-105">Overview</span></span>  
 <span data-ttu-id="79305-106">A partir do [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], o SQL Server pode criptografar os dados enquanto cria um backup.</span><span class="sxs-lookup"><span data-stu-id="79305-106">Starting in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SQL Server has the ability to encrypt the data while creating a backup.</span></span> <span data-ttu-id="79305-107">Especificando o algoritmo de criptografia e o criptografador (um certificado ou uma chave assimétrica) ao criar um backup, você pode criar um arquivo de backup criptografado.</span><span class="sxs-lookup"><span data-stu-id="79305-107">By specifying the encryption algorithm and the encryptor (a Certificate or Asymmetric Key) when creating a backup, you can create an encrypted backup file.</span></span> <span data-ttu-id="79305-108">Todos os destinos de armazenamento: há suporte para armazenamento local e do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="79305-108">All storage destinations: on-premises and Window Azure storage are supported.</span></span> <span data-ttu-id="79305-109">Além disso, as opções de criptografia podem ser configuradas para operações do [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] , um novo recurso incorporado no [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79305-109">In addition, encryption options can be configured for [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] operations, a new feature introduced in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="79305-110">Para realizar a criptografia durante o backup, você deve especificar um algoritmo de criptografia, e um criptografador para proteger a chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="79305-110">To encrypt during backup, you must specify an encryption algorithm, and an encryptor to secure the encryption key.</span></span> <span data-ttu-id="79305-111">Estas são as opções de criptografia com suporte:</span><span class="sxs-lookup"><span data-stu-id="79305-111">The following are the supported encryption options:</span></span>  
  
-   <span data-ttu-id="79305-112">**Algoritmo de criptografia:** os algoritmos de criptografia com suporte são: AES 128, AES 192, AES 256 e Triple DES</span><span class="sxs-lookup"><span data-stu-id="79305-112">**Encryption Algorithm:** The supported encryption algorithms are: AES 128, AES 192, AES 256, and Triple DES</span></span>  
  
-   <span data-ttu-id="79305-113">**Criptografador:** um certificado ou chave assimétrica</span><span class="sxs-lookup"><span data-stu-id="79305-113">**Encryptor:** A certificate or asymmetric Key</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="79305-114">É muito importante fazer backup do certificado ou da chave assimétrica e, preferencialmente, em um local diferente do arquivo de backup usado para criptografar.</span><span class="sxs-lookup"><span data-stu-id="79305-114">It is very important to back up the certificate or asymmetric key, and preferably to a different location than the backup file it was used to encrypt.</span></span> <span data-ttu-id="79305-115">Sem o certificado ou a chave assimétrica, você não pode restaurar o backup, tornando o arquivo de backup inutilizável.</span><span class="sxs-lookup"><span data-stu-id="79305-115">Without the certificate or asymmetric key, you cannot restore the backup, rendering the backup file unusable.</span></span>  
  
 <span data-ttu-id="79305-116">**Restaurar o backup criptografado:** a restauração do SQL Server não requer que nenhum parâmetro de criptografia seja especificado durante as restaurações.</span><span class="sxs-lookup"><span data-stu-id="79305-116">**Restoring the encrypted backup:** SQL Server restore does not require any encryption parameters to be specified during restores.</span></span> <span data-ttu-id="79305-117">Requer que o certificado ou a chave assimétrica usada para criptografar o arquivo de backup esteja disponível na instância em que você está fazendo a restauração.</span><span class="sxs-lookup"><span data-stu-id="79305-117">It does require that the certificate or the asymmetric key used to encrypt the backup file be available on the instance that you are restoring to.</span></span> <span data-ttu-id="79305-118">A conta de usuário que executa a restauração deve ter as permissões `VIEW DEFINITION` no certificado ou na chave.</span><span class="sxs-lookup"><span data-stu-id="79305-118">The user account performing the restore must have `VIEW DEFINITION` permissions on the certificate or key.</span></span> <span data-ttu-id="79305-119">Se você estiver restaurando o backup criptografado para uma instância diferente, verifique se o certificado está disponível nessa instância.</span><span class="sxs-lookup"><span data-stu-id="79305-119">If you are restoring the encrypted backup to a different instance, you must make sure that the certificate is available on that instance.</span></span>  
  
 <span data-ttu-id="79305-120">Se você estiver restaurando um backup de um banco de dados criptografado TDE, o certificado TDE deverá estar disponível na instância para a qual você estiver restaurando.</span><span class="sxs-lookup"><span data-stu-id="79305-120">If you are restoring a backup from a TDE encrypted database, the TDE certificate should be available on the instance you are restoring to.</span></span>  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="79305-121">Benefícios</span><span class="sxs-lookup"><span data-stu-id="79305-121">Benefits</span></span>  
  
1.  <span data-ttu-id="79305-122">Criptografar os backups de banco de dados ajuda a proteger os dados: o SQL Server fornece a opção de criptografar os dados de backup ao criar um backup.</span><span class="sxs-lookup"><span data-stu-id="79305-122">Encrypting the database backups helps secure the data: SQL Server provides the option to encrypt the backup data while creating a backup.</span></span>  
  
2.  <span data-ttu-id="79305-123">A criptografia também pode ser usada para bancos de dados criptografados usando a TDE.</span><span class="sxs-lookup"><span data-stu-id="79305-123">Encryption can also be used for databases that are encrypted using TDE.</span></span>  
  
3.  <span data-ttu-id="79305-124">Há suporte para a criptografia nos backups feitos por [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)], que fornece segurança adicional para backups fora do local.</span><span class="sxs-lookup"><span data-stu-id="79305-124">Encryption is supported for backups done by [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)], which provides additional security for off-site backups.</span></span>  
  
4.  <span data-ttu-id="79305-125">Esse recurso oferece suporte a vários algoritmos de criptografia até AES de 256 bits.</span><span class="sxs-lookup"><span data-stu-id="79305-125">This feature supports multiple encryption algorithms up to AES 256 bit.</span></span> <span data-ttu-id="79305-126">Isso permite que você selecione um algoritmo que atenda aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="79305-126">This gives you the option to select an algorithm that aligns with your requirements.</span></span>  
  
5.  <span data-ttu-id="79305-127">Você pode integrar chaves de criptografia com provedores EKM (Extended Key Management).</span><span class="sxs-lookup"><span data-stu-id="79305-127">You can integrate encryption keys with Extended Key Management (EKM) providers.</span></span>  
  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="79305-128">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="79305-128">Prerequisites</span></span>  
 <span data-ttu-id="79305-129">Estes são os pré-requisitos para criptografar um backup:</span><span class="sxs-lookup"><span data-stu-id="79305-129">The following are prerequisites for encrypting a backup:</span></span>  
  
1.  <span data-ttu-id="79305-130">**Criar uma chave mestra do banco de dados para o banco de dados mestre:** A chave mestra de banco de dados é uma chave simétrica usada para proteger as chaves privadas dos certificados e as chaves assimétricas presentes no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="79305-130">**Create a Database Master Key for the master database:** The database master key is a symmetric key that is used to protect the private keys of certificates and asymmetric keys that are present in the database.</span></span> <span data-ttu-id="79305-131">Para obter mais informações, consulte [Chaves de criptografia do SQL Server e banco de dados &#40;Mecanismo de Banco de Dados&#41;](../security/encryption/sql-server-and-database-encryption-keys-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="79305-131">For more information, see [SQL Server and Database Encryption Keys &#40;Database Engine&#41;](../security/encryption/sql-server-and-database-encryption-keys-database-engine.md).</span></span>  
  
2.  <span data-ttu-id="79305-132">Crie um certificado ou uma chave assimétrica a ser usada na criptografia de backup.</span><span class="sxs-lookup"><span data-stu-id="79305-132">Create a certificate or asymmetric Key to use for backup encryption.</span></span> <span data-ttu-id="79305-133">Para obter mais informações sobre a criação de um certificado, consulte [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="79305-133">For more information on creating a certificate, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span> <span data-ttu-id="79305-134">Para obter mais informações sobre a criação de uma chave assimétrica, consulte [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="79305-134">For more information on creating an asymmetric key, see [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="79305-135">Há suporte somente para chaves assimétricas que residem em um EKM (Extended Key Management).</span><span class="sxs-lookup"><span data-stu-id="79305-135">Only asymmetric keys residing in an Extended Key Management (EKM) are supported.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="79305-136">Restrições</span><span class="sxs-lookup"><span data-stu-id="79305-136">Restrictions</span></span>  
 <span data-ttu-id="79305-137">Estas são as restrições que se aplicam às opções de criptografia:</span><span class="sxs-lookup"><span data-stu-id="79305-137">The following are restrictions that apply to the encryption options:</span></span>  
  
-   <span data-ttu-id="79305-138">Se você estiver usando a chave assimétrica para criptografar os dados de backup, haverá suporte somente para as chaves assimétricas que residem no provedor EKM.</span><span class="sxs-lookup"><span data-stu-id="79305-138">If you are using asymmetric key to encrypt the backup data, only asymmetric keys residing in the EKM provider are supported.</span></span>  
  
-   <span data-ttu-id="79305-139">O SQL Server Express e o SQL Server Web não oferecem suporte à criptografia durante o backup.</span><span class="sxs-lookup"><span data-stu-id="79305-139">SQL Server Express and SQL Server Web do not support encryption during backup.</span></span> <span data-ttu-id="79305-140">No entanto, há suporte para a restauração de um backup criptografado para uma instância do SQL Server Express ou SQL Server Web.</span><span class="sxs-lookup"><span data-stu-id="79305-140">However restoring from an encrypted backup to an instance of SQL Server Express or SQL Server Web is supported.</span></span>  
  
-   <span data-ttu-id="79305-141">As versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não podem ler backups criptografados.</span><span class="sxs-lookup"><span data-stu-id="79305-141">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read encrypted backups.</span></span>  
  
-   <span data-ttu-id="79305-142">Não há suporte para a anexação a uma opção de conjunto de backup existente em backups criptografados.</span><span class="sxs-lookup"><span data-stu-id="79305-142">Appending to an existing backup set option is not supported for encrypted backups.</span></span>  
  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="79305-143">Permissões</span><span class="sxs-lookup"><span data-stu-id="79305-143">Permissions</span></span>  
 <span data-ttu-id="79305-144">**Para criptografar um backup ou restaurá-lo de um backup criptografado:**</span><span class="sxs-lookup"><span data-stu-id="79305-144">**To encrypt a backup or to restore from an encrypted backup:**</span></span>  
  
 <span data-ttu-id="79305-145">Permissão `VIEW DEFINITION` no certificado ou na chave assimétrica usada para criptografar o backup do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="79305-145">`VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database backup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79305-146">Não é necessário ter acesso ao certificado TDE para fazer backup ou restaurar um banco de dados protegido.</span><span class="sxs-lookup"><span data-stu-id="79305-146">Access to the TDE certificate is not required to back up or restore a TDE protected database.</span></span>  
  
##  <a name="backup-encryption-methods"></a><a name="Methods"></a> <span data-ttu-id="79305-147">Métodos de criptografia de backup</span><span class="sxs-lookup"><span data-stu-id="79305-147">Backup Encryption Methods</span></span>  
 <span data-ttu-id="79305-148">As seções a seguir fornecem uma breve introdução às etapas de criptografia dos dados durante o backup.</span><span class="sxs-lookup"><span data-stu-id="79305-148">The sections below provide a brief introduction to the steps to encrypting the data during backup.</span></span> <span data-ttu-id="79305-149">Para obter um passo a passo completo das diferentes etapas de criptografia de backup usando o Transact-SQL, consulte [Criar um backup criptografado](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="79305-149">For a complete walkthrough of the different steps of encrypting your backup using Transact-SQL, see [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
### <a name="using-sql-server-management-studio"></a><span data-ttu-id="79305-150">Como usar o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="79305-150">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="79305-151">Você pode criptografar um backup ao criar o backup de um banco de dados em qualquer uma destas caixas de diálogo:</span><span class="sxs-lookup"><span data-stu-id="79305-151">You can encrypt a backup when creating the backup of a database in any of the following dialog boxes:</span></span>  
  
1.  <span data-ttu-id="79305-152">[Backup de Banco de Dados &#40;página Opções de Backup&#41;](back-up-database-backup-options-page.md) Na página **Opções de Backup**, selecione **Criptografia**; em seguida, especifique o algoritmo de criptografia e o certificado ou a chave assimétrica a serem usados na criptografia.</span><span class="sxs-lookup"><span data-stu-id="79305-152">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) On the **Backup Options** page, you can select **Encryption**, and specify the encryption algorithm and the certificate or asymmetric key to use for the encryption.</span></span>  
  
2.  <span data-ttu-id="79305-153">[Usando o Assistente de Plano de Manutenção](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure) Ao selecionar uma tarefa de backup, na guia **Opções** da página **Define Backup ()Task (Definir ()Tarefa de Backup)** , selecione **Criptografia de Backup**e especifique o algoritmo de criptografia e o certificado ou a chave a serem usados na criptografia.</span><span class="sxs-lookup"><span data-stu-id="79305-153">[Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure) When you select a backup task, on the **Options** tab of the **Define Backup ()Task** page, you can select **Backup Encryption**, and specify the encryption algorithm and the certificate or key to use for the encryption.</span></span>  
  
### <a name="using-transact-sql"></a><span data-ttu-id="79305-154">Usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="79305-154">Using Transact SQL</span></span>  
 <span data-ttu-id="79305-155">Este é um exemplo de instrução Transact-SQL para criptografar o arquivo de backup:</span><span class="sxs-lookup"><span data-stu-id="79305-155">Following is a sample Transact-SQL statement to encrypt the backup file:</span></span>  
  
```sql
BACKUP DATABASE [MYTestDB]  
TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
WITH  
  COMPRESSION,  
  ENCRYPTION   
   (  
   ALGORITHM = AES_256,  
   SERVER CERTIFICATE = BackupEncryptCert  
   ),  
  STATS = 10  
GO
```  
  
 <span data-ttu-id="79305-156">Para obter a sintaxe completa da instrução Transact-SQL, consulte [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="79305-156">For the full Transact-SQL statement syntax, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="using-powershell"></a><span data-ttu-id="79305-157">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="79305-157">Using PowerShell</span></span>  
 <span data-ttu-id="79305-158">Esse exemplo cria as opções de criptografia e as utiliza como um valor de parâmetro no cmdlet **Backup-SqlDatabase** para criar um backup criptografado.</span><span class="sxs-lookup"><span data-stu-id="79305-158">This example creates the encryption options and uses it as a parameter value in **Backup-SqlDatabase** cmdlet to create an encrypted backup.</span></span>  
  
```powershell
$encryptionOption = New-SqlBackupEncryptionOption -Algorithm Aes256 -EncryptorType ServerCertificate -EncryptorName "BackupCert"  
Backup-SqlDatabase -ServerInstance . -Database "MyTestDB" -BackupFile "MyTestDB.bak" -CompressionOption On -EncryptionOption $encryptionOption  
```  
  
##  <a name="recommended-practices"></a><a name="RecommendedPractices"></a> <span data-ttu-id="79305-159">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="79305-159">Recommended Practices</span></span>  
 <span data-ttu-id="79305-160">Crie um backup do certificado e das chaves de criptografia em um local que não seja o computador local em que a instância está instalada.</span><span class="sxs-lookup"><span data-stu-id="79305-160">Create a backup of the encryption certificate and keys to a location other than your local machine where the instance is installed.</span></span> <span data-ttu-id="79305-161">Para dar conta de cenários de recuperação de desastre, é recomendável armazenar um backup do certificado ou da chave em um local externo.</span><span class="sxs-lookup"><span data-stu-id="79305-161">To account for disaster recovery scenarios, consider storing a backup of the certificate or key to an off-site location.</span></span> <span data-ttu-id="79305-162">Você não pode restaurar um backup criptografado sem o certificado usado para criptografar o backup.</span><span class="sxs-lookup"><span data-stu-id="79305-162">You cannot restore an encrypted backup without the certificate used to encrypt the backup.</span></span>  
  
 <span data-ttu-id="79305-163">Para restaurar um backup criptografado, o certificado original usado quando o backup foi feito com a impressão digital correspondente deve estar disponível na instância para a qual você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="79305-163">To restore an encrypted backup, the original certificate used when the backup was taken with the matching thumbprint should be available on the instance you are restoring to.</span></span> <span data-ttu-id="79305-164">Portanto, o certificado não deve ser renovado na expiração nem alterado de forma alguma.</span><span class="sxs-lookup"><span data-stu-id="79305-164">Therefore, the certificate should not be renewed on expiry or changed in any way.</span></span> <span data-ttu-id="79305-165">A renovação pode resultar na atualização do certificado que está disparando a alteração da impressão digital, tornando o certificado inválido para o arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="79305-165">Renewal can result in updating the certificate triggering the change of the thumbprint, therefore making the certificate invalid for the backup file.</span></span> <span data-ttu-id="79305-166">A conta que executa a restauração deve ter as permissões VIEW DEFINITION no certificado ou na chave assimétrica usada na criptografia durante o backup.</span><span class="sxs-lookup"><span data-stu-id="79305-166">The account performing the restore should have VIEW DEFINITION permissions on the certificate or the asymmetric key used to encrypt during backup.</span></span>  
  
 <span data-ttu-id="79305-167">Os backups de banco de dados do Grupo de Disponibilidade são tipicamente executados na réplica de backup preferencial.</span><span class="sxs-lookup"><span data-stu-id="79305-167">Availability Group database backups are typically performed on the preferred backup replica.</span></span>  <span data-ttu-id="79305-168">Se estiver restaurando um backup em uma réplica diferente daquela em que foi feito o backup, verifique se o certificado original usado para o backup está disponível na réplica para onde você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="79305-168">If restoring a backup on a replica other than where the backup was taken from, ensure that the original certificate used for backup is available on the replica you are restoring to.</span></span>  
  
 <span data-ttu-id="79305-169">Se o banco de dados for habilitado para TDE, escolha diferentes certificados ou chaves assimétricas na criptografia do banco de dados e do backup para aumentar a segurança.</span><span class="sxs-lookup"><span data-stu-id="79305-169">If the database is TDE enabled, choose different certificates or asymmetric keys for encrypting the database and the backup to increase security.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="79305-170">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="79305-170">Related Tasks</span></span>  
  
|<span data-ttu-id="79305-171">Tópico/tarefa</span><span class="sxs-lookup"><span data-stu-id="79305-171">Topic/Task</span></span>|<span data-ttu-id="79305-172">Descrição</span><span class="sxs-lookup"><span data-stu-id="79305-172">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="79305-173">Criar um backup criptografado</span><span class="sxs-lookup"><span data-stu-id="79305-173">Create an Encrypted Backup</span></span>](create-an-encrypted-backup.md)|<span data-ttu-id="79305-174">Descreve as etapas básicas necessárias para criar um backup criptografado</span><span class="sxs-lookup"><span data-stu-id="79305-174">Describes the basic steps required to create an encrypted backup</span></span>|  
|[<span data-ttu-id="79305-175">Backup gerenciado do SQL Server para Azure – Configurações de retenção e armazenamento</span><span class="sxs-lookup"><span data-stu-id="79305-175">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)|<span data-ttu-id="79305-176">Descreve as etapas básicas necessárias para configurar o [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] com as opções de criptografia especificadas.</span><span class="sxs-lookup"><span data-stu-id="79305-176">Describes the basic steps required to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with the encryption options specified.</span></span>|  
|[<span data-ttu-id="79305-177">Gerenciamento extensível de chaves usando o Cofre de Chaves do Azure &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="79305-177">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md)|<span data-ttu-id="79305-178">Fornece um exemplo de como criar um backup criptografado protegido por chaves no Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="79305-178">Provides an example of creating an encrypted backup protected by keys in the Azure Key Vault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79305-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79305-179">See Also</span></span>  
 [<span data-ttu-id="79305-180">Visão geral do backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="79305-180">Backup Overview &#40;SQL Server&#41;</span></span>](backup-overview-sql-server.md)  
  
  
