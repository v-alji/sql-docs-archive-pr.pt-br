---
title: Adicionar itens existentes a um projeto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 084b3879-e96b-45a7-b421-6a4b0db2b92b
author: stevestein
ms.author: sstein
ms.openlocfilehash: cffa683bfa2a2c81c059d887231531f03d5c892b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583276"
---
# <a name="add-existing-items-to-a-project"></a><span data-ttu-id="80639-102">Adicionar itens existentes a um projeto</span><span class="sxs-lookup"><span data-stu-id="80639-102">Add Existing Items to a Project</span></span>
  <span data-ttu-id="80639-103">Adicione novos itens a um projeto para estender a funcionalidade do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="80639-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="80639-104">Um item existente pode ser uma consulta ou um arquivo diverso.</span><span class="sxs-lookup"><span data-stu-id="80639-104">An existing item can be a query or a miscellaneous file.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="80639-105">tem dois tipos de projeto: Projeto de Script do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e Projeto de Script do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="80639-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="80639-106">O tipo de projeto determina os arquivos de consulta que você pode adicionar ao projeto.</span><span class="sxs-lookup"><span data-stu-id="80639-106">The project type determines the query files that you can add to the project.</span></span> <span data-ttu-id="80639-107">Por exemplo, você pode adicionar uma consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] (um arquivo com uma extensão .sql) a um projeto de script do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mas não pode adicioná-lo a um Projeto de Script do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="80639-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span> <span data-ttu-id="80639-108">Para associar extensões de arquivo adicionais a um tipo de projeto, consulte [associar extensões de arquivo a um editor de códigos](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span><span class="sxs-lookup"><span data-stu-id="80639-108">To associate additional file extensions to a project type, see [Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span></span>  
  
### <a name="to-add-an-existing-query-or-a-miscellaneous-file-to-a-project"></a><span data-ttu-id="80639-109">Para adicionar uma consulta existente ou um arquivo diverso a um projeto</span><span class="sxs-lookup"><span data-stu-id="80639-109">To add an existing query or a miscellaneous file to a project</span></span>  
  
