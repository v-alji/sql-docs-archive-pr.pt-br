---
title: Desanexando e anexando bancos de dados do DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 830e33bc-dd15-4f8e-a4ac-d8634b78fe45
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bcac9d1f53b10cf6356b878ce4006f66c198d99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570866"
---
# <a name="detaching-and-attaching-dqs-databases"></a><span data-ttu-id="fcbc9-102">Desanexando e anexando bancos de dados do DQS</span><span class="sxs-lookup"><span data-stu-id="fcbc9-102">Detaching and Attaching DQS Databases</span></span>
  <span data-ttu-id="fcbc9-103">Este tópico descreve como desanexar e anexar os bancos de dados do DQS.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-103">This topic describes how to detach and attach the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fcbc9-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fcbc9-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="fcbc9-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="fcbc9-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="fcbc9-106">Para obter uma lista de limitações e restrições, veja [Anexar e desanexar bancos de dados &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fcbc9-106">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fcbc9-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fcbc9-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="fcbc9-108">Verifique se não há nenhuma atividade ou processo em execução no DQS.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-108">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="fcbc9-109">Isso pode ser verificado com o uso da tela **Monitoramento de atividade** .</span><span class="sxs-lookup"><span data-stu-id="fcbc9-109">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="fcbc9-110">Para obter informações detalhadas sobre como trabalhar nessa tela, consulte [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="fcbc9-110">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="fcbc9-111">Verifique se não há usuários conectados no [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcbc9-111">Ensure that there are no users logged on the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fcbc9-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcbc9-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fcbc9-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="fcbc9-113">Permissions</span></span>  
  
-   <span data-ttu-id="fcbc9-114">Sua conta de usuário do Windows deve ser um membro da função de servidor fixa db_owner na instância do SQL Server para desanexar bancos de dados DQS.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-114">Your Windows user account must be a member of the db_owner fixed server role in the SQL Server instance to detach DQS databases.</span></span>  
  
-   <span data-ttu-id="fcbc9-115">Sua conta de usuário do Windows deve ter a permissão CREATE DATABASE, CREATE ANY DATABASE ou ALTER ANY DATABASE para anexar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-115">Your Windows user account must have CREATE DATABASE, CREATE ANY DATABASE, or ALTER ANY DATABASE permission to attach a database.</span></span>  
  
-   <span data-ttu-id="fcbc9-116">Você deve ter a função dqs_administrator no banco de dados DQS_MAIN para terminar as atividades em execução ou interromper os processos em execução no DQS.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-116">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="detach-dqs-databases"></a><a name="Detach"></a><span data-ttu-id="fcbc9-117">Desanexar bancos de dados DQS</span><span class="sxs-lookup"><span data-stu-id="fcbc9-117">Detach DQS Databases</span></span>  
 <span data-ttu-id="fcbc9-118">Quando você desanexa um banco de dados DQS usando o SQL Server Management Studio, os arquivos desanexados permanecem no computador e podem ser anexados novamente à mesma instância do SQL Server ou podem ser movidos para outro servidor e anexados lá.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-118">When you detach a DQS database using SQL Server Management Studio, the detached files remain on your computer, and can be reattached to the same SQL Server instance or can be can be moved to another server and attached there.</span></span> <span data-ttu-id="fcbc9-119">Os arquivos de banco de dados do DQS normalmente estão disponíveis no seguinte local no computador do Data Quality Services: C:\Arquivos de Programas\microsoft SQL Server\MSSQL12. *<Instance_Name>* \MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-119">The DQS database files are typically available at the following location on your Data Quality Services computer: C:\Program Files\Microsoft SQL Server\MSSQL12.*<Instance_Name>* \MSSQL\DATA.</span></span>  
  
