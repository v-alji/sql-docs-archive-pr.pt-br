---
title: Implantar pacotes usando o utilitário de implantação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], installing
- installing packages
- dependencies [Integration Services]
- deploying packages [Integration Services], installing
ms.assetid: eaf4b56e-2023-4d17-971c-703031da758c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a09ad307dc0215fca679cfb1ef5a37031f951caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681811"
---
# <a name="deploy-packages-by-using-the-deployment-utility"></a><span data-ttu-id="b0b87-102">Implantar pacotes usando o utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="b0b87-102">Deploy Packages by Using the Deployment Utility</span></span>
  <span data-ttu-id="b0b87-103">Quando você cria um utilitário de implantação para instalar pacotes de um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] em um computador diferente daquele em que o utilitário de implantação foi criado, é necessário primeiro copiar a pasta de implantação no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="b0b87-103">When you have built a deployment utility to install packages from an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project on a different computer than the one on which the deployment utility was built, you must first copy the deployment folder to the destination computer.</span></span>  
  
 <span data-ttu-id="b0b87-104">O caminho da pasta de implantação está especificado na propriedade DeploymentOutputPath do projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para o qual foi criado o utilitário de implantação.</span><span class="sxs-lookup"><span data-stu-id="b0b87-104">The path of the deployment folder is specified in the DeploymentOutputPath property of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you created the deployment utility.</span></span> <span data-ttu-id="b0b87-105">O caminho padrão é bin\Deployment, relativo ao projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0b87-105">The default path is bin\Deployment, relative to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="b0b87-106">Para obter mais informações, consulte [Criar um utilitário de implantação](../../2014/integration-services/create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b0b87-106">For more information, see [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="b0b87-107">É possível usar o Assistente de Instalação de Pacotes para instalar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="b0b87-107">You use the Package Installation Wizard to install the packages.</span></span> <span data-ttu-id="b0b87-108">Para iniciar o assistente, clique duas vezes no arquivo do utilitário de implantação depois de ter copiado a pasta de implantação no servidor.</span><span class="sxs-lookup"><span data-stu-id="b0b87-108">To launch the wizard, double-click the deployment utility file after you have copied the deployment folder to the server.</span></span> <span data-ttu-id="b0b87-109">Esse arquivo é chamado \<project name>.SSISDeploymentManifest e pode ser encontrado na pasta de implantação do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="b0b87-109">This file is named \<project name>.SSISDeploymentManifest, and can be found in the deployment folder on the destination computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0b87-110">Dependendo da versão do pacote que está sendo implantado, você poderá encontrar um erro se tiver diferentes versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instaladas lado a lado.</span><span class="sxs-lookup"><span data-stu-id="b0b87-110">Depending on the version of the package that you are deploying, you might encounter an error if you have different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installed side-by-side.</span></span> <span data-ttu-id="b0b87-111">Esse erro pode ocorrer porque a extensão do nome de arquivo .SSISDeploymentManifest é a mesma para todas as versões do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0b87-111">This error can occur because the .SSISDeploymentManifest file name extension is the same for all versions of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="b0b87-112">Clicar duas vezes no arquivo chama o instalador (dtsinstall.exe) da versão instalada mais recentemente do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], que talvez não seja a mesma versão do arquivo de utilitário de implantação.</span><span class="sxs-lookup"><span data-stu-id="b0b87-112">Double-clicking the file calls the installer (dtsinstall.exe) for the most recently installed version of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], which might not be the same version as the deployment utility file.</span></span> <span data-ttu-id="b0b87-113">Para resolver esse problema, execute a versão correta de dtsinstall.exe na linha de comando e forneça o caminho do arquivo de utilitário de implantação.</span><span class="sxs-lookup"><span data-stu-id="b0b87-113">To work around this problem, run the correct version of dtsinstall.exe from the command line, and provide the path of the deployment utility file.</span></span>  
  
 <span data-ttu-id="b0b87-114">O Assistente de Instalação de Pacotes o guiará pelas etapas para instalar pacotes no sistema de arquivos ou no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0b87-114">The Package Installation Wizard guides you through the steps to install packages to the file system or to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b0b87-115">Você pode configurar a instalação das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="b0b87-115">You can configure the installation in the following ways:</span></span>  
  
-   <span data-ttu-id="b0b87-116">Escolhendo o local e o tipo de local para instalar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="b0b87-116">Choosing the location type and location to install the packages.</span></span>  
  
-   <span data-ttu-id="b0b87-117">Escolhendo o local para instalar dependências dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="b0b87-117">Choosing location to install package dependencies.</span></span>  
  
