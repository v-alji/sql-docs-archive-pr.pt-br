---
title: Salvar scripts como projetos ou soluções | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 72dfd37f-dbe7-4d1d-bda6-7eb54c7922d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9fade3900c8859f211bb0c66820dc97792262481
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681314"
---
# <a name="save-scripts-as-projects-or-solutions"></a><span data-ttu-id="7f3a8-102">Salvar scripts como projetos ou soluções</span><span class="sxs-lookup"><span data-stu-id="7f3a8-102">Save Scripts as Projects or Solutions</span></span>
  <span data-ttu-id="7f3a8-103">Desenvolvedores familiarizados com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio darão as boas-vindas ao Gerenciador de Soluções no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3a8-103">Developers familiar with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio will welcome Solution Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7f3a8-104">Os scripts que dão suporte a seu negócio podem ser agrupados em projetos de script e os projetos de script podem ser administrados juntos, como uma solução.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-104">The scripts that support your business can be grouped into script projects, and the script projects can be managed together as a solution.</span></span> <span data-ttu-id="7f3a8-105">Quando os scripts são colocados em projetos de script e soluções, eles podem ser abertos em conjunto, como um grupo, ou salvos em conjunto em um produto de controle de código-fonte, como o Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-105">When scripts are placed in script projects and solutions they can be opened together as a group, or saved together to a source control product such as Visual SourceSafe.</span></span> <span data-ttu-id="7f3a8-106">Projetos de script incluem as informações de conexão dos scripts para serem executados corretamente, e podem incluir arquivos diferentes (não script), como um arquivo de texto de suporte.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-106">Script projects include the connection information for the scripts to execute properly, and can include non-script files such as a supporting text file.</span></span>  
  
 <span data-ttu-id="7f3a8-107">O procedimento a seguir cria um script curto que consulta o banco de dados do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , colocado em um projeto de script ou em uma solução.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-107">The following practice creates a short script that queries the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, placed in a script project and solution.</span></span>  
  
## <a name="using-script-projects-and-solutions"></a><span data-ttu-id="7f3a8-108">Utilizando projetos de script e soluções</span><span class="sxs-lookup"><span data-stu-id="7f3a8-108">Using Script Projects and Solutions</span></span>  
  
#### <a name="to-create-a-script-project-and-solution"></a><span data-ttu-id="7f3a8-109">Para criar um projeto de script e uma solução</span><span class="sxs-lookup"><span data-stu-id="7f3a8-109">To create a script project and solution</span></span>  
  
1.  <span data-ttu-id="7f3a8-110">Abra o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e faça a conexão com um servidor usando o Pesquisador de Objetos.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-110">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and connect to a server with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="7f3a8-111">No menu **Arquivo** , aponte para **Novo**e clique em **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-111">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="7f3a8-112">A caixa de diálogo **Novo Projeto** será aberta.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7f3a8-113">Na caixa de texto **Nome** , digite **StatusCheck**, clique em **Scripts do SQL Server** em **Modelos**e clique em **OK** para abrir uma nova solução e projeto de script.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-113">In the **Name** text box, type **StatusCheck**, click **SQL Server Scripts** in **Templates**, and then click **OK** to open a new solution and script project.</span></span>  
  
4.  <span data-ttu-id="7f3a8-114">No Gerenciador de Soluções, clique com o botão direito do mouse em **Conexões**e clique em **Nova Conexão**.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-114">In Solution Explorer, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="7f3a8-115">A caixa de diálogo **Conectar ao Servidor** é exibida.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-115">The **Connect to Server** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="7f3a8-116">Na caixa de listagem **Nome do servidor** , digite o nome de seu servidor.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-116">In the **Server name** list box, type the name of your server.</span></span>  
  
6.  <span data-ttu-id="7f3a8-117">Clique em **Opções**e clique na guia **Propriedades da Conexão** .</span><span class="sxs-lookup"><span data-stu-id="7f3a8-117">Click **Options**, and then click the **Connection Properties** tab.</span></span>  
  
7.  <span data-ttu-id="7f3a8-118">Na caixa **Conectar ao banco de dados** , procure o servidor, selecione o banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-118">In the **Connect to database** box, browse the server, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then click **Connect**.</span></span> <span data-ttu-id="7f3a8-119">As informações de conexão, incluindo o banco de dados, são adicionadas ao projeto.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-119">The connection information including the database is added to the project.</span></span>  
  
8.  <span data-ttu-id="7f3a8-120">Se a janela Propriedades não for exibida, clique na nova conexão no Gerenciador de Soluções e pressione F4.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-120">If the Properties window is not displayed, click the new connection in Solution Explorer, and then press F4.</span></span> <span data-ttu-id="7f3a8-121">As propriedades da conexão são exibidas e mostram informações sobre a conexão, incluindo o **Banco de Dados Inicial** como [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3a8-121">The properties for the connection appear, and show information about the connection including the **Initial Database** as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
9. <span data-ttu-id="7f3a8-122">No Gerenciador de Soluções, clique com o botão direito do mouse na conexão e clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-122">In Solution Explorer, right-click the connection, and then click **New Query**.</span></span> <span data-ttu-id="7f3a8-123">Uma nova consulta chamada **SQLQuery1.sql** é criada, conectada ao banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] em seu servidor e adicionada ao projeto de script.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-123">A new query called **SQLQuery1.sql** is created, connected to the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database on your server, and added to your script project.</span></span>  
  
10. <span data-ttu-id="7f3a8-124">No Editor de Consultas, digite a seguinte consulta para determinar quantos pedidos possuem datas de vencimento anteriores às datas de início dos pedidos.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-124">In Query Editor, type the following query to determine how many work orders have due dates, before the work order starting dates.</span></span> <span data-ttu-id="7f3a8-125">(Você pode copiar e colar o código da janela Tutorial.)</span><span class="sxs-lookup"><span data-stu-id="7f3a8-125">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT COUNT(WorkOrderID)  
    FROM Production.WorkOrder  
    WHERE DueDate < StartDate;  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="7f3a8-126">Se você precisar de mais espaço para inserir sua consulta, pressione SHIFT+ALT+ENTER, para alternar para o modo de tela inteira.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-126">If you need more room to type your query, press SHIFT+ALT+ENTER, to switch to full-screen mode.</span></span>  
  
11. <span data-ttu-id="7f3a8-127">No Gerenciador de Soluções, clique com o botão direito do mouse em **SQLQuery1**e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-127">In Solution Explorer, right-click **SQLQuery1**, and then click **Rename**.</span></span> <span data-ttu-id="7f3a8-128">Digite **verificar ordens de entrada. SQL** como o novo nome da consulta e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-128">Type **Check Workorders.sql** as the new name for the query and press ENTER.</span></span>  
  
12. <span data-ttu-id="7f3a8-129">Para salvar a solução e o projeto de script, no menu **Arquivo** , clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-129">To save your solution and script project, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7f3a8-130">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="7f3a8-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7f3a8-131">Resumo: Soluções e Projetos de Script</span><span class="sxs-lookup"><span data-stu-id="7f3a8-131">Summary: Solutions and Script Projects</span></span>](lesson-3-4-summary-solutions-and-script-projects.md)  
  
  
