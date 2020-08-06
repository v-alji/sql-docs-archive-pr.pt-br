---
title: Adicionar ou remover um projeto de Integration Services em uma solução | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- Integration Services projects, adding
- SQL Server Integration Services projects, adding
- SSIS projects, adding
- projects [Integration Services], adding
ms.assetid: f01f6475-b63c-41dc-82ac-b62162b3adf7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49984c61047a6b716015bd72e518b73cb08b3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568761"
---
# <a name="add-or-remove-an-integration-services-project-in-a-solution"></a><span data-ttu-id="a7532-102">Adicionar ou remover um projeto do Integration Services em uma solução</span><span class="sxs-lookup"><span data-stu-id="a7532-102">Add or Remove an Integration Services Project in a Solution</span></span>
  <span data-ttu-id="a7532-103">Os procedimentos a seguir descrevem como adicionar ou remover um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] em uma solução.</span><span class="sxs-lookup"><span data-stu-id="a7532-103">The following procedures descibe how to add or remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in a solution.</span></span>  
  
 <span data-ttu-id="a7532-104">Você só pode adicionar um projeto a uma solução existente, ou remover um projeto de uma solução, quando a solução estiver visível no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7532-104">You can only add a project to an existing solution, or remove a project from a solution, when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="a7532-105">Se você tiver selecionado a opção **sempre mostrar solução** no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] exibirá uma solução mesmo quando essa solução contiver apenas um projeto.</span><span class="sxs-lookup"><span data-stu-id="a7532-105">If you have selected the **Always show solution** option in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution even when that solution contains only one project.</span></span> <span data-ttu-id="a7532-106">Caso contrário, o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] só exibirá uma solução quando houver mais de um projeto.</span><span class="sxs-lookup"><span data-stu-id="a7532-106">Otherwise, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution only when that solution contains more than one project.</span></span> <span data-ttu-id="a7532-107">Os projetos adicionais podem ser projetos do [!INCLUDE[ssIS](../includes/ssis-md.md)] ou de outros tipos.</span><span class="sxs-lookup"><span data-stu-id="a7532-107">The additional projects can be either [!INCLUDE[ssIS](../includes/ssis-md.md)] projects or projects of other types.</span></span>  
  
## <a name="adding-an-integration-services-project"></a><span data-ttu-id="a7532-108">Adicionando um projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="a7532-108">Adding an Integration Services Project</span></span>  
 <span data-ttu-id="a7532-109">Ao adicionar um projeto, você pode deixar que o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] crie um novo projeto em branco ou pode adicionar um projeto que já tenha sido criado em outra solução.</span><span class="sxs-lookup"><span data-stu-id="a7532-109">When you add a project, you can have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] create a new, blank project, or you can add a project that you have already created for a different solution.</span></span> <span data-ttu-id="a7532-110">Você só pode adicionar um projeto a uma solução existente quando a solução estiver visível em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7532-110">You can only add a project to an existing solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
#### <a name="to-add-a-new-integration-services-project-to-a-solution"></a><span data-ttu-id="a7532-111">Para adicionar um novo projeto do Integration Services a uma solução</span><span class="sxs-lookup"><span data-stu-id="a7532-111">To add a new Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="a7532-112">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra a solução à qual deseja adicionar um novo projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="a7532-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="a7532-113">Clique com o botão direito do mouse na solução, escolha **Adicionar** e clique em **Novo Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a7532-113">Right-click the solution, click **Add**, and then click **New Project**.</span></span>  
  
    -   <span data-ttu-id="a7532-114">No menu **Arquivo**, aponte para **Adicionar** e clique em **Novo Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a7532-114">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="a7532-115">Na caixa de diálogo **Adicionar Novo Projeto**, clique em **Projeto do Integration Services** no painel **Modelos**.</span><span class="sxs-lookup"><span data-stu-id="a7532-115">In the **Add New Project** dialog box, click **Integration Services Project** in the **Templates** pane.</span></span>  
  
3.  <span data-ttu-id="a7532-116">Se preferir, edite o nome e o local do projeto.</span><span class="sxs-lookup"><span data-stu-id="a7532-116">Optionally, edit the project name and location.</span></span>  
  
4.  <span data-ttu-id="a7532-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7532-117">Click **OK**.</span></span>  
  
#### <a name="to-add-an-existing-integration-services-project-to-a-solution"></a><span data-ttu-id="a7532-118">Para adicionar um projeto existente do Integration Services a uma solução</span><span class="sxs-lookup"><span data-stu-id="a7532-118">To add an existing Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="a7532-119">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra a solução à qual deseja adicionar um projeto existente do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="a7532-119">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="a7532-120">Clique com o botão direito do mouse na solução, aponte a **Adicionar** e escolha **Projeto Existente**.</span><span class="sxs-lookup"><span data-stu-id="a7532-120">Right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
    -   <span data-ttu-id="a7532-121">No menu **Arquivo**, clique em **Adicionar** e escolha **Projeto Existente**.</span><span class="sxs-lookup"><span data-stu-id="a7532-121">On the **File** menu, click **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="a7532-122">Na caixa de diálogo **Adicionar Projeto Existente**, navegue até o local ao qual deseja adicionar o projeto e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a7532-122">In the **Add Existing Project** dialog box, browse to locate the project you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="a7532-123">O projeto é adicionado à pasta da solução no **Gerenciador de Soluções**.</span><span class="sxs-lookup"><span data-stu-id="a7532-123">The project is added to the solution folder in **Solution Explorer**.</span></span>  
  
## <a name="removing-an-integration-services-project"></a><span data-ttu-id="a7532-124">Removendo um projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="a7532-124">Removing an Integration Services Project</span></span>  
 <span data-ttu-id="a7532-125">Você só pode remover um projeto de uma solução quando a solução estiver visível em [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7532-125">You can only remove a project from a solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="a7532-126">Assim que a solução estiver visível, você poderá remover tudo, exceto um projeto.</span><span class="sxs-lookup"><span data-stu-id="a7532-126">After the solution is visible, you can remove all except one project.</span></span> <span data-ttu-id="a7532-127">Quando restar apenas um projeto, o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] não exibirá mais a pasta da solução e o último projeto não poderá ser removido.</span><span class="sxs-lookup"><span data-stu-id="a7532-127">As soon as only one project remains, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no longer displays the solution folder and you cannot remove the last project.</span></span>  
  
#### <a name="to-remove-an-integration-services-project-from-a-solution"></a><span data-ttu-id="a7532-128">Para remover um projeto do Integration Services de uma solução</span><span class="sxs-lookup"><span data-stu-id="a7532-128">To remove an Integration Services project from a solution</span></span>  
  
1.  <span data-ttu-id="a7532-129">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra a solução da qual deseja remover um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7532-129">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution from which you want to remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="a7532-130">No Gerenciador de Soluções, clique com o botão direito do mouse no projeto e, em seguida, clique em **Descarregar Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a7532-130">In Solution Explorer, right-click the project, and then click **Unload Project**.</span></span>  
  
3.  <span data-ttu-id="a7532-131">Clique em **OK** para confirmar a remoção.</span><span class="sxs-lookup"><span data-stu-id="a7532-131">Click **OK** to confirm the removal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7532-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a7532-132">See Also</span></span>  
 <span data-ttu-id="a7532-133">[Projetos do Integration Services &#40;SSIS&#41;](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="a7532-133">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="a7532-134">Criar um novo projeto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="a7532-134">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
  
