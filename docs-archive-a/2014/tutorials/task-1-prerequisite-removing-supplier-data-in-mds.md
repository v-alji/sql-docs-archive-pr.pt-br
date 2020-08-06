---
title: 'Tarefa 1 (pré-requisito): removendo dados do fornecedor no MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6f0a4287-7fd4-4f18-b7e4-a5191a9d4a3c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e78dc5ff04f95d42cf440e3f80b1b349e0315a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581645"
---
# <a name="task-1-prerequisite-removing-supplier-data-in-mds"></a><span data-ttu-id="f2c67-102">Tarefa 1 (pré-requisito): Removendo os dados do fornecedor no MDS</span><span class="sxs-lookup"><span data-stu-id="f2c67-102">Task 1 (Prerequisite): Removing Supplier Data in MDS</span></span>
  <span data-ttu-id="f2c67-103">Nesta tarefa, você removerá os dados do fornecedor armazenados no MDS.</span><span class="sxs-lookup"><span data-stu-id="f2c67-103">In this task, you remove the supplier data stored in MDS.</span></span> <span data-ttu-id="f2c67-104">Você carregou os dados manualmente usando **Suplemento MDS do Excel** na lição anterior.</span><span class="sxs-lookup"><span data-stu-id="f2c67-104">You uploaded the data manually using **MDS Excel Add-in** in the previous lesson.</span></span> <span data-ttu-id="f2c67-105">O pacote SSIS que será criado nesta lição carregará automaticamente os dados no MDS para você.</span><span class="sxs-lookup"><span data-stu-id="f2c67-105">The SSIS package you create in this lesson will automatically upload the data to MDS for you.</span></span> <span data-ttu-id="f2c67-106">Consequentemente, antes de testar o pacote SSIS, será necessário remover os dados do fornecedor do MDS, remover da hierarquia derivada, remover entidades de fornecedor e estado e criar a entidade do fornecedor sem dados.</span><span class="sxs-lookup"><span data-stu-id="f2c67-106">Therefore, before testing the SSIS package, you need to remove the supplier data from MDS, remove the derived hierarchy, remove supplier and state entities, and create the supplier entity with no data.</span></span>  
  
1.  <span data-ttu-id="f2c67-107">Inicie o **Master Data Manager** navegando até `http://localhost/MDS` o site e o aplicativo que você especificou ao configurar o MDS.</span><span class="sxs-lookup"><span data-stu-id="f2c67-107">Launch **Master Data Manager** by navigating to `http://localhost/MDS` or the website and application you specified when configuring MDS.</span></span> <span data-ttu-id="f2c67-108">Se você tiver mantido o **Master Data Manager** aberto, clique em **SQL Server 2012 Master Data Services** na parte superior para alternar para a **home page**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-108">If you kept the **Master Data Manager** open, click **SQL Server 2012 Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="f2c67-109">Clique em **Administração do Sistema** na seção **Tarefas Administrativas** .</span><span class="sxs-lookup"><span data-stu-id="f2c67-109">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="f2c67-110">Passe o mouse sobre **Gerenciar** no menu e clique em **Hierarquias Derivadas**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-110">Hover the mouse over **Manage** on the menu and click **Derived Hierarchies**.</span></span> <span data-ttu-id="f2c67-111">É necessário excluir a hierarquia derivada **SuppliersInState** antes de excluir as entidades no modelo **Fornecedores** .</span><span class="sxs-lookup"><span data-stu-id="f2c67-111">You need to delete the derived hierarchy **SuppliersInState** before deleting the entities in the **Suppliers** model.</span></span>  
  
4.  <span data-ttu-id="f2c67-112">Selecione **SuppliersInState** na lista **Hierarquia Derivada** e clique no botão **X (Excluir)** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="f2c67-112">Select **SuppliersInState** from the **Derived Hierarchy** list and click **X (Delete)** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="f2c67-113">Clique em **OK** para confirmar a exclusão.</span><span class="sxs-lookup"><span data-stu-id="f2c67-113">Click **OK** to confirm deletion.</span></span>  
  
6.  <span data-ttu-id="f2c67-114">Passe o mouse sobre **Gerenciar** no menu e clique em **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-114">Hover the mouse over **Manage** on the menu and click **Entities**.</span></span>  
  
7.  <span data-ttu-id="f2c67-115">Clique em **Supplier** e clique no botão **Excluir (X)** na barra de ferramentas para excluir a entidade.</span><span class="sxs-lookup"><span data-stu-id="f2c67-115">Click **Supplier** and click **Delete (X)** button on toolbar to delete the entity.</span></span> <span data-ttu-id="f2c67-116">Clique em **OK** nas caixas de mensagem.</span><span class="sxs-lookup"><span data-stu-id="f2c67-116">Click **OK** on message boxes.</span></span>  
  
8.  <span data-ttu-id="f2c67-117">Repita a etapa anterior para excluir a entidade **State** .</span><span class="sxs-lookup"><span data-stu-id="f2c67-117">Repeat the previous step to delete **State** entity.</span></span>  
  
9. <span data-ttu-id="f2c67-118">Não feche **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-118">Don't close **Master Data Manager**.</span></span>  
  
10. <span data-ttu-id="f2c67-119">Alterne para a janela do Excel que tem o arquivo **Cleansed and Matched Suppliers.xls** aberto.</span><span class="sxs-lookup"><span data-stu-id="f2c67-119">Switch to the Excel window that has **Cleansed and Matched Suppliers.xls** file open.</span></span> <span data-ttu-id="f2c67-120">Alterne para a guia **Planilha1** na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="f2c67-120">Switch to the **Sheet1** tab at the bottom.</span></span>  
  
