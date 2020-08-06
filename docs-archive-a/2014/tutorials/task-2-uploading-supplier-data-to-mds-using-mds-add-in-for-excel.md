---
title: 'Tarefa 2: carregando dados do fornecedor para o MDS usando Suplemento MDS para Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 598deb57-e0cc-4e0a-aeb1-94432c094c67
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 16c5fa9db81649b30c12fae4d2e57afa8bf094e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568954"
---
# <a name="task-2-uploading-supplier-data-to-mds-using-mds-add-in-for-excel"></a><span data-ttu-id="f8c56-102">Tarefa 2: Carregando dados do fornecedor no MDS usando o Suplemento MDS para Excel</span><span class="sxs-lookup"><span data-stu-id="f8c56-102">Task 2: Uploading Supplier Data to MDS using MDS Add-in for Excel</span></span>
  <span data-ttu-id="f8c56-103">Nesta tarefa, você publica os dados limpos e de fornecedor no **MDS** usando o **suplemento MDS para Excel**.</span><span class="sxs-lookup"><span data-stu-id="f8c56-103">In this task, you publish the cleansed and supplier data to **MDS** using the **MDS Add-in for Excel**.</span></span> <span data-ttu-id="f8c56-104">Você cria uma entidade chamada **Supplier** no modelo **suppliers** criado na lição anterior.</span><span class="sxs-lookup"><span data-stu-id="f8c56-104">You create an entity named **Supplier** in the **Suppliers** model you created in the previous lesson.</span></span> <span data-ttu-id="f8c56-105">A entidade terá um atributo para cada coluna no arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="f8c56-105">The entity will have an attribute for each column in the Excel file.</span></span> <span data-ttu-id="f8c56-106">Os atributos de código e nome da entidade Supplier correspondem às colunas **CódigoDoFornecedor** e **nome do fornecedor** no Excel.</span><span class="sxs-lookup"><span data-stu-id="f8c56-106">The Code and Name attributes of the Supplier entity correspond to the **SupplierID** and **Supplier Name** columns in Excel.</span></span>  
  
1.  <span data-ttu-id="f8c56-107">Abrir **Suppliers.xlslimpo e correspondente** no **Excel**.</span><span class="sxs-lookup"><span data-stu-id="f8c56-107">Open **Cleansed and Matched Suppliers.xls** in **Excel**.</span></span>  
  
2.  <span data-ttu-id="f8c56-108">Pressione **Ctrl + a** para selecionar os dados inteiros.</span><span class="sxs-lookup"><span data-stu-id="f8c56-108">Press **CTRL+A** to select entire data.</span></span> <span data-ttu-id="f8c56-109">É **importante** que você selecione todos os dados na planilha.</span><span class="sxs-lookup"><span data-stu-id="f8c56-109">It is **important** that you select the entire data in the spreadsheet.</span></span>  
  
3.  <span data-ttu-id="f8c56-110">Clique em **Dados Mestres** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="f8c56-110">Click **Master Data** on the menu bar.</span></span>  
  
4.  <span data-ttu-id="f8c56-111">Clique no botão **criar entidade** na faixa de faixas.</span><span class="sxs-lookup"><span data-stu-id="f8c56-111">Click **Create Entity** button on the ribbon.</span></span>  
  
     <span data-ttu-id="f8c56-112">![Excel - Guia Dados Mestre - Botão Criar Entidade](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Guia Dados Mestre - Botão Criar Entidade")</span><span class="sxs-lookup"><span data-stu-id="f8c56-112">![Excel - Master Data Tab - Create Entity Button](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Master Data Tab - Create Entity Button")</span></span>  
  
5.  <span data-ttu-id="f8c56-113">Na caixa de diálogo **Gerenciar Conexões** , se você não visualizar a conexão com o **servidor MDS local** em **Conexões existentes**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="f8c56-113">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="f8c56-114">Selecione **Criar uma nova conexão**e clique no botão **Nova** .</span><span class="sxs-lookup"><span data-stu-id="f8c56-114">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="f8c56-115">Na caixa de diálogo **Adicionar nova conexão** , digite **servidor MDS local** para **Descrição** e **http: \/ /localhost/MDS** para o **endereço do servidor MDS**e clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f8c56-115">In the **Add New Connection** dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="f8c56-116">Na caixa de diálogo **gerenciar conexões** , selecione **servidor MDS local** ( `http://localhost/MDS` ), clique em **testar** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="f8c56-116">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="f8c56-117">Clique em **OK** na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="f8c56-117">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="f8c56-118">Clique em **conectar** para se conectar ao servidor MDS.</span><span class="sxs-lookup"><span data-stu-id="f8c56-118">Click **Connect** to connect to the MDS server.</span></span>  
  
8.  <span data-ttu-id="f8c56-119">Na caixa de diálogo **criar entidade** , selecione **fornecedores** para o **modelo**.</span><span class="sxs-lookup"><span data-stu-id="f8c56-119">In the **Create Entity** dialog box, select **Suppliers** for the **Model**.</span></span>  
  
