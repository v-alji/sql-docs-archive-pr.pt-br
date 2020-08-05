---
title: 'Etapa 4: adicionar configurações de pacote | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e04a5321-63d5-4ec5-85b9-cb4eaf6c87f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 416cf17f967a145fccef1341b77f71a02ff3f3b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574136"
---
# <a name="step-4-adding-package-configurations"></a><span data-ttu-id="dfd7e-102">Etapa 4: Adicionar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="dfd7e-102">Step 4: Adding Package Configurations</span></span>
  <span data-ttu-id="dfd7e-103">Nessa tarefa, você adicionará uma configuração a cada pacote.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-103">In this task, you will add a configuration to each package.</span></span> <span data-ttu-id="dfd7e-104">As configurações atualizam os valores das propriedades e dos objetos do pacote em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-104">Configurations update the values of package properties and package objects at run time.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="dfd7e-105">fornece uma variedade de tipos de configuração.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-105">provides a variety of configuration types.</span></span> <span data-ttu-id="dfd7e-106">Você pode armazenar configurações em variáveis de ambiente, entradas de Registro, variáveis definidas pelo usuário, tabelas [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-106">You can store configurations in environment variables, registry entries, user-defined variables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables, and XML files.</span></span> <span data-ttu-id="dfd7e-107">Para fornecer flexibilidade adicional, o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] oferece suporte ao uso de configurações indiretas.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-107">To provide additional flexibility, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] supports the use of indirect configurations.</span></span> <span data-ttu-id="dfd7e-108">Isso significa que você usa uma variável de ambiente para especificar o local da configuração, que por sua vez especifica os valores reais.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-108">This means that you use an environment variable to specify the location of the configuration, which in turn specifies the actual values.</span></span> <span data-ttu-id="dfd7e-109">Os pacotes no projeto Tutorial de Implantação usam uma combinação de arquivos de configuração XML e configurações indiretas.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-109">The packages in the Deployment Tutorial project use a combination of XML configuration files and indirect configurations.</span></span> <span data-ttu-id="dfd7e-110">Um arquivo de configuração XML pode incluir configurações para várias propriedades e, quando apropriado, pode ser mencionado por vários pacotes.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-110">An XML configuration file can include configurations for multiple properties, and when appropriate, can be referenced by multiple packages.</span></span> <span data-ttu-id="dfd7e-111">Neste tutorial, você usará um arquivo de configuração separado para cada pacote.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-111">In this tutorial, you will use a separate configuration file for each package.</span></span>  
  
 <span data-ttu-id="dfd7e-112">Os arquivos de configuração normalmente contêm informações confidenciais, como cadeia de caracteres de conexão.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-112">Configuration files frequently contain sensitive information such as connection strings.</span></span> <span data-ttu-id="dfd7e-113">Portanto, você deverá usar uma lista de controle de acesso (ACL) para restringir o acesso ao local ou à pasta em que você armazena os arquivos, e fornecer acesso apenas aos usuários ou contas com permissão para executar pacotes.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-113">Therefore, you should use an access control list (ACL) to restrict access to the location or folder where you store the files, and give access only to users or accounts that are permitted to run packages.</span></span> <span data-ttu-id="dfd7e-114">Para obter mais informações, consulte [Acesso aos arquivos usados por pacotes](../../2014/integration-services/access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="dfd7e-114">For more information, see [Access to Files Used by Packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="dfd7e-115">Os pacotes (DataTransfer e LoadXMLData) adicionados ao projeto Tutorial de Implantação na tarefa anterior precisam de configurações para serem executados com êxito depois de implantados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-115">The packages (DataTransfer and LoadXMLData) that you added to the Deployment Tutorial project in the previous task need configurations to run successfully after they are deployed to the target server.</span></span> <span data-ttu-id="dfd7e-116">Para implementar configurações, você criará primeiro as configurações indiretas para os arquivos XML e, depois, criará os arquivos de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-116">To implement configurations, you will first create the indirect configurations for the XML configuration files, and then you will create the XML configuration files.</span></span>  
  
 <span data-ttu-id="dfd7e-117">Serão criados dois arquivos de configuração, DataTransferConfig.dtsConfig e LoadXMLData.dtsConfig.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-117">You will create two configuration files, DataTransferConfig.dtsConfig and LoadXMLData.dtsConfig.</span></span> <span data-ttu-id="dfd7e-118">Esses arquivos contêm os pares nome-valor que atualizam as propriedades nos pacotes que especificam o local dos arquivos de dados e de log usados pelo pacote.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-118">These files contain name-value pairs that update the properties in packages that specify the location of the data and log files used by the package.</span></span> <span data-ttu-id="dfd7e-119">Depois, como uma etapa no processo de implantação, você atualizará os valores nos arquivos de configuração para refletir o novo local dos arquivos no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-119">Later, as a step in the deployment process, you will update the values in the configuration files to reflect the new location of the files on the destination computer.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="dfd7e-120">reconhece que Datatransferconfig.dtsconfig e LoadXMLData.dtsConfig são dependências dos pacotes DataTransfer e LoadXMLData, e automaticamente incluirá os arquivos de configuração quando você criar o pacote de implantação na próxima lição.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-120">recognizes that the DataTransferConfig.dtsConfig and LoadXMLData.dtsConfig are dependencies of the DataTransfer and LoadXMLData packages, and automatically includes the configuration files when you create the deployment bundle in the next lesson.</span></span>  
  
### <a name="to-create-indirect-configuration-for-the-datatransfer-package"></a><span data-ttu-id="dfd7e-121">Para criar configuração indireta para o pacote DataTransfer</span><span class="sxs-lookup"><span data-stu-id="dfd7e-121">To create indirect configuration for the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="dfd7e-122">No Gerenciador de Soluções, clique duas vezes em DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-122">In Solution Explorer, double-click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="dfd7e-123">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique em qualquer local no plano de fundo da superfície de design do fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-123">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click anywhere in the background of the control flow design surface.</span></span>  
  
3.  <span data-ttu-id="dfd7e-124">No menu **SSIS** , clique em **Configurações do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-124">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="dfd7e-125">Na caixa de diálogo **Organizador de Configurações do Pacote**, selecione a opção **Habilitar configurações do pacote** , se não estiver selecionada, e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-125">In the **Package Configuration Organize**r dialog box, select **Enable package configurations** if it is not already selected, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="dfd7e-126">Na página inicial do assistente de configuração de pacotes, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-126">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
6.  <span data-ttu-id="dfd7e-127">Na página Selecionar tipo de configuração, selecione **arquivo de configuração XML** na lista **tipo de configuração** , selecione a opção o local de **configuração está armazenado em uma variável de ambiente** e digite `DataTransfer,` ou selecione a variável de ambiente **DataTransfer** na lista.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-127">On the Select Configuration Type page, select **XML configuration file** in the **Configuration type** list, select the **Configuration location is stored in an environment variable** option, and type `DataTransfer,` or select the **DataTransfer** environment variable in the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dfd7e-128">Para disponibilizar a variável de ambiente na lista, talvez você precise reiniciar o computador após a adição da variável.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-128">To make the environment variable available in the list, you may have to restart your computer after adding the variable.</span></span> <span data-ttu-id="dfd7e-129">Se você não quiser reiniciar o computador, poderá digitar o nome da variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-129">If you do not want to restart the computer, you can type the name of the environment variable.</span></span>  
  
7.  <span data-ttu-id="dfd7e-130">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-130">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="dfd7e-131">Na página Concluindo o Assistente, digite **DataTransfer EV Configuration** na caixa **Nome da Configuração** , revise o conteúdo da configuração no painel **Visualização** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-131">On the Completing the Wizard page, type **DataTransfer EV Configuration** in the **Configuration name** box, review the configuration contents in the **Preview** pane, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="dfd7e-132">Feche a caixa de diálogo **Organizador de Configurações do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-132">Close the **Package Configuration Organize**r dialog box.</span></span>  
  
### <a name="to-create-the-xml-configuration-for-the-datatransfer-package"></a><span data-ttu-id="dfd7e-133">Para criar a configuração XML para o pacote DataTransfer</span><span class="sxs-lookup"><span data-stu-id="dfd7e-133">To create the XML configuration for the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="dfd7e-134">No Gerenciador de Soluções, clique duas vezes em DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-134">In Solution Explorer, double-click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="dfd7e-135">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique em qualquer local no plano de fundo da superfície de design do fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-135">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click anywhere in the background of the control flow design surface.</span></span>  
  
3.  <span data-ttu-id="dfd7e-136">No menu **SSIS** , clique em **Configurações do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-136">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="dfd7e-137">Na caixa de diálogo do Organizador de Configurações do Pacote, selecione a caixa de seleção **Habilitar Configurações do Pacote** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-137">In the Package Configuration Organizer dialog box, select the **Enable Package Configurations** check-box, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="dfd7e-138">Na página inicial do assistente de configuração de pacotes, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-138">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
6.  <span data-ttu-id="dfd7e-139">Na página Selecionar Tipo de Configuração, selecione **Arquivo de configuração XML** na lista **Tipo de configuração** e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-139">On the Select Configuration Type page, select **XML configuration file** in the **Configuration type** list and then click **Browse**.</span></span>  
  
7.  <span data-ttu-id="dfd7e-140">Na caixa de diálogo **Selecionar Local do Arquivo de Configuração** , procure C:\DeploymentTutorial, digite **DataTransferConfig** na caixa **Nome do arquivo** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-140">In **Select Configuration File Location** dialog box, navigate to C:\DeploymentTutorial and type **DataTransferConfig** in the **File name** box, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="dfd7e-141">Na página Selecionar tipo de configuração, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-141">On the Select Configuration Type page, click **Next**.</span></span>  
  
9. <span data-ttu-id="dfd7e-142">Na página Selecionar Propriedades a Serem Exportadas, expanda DataTransfer, Gerenciadores de Conexões, Log do Tutorial de Implantação e Propriedades e marque a caixa de seleção **Cadeia de Conexão** .</span><span class="sxs-lookup"><span data-stu-id="dfd7e-142">On the Select Properties to Export page, expand DataTransfer, Connection Managers, Deployment Tutorial Log, and Properties, and then select the **Connection String** check-box.</span></span>  
  
10. <span data-ttu-id="dfd7e-143">Em Gerenciadores de Conexões, expanda NewCustomers e marque a caixa de seleção **Cadeia de Conexão** .</span><span class="sxs-lookup"><span data-stu-id="dfd7e-143">Within Connection Managers, expand NewCustomers, and then select the **Connection String** check-box.</span></span>  
  
11. <span data-ttu-id="dfd7e-144">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-144">Click **Next**.</span></span>  
  
12. <span data-ttu-id="dfd7e-145">Na página Concluindo o Assistente, digite **DataTransfer Configuration** na caixa **Nome da configuração** , revise o conteúdo da configuração e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-145">On the Completing the Wizard page, type **DataTransfer Configuration** in the **Configuration name** box, review the content of the configuration, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="dfd7e-146">Na caixa de diálogo **Organizador de Configurações do Pacote** , verifique se a opção DataTransfer EV Configuration é a primeira da lista e DataTransfer Configuration é a segunda da lista. Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-146">In the **Package Configuration Organizer** dialog box, verify that DataTransfer EV Configuration is listed first, and DataTransfer Configuration is listed second, and then click **Close**.</span></span>  
  
### <a name="to-create-indirect-configuration-for-the-loadxmldata-package"></a><span data-ttu-id="dfd7e-147">Para criar configuração indireta para o pacote LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="dfd7e-147">To create indirect configuration for the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="dfd7e-148">No Gerenciador de Soluções, clique duas vezes em LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-148">In Solution Explorer, double-click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="dfd7e-149">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique em qualquer local no plano de fundo da superfície de design do fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-149">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click anywhere in the background of the control flow design surface.</span></span>  
  
3.  <span data-ttu-id="dfd7e-150">No menu **SSIS** , clique em **Configurações do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-150">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="dfd7e-151">Na caixa de diálogo **Organizador de Configurações do Pacote**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-151">In the **Package Configuration Organize**r dialog box, Click **Add**.</span></span>  
  
5.  <span data-ttu-id="dfd7e-152">Na página inicial do assistente de configuração de pacotes, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-152">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
6.  <span data-ttu-id="dfd7e-153">Na página Selecionar tipo de configuração, selecione **arquivo de configuração XML** na lista **tipo de configuração** , selecione a opção o local de **configuração está armazenado em uma variável de ambiente** , digite `LoadXMLData` ou selecione a `LoadXMLData` variável de ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-153">On the Select Configuration Type page, select **XML configuration file** in the **Configuration type** list, select the **Configuration location is stored in an environment variable** option, type `LoadXMLData` or select the `LoadXMLData` environment variable in the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dfd7e-154">Para disponibilizar a variável de ambiente na lista, talvez você precise reiniciar o computador após a adição da variável.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-154">To make the environment variable available in the list, you may have to restart your computer after adding the variable.</span></span>  
  
7.  <span data-ttu-id="dfd7e-155">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-155">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="dfd7e-156">Na página Concluindo o Assistente, digite **LoadXMLData EV Configuration** na caixa **Nome da configuração** , revise o conteúdo da configuração e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-156">On the Completing the Wizard page, type **LoadXMLData EV Configuration** in the **Configuration name** box, review the content of the configuration, and then click **Finish**.</span></span>  
  
### <a name="to-create-the-xml-configuration-for-the-loadxmldata-package"></a><span data-ttu-id="dfd7e-157">Para criar a configuração XML para o pacote LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="dfd7e-157">To create the XML configuration for the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="dfd7e-158">No Gerenciador de Soluções, clique duas vezes em LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-158">In Solution Explorer, double-click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="dfd7e-159">No Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique em qualquer local no plano de fundo da superfície de design do fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-159">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click anywhere in the background of the control flow design surface.</span></span>  
  
3.  <span data-ttu-id="dfd7e-160">No menu **SSIS** , clique em **Configurações do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-160">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="dfd7e-161">Na caixa de diálogo do Organizador de Configurações do Pacote, marque a caixa de seleção **Habilitar Configurações do Pacote** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-161">In the Package Configuration Organizer dialog box, select the **Enable Package Configurations** check-box, and click **Add**.</span></span>  
  
5.  <span data-ttu-id="dfd7e-162">Na página inicial do assistente de configuração de pacotes, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-162">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
6.  <span data-ttu-id="dfd7e-163">Na página Selecionar Tipo de Configuração, selecione **Arquivo de configuração XML** na lista **Tipo de configuração** e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-163">On the Select Configuration Type page, select **XML configuration file** in the **Configuration type** list and click **Browse**.</span></span>  
  
7.  <span data-ttu-id="dfd7e-164">Na caixa de diálogo **Selecionar Local do Arquivo de Configuração** , procure C:\DeploymentTutorial, digite **LoadXMLDataConfig** na caixa **Nome do arquivo** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-164">In **Select Configuration File Location** dialog box, navigate to C:\DeploymentTutorial and type **LoadXMLDataConfig** in the **File name** box, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="dfd7e-165">Na página Selecionar tipo de configuração, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-165">On the Select Configuration Type page, click **Next**.</span></span>  
  
9. <span data-ttu-id="dfd7e-166">Na página Selecionar Propriedades a Serem Exportadas, expanda LoadXMLData, Executáveis, Carregar Dados XML e Propriedades e marque as caixas de seleção **[XMLSource].[XMLData]** e **[XMLSource].[XMLSchemaDefinition]** .</span><span class="sxs-lookup"><span data-stu-id="dfd7e-166">On the Select Properties to Export page, expand LoadXMLData, Executables, Load XML Data, and Properties, and then select the **[XMLSource].[XMLData]** and **[XMLSource].[XMLSchemaDefinition]** check boxes.</span></span>  
  
10. <span data-ttu-id="dfd7e-167">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-167">Click **Next**.</span></span>  
  
11. <span data-ttu-id="dfd7e-168">Na página Concluindo o Assistente, digite **LoadXMLData Configuration** na caixa **Nome da configuração** , revise o conteúdo da configuração e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-168">On the Completing the Wizard page, type **LoadXMLData Configuration** in the **Configuration name** box, review the content of the configuration, and then click **Finish**.</span></span>  
  
12. <span data-ttu-id="dfd7e-169">Na caixa de diálogo **Organizador de Configurações do Pacote** , verifique se a opção LoadXMLData EV Configuration é a primeira da lista e LoadXMLData Configuration é a segunda da lista e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-169">In the **Package Configuration Organizer** dialog box, verify that the LoadXMLData EV Configuration is listed first, and the LoadXMLData Configuration is listed second, and then click **Close**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dfd7e-170">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="dfd7e-170">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dfd7e-171">Etapa 5: Testar os pacotes atualizados</span><span class="sxs-lookup"><span data-stu-id="dfd7e-171">Step 5: Testing the Updated Packages</span></span>](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
<span data-ttu-id="dfd7e-172">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dfd7e-172">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dfd7e-173">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="dfd7e-173">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dfd7e-174">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="dfd7e-174">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dfd7e-175">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="dfd7e-175">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd7e-176">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dfd7e-176">See Also</span></span>  
 <span data-ttu-id="dfd7e-177">[Configurações do pacote](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="dfd7e-177">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="dfd7e-178">[Criar configurações de pacote](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="dfd7e-178">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 [<span data-ttu-id="dfd7e-179">Acesso aos arquivos usados por pacotes</span><span class="sxs-lookup"><span data-stu-id="dfd7e-179">Access to Files Used by Packages</span></span>](../../2014/integration-services/access-to-files-used-by-packages.md)  
  
  
