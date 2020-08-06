---
title: Assistente de implantação do Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.deploymentwizard.f1
ms.assetid: f3d93e13-2d85-47ff-a913-cda4046491c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9afdc529baa4546f126eb67456927e770cb345dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683610"
---
# <a name="integration-services-deployment-wizard"></a><span data-ttu-id="e5de8-102">Assistente de Implantação do Integration Services</span><span class="sxs-lookup"><span data-stu-id="e5de8-102">Integration Services Deployment Wizard</span></span>
  <span data-ttu-id="e5de8-103">O Assistente de Implantação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] implanta projetos no catálogo SSISDB em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usando o modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="e5de8-103">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard deploys projects to the SSISDB catalog on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance using the project deployment model.</span></span>  
  
 <span data-ttu-id="e5de8-104">Para iniciar o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Assistente de implantação em um projeto aberto no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , selecione **implantar** no menu **projeto** .</span><span class="sxs-lookup"><span data-stu-id="e5de8-104">To start the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard from an open project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], select **Deploy** from the **Project** menu.</span></span> <span data-ttu-id="e5de8-105">Para iniciar o assistente no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , expanda o nó **Integration Services catálogos**  >  **SSISDB** no Pesquisador de objetos, clique com o botão direito do mouse na pasta **projetos** e clique em **implantar projeto**.</span><span class="sxs-lookup"><span data-stu-id="e5de8-105">To start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** > **SSISDB** node in Object Explorer, right-click the **Projects** folder, and then click **Deploy Project**.</span></span>  
  
 <span data-ttu-id="e5de8-106">O assistente prossegue nas quatro etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e5de8-106">The wizard proceeds through the following four steps.</span></span> <span data-ttu-id="e5de8-107">Clique em **Avançar** para ir para a próxima etapa ou **anterior** para retornar à etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e5de8-107">Click **Next** to move to the next step, or **Previous** to return to the previous step.</span></span>  
  
1.  <span data-ttu-id="e5de8-108">**Selecionar origem** – selecione o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projeto que você deseja implantar.</span><span class="sxs-lookup"><span data-stu-id="e5de8-108">**Select Source** - Select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that you want to deploy.</span></span>  
  
2.  <span data-ttu-id="e5de8-109">**Selecione destino** -selecione o destino do projeto.</span><span class="sxs-lookup"><span data-stu-id="e5de8-109">**Select Destination** - Select the project destination.</span></span>  
  
3.  <span data-ttu-id="e5de8-110">**Revisão** – exibe suas seleções.</span><span class="sxs-lookup"><span data-stu-id="e5de8-110">**Review** - Displays your selections.</span></span>  
  
4.  <span data-ttu-id="e5de8-111">**Implantar/resultados** – implanta o projeto e exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="e5de8-111">**Deploy/Results** - Deploys the project and displays the results.</span></span>  
  
