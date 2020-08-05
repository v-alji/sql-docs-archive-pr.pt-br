---
title: Criar configurações de pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, configurations
- Package Configurations Organizer dialog box
- SSIS packages, configurations
- Integration Services packages, configurations
- configurations [Integration Services]
- packages [Integration Services], configurations
- deploying packages [Integration Services], configurations
ms.assetid: 91ac0347-f908-44f5-bd3d-115790223af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58c93242c9ef51a5e00076bd367e46b43187098e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572613"
---
# <a name="create-package-configurations"></a><span data-ttu-id="48ab9-102">Criar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="48ab9-102">Create Package Configurations</span></span>
  <span data-ttu-id="48ab9-103">Você cria as configurações do pacote por meio da caixa de diálogo **Organizador de Configurações do Pacote** e do Assistente de Configuração de Pacote.</span><span class="sxs-lookup"><span data-stu-id="48ab9-103">You create package configurations by using the **Package Configuration Organizer** dialog box and the Package Configuration Wizard.</span></span> <span data-ttu-id="48ab9-104">Para acessar essas ferramentas, clique em **Configurações do Pacote** no menu de **SSIS** em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48ab9-104">To access these tools, click **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48ab9-105">Você também pode acessar o **organizador de configurações do pacote**clicando no botão de reticências ao lado da propriedade de **configuração** .</span><span class="sxs-lookup"><span data-stu-id="48ab9-105">You can also access the **Package Configuration Organizer**, by clicking the ellipsis button next to the **Configuration** property.</span></span> <span data-ttu-id="48ab9-106">A propriedade Configuração aparece na janela de propriedades para o pacote.</span><span class="sxs-lookup"><span data-stu-id="48ab9-106">The Configuration property appears in the properties window for the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48ab9-107">As configurações estão disponíveis para o modelo de implantação de pacote.</span><span class="sxs-lookup"><span data-stu-id="48ab9-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="48ab9-108">Os parâmetros são usados no lugar das configurações para o modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="48ab9-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="48ab9-109">O modelo de implantação de projeto permite que você implante projetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48ab9-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="48ab9-110">Para obter mais informações sobre os modelos de implantação, consulte [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="48ab9-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="48ab9-111">Na caixa de diálogo **Organizador de Configurações do Pacote** , você pode habilitar pacotes para usar configurações, adicionar e excluir configurações e definir a ordem de preferência para carregar as configurações.</span><span class="sxs-lookup"><span data-stu-id="48ab9-111">In the **Package Configuration Organizer** dialog box, you can enable packages to use configurations, add and delete configurations, and set the preferred order in which configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48ab9-112">Quando as configurações de pacote são carregadas na ordem preferencial, elas são carregadas da parte superior da lista mostrada na caixa de diálogo **Organizador de Configurações do Pacote** até a parte inferior da lista.</span><span class="sxs-lookup"><span data-stu-id="48ab9-112">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="48ab9-113">Porém, no tempo de execução, talvez as configurações do pacote não sejam carregadas na ordem preferencial.</span><span class="sxs-lookup"><span data-stu-id="48ab9-113">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="48ab9-114">Em particular, as configurações do pacote pai são carregadas depois das configurações de outros tipos.</span><span class="sxs-lookup"><span data-stu-id="48ab9-114">In particular, parent package configurations load after configurations of other types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48ab9-115">Se várias configurações definirem a mesma propriedade de objeto, o valor carregado por último será usado no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="48ab9-115">If multiple configurations set the same object property, the value loaded last is used at run time.</span></span>  
  
 <span data-ttu-id="48ab9-116">Na caixa de diálogo **Organizador de Configurações do Pacote** , você executa o Assistente de Configuração de Pacotes, que o guia através de etapas para criar uma configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-116">From the **Package Configuration Organizer** dialog box, you run the Package Configuration Wizard, which guides you through the steps to create a configuration.</span></span> <span data-ttu-id="48ab9-117">Para executar o Assistente de Configuração de Pacotes, adicione uma nova configuração na caixa de diálogo **Organizador de Configurações do Pacote** ou edite uma existente.</span><span class="sxs-lookup"><span data-stu-id="48ab9-117">To run the Package Configuration Wizard, add a new configuration in the **Package Configurations Organizer** dialog box or edit an existing one.</span></span> <span data-ttu-id="48ab9-118">Nas páginas do assistente, você escolhe o tipo de configuração, escolhe se quer acessar a configuração diretamente ou usar variáveis de ambiente, e seleciona as propriedades a serem salvas na configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-118">On the wizard pages, you choose the configuration type, select whether you want to access the configuration directly or use environment variables, and select the properties to save in the configuration.</span></span>  
  
 <span data-ttu-id="48ab9-119">O exemplo a seguir mostra as propriedades de destino de uma variável e de um pacote, do modo como são mostradas na página Concluindo o Assistente, no Assistente de Configuração de Pacotes:</span><span class="sxs-lookup"><span data-stu-id="48ab9-119">The following example shows the target properties of a variable and a package as they appear on the Completing the Wizard page of the Package Configuration Wizard.:</span></span>  
  
 <span data-ttu-id="48ab9-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span><span class="sxs-lookup"><span data-stu-id="48ab9-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span></span>  
  
 <span data-ttu-id="48ab9-121">\Package.Properties[MaximumErrorCount]</span><span class="sxs-lookup"><span data-stu-id="48ab9-121">\Package.Properties[MaximumErrorCount]</span></span>  
  
 <span data-ttu-id="48ab9-122">\Package.Properties[LoggingMode]</span><span class="sxs-lookup"><span data-stu-id="48ab9-122">\Package.Properties[LoggingMode]</span></span>  
  
 <span data-ttu-id="48ab9-123">\Package.Properties[LocaleID]</span><span class="sxs-lookup"><span data-stu-id="48ab9-123">\Package.Properties[LocaleID]</span></span>  
  
 <span data-ttu-id="48ab9-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span><span class="sxs-lookup"><span data-stu-id="48ab9-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span></span>  
  
 <span data-ttu-id="48ab9-125">Neste exemplo, a configuração atualiza estas propriedades:</span><span class="sxs-lookup"><span data-stu-id="48ab9-125">In this example, the configuration updates these properties:</span></span>  
  
