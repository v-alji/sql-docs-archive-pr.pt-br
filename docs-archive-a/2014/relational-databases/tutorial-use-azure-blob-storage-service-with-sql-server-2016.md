---
title: 'Tutorial: SQL Server arquivos de dados no serviço de armazenamento do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e69be67d-da1c-41ae-8c9a-6b12c8c2fb61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 21a0fc11706a0c5ee35cf71e1af69f2927adc9db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583451"
---
# <a name="tutorial-sql-server-data-files-in-azure-storage-service"></a><span data-ttu-id="cf967-102">Tutorial: Arquivos de dados do SQL Server no serviço de Armazenamento do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="cf967-102">Tutorial: SQL Server Data Files in Azure Storage service</span></span>
  <span data-ttu-id="cf967-103">Bem-vindo ao tutorial SQL Server arquivos de dados no serviço de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="cf967-103">Welcome to the  SQL Server Data Files in Azure Storage Service tutorial.</span></span> <span data-ttu-id="cf967-104">Este tutorial explica como armazenar diretamente os arquivos de dados do SQL Server no serviço de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="cf967-104">This tutorial helps you understand how to store SQL Server data files in the Azure Blob storage service directly.</span></span>  
  
 <span data-ttu-id="cf967-105">SQL Server suporte à integração para o serviço de armazenamento de BLOBs do Azure é um aprimoramento SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="cf967-105">SQL Server integration support for the Azure Blob storage service is a SQL Server 2014 enhancement.</span></span> <span data-ttu-id="cf967-106">Para obter uma visão geral da funcionalidade e dos benefícios de usar essa funcionalidade, consulte [SQL Server arquivos de dados no Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="cf967-106">For an overview of the functionality and benefits of using this functionality, see [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="cf967-107">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="cf967-107">What you will learn</span></span>  
 <span data-ttu-id="cf967-108">Este tutorial mostra como armazenar SQL Server arquivos de dados no serviço de armazenamento do Azure em várias lições.</span><span class="sxs-lookup"><span data-stu-id="cf967-108">This tutorial shows you how to store SQL Server Data Files in Azure Storage service in multiple lessons.</span></span> <span data-ttu-id="cf967-109">Cada lição é centrada em uma tarefa específica.</span><span class="sxs-lookup"><span data-stu-id="cf967-109">Each lesson is focused on a specific task.</span></span> <span data-ttu-id="cf967-110">Primeiro, você aprenderá a criar uma conta de armazenamento e um contêiner no Azure.</span><span class="sxs-lookup"><span data-stu-id="cf967-110">First, you will learn how to create a storage account and a container in Azure.</span></span> <span data-ttu-id="cf967-111">Em seguida, você aprenderá a criar uma credencial SQL Server para poder integrar o SQL Server ao armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="cf967-111">Then, you will learn how to create a SQL Server credential to be able to integrate SQL Server with Azure Storage.</span></span> <span data-ttu-id="cf967-112">Em seguida, você criará um banco de dados no armazenamento do Azure diretamente.</span><span class="sxs-lookup"><span data-stu-id="cf967-112">Then, you will create a database in Azure Storage directly.</span></span> <span data-ttu-id="cf967-113">Além disso, o tutorial demonstrará criptografia, migração e os cenários de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="cf967-113">In addition, the tutorial will demonstrate encryption, migration, and backup and restore scenarios.</span></span>  
  
 <span data-ttu-id="cf967-114">Este tutorial divide-se em nove lições:</span><span class="sxs-lookup"><span data-stu-id="cf967-114">This tutorial is divided into nine lessons:</span></span>  
  
 <span data-ttu-id="cf967-115">**[Lição 1: Criar um contêiner e uma conta de Armazenamento do Microsoft Azure](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-115">**[Lesson 1: Create Azure Storage Account and Container](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span></span>  
 <span data-ttu-id="cf967-116">Nesta lição, você criará uma conta de armazenamento do Azure e um contêiner.</span><span class="sxs-lookup"><span data-stu-id="cf967-116">In this lesson, you create an Azure Storage account and a container.</span></span>  
  
 <span data-ttu-id="cf967-117">**[Lição 2. Criar uma política no contêiner e gerar uma assinatura de acesso compartilhado &#40;chave de&#41; SAS](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-117">**[Lesson 2. Create a policy on container and generate a Shared Access Signature &#40;SAS&#41; key](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="cf967-118">Nesta lição, você criará uma política no contêiner do blob e também gerará uma assinatura de acesso compartilhado.</span><span class="sxs-lookup"><span data-stu-id="cf967-118">In this lesson, you create a policy on the Blob container and also generate a shared access signature.</span></span>  
  
 <span data-ttu-id="cf967-119">**[Lição 3: Criar uma credencial do SQL Server](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-119">**[Lesson 3: Create a SQL Server Credential](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="cf967-120">Nesta lição, você criará uma credencial para armazenar as informações de segurança usadas para acessar a conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="cf967-120">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="cf967-121">**[Lição 4: Criar um banco de dados no Armazenamento do Microsoft Azure](../relational-databases/lesson-3-database-backup-to-url.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-121">**[Lesson 4: Create a database in Azure Storage](../relational-databases/lesson-3-database-backup-to-url.md)**</span></span>  
 <span data-ttu-id="cf967-122">Nesta lição, você criará um banco de dados no armazenamento do Azure usando a opção criar nome de arquivo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cf967-122">In this lesson, you create a database in Azure Storage using CREATE Database FILENAME option.</span></span>  
  
 <span data-ttu-id="cf967-123">**[Lição 5. &#40;opcional&#41; criptografar seu banco de dados usando TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-123">**[Lesson 5. &#40;Optional&#41; Encrypt your database using TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span></span>  
 <span data-ttu-id="cf967-124">Nesta lição, você criptografará o banco de dados usando uma criptografia de dados transparente (TDE) e um certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="cf967-124">In this lesson, you encrypt your database by using a transparent data encryption (TDE) and a server certificate.</span></span>  
  
 <span data-ttu-id="cf967-125">**[Lição 6: Migrar um banco de dados de um computador de origem no local para um computador de destino no Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-125">**[Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="cf967-126">Nesta lição, você migra um banco de dados do local para uma máquina virtual no Azure usando a opção criar banco de dados para anexar.</span><span class="sxs-lookup"><span data-stu-id="cf967-126">In this lesson, you migrate a database from on-premises to a virtual machine in Azure using CREATE DATABASE FOR ATTACH option.</span></span>  
  
 <span data-ttu-id="cf967-127">**[Lição 7: Migrar seus arquivos de dados para o Armazenamento do Microsoft Azure](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-127">**[Lesson 7: Move your data files to Azure Storage](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="cf967-128">Nesta lição, você move os arquivos de dados para o armazenamento do Azure usando a instrução ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cf967-128">In this lesson, you move your data files to Azure Storage using ALTER DATABASE statement.</span></span>  
  
 <span data-ttu-id="cf967-129">**[Lição 8. Restaurar um banco de dados no armazenamento do Azure](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-129">**[Lesson 8. Restore a database to Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span></span>  
 <span data-ttu-id="cf967-130">Nesta lição, você restaura um banco de dados no armazenamento do Azure usando a opção de movimentação do banco de dados de restauração.</span><span class="sxs-lookup"><span data-stu-id="cf967-130">In this lesson, you restore a database to Azure Storage using RESTORE Database MOVE option.</span></span>  
  
 <span data-ttu-id="cf967-131">**[Lição 9. Restaurar um banco de dados do armazenamento do Azure](lesson-8-restore-as-new-database-from-log-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="cf967-131">**[Lesson 9. Restore a database from Azure Storage](lesson-8-restore-as-new-database-from-log-backup.md)**</span></span>  
 <span data-ttu-id="cf967-132">Nesta lição, você restaura um banco de dados do armazenamento do Azure usando a opção de movimentação do banco de dados de restauração.</span><span class="sxs-lookup"><span data-stu-id="cf967-132">In this lesson, you restore a database from Azure Storage using RESTORE Database MOVE option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf967-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cf967-133">See Also</span></span>  
 [<span data-ttu-id="cf967-134">SQL Server arquivos de dados no Azure</span><span class="sxs-lookup"><span data-stu-id="cf967-134">SQL Server Data Files in Azure</span></span>](databases/sql-server-data-files-in-microsoft-azure.md)  
  
  