## <a name="select-source"></a><span data-ttu-id="e5de8-112">Selecionar fonte</span><span class="sxs-lookup"><span data-stu-id="e5de8-112">Select Source</span></span>  
 <span data-ttu-id="e5de8-113">Para implantar um arquivo de implantação de projeto que você criou, selecione **arquivo de implantação do projeto** e insira o caminho para o arquivo. ispac ou clique em **procurar** para localizá-lo na [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pasta do projeto.</span><span class="sxs-lookup"><span data-stu-id="e5de8-113">To deploy a project deployment file that you created, select **Project deployment file** and enter the path to the .ispac file or click **Browse** to find it in the [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project folder.</span></span> <span data-ttu-id="e5de8-114">Para implantar um projeto residente no catálogo [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , selecione **Catálogo do Integration Services**e insira o nome do servidor e o caminho para o projeto no catálogo.</span><span class="sxs-lookup"><span data-stu-id="e5de8-114">To deploy a project that resides in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, select **Integration Services catalog**, and then enter the server name and the path to the project in the catalog.</span></span>  
  
 <span data-ttu-id="e5de8-115">Se você iniciar o assistente no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], então por padrão o assistente selecionará o projeto aberto como a origem e ignorará esta etapa.</span><span class="sxs-lookup"><span data-stu-id="e5de8-115">If you start the wizard in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], then by default the wizard selects the open project as the source and skips this step.</span></span> <span data-ttu-id="e5de8-116">Para retornar a esta etapa e selecionar uma fonte diferente, clique em **anterior** ou clique em **selecionar origem** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="e5de8-116">To return to this step and select a different source, click **Previous** or click **Select Source** in the left pane.</span></span>  
  
## <a name="select-destination"></a><span data-ttu-id="e5de8-117">Selecionar Destino</span><span class="sxs-lookup"><span data-stu-id="e5de8-117">Select Destination</span></span>  
 <span data-ttu-id="e5de8-118">Para selecionar a pasta de destino para o projeto no catálogo [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , insira a instância [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou clique em **Procurar** para selecionar de uma lista de servidores.</span><span class="sxs-lookup"><span data-stu-id="e5de8-118">To select the destination folder for the project in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, enter the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance or click **Browse** to select from a list of servers.</span></span> <span data-ttu-id="e5de8-119">Digite o caminho do projeto no SSISDB ou clique em **Procurar** para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="e5de8-119">Enter the project path in SSISDB or click **Browse** to select it.</span></span>  
  
 <span data-ttu-id="e5de8-120">Se você iniciar o assistente no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], então por padrão o assistente selecionará a instância de servidor conectada e inserirá o caminho para o projeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="e5de8-120">If you start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], then by default the wizard selects the connected server instance and enters the path to the selected project.</span></span> <span data-ttu-id="e5de8-121">Você pode alterar estes valores para implantar o projeto em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="e5de8-121">You can change these values to deploy the project to a different location.</span></span>  
  
## <a name="review"></a><span data-ttu-id="e5de8-122">Revisão</span><span class="sxs-lookup"><span data-stu-id="e5de8-122">Review</span></span>  
 <span data-ttu-id="e5de8-123">O assistente permite que você examine as configurações selecionadas antes da implantação do projeto.</span><span class="sxs-lookup"><span data-stu-id="e5de8-123">The wizard allows you to review the settings you have selected before deploying the project.</span></span> <span data-ttu-id="e5de8-124">Você pode alterar suas seleções clicando em **Anterior**ou clicando em qualquer uma das etapas no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="e5de8-124">You can change your selections by clicking **Previous**, or by clicking any of the steps in the left pane.</span></span>  
  
## <a name="deployresults"></a><span data-ttu-id="e5de8-125">Implantar/Resultados</span><span class="sxs-lookup"><span data-stu-id="e5de8-125">Deploy/Results</span></span>  
 <span data-ttu-id="e5de8-126">Quando você clica em **implantar** na página **revisão** , o projeto é implantado e a página **resultados** exibe o êxito ou a falha de cada ação.</span><span class="sxs-lookup"><span data-stu-id="e5de8-126">When you click **Deploy** from the **Review** page, the project is deployed and the **Results** page displays the success or failure of each action.</span></span> <span data-ttu-id="e5de8-127">Se a ação falhar, clique em **Com falha** na coluna **Resultado** para exibir uma explicação do erro.</span><span class="sxs-lookup"><span data-stu-id="e5de8-127">If the action fails, click the **Failed** in the **Result** column to display an explanation of the error.</span></span> <span data-ttu-id="e5de8-128">Clique em **Salvar relatório...** para salvar os resultados em um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="e5de8-128">Click **Save Report...** to save the results to an XML file.</span></span>  
  
 <span data-ttu-id="e5de8-129">Clique em **Fechar** para sair do assistente.</span><span class="sxs-lookup"><span data-stu-id="e5de8-129">Click **Close** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5de8-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5de8-130">See Also</span></span>  
 <span data-ttu-id="e5de8-131">[Implantar projetos no Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="e5de8-131">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 [<span data-ttu-id="e5de8-132">Implantação de projetos e pacotes</span><span class="sxs-lookup"><span data-stu-id="e5de8-132">Deployment of Projects and Packages</span></span>](packages/deploy-integration-services-ssis-projects-and-packages.md)  
  
  
