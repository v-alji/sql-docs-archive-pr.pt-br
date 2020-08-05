---
title: 'Etapa 2: criar o projeto de implantação | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 59990fe2-7036-4e9c-8efc-6ece9e66eda7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebfce8796f98628c2832c5ab7f4be665c7915d10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574144"
---
# <a name="step-2-creating-the-deployment-project"></a><span data-ttu-id="80111-102">Etapa 2: Criar o projeto de implantação</span><span class="sxs-lookup"><span data-stu-id="80111-102">Step 2: Creating the Deployment Project</span></span>
  <span data-ttu-id="80111-103">No [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], a unidade que permite a implantação é um projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80111-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the deployable unit is an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="80111-104">Antes de implantar os pacotes, você deve criar um novo projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e adicionar todos os pacotes e qualquer arquivo auxiliar que deseja implantar com os pacotes nesse projeto.</span><span class="sxs-lookup"><span data-stu-id="80111-104">Before you can deploy packages, you must create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and add all the packages and any ancillary files that you want to deploy with the packages to that project.</span></span>  
  
### <a name="to-create-the-integration-services-project"></a><span data-ttu-id="80111-105">Para criar o projeto Integration Services</span><span class="sxs-lookup"><span data-stu-id="80111-105">To create the Integration Services project</span></span>  
  
1.  <span data-ttu-id="80111-106">Clique em **Iniciar**, aponte para **Todos os Programas**, **Microsoft SQL Server**e clique em **SQL Server SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="80111-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL ServerSQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="80111-107">No menu **Arquivo** , aponte para **Novo**e clique em **Projeto** para criar um novo projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80111-107">On the **File** menu, point to **New**, and then click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="80111-108">Na caixa de diálogo **Novo Projeto** , selecione **Projeto do Integration Services** no painel **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="80111-108">In the **New Project** dialog box, select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="80111-109">Na caixa **Nome** , altere o nome padrão para **Tutorial de Implantação**.</span><span class="sxs-lookup"><span data-stu-id="80111-109">In the **Name** box, change the default name to **Deployment Tutorial**.</span></span> <span data-ttu-id="80111-110">Opcionalmente, desmarque a caixa de seleção **Criar diretório para a solução** .</span><span class="sxs-lookup"><span data-stu-id="80111-110">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="80111-111">Aceite o local padrão ou clique em **Procurar** para localizar a pasta que você quer usar.</span><span class="sxs-lookup"><span data-stu-id="80111-111">Accept the default location, or click **Browse** to locate the folder you want to use.</span></span>  
  
6.  <span data-ttu-id="80111-112">Na caixa de diálogo **Local do Projeto** , clique na pasta e em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="80111-112">In the **Project Location** dialog box, click the folder, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="80111-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="80111-113">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="80111-114">Por padrão, um pacote vazio, chamado Package.dtsx, é criado e adicionado ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="80111-114">By default, an empty package, named Package.dtsx, is created and added to your project.</span></span> <span data-ttu-id="80111-115">Porém, você não usará este pacote; em vez disso, adicionará os pacotes existentes ao projeto.</span><span class="sxs-lookup"><span data-stu-id="80111-115">However, you will not use this package; instead, you will add existing packages to the project.</span></span> <span data-ttu-id="80111-116">Como todos os pacotes em um projeto serão incluídos na implantação, você deverá excluir o Package.dtsx.</span><span class="sxs-lookup"><span data-stu-id="80111-116">Because all the packages in a project will be included in the deployment, you should delete Package.dtsx.</span></span> <span data-ttu-id="80111-117">Para excluí-lo, clique nele com o botão direito do mouse e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="80111-117">To delete it, right-click it, and then click **Delete**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="80111-118">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="80111-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="80111-119">Etapa 3: Adicionando pacotes e outros arquivos</span><span class="sxs-lookup"><span data-stu-id="80111-119">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
<span data-ttu-id="80111-120">![Ícone de Integration Services (pequeno)](media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="80111-120">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="80111-121">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="80111-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="80111-122">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="80111-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="80111-123">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="80111-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80111-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="80111-124">See Also</span></span>  
 [<span data-ttu-id="80111-125">Projetos do Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="80111-125">Integration Services &#40;SSIS&#41; Projects</span></span>](integration-services-ssis-projects-and-solutions.md)  
  
  