9. <span data-ttu-id="f8c56-120">Verifique se **VERSION_1** está selecionado para a **versão**.</span><span class="sxs-lookup"><span data-stu-id="f8c56-120">Ensure that **VERSION_1** is selected for **Version**.</span></span>  
  
10. <span data-ttu-id="f8c56-121">Insira **fornecedor** para o **nome da nova entidade**.</span><span class="sxs-lookup"><span data-stu-id="f8c56-121">Enter **Supplier** for **New entity name**.</span></span>  
  
11. <span data-ttu-id="f8c56-122">Selecione **CódigoDoFornecedor** para **a coluna que contém um campo identificador exclusivo** (você também pode gerar um código automaticamente).</span><span class="sxs-lookup"><span data-stu-id="f8c56-122">Select **SupplierID** for **the column that contains a unique identifier** field (you can also generate a code automatically).</span></span> <span data-ttu-id="f8c56-123">Essencialmente, você está mapeando a coluna **CódigoDoFornecedor** no **Excel** para o atributo de **código** da entidade **Supplier** .</span><span class="sxs-lookup"><span data-stu-id="f8c56-123">You are essentially mapping the **SupplierID** column in **Excel** to the **Code** attribute of **Supplier** entity.</span></span>  
  
12. <span data-ttu-id="f8c56-124">Selecione **nome do fornecedor** para **a coluna que contém o campo nomes** .</span><span class="sxs-lookup"><span data-stu-id="f8c56-124">Select **Supplier Name** for **the column that contains names** field.</span></span> <span data-ttu-id="f8c56-125">Essencialmente, você está mapeando a coluna **nome do fornecedor** no **Excel** para o atributo **nome** da entidade **fornecedor** .</span><span class="sxs-lookup"><span data-stu-id="f8c56-125">You are essentially mapping the **Supplier Name** column in **Excel** to the **Name** attribute of the **Supplier** entity.</span></span> <span data-ttu-id="f8c56-126">Os atributos de **código** e **nome** são atributos obrigatórios para uma entidade no MDS.</span><span class="sxs-lookup"><span data-stu-id="f8c56-126">The **Code** and **Name** attributes are mandatory attributes for an entity in MDS.</span></span>  
  
     <span data-ttu-id="f8c56-127">![Caixa de diálogo Criar Entidade](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Caixa de diálogo Criar Entidade")</span><span class="sxs-lookup"><span data-stu-id="f8c56-127">![Create Entity Dialog Box](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Create Entity Dialog Box")</span></span>  
  
13. <span data-ttu-id="f8c56-128">Clique em **OK** para criar a entidade no MDS, publicar os dados mestre na entidade e fechar a caixa de diálogo **criar entidade** .</span><span class="sxs-lookup"><span data-stu-id="f8c56-128">Click **OK** to create the entity on MDS, publish the master data to the entity, and close **Create Entity** dialog box.</span></span>  
  
14. <span data-ttu-id="f8c56-129">Agora, você deve ver uma nova planilha chamada **fornecedor**, que é o nome da entidade, adicionada à sua planilha do Excel e, na parte superior da planilha, você verá que a planilha está conectada ao servidor MDS.</span><span class="sxs-lookup"><span data-stu-id="f8c56-129">Now, you should see a new sheet titled **Supplier**, which is the name of the entity, added to your Excel spreadsheet and at the top of the worksheet you should see that the worksheet is connected to the MDS server.</span></span> <span data-ttu-id="f8c56-130">Observe que a planilha original (intitulada **Plan1**) ainda existe.</span><span class="sxs-lookup"><span data-stu-id="f8c56-130">Notice that the original worksheet (titled **Sheet1**) still exists.</span></span>  
  
     <span data-ttu-id="f8c56-131">![Excel - Guias Fornecedor e Planilha1](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Guias Fornecedor e Planilha1")</span><span class="sxs-lookup"><span data-stu-id="f8c56-131">![Excel - Supplier and Sheet1 Tabs](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Supplier and Sheet1 Tabs")</span></span>  
  
     <span data-ttu-id="f8c56-132">![Excel - Mostrando Detalhes de Conexão do MDS](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Mostrando Detalhes de Conexão do MDS")</span><span class="sxs-lookup"><span data-stu-id="f8c56-132">![Excel - Showing MDS Connection Details](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Showing MDS Connection Details")</span></span>  
  
15. <span data-ttu-id="f8c56-133">Mantenha o **Excel** aberto.</span><span class="sxs-lookup"><span data-stu-id="f8c56-133">Keep **Excel** open.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="f8c56-134">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="f8c56-134">Next Task</span></span>  
 [<span data-ttu-id="f8c56-135">Tarefa 3: Verificando os dados no Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="f8c56-135">Task 3: Verifying the Data in Master Data Manager</span></span>](../../2014/tutorials/task-3-verifying-the-data-in-master-data-manager.md)  
  
  
