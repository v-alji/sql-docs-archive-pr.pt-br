---
title: Executar um pacote no SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, running
- SSIS packages, running
- packages [Integration Services], running
- SQL Server Integration Services packages, running
ms.assetid: 318e6beb-5540-4101-82a5-18c9d47f0570
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31ca2390ef6bb04b63e4de9978193aed8884da36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679396"
---
# <a name="run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="17aee-102">Executar um pacote no SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="17aee-102">Run a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="17aee-103">Normalmente, os pacotes são executados no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] durante o desenvolvimento, a depuração e o teste dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="17aee-103">You typically run packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] during the development, debugging, and testing of packages.</span></span> <span data-ttu-id="17aee-104">Quando você executa um pacote no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , o pacote é sempre executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="17aee-104">When you run a package from [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the package always runs immediately.</span></span>  
  
 <span data-ttu-id="17aee-105">Enquanto um pacote estiver sendo executado, o Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] exibe o andamento da execução do pacote na guia **Progresso** . Você pode exibir a hora de início e do fim do pacote e suas tarefas e contêineres, além de informações sobre quaisquer tarefas ou contêineres no pacote em que houve falha.</span><span class="sxs-lookup"><span data-stu-id="17aee-105">While a package is running, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer displays the progress of package execution on the **Progress** tab. You can view the start and finish time of the package and its tasks and containers, in addition to information about any tasks or containers in the package that failed.</span></span> <span data-ttu-id="17aee-106">Depois que o pacote concluir a execução, as informações em tempo de execução continuarão disponíveis na guia **Resultados da Execução** . Para obter mais informações, consulte a seção "Relatório de progresso", no tópico [Depuração do fluxo de controle](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="17aee-106">After the package finishes running, the run-time information remains available on the **Execution Results** tab. For more information, see the section, "Progress Reporting," in the topic, [Debugging Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="17aee-107">**Implantação de tempo de design**.</span><span class="sxs-lookup"><span data-stu-id="17aee-107">**Design-time deployment**.</span></span> <span data-ttu-id="17aee-108">Quando um pacote é executado no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ele é criado e, em seguida, implantado em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="17aee-108">When you run a package in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the package is built and then deployed to a folder.</span></span> <span data-ttu-id="17aee-109">Antes de executar o pacote, você pode especificar a pasta na qual ele será implantado.</span><span class="sxs-lookup"><span data-stu-id="17aee-109">Before you run the package, you can specify the folder to which the package is deployed.</span></span> <span data-ttu-id="17aee-110">Por padrão, se você não especificar uma pasta, a pasta **bin** será usada.</span><span class="sxs-lookup"><span data-stu-id="17aee-110">If you do not specify a folder, the **bin** folder is used by default.</span></span> <span data-ttu-id="17aee-111">Este tipo de implantação é chamado de implantação de tempo de design.</span><span class="sxs-lookup"><span data-stu-id="17aee-111">This type of deployment is called design-time deployment.</span></span>  
  
### <a name="to-run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="17aee-112">Para executar um pacote nas Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="17aee-112">To run a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="17aee-113">No Gerenciador de Soluções, se sua solução contiver vários projetos, clique com o botão direito do mouse no projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote e clique em **Definir como Objeto de Inicialização** para definir o projeto de inicialização.</span><span class="sxs-lookup"><span data-stu-id="17aee-113">In Solution Explorer, if your solution contains multiple projects, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package, and then click **Set as StartUp Object** to set the startup project.</span></span>  
  
2.  <span data-ttu-id="17aee-114">No Gerenciador de Soluções, se o projeto contiver vários pacotes, clique com o botão direito do mouse em um pacote e clique em **Definir como Objeto de Inicialização** para definir o pacote de inicialização.</span><span class="sxs-lookup"><span data-stu-id="17aee-114">In Solution Explorer, if your project contains multiple packages, right-click a package, and then click **Set as StartUp Object** to set the startup package.</span></span>  
  
3.  <span data-ttu-id="17aee-115">Para executar um pacote, use um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="17aee-115">To run a package, use one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="17aee-116">Abra o pacote que você deseja executar e clique em **Iniciar Depuração** na barra de menus ou pressione F5.</span><span class="sxs-lookup"><span data-stu-id="17aee-116">Open the package that you want to run and then click **Start Debugging** on the menu bar, or press F5.</span></span> <span data-ttu-id="17aee-117">Após a execução do pacote, pressione Shift+F5 para retornar ao modo de design.</span><span class="sxs-lookup"><span data-stu-id="17aee-117">After the package finishes running, press Shift+F5 to return to design mode.</span></span>  
  
    -   <span data-ttu-id="17aee-118">No Gerenciador de Soluções, clique com o botão direito do mouse no pacote e, em seguida, clique em **Executar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="17aee-118">In Solution Explorer, right-click the package, and then click **Execute Package**.</span></span>  
  
### <a name="to-specify-a-different-folder-for-design-time-deployment"></a><span data-ttu-id="17aee-119">Para especificar uma pasta diferente para implantação em tempo de design</span><span class="sxs-lookup"><span data-stu-id="17aee-119">To specify a different folder for design-time deployment</span></span>  
  
1.  <span data-ttu-id="17aee-120">No Gerenciador de Soluções, clique com o botão direito do mouse na pasta de projetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote que você deseja executar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="17aee-120">In Solution Explorer, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project folder that contains the package you want to run, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="17aee-121">Na caixa de diálogo **Página de Propriedades do \<project name>** , clique em **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="17aee-121">In the **\<project name> Property Pages** dialog box, click **Build**.</span></span>  
  
3.  <span data-ttu-id="17aee-122">Atualize o valor na propriedade OutputPath para especificar a pasta que você deseja usar para a implantação em tempo de design e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="17aee-122">Update the value in the OutputPath property to specify the folder you want to use for design-time deployment, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17aee-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="17aee-123">See Also</span></span>  
 <span data-ttu-id="17aee-124">[Execução de projetos e pacotes](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="17aee-124">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="17aee-125">Pacotes do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="17aee-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
