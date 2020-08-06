---
title: 'Lição 8: Restaurar um banco de dados no armazenamento do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9f99670-e1de-441e-972c-69faffcac17a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: adec725d1b519fb67560dc572823ba0a116aaa54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583028"
---
# <a name="lesson-8-restore-a-database-to-azure-storage"></a><span data-ttu-id="3473a-103">Lição 8:</span><span class="sxs-lookup"><span data-stu-id="3473a-103">Lesson 8.</span></span> <span data-ttu-id="3473a-104">Restaurar um banco de dados no Armazenamento do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="3473a-104">Restore a database to Azure Storage</span></span>
  <span data-ttu-id="3473a-105">Nesta lição, você aprenderá a criar um arquivo de backup localmente e, em seguida, restaurá-lo no armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="3473a-105">In this lesson, you will learn how to create a backup file locally and then restore it to Azure Storage.</span></span> <span data-ttu-id="3473a-106">Observe que você pode ter seu banco de dados no local ou em uma máquina virtual no Azure.</span><span class="sxs-lookup"><span data-stu-id="3473a-106">Note that you can have your database either on either on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="3473a-107">Para acompanhar esta lição, você não precisará concluir as lições 4, 5, 6 e 7.</span><span class="sxs-lookup"><span data-stu-id="3473a-107">To follow this lesson, you do not need to complete Lesson 4, 5, 6, and 7.</span></span>  
  
 <span data-ttu-id="3473a-108">Esta lição supõe que você já concluiu as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3473a-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="3473a-109">Você tem uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="3473a-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="3473a-110">Você criou um contêiner em sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="3473a-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="3473a-111">Você criou uma política em um contêiner com direitos de leitura, gravação e lista.</span><span class="sxs-lookup"><span data-stu-id="3473a-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="3473a-112">Você também gerou uma chave de SAS.</span><span class="sxs-lookup"><span data-stu-id="3473a-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="3473a-113">Você criou uma credencial do SQL Server no computador de origem com base na Assinatura de Acesso Compartilhado.</span><span class="sxs-lookup"><span data-stu-id="3473a-113">You have created a SQL Server credential on the source machine based on Shared Access Signature.</span></span>  
  
-   <span data-ttu-id="3473a-114">Você criou um banco de dados no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="3473a-114">You have created a database in the source machine.</span></span>  
  
 <span data-ttu-id="3473a-115">Para restaurar um banco de dados no armazenamento do Azure, você pode seguir estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3473a-115">To restore a database to Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="3473a-116">No computador de origem, inicie o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="3473a-116">In the source machine, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="3473a-117">Quando conectado ao banco de dados recém-criado, abra a janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="3473a-117">When connected to the newly created database, open the query window.</span></span> <span data-ttu-id="3473a-118">Execute a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="3473a-118">Run the following statement:</span></span>  
  
    ```sql  
  
    USE TestDB3Restore;   
    GO   
    BACKUP DATABASE TestDB3Restore   
    TO DISK = 'C:\BACKUP\TestDB3Restore.Bak'   
       WITH FORMAT,   
       NAME = 'Full Backup of TestDB3Restore'   
    GO  
  
    ```  
  
3.  <span data-ttu-id="3473a-119">Depois, copie e execute as seguintes instruções na janela Consulta.</span><span class="sxs-lookup"><span data-stu-id="3473a-119">Next, copy and run the following statements in the Query window.</span></span>  
  
    ```sql  
  
    USE master;   
    GO   
    RESTORE DATABASE TestDB3Restore    
    FROM DISK = 'C:\BACKUP\TestDB3Restore.bak'    
    WITH REPLACE,   
    MOVE 'TestDB3Restore' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore.mdf',     
    MOVE 'TestDB3Restore_log' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore_log.ldf';   
    GO  
  
    ```  
  
     <span data-ttu-id="3473a-120">No final dessa etapa, o contêiner listará os dados (.mdf) e os arquivos (.ldf) no Portal de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="3473a-120">At the end of this step, your container should list data (.mdf) and (.ldf) files on the Management Portal.</span></span>  
  
 <span data-ttu-id="3473a-121">Para restaurar um banco de dados com arquivos de log e de logs apontando para o armazenamento do Azure usando SQL Server Management Studio interface do usuário, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3473a-121">To restore a database with data and log files pointing to Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="3473a-122">No Pesquisador de **objetos**, clique no nome do servidor para expandir a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="3473a-122">In **Object Explorer**, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3473a-123">Expanda **bancos**de dados e, em seguida, selecione o seu Database.</span><span class="sxs-lookup"><span data-stu-id="3473a-123">Expand **Databases**, and, select your database.</span></span>  
  
3.  <span data-ttu-id="3473a-124">Clique com o botão direito do mouse no banco de dados, aponte para **Tarefas**e clique em **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="3473a-124">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="3473a-125">Na página **geral** , na seção **restaurar** origem, clique em dispositivo de **origem** .</span><span class="sxs-lookup"><span data-stu-id="3473a-125">On the **General** page, in the **Restore** source section, click **Source** device.</span></span>  
  
5.  <span data-ttu-id="3473a-126">Clique no botão procurar da caixa de texto dispositivo de **origem** , que abre a caixa de diálogo **selecionar dispositivos de backup** .</span><span class="sxs-lookup"><span data-stu-id="3473a-126">Click the browse button for the **Source** device text box, which opens the **Select Backup Devices** dialog box.</span></span>  
  
6.  <span data-ttu-id="3473a-127">Na caixa de texto mídia de backup, selecione **arquivo**e clique no botão **Adicionar** para localizar o arquivo de backup (. bak).</span><span class="sxs-lookup"><span data-stu-id="3473a-127">In the Backup media text box, select **File**, and click the **Add** button to locate the backup (.bak) file.</span></span> <span data-ttu-id="3473a-128">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3473a-128">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="3473a-129">Clique em **arquivos** na primeira página.</span><span class="sxs-lookup"><span data-stu-id="3473a-129">Click **Files** on the first page.</span></span>  
  
8.  <span data-ttu-id="3473a-130">Na seção **restaurar arquivos de banco de dados** como, em campo **restaurar como** , digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3473a-130">In the **Restore Database Files** as section, under **Restore As** field, type the followings:</span></span>  
  
     <span data-ttu-id="3473a-131">Para arquivo de dados, digite: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf` .</span><span class="sxs-lookup"><span data-stu-id="3473a-131">For data file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf`.</span></span> <span data-ttu-id="3473a-132">Para arquivo de log, digite: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf` .</span><span class="sxs-lookup"><span data-stu-id="3473a-132">For log file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf`.</span></span>  
  
     <span data-ttu-id="3473a-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="3473a-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span></span>  
  
9. <span data-ttu-id="3473a-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3473a-134">Click **OK**.</span></span>  
  
 <span data-ttu-id="3473a-135">Quando a restauração for feita, faça logon no Portal de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="3473a-135">When the restore is done, log in to the Management Portal.</span></span> <span data-ttu-id="3473a-136">Você verá os arquivos .mdf e .ldf no contêiner da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3473a-136">You should be able to see the .mdf and .ldf files in the container as follows:</span></span>  
  
 <span data-ttu-id="3473a-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="3473a-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="3473a-138">**Próxima lição:**</span><span class="sxs-lookup"><span data-stu-id="3473a-138">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="3473a-139">Lição 9. Restaurar um banco de dados do armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="3473a-139">Lesson 9. Restore a database from Azure Storage</span></span>](../relational-databases/lesson-8-restore-as-new-database-from-log-backup.md)  
  
  