-   <span data-ttu-id="48ab9-126">A propriedade RaiseChangedEvent da variável definida pelo usuário, `TodaysDate`.</span><span class="sxs-lookup"><span data-stu-id="48ab9-126">The RaiseChangedEvent property of user-defined variable, `TodaysDate`.</span></span>  
  
-   <span data-ttu-id="48ab9-127">As propriedades MaximumErrorCount, LoggingMode e LocaleID do pacote.</span><span class="sxs-lookup"><span data-stu-id="48ab9-127">The MaximumErrorCount, LoggingMode, and LocaleID properties of the package.</span></span>  
  
-   <span data-ttu-id="48ab9-128">A propriedade Value da variável definida pelo usuário, `varTableName`, dentro do escopo da tarefa, My SQL Task.</span><span class="sxs-lookup"><span data-stu-id="48ab9-128">The Value property of user-defined variable, `varTableName`, within scope of the task, My SQL Task.</span></span>  
  
 <span data-ttu-id="48ab9-129">O "\Package" representa a raiz e pontos (.) separam os objetos que definem o caminho até a propriedade que a configuração atualiza.</span><span class="sxs-lookup"><span data-stu-id="48ab9-129">The "\Package" represents the root, and periods (.) separate the objects that define the path to the property that the configuration updates.</span></span> <span data-ttu-id="48ab9-130">Os nomes das variáveis e das propriedades estão entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="48ab9-130">The names of variables and properties are enclosed in brackets.</span></span> <span data-ttu-id="48ab9-131">O termo Package sempre é usado na configuração, independente do nome do pacote; porém, todos os outros objetos no caminho usam os nomes definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="48ab9-131">The term Package is always used in configuration, regardless of the package name; however, all other objects in the path use their user-defined names.</span></span>  
  
 <span data-ttu-id="48ab9-132">Depois que o assistente terminar, a nova configuração é adicionada à lista de configurações na caixa de diálogo **Organizador de Configurações do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="48ab9-132">After the wizard finishes, the new configuration is added to the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48ab9-133">A última página do Assistente de Configuração de Pacote, Concluindo o Assistente, lista as propriedades de destino da configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-133">The last page in the Package Configuration Wizard, Completing the Wizard, lists the target properties in the configuration.</span></span> <span data-ttu-id="48ab9-134">Se quiser atualizar as propriedades enquanto estiver executando pacotes usando o utilitário prompt de comando **dtexec** , você poderá gerar as cadeias de caracteres que representam os caminhos de propriedade executando o Assistente de Configuração de Pacotes e, então, copiá-las e colá-las na janela do prompt de comando para usar com a opção definida de **dtexec.**</span><span class="sxs-lookup"><span data-stu-id="48ab9-134">If you want to update properties when you run packages by using the **dtexec** command prompt utility, you can generate the strings that represent the property paths by running the Package Configuration Wizard and then copy and paste them into the command prompt window for use with the set option of **dtexec.**</span></span>  
  
 <span data-ttu-id="48ab9-135">A tabela a seguir descreve as colunas da lista de configurações na caixa de diálogo **Organizador de Configurações do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="48ab9-135">The following table describes the columns in the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
