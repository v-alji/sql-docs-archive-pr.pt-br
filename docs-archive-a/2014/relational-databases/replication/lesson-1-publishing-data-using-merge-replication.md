---
title: 'Lição 1: Publicando dados usando a replicação de mesclagem | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: c3c6e0b6-54cd-4b7d-8efb-2cefe14fcd7f
author: rothja
ms.author: jroth
ms.openlocfilehash: ba1d8829d84c02d1436013af80de4bf0979049e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683493"
---
# <a name="lesson-1-publishing-data-using-merge-replication"></a><span data-ttu-id="2052c-102">Lição 1: Publicando dados usando replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="2052c-102">Lesson 1: Publishing Data Using Merge Replication</span></span>
  <span data-ttu-id="2052c-103"> Nesta lição, você aprenderá a criar uma publicação de mesclagem usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para publicar um subconjunto das tabelas **Employee**, **SalesOrderHeader** e **SalesOrderDetail** no banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2052c-103">In this lesson, you will create a merge publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a subset of the **Employee**, **SalesOrderHeader**, and **SalesOrderDetail** tables in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="2052c-104">Essas tabelas são filtradas com filtros de linha com parâmetros de modo que cada assinatura contenha uma partição exclusiva dos dados.</span><span class="sxs-lookup"><span data-stu-id="2052c-104">These tables are filtered with parameterized row filters so that each subscription contains a unique partition of the data.</span></span> <span data-ttu-id="2052c-105">Você também adicionará o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado pelo Agente de Mesclagem à PAL (lista de acesso à publicação).</span><span class="sxs-lookup"><span data-stu-id="2052c-105">You will also add the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Merge Agent to the publication access list (PAL).</span></span> <span data-ttu-id="2052c-106">Este tutorial exige a conclusão do tutorial anterior, [Preparando o servidor para replicação](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="2052c-106">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="2052c-107">Para criar uma publicação e definir artigos</span><span class="sxs-lookup"><span data-stu-id="2052c-107">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="2052c-108">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="2052c-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="2052c-109">Expanda a pasta **Replicação** , clique com o botão direito do mouse em **Publicações Locais**e clique em **Nova Publicação**.</span><span class="sxs-lookup"><span data-stu-id="2052c-109">Expand the **Replication** folder, right-click **Local Publications**, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="2052c-110">O Assistente de Configuração de Publicação é inicializado.</span><span class="sxs-lookup"><span data-stu-id="2052c-110">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="2052c-111">Na página Banco de Dados de Publicação, selecione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2052c-111">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2052c-112">Na página Tipo de Publicação, selecione **Publicação de mesclagem**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2052c-112">On the Publication Type page, select **Merge publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="2052c-113">Na página Tipos de Assinante, verifique se somente o [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou posterior está selecionado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2052c-113">On the Subscriber Types page, ensure that only [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later is selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="2052c-114">Na página Artigos, expanda o nó **Tabelas** e selecione **SalesOrderHeader** e **SalesOrderDetail**; a seguir, expanda **Employee**, selecione **EmployeeID** ou **LoginID**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2052c-114">On the Articles page, expand the **Tables** node, select **SalesOrderHeader** and **SalesOrderDetail**, then expand **Employee**, select **EmployeeID** or **LoginID**, and then click **Next**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="2052c-115">As colunas adicionais necessárias são selecionadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2052c-115">Additional required columns are automatically selected.</span></span> <span data-ttu-id="2052c-116">Selecione uma das colunas selecionadas automaticamente e exiba a observação abaixo da lista **Objetos para publicação** para obter uma explicação do porquê a coluna é necessária.</span><span class="sxs-lookup"><span data-stu-id="2052c-116">Select any of  the automatically selected columns and view the note below the **Objects to publish** list for an explanation why the column is required.</span></span>  
  
7.  <span data-ttu-id="2052c-117">Na página Linhas de Tabela de Filtro, clique em **Adicionar** e em **Adicionar Filtro**.</span><span class="sxs-lookup"><span data-stu-id="2052c-117">On the Filter Table Rows page, click **Add** and then click **Add Filter**.</span></span>  
  
8.  <span data-ttu-id="2052c-118">Na caixa de diálogo **Adicionar Filtro** , selecione **Employee (HumanResources)** em **Selecionar a tabela a ser filtrada**, clique na coluna **LoginID** , clique na seta para a direita a fim de adicionar a coluna à cláusula WHERE da consulta de filtro e modifique a cláusula WHERE da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2052c-118">In the **Add Filter** dialog box, select **Employee (HumanResources)** in **Select the table to filter**, click the **LoginID** column, click the right arrow to add the column to the WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [LoginID] = HOST_NAME()  
    ```  
  
9. <span data-ttu-id="2052c-119">Clique em **Uma linha desta tabela irá para apenas uma assinatura**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2052c-119">Click **A row from this table will go to only one subscription**, and click **OK**.</span></span>  
  
10. <span data-ttu-id="2052c-120">Na página **Filtrar Linhas da Tabela** , clique em **Funcionário (Recursos Humanos)**, clique em **Adicionar** e clique em **Adicionar Junção para Estender o Filtro Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="2052c-120">On the **Filter Table Rows** page, click **Employee (Human Resources)**, click **Add,** and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
11. <span data-ttu-id="2052c-121">Na caixa de diálogo **Adicionar Junção** , selecione **Sales.SalesOrderHeader** sob **Tabela unida**, clique em **Gravar a instrução de junção manualmente**e conclua a instrução de junção da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="2052c-121">In the **Add Join** dialog box, select **Sales.SalesOrderHeader** under **Joined table**, click **Write the join statement manually**, and complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
    ```  
  
12. <span data-ttu-id="2052c-122">Em **Especificar opções de junção**, selecione **Chave exclusiva**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2052c-122">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="2052c-123">Na página Linhas de Tabela de Filtro, clique em **SalesOrderHeader**, **Adicionar**e em **Adicionar Junção para Estender o Filtro Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="2052c-123">On the Filter Table Rows page, click **SalesOrderHeader**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
14. <span data-ttu-id="2052c-124">Na caixa de diálogo **Adicionar Junção** , selecione **Sales.SalesOrderDetail** sob **Tabela unida**.</span><span class="sxs-lookup"><span data-stu-id="2052c-124">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**.</span></span>  
  
15. <span data-ttu-id="2052c-125">Clique em **Gravar a instrução de junção manualmente**.</span><span class="sxs-lookup"><span data-stu-id="2052c-125">Click **Write the join statement manually**.</span></span>  
  
16. <span data-ttu-id="2052c-126">Em **Colunas da tabela filtrada**, selecione **BusinessEntityID**e clique no botão de seta para copiar o nome da coluna na instrução de junção.</span><span class="sxs-lookup"><span data-stu-id="2052c-126">In **Filtered table columns**, select **BusinessEntityID**, then click the arrow button to copy the column name to the loin statement.</span></span>  
  
17. <span data-ttu-id="2052c-127">Na caixa **Instrução de junção** , preencha a instrução de junção da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2052c-127">In the **Join statement** box, complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.BusinessEntityID = SalesOrderHeader.SalesPersonID  
    ```  
  
18. <span data-ttu-id="2052c-128">Em **Especificar opções de junção**, selecione **Chave exclusiva**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2052c-128">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="2052c-129">Na página **Filtrar Linhas da Tabela** , clique em **SalesOrderHeader (Sales)**, **Adicionar**e em **Adicionar Junção para Estender o Filtro Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="2052c-129">On the **Filter Table Rows** page, click **SalesOrderHeader (Sales)**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
20. <span data-ttu-id="2052c-130">Na caixa de diálogo **Adicionar Junção** , selecione **Sales.SalesOrderDetail** sob **Tabela unida**, clique em **OK**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2052c-130">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**, click **OK**, and then click **Next**.</span></span>  
  
21. <span data-ttu-id="2052c-131">Selecione **Criar um instantâneo imediatamente**, desmarque a opção **Agendar o agente de instantâneo para ser executado nos seguintes momentos**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2052c-131">Select **Create a snapshot immediately**, clear **Schedule the snapshot agent to run at the following times**, and click **Next**.</span></span>  
  
22. <span data-ttu-id="2052c-132">Na página segurança do agente, clique em **configurações de segurança**, digite \<_Machine_Name> _**\ repl_snapshot** na caixa **conta de processo** , forneça a senha dessa conta e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2052c-132">On the Agent Security page, click **Security Settings**, type \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span> <span data-ttu-id="2052c-133">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2052c-133">Click **Finish**.</span></span>  
  
23. <span data-ttu-id="2052c-134">Na página Concluir o Assistente, insira **AdvWorksSalesOrdersMerge** na caixa **Nome da publicação** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2052c-134">On the Complete the Wizard page, enter **AdvWorksSalesOrdersMerge** in the **Publication name** box and click **Finish**.</span></span>  
  
24. <span data-ttu-id="2052c-135">Depois que a publicação for criada, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="2052c-135">After the publication is created, click **Close**.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="2052c-136">Para exibir o status de geração do instantâneo</span><span class="sxs-lookup"><span data-stu-id="2052c-136">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="2052c-137">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda o nó do servidor e expanda a pasta **replicação** .</span><span class="sxs-lookup"><span data-stu-id="2052c-137">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="2052c-138">Na pasta Publicações Locais, clique com o botão direito do mouse em **AdvWorksSalesOrdersMerge**e clique em **Exibir Status do Agente de Instantâneo**.</span><span class="sxs-lookup"><span data-stu-id="2052c-138">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="2052c-139">O status atual do trabalho do Snapshot Agent para a publicação é exibido.</span><span class="sxs-lookup"><span data-stu-id="2052c-139">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="2052c-140">Certifique-se de que o trabalho de instantâneo teve sucesso antes de passar à próxima lição.</span><span class="sxs-lookup"><span data-stu-id="2052c-140">Ensure that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-merge-agent-login-to-the-pal"></a><span data-ttu-id="2052c-141">Para adicionar o logon do Merge Agent à PAL</span><span class="sxs-lookup"><span data-stu-id="2052c-141">To add the Merge Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="2052c-142">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda o nó do servidor e expanda a pasta **replicação** .</span><span class="sxs-lookup"><span data-stu-id="2052c-142">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="2052c-143">Na pasta Publicações Locais, clique com o botão direito do mouse em **AdvWorksSalesOrdersMerge**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2052c-143">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="2052c-144">A caixa de diálogo **Propriedades da Publicação** é exibida.</span><span class="sxs-lookup"><span data-stu-id="2052c-144">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="2052c-145">Selecione a página **Lista de Acesso à Publicação** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2052c-145">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="2052c-146">Na caixa de diálogo Adicionar Acesso à Publicação, selecione _<Machine_Name>_**\repl_merge** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2052c-146">In the Add Publication Access dialog box, select _<Machine_Name>_**\repl_merge** and click **OK**.</span></span> <span data-ttu-id="2052c-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2052c-147">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2052c-148">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2052c-148">Next Steps</span></span>  
 <span data-ttu-id="2052c-149">Você criou a publicação de mesclagem com sucesso.</span><span class="sxs-lookup"><span data-stu-id="2052c-149">You have successfully created the merge publication.</span></span> <span data-ttu-id="2052c-150">A seguir, você assinará essa publicação.</span><span class="sxs-lookup"><span data-stu-id="2052c-150">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="2052c-151">Consulte [Lição 2: Criando uma assinatura na publicação de mesclagem](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="2052c-151">See [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2052c-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2052c-152">See Also</span></span>  
 <span data-ttu-id="2052c-153">[Filtrar os dados publicados](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="2052c-153">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="2052c-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="2052c-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="2052c-155">Defina um Artigo</span><span class="sxs-lookup"><span data-stu-id="2052c-155">Define an Article</span></span>](publish/define-an-article.md)  
  
  
