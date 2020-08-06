---
title: 'Lição 9: Restaurar um banco de dados do armazenamento do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ebba12c7-3d13-4c9d-8540-ad410a08356d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5e7c2350bb2a9b1f8c31da8e094459b5bc8ccd90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583027"
---
# <a name="lesson-9-restore-a-database-from-azure-storage"></a><span data-ttu-id="9b0d5-103">Lição 9:</span><span class="sxs-lookup"><span data-stu-id="9b0d5-103">Lesson 9.</span></span> <span data-ttu-id="9b0d5-104">Restaurar um banco de dados do Armazenamento do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="9b0d5-104">Restore a database from Azure Storage</span></span>
  <span data-ttu-id="9b0d5-105">Nesta lição, você aprenderá a restaurar um arquivo de backup de banco de dados do armazenamento do Azure para um banco de dados, que reside no local ou em uma máquina virtual no Azure.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-105">In this lesson, you will learn how to restore a database backup file from Azure Storage to a database, which either resides on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="9b0d5-106">Para acompanhar esta lição, você não precisará concluir as lições 4, 5, 6, 7 e 8.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-106">To follow this lesson, you do not need to complete Lesson 4, 5, 6, 7, and 8.</span></span>  
  
 <span data-ttu-id="9b0d5-107">Esta lição supõe que você já concluiu as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9b0d5-107">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="9b0d5-108">Você criou um banco de dados no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-108">You have created a database in the source machine.</span></span>  
  
-   <span data-ttu-id="9b0d5-109">Você criou um backup do seu banco de dados (. bak) no armazenamento do Azure usando o recurso de [SQL Server Backup e restauração com o serviço de armazenamento de BLOBs do Azure](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="9b0d5-109">You have created a backup of your database (.bak) in Azure Storage by using the [SQL Server Backup and Restore with Azure Blob Storage Service](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) feature.</span></span> <span data-ttu-id="9b0d5-110">Observe que você precisará criar outra Credencial do SQL Server nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-110">Note that you will need to create another SQL Server Credential in this step.</span></span> <span data-ttu-id="9b0d5-111">Essa credencial usará as chaves da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-111">This credential uses storage account keys.</span></span>  
  
-   <span data-ttu-id="9b0d5-112">Você tem uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-112">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="9b0d5-113">Você criou um contêiner em sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-113">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="9b0d5-114">Você criou uma política em um contêiner com direitos de leitura, gravação e lista.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-114">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="9b0d5-115">Você também gerou uma chave de SAS.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-115">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="9b0d5-116">Você criou uma credencial de SQL Server no seu computador para o recurso de integração de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-116">You have created a SQL Server credential on your machine for Azure Storage Integration feature.</span></span> <span data-ttu-id="9b0d5-117">Observe que essa credencial exige uma chave SAS (assinatura de acesso compartilhado).</span><span class="sxs-lookup"><span data-stu-id="9b0d5-117">Note that this credential requires a Shared Access Signature (SAS) key.</span></span>  
  
 <span data-ttu-id="9b0d5-118">Para restaurar um banco de dados do armazenamento do Azure, você pode seguir estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9b0d5-118">To restore a database from Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="9b0d5-119">Inicie o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-119">Start SQL Server Management Studio.</span></span> <span data-ttu-id="9b0d5-120">Conecte-se à instância padrão.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-120">Connect to the default instance.</span></span>  
  
2.  <span data-ttu-id="9b0d5-121">Clique em **nova consulta** na barra de ferramentas padrão.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-121">Click **New Query** on the Standard Toolbar.</span></span>  
  
3.  <span data-ttu-id="9b0d5-122">Copie e cole o script completo a seguir na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-122">Copy and paste the following complete script to the query window.</span></span> <span data-ttu-id="9b0d5-123">Modifique o script conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-123">Modify the script as needed.</span></span>  
  
     <span data-ttu-id="9b0d5-124">**Observação:** Você executa a `RESTORE` instrução para restaurar o backup do banco de dados (. bak) no armazenamento do Azure para uma instância de banco de dados em outro computador.</span><span class="sxs-lookup"><span data-stu-id="9b0d5-124">**Note:** You run the `RESTORE` statement to restore the database backup (.bak) in Azure Storage to a database instance in another machine.</span></span>  
  
    ```sql  
  
    USE master   
    GO   
    -- Create a new database to be backed up.   
    CREATE DATABASE TestDbRestoreFrom;   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    SELECT * from dbo.Table1;   
    GO   
    -- Create a credential to be used by SQL Server Backup and Restore with Azure -----Blob Storage Service.   
    USE master;   
    GO   
    CREATE CREDENTIAL BackupCredential    
    WITH IDENTITY= 'teststorageaccnt',   
    SECRET = 'BO1nH/lWRdnc8TGPlQIXmGLWVCoEa48suYSGiAlC73+S0TX5VXo5/LCm8qiyGCYafDg4ZsueDIV3GQ5RXHaRGw=='    
    GO   
    -- Display the newly created credential   
    SELECT * from sys.credentials   
    -- Create a backup in Azure Storage.   
    BACKUP DATABASE TestDBRestoreFrom    
    TO URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
          WITH CREDENTIAL = 'BackupCredential'    
         ,COMPRESSION   
         ,STATS = 5;   
    GO    
    -- Create a Shared Access Signature credential   
    CREATE CREDENTIAL [https://teststorageaccnt.blob.core.windows.net/testrestorefrom]   
    WITH IDENTITY='SHARED ACCESS SIGNATURE',   
    SECRET = 'sv=2012-02-12&sr=c&si=policy_resfrom&sig=EhVpzLUXjG4ThAMLmVhrnoiCt8IfmD3BsuYiMawGzxc%3D'   
    GO   
    USE master;   
    GO   
    RESTORE DATABASE TestDBRestoreFrom    
    FROM URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
    WITH    
    CREDENTIAL = 'BackupCredential',    
    REPLACE,   
    MOVE 'TestDBRestoreFrom' TO 'C:\Backup\TestDBRestoreFrom.mdf',     
    MOVE 'TestDBRestoreFrom_log' TO 'C:\Backup\TestDBRestoreFrom_log.ldf';   
    GO  
  
    ```  
  
 <span data-ttu-id="9b0d5-125">**Fim do tutorial: SQL Server arquivos de dados no serviço de armazenamento do Azure**</span><span class="sxs-lookup"><span data-stu-id="9b0d5-125">**End of Tutorial: SQL Server Data Files in Azure Storage service**</span></span>  
  
  
