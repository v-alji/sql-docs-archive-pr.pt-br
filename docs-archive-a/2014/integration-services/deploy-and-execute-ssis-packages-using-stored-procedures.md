---
title: Implantar e executar pacotes SSIS usando procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 60914b0c-1f65-45f8-8132-0ca331749fcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1570207dca6e944b54c553a1d83256d8f4fa3244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684809"
---
# <a name="deploy-and-execute-ssis-packages-using-stored-procedures"></a><span data-ttu-id="ff914-102">Implantar e executar pacotes SSIS usando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ff914-102">Deploy and Execute SSIS Packages using Stored Procedures</span></span>
  <span data-ttu-id="ff914-103">Quando configura um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para usar o modelo de implantação de projeto, você pode usar procedimentos armazenados no catálogo do [!INCLUDE[ssIS](../includes/ssis-md.md)] para implantar o projeto e executar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="ff914-103">When you configure an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to use the project deployment model, you can use stored procedures in the [!INCLUDE[ssIS](../includes/ssis-md.md)] catalog to deploy the project and execute the packages.</span></span> <span data-ttu-id="ff914-104">Para obter informações sobre o modelo de implantação de projeto, consulte [Implantação de projetos e pacotes](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="ff914-104">For information about the project deployment model, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="ff914-105">Você também pode usar o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para implantar o projeto e executar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="ff914-105">You can also use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to deploy the project and execute the packages.</span></span> <span data-ttu-id="ff914-106">Para obter mais informações, consulte os tópicos na seção **Consulte também** .</span><span class="sxs-lookup"><span data-stu-id="ff914-106">For more information, see the topics in the **See Also** section.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="ff914-107">Você pode facilmente gerar as instruções Transact-SQL para os procedimentos armazenados listados no procedimento abaixo, com exceção de catalog.deploy_project, fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ff914-107">You can easily generate the Transact-SQL statements for the stored procedures listed in the procedure below, with the exception of catalog.deploy_project, by doing the following:</span></span>  
> 
>  1.  <span data-ttu-id="ff914-108">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expanda o nó **Catálogos do Integration Services** no Pesquisador de Objetos e navegue até o pacote que deseja executar.</span><span class="sxs-lookup"><span data-stu-id="ff914-108">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** node in Object Explorer and navigate to the package you want to execute.</span></span>  
> 2.  <span data-ttu-id="ff914-109">Clique com o botão direito do mouse no pacote e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ff914-109">Right-click the package, and then click **Execute**.</span></span>  
> 3.  <span data-ttu-id="ff914-110">Conforme necessário, defina valores de parâmetros, propriedades do gerenciador de conexões e opções na guia **Avançado** , como nível de log.</span><span class="sxs-lookup"><span data-stu-id="ff914-110">As needed, set parameters values, connection manager properties, and options in the **Advanced** tab such as the logging level.</span></span>  
> 
>      <span data-ttu-id="ff914-111">Para obter mais informações sobre os níveis de log, veja [Habilitar o log para a execução do pacote no servidor SSIS](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span><span class="sxs-lookup"><span data-stu-id="ff914-111">For more information about logging levels, see [Enable Logging for Package Execution on the SSIS Server](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span></span>  
> 4.  <span data-ttu-id="ff914-112">Antes de clicar em **OK** para executar o pacote, clique em **Script**.</span><span class="sxs-lookup"><span data-stu-id="ff914-112">Before clicking **OK** to execute the package, click **Script**.</span></span> <span data-ttu-id="ff914-113">O Transact-SQL é exibido em uma janela do Editor de Consultas no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff914-113">The Transact-SQL appears in a Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="to-deploy-and-execute-a-package-using-stored-procedures"></a><span data-ttu-id="ff914-114">Para implantar e executar um pacote usando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ff914-114">To deploy and execute a package using stored procedures</span></span>  
  
1.  <span data-ttu-id="ff914-115">Chame [catalog.deploy_project &#40;Banco de Dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) para implantar o projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote para o servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff914-115">Call [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) to deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="ff914-116">Para recuperar o conteúdo binário do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] arquivo de implantação do projeto, para o parâmetro \* \@ project_stream\* , use uma instrução SELECT com a função OPENROWSET e o provedor de conjunto de linhas em massa.</span><span class="sxs-lookup"><span data-stu-id="ff914-116">To retrieve the binary contents of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project deployment file, for the *\@project_stream* parameter, use a SELECT statement with the OPENROWSET function and the BULK rowset provider.</span></span> <span data-ttu-id="ff914-117">O conjuntos de linhas BULK permite a você ler dados de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="ff914-117">The BULK rowset provider enables you to read data from a file.</span></span> <span data-ttu-id="ff914-118">O argumento SINGLE_BLOB do provedor de conjuntos de linhas BULK retorna o conteúdo do arquivo de dados como uma única linha, um conjunto de linhas de coluna única do tipo varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="ff914-118">The SINGLE_BLOB argument for the BULK rowset provider returns the contents of the data file as a single-row, single-column rowset of type varbinary(max).</span></span> <span data-ttu-id="ff914-119">Para obter mais informações, consulte [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ff914-119">For more information, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
     <span data-ttu-id="ff914-120">No exemplo a seguir, o projeto SSISPackages_ProjectDeployment é implantado na pasta Pacotes SSIS no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff914-120">In the following example, the SSISPackages_ProjectDeployment project is deployed to the SSIS Packages folder on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="ff914-121">Os dados binários são lidos do arquivo de projeto (SSISPackage_ProjectDeployment. ispac) e armazenados no parâmetro \* \@ ProjectBinary\* do tipo varbinary (max).</span><span class="sxs-lookup"><span data-stu-id="ff914-121">The binary data is read from the project file (SSISPackage_ProjectDeployment.ispac) and is stored in the *\@ProjectBinary* parameter of type varbinary(max).</span></span> <span data-ttu-id="ff914-122">O valor do parâmetro \* \@ ProjectBinary\* é atribuído ao parâmetro \* \@ project_stream\* .</span><span class="sxs-lookup"><span data-stu-id="ff914-122">The *\@ProjectBinary* parameter value is assigned to the *\@project_stream* parameter.</span></span>  
  
    ```  
    DECLARE @ProjectBinary as varbinary(max)  
    DECLARE @operation_id as bigint  
    Set @ProjectBinary = (SELECT * FROM OPENROWSET(BULK 'C:\MyProjects\ SSISPackage_ProjectDeployment.ispac', SINGLE_BLOB) as BinaryData)  
  
    Exec catalog.deploy_project @folder_name = 'SSIS Packages', @project_name = 'DeployViaStoredProc_SSIS', @Project_Stream = @ProjectBinary, @operation_id = @operation_id out  
  
    ```  
  
2.  <span data-ttu-id="ff914-123">Chame [catalog.create_execution &amp;#40;Banco de Dados SSISDB&amp;#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) para criar uma instância da execução do pacote e, opcionalmente, chame [catalog.set_execution_parameter_value &amp;#40;Banco de Dados SSISDB&amp;#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) Para definir valores de parâmetro de runtime.</span><span class="sxs-lookup"><span data-stu-id="ff914-123">Call [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) to create an instance of the package execution, and optionally call [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) to set runtime parameter values.</span></span>  
  
     <span data-ttu-id="ff914-124">No exemplo a seguir, catalog.create_execution cria uma instância de execução para package.dtsx que está contida no projeto SSISPackage_ProjectDeployment.</span><span class="sxs-lookup"><span data-stu-id="ff914-124">In the following example, catalog.create_execution creates an instance of execution for package.dtsx that is contained in the SSISPackage_ProjectDeployment project.</span></span> <span data-ttu-id="ff914-125">O projeto está localizado na pasta Pacotes SSIS.</span><span class="sxs-lookup"><span data-stu-id="ff914-125">The project is located in the SSIS Packages folder.</span></span> <span data-ttu-id="ff914-126">A execution_id retornada pelo procedimento armazenado é usado na chamada para catalog.set_execution_parameter_value.</span><span class="sxs-lookup"><span data-stu-id="ff914-126">The execution_id returned by the stored procedure is used in the call to catalog.set_execution_parameter_value.</span></span> <span data-ttu-id="ff914-127">Esse segundo procedimento armazenado define o parâmetro LOGGING_LEVEL como 3 (log detalhado) e define um parâmetro de pacote denominado Parameter1 com um valor de 1.</span><span class="sxs-lookup"><span data-stu-id="ff914-127">This second stored procedure sets the LOGGING_LEVEL parameter to 3 (verbose logging) and sets a package parameter named Parameter1 to a value of 1.</span></span>  
  
     <span data-ttu-id="ff914-128">Para parâmetros como LOGGING_LEVEL, o valor de object_type é 50.</span><span class="sxs-lookup"><span data-stu-id="ff914-128">For parameters such as LOGGING_LEVEL the object_type value is 50.</span></span> <span data-ttu-id="ff914-129">Para parâmetros de pacote, o valor de object_type é 30.</span><span class="sxs-lookup"><span data-stu-id="ff914-129">For package parameters the object_type value is 30.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    GO  
  
    ```  
  
3.  <span data-ttu-id="ff914-130">Chame [catalog.start_execution &#40;Banco de Dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="ff914-130">Call [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) to execute the package.</span></span>  
  
     <span data-ttu-id="ff914-131">No exemplo a seguir, uma chamada a catalog.start_execution é adicionada ao Transact-SQL para iniciar a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="ff914-131">In the following example, a call to catalog.start_execution is added to the Transact-SQL to start the package execution.</span></span> <span data-ttu-id="ff914-132">A execution_id retornada pelo procedimento armazenado catalog.create_execution é usada.</span><span class="sxs-lookup"><span data-stu-id="ff914-132">The execution_id returned by the catalog.create_execution stored procedure is used.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    EXEC [SSISDB].[catalog].[start_execution] @execution_id  
    GO  
  
    ```  
  
## <a name="to-deploy-a-project-from-server-to-server-using-stored-procedures"></a><span data-ttu-id="ff914-133">Para implantar um projeto de servidor para servidor usando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ff914-133">To deploy a project from server to server using stored procedures</span></span>  
 <span data-ttu-id="ff914-134">Você pode implantar um projeto de servidor para servidor usando os procedimentos armazenados [catalog.get_project &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) e [catalog.deploy_project &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="ff914-134">You can deploy a project from server to server by using the [catalog.get_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) and [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) stored procedures.</span></span>  
  
 <span data-ttu-id="ff914-135">Você precisa fazer o seguinte antes de executar os procedimentos armazenados:</span><span class="sxs-lookup"><span data-stu-id="ff914-135">You need to do the following before running the stored procedures.</span></span>  
  
-   <span data-ttu-id="ff914-136">Crie um objeto de servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="ff914-136">Create a linked server object.</span></span> <span data-ttu-id="ff914-137">Para obter mais informações, consulte [Criar servidores vinculados &#40;Mecanismo de Banco de Dados do SQL Server&#41;](../database-engine/sql-server-database-engine-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ff914-137">For more information, see [Create Linked Servers &#40;SQL Server Database Engine&#41;](../database-engine/sql-server-database-engine-overview.md).</span></span>  
  
     <span data-ttu-id="ff914-138">Na página **Opções do Servidor** da caixa de diálogo **Propriedades do Servidor Vinculado** , defina **RPC** e **RPC Out** como **True**.</span><span class="sxs-lookup"><span data-stu-id="ff914-138">On the **Server Options** page of the **Linked Server Properties** dialog box, set **RPC** and **RPC Out** to **True**.</span></span> <span data-ttu-id="ff914-139">Além disso, defina **Habilitar Promoção de Transações Distribuídas para RPC** como **False**.</span><span class="sxs-lookup"><span data-stu-id="ff914-139">Also, set **Enable Promotion of Distributed Transactions for RPC** to **False**.</span></span>  
  
-   <span data-ttu-id="ff914-140">Habilite parâmetros dinâmicos para o provedor selecionado para o servidor vinculado expandindo o nó **Provedores** sob **Servidores Vinculados** no Pesquisador de Objetos, clicando com o botão direito do mouse no provedor e clicando em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ff914-140">Enable dynamic parameters for the provider you selected for the linked server, by expanding the **Providers** node under **Linked Servers** in Object Explorer, right-clicking the provider, and then clicking **Properties**.</span></span> <span data-ttu-id="ff914-141">Selecione **Habilitar** ao lado de **Parâmetro dinâmico**.</span><span class="sxs-lookup"><span data-stu-id="ff914-141">Select **Enable** next to **Dynamic parameter.**</span></span>  
  
-   <span data-ttu-id="ff914-142">Confirme se o DTC (Distributed Transaction Coordinator) foi iniciado em ambos os servidores.</span><span class="sxs-lookup"><span data-stu-id="ff914-142">Confirm that the Distributed Transaction Coordinator (DTC) is started on both servers.</span></span>  
  
 <span data-ttu-id="ff914-143">Chame catalog.get_project para retornar o binário do projeto e chame catalog.deploy_project.</span><span class="sxs-lookup"><span data-stu-id="ff914-143">Call catalog.get_project to return the binary for the project, and then call catalog.deploy_project.</span></span> <span data-ttu-id="ff914-144">O valor retornado por catalog.get_project é inserido em uma variável de tabela do tipo varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="ff914-144">The value returned by catalog.get_project is inserted into a table variable of type varbinary(max).</span></span> <span data-ttu-id="ff914-145">O servidor vinculado não pode retornar os resultados que são varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="ff914-145">The linked server can't return results that are varbinary(max).</span></span>  
  
 <span data-ttu-id="ff914-146">No exemplo a seguir, catalog.get_project retorna um binário para o projeto SSISPackages no servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="ff914-146">In the following example, catalog.get_project returns a binary for the SSISPackages project on the linked server.</span></span> <span data-ttu-id="ff914-147">O catalog.deploy_project implanta o projeto no servidor local, na pasta chamada DestFolder.</span><span class="sxs-lookup"><span data-stu-id="ff914-147">The catalog.deploy_project deploys the project to the local server, to the folder named DestFolder.</span></span>  
  
```  
declare @resultsTableVar table (  
project_binary varbinary(max)  
)  
  
INSERT @resultsTableVar (project_binary)  
EXECUTE [MyLinkedServer].[SSISDB].[catalog].[get_project] 'Packages', 'SSISPackages'  
  
declare @project_binary varbinary(max)  
select @project_binary = project_binary from @resultsTableVar  
  
exec [SSISDB].[CATALOG].[deploy_project] 'DestFolder', 'SSISPackages', @project_binary  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff914-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff914-148">See Also</span></span>  
 <span data-ttu-id="ff914-149">[Implantar projetos no Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="ff914-149">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 <span data-ttu-id="ff914-150">[Executar um pacote no SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ff914-150">[Run a Package in SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="ff914-151">Executar um pacote no servidor SSIS usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ff914-151">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
  
