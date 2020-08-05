---
title: 'Etapa 3: Testando os pacotes implantados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9159da3f-c9ca-4015-9e85-3bf4373a1349
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d11ae071d97d9fdadec6ee144813c91519b54ea4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573186"
---
# <a name="step-3-testing-the-deployed-packages"></a><span data-ttu-id="10888-102">Etapa 3: Testar os pacotes implantados</span><span class="sxs-lookup"><span data-stu-id="10888-102">Step 3: Testing the Deployed Packages</span></span>
  <span data-ttu-id="10888-103">Nesta tarefa, você testará os pacotes implantados em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10888-103">In this task, you will test the packages that you deployed to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>

 <span data-ttu-id="10888-104">Em outros tutoriais do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , você executou pacotes no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], o ambiente de desenvolvimento do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], usando a opção **Iniciar Depuração** no menu **Depurar** .</span><span class="sxs-lookup"><span data-stu-id="10888-104">In other [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorials, you ran packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the development environment for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], using the **Start Debugging** option on the **Debug** menu.</span></span> <span data-ttu-id="10888-105">Desta vez você executará os pacotes de modo diferente.</span><span class="sxs-lookup"><span data-stu-id="10888-105">This time you will run the packages differently.</span></span>

 <span data-ttu-id="10888-106">O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] fornece várias ferramentas que podem ser usadas para executar pacotes no ambiente de teste e de produção: o utilitário de prompt de comando `dtexec` e o Utilitário de Execução de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="10888-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides several tools that you can use to run packages in the test and production environment: the command prompt utility `dtexec` and the Execute Package Utility.</span></span> <span data-ttu-id="10888-107">O Utilitário do Pacote de Execução é uma ferramenta gráfica compilada no `dtexec`.</span><span class="sxs-lookup"><span data-stu-id="10888-107">The Execute Package Utility is a graphical tool that is built on `dtexec`.</span></span> <span data-ttu-id="10888-108">Ambas as ferramentas executam o pacote imediatamente.</span><span class="sxs-lookup"><span data-stu-id="10888-108">Both of these tools execute the package immediately.</span></span> <span data-ttu-id="10888-109">Além disso, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fornece um subsistema do SQL Server Agent desenvolvido especialmente para agendar a execução do pacote como uma etapa em um trabalho do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="10888-109">In addition, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provides a subsystem of SQL Server Agent that is especially designed for scheduling package execution as a step in a SQL Server Agent job.</span></span>

 <span data-ttu-id="10888-110">Você usará o Utilitário do Pacote de Execução para executar os pacotes implantados.</span><span class="sxs-lookup"><span data-stu-id="10888-110">You will use the Execute Package Utility to run the deployed packages.</span></span> <span data-ttu-id="10888-111">Os pacotes serão usados como estão; portanto, você não precisa atualizar as informações em nenhuma página na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="10888-111">The packages will be used as is; therefore, you do not have to update information on any pages in the dialog box.</span></span> <span data-ttu-id="10888-112">Você executará os pacotes na página Geral, que é a primeira página do Utilitário do Pacote de Execução.</span><span class="sxs-lookup"><span data-stu-id="10888-112">You will run the packages from the General page, which is the first page in the Execute Package Utility.</span></span> <span data-ttu-id="10888-113">Se preferir, também pode clicar em outras páginas para ver as informações que elas contêm para cada pacote.</span><span class="sxs-lookup"><span data-stu-id="10888-113">If you like, you can click the other pages too see the information that they contain for each package.</span></span>

