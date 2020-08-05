---
title: Criar o catálogo do SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6ed56d36-18d9-40c2-b51f-f2a4c71d1e73
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2572cc131f34a21171054a159e3b7968c453a780
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570787"
---
# <a name="create-the-ssis-catalog"></a><span data-ttu-id="fd041-102">Criar o catálogo do SSIS</span><span class="sxs-lookup"><span data-stu-id="fd041-102">Create the SSIS Catalog</span></span>
  <span data-ttu-id="fd041-103">Depois de criar e testar pacotes no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], você pode implantar os projetos que contêm os pacotes em um servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd041-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="fd041-104">Para poder implantar os projetos no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], o servidor deve conter o catálogo do `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="fd041-104">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the server must contain the `SSISDB` catalog.</span></span> <span data-ttu-id="fd041-105">O programa de instalação do [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] não cria o catálogo automaticamente; você precisará criar o catálogo manualmente por meio das instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd041-105">The installation program for [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] does not automatically create the catalog; you need to manually create the catalog by using the following instructions.</span></span>  
  
 <span data-ttu-id="fd041-106">Você pode criar o catálogo do SSISDB no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd041-106">You can create the SSISDB catalog in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="fd041-107">Você também pode criar o catálogo programaticamente usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd041-107">You also create the catalog programmatically by using Windows PowerShell.</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-in-sql-server-management-studio"></a><span data-ttu-id="fd041-108">Para criar o catálogo SSISDB no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fd041-108">To create the SSISDB catalog in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="fd041-109">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd041-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="fd041-110">Conecte-se ao Mecanismo de Banco de Dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd041-110">Connect to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Database Engine.</span></span>  
  
3.  <span data-ttu-id="fd041-111">No Pesquisador de Objetos, expanda o nó de servidor, clique com o botão direito do mouse no nó **Catálogos do Integration Services** e clique em **Criar Catálogo**.</span><span class="sxs-lookup"><span data-stu-id="fd041-111">In Object Explorer, expand the server node, right-click the **Integration Services Catalogs** node, and then click **Create Catalog**.</span></span>  
  
4.  <span data-ttu-id="fd041-112">Clique em **Habilitar Integração CLR**.</span><span class="sxs-lookup"><span data-stu-id="fd041-112">Click **Enable CLR Integration**.</span></span>  
  
     <span data-ttu-id="fd041-113">Esse catálogo usa procedimentos armazenados CLR.</span><span class="sxs-lookup"><span data-stu-id="fd041-113">The catalog uses CLR stored procedures.</span></span>  
  
5.  <span data-ttu-id="fd041-114">Clique em **Habilitar a execução automática de procedimento armazenado do Integration Services na inicialização do SQL Server** para habilitar o procedimento armazenado [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) a ser executado toda vez que a instância do servidor [!INCLUDE[ssIS](../includes/ssis-md.md)] for reiniciada.</span><span class="sxs-lookup"><span data-stu-id="fd041-114">Click **Enable automatic execution of Integration Services stored procedure at SQL Server startup** to enable the [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) stored procedure to run each time the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance is restarted.</span></span>  
  
     <span data-ttu-id="fd041-115">O procedimento armazenado executa a manutenção do estado das operações para o catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="fd041-115">The stored procedure performs maintenance of the state of operations for the SSISDB catalog.</span></span> <span data-ttu-id="fd041-116">Ele corrigirá o status de todos os pacotes que estavam sendo executados se e quando a instância do servidor [!INCLUDE[ssIS](../includes/ssis-md.md)] ficar inoperante.</span><span class="sxs-lookup"><span data-stu-id="fd041-116">It fixes the status of any packages there were running if and when the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance goes down.</span></span>  
  
6.  <span data-ttu-id="fd041-117">Digite uma senha e clique em **Ok**.</span><span class="sxs-lookup"><span data-stu-id="fd041-117">Enter a password, and then click **Ok**.</span></span>  
  
     <span data-ttu-id="fd041-118">A senha protege a chave mestra do banco de dados que é usada para criptografar os dados do catálogo.</span><span class="sxs-lookup"><span data-stu-id="fd041-118">The password protects the database master key that is used for encrypting the catalog data.</span></span> <span data-ttu-id="fd041-119">Salve a senha em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="fd041-119">Save the password in a secure location.</span></span> <span data-ttu-id="fd041-120">É recomendado que você também faça backup da chave mestra do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fd041-120">It is recommended that you also back up the database master key.</span></span> <span data-ttu-id="fd041-121">Para obter mais informações, consulte [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="fd041-121">For more information, see [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-programmatically"></a><span data-ttu-id="fd041-122">Para criar o catálogo do SSISDB programaticamente</span><span class="sxs-lookup"><span data-stu-id="fd041-122">To create the SSISDB catalog programmatically</span></span>  
  
1.  <span data-ttu-id="fd041-123">Execute o seguinte script do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fd041-123">Execute the following PowerShell script:</span></span>  
  
    ```powershell
    # Load the IntegrationServices Assembly  
    [Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Management.IntegrationServices")  
  
    # Store the IntegrationServices Assembly namespace to avoid typing it every time  
    $ISNamespace = "Microsoft.SqlServer.Management.IntegrationServices"  
  
    Write-Host "Connecting to server ..."  
  
    # Create a connection to the server  
    $sqlConnectionString = "Data Source=localhost;Initial Catalog=master;Integrated Security=SSPI;"  
    $sqlConnection = New-Object System.Data.SqlClient.SqlConnection $sqlConnectionString  
  
    # Create the Integration Services object  
    $integrationServices = New-Object $ISNamespace".IntegrationServices" $sqlConnection  
  
    # Provision a new SSIS Catalog  
    $catalog = New-Object $ISNamespace".Catalog" ($integrationServices, "SSISDB", "P@assword1")  
    $catalog.Create()
    ```  
  
     <span data-ttu-id="fd041-124">Para obter mais exemplos de como usar o Windows PowerShell e o namespace <xref:Microsoft.SqlServer.Management.IntegrationServices>, confira a entrada de blog [SSIS e o PowerShell no SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539) em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="fd041-124">For more examples of how to use Windows PowerShell and the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace, see the blog entry, [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539), on blogs.msdn.com.</span></span> <span data-ttu-id="fd041-125">Para obter uma visão geral do namespace e dos exemplos de códigos, consulte a entrada do blog [Prévia do modelo do objeto gerenciado do catálogo do SSIS](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892)em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="fd041-125">For an overview of the namespace and code examples, see the blog entry, [A Glimpse of the SSIS Catalog Managed Object Model](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd041-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd041-126">See Also</span></span>  
 <span data-ttu-id="fd041-127">[Catálogo do SSIS](catalog/ssis-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="fd041-127">[SSIS Catalog](catalog/ssis-catalog.md) </span></span>  
 [<span data-ttu-id="fd041-128">Fazer backup, restaurar e mover o catálogo do SSIS</span><span class="sxs-lookup"><span data-stu-id="fd041-128">Backup, Restore, and Move the SSIS Catalog</span></span>](../../2014/integration-services/backup-restore-and-move-the-ssis-catalog.md)  
