---
title: 'Lição 1: Criando um projeto do servidor de relatório (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 675671ca-e6c9-48a2-82e9-386778f3a49f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a708e5114344e87edd620ef58bc50594a9b9ef8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686103"
---
# <a name="lesson-1-creating-a-report-server-project-reporting-services"></a><span data-ttu-id="39842-102">Lição 1: Criando um projeto do servidor de relatórios (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="39842-102">Lesson 1: Creating a Report Server Project (Reporting Services)</span></span>
  <span data-ttu-id="39842-103">Para criar um relatório no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], primeiro crie um projeto de servidor de relatório em que o arquivo de definição de relatório (.rdl) e qualquer outro arquivo de recursos que seja necessário sejam salvos para o relatório.</span><span class="sxs-lookup"><span data-stu-id="39842-103">To create a report in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you must first create a report server project where you will save your report definition (.rdl) file and any other resource files that you need for your report.</span></span> <span data-ttu-id="39842-104">Em seguida, você criará o arquivo de definição do relatório real, definirá uma fonte de dados para o relatório, um conjunto de dados e o layout do relatório.</span><span class="sxs-lookup"><span data-stu-id="39842-104">Then you will create the actual report definition file, define a data source for your report, define a dataset, and define the report layout.</span></span> <span data-ttu-id="39842-105">Quando você executar o relatório, os dados reais serão recuperados e combinados com o layout e renderizados na tela, de onde ele poderá ser exportado, impresso ou salvo.</span><span class="sxs-lookup"><span data-stu-id="39842-105">When you run the report, the actual data is retrieved and combined with the layout, and then rendered on your screen, from where you can export it, print it, or save it.</span></span>  
  
 <span data-ttu-id="39842-106">Nesta lição, você obterá informações sobre como criar um projeto de servidor de relatório no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39842-106">In this lesson, you will learn how to create a report server project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="39842-107">Um projeto de servidor de relatório é usado para criar relatórios que são executados em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="39842-107">A report server project is used to create reports that run on a report server.</span></span>  
  
### <a name="to-create-a-report-server-project"></a><span data-ttu-id="39842-108">Para criar um projeto do servidor de relatórios</span><span class="sxs-lookup"><span data-stu-id="39842-108">To create a report server project</span></span>  
  
1.  <span data-ttu-id="39842-109">Clique em **Iniciar**, aponte para **todos os programas**, aponte para [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] e clique em **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="39842-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)], and then click **SQL Server Data Tools**.</span></span> <span data-ttu-id="39842-110">Se esta for a primeira vez que você abriu [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , clique em **configurações de Business Intelligence** para as configurações de ambiente padrão.</span><span class="sxs-lookup"><span data-stu-id="39842-110">If this is the first time you have opened [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Business Intelligence Settings** for the default environment settings.</span></span>  
  
2.  <span data-ttu-id="39842-111">No menu **Arquivo** , aponte para **Novo**e clique em **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="39842-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="39842-112">Na lista **Modelos Instalados** , clique em **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="39842-112">In the **Installed Templates** list, click **Business Intelligence**.</span></span>  
  
4.  <span data-ttu-id="39842-113">Clique em **projeto do servidor de relatório**.</span><span class="sxs-lookup"><span data-stu-id="39842-113">Click **Report Server Project**.</span></span>  
  
5.  <span data-ttu-id="39842-114">Em **Nome**, digite **Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="39842-114">In **Name**, type **Tutorial**.</span></span>  
  
6.  <span data-ttu-id="39842-115">Clique em **OK** para criar o projeto.</span><span class="sxs-lookup"><span data-stu-id="39842-115">Click **OK** to create the project.</span></span>  
  
     <span data-ttu-id="39842-116">O projeto Tutorial é exibido no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="39842-116">The Tutorial project is displayed in Solution Explorer.</span></span>  
  
### <a name="to-create-a-new-report-definition-file"></a><span data-ttu-id="39842-117">Para criar um novo arquivo de definição de relatório</span><span class="sxs-lookup"><span data-stu-id="39842-117">To create a new report definition file</span></span>  
  
1.  <span data-ttu-id="39842-118">Em Gerenciador de Soluções, clique com o botão direito do mouse em **relatórios**, aponte para **Adicionar**e clique em **novo item**.</span><span class="sxs-lookup"><span data-stu-id="39842-118">In Solution Explorer, right-click **Reports**, point to **Add**, and click **New Item**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="39842-119">Se a janela **Gerenciador de Soluções** não estiver visível, no menu **Exibir** , clique em **Gerenciador de Soluções**.</span><span class="sxs-lookup"><span data-stu-id="39842-119">If the **Solution Explorer** window is not visible, from the **View** menu, click **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="39842-120">Na caixa de diálogo **Adicionar novo item** , em **modelos**, clique em **relatório**.</span><span class="sxs-lookup"><span data-stu-id="39842-120">In the **Add New Item** dialog box, under **Templates**, click **Report**.</span></span>  
  
3.  <span data-ttu-id="39842-121">Em **Nome**, digite **Sales Orders.rdl** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="39842-121">In **Name**, type **Sales Orders.rdl** and then click **Add**.</span></span>  
  
     <span data-ttu-id="39842-122">O Designer de Relatórios abre e exibe o novo arquivo .rdl na exibição Design.</span><span class="sxs-lookup"><span data-stu-id="39842-122">Report Designer opens and displays the new .rdl file in Design view.</span></span>  
  
 <span data-ttu-id="39842-123">O Designer de Relatórios é um componente do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] que é executado no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39842-123">Report Designer is a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] component that runs in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="39842-124">Ele tem duas exibições: **Design** e **Visualização**.</span><span class="sxs-lookup"><span data-stu-id="39842-124">It has two views: **Design** and **Preview**.</span></span> <span data-ttu-id="39842-125">Clique em cada guia para alterar exibições.</span><span class="sxs-lookup"><span data-stu-id="39842-125">Click each tab to change views.</span></span>  
  
 <span data-ttu-id="39842-126">Você define os dados no painel **Dados do Relatório** .</span><span class="sxs-lookup"><span data-stu-id="39842-126">You define your data in the **Report Data** pane.</span></span> <span data-ttu-id="39842-127">Você define o layout do relatório no modo **Design** .</span><span class="sxs-lookup"><span data-stu-id="39842-127">You define your report layout in **Design** view.</span></span> <span data-ttu-id="39842-128">É possível executar o relatório e ver sua aparência na exibição **Visualização** .</span><span class="sxs-lookup"><span data-stu-id="39842-128">You can run the report and see what it looks like in **Preview** view.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="39842-129">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="39842-129">Next Task</span></span>  
 <span data-ttu-id="39842-130">Você criou um projeto de relatório chamado "Tutorial" e adicionou um arquivo de definição de relatório (.rdl) ao projeto de relatório com êxito.</span><span class="sxs-lookup"><span data-stu-id="39842-130">You have successfully created a report project called "Tutorial" and added a report definition (.rdl) file to the report project.</span></span> <span data-ttu-id="39842-131">Em seguida, você especificará uma fonte de dados para usar para o relatório.</span><span class="sxs-lookup"><span data-stu-id="39842-131">Next, you will specify a data source to use for the report.</span></span> <span data-ttu-id="39842-132">Consulte [Lição 2: Especificando informações de conexão &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="39842-132">See [Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39842-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39842-133">See Also</span></span>  
 [<span data-ttu-id="39842-134">Criar um relatório de tabela básico &#40;Tutorial do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="39842-134">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
