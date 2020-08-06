---
title: Organizador de configurações de pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.packageconfigurationorganizer.f1
helpviewer_keywords:
- Package Configurations Organizer dialog box
ms.assetid: f20ae6cb-9e6a-4d24-88ff-d7a903a4e8d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fdc9ca0faeff57c18fdb6e4d10acca3e9963f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683595"
---
# <a name="package-configurations-organizer"></a><span data-ttu-id="405c1-102">Organizador de Configurações do Pacote</span><span class="sxs-lookup"><span data-stu-id="405c1-102">Package Configurations Organizer</span></span>
  <span data-ttu-id="405c1-103">Use a caixa de diálogo **Organizador de Configurações do Pacote** para habilitar configurações de pacote, visualizar uma lista de configurações para o pacote atual e para definir a ordem de preferência para carregar as configurações.</span><span class="sxs-lookup"><span data-stu-id="405c1-103">Use the **Package Configurations Organizer** dialog box to enable package configurations, view a list of configurations for the current package, and specify the preferred order in which the configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="405c1-104">As configurações estão disponíveis para o modelo de implantação de pacote.</span><span class="sxs-lookup"><span data-stu-id="405c1-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="405c1-105">Os parâmetros são usados no lugar das configurações para o modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="405c1-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="405c1-106">O modelo de implantação de projeto permite que você implante projetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="405c1-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="405c1-107">Para obter mais informações sobre os modelos de implantação, consulte [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="405c1-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="405c1-108">Se várias configurações atualizarem a mesma propriedade, valores de configurações listadas na parte inferior da lista de configurações substituirão os valores das configurações na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="405c1-108">If multiple configurations update the same property, values from configurations listed lower in the configuration list will replace values from configurations higher in the list.</span></span> <span data-ttu-id="405c1-109">O último valor carregado na propriedade é o valor usado quando o pacote executar.</span><span class="sxs-lookup"><span data-stu-id="405c1-109">The last value loaded into the property is the value that is used when the package runs.</span></span> <span data-ttu-id="405c1-110">Além disso, se o pacote usar uma combinação de configuração direta, como um arquivo de configuração XML, e uma configuração indireta, como uma variável de ambiente, a configuração indireta que aponta para o local da configuração direta deve estar na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="405c1-110">Also, if the package uses a combination of direct configuration such as an XML configuration file and an indirect configuration such as an environment variable, the indirect configuration that points to the location of the direct configuration must be higher in the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="405c1-111">Quando as configurações de pacote são carregadas na ordem preferencial, elas são carregadas da parte superior da lista mostrada na caixa de diálogo **Organizador de Configurações do Pacote** até a parte inferior da lista.</span><span class="sxs-lookup"><span data-stu-id="405c1-111">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="405c1-112">Porém, no tempo de execução, talvez as configurações do pacote não sejam carregadas na ordem preferencial.</span><span class="sxs-lookup"><span data-stu-id="405c1-112">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="405c1-113">Em particular, Configurações do Pacote Pai são carregadas depois das configurações de outros tipos.</span><span class="sxs-lookup"><span data-stu-id="405c1-113">In particular, Parent Package Configurations load after configurations of other types.</span></span>  
  
 <span data-ttu-id="405c1-114">Configurações de Pacote atualizam os valores das propriedades de objetos de pacote em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="405c1-114">Package configurations update the values of properties of package objects at run time.</span></span> <span data-ttu-id="405c1-115">Quando um pacote é carregado, os valores das configurações substituem os valores que foram definidos quando o pacote foi desenvolvido.</span><span class="sxs-lookup"><span data-stu-id="405c1-115">When a package is loaded, the values from the configurations replace the values that were set when the package was developed.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="405c1-116">dá suporte a diferentes tipos de configuração.</span><span class="sxs-lookup"><span data-stu-id="405c1-116">supports different configuration types.</span></span> <span data-ttu-id="405c1-117">Por exemplo, é possível usar um arquivo XML que pode ter várias configurações, ou uma variável de ambiente que contenha uma única configuração.</span><span class="sxs-lookup"><span data-stu-id="405c1-117">For example, you can use an XML file that can contain multiple configurations, or an environment variable that contains a single configuration.</span></span> <span data-ttu-id="405c1-118">Para obter mais informações, consulte [Package Configurations](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="405c1-118">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="405c1-119">Opções</span><span class="sxs-lookup"><span data-stu-id="405c1-119">Options</span></span>  
 <span data-ttu-id="405c1-120">**Habilitar configurações de pacote**</span><span class="sxs-lookup"><span data-stu-id="405c1-120">**Enable package configurations**</span></span>  
 <span data-ttu-id="405c1-121">Selecione para usar configurações com o pacote.</span><span class="sxs-lookup"><span data-stu-id="405c1-121">Select to use configurations with the package.</span></span>  
  
 <span data-ttu-id="405c1-122">**Nome da Configuração**</span><span class="sxs-lookup"><span data-stu-id="405c1-122">**Configuration Name**</span></span>  
 <span data-ttu-id="405c1-123">Exibe o nome da configuração.</span><span class="sxs-lookup"><span data-stu-id="405c1-123">View the name of the configuration.</span></span>  
  
 <span data-ttu-id="405c1-124">**Tipo de Configuração**</span><span class="sxs-lookup"><span data-stu-id="405c1-124">**Configuration Type**</span></span>  
 <span data-ttu-id="405c1-125">Exibe o tipo do local onde as configurações são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="405c1-125">View the type of the location where configurations are stored.</span></span>  
  
 <span data-ttu-id="405c1-126">**Cadeia de Caracteres de Configuração**</span><span class="sxs-lookup"><span data-stu-id="405c1-126">**Configuration String**</span></span>  
 <span data-ttu-id="405c1-127">Exibe o local no qual os valores de configuração são armazenados.</span><span class="sxs-lookup"><span data-stu-id="405c1-127">View the location where the configuration values are stored.</span></span> <span data-ttu-id="405c1-128">O local pode ser um caminho de um arquivo, o nome de uma variável de ambiente, uma chave do Registro, o nome de uma variável do pacote pai ou o nome de uma tabela do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="405c1-128">The location can be the path of a file, the name of an environment variable, the name of a parent package variable, a Registry key, or the name of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="405c1-129">**Objeto de Destino**</span><span class="sxs-lookup"><span data-stu-id="405c1-129">**Target Object**</span></span>  
 <span data-ttu-id="405c1-130">Exibe o nome do objeto atualizado pela configuração.</span><span class="sxs-lookup"><span data-stu-id="405c1-130">View the name of the object that the configuration updates.</span></span> <span data-ttu-id="405c1-131">Se a configuração for um arquivo de configuração XML ou uma tabela do SQL Server, a coluna ficará em branco porque a configuração pode incluir vários objetos.</span><span class="sxs-lookup"><span data-stu-id="405c1-131">If the configuration is an XML configuration file or a SQL Server table, the column is blank because the configuration can include multiple objects.</span></span>  
  
 <span data-ttu-id="405c1-132">**Propriedade de Destino**</span><span class="sxs-lookup"><span data-stu-id="405c1-132">**Target Property**</span></span>  
 <span data-ttu-id="405c1-133">Exibe o nome da propriedade modificada pela configuração.</span><span class="sxs-lookup"><span data-stu-id="405c1-133">View the name of the property modified by the configuration.</span></span> <span data-ttu-id="405c1-134">Esta coluna estará em branco se o tipo de configuração oferecer suporte a várias configurações.</span><span class="sxs-lookup"><span data-stu-id="405c1-134">This column is blank if the configuration type supports multiple configurations.</span></span>  
  
 <span data-ttu-id="405c1-135">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="405c1-135">**Add**</span></span>  
 <span data-ttu-id="405c1-136">Adicione uma configuração usando o Assistente de Configuração do Pacote.</span><span class="sxs-lookup"><span data-stu-id="405c1-136">Add a configuration by using the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="405c1-137">**Editar**</span><span class="sxs-lookup"><span data-stu-id="405c1-137">**Edit**</span></span>  
 <span data-ttu-id="405c1-138">Edite uma configuração existente executando novamente o Assistente de Configuração do Pacote.</span><span class="sxs-lookup"><span data-stu-id="405c1-138">Edit an existing configuration by rerunning the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="405c1-139">**Remover**</span><span class="sxs-lookup"><span data-stu-id="405c1-139">**Remove**</span></span>  
 <span data-ttu-id="405c1-140">Selecione uma configuração e depois clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="405c1-140">Select a configuration, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="405c1-141">**Setas**</span><span class="sxs-lookup"><span data-stu-id="405c1-141">**Arrows**</span></span>  
 <span data-ttu-id="405c1-142">Selecione uma configuração e use as setas para cima e para baixo para movê-la para cima ou para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="405c1-142">Select a configuration and use the up and down arrows to move it up or down in the list.</span></span> <span data-ttu-id="405c1-143">As configurações são carregadas na sequência exibida na lista.</span><span class="sxs-lookup"><span data-stu-id="405c1-143">Configurations are loaded in the sequence in which they appear in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="405c1-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="405c1-144">See Also</span></span>  
 [<span data-ttu-id="405c1-145">Criar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="405c1-145">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