1.  <span data-ttu-id="fcbc9-120">Inicie o Microsoft SQL Server Management Studio e conecte-se à instância apropriada do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-120">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="fcbc9-121">No Pesquisador de Objetos, expanda o nó **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="fcbc9-121">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="fcbc9-122">Clique com o botão direito do mouse no banco de dados **DQS_MAIN** , aponte para **Tarefas**e clique em **Desanexar**.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-122">Right-click the **DQS_MAIN** database, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="fcbc9-123">A caixa de diálogo **Desanexar Banco de Dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-123">The **Detach Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="fcbc9-124">Marque a caixa de seleção na coluna **Descartar** e clique em **OK** para desanexar o banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-124">Select the check box under the **Drop** column, and click **OK** to detach the DQS_MAIN database.</span></span>  
  
5.  <span data-ttu-id="fcbc9-125">Repita as etapas 3 e 4 com os bancos de dados DQS_PROJECTS e DQS_STAGING_DATA para desanexá-los.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-125">Repeat steps 3 and 4 with the DQS_PROJECTS and DQS_STAGING_DATA databases to detach them.</span></span>  
  
 <span data-ttu-id="fcbc9-126">Você também pode desanexar bancos de dados DQS usando as instruções Transact-SQL usando o procedimento armazenado sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-126">You can also detach DQS databases using the Transact-SQL statements by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="fcbc9-127">Para obter mais informações sobre como desanexar bancos de dados usando instruções Transact-SQL, consulte [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) em [Detach a Database](../relational-databases/databases/detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="fcbc9-127">For more information about detaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) in [Detach a Database](../relational-databases/databases/detach-a-database.md).</span></span>  
  