> [!NOTE]
>  <span data-ttu-id="10888-114">Para garantir que os pacotes sejam executados com êxito no contexto desse tutorial, você não deve modificar nenhuma opção.</span><span class="sxs-lookup"><span data-stu-id="10888-114">To ensure that the packages run successfully in the context of this tutorial, you should not modify any options.</span></span>

 <span data-ttu-id="10888-115">Antes de executar os pacotes no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] usando o Utilitário do Pacote de Execução, verifique se o serviço Integration Services está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="10888-115">Before you run packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] by using the Execute Package Utility, ensure that the Integration Services service is running.</span></span> <span data-ttu-id="10888-116">O serviço Integration Services fornece suporte ao armazenamento e execução de pacotes.</span><span class="sxs-lookup"><span data-stu-id="10888-116">The Integration Services service provides support for package storage and execution.</span></span> <span data-ttu-id="10888-117">Se o serviço for interrompido, você não poderá se conectar ao [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] não listará os pacotes a serem executados.</span><span class="sxs-lookup"><span data-stu-id="10888-117">If the service is stopped, you cannot connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] does not list the packages to run.</span></span> <span data-ttu-id="10888-118">Você também deve ter permissões para executar o pacote na instância em que o pacote foi implantado.</span><span class="sxs-lookup"><span data-stu-id="10888-118">You also must have permissions to run the package on the instance where the package has been deployed.</span></span> <span data-ttu-id="10888-119">Para obter mais informações, veja [Funções do Integration Services &#40;Serviço do SSIS&#41;](security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="10888-119">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](security/integration-services-roles-ssis-service.md).</span></span>

 <span data-ttu-id="10888-120">As pastas de nível superior dentro da pasta Pacotes Armazenados são as pastas definidas pelo usuário que o serviço Integration Services monitora.</span><span class="sxs-lookup"><span data-stu-id="10888-120">The top-level folders within the Stored Packages folder are the user-defined folders that Integration Services service monitors.</span></span> <span data-ttu-id="10888-121">Você pode especificar o número de pastas que quiser no arquivo MsDtsSrvr.ini.xml.</span><span class="sxs-lookup"><span data-stu-id="10888-121">You can specify as many or few folders in the MsDtsSrvr.ini.xml file as you want.</span></span> <span data-ttu-id="10888-122">Esse tutorial assume que você está usando o arquivo padrão MsDtsSrvr.ini.xml, e que os nomes das pastas de nível superior dos Pacotes Armazenados são Sistema de Arquivos e MSDB.</span><span class="sxs-lookup"><span data-stu-id="10888-122">This tutorial assumes that you are using the default MsDtsSrvr.ini.xml file, and that the names of the top-level folders within Stored Packages are File System and MSDB.</span></span>

### <a name="to-connect-to-integration-services-in-sql-server-management-studio"></a><span data-ttu-id="10888-123">Para se conectar ao Integration Services no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10888-123">To connect to Integration Services in SQL Server Management Studio</span></span>

1.  <span data-ttu-id="10888-124">Clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Microsoft SQL Server**e clique em **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="10888-124">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="10888-125">Na caixa de diálogo **Conectar ao Servidor** , selecione **Integration Services** na lista **Tipo de servidor** , forneça um nome de servidor na caixa **Nome do servidor** e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="10888-125">In the **Connect to Server** dialog box, select **Integration Services** in the **Server type** list, provide a server name in the **Server name** box, and click **Connect**.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="10888-126">Se você não consegue se conectar ao [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], provavelmente o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] não está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="10888-126">If you cannot connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is likely not running.</span></span> <span data-ttu-id="10888-127">Para saber o status do serviço, clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Microsoft SQL Server**, aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="10888-127">To learn the status of the service, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="10888-128">No painel esquerdo, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="10888-128">In the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="10888-129">No painel direito, localize o serviço do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10888-129">In the right pane, find the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="10888-130">Inicie o serviço se ainda não estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="10888-130">Start the service if it is not already running.</span></span>

     [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="10888-131">é aberto.</span><span class="sxs-lookup"><span data-stu-id="10888-131">opens.</span></span> <span data-ttu-id="10888-132">Por padrão, a janela Pesquisador de Objetos é aberta e colocada no canto superior direito do estúdio.</span><span class="sxs-lookup"><span data-stu-id="10888-132">By default the Object Explorer window is open and placed in the upper right corner of the studio.</span></span> <span data-ttu-id="10888-133">Se o Pesquisador de Objetos não for aberto, clique em **Pesquisador de Objetos** no menu **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="10888-133">If Object Explorer is not open, click **Object Explorer** on the **View** menu.</span></span>

### <a name="to-run-the-packages-using-the-execute-package-utility"></a><span data-ttu-id="10888-134">Para executar os pacotes usando o Utilitário do Pacote de Execução</span><span class="sxs-lookup"><span data-stu-id="10888-134">To run the packages using the Execute Package Utility</span></span>

1.  <span data-ttu-id="10888-135">No Pesquisador de Objetos, expanda a pasta Pacotes Armazenados.</span><span class="sxs-lookup"><span data-stu-id="10888-135">In Object Explorer, expand the Stored Packages folder.</span></span>

2.  <span data-ttu-id="10888-136">Expanda a pasta MSDB.</span><span class="sxs-lookup"><span data-stu-id="10888-136">Expand the MSDB folder.</span></span> <span data-ttu-id="10888-137">Como você implantou os pacotes no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], todos os pacotes implantados serão armazenados no banco de dados msdb do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e todos os pacotes implantados serão exibidos na pasta MSDB.</span><span class="sxs-lookup"><span data-stu-id="10888-137">Because you deployed the packages to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], all the deployed packages are stored in the msdb [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, and all deployed packages appear in the MSDB folder.</span></span> <span data-ttu-id="10888-138">A pasta Sistema de Arquivos está vazia, a menos que você tenha implantado pacotes no sistema de arquivos fora do Tutorial de Implantação.</span><span class="sxs-lookup"><span data-stu-id="10888-138">The File System folder is empty, unless you have deployed packages to the file system outside of the Deployment Tutorial.</span></span>

3.  <span data-ttu-id="10888-139">Começando no início da lista de pacotes, clique com o botão direito do mouse em DataTransfer e clique em **Executar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="10888-139">Starting at the top of the package list, right-click DataTransfer, and click **Run Package**.</span></span>

4.  <span data-ttu-id="10888-140">Na caixa de diálogo **Utilitário do Pacote de Execução** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="10888-140">In the **Execute Package Utility** dialog box, click **Execute**.</span></span>

5.  <span data-ttu-id="10888-141">Na caixa de diálogo **Utilitário do Pacote de Execução** , visualize os resultados de progresso e execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="10888-141">In the **Execute Package Utility** dialog box, view the progress and execution results of the package.</span></span> <span data-ttu-id="10888-142">Quando o botão **Parar** ficar indisponível, o que indica que o pacote está concluído, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="10888-142">When the **Stop** button becomes unavailable, which indicates that the package has completed, click **Close**.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="10888-143">Se você clicar em **Parar** enquanto o pacote estiver sendo executado, o pacote não será concluído.</span><span class="sxs-lookup"><span data-stu-id="10888-143">If you click **Stop** while the package is running, the package will not finish.</span></span>

6.  <span data-ttu-id="10888-144">Na caixa de diálogo **Utilitário do Pacote de Execução** , clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="10888-144">In the **Execute Package Utility** dialog box, click **Close**.</span></span>

7.  <span data-ttu-id="10888-145">Repita as etapas de 3 a 6 para o pacote LoadXML.</span><span class="sxs-lookup"><span data-stu-id="10888-145">Repeat steps 3 - 6 for the LoadXML package.</span></span>

8.  <span data-ttu-id="10888-146">No menu **Arquivo** , clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="10888-146">On the **File** menu, click **Exit**.</span></span>

### <a name="to-verify-the-results-of-the-datatransfer-package"></a><span data-ttu-id="10888-147">Para verificar os resultados do pacote DataTransfer</span><span class="sxs-lookup"><span data-stu-id="10888-147">To verify the results of the DataTransfer package</span></span>

1.  <span data-ttu-id="10888-148">Na barra de ferramentas do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="10888-148">On the toolbar in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], click **New Query**.</span></span>

