---
title: Exportar um aplicativo da camada de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportdac.settings.f1
- sql12.swb. exportdac.settings.f1
- sql12.swb.exportdac.welcome.f1
- sql12.swb. exportdac.summary.f1
- sql12.swb.exportdac.progress.f1
- sql12.swb.exportdac.summary.f1
- sql12.swb.exportdac.results.f1
- sql12.swb. exportdac.results.f1
helpviewer_keywords:
- How to [DAC], export
- wizard [DAC], export
- export DAC
- data-tier application [SQL Server], export
ms.assetid: 61915bc5-0f5f-45ac-8cfe-3452bc185558
author: stevestein
ms.author: sstein
ms.openlocfilehash: d5e1bbfc5c38dee5e7f29598086d87b680880641
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581934"
---
# <a name="export-a-data-tier-application"></a><span data-ttu-id="c6651-102">Exportar um aplicativo da camada de dados</span><span class="sxs-lookup"><span data-stu-id="c6651-102">Export a Data-tier Application</span></span>
  <span data-ttu-id="c6651-103">A exportação de um aplicativo de camada de dados implantado (DAC) ou de um banco de dados cria um arquivo de exportação que contém as definições dos objetos no banco de dados e todos os dados contidos nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="c6651-103">Exporting a deployed data-tier application (DAC) or database creates an export file that includes both the definitions of the objects in the database and all of the data contained in the tables.</span></span> <span data-ttu-id="c6651-104">O arquivo de exportação pode ser importado para outra instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)], ou para [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6651-104">The export file can then be imported to another instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="c6651-105">As operações de importação-exportação podem ser combinadas para migrar um DAC entre instâncias, criar um backup lógico ou criar uma cópia no local de um banco de dados implantado no [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6651-105">The export-import operations can be combined to migrate a DAC between instances, to create a logical backup, or to create an on-premise copy of a database deployed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="c6651-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c6651-106">Before You Begin</span></span>  
 <span data-ttu-id="c6651-107">O processo de exportação compila um arquivo de exportação DAC em duas fases.</span><span class="sxs-lookup"><span data-stu-id="c6651-107">The export process builds a DAC export file in two stages.</span></span>  
  
1.  <span data-ttu-id="c6651-108">A exportação compila uma definição de DAC no arquivo de exportação – BACPAC – do mesmo modo que uma extração de DAC compila uma definição de DAC em um arquivo de pacote de DAC.</span><span class="sxs-lookup"><span data-stu-id="c6651-108">The export builds a DAC definition in the export file - BACPAC file - in the same way a DAC extract builds a DAC definition in a DAC package file.</span></span> <span data-ttu-id="c6651-109">A definição do DAC exportada inclui todos os objetos no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="c6651-109">The exported DAC definition includes all of the objects in the current database.</span></span> <span data-ttu-id="c6651-110">Se o processo de exportação for executado em um banco de dados que foi implantado originalmente de um DAC, e tiverem sido feitas alterações diretamente no banco de dados depois da implantação, a definição exportada corresponderá ao objeto definido no banco de dados, e não ao que foi definido no DAC original.</span><span class="sxs-lookup"><span data-stu-id="c6651-110">If the export process is run against a database that was originally deployed from a DAC, and changes were made directly to the database after deployment, the exported definition matches the object set in the database, not what was defined in the original DAC.</span></span>  
  
2.  <span data-ttu-id="c6651-111">A exportação em massa copia os dados de todas as tabelas no banco de dados e incorpora os dados no arquivo de exportação.</span><span class="sxs-lookup"><span data-stu-id="c6651-111">The export bulk copies out the data from all of the tables in the database and incorporates the data into the export file.</span></span>  
  
 <span data-ttu-id="c6651-112">O processo de exportação define a versão de DAC como 1.0.0.0 e a descrição de DAC no arquivo de exportação para uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="c6651-112">The export process sets the DAC version to 1.0.0.0 and the DAC description in the export file to an empty string.</span></span> <span data-ttu-id="c6651-113">Se o banco de dados foi implantado de um DAC, a definição do DAC no arquivo de exportação conterá o nome atribuído ao DAC original; caso contrário, o nome do DAC será definido como o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6651-113">If the database was deployed from a DAC, the DAC definition in the export file contains the name given to the original DAC, otherwise the DAC name is set to the database name.</span></span>  
  

###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="c6651-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c6651-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c6651-115">Um DAC ou banco de dados só pode ser exportado de um banco de dados no [!INCLUDE[ssSDS](../../includes/sssds-md.md)]ou [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="c6651-115">A DAC or database can only be exported from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
 <span data-ttu-id="c6651-116">Você não poderá exportar um banco de dados com objetos sem suporte em um DAC ou usuários contidos.</span><span class="sxs-lookup"><span data-stu-id="c6651-116">You cannot export a database that has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="c6651-117">Para obter mais informações sobre os tipos de objetos com suporte em um DAC, consulte [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="c6651-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6651-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="c6651-118">Permissions</span></span>  
 <span data-ttu-id="c6651-119">A exportação de um DAC exige, no mínimo, as permissões ALTER ANY LOGIN e VIEW DEFINITION do escopo do banco de dados, bem como as permissões SELECT em **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="c6651-119">Exporting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="c6651-120">A exportação de um DAC pode ser feita por membros da função de servidor fixa securityadmin que também são membros da função de banco de dados fixa database_owner no banco de dados do qual o DAC é exportado.</span><span class="sxs-lookup"><span data-stu-id="c6651-120">Exporting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is exported.</span></span> <span data-ttu-id="c6651-121">Membros da função de servidor fixa sysadmin ou da conta interna do administrador do sistema do SQL Server denominada **sa** também podem exportar um DAC.</span><span class="sxs-lookup"><span data-stu-id="c6651-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also export a DAC.</span></span>  
  
##  <a name="using-the-export-data-tier-application-wizard"></a><a name="UsingDeployDACWizard"></a><span data-ttu-id="c6651-122">Usando o assistente para exportar aplicativo da camada de dados</span><span class="sxs-lookup"><span data-stu-id="c6651-122">Using the Export Data-tier Application Wizard</span></span>  
 <span data-ttu-id="c6651-123">**Para exportar um DAC usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="c6651-123">**To Export a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="c6651-124">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], seja no local ou no [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6651-124">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], whether on-premise or in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
2.  <span data-ttu-id="c6651-125">No **Pesquisador de Objetos**, expanda o nó da instância na qual você deseja exportar o DAC.</span><span class="sxs-lookup"><span data-stu-id="c6651-125">In **Object Explorer**, expand the node for the instance from which you want to export the DAC.</span></span>  
  
3.  <span data-ttu-id="c6651-126">Clique com o botão direito do mouse no nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6651-126">Right-click the database name.</span></span>  
  
4.  <span data-ttu-id="c6651-127">Clique em **tarefas** e selecione **Exportar aplicativo da camada de dados...**</span><span class="sxs-lookup"><span data-stu-id="c6651-127">Click **Tasks** and then select **Export Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="c6651-128">Conclua as etapas das caixas de diálogo do assistente:</span><span class="sxs-lookup"><span data-stu-id="c6651-128">Complete the wizard dialogs:</span></span>  
  
    -   [<span data-ttu-id="c6651-129">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="c6651-129">Introduction Page</span></span>](#Introduction)  
  
    -   [<span data-ttu-id="c6651-130">Página Configurações de Exportação</span><span class="sxs-lookup"><span data-stu-id="c6651-130">Export Settings Page</span></span>](#Export_settings)  
  
    -   [<span data-ttu-id="c6651-131">Página de Validação</span><span class="sxs-lookup"><span data-stu-id="c6651-131">Validation Page</span></span>](#Validation)  
  
    -   [<span data-ttu-id="c6651-132">Página de Resumo</span><span class="sxs-lookup"><span data-stu-id="c6651-132">Summary Page</span></span>](#Summary)  
  
    -   [<span data-ttu-id="c6651-133">Página progresso</span><span class="sxs-lookup"><span data-stu-id="c6651-133">Progress Page</span></span>](#Progress)  
  
    -   [<span data-ttu-id="c6651-134">Página Resultados</span><span class="sxs-lookup"><span data-stu-id="c6651-134">Results Page</span></span>](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="c6651-135">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="c6651-135">Introduction Page</span></span>  
 <span data-ttu-id="c6651-136">Esta página descreve as etapas do Assistente de Exportação do Aplicativo da Camada de Dados.</span><span class="sxs-lookup"><span data-stu-id="c6651-136">This page describes the steps for the Export Data-tier Application Wizard.</span></span>  
  
 <span data-ttu-id="c6651-137">**Opções**</span><span class="sxs-lookup"><span data-stu-id="c6651-137">**Options**</span></span>  
  
 <span data-ttu-id="c6651-138">**Não mostrar esta página novamente.**</span><span class="sxs-lookup"><span data-stu-id="c6651-138">**Do not show this page again.**</span></span> <span data-ttu-id="c6651-139">- Clique na caixa de seleção para interromper a exibição da página de Introdução no futuro.</span><span class="sxs-lookup"><span data-stu-id="c6651-139">- Click the check box to stop the Introduction page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="c6651-140">**Avançar** – Segue para a página **Selecionar Pacote de DAC** .</span><span class="sxs-lookup"><span data-stu-id="c6651-140">**Next** - Proceeds to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="c6651-141">**Cancelar** – cancela a operação e fecha o assistente.</span><span class="sxs-lookup"><span data-stu-id="c6651-141">**Cancel** - Cancels the operation and closes the Wizard.</span></span>  
  
##  <a name="export-settings-page"></a><a name="Export_settings"></a><span data-ttu-id="c6651-142">Página Configurações de exportação</span><span class="sxs-lookup"><span data-stu-id="c6651-142">Export Settings Page</span></span>  
 <span data-ttu-id="c6651-143">Use essa página para especificar o local onde criar o arquivo BACPAC a ser criado.</span><span class="sxs-lookup"><span data-stu-id="c6651-143">Use this page to specify the location where you want the BACPAC file to be created.</span></span>  
  
-   <span data-ttu-id="c6651-144">**Salvar no disco local** – Cria um arquivo BACPAC em um diretório no computador local.</span><span class="sxs-lookup"><span data-stu-id="c6651-144">**Save to local disk** - Creates a BACPAC file in a directory on the local computer.</span></span> <span data-ttu-id="c6651-145">Clique em **Procurar...** para navegar no computador local ou especifique o caminho no espaço fornecido.</span><span class="sxs-lookup"><span data-stu-id="c6651-145">Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span> <span data-ttu-id="c6651-146">O nome do caminho deve incluir um nome de arquivo e a extensão .bacpac.</span><span class="sxs-lookup"><span data-stu-id="c6651-146">The path name must include a file name and the .bacpac extension.</span></span>  
  
-   <span data-ttu-id="c6651-147">**Salvar no Azure**: cria um arquivo BACPAC em um contêiner do Azure.</span><span class="sxs-lookup"><span data-stu-id="c6651-147">**Save to Azure** - Creates a BACPAC file in an Azure container.</span></span> <span data-ttu-id="c6651-148">Você precisa se conectar a um contêiner do Azure para validar essa opção.</span><span class="sxs-lookup"><span data-stu-id="c6651-148">You must connect to an Azure container in order to validate this option.</span></span> <span data-ttu-id="c6651-149">Observe que esta opção também exige que você especifique um diretório local para o arquivo temporário.</span><span class="sxs-lookup"><span data-stu-id="c6651-149">Note that this option also requires that you specify a local directory for the temporary file.</span></span> <span data-ttu-id="c6651-150">Observe que o arquivo temporário será criado no local especificado e permanecerá lá depois que a operação for concluída.</span><span class="sxs-lookup"><span data-stu-id="c6651-150">Note that the temporary file will be created at the specified location and will remain there after the operation completes.</span></span>  
  
 <span data-ttu-id="c6651-151">Para especificar um subconjunto de tabelas a serem exportadas, use a opção **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="c6651-151">To specify a subset of tables to export, use the **Advanced** option.</span></span>  
  
##  <a name="validation-page"></a><a name="Validation"></a><span data-ttu-id="c6651-152">Página validação</span><span class="sxs-lookup"><span data-stu-id="c6651-152">Validation Page</span></span>  
 <span data-ttu-id="c6651-153">Use a página de validação para revisar os problemas que bloqueiam a operação.</span><span class="sxs-lookup"><span data-stu-id="c6651-153">Use the validation page to review any issues that block the operation.</span></span> <span data-ttu-id="c6651-154">Para continuar, resolva os problemas de bloqueio e clique em **Executar Novamente a Validação** para verificar se a validação foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c6651-154">To continue, resolve blocking issues and then click **Re-run Validation** to ensure that validation is successful.</span></span>  
  
 <span data-ttu-id="c6651-155">Para continuar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6651-155">To continue, click **Next**.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="c6651-156">Página de Resumo</span><span class="sxs-lookup"><span data-stu-id="c6651-156">Summary Page</span></span>  
 <span data-ttu-id="c6651-157">Use esta página para analisar a origem especificada e as configurações de destino para a operação.</span><span class="sxs-lookup"><span data-stu-id="c6651-157">Use this page to review the specified source and target settings for the operation.</span></span> <span data-ttu-id="c6651-158">Para concluir a operação de exportação usando as configurações especificadas, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c6651-158">To complete the export operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="c6651-159">Para cancelar a operação de exportação e sair do Assistente, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="c6651-159">To cancel the export operation and exit the Wizard, click **Cancel**.</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="c6651-160">Página Progresso</span><span class="sxs-lookup"><span data-stu-id="c6651-160">Progress Page</span></span>  
 <span data-ttu-id="c6651-161">Esta página exibe a barra de progresso que indica o status da operação.</span><span class="sxs-lookup"><span data-stu-id="c6651-161">This page displays a progress bar that indicates the status of the operation.</span></span> <span data-ttu-id="c6651-162">Para exibir o status detalhado, clique na opção **Exibir detalhes** .</span><span class="sxs-lookup"><span data-stu-id="c6651-162">To view detailed status, click the **View details** option.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="c6651-163">Página de resultados</span><span class="sxs-lookup"><span data-stu-id="c6651-163">Results Page</span></span>  
 <span data-ttu-id="c6651-164">Esta página reporta o êxito ou falha da operação de exportação, mostrando os resultados de cada ação.</span><span class="sxs-lookup"><span data-stu-id="c6651-164">This page reports the success or failure of the export operation, showing the results of each action.</span></span> <span data-ttu-id="c6651-165">Todas as ações que encontrarem um erro terão um link na coluna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="c6651-165">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="c6651-166">Clique no link para exibir um relatório do erro para essa ação.</span><span class="sxs-lookup"><span data-stu-id="c6651-166">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="c6651-167">Clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="c6651-167">Click **Finish** to close the Wizard.</span></span>  
  
##  <a name="using-a-net-framework-application"></a><a name="NetApp"></a><span data-ttu-id="c6651-168">Usando um aplicativo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c6651-168">Using a .Net Framework Application</span></span>  
 <span data-ttu-id="c6651-169">**Para exportar um DAC usando o método Export() em um aplicativo .NET Framework.**</span><span class="sxs-lookup"><span data-stu-id="c6651-169">**To export a DAC using the Export() method in a .Net Framework application.**</span></span>  
  
 <span data-ttu-id="c6651-170">Para exibir um exemplo de código, baixe o aplicativo de exemplo do DAC em [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span><span class="sxs-lookup"><span data-stu-id="c6651-170">To view a code example, download the DAC sample application on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span></span>  
  
1.  <span data-ttu-id="c6651-171">Crie um objeto de servidor SMO e defina-o como a instância que contém o DAC a ser exportado.</span><span class="sxs-lookup"><span data-stu-id="c6651-171">Create a SMO Server object and set it to the instance that contains the DAC to be exported.</span></span>  
  
2.  <span data-ttu-id="c6651-172">Abra um objeto `ServerConnection` e conecte-se à mesma instância.</span><span class="sxs-lookup"><span data-stu-id="c6651-172">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="c6651-173">Use o método `Export` do tipo `Microsoft.SqlServer.Management.Dac.DacStore` para exportar o DAC.</span><span class="sxs-lookup"><span data-stu-id="c6651-173">Use the `Export` method of the `Microsoft.SqlServer.Management.Dac.DacStore` type to export the DAC.</span></span> <span data-ttu-id="c6651-174">Especifique o nome do DAC a ser exportado e o caminho para a pasta onde o arquivo de exportação será colocado.</span><span class="sxs-lookup"><span data-stu-id="c6651-174">Specify the name of the DAC to be exported, and the path to the folder where the export file is to be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6651-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6651-175">See Also</span></span>  
 <span data-ttu-id="c6651-176">[Aplicativos da Camada de Dados](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c6651-176">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="c6651-177">Extrair um DAC de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="c6651-177">Extract a DAC From a Database</span></span>](extract-a-dac-from-a-database.md)  
  
  