1.  <span data-ttu-id="80639-110">No Gerenciador de Soluções, selecione um projeto de destino.</span><span class="sxs-lookup"><span data-stu-id="80639-110">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="80639-111">No menu **Projeto** , clique em **Adicionar Item Existente**.</span><span class="sxs-lookup"><span data-stu-id="80639-111">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
     <span data-ttu-id="80639-112">**Look in**</span><span class="sxs-lookup"><span data-stu-id="80639-112">**Look in**</span></span>  
     <span data-ttu-id="80639-113">Localize os arquivos ou pastas a adicionar ao seu projeto nesta lista.</span><span class="sxs-lookup"><span data-stu-id="80639-113">Locate the files or folders to add to your project from this list.</span></span> <span data-ttu-id="80639-114">Em XML Web Services e aplicativos Web ASP.NET, os arquivos se localizam no servidor Web.</span><span class="sxs-lookup"><span data-stu-id="80639-114">For XML Web services and ASP.NET Web applications, the files are located on the Web server.</span></span>  
  
     <span data-ttu-id="80639-115">**Área de Trabalho**</span><span class="sxs-lookup"><span data-stu-id="80639-115">**Desktop**</span></span>  
     <span data-ttu-id="80639-116">Exibe os arquivos e pastas localizadas na área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="80639-116">Displays the files and folders located on the desktop.</span></span>  
  
     <span data-ttu-id="80639-117">**Meus Projetos**</span><span class="sxs-lookup"><span data-stu-id="80639-117">**My Projects**</span></span>  
     <span data-ttu-id="80639-118">Exibe os arquivos e pastas no local padrão **Meus Projetos** .</span><span class="sxs-lookup"><span data-stu-id="80639-118">Displays the files and folders at the default **My Projects** location.</span></span>  
  
     <span data-ttu-id="80639-119">**Meu Computador**</span><span class="sxs-lookup"><span data-stu-id="80639-119">**My Computer**</span></span>  
     <span data-ttu-id="80639-120">Exibe o conteúdo de sua pasta **Meu Computador** .</span><span class="sxs-lookup"><span data-stu-id="80639-120">Displays the contents of your **My Computer** folder.</span></span>  
  
     <span data-ttu-id="80639-121">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="80639-121">**File name**</span></span>  
     <span data-ttu-id="80639-122">Use esta opção para filtrar os arquivos e pastas a serem exibidos.</span><span class="sxs-lookup"><span data-stu-id="80639-122">Use this option to filter the files and folders that are displayed.</span></span> <span data-ttu-id="80639-123">Insira o nome completo ou parcial do arquivo a filtrar; use um asterisco (`*`) como curinga.</span><span class="sxs-lookup"><span data-stu-id="80639-123">Enter the full or partial file name on which to filter; use an asterisk (`*`) as a wildcard.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80639-124">Navegue na Web e em locais de rede inserindo a URL ou o caminho de rede na caixa **Nome do arquivo** .</span><span class="sxs-lookup"><span data-stu-id="80639-124">Navigate to Web and network locations by entering the URL or network path in the **File name** box.</span></span> <span data-ttu-id="80639-125">Por exemplo, **http://mywebsite** exibe os arquivos disponíveis no local da Web meusite e **\\\meuservidor\meucompartilhamento** exibe os arquivos disponíveis no local meucompartilhamento em meuservidor.</span><span class="sxs-lookup"><span data-stu-id="80639-125">For example, **http://mywebsite** displays the files available at the mywebsite Web location, and **\\\myserver\myshare** displays the files available at the myshare location on myserver.</span></span>  
  
     <span data-ttu-id="80639-126">**Arquivos do tipo**</span><span class="sxs-lookup"><span data-stu-id="80639-126">**Files of type**</span></span>  
     <span data-ttu-id="80639-127">Use esta opção para filtrar arquivos com base na extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="80639-127">Use this option to filter files based on file extension.</span></span> <span data-ttu-id="80639-128">Cada produto lista filtros padrões dos tipos de arquivo mais comuns.</span><span class="sxs-lookup"><span data-stu-id="80639-128">Each product lists default filters of the most common file types.</span></span>  
  
     <span data-ttu-id="80639-129">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="80639-129">**Add**</span></span>  
     <span data-ttu-id="80639-130">Use este botão suspenso para adicionar o item ao projeto e abrir o item em seu editor padrão.</span><span class="sxs-lookup"><span data-stu-id="80639-130">Use this drop-down button to add the item to the project and open the item in its default editor.</span></span>  
  
    -   <span data-ttu-id="80639-131">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="80639-131">**Add**</span></span>  
  
         <span data-ttu-id="80639-132">Copia o item existente na sua pasta de projeto no disco e adiciona o item sob o projeto selecionado no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="80639-132">Copies the existing item to your project folder on disk and adds the item under the selected project in Solution Explorer.</span></span> <span data-ttu-id="80639-133">Nenhuma alteração feita ao item é refletida no item no local original.</span><span class="sxs-lookup"><span data-stu-id="80639-133">Any changes made to the item are not reflected in the item at the original location.</span></span> <span data-ttu-id="80639-134">Esse é o editor padrão do tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="80639-134">This is the default editor for the file type.</span></span>  
  
    -   <span data-ttu-id="80639-135">**Adicionar Como Vínculo**</span><span class="sxs-lookup"><span data-stu-id="80639-135">**Add As Link**</span></span>  
  
         <span data-ttu-id="80639-136">Adiciona o arquivo selecionado ao projeto e abre-o com o editor padrão do tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="80639-136">Adds the selected file to the project and opens it with the default editor for the file type.</span></span> <span data-ttu-id="80639-137">Essa opção abre o arquivo originalmente selecionado e não copia o arquivo na pasta de projeto.</span><span class="sxs-lookup"><span data-stu-id="80639-137">This option opens the originally selected file and does not copy the file to the project folder.</span></span>  
  
3.  <span data-ttu-id="80639-138">Na adição de arquivos de consulta, a caixa de diálogo de conexão solicitará que você especifique uma conexão para a consulta.</span><span class="sxs-lookup"><span data-stu-id="80639-138">If you are adding query files, the connection dialog will prompt you to specify a connection for the query.</span></span> <span data-ttu-id="80639-139">Você poderá clicar em **Cancelar** na caixa de diálogo de conexão se não quiser associar uma conexão à consulta.</span><span class="sxs-lookup"><span data-stu-id="80639-139">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the query.</span></span>  
  
4.  <span data-ttu-id="80639-140">O arquivo será adicionado à pasta **Consultas** ou **Arquivos Diversos** do projeto.</span><span class="sxs-lookup"><span data-stu-id="80639-140">The file will be added to the **Queries** or **Miscellaneous Files** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80639-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="80639-141">See Also</span></span>  
 <span data-ttu-id="80639-142">[Gerenciador de Soluções](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="80639-142">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="80639-143">[Adicionar novos itens a um projeto](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="80639-143">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="80639-144">Remover ou excluir um item ou projeto</span><span class="sxs-lookup"><span data-stu-id="80639-144">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