2.  <span data-ttu-id="10888-149">Na caixa de diálogo **Conectar ao Servidor** , selecione **Mecanismo de Banco de Dados** na lista **Tipo de servidor** , forneça o nome do servidor no qual você instalou os pacotes do tutorial ou digite (local) na caixa **Nome do servidor** e selecione um modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="10888-149">In the **Connect to Server** dialog box, select **Database Engine** in the **Server type** list, provide the name of the server name on which you installed the tutorial packages or type (local) in the **Server name** box, and select an authentication mode.</span></span> <span data-ttu-id="10888-150">Se estiver usando a Autenticação do SQL Server, forneça um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="10888-150">If using SQL Server Authentication, provide a user name and password.</span></span>

3.  <span data-ttu-id="10888-151">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="10888-151">Click **Connect**.</span></span>

4.  <span data-ttu-id="10888-152">Na janela de consulta, digite ou cole a instrução SQL seguinte:</span><span class="sxs-lookup"><span data-stu-id="10888-152">In the query window, type or paste the following SQL statement:</span></span>

     `USE AdventureWorks`

     `SELECT * FROM HighIncomeCustomers`

5.  <span data-ttu-id="10888-153">Pressione **F5** ou clique no ícone Executar na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="10888-153">Press **F5** or click the Execute icon on the toolbar.</span></span>

     <span data-ttu-id="10888-154">A consulta retorna 31 linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="10888-154">The query returns 31 rows of data.</span></span> <span data-ttu-id="10888-155">O resultado de retorno contém todas as linhas do arquivo de texto, Customers.txt, com valores maiores que 100.000 na coluna YearlyIncome.</span><span class="sxs-lookup"><span data-stu-id="10888-155">The return result contains any rows from the text file, Customers.txt, that have values larger than 100000 in the YearlyIncome column.</span></span>

