---
title: Projeto de scripts de Analysis Services no SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [Analysis Services]
- scripts [Analysis Services], projects
- projects [Analysis Services], Analysis Server Scripts project
- projects [Analysis Services], creating
- Analysis Server Scripts project
- items [Analysis Services]
ms.assetid: c4f5a06b-e2e4-4660-a3a8-6fd356742c02
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3dc10280e2ee957cd2245bb6a4993d7dcf536680
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574402"
---
# <a name="analysis-services-scripts-project-in-sql-server-management-studio"></a><span data-ttu-id="524b7-102">Projeto de scripts do Analysis Services no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="524b7-102">Analysis Services Scripts Project in SQL Server Management Studio</span></span>
  <span data-ttu-id="524b7-103">No [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], você pode criar um projeto do Analysis Server Scripts no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para agrupar scripts relacionados para uso em desenvolvimento, gerenciamento e controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="524b7-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can create an Analysis Server Scripts project in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to group related scripts together for development, management, and source control purposes.</span></span> <span data-ttu-id="524b7-104">Se não houver uma solução carregada no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a criação de um novo projeto do Analysis Server Scripts criará automaticamente uma nova solução.</span><span class="sxs-lookup"><span data-stu-id="524b7-104">If no solution is currently loaded in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], creating a new Analysis Server Scripts project automatically creates a new solution.</span></span> <span data-ttu-id="524b7-105">Caso contrário, o novo projeto do Analysis Server Scripts pode ser adicionado à solução existente ou criado em uma solução nova.</span><span class="sxs-lookup"><span data-stu-id="524b7-105">Otherwise, the new Analysis Server Scripts project can be added to the existing solution or created in a new solution.</span></span>  
  
 <span data-ttu-id="524b7-106">Siga estas etapas básicas para criar um projeto do Analysis Server Scripts no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="524b7-106">You use the following basic steps to create an Analysis Server Scripts project in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]:</span></span>  
  
1.  <span data-ttu-id="524b7-107">No menu Arquivo , aponte para **Novo**e clique em **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="524b7-107">On the File menu, point to **New**, and then click **Project**.</span></span>  
  
     <span data-ttu-id="524b7-108">Selecione o modelo de projeto **Scripts do Analysis Server** e especifique um nome e um local para o novo projeto.</span><span class="sxs-lookup"><span data-stu-id="524b7-108">Select **Analysis Server Scripts** project template and then specify a name and location for the new project.</span></span>  
  
2.  <span data-ttu-id="524b7-109">Clique com o botão direito do mouse em **Conexões** para criar uma nova conexão na pasta Conexões do projeto do Analysis Server Scripts no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="524b7-109">Right-click **Connections** to create a new connection in the Connections folder of the Analysis Server Scripts project in Solution Explorer.</span></span>  
  
     <span data-ttu-id="524b7-110">Esta pasta contém cadeias de conexão com instâncias do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , nas quais os scripts contidos no projeto do Analysis Server Scripts podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="524b7-110">This folder contains connection strings to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instances, against which the scripts contained by the Analysis Server Scripts project can be executed.</span></span> <span data-ttu-id="524b7-111">Podem existir várias conexões em um projeto do Analysis Server Scripts e você pode escolher uma delas para executar um script contido no projeto no momento da execução.</span><span class="sxs-lookup"><span data-stu-id="524b7-111">You can have multiple connections in an Analysis Server Scripts project, and you can choose a connection against which to run a script contained by the project at the time of execution.</span></span>  
  
