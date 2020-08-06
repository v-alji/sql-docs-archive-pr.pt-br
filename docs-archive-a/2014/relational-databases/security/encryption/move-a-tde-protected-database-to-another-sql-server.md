---
title: Mover um banco de dados protegido por TDE para outro SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, moving
- TDE, moving a database
ms.assetid: fb420903-df54-4016-bab6-49e6dfbdedc7
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b03b4d9ecf31e9953fd3e22cec5c51bbacc0c25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686230"
---
# <a name="move-a-tde-protected-database-to-another-sql-server"></a><span data-ttu-id="3f588-102">Mover um banco de dados protegido por TDE para outro SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f588-102">Move a TDE Protected Database to Another SQL Server</span></span>
  <span data-ttu-id="3f588-103">Este tópico descreve como proteger um banco de dados usando a TDE (Transparent Data Encryption) e, em seguida, mover o banco de dados para outra instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f588-103">This topic describes how to protect a database by using transparent data encryption (TDE), and then move the database to another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3f588-104">A TDE realiza a criptografia e a descriptografia de E/S em tempo real dos arquivos de log e de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-104">TDE performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="3f588-105">A criptografia usa uma chave de criptografia de banco de dados (DEK), que é armazenada no registro de inicialização do banco de dados para disponibilidade durante a recuperação.</span><span class="sxs-lookup"><span data-stu-id="3f588-105">The encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="3f588-106">A DEK é uma chave simétrica protegida por um certificado armazenado no banco de dados `master` do servidor ou uma chave assimétrica protegida por um módulo EKM.</span><span class="sxs-lookup"><span data-stu-id="3f588-106">The DEK is a symmetric key secured by using a certificate stored in the `master` database of the server or an asymmetric key protected by an EKM module.</span></span>  
  
 <span data-ttu-id="3f588-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="3f588-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3f588-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="3f588-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3f588-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="3f588-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3f588-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="3f588-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3f588-111">**Para criar um banco de dados protegido por criptografia de dados transparente usando:**</span><span class="sxs-lookup"><span data-stu-id="3f588-111">**To create a database protected by transparent data encryption, using:**</span></span>  
  
     [<span data-ttu-id="3f588-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f588-112">SQL Server Management Studio</span></span>](#SSMSCreate)  
  
     [<span data-ttu-id="3f588-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3f588-113">Transact-SQL</span></span>](#TsqlCreate)  
  
-   <span data-ttu-id="3f588-114">**Para mover um banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="3f588-114">**To move a database, using:**</span></span>  
  
     [<span data-ttu-id="3f588-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f588-115">SQL Server Management Studio</span></span>](#SSMSMove)  
  
     [<span data-ttu-id="3f588-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3f588-116">Transact-SQL</span></span>](#TsqlMove)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3f588-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3f588-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3f588-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="3f588-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3f588-119">Ao mover um banco de dados protegido por TDE, é necessário também mover o certificado ou a chave assimétrica que é usada para abrir a DEK.</span><span class="sxs-lookup"><span data-stu-id="3f588-119">When moving a TDE protected database, you must also move the certificate or asymmetric key that is used to open the DEK.</span></span> <span data-ttu-id="3f588-120">O certificado ou a chave assimétrica deve ser instalado no `master` banco de dados do servidor de destino, para que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o possa acessar os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-120">The certificate or asymmetric key must be installed in the `master` database of the destination server, so that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can access the database files.</span></span> <span data-ttu-id="3f588-121">Para obter mais informações, veja [TDE &#40;Transparent Data Encryption&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="3f588-121">For more information, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span>  
  
-   <span data-ttu-id="3f588-122">Você deve reter cópias do arquivo de certificado e do arquivo de chave privada para poder recuperar o certificado.</span><span class="sxs-lookup"><span data-stu-id="3f588-122">You must retain copies of both the certificate file and the private key file in order to recover the certificate.</span></span> <span data-ttu-id="3f588-123">A senha da chave privada não precisa ser igual à senha da chave mestra do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-123">The password for the private key does not have to be the same as the database master key password.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="3f588-124">armazena os arquivos criados aqui em **c:\Arquivos de PROGRAMAS\MICROSOFT SQL Server\MSSQL12. MSSQLSERVER\MSSQL\DATA** por padrão.</span><span class="sxs-lookup"><span data-stu-id="3f588-124">stores the files created here in **C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA** by default.</span></span> <span data-ttu-id="3f588-125">Os nomes e locais dos seus arquivos poderão ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="3f588-125">Your file names and locations might be different.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3f588-126">Segurança</span><span class="sxs-lookup"><span data-stu-id="3f588-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3f588-127">Permissões</span><span class="sxs-lookup"><span data-stu-id="3f588-127">Permissions</span></span>  
  
-   <span data-ttu-id="3f588-128">Requer `CONTROL DATABASE` permissão no `master` banco de dados para criar a chave mestra do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-128">Requires `CONTROL DATABASE` permission on the `master` database to create the database master key.</span></span>  
  
-   <span data-ttu-id="3f588-129">Exige a `CREATE CERTIFICATE` permissão no `master` banco de dados para criar o certificado que protege o DEK.</span><span class="sxs-lookup"><span data-stu-id="3f588-129">Requires `CREATE CERTIFICATE` permission on the `master` database to create the certificate that protects the DEK.</span></span>  
  
-   <span data-ttu-id="3f588-130">Requer a permissão `CONTROL DATABASE` no banco de dados criptografado e a permissão `VIEW DEFINITION` na chave assimétrica ou no certificado usado para criptografar a chave de criptografia do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-130">Requires `CONTROL DATABASE` permission on the encrypted database and `VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database encryption key.</span></span>  
  
##  <a name="to-create-a-database-protected-by-transparent-data-encryption"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3f588-131">Para criar um banco de dados protegido por criptografia de dados transparente</span><span class="sxs-lookup"><span data-stu-id="3f588-131">To create a database protected by transparent data encryption</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSCreate"></a> <span data-ttu-id="3f588-132">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f588-132">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="3f588-133">Crie uma chave mestra de banco de dados e um certificado no `master` banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-133">Create a database master key and certificate in the `master` database.</span></span> <span data-ttu-id="3f588-134">Para obter mais informações, veja **Usando o Transact-SQL** abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f588-134">For more information, see **Using Transact-SQL** below.</span></span>  
  
2.  <span data-ttu-id="3f588-135">Crie um backup do certificado do servidor no `master` banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-135">Create a backup of the server certificate in the `master` database.</span></span> <span data-ttu-id="3f588-136">Para obter mais informações, veja **Usando o Transact-SQL** abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f588-136">For more information, see **Using Transact-SQL** below.</span></span>  
  
3.  <span data-ttu-id="3f588-137">No Pesquisador de Objetos, clique com o botão direito do mouse na pasta **Bancos de Dados** e selecione **Novo Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="3f588-137">In Object Explorer, right-click the **Databases** folder and select **New Database**.</span></span>  
  
4.  <span data-ttu-id="3f588-138">Na caixa de diálogo **Novo Banco de Dados** , na caixa **Nome do banco de dados** , digite o nome do novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-138">In the **New Database** dialog box, in the **Database name** box, enter the name of the new database.</span></span>  
  
5.  <span data-ttu-id="3f588-139">Na caixa de diálogo **Proprietário** , digite o nome do proprietário do novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-139">In the **Owner** box, enter the name of the new database's owner.</span></span> <span data-ttu-id="3f588-140">Como alternativa, clique nas reticências **(...)** para abrir a caixa de diálogo **Selecionar Proprietário do Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="3f588-140">Alternately, click the ellipsis **(...)** to open the **Select Database Owner** dialog box.</span></span> <span data-ttu-id="3f588-141">Para obter mais informações sobre a criação de um novo banco de dados, consulte [Create a Database](../../databases/create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="3f588-141">For more information on creating a new database, see [Create a Database](../../databases/create-a-database.md).</span></span>  
  
6.  <span data-ttu-id="3f588-142">No Pesquisador de Objetos, clique no sinal de mais para expandir a pasta **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="3f588-142">In Object Explorer, click the plus sign to expand the **Databases** folder.</span></span>  
  
7.  <span data-ttu-id="3f588-143">Clique com o botão direito do mouse no banco de dados que você criou, aponte para **Tarefas**e selecione **Gerenciar Criptografia de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="3f588-143">Right-click the database you created, point to **Tasks**, and select **Manage Database Encryption**.</span></span>  
  
     <span data-ttu-id="3f588-144">As opções a seguir estão disponíveis na caixa de diálogo **Gerenciar Criptografia de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="3f588-144">The following options are available on the **Manage Database Encryption** dialog box.</span></span>  
  
     <span data-ttu-id="3f588-145">**Algoritmo de Criptografia**</span><span class="sxs-lookup"><span data-stu-id="3f588-145">**Encryption Algorithm**</span></span>  
     <span data-ttu-id="3f588-146">Exibe ou define o algoritmo para uso na criptografia de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-146">Displays or sets the algorithm to use for database encryption.</span></span> <span data-ttu-id="3f588-147">`AES128` é o algoritmo padrão.</span><span class="sxs-lookup"><span data-stu-id="3f588-147">`AES128` is the default algorithm.</span></span> <span data-ttu-id="3f588-148">Este campo não pode ficar em branco.</span><span class="sxs-lookup"><span data-stu-id="3f588-148">This field cannot be blank.</span></span> <span data-ttu-id="3f588-149">Para obter mais informações sobre algoritmos de criptografia, consulte [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="3f588-149">For more information on encryption algorithms, see [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span></span>  
  
     <span data-ttu-id="3f588-150">**Usar certificado de servidor**</span><span class="sxs-lookup"><span data-stu-id="3f588-150">**Use server certificate**</span></span>  
     <span data-ttu-id="3f588-151">Define a criptografia a ser protegida por um certificado.</span><span class="sxs-lookup"><span data-stu-id="3f588-151">Sets the encryption to be secured by a certificate.</span></span> <span data-ttu-id="3f588-152">Selecione uma opção da lista.</span><span class="sxs-lookup"><span data-stu-id="3f588-152">Select one from the list.</span></span> <span data-ttu-id="3f588-153">Se você não tiver a permissão `VIEW DEFINITION` em certificados de servidor, essa lista estará vazia.</span><span class="sxs-lookup"><span data-stu-id="3f588-153">If you do not have the `VIEW DEFINITION` permission on server certificates, this list will be empty.</span></span> <span data-ttu-id="3f588-154">Se um método de certificado de criptografia for selecionado, esse valor não poderá ficar em branco.</span><span class="sxs-lookup"><span data-stu-id="3f588-154">If a certificate method of encryption is selected, this value cannot be empty.</span></span> <span data-ttu-id="3f588-155">Para obter mais informações sobre certificados, consulte [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="3f588-155">For more information about certificates, see [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
     <span data-ttu-id="3f588-156">**Usar chave assimétrica do servidor**</span><span class="sxs-lookup"><span data-stu-id="3f588-156">**Use server asymmetric key**</span></span>  
     <span data-ttu-id="3f588-157">Define a criptografia a ser protegida por uma chave assimétrica.</span><span class="sxs-lookup"><span data-stu-id="3f588-157">Sets the encryption to be secured by an asymmetric key.</span></span> <span data-ttu-id="3f588-158">Somente as chaves assimétricas disponíveis são exibidas.</span><span class="sxs-lookup"><span data-stu-id="3f588-158">Only available asymmetric keys are displayed.</span></span> <span data-ttu-id="3f588-159">Somente uma chave assimétrica protegida por um módulo EKM pode criptografar um banco de dados que usa a TDE.</span><span class="sxs-lookup"><span data-stu-id="3f588-159">Only an asymmetric key protected by an EKM module can encrypt a database using TDE.</span></span>  
  
     <span data-ttu-id="3f588-160">**Definir criptografia de banco de dados como ativa**</span><span class="sxs-lookup"><span data-stu-id="3f588-160">**Set Database Encryption On**</span></span>  
     <span data-ttu-id="3f588-161">Altera o banco de dados para ativar (marcado) ou desativar (desmarcado) a TDE.</span><span class="sxs-lookup"><span data-stu-id="3f588-161">Alters the database to turn on (checked) or turn off (unchecked) TDE.</span></span>  
  
8.  <span data-ttu-id="3f588-162">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f588-162">When finished, click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlCreate"></a> <span data-ttu-id="3f588-163">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3f588-163">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="3f588-164">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f588-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3f588-165">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3f588-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3f588-166">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3f588-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a database master key and a certificate in the master database.  
    USE master ;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    CREATE CERTIFICATE TestSQLServerCert   
    WITH SUBJECT = 'Certificate to protect TDE key'  
    GO  
    -- Create a backup of the server certificate in the master database.  
    -- The following code stores the backup of the certificate and the private key file in the default data location for this instance of SQL Server   
    -- (C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA).  
  
    BACKUP CERTIFICATE TestSQLServerCert   
    TO FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Create a database to be protected by TDE.  
    CREATE DATABASE CustRecords ;  
    GO  
    -- Switch to the new database.  
    -- Create a database encryption key, that is protected by the server certificate in the master database.   
    -- Alter the new database to encrypt the database using TDE.  
    USE CustRecords;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM = AES_128  
    ENCRYPTION BY SERVER CERTIFICATE TestSQLServerCert;  
    GO  
    ALTER DATABASE CustRecords  
    SET ENCRYPTION ON;  
    GO  
    ```  
  
 <span data-ttu-id="3f588-167">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="3f588-167">For more information, see:</span></span>  
  
-   [<span data-ttu-id="3f588-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="3f588-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="3f588-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-certificate-transact-sql)  
  
-   [<span data-ttu-id="3f588-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="3f588-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="3f588-173">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-173">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
##  <a name="to-move-a-database"></a><a name="TsqlProcedure"></a><span data-ttu-id="3f588-174">Para mover um banco de dados</span><span class="sxs-lookup"><span data-stu-id="3f588-174">To move a database</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSMove"></a> <span data-ttu-id="3f588-175">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f588-175">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="3f588-176">No Pesquisador de Objetos, clique com o botão direito do mouse no banco de dados que você criptografou acima, aponte para **Tarefas** e selecione **Desanexar...** .</span><span class="sxs-lookup"><span data-stu-id="3f588-176">In Object Explorer, right-click the database you encrypted above, point to **Tasks** and select **Detach...**.</span></span>  
  
     <span data-ttu-id="3f588-177">As opções a seguir estão disponíveis na caixa de diálogo **Desanexar Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="3f588-177">The following options are available in the **Detach Database** dialog box.</span></span>  
  
     <span data-ttu-id="3f588-178">**Bancos de dados a serem desanexados**</span><span class="sxs-lookup"><span data-stu-id="3f588-178">**Databases to detach**</span></span>  
     <span data-ttu-id="3f588-179">Lista os bancos de dados a serem desanexados</span><span class="sxs-lookup"><span data-stu-id="3f588-179">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="3f588-180">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="3f588-180">**Database Name**</span></span>  
     <span data-ttu-id="3f588-181">Exibe o nome do banco de dados a ser desanexado.</span><span class="sxs-lookup"><span data-stu-id="3f588-181">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="3f588-182">**Cancelar Conexões**</span><span class="sxs-lookup"><span data-stu-id="3f588-182">**Drop Connections**</span></span>  
     <span data-ttu-id="3f588-183">Cancelar conexões com o banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="3f588-183">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3f588-184">Você não pode desanexar um banco de dados com conexões ativas.</span><span class="sxs-lookup"><span data-stu-id="3f588-184">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="3f588-185">**Atualização de Estatísticas**</span><span class="sxs-lookup"><span data-stu-id="3f588-185">**Update Statistics**</span></span>  
     <span data-ttu-id="3f588-186">Por padrão, a operação desanexar retém qualquer estatística de otimização desatualizada ao desanexar o banco de dados; para atualizar as estatísticas de otimização existentes, clique nesta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="3f588-186">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="3f588-187">**Manter Catálogos de Texto Completo**</span><span class="sxs-lookup"><span data-stu-id="3f588-187">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="3f588-188">Por padrão, a operação desanexar mantém qualquer catálogo de texto completo que esteja associado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-188">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="3f588-189">Para removê-los, desmarque a caixa de seleção **Manter Catálogos de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="3f588-189">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="3f588-190">Essa opção é exibida apenas quando você está atualizando um banco de dados do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f588-190">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="3f588-191">**Status**</span><span class="sxs-lookup"><span data-stu-id="3f588-191">**Status**</span></span>  
     <span data-ttu-id="3f588-192">Exibe um dos estados a seguir: **Pronto** ou **Não pronto**.</span><span class="sxs-lookup"><span data-stu-id="3f588-192">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="3f588-193">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="3f588-193">**Message**</span></span>  
     <span data-ttu-id="3f588-194">A coluna **Mensagem** pode exibir informações sobre o banco de dados, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="3f588-194">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="3f588-195">Quando um banco de dados estiver envolvido com replicação, o **Status** será **Não pronto** e a coluna **Mensagem** exibirá **Banco de Dados replicado**.</span><span class="sxs-lookup"><span data-stu-id="3f588-195">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="3f588-196">Quando um banco de dados tiver uma ou mais conexões ativas, o **Status** será **Não está pronto** e a coluna **Mensagem** exibirá _<número_de_conexões_ativas>_ **Conexão(ões) ativa(s)** – por exemplo: **1 Conexão ativa**.</span><span class="sxs-lookup"><span data-stu-id="3f588-196">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="3f588-197">Antes de desanexar o banco de dados, você deverá cancelar qualquer conexão ativa selecionando **Cancelar Conexões**.</span><span class="sxs-lookup"><span data-stu-id="3f588-197">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="3f588-198">Para obter mais informações sobre a mensagem, clique o texto com hiperlink para abrir o Monitor de atividades.</span><span class="sxs-lookup"><span data-stu-id="3f588-198">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
2.  <span data-ttu-id="3f588-199">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f588-199">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="3f588-200">Usando o Windows Explorer, mova ou copie os arquivos de banco de dados do servidor de origem para o mesmo local no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="3f588-200">Using Windows Explorer, move or copy the database files from the source server to the same location on the destination server.</span></span>  
  
4.  <span data-ttu-id="3f588-201">Usando o Windows Explorer, mova ou copie o backup do certificado do servidor e o arquivo de chave privada do servidor de origem para o mesmo local no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="3f588-201">Using Windows Explorer, move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.</span></span>  
  
5.  <span data-ttu-id="3f588-202">Crie uma chave mestra de banco de dados na instância de destino do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f588-202">Create a database master key on the destination instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3f588-203">Para obter mais informações, veja **Usando o Transact-SQL** abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f588-203">For more information, see **Using Transact-SQL** below.</span></span>  
  
6.  <span data-ttu-id="3f588-204">Recrie o certificado do servidor usando o arquivo de backup de certificado do servidor original.</span><span class="sxs-lookup"><span data-stu-id="3f588-204">Recreate the server certificate by using the original server certificate backup file.</span></span> <span data-ttu-id="3f588-205">Para obter mais informações, veja **Usando o Transact-SQL** abaixo.</span><span class="sxs-lookup"><span data-stu-id="3f588-205">For more information, see **Using Transact-SQL** below.</span></span>  
  
7.  <span data-ttu-id="3f588-206">No Pesquisador de Objetos no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse na pasta **Bancos de Dados** e selecione **Anexar...** .</span><span class="sxs-lookup"><span data-stu-id="3f588-206">In Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], right-click the **Databases** folder and select **Attach...**.</span></span>  
  
8.  <span data-ttu-id="3f588-207">Na caixa de diálogo **Anexar Bancos de Dados** , em **Bancos de dados a serem anexados**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3f588-207">In the **Attach Databases** dialog box, under **Databases to attach**, click **Add**.</span></span>  
  
9. <span data-ttu-id="3f588-208">Na caixa de diálogo **Localizar arquivos de banco de dados-**_server_name_ , selecione o arquivo de banco de dados a ser anexado ao novo servidor e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f588-208">In the **Locate Database Files -**_server_name_ dialog box, select the database file to attach to the new server and click **OK**.</span></span>  
  
     <span data-ttu-id="3f588-209">As opções a seguir estão disponíveis na caixa de diálogo **Anexar Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="3f588-209">The following options are available in the **Attach Databases** dialog box.</span></span>  
  
     <span data-ttu-id="3f588-210">**Bancos de dados a serem anexados**</span><span class="sxs-lookup"><span data-stu-id="3f588-210">**Databases to attach**</span></span>  
     <span data-ttu-id="3f588-211">Exibe informações sobre os bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="3f588-211">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="3f588-212">Exibe um ícone que indica o status da operação de anexação.</span><span class="sxs-lookup"><span data-stu-id="3f588-212">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="3f588-213">Os possíveis ícones são descritos em **Status** , abaixo).</span><span class="sxs-lookup"><span data-stu-id="3f588-213">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="3f588-214">**Local do Arquivo MDF**</span><span class="sxs-lookup"><span data-stu-id="3f588-214">**MDF File Location**</span></span>  
     <span data-ttu-id="3f588-215">Exibe o caminho e o nome de arquivo do arquivo MDF selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f588-215">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="3f588-216">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="3f588-216">**Database Name**</span></span>  
     <span data-ttu-id="3f588-217">Exibe o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-217">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="3f588-218">**Anexar como**</span><span class="sxs-lookup"><span data-stu-id="3f588-218">**Attach As**</span></span>  
     <span data-ttu-id="3f588-219">Opcionalmente, especifique um nome diferente para o banco de dados anexar como.</span><span class="sxs-lookup"><span data-stu-id="3f588-219">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="3f588-220">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="3f588-220">**Owner**</span></span>  
     <span data-ttu-id="3f588-221">Fornece uma lista suspensa de possíveis proprietários de banco de dados dos quais você pode selecionar um proprietário diferente opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="3f588-221">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="3f588-222">**Status**</span><span class="sxs-lookup"><span data-stu-id="3f588-222">**Status**</span></span>  
     <span data-ttu-id="3f588-223">Exibe o status do banco de dados de acordo com a seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="3f588-223">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="3f588-224">ícone</span><span class="sxs-lookup"><span data-stu-id="3f588-224">Icon</span></span>|<span data-ttu-id="3f588-225">Texto de status</span><span class="sxs-lookup"><span data-stu-id="3f588-225">Status text</span></span>|<span data-ttu-id="3f588-226">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f588-226">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="3f588-227">(No icon)</span><span class="sxs-lookup"><span data-stu-id="3f588-227">(No icon)</span></span>|<span data-ttu-id="3f588-228">(Nenhum texto)</span><span class="sxs-lookup"><span data-stu-id="3f588-228">(No text)</span></span>|<span data-ttu-id="3f588-229">A operação de anexação não foi iniciada ou pode estar pendente para esse objeto.</span><span class="sxs-lookup"><span data-stu-id="3f588-229">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="3f588-230">Esse é o padrão quando a caixa de diálogo é aberta.</span><span class="sxs-lookup"><span data-stu-id="3f588-230">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="3f588-231">Triângulo verde apontando para a direita</span><span class="sxs-lookup"><span data-stu-id="3f588-231">Green, right-pointing triangle</span></span>|<span data-ttu-id="3f588-232">Em andamento</span><span class="sxs-lookup"><span data-stu-id="3f588-232">In progress</span></span>|<span data-ttu-id="3f588-233">A operação de anexação foi iniciada mas não está completa.</span><span class="sxs-lookup"><span data-stu-id="3f588-233">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="3f588-234">Sinal de verificação verde</span><span class="sxs-lookup"><span data-stu-id="3f588-234">Green check mark</span></span>|<span data-ttu-id="3f588-235">Sucesso</span><span class="sxs-lookup"><span data-stu-id="3f588-235">Success</span></span>|<span data-ttu-id="3f588-236">O objeto foi anexado com êxito.</span><span class="sxs-lookup"><span data-stu-id="3f588-236">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="3f588-237">Círculo vermelho contendo uma cruz branca</span><span class="sxs-lookup"><span data-stu-id="3f588-237">Red circle containing a white cross</span></span>|<span data-ttu-id="3f588-238">Erro</span><span class="sxs-lookup"><span data-stu-id="3f588-238">Error</span></span>|<span data-ttu-id="3f588-239">A operação de anexação encontrou um erro e não foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="3f588-239">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="3f588-240">Círculo que contém dois quadrantes pretos (à esquerda e à direita) e dois quadrantes brancos (em cima e em baixo)</span><span class="sxs-lookup"><span data-stu-id="3f588-240">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="3f588-241">Parado</span><span class="sxs-lookup"><span data-stu-id="3f588-241">Stopped</span></span>|<span data-ttu-id="3f588-242">A operação de anexação não foi completada com êxito porque o usuário interrompeu a operação.</span><span class="sxs-lookup"><span data-stu-id="3f588-242">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="3f588-243">Círculo que contém uma seta curvada que aponta para o sentido anti-horário</span><span class="sxs-lookup"><span data-stu-id="3f588-243">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="3f588-244">Revertida</span><span class="sxs-lookup"><span data-stu-id="3f588-244">Rolled Back</span></span>|<span data-ttu-id="3f588-245">A operação de anexação teve êxito, mas foi revertida devido a um erro ao se anexar outro objeto.</span><span class="sxs-lookup"><span data-stu-id="3f588-245">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="3f588-246">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="3f588-246">**Message**</span></span>  
     <span data-ttu-id="3f588-247">Exibe uma mensagem em branco ou um hiperlink "Arquivo não encontrado"</span><span class="sxs-lookup"><span data-stu-id="3f588-247">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="3f588-248">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="3f588-248">**Add**</span></span>  
     <span data-ttu-id="3f588-249">Encontrar os arquivos de banco de dados principais necessários.</span><span class="sxs-lookup"><span data-stu-id="3f588-249">Find the necessary main database files.</span></span> <span data-ttu-id="3f588-250">Quando o usuário selecionar um arquivo .mdf , os respectivos campos são automaticamente preenchidos com informações aplicáveis da grade **Bancos de dados a serem anexados** .</span><span class="sxs-lookup"><span data-stu-id="3f588-250">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="3f588-251">**Remover**</span><span class="sxs-lookup"><span data-stu-id="3f588-251">**Remove**</span></span>  
     <span data-ttu-id="3f588-252">Remove o arquivo selecionado da grade **Bancos de dados a serem anexados** .</span><span class="sxs-lookup"><span data-stu-id="3f588-252">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="3f588-253">**"** _<nome_do_banco_de_dados>_ **" detalhes do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="3f588-253">**"** _<database_name>_ **" database details**</span></span>  
     <span data-ttu-id="3f588-254">Exibe os nomes dos arquivos a serem anexados.</span><span class="sxs-lookup"><span data-stu-id="3f588-254">Displays the names of the files to be attached.</span></span> <span data-ttu-id="3f588-255">Para verificar ou alterar o nome do caminho de um arquivo, clique no botão **Procurar** ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="3f588-255">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3f588-256">Se um arquivo não existir, a coluna **Mensagem** exibe "Não encontrado."</span><span class="sxs-lookup"><span data-stu-id="3f588-256">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="3f588-257">Se um arquivo de log não for encontrado, ele existe em outro diretório ou foi excluído.</span><span class="sxs-lookup"><span data-stu-id="3f588-257">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="3f588-258">Você precisa atualizar o caminho do arquivo na grade **detalhes do banco de dados** para indicar o local correto ou remover o arquivo de log da grade.</span><span class="sxs-lookup"><span data-stu-id="3f588-258">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="3f588-259">Se um arquivo de dados .ndf não for encontrado, você precisará atualizar seu caminho na grade a fim de indicar o local correto.</span><span class="sxs-lookup"><span data-stu-id="3f588-259">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="3f588-260">**Nome do arquivo original**</span><span class="sxs-lookup"><span data-stu-id="3f588-260">**Original File Name**</span></span>  
     <span data-ttu-id="3f588-261">Exibe o nome do arquivo anexado que pertence ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3f588-261">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="3f588-262">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="3f588-262">**File Type**</span></span>  
     <span data-ttu-id="3f588-263">Indica o tipo de arquivo, **Dados** ou **Log**.</span><span class="sxs-lookup"><span data-stu-id="3f588-263">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="3f588-264">**Caminho do arquivo atual**</span><span class="sxs-lookup"><span data-stu-id="3f588-264">**Current File Path**</span></span>  
     <span data-ttu-id="3f588-265">Exibe o caminho para o arquivo de banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f588-265">Displays the path to the selected database file.</span></span> <span data-ttu-id="3f588-266">O caminho pode ser editado manualmente.</span><span class="sxs-lookup"><span data-stu-id="3f588-266">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="3f588-267">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="3f588-267">**Message**</span></span>  
     <span data-ttu-id="3f588-268">Exibe uma mensagem em branco ou um hiperlink “**Arquivo não encontrado**”.</span><span class="sxs-lookup"><span data-stu-id="3f588-268">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlMove"></a> <span data-ttu-id="3f588-269">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3f588-269">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="3f588-270">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f588-270">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3f588-271">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="3f588-271">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3f588-272">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3f588-272">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Detach the TDE protected database from the source server.   
    USE master ;  
    GO  
    EXEC master.dbo.sp_detach_db @dbname = N'CustRecords';  
    GO  
    -- Move or copy the database files from the source server to the same location on the destination server.   
    -- Move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.   
    -- Create a database master key on the destination instance of SQL Server.   
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    -- Recreate the server certificate by using the original server certificate backup file.   
    -- The password must be the same as the password that was used when the backup was created.  
  
    CREATE CERTIFICATE TestSQLServerCert   
    FROM FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        DECRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Attach the database that is being moved.   
    -- The path of the database files must be the location where you have stored the database files.  
    CREATE DATABASE [CustRecords] ON   
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords.mdf' ),  
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords_log.LDF' )  
    FOR ATTACH ;  
    GO  
    ```  
  
 <span data-ttu-id="3f588-273">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="3f588-273">For more information, see:</span></span>  
  
-   [<span data-ttu-id="3f588-274">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-274">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
-   [<span data-ttu-id="3f588-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="3f588-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="3f588-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="3f588-278">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3f588-278">See Also</span></span>  
 [<span data-ttu-id="3f588-279">Anexar e desanexar bancos de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3f588-279">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../databases/database-detach-and-attach-sql-server.md)  
  
  