6.  <span data-ttu-id="10888-156">Localize a pasta DeploymentTutorial, clique com o botão direito do mouse no arquivo XML de log, Log do Tutorial de Implantação e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="10888-156">Locate the DeploymentTutorial folder, right-click the log XML file, Deployment Tutorial Log, and then click **Open**.</span></span> <span data-ttu-id="10888-157">Você pode abrir o arquivo usando o Bloco de Notas ou o editor de texto/XML de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="10888-157">You can open the file by using Notepad or the text/XML editor of choice.</span></span>

### <a name="to-verify-the-results-of-the-loadxmldata-package"></a><span data-ttu-id="10888-158">Para verificar os resultados do pacote LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="10888-158">To verify the results of the LoadXMLData package</span></span>

1.  <span data-ttu-id="10888-159">Na barra de ferramentas do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="10888-159">On the toolbar in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], click **New Query**.</span></span>

2.  <span data-ttu-id="10888-160">Se for solicitado que você se conecte novamente, na caixa de diálogo **Conectar ao Servidor** , selecione **Mecanismo de Banco de Dados** na lista **Tipo de servidor** , forneça o nome do servidor no qual você instalou os pacotes do tutorial ou digite (local) na caixa **Nome do servidor** e selecione um modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="10888-160">If prompted to connect again, in the **Connect to Server** dialog box, select **Database Engine** in the **Server type** list, provide the name of the server on which you installed the tutorial packages or enter (local) in the **Server name** box, and select an authentication mode.</span></span> <span data-ttu-id="10888-161">Se estiver usando a Autenticação do SQL Server, forneça um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="10888-161">If using SQL Server Authentication, provide a user name and password.</span></span>

3.  <span data-ttu-id="10888-162">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="10888-162">Click **Connect**.</span></span>

4.  <span data-ttu-id="10888-163">Na janela de consulta, digite ou cole a instrução SQL seguinte:</span><span class="sxs-lookup"><span data-stu-id="10888-163">In the query window, type or paste the following SQL statement:</span></span>

     `USE AdventureWorks`

     `SELECT * FROM OrderDatesByCountryRegion`

5.  <span data-ttu-id="10888-164">Pressione **F5** ou clique no ícone Executar na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="10888-164">Press **F5** or click the Execute icon on the toolbar.</span></span>

     <span data-ttu-id="10888-165">A consulta retorna 21 linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="10888-165">The query returns 21 rows of data.</span></span> <span data-ttu-id="10888-166">O resultado de retorno consiste em linhas do arquivo de dados XML, orders.xml.</span><span class="sxs-lookup"><span data-stu-id="10888-166">The return result consists of the rows from the XML data file, orders.xml.</span></span> <span data-ttu-id="10888-167">Cada linha é um resumo por país/região; a linha lista o nome do país/região, o número de ordens de cada país/região e as datas das ordens mais antigas e mais recentes.</span><span class="sxs-lookup"><span data-stu-id="10888-167">Each row is a summary by country/region; the row lists the name of a country/region, the number of orders for each country/region and the dates of the newest and oldest orders.</span></span>

<span data-ttu-id="10888-168">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="10888-168">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="10888-169">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="10888-169">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="10888-170">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="10888-170">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="10888-171">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="10888-171">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="10888-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10888-172">See Also</span></span>
 [<span data-ttu-id="10888-173">Utilitário dtexec</span><span class="sxs-lookup"><span data-stu-id="10888-173">dtexec Utility</span></span>](packages/dtexec-utility.md)