|<span data-ttu-id="48ab9-136">Coluna</span><span class="sxs-lookup"><span data-stu-id="48ab9-136">Column</span></span>|<span data-ttu-id="48ab9-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="48ab9-137">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="48ab9-138">**Nome da Configuração**</span><span class="sxs-lookup"><span data-stu-id="48ab9-138">**Configuration Name**</span></span>|<span data-ttu-id="48ab9-139">O nome da configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-139">The name of the configuration.</span></span>|  
|<span data-ttu-id="48ab9-140">**Tipo de Configuração**</span><span class="sxs-lookup"><span data-stu-id="48ab9-140">**Configuration Type**</span></span>|<span data-ttu-id="48ab9-141">O tipo de configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-141">The configuration type.</span></span>|  
|<span data-ttu-id="48ab9-142">**Cadeia de Caracteres de Configuração**</span><span class="sxs-lookup"><span data-stu-id="48ab9-142">**Configuration String**</span></span>|<span data-ttu-id="48ab9-143">O local da configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-143">The location of the configuration.</span></span> <span data-ttu-id="48ab9-144">O local pode ser um caminho, uma variável de ambiente, uma chave do Registro, um nome de variável do pacote pai ou uma tabela em um banco de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48ab9-144">The location can be a path, an environment variable, a Registry key, a parent package variable name, or a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="48ab9-145">**Objeto de Destino**</span><span class="sxs-lookup"><span data-stu-id="48ab9-145">**Target Object**</span></span>|<span data-ttu-id="48ab9-146">O nome do objeto com uma propriedade que tem uma configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-146">The name of the object with a property that has a configuration.</span></span> <span data-ttu-id="48ab9-147">Se a configuração for um arquivo de configuração XML, a coluna ficará em branco, devido à configuração poder atualizar vários objetos.</span><span class="sxs-lookup"><span data-stu-id="48ab9-147">If the configuration is an XML configuration file, the column is blank, because the configuration can update multiple objects.</span></span>|  
|<span data-ttu-id="48ab9-148">**Propriedade de Destino**</span><span class="sxs-lookup"><span data-stu-id="48ab9-148">**Target Property**</span></span>|<span data-ttu-id="48ab9-149">O nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="48ab9-149">The name of the property.</span></span> <span data-ttu-id="48ab9-150">Se a configuração gravar em um arquivo de configuração XML ou em uma tabela do SQL Server, a coluna ficará em branco, pois a configuração pode atualizar vários objetos.</span><span class="sxs-lookup"><span data-stu-id="48ab9-150">If the configuration writes to an XML configuration file or a SQL Server table, the column is blank, because the configuration can update multiple objects.</span></span>|  
  
### <a name="to-create-a-package-configuration"></a><span data-ttu-id="48ab9-151">Para criar uma configuração de pacote</span><span class="sxs-lookup"><span data-stu-id="48ab9-151">To create a package configuration</span></span>  
  
