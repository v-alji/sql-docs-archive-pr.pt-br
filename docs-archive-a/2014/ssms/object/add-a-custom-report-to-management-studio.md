---
title: Adicionar um relatório personalizado ao Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 3cf8d726-0a90-4f80-98d0-352a2a59be0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07263edfb9b255257e0c79733c2c34b279b61cd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568321"
---
# <a name="add-a-custom-report-to-management-studio"></a><span data-ttu-id="dbbd7-102">adicionar um relatório personalizado ao Management Studio</span><span class="sxs-lookup"><span data-stu-id="dbbd7-102">Add a Custom Report to Management Studio</span></span>
  <span data-ttu-id="dbbd7-103">Esse tópico descreve como criar um relatório simples do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que é salvo como um arquivo .rdl e, em seguida, adicionar esse arquivo rdl ao [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] como um relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-103">This topic describes how to create a simple [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report that is saved as an .rdl file, and then add that rdl file to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a custom report.</span></span> [!INCLUDE[ssRS](../../includes/ssrs.md)] <span data-ttu-id="dbbd7-104">pode criar um ampla variedade de relatórios sofisticados.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-104">can create a wide variety of sophisticated reports.</span></span> <span data-ttu-id="dbbd7-105">Para criar um relatório com o uso desse tópico, o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] deve estar instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-105">To create a report by using this topic, you must have [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] installed on the computer.</span></span> <span data-ttu-id="dbbd7-106">Não é necessário instalar o [!INCLUDE[ssRS](../../includes/ssrs.md)] no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para executar um relatório personalizado com o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbbd7-106">You do not have to install [!INCLUDE[ssRS](../../includes/ssrs.md)] on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run a custom report using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
  
### <a name="to-create-a-simple-report-saved-as-an-rdl-file"></a><span data-ttu-id="dbbd7-107">Para criar um relatório simples salvo como um arquivo .rdl</span><span class="sxs-lookup"><span data-stu-id="dbbd7-107">To create a simple report saved as an .rdl file</span></span>  
  
1.  <span data-ttu-id="dbbd7-108">Clique em **Iniciar**, aponte para **Programas**, **Microsoft SQL Server**e clique em **Ferramentas de Dados do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-108">Click **Start**, point to **Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="dbbd7-109">No menu **Arquivo** , aponte para **Novo**e clique em **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-109">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="dbbd7-110">Na lista **Tipos de Projeto** , clique em **Projetos de Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-110">In the **Project Types** list, click **Business Intelligence Projects**.</span></span>  
  
4.  <span data-ttu-id="dbbd7-111">Na lista **Modelos** , clique em **Assistente de Projeto do Servidor de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-111">In the **Templates** list, click **Report Server Project Wizard**.</span></span>  
  
5.  <span data-ttu-id="dbbd7-112">Em **Nome**, digite **ConnectionsReport**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-112">In **Name**, type **ConnectionsReport**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="dbbd7-113">Na página de introdução do **Assistente de Relatório** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-113">On the **Report Wizard** introduction page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="dbbd7-114">Na página **Selecionar Fonte de Dados** , na caixa Nome, digite um nome para essa conexão com o [!INCLUDE[ssDE](../../includes/ssde-md.md)]e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-114">On the **Select the Data Source** page, in the Name box type a name for this connection to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Edit**.</span></span>  
  
