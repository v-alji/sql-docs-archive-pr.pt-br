---
title: Criar um projeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], creating
ms.assetid: 7897be19-365b-4b06-bcf0-8a669f67a673
author: stevestein
ms.author: sstein
ms.openlocfilehash: 269feee7225ceb09b1c2ed86419b19ec4001c1f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575525"
---
# <a name="create-a-project"></a><span data-ttu-id="1cb90-102">Criar um projeto</span><span class="sxs-lookup"><span data-stu-id="1cb90-102">Create a Project</span></span>
  <span data-ttu-id="1cb90-103">Você pode criar um ou mais projetos dentro de uma solução existente.</span><span class="sxs-lookup"><span data-stu-id="1cb90-103">You can create one or more projects within an existing solution.</span></span>  
  
### <a name="to-create-a-new-project-and-add-it-to-a-solution"></a><span data-ttu-id="1cb90-104">Para criar um novo projeto e adicioná-lo a uma solução</span><span class="sxs-lookup"><span data-stu-id="1cb90-104">To create a new project and add it to a solution</span></span>  
  
1.  <span data-ttu-id="1cb90-105">No Gerenciador de Soluções, selecione a solução.</span><span class="sxs-lookup"><span data-stu-id="1cb90-105">In Solution Explorer, select the solution.</span></span>  
  
2.  <span data-ttu-id="1cb90-106">No menu **Arquivo** , aponte para **Adicionar**e clique em **Novo Projeto**.</span><span class="sxs-lookup"><span data-stu-id="1cb90-106">On the **File** menu, point to **Add**, and click **New Project**.</span></span>  
  