1.  <span data-ttu-id="48ab9-152">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="48ab9-152">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="48ab9-153">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="48ab9-153">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="48ab9-154">No Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique na guia **Fluxo de Controle**, **Fluxo de Dados**, **Manipulador de Eventos**ou **Explorador de Pacotes** .</span><span class="sxs-lookup"><span data-stu-id="48ab9-154">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, **Event Handler**, or **Package Explorer** tab.</span></span>  
  
4.  <span data-ttu-id="48ab9-155">No menu **SSIS** , clique em **Configurações do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="48ab9-155">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="48ab9-156">Na caixa de diálogo **Organizador de Configurações do Pacote** , selecione **Habilitar configurações do pacote**e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="48ab9-156">In the **Package Configuration Organizer** dialog box, select **Enable package configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="48ab9-157">Na página inicial da página Assistente de Configuração de Pacotes, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="48ab9-157">On the welcome page of the Package Configuration Wizard page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="48ab9-158">Na página Selecionar Tipo de Configuração, especifique o tipo de configuração e defina as propriedades pertinentes ao tipo de configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-158">On the Select Configuration Type page, specify the configuration type, and then set the properties that are relevant to the configuration type.</span></span> <span data-ttu-id="48ab9-159">Para obter mais informações, consulte [Referência da interface do usuário do Assistente de Configuração de Pacotes](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="48ab9-159">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
8.  <span data-ttu-id="48ab9-160">Na página Selecionar Propriedades a Serem Exportadas, selecione as propriedades dos objetos do pacote a serem incluídas na configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-160">On the Select Properties to Export page, select the properties of package objects to include in the configuration.</span></span> <span data-ttu-id="48ab9-161">Se o tipo de configuração oferecer suporte somente a uma propriedade, o título dessa página de assistente será Selecionar Propriedade de Destino.</span><span class="sxs-lookup"><span data-stu-id="48ab9-161">If the configuration type supports only one property, the title of this wizard page is Select Target Property.</span></span> <span data-ttu-id="48ab9-162">Para obter mais informações, consulte [Referência da interface do usuário do Assistente de Configuração de Pacotes](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="48ab9-162">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48ab9-163">Somente os tipos de configuração **Arquivo de Configuração XML** e **SQL Server** dão suporte à inclusão de várias propriedades em uma configuração.</span><span class="sxs-lookup"><span data-stu-id="48ab9-163">Only the **XML Configuration File** and **SQL Server** configuration types support including multiple properties in a configuration.</span></span>  
  
9. <span data-ttu-id="48ab9-164">Na página Concluindo o Assistente, digite o nome da configuração e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="48ab9-164">On the Completing the Wizard page, type the name of the configuration, and then click **Finish**.</span></span>  
  
10. <span data-ttu-id="48ab9-165">Exiba a configuração na caixa de diálogo **Organizador de Configurações do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="48ab9-165">View the configuration in the **Package Configuration Organizer** dialog box.</span></span>  
  
11. <span data-ttu-id="48ab9-166">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="48ab9-166">Click **Close**.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="48ab9-167">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="48ab9-167">External Resources</span></span>  
  
-   <span data-ttu-id="48ab9-168">Artigo técnico de [Noções básicas sobre configurações de pacotes do Integration Services](https://go.microsoft.com/fwlink/?LinkId=165643), em msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="48ab9-168">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="48ab9-169">Entrada de blog, [criando pacotes em configurações de pacote de código](https://go.microsoft.com/fwlink/?LinkId=217663), em www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="48ab9-169">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="48ab9-170">Entrada de blog, [exemplo de API – adicione programaticamente um arquivo de configuração a um pacote](https://go.microsoft.com/fwlink/?LinkId=217664), em Blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="48ab9-170">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ab9-171">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48ab9-171">See Also</span></span>  
 <span data-ttu-id="48ab9-172">[Configurações do pacote](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="48ab9-172">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="48ab9-173">[Implantação de pacote &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="48ab9-173">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="48ab9-174">Trabalhando com variáveis programaticamente</span><span class="sxs-lookup"><span data-stu-id="48ab9-174">Working with Variables Programmatically</span></span>](building-packages-programmatically/working-with-variables-programmatically.md)  
  
  
