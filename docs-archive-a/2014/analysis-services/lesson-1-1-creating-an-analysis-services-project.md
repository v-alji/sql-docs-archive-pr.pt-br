---
title: Criando um projeto de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 065fdc60-1791-4e27-9ed5-51d751b3f8c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50640dd7821943dfc3914326f7e8cba32253d307
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568858"
---
# <a name="creating-an-analysis-services-project"></a><span data-ttu-id="a751f-102">Criando um projeto do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a751f-102">Creating an Analysis Services Project</span></span>
  <span data-ttu-id="a751f-103">Na tarefa a seguir, você usa o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para criar um novo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projeto chamado `Analysis Services Tutorial` , com base no modelo de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="a751f-103">In the following task, you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project named `Analysis Services Tutorial`, based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Project template.</span></span> <span data-ttu-id="a751f-104">Um *projeto* é uma coleção de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="a751f-104">A *project* is a collection of related objects.</span></span> <span data-ttu-id="a751f-105">Os projetos existem dentro de uma solução que inclui um ou mais projetos.</span><span class="sxs-lookup"><span data-stu-id="a751f-105">Projects exist within a solution, which includes one or more projects.</span></span> <span data-ttu-id="a751f-106">Para obter mais informações, consulte [Criar um projeto do Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="a751f-106">For more information, see [Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span></span>  
  
### <a name="to-create-a-new-analysis-services-project"></a><span data-ttu-id="a751f-107">Para criar um novo projeto do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a751f-107">To create a new Analysis Services project</span></span>  
  
1.  <span data-ttu-id="a751f-108">Clique em **Iniciar**, aponte para **Todos os Programas**, **Microsoft SQL Server 2012**e clique em **Ferramentas de Dados do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a751f-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
     <span data-ttu-id="a751f-109">O [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ambiente de desenvolvimento é aberto.</span><span class="sxs-lookup"><span data-stu-id="a751f-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment opens.</span></span>  
  
2.  <span data-ttu-id="a751f-110">Na página Iniciar do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], clique em **Novo Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a751f-110">On the Start page of [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New Project**.</span></span>  
  
3.  <span data-ttu-id="a751f-111">Na caixa de diálogo **Novo Projeto** , no painel **Modelos Instalados** , expanda **Business Intelligence**e selecione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="a751f-111">In the **New Project** dialog box, in the **Installed Templates** pane, expand **Business Intelligence**, and then select **Analysis Services**.</span></span> <span data-ttu-id="a751f-112">Escolha o modelo **Projeto Multidimensional e de Mineração de Dados do Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="a751f-112">Choose the **Analysis Services Multidimensional and Data Mining Project** template.</span></span>  
  
     <span data-ttu-id="a751f-113">Observe que o nome de projeto padrão, o local e o nome de solução padrão são gerados na parte inferior da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a751f-113">Notice the default project name, location, and the default solution name are generated in the bottom of the dialog box.</span></span> <span data-ttu-id="a751f-114">Por padrão, um novo diretório será criado para a solução.</span><span class="sxs-lookup"><span data-stu-id="a751f-114">By default, a new directory is created for the solution.</span></span>  
  
4.  <span data-ttu-id="a751f-115">Altere o nome do projeto para `Analysis Services Tutorial` , que também altera a caixa **nome da solução** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a751f-115">Change the project Name to `Analysis Services Tutorial`, which also changes the **Solution name** box, and then click **OK**.</span></span>  
  
 <span data-ttu-id="a751f-116">Você criou o projeto com êxito `Analysis Services Tutorial` , com base no modelo de **projeto Analysis Services multidimensional e de mineração de dados** , em uma nova solução que também é denominada `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="a751f-116">You have successfully created the `Analysis Services Tutorial` project, based on the **Analysis Services Multidimensional and Data Mining Project** template, within a new solution that is also named `Analysis Services Tutorial`.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a751f-117">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="a751f-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a751f-118">Definindo uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="a751f-118">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="a751f-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a751f-119">See Also</span></span>  
 <span data-ttu-id="a751f-120">[Criando modelos multidimensionais usando o SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="a751f-120">[Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span></span>  
 [<span data-ttu-id="a751f-121">Criar um projeto do Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="a751f-121">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](multidimensional-models/create-an-analysis-services-project-ssdt.md)  
  
  
