---
title: 'Lição 4: criar um banco de dados no armazenamento do Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9ae1501-b614-49d3-b975-6569da8350b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50fca85111d5897b738e577e7735049e0b055a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583031"
---
# <a name="lesson-4-create-a-database-in-azure-storage"></a><span data-ttu-id="d78b0-102">Lição 4: Criar um banco de dados no Armazenamento do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="d78b0-102">Lesson 4: Create a database in Azure Storage</span></span>
  <span data-ttu-id="d78b0-103">Nesta lição, você aprenderá a criar um banco de dados usando o recurso arquivos de SQL Server Data no Azure.</span><span class="sxs-lookup"><span data-stu-id="d78b0-103">In this lesson, you will learn how to create a database using the SQL Server Data Files in Azure feature.</span></span> <span data-ttu-id="d78b0-104">Observe que antes desta lição, você deverá concluir as lições 1, 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="d78b0-104">Note that before this lesson, you must complete the Lesson 1, 2, and 3.</span></span> <span data-ttu-id="d78b0-105">A lição 3 é uma etapa muito importante, pois você precisa armazenar as informações sobre seu contêiner de armazenamento do Azure e seu nome de política associado e a chave SAS no repositório de credenciais de SQL Server antes da lição 4.</span><span class="sxs-lookup"><span data-stu-id="d78b0-105">Lesson 3 is a very important step because you need to store the information about your Azure storage container and its associated policy name and SAS key in the SQL Server credential store before Lesson 4.</span></span>  
  
 <span data-ttu-id="d78b0-106">Para cada contêiner de armazenamento usado por um arquivo de dados ou de log, você deve criar uma Credencial do SQL Server cujo nome corresponda ao caminho do contêiner.</span><span class="sxs-lookup"><span data-stu-id="d78b0-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span> <span data-ttu-id="d78b0-107">Em seguida, você pode criar um novo banco de dados no armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="d78b0-107">Then, you can create a new database in Azure Storage</span></span>  
  
 <span data-ttu-id="d78b0-108">Esta lição supõe que você já concluiu as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d78b0-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="d78b0-109">Você tem uma conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="d78b0-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="d78b0-110">Você criou um contêiner em sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="d78b0-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="d78b0-111">Você criou uma política em um contêiner com direitos de leitura, gravação e lista.</span><span class="sxs-lookup"><span data-stu-id="d78b0-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="d78b0-112">Você também gerou uma chave de SAS.</span><span class="sxs-lookup"><span data-stu-id="d78b0-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="d78b0-113">Você criou uma credencial do SQL Server no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="d78b0-113">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="d78b0-114">Para criar um banco de dados no Azure usando os arquivos de SQL Server Data no recurso de armazenamento do Azure, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d78b0-114">To create a database in Azure using the SQL Server Data Files in Azure Storage feature, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d78b0-115">Conecte-se ao SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d78b0-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="d78b0-116">No Pesquisador de Objetos, conecte-se à instância do Mecanismo de Banco de Dados instalado.</span><span class="sxs-lookup"><span data-stu-id="d78b0-116">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="d78b0-117">Na barra de ferramentas Padrão, clique em Nova Consulta.</span><span class="sxs-lookup"><span data-stu-id="d78b0-117">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="d78b0-118">Copie e cole o exemplo a seguir na janela de consulta, e modifique conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d78b0-118">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="d78b0-119">Observe que o campo FILENAME faz referência ao caminho do URI do arquivo de banco de dados no contêiner de armazenamento e deve iniciar com https.</span><span class="sxs-lookup"><span data-stu-id="d78b0-119">Note that the FILENAME field refers to the URI path of the database file in storage container and it must start with https.</span></span>  
  
    ```  
  
    --Create a database that uses a SQL Server credential    
    CREATE DATABASE TestDB1    
    ON   
    (NAME = TestDB1_data,   
       FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf')   
     LOG ON   
    (NAME = TestDB1_log,   
        FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
    GO  
  
    ```  
  
     <span data-ttu-id="d78b0-120">Adicione alguns dados ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d78b0-120">Add some data to your database.</span></span>  
  
    ```  
  
    USE TestDB1;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
5.  <span data-ttu-id="d78b0-121">Para ver o novo TestDB1 no SQL Server local, atualize os bancos de dados no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="d78b0-121">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span>  
  
6.  <span data-ttu-id="d78b0-122">Da mesma forma, para ver o banco de dados recém-criado na conta de armazenamento, conecte-se à conta de armazenamento através do SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="d78b0-122">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="d78b0-123">Para obter informações sobre como se conectar a um armazenamento do Azure usando SQL Server Management Studio, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d78b0-123">For information on how to connect to an Azure storage using SQL Server Management Studio, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="d78b0-124">Primeiro, obtenha as informações da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="d78b0-124">First, get the storage account information.</span></span> <span data-ttu-id="d78b0-125">Faça logon no Portal de Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="d78b0-125">Log in to the Management Portal.</span></span> <span data-ttu-id="d78b0-126">Em seguida, clique em **armazenamento** e escolha sua conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="d78b0-126">Then, click **Storage** and choose your storage account.</span></span> <span data-ttu-id="d78b0-127">Quando uma conta de armazenamento estiver selecionada, clique em **gerenciar chaves de acesso** na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="d78b0-127">When a storage account is selected, click **Manage Access Keys** at the bottom of the page.</span></span> <span data-ttu-id="d78b0-128">Isso abre uma janela de caixa de diálogo similar:</span><span class="sxs-lookup"><span data-stu-id="d78b0-128">This opens a similar dialog window:</span></span>  
  
         <span data-ttu-id="d78b0-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="d78b0-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span></span>  
  
    2.  <span data-ttu-id="d78b0-130">Copie o **nome da conta de armazenamento** e os valores de **chave de acesso primário** para a janela de diálogo **conectar ao armazenamento do Azure** no SSMS.</span><span class="sxs-lookup"><span data-stu-id="d78b0-130">Copy the **Storage Account Name** and **Primary Access Key** values to the **Connect to Azure Storage** dialog window in SSMS.</span></span> <span data-ttu-id="d78b0-131">Em seguida, clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="d78b0-131">Then, click **Connect**.</span></span> <span data-ttu-id="d78b0-132">Isso colocará as informações sobre contêineres da conta de armazenamento no SSMS, conforme mostrado na seguinte captura de tela:</span><span class="sxs-lookup"><span data-stu-id="d78b0-132">This brings the information about storage account containers to SSMS as shown in the following screenshot:</span></span>  
  
         <span data-ttu-id="d78b0-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="d78b0-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="d78b0-134">A captura de tela a seguir demonstra o novo banco de dados criado no ambiente local e do armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="d78b0-134">The following screenshot demonstrates the new created database both in on-premises and Azure Storage environment.</span></span>  
  
 <span data-ttu-id="d78b0-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="d78b0-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="d78b0-136">**Observação:** Se houver quaisquer referências ativas a arquivos de dados em um contêiner, qualquer tentativa de excluir a credencial SQL Server associada falhará.</span><span class="sxs-lookup"><span data-stu-id="d78b0-136">**Note:** If there are any active references to data files in a container, any attempts to delete the associated SQL Server credential fails.</span></span> <span data-ttu-id="d78b0-137">Da mesma forma, se já houver uma concessão em um arquivo de banco de dados específico em um blob e você quiser excluí-lo, primeiro você precisa interromper a concessão no blob.</span><span class="sxs-lookup"><span data-stu-id="d78b0-137">Similarly, if there is already a lease on a specific database file in a blob and you want to delete it, first you need to break the lease on the blob.</span></span> <span data-ttu-id="d78b0-138">Para interromper a concessão, você pode usar o [blob de concessão](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span><span class="sxs-lookup"><span data-stu-id="d78b0-138">To break the lease, you can use [Lease Blob](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span></span>  
  
 <span data-ttu-id="d78b0-139">Usando esse novo recurso, você pode configurar o SQL Server de modo que qualquer instrução CREATE DATABASE assuma como padrão um banco de dados habilitado para nuvem.</span><span class="sxs-lookup"><span data-stu-id="d78b0-139">Using this new feature, you can configure SQL Server so that any CREATE DATABASE statement will default to a cloud enabled database.</span></span> <span data-ttu-id="d78b0-140">Em outras palavras, você pode definir locais de dados e de log padrão em SQL Server Management Studio Propriedades da instância do servidor, de modo que sempre que você criar um banco de dado, todos os arquivos de banco (. MDF,. ldf) sejam criados como BLOBs de páginas no armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="d78b0-140">In other words, you can set default data and log locations in SQL Server Management Studio Server instance properties so anytime you create a database, all database files (.mdf, .ldf) are created as page blobs in Azure Storage.</span></span>  
  
 <span data-ttu-id="d78b0-141">Para criar um banco de dados no armazenamento do Azure usando SQL Server Management Studio interface do usuário, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d78b0-141">To create a database in Azure Storage by using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="d78b0-142">No Pesquisador de Objetos, conecte-se a uma instância do Mecanismo de Banco de Dados do SQL Server e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="d78b0-142">In Object Explorer, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d78b0-143">Clique com o botão direito do mouse em Bancos de Dados e clique em Novo Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="d78b0-143">Right-click Databases, and then click New Database.</span></span>  
  
3.  <span data-ttu-id="d78b0-144">Na janela da caixa de diálogo Novo Banco de Dados, digite um nome de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d78b0-144">In the New Database dialog window, type a database name.</span></span>  
  
4.  <span data-ttu-id="d78b0-145">Altere os valores padrão dos arquivos de dados primários e de log de transações, na grade de arquivos de banco de dados, clique na célula apropriada e digite o novo valor.</span><span class="sxs-lookup"><span data-stu-id="d78b0-145">Change the default values of the primary data and transaction log files, in the Database files grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="d78b0-146">Além disso, especifique o caminho para o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d78b0-146">Also, specify the path for the file location.</span></span> <span data-ttu-id="d78b0-147">Em Caminho, digite o caminho da URL do contêiner de armazenamento, como `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span><span class="sxs-lookup"><span data-stu-id="d78b0-147">For Path, type the URL path of the storage container, such as `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span> <span data-ttu-id="d78b0-148">Em Nome do Arquivo, digite os nomes de arquivo físicos dos arquivos de banco de dados (.mdf, .ldf).</span><span class="sxs-lookup"><span data-stu-id="d78b0-148">For FileName, type the physical file names of the database files (.mdf, .ldf).</span></span>  
  
     <span data-ttu-id="d78b0-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="d78b0-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span></span>  
  
     <span data-ttu-id="d78b0-150">Para obter mais informações, consulte [adicionar dados ou arquivos de Log para um banco de dados](databases/add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="d78b0-150">For more information, see [Add Data or Log Files to a Database](databases/add-data-or-log-files-to-a-database.md).</span></span>  
  
5.  <span data-ttu-id="d78b0-151">Mantenha todos os outros valores padrão.</span><span class="sxs-lookup"><span data-stu-id="d78b0-151">Keep all other default values.</span></span>  
  
6.  <span data-ttu-id="d78b0-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d78b0-152">Click OK.</span></span>  
  
 <span data-ttu-id="d78b0-153">Para ver o novo TestDB1 no SQL Server local, atualize os bancos de dados no Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="d78b0-153">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span> <span data-ttu-id="d78b0-154">Da mesma forma, para ver o banco de dados recém-criado na conta de armazenamento, conecte-se à conta de armazenamento através do SQL Server Management Studio (SSMS), conforme explicado anteriormente nessa lição.</span><span class="sxs-lookup"><span data-stu-id="d78b0-154">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS) as explained earlier in this lesson.</span></span>  
  
 <span data-ttu-id="d78b0-155">**Próxima lição:**</span><span class="sxs-lookup"><span data-stu-id="d78b0-155">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="d78b0-156">Lição 5. &#40;opcional&#41; criptografar seu banco de dados usando TDE</span><span class="sxs-lookup"><span data-stu-id="d78b0-156">Lesson 5. &#40;Optional&#41; Encrypt your database using TDE</span></span>](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)  
  
  
