---
title: Especificando definições de configuração para implantação de solução | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services Deployment Wizard, configuration settings
- input files [Analysis Services]
- configuration options [Analysis Services]
- Analysis Services deployments, configuration settings
- deploying [Analysis Services], configuration settings
ms.assetid: 953814a3-85ef-40cc-b46a-d532aa7a6569
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83b08ce2b6296a5098c1b21a3afa443668c481a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572754"
---
# <a name="specifying-configuration-settings-for-solution-deployment"></a><span data-ttu-id="38840-102">Especificando definições de configuração para implantação de solução</span><span class="sxs-lookup"><span data-stu-id="38840-102">Specifying Configuration Settings for Solution Deployment</span></span>
  <span data-ttu-id="38840-103">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Assistente de implantação lê as opções de implantação de partição e função que você usa no script de implantação do \<*project name*> arquivo. configsettings.</span><span class="sxs-lookup"><span data-stu-id="38840-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the partition and role deployment options that you use in the deployment script from the \<*project name*>.configsettings file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="38840-104">cria esse arquivo quando você compila o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="38840-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="38840-105">usa as definições de configuração do projeto atual para criar o \<*project name*> arquivo. configsettings.</span><span class="sxs-lookup"><span data-stu-id="38840-105">uses the configuration settings of the current project to create the \<*project name*>.configsettings file.</span></span>  
  
## <a name="reviewing-the-configuration-settings-for-deployment"></a><span data-ttu-id="38840-106">Revisando parâmetros de configuração para implantação</span><span class="sxs-lookup"><span data-stu-id="38840-106">Reviewing the Configuration Settings for Deployment</span></span>  
 <span data-ttu-id="38840-107">Veja a seguir as definições de configuração armazenadas no \<*project name*> arquivo. configsettings:</span><span class="sxs-lookup"><span data-stu-id="38840-107">The following are the configuration settings stored in the \<*project name*>.configsettings file:</span></span>  
  
