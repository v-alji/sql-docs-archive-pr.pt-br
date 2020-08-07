---
title: 'Lição 6: migrar um banco de dados de um computador de origem local para um computador de destino no Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: d9134ade-7b03-4c5c-8ed3-3bc369a61691
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9af8a260493561f9728d1677b7667bd3f36cb46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576373"
---
# <a name="lesson-6-migrate-a-database-from-a-source-machine-on-premises-to-a-destination-machine-in-azure"></a><span data-ttu-id="ff346-102">Lição 6: Migrar um banco de dados de um computador de origem no local para um computador de destino no Azure</span><span class="sxs-lookup"><span data-stu-id="ff346-102">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>
  <span data-ttu-id="ff346-103">Esta lição pressupõe que você já tem outra SQL Server, que pode residir em outro computador local ou em uma máquina virtual no Azure.</span><span class="sxs-lookup"><span data-stu-id="ff346-103">This lesson assumes that you already have another SQL Server, which might reside in another on-premises computer or in a virtual machine in Azure.</span></span> <span data-ttu-id="ff346-104">Para obter informações sobre como criar uma máquina virtual SQL Server no Azure, consulte [Provisionando uma máquina virtual SQL Server no Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span><span class="sxs-lookup"><span data-stu-id="ff346-104">For information on how to create a SQL Server virtual machine in Azure, see [Provisioning a SQL Server Virtual Machine on Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span></span> <span data-ttu-id="ff346-105">Depois de provisionar uma máquina virtual SQL Server no Azure, verifique se você pode se conectar a uma instância do SQL Server nessa máquina virtual por meio de SQL Server Management Studio em outro computador.</span><span class="sxs-lookup"><span data-stu-id="ff346-105">After provisioning a SQL Server virtual machine in Azure, make sure that you can connect to an instance of SQL Server in this virtual machine via SQL Server Management Studio in another computer.</span></span>  
  
 <span data-ttu-id="ff346-106">Esta lição supõe também que você já concluiu as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ff346-106">This lesson also assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="ff346-107">Você tem uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="ff346-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="ff346-108">Você criou um contêiner em sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="ff346-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="ff346-109">Você criou uma política em um contêiner com direitos de leitura, gravação e lista.</span><span class="sxs-lookup"><span data-stu-id="ff346-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="ff346-110">Você também gerou uma chave de SAS.</span><span class="sxs-lookup"><span data-stu-id="ff346-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="ff346-111">Você criou uma credencial do SQL Server no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="ff346-111">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="ff346-112">Você já criou um destino SQL Server máquina virtual no Azure.</span><span class="sxs-lookup"><span data-stu-id="ff346-112">You already have created a destination SQL Server virtual machine in Azure.</span></span> <span data-ttu-id="ff346-113">É recomendável que você a crie selecionando uma imagem da plataforma que inclua o SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="ff346-113">We recommend that you create it by selecting a platform image that includes SQL Server 2014.</span></span>  
  
 <span data-ttu-id="ff346-114">Para migrar um banco de dados do SQL Server local para outra máquina virtual no Azure, você pode seguir estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ff346-114">To migrate a database from SQL Server on-premises to another virtual machine in Azure, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="ff346-115">No computador de origem (que é um computador local neste tutorial), abra uma janela de consulta no SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="ff346-115">In the source machine (which is an on-premises computer in this tutorial), open a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="ff346-116">Desanexe seu banco de dados para movê-lo para outro computador executando estas instruções:</span><span class="sxs-lookup"><span data-stu-id="ff346-116">Detach your database to move it to another machine by executing these statements:</span></span>  
  
    ```  
    -- Detach the database in the source machine   
    USE master  
    EXEC sp_detach_db 'TestDB1', 'true';  
    ```  
  
2.  <span data-ttu-id="ff346-117">Se você precisar transferir um banco de dados para um computador de destino, primeiro você deverá prepará-lo.</span><span class="sxs-lookup"><span data-stu-id="ff346-117">If you need to transfer a database to a destination machine, first you must prepare it.</span></span> <span data-ttu-id="ff346-118">Para preparar seu computador de destino, primeiro é necessário criar uma credencial do SQL Server no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="ff346-118">To prepare your destination machine, first you need to create a SQL Server credential in the destination machine.</span></span> <span data-ttu-id="ff346-119">Se ele for um banco de dados criptografado, você precisará importar também o certificado do computador de origem para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="ff346-119">If it is an encrypted database, you need to import the certificate from the source machine to the destination machine as well.</span></span>  
  
    1.  <span data-ttu-id="ff346-120">Para criar uma credencial do SQL Server no computador de destino, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ff346-120">To create a SQL Server Credential in the destination machine, follow these steps:</span></span>  
  
        1.  <span data-ttu-id="ff346-121">Conecte-se ao computador de destino por meio do SQL Server Management Studio no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="ff346-121">Connect to the destination machine via SQL Server Management Studio in your source computer.</span></span>  <span data-ttu-id="ff346-122">Ou, inicie o SQL Server Management Studio no computador de destino diretamente.</span><span class="sxs-lookup"><span data-stu-id="ff346-122">Or, start SQL Server Management Studio in your destination computer directly.</span></span>  
  
        2.  <span data-ttu-id="ff346-123">Na barra de ferramentas Padrão , clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ff346-123">On the Standard tool bar, click **New Query**.</span></span>  
  
        3.  <span data-ttu-id="ff346-124">Copie e cole o exemplo a seguir na janela de consulta, e modifique conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ff346-124">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="ff346-125">A instrução a seguir cria uma credencial SQL Server para armazenar o certificado de acesso compartilhado do seu contêiner de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="ff346-125">The following statement creates a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
            ```sql  
  
            USE master   
            GO   
            CREATE CREDENTIAL [http://teststorageaccnt.blob.core.windows.net/testcontainer]   
            WITH IDENTITY='SHARED ACCESS SIGNATURE',   
            SECRET = 'your SAS key'   
            GO  
  
            ```  
  
        4.  <span data-ttu-id="ff346-126">Para ver todas as credenciais disponíveis, você pode executar a instrução a seguir na janela de consulta:</span><span class="sxs-lookup"><span data-stu-id="ff346-126">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
            ```sql  
            SELECT * from sys.credentials   
            ```  
  
        5.  <span data-ttu-id="ff346-127">Quando conectado a um servidor de destino, abra a janela de consulta e execute:</span><span class="sxs-lookup"><span data-stu-id="ff346-127">When connected to the destination server, open query window, and run:</span></span>  
  
            ```sql  
  
            -- Create a master key and a server certificate   
            USE master   
            GO   
            CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01'; -- You may use a different password.   
            GO   
            CREATE CERTIFICATE MySQLCert   
            FROM FILE = 'C:\certs\MySQLCert.CER'   
            WITH PRIVATE KEY   
            (   
            FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
            DECRYPTION BY PASSWORD = 'MySQLKey01'   
            );   
            GO  
  
            ```  
  
             <span data-ttu-id="ff346-128">No final dessa etapa, o computador de destino terá importado o certificado de criptografia que foi submetido a backup a partir do computador de origem.</span><span class="sxs-lookup"><span data-stu-id="ff346-128">At the end of this step, the destination machine has imported the encryption certificate that was backed up from the source machine.</span></span> <span data-ttu-id="ff346-129">Em seguida, você pode anexar os arquivos de dados ao computador de destino.</span><span class="sxs-lookup"><span data-stu-id="ff346-129">Next, you can attach the data files in the destination machine.</span></span>  
  
    2.  <span data-ttu-id="ff346-130">Em seguida, crie um banco de dados com arquivos de log e de logs apontando para os arquivos existentes no armazenamento do Azure usando a opção FOR ATTACH.</span><span class="sxs-lookup"><span data-stu-id="ff346-130">Then, create a database with data and log files pointing to the existing files in Azure Storage by using FOR ATTACH option.</span></span> <span data-ttu-id="ff346-131">Na janela de consulta, execute a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="ff346-131">In the query window, run the following statement:</span></span>  
  
        ```sql  
  
        --Create a database on the destination server   
        CREATE DATABASE TestDB1onDest   
        ON   
        (NAME = TestDB1_data,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf' )   
        LOG ON   
         (NAME = TestDB1_log,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
        FOR ATTACH   
        GO  
  
        ```  
  
    3.  <span data-ttu-id="ff346-132">No Pesquisador de Objetos, clique em Bancos de Dados e clique com o botão direito em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="ff346-132">On the Object Explorer, click Databases, right-click Refresh.</span></span> <span data-ttu-id="ff346-133">Você verá o banco de dados TestDB1onDest recém-criado listado.</span><span class="sxs-lookup"><span data-stu-id="ff346-133">You should be able to see the newly created database TestDB1onDest listed.</span></span>  
  
    4.  <span data-ttu-id="ff346-134">Em seguida, execute a seguinte instrução na janela de consulta:</span><span class="sxs-lookup"><span data-stu-id="ff346-134">Next, run the following statement in the query window:</span></span>  
  
        ```sql  
  
        USE TestDB1onDest   
        SELECT * FROM Table1;   
        GO  
  
        ```  
  
         <span data-ttu-id="ff346-135">Isso deve listar todos os dados que você inseriu na lição 4.</span><span class="sxs-lookup"><span data-stu-id="ff346-135">This should list all the data you entered in Lesson 4.</span></span>  
  
 <span data-ttu-id="ff346-136">Observe que o banco de dados criptografado foi transferido para outra instância do computador sem o movimento de dados.</span><span class="sxs-lookup"><span data-stu-id="ff346-136">Note that the encrypted database was transferred to another compute instance with no data movement.</span></span>  
  
 <span data-ttu-id="ff346-137">Para criar um banco de dados com arquivos de log e de logs apontando para os arquivos existentes no armazenamento do Azure usando SQL Server Management Studio interface do usuário, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ff346-137">To create a database with data and log files pointing to the existing files in Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="ff346-138">No **Pesquisador de Objetos**, conecte-se a uma instância do Mecanismo de Banco de Dados do SQL Server e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="ff346-138">In **Object Explorer**, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ff346-139">Clique com o botão direito do mouse em **Bancos de Dados**e clique em **Novo Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="ff346-139">Right-click **Databases**, and then click **New Database**.</span></span> <span data-ttu-id="ff346-140">Em seguida, clique com o botão direito do mouse em TestDB1.</span><span class="sxs-lookup"><span data-stu-id="ff346-140">Then, right-click TestDB1.</span></span> <span data-ttu-id="ff346-141">Clique em Tarefas e, em seguida, clique em Desanexar.</span><span class="sxs-lookup"><span data-stu-id="ff346-141">Click Tasks, and then click Detach.</span></span> <span data-ttu-id="ff346-142">Na janela da caixa de diálogo Desanexar, marque Descartar Conexões.</span><span class="sxs-lookup"><span data-stu-id="ff346-142">In the Detach dialog window, check Drop Connections.</span></span> <span data-ttu-id="ff346-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff346-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="ff346-144">Conecte-se ao computador de destino, que tem o SQL Server CTP2 2014 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="ff346-144">Connect to the destination machine, which has SQL Server 2014 CTP2 or later.</span></span> <span data-ttu-id="ff346-145">Para preparar seu computador de destino, é necessário criar uma credencial do SQL Server no computador de destino que aponte para o mesmo contêiner em que você colocou TestDB1.</span><span class="sxs-lookup"><span data-stu-id="ff346-145">To prepare your destination machine, you need to create a SQL Server credential in the destination machine to point to the same container that you put TestDB1 in.</span></span> <span data-ttu-id="ff346-146">Se você pretende anexar novamente no mesmo computador, não será necessário criar outra credencial.</span><span class="sxs-lookup"><span data-stu-id="ff346-146">If you are going to re-attach in the same computer, you do not need to create another credential.</span></span>  
  
4.  <span data-ttu-id="ff346-147">No Pesquisador de **objetos**, clique com o botão direito do mouse em **bancos de dados** e clique em **anexar**.</span><span class="sxs-lookup"><span data-stu-id="ff346-147">In **Object Explorer**, right-click **Databases** and click **Attach**.</span></span>  
  
5.  <span data-ttu-id="ff346-148">Na caixa de diálogo **anexar bancos** de dados, para especificar o banco de dados a ser anexado, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ff346-148">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="ff346-149">Na janela da caixa de diálogo **Localizar arquivos de banco de dados** :</span><span class="sxs-lookup"><span data-stu-id="ff346-149">In the **Locate Database Files** dialog window:</span></span>  
  
     <span data-ttu-id="ff346-150">Para local do arquivo de dados do banco de dado, digite: `https://teststorageaccnt.blob.core.windows.net/testcontainer/` .</span><span class="sxs-lookup"><span data-stu-id="ff346-150">For Database Data File Location, type: `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span>  
  
     <span data-ttu-id="ff346-151">Para nome do arquivo, digite: `TestDB1Data.mdf` .</span><span class="sxs-lookup"><span data-stu-id="ff346-151">For File name, type: `TestDB1Data.mdf`.</span></span>  
  
6.  <span data-ttu-id="ff346-152">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff346-152">Click **OK**.</span></span>  
  
     <span data-ttu-id="ff346-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="ff346-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="ff346-154">**Próxima lição:**</span><span class="sxs-lookup"><span data-stu-id="ff346-154">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="ff346-155">Lição 7: Migrar seus arquivos de dados para o Armazenamento do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="ff346-155">Lesson 7: Move your data files to Azure Storage</span></span>](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)  
  