##  <a name="attach-dqs-databases"></a><a name="Attach"></a><span data-ttu-id="fcbc9-128">Anexar bancos de dados DQS</span><span class="sxs-lookup"><span data-stu-id="fcbc9-128">Attach DQS Databases</span></span>  
 <span data-ttu-id="fcbc9-129">Use as instruções a seguir para anexar um banco de dados DQS na mesma instância do SQL Server (de onde você desanexou) ou a uma instância diferente do SQL Server em que o [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-129">Use the following instructions to attach a DQS database to the same SQL Server instance (from where you detached) or a different SQL Server instance where [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
1.  <span data-ttu-id="fcbc9-130">Inicie o Microsoft SQL Server Management Studio e conecte-se à instância apropriada do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-130">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="fcbc9-131">No Pesquisador de Objetos, clique com o botão direito do mouse em **Bancos de Dados**e em **Anexar**.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-131">In Object Explorer, right-click **Databases**, and then click **Attach**.</span></span> <span data-ttu-id="fcbc9-132">A caixa de diálogo **Anexar Bancos de Dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-132">The **Attach Databases** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="fcbc9-133">Para especificar o banco de dados a ser anexado, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-133">To specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="fcbc9-134">A caixa de diálogo **Localizar Arquivos de Banco de Dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-134">The **Locate Database Files** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="fcbc9-135">Selecione a unidade de disco onde o banco de dados reside e expanda a árvore do diretório para localizar e selecionar o arquivo .mdf do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-135">Select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database.</span></span> <span data-ttu-id="fcbc9-136">Por exemplo, para o banco de dados DQS_MAIN:</span><span class="sxs-lookup"><span data-stu-id="fcbc9-136">For example, for the DQS_MAIN database:</span></span>  
  
    ```  
    C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\DQS_MAIN.mdf  
    ```  
  
5.  <span data-ttu-id="fcbc9-137">O painel **detalhes do banco de dados** (inferior) exibe os nomes dos arquivos a serem anexados.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-137">The **database details** (lower) pane displays the names of the files to be attached.</span></span> <span data-ttu-id="fcbc9-138">Para verificar ou alterar o nome do caminho de um arquivo, clique no botão **Procurar** ( ... ).</span><span class="sxs-lookup"><span data-stu-id="fcbc9-138">To verify or change the pathname of a file, click the **Browse** button (...).</span></span>  
  
6.  <span data-ttu-id="fcbc9-139">Clique em **OK** para anexar o banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-139">Click **OK** to attach the DQS_MAIN database.</span></span>  
  
7.  <span data-ttu-id="fcbc9-140">Repita as etapas 2 a 6 para os bancos de dados DQS_PROJECTS e DQS_STAGING_DATA para anexá-los.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-140">Repeat steps 2-6 for the DQS_PROJECTS and DQS_STAGING_DATA databases to attach them.</span></span>  
  
8.  <span data-ttu-id="fcbc9-141">Você também deve executar as instruções Transact-SQL na próxima etapa depois de restaurar o banco de dados DQS_MAIN, caso contrário, uma mensagem de erro será exibida quando você tentar se conectar ao Data Quality Server usando o aplicativo Cliente Data Quality, e você não puder se conectar.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-141">You must also run the Transact-SQL statements in the next step after restoring the DQS_MAIN database otherwise an error message is displayed when you try to connect to Data Quality Server by using the Data Quality Client application, and you cannot connect.</span></span> <span data-ttu-id="fcbc9-142">Porém, você não precisa executar as etapas 9 e 10 se tiver acabado de anexar o banco de dados DQS_PROJECTS ou DQS_STAGING_DATA e não o DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-142">However, you do not need to perform steps 9 and 10 if you have just attached the DQS_PROJECTS or DQS_STAGING_DATA database, and not DQS_MAIN.</span></span>  
  
     <span data-ttu-id="fcbc9-143">Para executar as instruções Transact-SQL, no Pesquisador de Objetos, clique com o botão direito do mouse no servidor e clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-143">To run the Transact-SQL statements, in Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
9. <span data-ttu-id="fcbc9-144">Na janela Editor de Consultas, copie as seguintes instruções SQL:</span><span class="sxs-lookup"><span data-stu-id="fcbc9-144">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    ALTER DATABASE [DQS_MAIN] SET TRUSTWORTHY ON;  
    EXEC sp_configure 'clr enabled', 1;  
    RECONFIGURE WITH OVERRIDE  
    ALTER DATABASE [DQS_MAIN] SET ENABLE_BROKER  
    ALTER AUTHORIZATION ON DATABASE::[DQS_MAIN] TO [##MS_dqs_db_owner_login##]  
    ALTER AUTHORIZATION ON DATABASE::[DQS_PROJECTS] TO [##MS_dqs_db_owner_login##]  
    ```  
  
10. <span data-ttu-id="fcbc9-145">Pressione F5 para executar as instruções.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-145">Press F5 to execute the statements.</span></span> <span data-ttu-id="fcbc9-146">Consulte o painel Resultados para verificar se as instruções foram executadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-146">Check the Results pane to verify that the statements have executed successfully.</span></span> <span data-ttu-id="fcbc9-147">Você verá a seguinte mensagem: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span><span class="sxs-lookup"><span data-stu-id="fcbc9-147">You will see the following message: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span></span>  
  
11. <span data-ttu-id="fcbc9-148">Conecte-se ao Data Quality Server usando o Cliente Data Quality para verificar se é possível conectar-se com êxito.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-148">Connect to the Data Quality Server using the Data Quality Client to verify if you can connect successfully.</span></span>  
  
 <span data-ttu-id="fcbc9-149">Você também pode anexar bancos de dados DQS usando as instruções Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="fcbc9-149">You can also attach DQS databases using the Transact-SQL statements.</span></span> <span data-ttu-id="fcbc9-150">Para obter mais informações sobre como anexar bancos de dados usando instruções Transact-SQL, consulte [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) em [Attach a Database](../relational-databases/databases/attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="fcbc9-150">For more information about attaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) in [Attach a Database](../relational-databases/databases/attach-a-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcbc9-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fcbc9-151">See Also</span></span>  
 [<span data-ttu-id="fcbc9-152">Gerenciar bancos de dados do DQS</span><span class="sxs-lookup"><span data-stu-id="fcbc9-152">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