8.  <span data-ttu-id="dbbd7-115">Na caixa de diálogo **Propriedades da Conexão** , na caixa **Nome do servidor** , digite o nome da sua instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbbd7-115">In the **Connection Properties** dialog box, in the **Server name** box, type the name of your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
9. <span data-ttu-id="dbbd7-116">Na caixa **Selecionar ou digitar um nome de banco de dados** , digite o nome de qualquer banco de dados no seu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], como [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-116">In the **Select or enter a database name** box, type the name of any database on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
10. <span data-ttu-id="dbbd7-117">Na página **Selecionar Fonte de Dados** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-117">On the **Select the Data Source** page, click **Next**.</span></span>  
  
11. <span data-ttu-id="dbbd7-118">Na página **Criar Consulta** , na caixa **Cadeia de caracteres de consulta** , digite a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir que lista as conexões atuais com o [!INCLUDE[ssDE](../../includes/ssde-md.md)]e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-118">On the **Design the Query** page, in the **Query string** box, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that lists the current connections to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Next**.</span></span> <span data-ttu-id="dbbd7-119">A caixa de cadeia de caracteres de Consulta do Assistente de Relatório não aceita parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-119">The Report Wizard Query string box will not accept report parameters.</span></span> <span data-ttu-id="dbbd7-120">Relatórios personalizados mais complexos devem ser criados manualmente.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-120">More complex custom reports must be created manually.</span></span>  
  
     `SELECT session_id, net_transport FROM sys.dm_exec_connections;`  
  
12. <span data-ttu-id="dbbd7-121">Na página **Selecionar Tipo de Relatório** , selecione **Tabular**e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-121">On the **Select the Report Type** page, select **Tabular**, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="dbbd7-122">Na página **Concluindo o Assistente** , na caixa **Nome do relatório** , digite **ConnectionsReport**e clique em **Concluir** para criar e salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-122">On the **Completing the Wizard** page, in the **Report name** box, type **ConnectionsReport**, and then click **Finish** to create and save the report.</span></span>  
  
14. <span data-ttu-id="dbbd7-123">Feche o [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbbd7-123">Close [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
15. <span data-ttu-id="dbbd7-124">Copie **ConnectionsReport.rdl** para uma pasta que você criou no servidor de banco de dados para relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-124">Copy **ConnectionsReport.rdl** to a folder that you created on the database server for custom reports.</span></span>  
  
### <a name="to-add-a-report-to-management-studio"></a><span data-ttu-id="dbbd7-125">Para adicionar um relatório ao Management Studio</span><span class="sxs-lookup"><span data-stu-id="dbbd7-125">To add a report to Management Studio</span></span>  
  
-   <span data-ttu-id="dbbd7-126">No [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], clique com o botão direito do mouse em um nó no Pesquisador de Objetos, aponte para **Relatórios**e clique em **Relatórios Personalizados**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-126">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click a node in Object Explorer, point to **Reports**, click **Custom Reports**.</span></span> <span data-ttu-id="dbbd7-127">Na caixa de diálogo **Abrir Arquivo** , localize a pasta de relatórios personalizados, selecione o arquivo **ConnectionsReport.rdl** e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-127">In the **Open File** dialog box, locate the custom reports folder and select the **ConnectionsReport.rdl** file, and then click **Open**.</span></span>  
  
     <span data-ttu-id="dbbd7-128">Quando um novo relatório personalizado é aberto pela primeira vez de um nó do Pesquisador de Objetos, esse relatório é adicionado à lista dos relatórios usados mais recentemente, em **Relatórios Personalizados** no menu de atalho desse nó.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-128">When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node.</span></span> <span data-ttu-id="dbbd7-129">Quando um relatório padrão é aberto pela primeira vez, ele também é exibido nessa lista, em **Relatórios Personalizados**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-129">When a standard report is opened for the first time, it will also appear on the most recently used list under **Custom Reports**.</span></span> <span data-ttu-id="dbbd7-130">Se um relatório personalizado for excluído, na próxima vez que ele for selecionado, será exibido um prompt para excluir o item da lista de relatórios usados mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-130">If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.</span></span>  
  
    1.  <span data-ttu-id="dbbd7-131">Para alterar o número de arquivos exibidos na lista de itens usados recentemente, no menu **Ferramentas** , clique em **Opções** , expanda a pasta **Ambiente** e clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-131">To change the number of files that are displayed on the recently used list, on the **Tools** menu, click **Options,** expand the **Environment** folder, and then click **General**.</span></span>  
  
    2.  <span data-ttu-id="dbbd7-132">Ajuste o número para **Exibir arquivos na lista dos usados recentemente**.</span><span class="sxs-lookup"><span data-stu-id="dbbd7-132">Adjust the number for **Display files in recently used list**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbbd7-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dbbd7-133">See Also</span></span>  
 <span data-ttu-id="dbbd7-134">[Relatórios personalizados no Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="dbbd7-134">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="dbbd7-135">[Usar relatórios personalizados com propriedades de nó do pesquisador de objetos](use-custom-reports-with-object-explorer-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="dbbd7-135">[Use Custom Reports with Object Explorer Node Properties](use-custom-reports-with-object-explorer-node-properties.md) </span></span>  
 <span data-ttu-id="dbbd7-136">[Cancelar supressão de executar avisos de relatório personalizado](unsuppress-run-custom-report-warnings.md) </span><span class="sxs-lookup"><span data-stu-id="dbbd7-136">[Unsuppress Run Custom Report Warnings](unsuppress-run-custom-report-warnings.md) </span></span>  
 [<span data-ttu-id="dbbd7-137">Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dbbd7-137">Reporting Services &#40;SSRS&#41;</span></span>](../../reporting-services/create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