3.  <span data-ttu-id="524b7-112">Clique com o botão direito do mouse em **Consultas** para criar scripts MDX (expressão MDX), DMX (extensões DMX) e XMLA (XML for Analysis) na pasta Scripts do projeto do Analysis Server Scripts no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="524b7-112">Right-click **Queries** to create Multidimensional Expressions (MDX), Data Mining Extensions (DMX), and XML for Analysis (XMLA) scripts in the Scripts folder of the Analysis Server Scripts project in Solution Explorer.</span></span> <span data-ttu-id="524b7-113">Para obter mais informações, consulte [Script de tarefas administrativas no Analysis Services](../script-administrative-tasks-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="524b7-113">For more information, see [Script Administrative Tasks in Analysis Services](../script-administrative-tasks-in-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="524b7-114">Clique com o botão direito do mouse no projeto, aponte para **Adicionar**e selecione **Item Existente** para adicionar arquivos diversos, como arquivos de texto com observações sobre o projeto, na pasta **Diversos** do Analysis Server Scripts no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="524b7-114">Right-click on the project, point to **Add**, and then select **Existing Item** to add miscellaneous files, such as text files that contain notes on the project, in the **Miscellaneous** folder of the Analysis Server Scripts project in Solution Explorer.</span></span> <span data-ttu-id="524b7-115">Esses arquivos são ignorados pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="524b7-115">These files are ignored by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="file-types"></a><span data-ttu-id="524b7-116">Tipos de arquivo</span><span class="sxs-lookup"><span data-stu-id="524b7-116">File Types</span></span>  
 <span data-ttu-id="524b7-117">A solução do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pode conter vários tipos de arquivo, dependendo dos projetos incluídos nela e de seus itens.</span><span class="sxs-lookup"><span data-stu-id="524b7-117">A [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution can contain several file types, depending on what projects you included in the solution and what items you included in each project for that solution.</span></span> <span data-ttu-id="524b7-118">Para obter mais informações sobre tipos de arquivo para soluções em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], consulte [Arquivos que gerenciam soluções e projetos](../../ssms/solution/files-that-manage-solutions-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="524b7-118">For more information about file types for solutions in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [Files That Manage Solutions and Projects](../../ssms/solution/files-that-manage-solutions-and-projects.md).</span></span> <span data-ttu-id="524b7-119">Em geral, os arquivos de cada projeto de uma solução do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] são armazenados na pasta da solução, em uma pasta separada para cada projeto.</span><span class="sxs-lookup"><span data-stu-id="524b7-119">Typically, the files for each project in a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution are stored in the solution folder, in a separate folder for each project.</span></span>  
  
 <span data-ttu-id="524b7-120">A pasta de um projeto do Analysis Server Scripts pode conter os tipos de arquivo listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="524b7-120">The project folder for an Analysis Server Scripts project can contain the file types listed in the following table.</span></span>  
  
|<span data-ttu-id="524b7-121">Tipo de arquivo</span><span class="sxs-lookup"><span data-stu-id="524b7-121">File type</span></span>|<span data-ttu-id="524b7-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="524b7-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="524b7-123">Arquivo de definição do projeto do Analysis Server Scripts (.ssmsasproj)</span><span class="sxs-lookup"><span data-stu-id="524b7-123">Analysis Server Scripts project definition file (.ssmsasproj)</span></span>|<span data-ttu-id="524b7-124">Contém metadados sobre as pastas mostradas no Gerenciador de Soluções, além de informações que indicam quais pastas devem exibir os arquivos incluídos no projeto.</span><span class="sxs-lookup"><span data-stu-id="524b7-124">Contains metadata about the folders shown in Solution Explorer, as well as information that indicates which folders should display files included in the project.</span></span><br /><br /> <span data-ttu-id="524b7-125">O arquivo de definição do projeto também contém os metadados das conexões do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contidas no projeto, além dos metadados que associam conexões aos arquivos de script incluídos no projeto.</span><span class="sxs-lookup"><span data-stu-id="524b7-125">The project definition file also contains the metadata for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connections contained in the project, as well as metadata that associates connections with script files included in the project.</span></span>|  
|<span data-ttu-id="524b7-126">Arquivo de script DMX (.dmx)</span><span class="sxs-lookup"><span data-stu-id="524b7-126">DMX script file (.dmx)</span></span>|<span data-ttu-id="524b7-127">Contém um script DMX incluído no projeto.</span><span class="sxs-lookup"><span data-stu-id="524b7-127">Contains a DMX script included in the project.</span></span>|  
|<span data-ttu-id="524b7-128">Arquivo de script MDX (.mdx)</span><span class="sxs-lookup"><span data-stu-id="524b7-128">MDX script file (.mdx)</span></span>|<span data-ttu-id="524b7-129">Contém um script MDX incluído no projeto.</span><span class="sxs-lookup"><span data-stu-id="524b7-129">Contains an MDX script included in the project.</span></span>|  
|<span data-ttu-id="524b7-130">Arquivo de script XMLA (.xmla)</span><span class="sxs-lookup"><span data-stu-id="524b7-130">XMLA script file (.xmla)</span></span>|<span data-ttu-id="524b7-131">Contém um script XMLA incluído no projeto.</span><span class="sxs-lookup"><span data-stu-id="524b7-131">Contains an XMLA script included in the project.</span></span>|  
  
## <a name="analysis-services-templates"></a><span data-ttu-id="524b7-132">Modelos do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="524b7-132">Analysis Services Templates</span></span>  
 <span data-ttu-id="524b7-133">Ao adicionar novos scripts MDX, DMX ou XMLA a um projeto do Analysis Server Scripts, você tem a opção de usar o Explorador de Modelos para localizar os modelos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , uma coleção de scripts ou instruções predefinidos(as) que demonstram como executar a ação especificada.</span><span class="sxs-lookup"><span data-stu-id="524b7-133">When adding new MDX, DMX, or XMLA scripts to an Analysis Server Scripts project, you have the option of using Template Explorer to locate [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] templates, which are a collection of predefined scripts or statements that demonstrate how to perform a specified action.</span></span> <span data-ttu-id="524b7-134">O Gerenciador de modelos está disponível no menu **Exibir** e inclui modelos para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o e o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="524b7-134">Template Explorer is available on the **View** menu and includes templates for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], and [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="524b7-135">Para obter mais informações, consulte [Usar modelos do Analysis Services no SQL Server Management Studio](use-analysis-services-templates-in-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="524b7-135">For more information, see [Use Analysis Services Templates in SQL Server Management Studio](use-analysis-services-templates-in-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524b7-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="524b7-136">See Also</span></span>  
 <span data-ttu-id="524b7-137">[Criando modelos multidimensionais usando o SQL Server Data Tools &#40;SSDT&#41;](../multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="524b7-137">[Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;](../multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span></span>  
 <span data-ttu-id="524b7-138">[Expressões multidimensionais &#40;referência de&#41; MDX](/sql/mdx/multidimensional-expressions-mdx-reference) </span><span class="sxs-lookup"><span data-stu-id="524b7-138">[Multidimensional Expressions &#40;MDX&#41; Reference](/sql/mdx/multidimensional-expressions-mdx-reference) </span></span>  
 <span data-ttu-id="524b7-139">[Referência de&#41; &#40;DMX de extensões de mineração de dados](/sql/dmx/data-mining-extensions-dmx-reference) </span><span class="sxs-lookup"><span data-stu-id="524b7-139">[Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference) </span></span>  
 <span data-ttu-id="524b7-140">[Analysis Services linguagem de script &#40;referência de&#41; do ASSL](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span><span class="sxs-lookup"><span data-stu-id="524b7-140">[Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span></span>  
 [<span data-ttu-id="524b7-141">Analysis Services linguagem de script &#40;referência de&#41; do ASSL</span><span class="sxs-lookup"><span data-stu-id="524b7-141">Analysis Services Scripting Language &#40;ASSL&#41; Reference</span></span>](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla)  
  
  