-   <span data-ttu-id="38840-108">**Cadeias de Conexão de Fonte de Dados** São cadeias de caracteres de conexão para cada fonte de dados baseada nos valores especificados do projeto [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38840-108">**Data Source Connection Strings** These are the connection strings for each data source based on the values specified in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="38840-109">A ID de usuário e senha são sempre removidas da cadeia de caracteres de conexão antes da cadeia restante ser armazenada nesse arquivo.</span><span class="sxs-lookup"><span data-stu-id="38840-109">The user id and password are always removed from the connection string before the remainder of the string is stored in this file.</span></span> <span data-ttu-id="38840-110">Porém, se o Assistente para Implantação estiver fazendo a implantação diretamente em uma instância do Analysis Services, você poderá adicionar as informações adequadas de ID de usuário e senha ao assistente para habilitar um processamento bem-sucedido do banco de dados de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="38840-110">However, if the Deployment Wizard is deploying directly to an Analysis Services instance, you can add the appropriate user id and password information within the wizard to enable a successful processing of the deployment database.</span></span> <span data-ttu-id="38840-111">Essas informações de conexão não serão armazenadas no próprio script de implantação se alguma for salva pelo Assistente para Implantação.</span><span class="sxs-lookup"><span data-stu-id="38840-111">This connection information will not be stored in the deployment script itself if one is saved by the Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="38840-112">**Contas de representação** Esta configuração especifica o nome de usuário que o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usa para executar instruções em cada fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="38840-112">**Impersonation Accounts** This setting specifies the user name that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses to run statements in each data source.</span></span> <span data-ttu-id="38840-113">Se nenhuma conta de representação for especificada, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usará sua conta de logon para executar instruções.</span><span class="sxs-lookup"><span data-stu-id="38840-113">If no impersonation account is specified, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses its logon account to run statements.</span></span> <span data-ttu-id="38840-114">Se a conta de logon do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] receber permissões diretamente na fonte de dados, todos os administradores de banco de dados em todos os bancos de dados na instância [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] terão acesso à fonte de dados pela conta de logon.</span><span class="sxs-lookup"><span data-stu-id="38840-114">If the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] logon account is granted permissions directly in the data source, all database administrators in all databases in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance have access to the data source through the logon account.</span></span> <span data-ttu-id="38840-115">Se uma conta e senha do usuário forem especificadas, essas informações sempre serão removidas antes de as informações de representação serem armazenadas nesse arquivo.</span><span class="sxs-lookup"><span data-stu-id="38840-115">If a user account and password is specified, this information is always removed before the impersonation information is stored in this file.</span></span> <span data-ttu-id="38840-116">Porém, se o Assistente para Implantação estiver fazendo a implantação diretamente em uma instância do Analysis Services, você poderá adicionar as informações adequadas de ID de usuário e senha ao assistente para habilitar um processamento bem-sucedido do banco de dados de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="38840-116">However, if the Deployment Wizard is deploying directly to an Analysis Services instance, you can add the appropriate user id and password information within the wizard to enable a successful processing of the deployment database.</span></span> <span data-ttu-id="38840-117">Essas informações de representação não serão armazenadas no próprio script de implantação se alguma for salva pelo Assistente para Implantação.</span><span class="sxs-lookup"><span data-stu-id="38840-117">This impersonation information will not be stored in the deployment script itself if one is saved by the Deployment Wizard.</span></span>  
  
-   <span data-ttu-id="38840-118">**Arquivos de log de erros de chave** Essa configuração especifica o nome e o caminho do arquivo de log de erros de chave para cada cubo, grupo de medidas, partição e dimensão do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="38840-118">**Key Error Log Files** This setting specifies the file name and path of the key error log file for each cube, measure group, partition, and dimension in the database.</span></span>  
  
-   <span data-ttu-id="38840-119">**Locais de armazenamento** Essa configuração especifica o local de armazenamento para cada cubo, grupo de medidas e partição do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="38840-119">**Storage Locations** This setting specifies the storage location for each cube, measure group, and partition in the database.</span></span> <span data-ttu-id="38840-120">Se nenhum valor for fornecido para um objeto, o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usará o local padrão do objeto.</span><span class="sxs-lookup"><span data-stu-id="38840-120">If no value is provided for an object, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard uses the default location for the object.</span></span> <span data-ttu-id="38840-121">Por exemplo, as partições usam o local para o grupo de medidas, os grupos de medidas usam o local para o cubo e os cubos usam o local padrão para objetos na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38840-121">For example, partitions use the location for the measure group, measure groups use the location for the cube, and cubes use the default location for objects on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="38840-122">O local de armazenamento pode ser um local ou um caminho UNC (Convenção Universal de Nomenclatura).</span><span class="sxs-lookup"><span data-stu-id="38840-122">The storage location can be a local or a Universal Naming Convention (UNC) path.</span></span>  
  
-   <span data-ttu-id="38840-123">**Servidor de relatório** Esta configuração especifica o servidor de relatório e o local da pasta para cada ação de relatório definida em cada cubo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="38840-123">**Report Server** This setting specifies the report server and folder location for each report action defined in each cube in the database.</span></span>  
  
## <a name="modifying-the-configuration-settings-for-deployment"></a><span data-ttu-id="38840-124">Modificando os parâmetros de configuração para implantação</span><span class="sxs-lookup"><span data-stu-id="38840-124">Modifying the Configuration Settings for Deployment</span></span>  
 <span data-ttu-id="38840-125">Em alguns casos, talvez seja necessário implantar o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto usando definições de configuração diferentes das armazenadas no \<*project name*> arquivo. configsettings.</span><span class="sxs-lookup"><span data-stu-id="38840-125">In some cases, you may need to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different configuration settings than those stored in the \<*project name*>.configsettings file.</span></span> <span data-ttu-id="38840-126">Por exemplo, convém alterar a cadeia de caracteres para uma ou mais fontes de dados ou especificar locais de armazenamento para partições ou grupos de medidas específicos.</span><span class="sxs-lookup"><span data-stu-id="38840-126">For example, you may want to change the connection string to one or more data sources, or specify storage locations for specific partitions or measure groups.</span></span>  
  
 <span data-ttu-id="38840-127">Para modificar a implantação de partições e funções em um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projeto do, você deve alterar essas informações no \<*project name*> arquivo. configsettings, conforme descrito no procedimento abaixo.</span><span class="sxs-lookup"><span data-stu-id="38840-127">To modify the deployment of partitions and roles in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you must change this information within the \<*project name*>.configsettings file, as described in the procedure below.</span></span> <span data-ttu-id="38840-128">Você não pode alterar as configurações de partição e de funções no projeto porque a *\<project name>* caixa de diálogo **páginas de propriedades** no não [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] exibe essas opções.</span><span class="sxs-lookup"><span data-stu-id="38840-128">You cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] does not display these options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38840-129">Os parâmetros de configuração podem se aplicar a todos os objetos ou só aos objetos recentemente criados.</span><span class="sxs-lookup"><span data-stu-id="38840-129">Configuration settings can apply to all objects or only to newly created objects.</span></span> <span data-ttu-id="38840-130">Aplique os parâmetros de configuração a objetos recém-criados apenas quando estiver implantando objetos adicionais em um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] anteriormente implantado e não quiser substituir os objetos existentes.</span><span class="sxs-lookup"><span data-stu-id="38840-130">Apply configuration settings to newly created objects only when you are deploying additional objects to a previously deployed [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and do not want to overwrite existing objects.</span></span> <span data-ttu-id="38840-131">Para especificar se as definições de configuração se aplicam a todos os objetos ou apenas aos recém-criados, defina essa opção no \<*project name*> arquivo. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="38840-131">To specify whether configuration settings apply to all objects or only to newly created ones, set this option in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="38840-132">Para obter mais informações, consulte [Especificando opções de implantação de função e de partição](deployment-script-files-partition-and-role-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="38840-132">For more information, see [Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md).</span></span>  
  
