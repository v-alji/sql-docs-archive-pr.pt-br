---
title: Toques de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2d847adf-4b3d-4949-a195-ef43de275077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053b34add45354d0df71fa73a72f8786cc706d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679454"
---
# <a name="data-flow-taps"></a><span data-ttu-id="6c4fa-102">Toques de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="6c4fa-102">Data Flow Taps</span></span>
  <span data-ttu-id="6c4fa-103">O [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] introduz um novo recurso que permite adicionar um toque de dados em um caminho de fluxo de dados de um pacote em runtime e direcionar a saída do toque de dados para um arquivo externo.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-103">[!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] introduces a new feature that allows you to add a data tap on a data flow path of a package at runtime and direct the output from the data tap to an external file.</span></span> <span data-ttu-id="6c4fa-104">Para usar esse recurso, você deverá implantar seu projeto SSIS usando o modelo de implantação de projeto em um servidor SSIS.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-104">To use this feature, you must deploy your SSIS project using the project deployment model to an SSIS Server.</span></span> <span data-ttu-id="6c4fa-105">Depois que você implantar o pacote no servidor, precisará executar scripts T-SQL no banco de dados SSISDB para adicionar toques de dados antes de executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-105">After you deploy the package to the server, you need to execute T-SQL scripts against the SSISDB database to add data taps before executing the package.</span></span> <span data-ttu-id="6c4fa-106">Aqui está um cenário de exemplo:</span><span class="sxs-lookup"><span data-stu-id="6c4fa-106">Here is a sample scenario:</span></span>  
  
