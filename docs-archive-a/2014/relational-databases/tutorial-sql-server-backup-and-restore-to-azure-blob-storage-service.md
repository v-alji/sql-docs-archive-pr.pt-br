---
title: 'Tutorial: backup e restauração do SQL Server para o Serviço de Armazenamento de Blobs do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 9e1d94ce-2c93-45d1-ae2a-2a7d1fa094c4
author: rothja
ms.author: jroth
ms.openlocfilehash: d15200968011cdb314829736512f39730782dc0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679286"
---
# <a name="tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service"></a><span data-ttu-id="b3bdc-102">Tutorial: Backup e restauração do SQL Server no serviço de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="b3bdc-102">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>
  <span data-ttu-id="b3bdc-103">Bem-vindo ao tutorial de Introdução com SQL Server Backup e restauração com o serviço de armazenamento de BLOBs do Azure.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-103">Welcome to the Getting Started with SQL Server Backup and Restore with Azure Blob Storage Service tutorial.</span></span> <span data-ttu-id="b3bdc-104">Este tutorial ajudará você a compreender como gravar backups e executar restaurações no serviço de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-104">This tutorial helps you understand how to write backups to and restore from the Azure Blob storage service.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="b3bdc-105">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="b3bdc-105">What You Will Learn</span></span>  
 <span data-ttu-id="b3bdc-106">Este tutorial mostra como criar uma conta de armazenamento do Windows, um contêiner de blob, criando credenciais para acessar a conta de armazenamento, gravando um backup no serviço de blob e executando uma restauração simples.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-106">This tutorial shows you how to create a Windows Storage account, a blob container, creating credentials to access the storage account, writing a backup to the blob service, and performing a simple restore.</span></span> <span data-ttu-id="b3bdc-107">Este tutorial é dividido em quatro lições:</span><span class="sxs-lookup"><span data-stu-id="b3bdc-107">This tutorial is divided into four lessons:</span></span>  
  
 [<span data-ttu-id="b3bdc-108">Lição 1: criar objetos de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="b3bdc-108">Lesson 1: Create Azure Storage Objects</span></span>](../tutorials/lesson-1-create-windows-azure-storage-objects.md)  
 <span data-ttu-id="b3bdc-109">Nesta lição, você criará uma conta de armazenamento do Azure e um contêiner de blobs.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-109">In this lesson, you create an Azure storage account and a blob container.</span></span>  
  
 [<span data-ttu-id="b3bdc-110">Lição 2: Criar uma credencial do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3bdc-110">Lesson 2: Create a SQL Server Credential</span></span>](../tutorials/lesson-2-create-a-sql-server-credential.md)  
 <span data-ttu-id="b3bdc-111">Nesta lição, você criará uma credencial para armazenar as informações de segurança usadas para acessar a conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-111">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 [<span data-ttu-id="b3bdc-112">Lição 3: Gravar um backup de banco de dados completo no serviço de Armazenamento de Blobs</span><span class="sxs-lookup"><span data-stu-id="b3bdc-112">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>](../tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md)  
 <span data-ttu-id="b3bdc-113">Nesta lição, você gerará uma instrução T-SQL para gravar um backup do banco de dados AdventureWorks2012 no serviço de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-113">In this lesson, you issue a T-SQL statement to write a backup of the AdventureWorks2012 database to the Azure Blob storage service.</span></span>  
  
 [<span data-ttu-id="b3bdc-114">Lição 4: Executar uma restauração de um backup de banco de dados completo</span><span class="sxs-lookup"><span data-stu-id="b3bdc-114">Lesson 4: Perform a Restore From a Full Database Backup</span></span>](../tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md)  
 <span data-ttu-id="b3bdc-115">Nesta lição, você emitirá uma instrução T-SQL para fazer a restauração a partir do backup de banco de dados criado na lição anterior.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-115">In this lesson, you issue a T-SQL statement to restore from the database backup you created in the previous lesson.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="b3bdc-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3bdc-116">Requirements</span></span>  
 <span data-ttu-id="b3bdc-117">Para concluir este tutorial, você deve estar familiarizado com os conceitos de backup e restauração do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e a sintaxe do T-SQL.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-117">To complete this tutorial, you must be familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore concepts and T-SQL syntax.</span></span> <span data-ttu-id="b3bdc-118">Para usar este tutorial, o sistema deve atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="b3bdc-118">To use this tutorial, your system must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="b3bdc-119">Uma instância do [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], e o banco de dados AdventureWorks2012 instalado.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-119">An instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], and AdventureWorks2012 database installed.</span></span>  
  
     <span data-ttu-id="b3bdc-120">A instância do SQL Server pode ser local ou em uma máquina virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-120">The SQL Server instance can be on-premises or in an Azure Virtual Machine.</span></span>  
  
     <span data-ttu-id="b3bdc-121">Você pode usar um banco de dados de usuário no lugar do AdventureWorks2012 e modificar a sintaxe do tsql adequadamente.</span><span class="sxs-lookup"><span data-stu-id="b3bdc-121">You can use a user database in place of AdventureWorks2012, and modify the tsql syntax accordingly.</span></span>  
  
-   <span data-ttu-id="b3bdc-122">A conta de usuário usada para emitir os comandos BACKUP ou RESTORE deve estar na função de banco de dados **operador db_backup** com as permissões **Alterar qualquer credencial** .</span><span class="sxs-lookup"><span data-stu-id="b3bdc-122">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
### <a name="additional-reading"></a><span data-ttu-id="b3bdc-123">Leituras Adicionais</span><span class="sxs-lookup"><span data-stu-id="b3bdc-123">Additional Reading</span></span>  
 <span data-ttu-id="b3bdc-124">Estas são algumas leituras que podem ajudar a compreender os conceitos e as práticas recomendadas ao usar o serviço de armazenamento de Blobs do Azure para backups do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3bdc-124">Following are some recommended reading to understand the concepts, best practices when using Azure Blob storage service for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups.</span></span>  
  
1.  [<span data-ttu-id="b3bdc-125">Backup e restauração do SQL Server no serviço de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="b3bdc-125">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
2.  [<span data-ttu-id="b3bdc-126">Solução de problemas e melhores práticas de backup do SQL Server para URL</span><span class="sxs-lookup"><span data-stu-id="b3bdc-126">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](backup-restore/sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
  
  