11. <span data-ttu-id="f2c67-121">Selecione apenas a **primeira linha com cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-121">Select only the **first row with headers**.</span></span> <span data-ttu-id="f2c67-122">Não selecione nenhuma outra linha.</span><span class="sxs-lookup"><span data-stu-id="f2c67-122">Don't select any other row.</span></span> <span data-ttu-id="f2c67-123">Você deseja criar as entidades com base nas colunas do Excel, mas não deseja carregar nenhum dado.</span><span class="sxs-lookup"><span data-stu-id="f2c67-123">You want to create the entities based on the Excel columns but don't want to upload any data.</span></span> <span data-ttu-id="f2c67-124">Portanto, selecione apenas a primeira linha com os cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="f2c67-124">Therefore you select only the first row with the headers.</span></span>  
  
12. <span data-ttu-id="f2c67-125">Clique em **Dados Mestres** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="f2c67-125">Click **Master Data** on the menu bar.</span></span>  
  
13. <span data-ttu-id="f2c67-126">Clique em **Criar Entidade** na faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="f2c67-126">Click **Create Entity** from the ribbon.</span></span>  
  
14. <span data-ttu-id="f2c67-127">Na caixa de diálogo **Gerenciar Conexões** , se você não visualizar a conexão com o **servidor MDS local** em **Conexões existentes**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="f2c67-127">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="f2c67-128">Selecione **Criar uma nova conexão**e clique no botão **Nova** .</span><span class="sxs-lookup"><span data-stu-id="f2c67-128">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="f2c67-129">Na caixa de diálogo Adicionar nova conexão, digite **servidor MDS local** para **Descrição** e **http: \/ /localhost/MDS** para o **endereço do servidor MDS**e clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f2c67-129">In the Add New Connection dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="f2c67-130">Na caixa de diálogo **gerenciar conexões** , selecione **servidor MDS local** ( `http://localhost/MDS` ), clique em **testar** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="f2c67-130">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="f2c67-131">Clique em **OK** na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="f2c67-131">Click **OK** on the message box.</span></span>  
  
16. <span data-ttu-id="f2c67-132">Clique em **Conectar** para estabelecer uma conexão com o servidor MDS.</span><span class="sxs-lookup"><span data-stu-id="f2c67-132">Click **Connect** to make a connection to the MDS server.</span></span>  
  
17. <span data-ttu-id="f2c67-133">Na caixa de diálogo **Criar Entidade** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f2c67-133">In the **Create Entity** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f2c67-134">Confirme se **Intervalo** está definido como **$1:$1**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-134">Confirm that **Range** is set to **$1:$1**.</span></span>  
  
    2.  <span data-ttu-id="f2c67-135">Selecione **Fornecedores** como **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-135">Select **Suppliers** for **Model**.</span></span>  
  
    3.  <span data-ttu-id="f2c67-136">Selecione **VERSION_1** como **Versão**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-136">Select **VERSION_1** for **Version**.</span></span>  
  
    4.  <span data-ttu-id="f2c67-137">Digite **Supplier** como **Nome da nova entidade**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-137">Type **Supplier** for **New entity name**.</span></span>  
  
    5.  <span data-ttu-id="f2c67-138">Selecione **SupplierID** como **Code**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-138">Select **SupplierID** for **Code**.</span></span>  
  
    6.  <span data-ttu-id="f2c67-139">Selecione **Supplier Name** como **Nome**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-139">Select **Supplier Name** for **Name**.</span></span>  
  
    7.  <span data-ttu-id="f2c67-140">Clique em **OK** para criar a entidade e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f2c67-140">Click **OK** to create the entity and close the dialog box.</span></span>  
  
18. <span data-ttu-id="f2c67-141">Feche o **Excel** e **não salve** o arquivo.</span><span class="sxs-lookup"><span data-stu-id="f2c67-141">Close **Excel** and **do not save** the file.</span></span>  
  
19. <span data-ttu-id="f2c67-142">No **Master Data Manager**, atualize o navegador da Internet e confirme se a entidade **Supplier** é exibida na lista.</span><span class="sxs-lookup"><span data-stu-id="f2c67-142">In **Master Data Manager**, refresh the internet browser and confirm that **Supplier** entity is displayed in the list.</span></span>  
  
20. <span data-ttu-id="f2c67-143">Alterne para a **home page** clicando em **SQL Server 2012 Master Data Services** na parte superior.</span><span class="sxs-lookup"><span data-stu-id="f2c67-143">Switch to the **home page** by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
21. <span data-ttu-id="f2c67-144">Confirme se o modelo **Fornecedores** está selecionado como **Modelo** e **VERSION_1** está selecionada como **Versão**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-144">Confirm that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**.</span></span>  
  
22. <span data-ttu-id="f2c67-145">Clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-145">Click **Explorer**.</span></span> <span data-ttu-id="f2c67-146">Observe que a entidade **Supplier** com todos os atributos foi criada sem **nenhum valor**.</span><span class="sxs-lookup"><span data-stu-id="f2c67-146">Notice that the **Supplier** entity with all the attributes is created with **no values**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f2c67-147">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f2c67-147">Next Step</span></span>  
 [<span data-ttu-id="f2c67-148">Tarefa 2 &#40;&#41; opcional: criando uma exibição de assinatura do MDS usando o Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="f2c67-148">Task 2 &#40;Optional&#41;: Creating a MDS Subscription View using Master Data Manager</span></span>](../../2014/tutorials/task-2-optional-creating-a-mds-subscription-view-using-master-data-manager.md)  
  
  