3.  <span data-ttu-id="1cb90-107">Na caixa de diálogo  **Novo Projeto** , clique em um tipo de projeto.</span><span class="sxs-lookup"><span data-stu-id="1cb90-107">In the  **New Project** dialog box, click a type of project.</span></span>  
  
     <span data-ttu-id="1cb90-108">**Modelos**</span><span class="sxs-lookup"><span data-stu-id="1cb90-108">**Templates**</span></span>  
     <span data-ttu-id="1cb90-109">Na caixa **Modelos** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="1cb90-109">In the **Templates** box, select a template.</span></span> <span data-ttu-id="1cb90-110">Uma breve descrição do modelo de projeto selecionado aparece abaixo da caixa **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="1cb90-110">A brief description of the selected project template appears beneath the **Templates** box.</span></span>  
  
     <span data-ttu-id="1cb90-111">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1cb90-111">**Name**</span></span>  
     <span data-ttu-id="1cb90-112">Digite o nome do projeto de script que deseja criar.</span><span class="sxs-lookup"><span data-stu-id="1cb90-112">Enter the name of the script project you want to create.</span></span> <span data-ttu-id="1cb90-113">Também é criada uma pasta com o mesmo nome do projeto no local exibido no campo **Local** .</span><span class="sxs-lookup"><span data-stu-id="1cb90-113">A folder with the same name as the project is also created in the location displayed in the **Location** field.</span></span> <span data-ttu-id="1cb90-114">Para alguns projetos, o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] cria fonte e outros arquivos de suporte e os adiciona à pasta de projeto nova.</span><span class="sxs-lookup"><span data-stu-id="1cb90-114">For some projects, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates source and other supporting files and adds them to the new project folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1cb90-115">Para alguns tipos de projeto, a caixa de texto **Nome** fica indisponível, pois especificar o local define o nome.</span><span class="sxs-lookup"><span data-stu-id="1cb90-115">For some project types, the **Name** text box is unavailable because specifying the location sets the name.</span></span> <span data-ttu-id="1cb90-116">Por exemplo, aplicativos e serviços Web estão localizados em um servidor Web e extraem seus nomes de diretórios virtuais especificados nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="1cb90-116">For example, Web applications and Web services are located on a Web server and derive their name from the virtual directory specified on that server.</span></span>  
  
     <span data-ttu-id="1cb90-117">Nomes não podem conter os seguintes caracteres:</span><span class="sxs-lookup"><span data-stu-id="1cb90-117">Names cannot contain the following characters:</span></span>  
  
    -   <span data-ttu-id="1cb90-118">Cerquilha (#)</span><span class="sxs-lookup"><span data-stu-id="1cb90-118">Pound (#)</span></span>  
  
    -   <span data-ttu-id="1cb90-119">Porcentagem (%)</span><span class="sxs-lookup"><span data-stu-id="1cb90-119">Percent (%)</span></span>  
  
    -   <span data-ttu-id="1cb90-120">E comercial (&)</span><span class="sxs-lookup"><span data-stu-id="1cb90-120">Ampersand (&)</span></span>  
  
    -   <span data-ttu-id="1cb90-121">Asterisco (\*)</span><span class="sxs-lookup"><span data-stu-id="1cb90-121">Asterisk (\*)</span></span>  
  
    -   <span data-ttu-id="1cb90-122">Barra vertical (|)</span><span class="sxs-lookup"><span data-stu-id="1cb90-122">Vertical bar (|)</span></span>  
  
    -   <span data-ttu-id="1cb90-123">Barra invertida (\\)</span><span class="sxs-lookup"><span data-stu-id="1cb90-123">Backslash (\\)</span></span>  
  
    -   <span data-ttu-id="1cb90-124">Dois-pontos (:)</span><span class="sxs-lookup"><span data-stu-id="1cb90-124">Colon (:)</span></span>  
  
    -   <span data-ttu-id="1cb90-125">Aspas (")</span><span class="sxs-lookup"><span data-stu-id="1cb90-125">Quotation mark (")</span></span>  
  
    -   <span data-ttu-id="1cb90-126">Menor que (\<)</span><span class="sxs-lookup"><span data-stu-id="1cb90-126">Less than (\<)</span></span>  
  
    -   <span data-ttu-id="1cb90-127">Maior que (>)</span><span class="sxs-lookup"><span data-stu-id="1cb90-127">Greater than (>)</span></span>  
  
    -   <span data-ttu-id="1cb90-128">Ponto de interrogação (?)</span><span class="sxs-lookup"><span data-stu-id="1cb90-128">Question mark (?)</span></span>  
  
    -   <span data-ttu-id="1cb90-129">Barra (/)</span><span class="sxs-lookup"><span data-stu-id="1cb90-129">Forward slash (/)</span></span>  
  
    -   <span data-ttu-id="1cb90-130">Espaços iniciais ou finais (' ')</span><span class="sxs-lookup"><span data-stu-id="1cb90-130">Leading or trailing spaces (' ')</span></span>  
  
    -   <span data-ttu-id="1cb90-131">Nomes reservados para o Microsoft Windows ou MS-DOS, como ("nul", "aux", "con", "com1", "lpt1" e assim por diante)</span><span class="sxs-lookup"><span data-stu-id="1cb90-131">Names reserved for Microsoft Windows or MS-DOS, such as ("nul", "aux", "con", "com1", "lpt1", and so on)</span></span>  
  
     <span data-ttu-id="1cb90-132">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="1cb90-132">**Location**</span></span>  
     <span data-ttu-id="1cb90-133">Insira o local onde deseja criar seu projeto ou escolha um na lista.</span><span class="sxs-lookup"><span data-stu-id="1cb90-133">Enter the location where you want to create your project, or choose one from the list.</span></span>  
  
     <span data-ttu-id="1cb90-134">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="1cb90-134">**Browse**</span></span>  
     <span data-ttu-id="1cb90-135">Exibe a caixa de diálogo **Local do Projeto** , permitindo que você navegue até um novo diretório no qual salvar o projeto.</span><span class="sxs-lookup"><span data-stu-id="1cb90-135">Displays the **Project Location** dialog box, allowing you to navigate to a new directory in which to save the project.</span></span>  
  
     <span data-ttu-id="1cb90-136">**Solução**</span><span class="sxs-lookup"><span data-stu-id="1cb90-136">**Solution**</span></span>  
     <span data-ttu-id="1cb90-137">Selecione **Criar Nova Solução** para criar uma solução no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="1cb90-137">Select **Create new Solution** to create a solution in Solution Explorer.</span></span> <span data-ttu-id="1cb90-138">Selecione **Adicionar à Solução** para adicionar o novo projeto à solução atualmente aberta no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="1cb90-138">Select **Add to Solution** to add the new project to the solution currently open in Solution Explorer.</span></span>  
  
     <span data-ttu-id="1cb90-139">**Criar diretório para a solução**</span><span class="sxs-lookup"><span data-stu-id="1cb90-139">**Create directory for Solution**</span></span>  
     <span data-ttu-id="1cb90-140">Selecione para habilitar a caixa de texto **(Solução) Nome** .</span><span class="sxs-lookup"><span data-stu-id="1cb90-140">Select to enable the **(Solution) Name** text box.</span></span> <span data-ttu-id="1cb90-141">Esta opção cria um novo diretório do nome escolhido para seu projeto e solução.</span><span class="sxs-lookup"><span data-stu-id="1cb90-141">This option creates a new directory of the name you choose for your project and solution.</span></span>  
  
     <span data-ttu-id="1cb90-142">**Nome da Solução**</span><span class="sxs-lookup"><span data-stu-id="1cb90-142">**Solution Name**</span></span>  
     <span data-ttu-id="1cb90-143">Digite o nome da nova solução em que você deseja que seu projeto seja criado.</span><span class="sxs-lookup"><span data-stu-id="1cb90-143">Enter the name of the new solution in which you want your project to be created.</span></span> <span data-ttu-id="1cb90-144">Por padrão, este campo usa o mesmo nome digitado no campo **Nome** .</span><span class="sxs-lookup"><span data-stu-id="1cb90-144">By default, this field uses the same name as entered in the **Name** field.</span></span>  
  
     <span data-ttu-id="1cb90-145">**Observação** Para acessar essa opção, você deve marcar as caixas de seleção **Criar Nova Solução** em **Solução** e **Criar diretório para a solução** .</span><span class="sxs-lookup"><span data-stu-id="1cb90-145">**Note** To access this option, you must select both the **Create New Solution** in the **Solution** and the **Create directory for Solution** check boxes.</span></span> <span data-ttu-id="1cb90-146">Alguns modelos de projeto não oferecem suporte a esta opção, como aplicativos Web.</span><span class="sxs-lookup"><span data-stu-id="1cb90-146">Some project templates do not support this option, such as Web applications.</span></span>  
  
     <span data-ttu-id="1cb90-147">**Adicionar ao Controle do Código Fonte**</span><span class="sxs-lookup"><span data-stu-id="1cb90-147">**Add to Source Control**</span></span>  
     <span data-ttu-id="1cb90-148">Quando esta caixa de seleção é marcada, seu aplicativo de controle do código-fonte é aberto quando você clica em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cb90-148">When this check box is selected, your source control application opens when you click **OK**.</span></span> <span data-ttu-id="1cb90-149">Preencha qualquer informação solicitada por seu aplicativo de controle do código fonte para continuar.</span><span class="sxs-lookup"><span data-stu-id="1cb90-149">Complete any information required by your source control application to continue.</span></span> <span data-ttu-id="1cb90-150">Você deve ter um aplicativo cliente de controle do código-fonte instalado para usar esta opção.</span><span class="sxs-lookup"><span data-stu-id="1cb90-150">You must have a source control client application installed to use this option.</span></span>  
  
4.  <span data-ttu-id="1cb90-151">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cb90-151">Click **OK**.</span></span>  
  
 <span data-ttu-id="1cb90-152">Você pode definir um nome para o projeto de script, mas os nomes de pastas são definidos pelo [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="1cb90-152">You can set a name for the script project, but the folder names are established by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and cannot be changed.</span></span> <span data-ttu-id="1cb90-153">Você pode configurar a unidade e a especificação do caminho do conjunto comum de pastas usando a caixa de diálogo **Adicionar Novo Projeto** .</span><span class="sxs-lookup"><span data-stu-id="1cb90-153">You can configure the drive and path specification for the common set of folders by using the **Add New Project** dialog box.</span></span> <span data-ttu-id="1cb90-154">No **Gerenciador de Soluções**, clique com o botão direito do mouse no ícone da solução e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1cb90-154">Right-click the solution icon in **Solution Explorer**, and then click **Add**.</span></span> <span data-ttu-id="1cb90-155">O local padrão para pastas de projeto de script é: C:\Documents and Settings\\*username*\My Documents\SQL Server Management Studio\Projects\\.</span><span class="sxs-lookup"><span data-stu-id="1cb90-155">The default location for script project folders is: C:\Documents and Settings\\*username*\My Documents\SQL Server Management Studio\Projects\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb90-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1cb90-156">See Also</span></span>  
 <span data-ttu-id="1cb90-157">[Gerenciador de Soluções](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="1cb90-157">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="1cb90-158">[Adicionar um projeto existente a uma solução](add-an-existing-project-to-a-solution.md) </span><span class="sxs-lookup"><span data-stu-id="1cb90-158">[Add an Existing Project to a Solution](add-an-existing-project-to-a-solution.md) </span></span>  
 <span data-ttu-id="1cb90-159">[Adicionar novos itens a um projeto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="1cb90-159">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 <span data-ttu-id="1cb90-160">[Adicionar itens existentes a um projeto](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="1cb90-160">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 <span data-ttu-id="1cb90-161">[Alterar o local padrão dos projetos](change-the-default-location-for-projects.md) </span><span class="sxs-lookup"><span data-stu-id="1cb90-161">[Change the Default Location for Projects](change-the-default-location-for-projects.md) </span></span>  
 <span data-ttu-id="1cb90-162">[Remover ou excluir um item ou projeto](remove-or-delete-an-item-or-project.md) </span><span class="sxs-lookup"><span data-stu-id="1cb90-162">[Remove or Delete an Item or Project](remove-or-delete-an-item-or-project.md) </span></span>  
 [<span data-ttu-id="1cb90-163">Excluir uma solução</span><span class="sxs-lookup"><span data-stu-id="1cb90-163">Delete a Solution</span></span>](delete-a-solution.md)  
  
  
