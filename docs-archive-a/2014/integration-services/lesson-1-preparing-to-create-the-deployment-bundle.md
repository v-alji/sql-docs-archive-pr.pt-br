---
title: 'Lição 1: preparando-se para criar o pacote de implantação | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6fe283c-9856-4ba1-a497-e3912424fd18
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0deda2a81ddd86d4e40c1c546232b8056264508a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574122"
---
# <a name="lesson-1-preparing-to-create-the-deployment-bundle"></a><span data-ttu-id="9d2e8-102">Lição 1: Preparando-se para criar o pacote de implantação</span><span class="sxs-lookup"><span data-stu-id="9d2e8-102">Lesson 1: Preparing to Create the Deployment Bundle</span></span>
  <span data-ttu-id="9d2e8-103">Nesta lição, você criará as pastas de trabalho e as variáveis de ambiente que oferecem suporte ao tutorial, criará um projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , adicionará vários pacotes e seus arquivos de suporte ao projeto e implementará configurações em pacotes.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-103">In this lesson, you will create the working folders and environment variables that support the tutorial, create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add several packages and their supporting files to the project, and implement configurations in packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="9d2e8-104">implanta pacotes em uma base de projeto; portanto, como a primeira etapa na criação do pacote de implantação, você deve coletar todos os pacotes e dependências de pacotes em um único projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d2e8-104">deploys packages on a project basis; therefore, as the first step in creating the deployment bundle, you must collect all the packages and package dependencies into one [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="9d2e8-105">Normalmente é útil incluir outras informações com os pacotes implantados: por exemplo, você também adicionará ao projeto um arquivo Leiame, que fornece a documentação básica para esse grupo de pacotes.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-105">Frequently it is useful to include other information with the deployed packages: for example you will also add to the project a Readme file that provides basic documentation for this group of packages.</span></span>  
  
 <span data-ttu-id="9d2e8-106">Depois que você adicionar os pacotes e os arquivos, adicionará configurações aos pacotes que ainda não usam as configurações.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-106">After you have added the packages and files, you will add configurations to packages that do not already use configurations.</span></span> <span data-ttu-id="9d2e8-107">As configurações atualizam as propriedades dos pacotes e os objetos do pacote em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-107">The configurations update properties of packages and package objects at run time.</span></span> <span data-ttu-id="9d2e8-108">Em uma lição posterior, você modificará os valores dessas configurações durante a implantação de pacotes para oferecer suporte aos pacotes no ambiente implantado.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-108">In a later lesson, you will modify the values of these configurations during package deployment to support the packages in the deployed-to environment.</span></span>  
  
 <span data-ttu-id="9d2e8-109">Depois que você adicionar as configurações, deverá abrir os pacotes no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , a ferramenta gráfica do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para compilação de pacotes ETL, e examinar as propriedades e os elementos do pacote, assim como as configurações de pacote, para entender melhor os problemas que a implantação precisa resolver.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-109">After you have added the configurations, you should open the packages in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] graphical tool for building ETL packages, and examine the properties of packages and package elements as well as the package configurations to better understand the issues that the deployment needs to address.</span></span> <span data-ttu-id="9d2e8-110">Por exemplo, um dos pacotes extrai dados de arquivos de texto, portanto, o local dos arquivos de dados deve ser atualizado antes dos pacotes serem implantados com êxito.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-110">For example, one of the packages extracts data from text files, so the location of the data files must be updated before the deployed packages will run successfully.</span></span>  
  
 <span data-ttu-id="9d2e8-111">**Tempo estimado para concluir esta lição:** 1 hora</span><span class="sxs-lookup"><span data-stu-id="9d2e8-111">**Estimated time to complete this lesson:** 1 hour</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9d2e8-112">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="9d2e8-112">Lesson Tasks</span></span>  
 <span data-ttu-id="9d2e8-113">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9d2e8-113">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="9d2e8-114">Etapa 1: Criando pastas de trabalho e variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="9d2e8-114">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
-   [<span data-ttu-id="9d2e8-115">Etapa 2: Criando o projeto de implantação</span><span class="sxs-lookup"><span data-stu-id="9d2e8-115">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
-   [<span data-ttu-id="9d2e8-116">Etapa 3: Adicionando pacotes e outros arquivos</span><span class="sxs-lookup"><span data-stu-id="9d2e8-116">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
-   [<span data-ttu-id="9d2e8-117">Etapa 4: Adicionando configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="9d2e8-117">Step 4: Adding Package Configurations</span></span>](../integration-services/lesson-1-4-adding-package-configurations.md)  
  
-   [<span data-ttu-id="9d2e8-118">Etapa 5: Testando os pacotes atualizados</span><span class="sxs-lookup"><span data-stu-id="9d2e8-118">Step 5: Testing the Updated Packages</span></span>](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="9d2e8-119">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="9d2e8-119">Start the Lesson</span></span>  
 [<span data-ttu-id="9d2e8-120">Etapa 1: Criando pastas de trabalho e variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="9d2e8-120">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
<span data-ttu-id="9d2e8-121">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9d2e8-121">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9d2e8-122">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="9d2e8-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9d2e8-123">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="9d2e8-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9d2e8-124">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