-   <span data-ttu-id="b0b87-118">Validando os pacotes após a instalação no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="b0b87-118">Validating the packages after they are installed on the target server.</span></span>  
  
 <span data-ttu-id="b0b87-119">As dependências com base em arquivo para pacotes sempre são instaladas no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b0b87-119">The file-based dependencies for packages are always installed to the file system.</span></span> <span data-ttu-id="b0b87-120">Se for instalado um pacote no sistema de arquivos, as dependências serão instaladas na mesma pasta especificada por você para o pacote.</span><span class="sxs-lookup"><span data-stu-id="b0b87-120">If you install a package to the file system, the dependencies are installed in the same folder as the one that you specify for the package.</span></span> <span data-ttu-id="b0b87-121">Se instalar um pacote em [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], você poderá especificar a pasta na qual armazenará as dependências com base no arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0b87-121">If you install a package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify the folder in which to store the file-based dependencies.</span></span>  
  
 <span data-ttu-id="b0b87-122">Se o pacote incluir configurações que deseja modificar para usar no computador destino, você poderá atualizar os valores e as propriedades usando o assistente.</span><span class="sxs-lookup"><span data-stu-id="b0b87-122">If the package includes configurations that you want to modify for use on the destination computer, you can update the values of the properties by using the wizard.</span></span>  
  
 <span data-ttu-id="b0b87-123">Além de instalar os pacotes com o Assistente de Instalação de Pacotes, você pode copiar e mover pacotes com o utilitário de prompt de comando **dtutil** .</span><span class="sxs-lookup"><span data-stu-id="b0b87-123">In addition to installing packages by using the Package Installation Wizard, you can copy and move packages by using the **dtutil** command prompt utility.</span></span> <span data-ttu-id="b0b87-124">Para obter mais informações, consulte [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b0b87-124">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-deploy-packages-to-an-instance-of-sql-server"></a><span data-ttu-id="b0b87-125">Para implantar pacotes em uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b0b87-125">To deploy packages to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="b0b87-126">Abra a pasta de implantação no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="b0b87-126">Open the deployment folder on the target computer.</span></span>  
  
2.  <span data-ttu-id="b0b87-127">Clique duas vezes no arquivo de manifesto, \<project name>.SSISDeploymentManifest, para iniciar o Assistente de Instalação de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="b0b87-127">Double-click the manifest file, \<project name>.SSISDeploymentManifest, to start the Package Installation Wizard.</span></span>  
  
3.  <span data-ttu-id="b0b87-128">Na página **Implantar Pacotes SSIS** , selecione a opção **Implantação no SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="b0b87-128">On the **Deploy SSIS Packages** page, select the **SQL Server deployment** option.</span></span>  
  
4.  <span data-ttu-id="b0b87-129">Opcionalmente, selecione **Validar pacotes após instalação** para validar os pacotes depois de instalados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="b0b87-129">Optionally, select **Validate packages after installation** to validate packages after they are installed on the target server.</span></span>  
  
5.  <span data-ttu-id="b0b87-130">Na página **Especificar SQL Server de Destino** , especifique a instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para instalar os pacotes e selecionar um modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="b0b87-130">On the **Specify Target SQL Server** page, specify the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to install the packages to and select an authentication mode.</span></span> <span data-ttu-id="b0b87-131">Se você selecionar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , precisará fornecer um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="b0b87-131">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and a password.</span></span>  
  
6.  <span data-ttu-id="b0b87-132">Na página **Selecionar Pasta de Instalação** , especifique a pasta no sistema de arquivos para as dependências do pacote que serão instaladas.</span><span class="sxs-lookup"><span data-stu-id="b0b87-132">On the **Select Installation Folder** page, specify the folder in the file system for the package dependencies that will be installed.</span></span>  
  
7.  <span data-ttu-id="b0b87-133">Se o pacote incluir configurações, você poderá editar as configurações atualizando os valores na lista **Valor** da página Configurar Pacotes.</span><span class="sxs-lookup"><span data-stu-id="b0b87-133">If the package includes configurations, you can edit configurations by updating values in the **Value** list on the Configure Packages page.</span></span>  
  
8.  <span data-ttu-id="b0b87-134">Se você escolheu validar os pacotes após a instalação, exiba os resultados de validação dos pacotes implantados.</span><span class="sxs-lookup"><span data-stu-id="b0b87-134">If you elected to validate packages after installation, view the validation results of the deployed packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b87-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0b87-135">See Also</span></span>  
 [<span data-ttu-id="b0b87-136">Implantação de pacote &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b0b87-136">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