#### <a name="to-change-configuration-settings-after-the-input-files-have-been-generated"></a><span data-ttu-id="38840-133">Para alterar os parâmetros de configuração depois que os arquivos de entrada tiverem sido gerados</span><span class="sxs-lookup"><span data-stu-id="38840-133">To change configuration settings after the input files have been generated</span></span>  
  
-   <span data-ttu-id="38840-134">Execute o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] interativamente, e na página **Parâmetros de Configuração** , especifique o parâmetro de configuração para os objetos que estão sendo implantados.</span><span class="sxs-lookup"><span data-stu-id="38840-134">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively, and on the **Configuration Settings** page, specify the configuration setting for the objects being deployed.</span></span>  
  
     <span data-ttu-id="38840-135">- ou -</span><span class="sxs-lookup"><span data-stu-id="38840-135">-or-</span></span>  
  
-   <span data-ttu-id="38840-136">Execute o Assistente para Implantação do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no prompt de comando e defina o assistente para executar em modo de arquivo de resposta.</span><span class="sxs-lookup"><span data-stu-id="38840-136">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="38840-137">Para obter mais informações sobre o modo de arquivo de resposta, consulte [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="38840-137">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="38840-138">- ou -</span><span class="sxs-lookup"><span data-stu-id="38840-138">-or-</span></span>  
  
-   <span data-ttu-id="38840-139">Modifique o \<*project name*> arquivo. configsettings usando qualquer editor de texto.</span><span class="sxs-lookup"><span data-stu-id="38840-139">Modify the \<*project name*>.configsettings file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38840-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38840-140">See Also</span></span>  
 <span data-ttu-id="38840-141">[Especificando o destino de instalação](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="38840-141">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="38840-142">[Especificando opções de implantação de partição e função](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="38840-142">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 [<span data-ttu-id="38840-143">Especificando opções de processamento</span><span class="sxs-lookup"><span data-stu-id="38840-143">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  