1.  <span data-ttu-id="6c4fa-107">Crie uma instância de execução de um pacote usando o procedimento armazenado [catalog.create_execution &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="6c4fa-107">Create an execution instance of a package by using the [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) stored procedure.</span></span>  
  
2.  <span data-ttu-id="6c4fa-108">Adicione um toque de dados usando o procedimento armazenado [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) ou [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) .</span><span class="sxs-lookup"><span data-stu-id="6c4fa-108">Add a data tap by using either [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) or [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) stored procedure.</span></span>  
  
3.  <span data-ttu-id="6c4fa-109">Inicie a instância de execução do pacote usando [catalog.start_execution &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="6c4fa-109">Start the execution instance of the package by using the [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
 <span data-ttu-id="6c4fa-110">Veja um script SQL de exemplo que executa as etapas descritas no cenário anterior:</span><span class="sxs-lookup"><span data-stu-id="6c4fa-110">Here is a sample SQL script that performs the steps described in the above scenario:</span></span>  
  
```  
  
Declare @execid bigint  
EXEC [SSISDB].[catalog].[create_execution] @folder_name=N'ETL Folder', @project_name=N'ETL Project', @package_name=N'Package.dtsx', @execution_id=@execid OUTPUT  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt'  
EXEC [SSISDB].[catalog].[start_execution] @execid  
  
```  
  
 <span data-ttu-id="6c4fa-111">O nome da pasta, o nome do projeto, os parâmetros do nome do pacote do procedimento armazenado create_execution correspondem à pasta, ao projeto e aos nomes de pacote no catálogo do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-111">The folder name, project name, and package name parameters of the create_execution stored procedure correspond to the folder, project, and package names in the Integration Services catalog.</span></span> <span data-ttu-id="6c4fa-112">Você pode obter os nomes de pasta, projeto e pacote para usar na chamada de create_execution do SQL Server Management Studio como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-112">You can get the folder, project, and package names to use in the create_execution call from the SQL Server Management Studio as shown in the following image.</span></span> <span data-ttu-id="6c4fa-113">Se você não vir o seu projeto SSIS agora, isso significará que ainda poderá não ter implantado o projeto no servidor SSIS.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-113">If you do not see your SSIS project here, you may not have deployed the project to SSIS server yet.</span></span> <span data-ttu-id="6c4fa-114">Clique com o botão direito do mouse no projeto SSIS no Visual Studio e clique em Implantar para implantar o projeto no servidor SSIS esperado.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-114">Right-click on SSIS project in Visual Studio and click Deploy to deploy the project to the expected SSIS server.</span></span>  
  
 <span data-ttu-id="6c4fa-115">Em vez de digitar as instruções SQL, é possível gerar o script de pacote de execução realizando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6c4fa-115">Instead of typing the SQL statements, you can generate the execute package script by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="6c4fa-116">Clique com o botão direito do mouse em **Package.dtsx** e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-116">Right-click **Package.dtsx** and click **Execute**.</span></span>  
  
2.  <span data-ttu-id="6c4fa-117">Clique no botão da barra de ferramentas **Script** para gerar o script.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-117">Click **Script** toolbar button to generate the script.</span></span>  
  
3.  <span data-ttu-id="6c4fa-118">Agora, adicione a instrução add_data_tap antes da chamada start_execution.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-118">Now, add the add_data_tap statement before the start_execution call.</span></span>  
  
 <span data-ttu-id="6c4fa-119">O parâmetro task_package_path do procedimento armazenado add_data_tap corresponde à propriedade PackagePath da tarefa de fluxo de dados no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-119">The task_package_path parameter of add_data_tap stored procedure corresponds to the PackagePath property of the data flow task in Visual Studio.</span></span> <span data-ttu-id="6c4fa-120">No Visual Studio, clique com o botão direito do mouse em **Tarefa Fluxo de Dados**e clique em **Propriedades** para iniciar a janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-120">In Visual Studio, right-click the **Data Flow Task**, and click **Properties** to launch the Properties window.</span></span>  <span data-ttu-id="6c4fa-121">Observe o valor da propriedade **PackagePath** para usá-la como um valor para o parâmetro task_package_path da chamada de procedimento armazenado add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-121">Note the value of the **PackagePath** property to use it as a value for the task_package_path parameter for add_data_tap stored procedure call.</span></span>  
  
 <span data-ttu-id="6c4fa-122">O parâmetro dataflow_path_id_string do procedimento armazenado add_data_tap corresponde à propriedade IdentificationString do caminho de fluxo de dados ao qual você deseja adicionar um toque de dados.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-122">The dataflow_path_id_string  parameter of add_data_tap stored procedure corresponds to the IdentificationString property of the data flow path to which you want to add a data tap.</span></span> <span data-ttu-id="6c4fa-123">Para obter dataflow_path_id_string, clique no caminho de fluxo de dados (seta entre as tarefas no fluxo de dados) e observe o valor da propriedade **IdentificationString** na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-123">To get the dataflow_path_id_string, click the data flow path (arrow between tasks in the data flow), and note the value of the **IdentificationString** property in the Properties window.</span></span>  
  
 <span data-ttu-id="6c4fa-124">Quando você executa o script, o arquivo de saída é armazenado em \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-124">When you execute the script, the output file is stored in \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span></span> <span data-ttu-id="6c4fa-125">Se um arquivo com o mesmo nome já existir, um novo arquivo com um sufixo (por exemplo: output[1].txt) será criado.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-125">If a file with the name already exists, a new file with a suffix (for example: output[1].txt)  is created.</span></span>  
  
 <span data-ttu-id="6c4fa-126">Como mencionado anteriormente, você também pode usar o procedimento armazenado [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)em vez de usar o procedimento armazenado add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-126">As mentioned earlier, you can also use [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)stored procedure instead of using add_data_tap stored procedure.</span></span> <span data-ttu-id="6c4fa-127">Esse procedimento armazenado utiliza a ID da tarefa de fluxo de dados como um parâmetro em vez de task_package_path.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-127">This stored procedure takes the ID of data flow task as a parameter instead of task_package_path.</span></span> <span data-ttu-id="6c4fa-128">Você pode obter a ID da tarefa de fluxo de dados da janela de propriedades no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-128">You can get the ID of data flow task from the properties window in Visual Studio.</span></span>  
  
## <a name="removing-a-data-tap"></a><span data-ttu-id="6c4fa-129">Removendo um toque de dados</span><span class="sxs-lookup"><span data-stu-id="6c4fa-129">Removing a data tap</span></span>  
 <span data-ttu-id="6c4fa-130">Você pode remover um toque de dados antes de iniciar a execução usando o procedimento armazenado [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) .</span><span class="sxs-lookup"><span data-stu-id="6c4fa-130">You can remove a data tap before starting the execution by using the [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) stored procedure.</span></span> <span data-ttu-id="6c4fa-131">Esse procedimento armazenado utiliza a ID do toque de dados como um parâmetro, que você pode obter como uma saída do procedimento armazenado add_data_tap.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-131">This stored procedure takes the ID of data tap as a parameter, which you can get as an output of the add_data_tap stored procedure.</span></span>  
  
```  
  
DECLARE @tap_id bigint  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt' @data_tap_id=@tap_id OUTPUT  
EXEC [SSISDB].[catalog].remove_data_tap @tap_id  
  
```  
  
## <a name="listing-all-data-taps"></a><span data-ttu-id="6c4fa-132">Listando todos os toques de dados</span><span class="sxs-lookup"><span data-stu-id="6c4fa-132">Listing all data taps</span></span>  
 <span data-ttu-id="6c4fa-133">Você também pode listar todos os toques de dados usando a exibição de catalog.execution_data_taps.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-133">You can also list all the data taps by using the catalog.execution_data_taps view.</span></span> <span data-ttu-id="6c4fa-134">O exemplo a seguir extrai toques de dados para uma instância de execução da especificação (ID: 54).</span><span class="sxs-lookup"><span data-stu-id="6c4fa-134">The following example extracts data taps for a specification execution instance (ID: 54).</span></span>  
  
```  
select * from [SSISDB].[catalog].execution_data_taps where execution_id=@execid  
```  
  
## <a name="performance-consideration"></a><span data-ttu-id="6c4fa-135">Considerações sobre o desempenho</span><span class="sxs-lookup"><span data-stu-id="6c4fa-135">Performance consideration</span></span>  
 <span data-ttu-id="6c4fa-136">Habilitar o nível de log detalhado e adicionar toques de dados aumenta as operações de E/S executadas por sua solução de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-136">Enabling verbose logging level and adding data taps increase the I/O operations performed by your data integration solution.</span></span> <span data-ttu-id="6c4fa-137">Consequentemente, recomendamos que você adicione toques de dados somente para fins de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6c4fa-137">Hence, we recommend that you add data taps only for troubleshooting purposes</span></span>  
  
## <a name="video"></a><span data-ttu-id="6c4fa-138">Vídeo</span><span class="sxs-lookup"><span data-stu-id="6c4fa-138">Video</span></span>  
 <span data-ttu-id="6c4fa-139">Esse [vídeo no TechNet](https://technet.microsoft.com/sqlserver/dn600163) demonstra como adicionar/usar toques de dados no catálogo SSISDB do SQL Server 2012 que ajudam a depurar pacotes programaticamente e capturar resultados parciais em runtime.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-139">This [video on TechNet](https://technet.microsoft.com/sqlserver/dn600163) demonstrates how to add/use data taps in SQL Server 2012 SSISDB catalog that help with debugging packages programmatically and capturing the partial results at the runtime.</span></span> <span data-ttu-id="6c4fa-140">Ele também discute como listar/remover esses toques de dados e as práticas recomendadas para usar os toque de dados em pacotes SSIS.</span><span class="sxs-lookup"><span data-stu-id="6c4fa-140">It also discusses how to list/ remove these data taps and best practices for using data taps in SSIS packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6c4fa-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="6c4fa-141">Related Tasks</span></span>  
 [<span data-ttu-id="6c4fa-142">Depurar o fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="6c4fa-142">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="6c4fa-143">Ferramentas de solução de problemas de execução de pacote</span><span class="sxs-lookup"><span data-stu-id="6c4fa-143">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
  
