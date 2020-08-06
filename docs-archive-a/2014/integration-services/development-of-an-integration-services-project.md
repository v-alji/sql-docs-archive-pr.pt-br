---
title: Desenvolvimento de um projeto de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 6e90b016-36a5-415e-9440-a20199fffff0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da648b3b09b25fa2a7b1cf886ad1bf770296f5ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582552"
---
# <a name="development-of-an-integration-services-project"></a><span data-ttu-id="e6286-102">Implantação de um projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="e6286-102">Development of an Integration Services Project</span></span>
  <span data-ttu-id="e6286-103">Você adiciona pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a projetos.</span><span class="sxs-lookup"><span data-stu-id="e6286-103">You add [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to projects.</span></span> <span data-ttu-id="e6286-104">Para criar e trabalhar com projetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , você deve instalar o ambiente do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6286-104">To create and work with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects, you must install the [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] environment.</span></span> <span data-ttu-id="e6286-105">Para obter mais informações, consulte [Instalar o Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="e6286-105">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
 <span data-ttu-id="e6286-106">Quando você cria um novo projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], a caixa de diálogo **Novo Projeto** inclui um modelo do **Integration Services Project** .</span><span class="sxs-lookup"><span data-stu-id="e6286-106">When you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the **New Project** dialog box includes an **Integration Services Project** template.</span></span> <span data-ttu-id="e6286-107">Este modelo de projeto cria um novo projeto que contém um único pacote.</span><span class="sxs-lookup"><span data-stu-id="e6286-107">This project template creates a new project that contains a single package.</span></span>  
  
## <a name="projects-and-solutions"></a><span data-ttu-id="e6286-108">Soluções e Projetos</span><span class="sxs-lookup"><span data-stu-id="e6286-108">Projects and Solutions</span></span>  
 <span data-ttu-id="e6286-109">Projetos são armazenados em soluções.</span><span class="sxs-lookup"><span data-stu-id="e6286-109">Projects are stored in solutions.</span></span> <span data-ttu-id="e6286-110">Você pode primeiro criar uma solução e, então, adicionar um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] à solução.</span><span class="sxs-lookup"><span data-stu-id="e6286-110">You can create a solution first and then add an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the solution.</span></span> <span data-ttu-id="e6286-111">Se não existir uma solução, ela será criada automaticamente pelo [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] quando o projeto for criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="e6286-111">If no solution exists, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] automatically creates one for you when you first create the project.</span></span> <span data-ttu-id="e6286-112">Uma solução pode conter vários projetos de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="e6286-112">A solution can contain multiple projects of different types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6286-113">Por padrão, quando você cria um novo projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], a solução não é mostrada no painel **Gerenciador de Soluções** .</span><span class="sxs-lookup"><span data-stu-id="e6286-113">By default, when you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the solution is not shown in the **Solution Explorer** pane.</span></span> <span data-ttu-id="e6286-114">Para alterar este comportamento padrão, no menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="e6286-114">To change this default behavior, on the **Tools** menus, click **Options**.</span></span> <span data-ttu-id="e6286-115">Na caixa de diálogo **Opções** , expanda **Projetos e Soluções**e clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="e6286-115">In the **Options** dialog box, expand **Projects and Solutions**, and then click **General**.</span></span> <span data-ttu-id="e6286-116">Na página **Geral** , selecione **Sempre mostrar solução**.</span><span class="sxs-lookup"><span data-stu-id="e6286-116">On the **General** page, select **Always show solution**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e6286-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e6286-117">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e6286-118">Criar um novo projeto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="e6286-118">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="e6286-119">Adicionar um item a um projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="e6286-119">Add an Item to an Integration Services Project</span></span>](../../2014/integration-services/add-an-item-to-an-integration-services-project.md)  
  
-   [<span data-ttu-id="e6286-120">Adicionar ou remover um projeto do Integration Services em uma solução</span><span class="sxs-lookup"><span data-stu-id="e6286-120">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
