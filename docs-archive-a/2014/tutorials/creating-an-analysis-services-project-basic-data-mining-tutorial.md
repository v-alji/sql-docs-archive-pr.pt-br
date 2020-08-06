---
title: Criando um projeto de Analysis Services (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 784c0401-0358-4117-9c85-4e8220ce71d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 83eb808bc7d18ebe715d309d9f911c010ee172d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569777"
---
# <a name="creating-an-analysis-services-project-basic-data-mining-tutorial"></a><span data-ttu-id="c3d31-102">Criando um projeto do Analysis Services (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="c3d31-102">Creating an Analysis Services Project (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="c3d31-103">Cada [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projeto define os objetos em um único [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c3d31-103">Each [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project defines the objects in a single [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="c3d31-104">Um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] pode conter muitos tipos diferentes de objetos</span><span class="sxs-lookup"><span data-stu-id="c3d31-104">An [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database can contains many different types of objects</span></span>  
  
-   <span data-ttu-id="c3d31-105">Modelos multidimensionais (cubos)</span><span class="sxs-lookup"><span data-stu-id="c3d31-105">Multidimensional models (cubes)</span></span>  
  
-   <span data-ttu-id="c3d31-106">Estruturas de mineração e modelos de mineração</span><span class="sxs-lookup"><span data-stu-id="c3d31-106">Mining structures and mining models</span></span>  
  
-   <span data-ttu-id="c3d31-107">Suporte a objetos como fontes de dados, exibições de fonte de dados, e assemblies personalizados</span><span class="sxs-lookup"><span data-stu-id="c3d31-107">Supporting objects such as data sources, data source views, and custom assemblies</span></span>  
  
 <span data-ttu-id="c3d31-108">Observe que você **não** requer um cubo para executar a mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="c3d31-108">Note that you **do not** require a cube to do data mining.</span></span> <span data-ttu-id="c3d31-109">Se você precisar executar a mineração de dados em um cubo existente, deverá adicionar os modelos de mineração de dados ao mesmo projeto usado para criar o cubo.</span><span class="sxs-lookup"><span data-stu-id="c3d31-109">If you need to perform data mining on an existing cube, you should add the data mining models to the same project you used to build the cube.</span></span> <span data-ttu-id="c3d31-110">No entanto, para a maioria dos propósitos, você poderá criar seus modelos em fontes de dados relacionais, como um data warehouse, e obter o melhor desempenho se um cubo não estiver envolvido.</span><span class="sxs-lookup"><span data-stu-id="c3d31-110">However, for most purposes you can build your models on relational data sources, such as a data warehouse, and get better performance if a cube is not involved.</span></span>  
  
 <span data-ttu-id="c3d31-111">Neste tutorial você usará um data warehouse relacional, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], como a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c3d31-111">In this tutorial you will use a relational data warehouse, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], as the data source.</span></span> <span data-ttu-id="c3d31-112">Você implantará todos os seus objetos de mineração de dados em um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] chamado `BasicDataMining`, usado apenas para mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="c3d31-112">You will deploy all your data mining objects to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database named `BasicDataMining`, used just for data mining.</span></span>  
  
 <span data-ttu-id="c3d31-113">Por padrão, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usa a instância **localhost** para novos projetos.</span><span class="sxs-lookup"><span data-stu-id="c3d31-113">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses the **localhost** instance for new projects.</span></span> <span data-ttu-id="c3d31-114">Se você estiver usando uma instância nomeada ou um servidor diferente, primeiro crie e abra o projeto e depois altere o nome da instância.</span><span class="sxs-lookup"><span data-stu-id="c3d31-114">If you are using a named instance or a different server, you must first create and open the project and then change the instance name.</span></span>  
  
 <span data-ttu-id="c3d31-115">Para obter mais informações sobre projetos do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , consulte [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span><span class="sxs-lookup"><span data-stu-id="c3d31-115">For more information about [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects, see [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span></span>  
  
### <a name="to-create-an-analysis-services-project"></a><span data-ttu-id="c3d31-116">Para criar um Projeto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c3d31-116">To create an Analysis Services project</span></span>  
  
1.  <span data-ttu-id="c3d31-117">Abra o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3d31-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3d31-118">No menu **Arquivo** , aponte para **Novo**e selecione **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="c3d31-118">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
3.  <span data-ttu-id="c3d31-119">Verifique se **Projetos do Business Intelligence** está selecionado no painel **Tipos de projeto** .</span><span class="sxs-lookup"><span data-stu-id="c3d31-119">Verify that **Business Intelligence Projects** is selected in the **Project types** pane.</span></span>  
  
4.  <span data-ttu-id="c3d31-120">No painel **Modelos** , selecione **Projeto Multidimensional e de Mineração de Dados do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="c3d31-120">In the **Templates** pane, select **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
5.  <span data-ttu-id="c3d31-121">Na caixa **nome** , nomeie o novo projeto `BasicDataMining` .</span><span class="sxs-lookup"><span data-stu-id="c3d31-121">In the **Name** box, name the new project `BasicDataMining`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-change-the-instance-where-data-mining-objects-are-stored"></a><span data-ttu-id="c3d31-122">Para alterar a instância em que os objetos de mineração de dados estão armazenados</span><span class="sxs-lookup"><span data-stu-id="c3d31-122">To change the instance where data mining objects are stored</span></span>  
  
1.  <span data-ttu-id="c3d31-123">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], no menu **Projeto** , selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c3d31-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Project** menu, select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c3d31-124">No lado esquerdo do painel **Páginas de Propriedades** , sob **Propriedades de Configuração**, clique em **Implantação**.</span><span class="sxs-lookup"><span data-stu-id="c3d31-124">On the left side of the **Property Pages** pane, under **Configuration Properties**, click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="c3d31-125">No lado direito do painel **Páginas de Propriedades** , sob **Destino**, verifique se o nome de **Servidor** é **localhost**.</span><span class="sxs-lookup"><span data-stu-id="c3d31-125">On the right side of the **Property Pages** pane, under **Target**, verify that the **Server** name is **localhost**.</span></span> <span data-ttu-id="c3d31-126">Se você estiver usando uma instância diferente, digite o nome dessa instância.</span><span class="sxs-lookup"><span data-stu-id="c3d31-126">If you are using a different instance, type the name of the instance.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c3d31-127">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="c3d31-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c3d31-128">Criando uma fonte de dados &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="c3d31-128">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3d31-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3d31-129">See Also</span></span>  
 <span data-ttu-id="c3d31-130">[Compilar projetos de Analysis Services &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="c3d31-130">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="c3d31-131">Criar um projeto do Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="c3d31-131">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/create-an-analysis-services-project-ssdt)  
  
  
