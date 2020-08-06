---
title: 'Lição 4: Definir uma conexão de dados e uma tabela de dados para o relatório filho | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6aa2c56-227c-43c5-a28e-c7104131ac5e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d9144d960ad933afa65f9d4483e96b5f732d944
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570516"
---
# <a name="lesson-4-define-a-data-connection-and-data-table-for-child-report"></a><span data-ttu-id="fef0b-102">Lição 4: Definir uma conexão de dados e uma tabela de dados para o relatório filho</span><span class="sxs-lookup"><span data-stu-id="fef0b-102">Lesson 4: Define a Data Connection and Data Table for Child Report</span></span>
  <span data-ttu-id="fef0b-103">Depois que você criar o relatório pai, a próxima etapa será criar uma conexão de dados e uma tabela de dados para o relatório filho.</span><span class="sxs-lookup"><span data-stu-id="fef0b-103">After you design the parent report, you next step is to create a data connection and a data table for the child report.</span></span> <span data-ttu-id="fef0b-104">Neste tutorial, a conexão de dados é com o banco de dados AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="fef0b-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="fef0b-105">Você também tem a opção de se conectar ao banco de dados AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="fef0b-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-datatable-by-adding-a-dataset-for-child-report"></a><span data-ttu-id="fef0b-106">Para definir uma conexão de dados e uma DataTable adicionando um DataSet (para o relatório filho)</span><span class="sxs-lookup"><span data-stu-id="fef0b-106">To define a data connection and DataTable by adding a DataSet (for child report)</span></span>  
  
1.  <span data-ttu-id="fef0b-107">No menu do **site** , clique em **Adicionar novo item**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-107">On the **Website** menu, click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="fef0b-108">Na caixa de diálogo **Adicionar novo item** , clique em **conjunto** de um e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-108">In the **Add New Item** dialog box, click **DataSet** and then click **Add**.</span></span> <span data-ttu-id="fef0b-109">Quando solicitado, você deve adicionar o item à pasta **App_Code** clicando em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-109">When prompted, you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="fef0b-110">Isso adicionará um novo arquivo XSD **DataSet2.xsd** ao projeto e abrirá o Designer de Conjunto de Dados.</span><span class="sxs-lookup"><span data-stu-id="fef0b-110">This adds a new XSD file **DataSet2.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="fef0b-111">Na janela Caixa de Ferramentas, arraste um controle **TableAdapter** até a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="fef0b-111">From the Toolbox window, drag a **TableAdapter** control to the design surface.</span></span> <span data-ttu-id="fef0b-112">Isso inicializará o Assistente de Configuração do **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="fef0b-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="fef0b-113">Na página **escolher sua conexão de dados** , clique em **nova conexão**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="fef0b-114">Na caixa de diálogo **Adicionar Conexão** , realize as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="fef0b-114">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="fef0b-115">Na caixa **nome do servidor** , insira o servidor no qual o banco de dados **AdventureWorks2008** está localizado.</span><span class="sxs-lookup"><span data-stu-id="fef0b-115">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="fef0b-116">A instância padrão do SQL Server Express é **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-116">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="fef0b-117">Na seção **Fazer logon no servidor** , selecione a opção que lhe fornece acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="fef0b-117">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="fef0b-118">**Usar Autenticação do Windows** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="fef0b-118">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="fef0b-119">Na lista suspensa **selecionar ou digitar um nome de banco de dados** , clique em **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-119">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="fef0b-120">Clique em **OK** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-120">Click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="fef0b-121">Se você selecionou **Usar Autenticação do SQL Server** na etapa 5 (b), selecione a opção que especificará se os dados confidenciais serão incluídos na cadeia de caracteres ou defina as informações no código do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fef0b-121">If you selected **Use SQL Server Authentication** in Step 5 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
7.  <span data-ttu-id="fef0b-122">Na página **salvar a cadeia de conexão no arquivo de configuração do aplicativo** , digite o nome da cadeia de conexão ou aceite o **AdventureWorks2008ConnectionString**padrão.</span><span class="sxs-lookup"><span data-stu-id="fef0b-122">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="fef0b-123">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-123">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="fef0b-124">Na página **escolher um tipo de comando** , selecione **usar instruções SQL**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-124">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="fef0b-125">Na página **Inserir uma instrução SQL** , insira a seguinte consulta TRANSACT-SQL para recuperar dados do banco de **AdventureWorks2008** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-125">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail  
    ```  
  
     <span data-ttu-id="fef0b-126">Você também pode criar a consulta clicando em **Construtor de consultas**e, em seguida, verificar a consulta clicando no botão **Executar consulta** .</span><span class="sxs-lookup"><span data-stu-id="fef0b-126">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query** button.</span></span> <span data-ttu-id="fef0b-127">Se a consulta não retornar os dados esperados, talvez você esteja usando uma versão anterior do AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="fef0b-127">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="fef0b-128">Para obter mais informações sobre como instalar a versão **AdventureWorks2008** do AdventureWorks, consulte [passo a passos: Instalando o banco de dados AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="fef0b-128">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
10. <span data-ttu-id="fef0b-129">Na página **escolher os métodos a serem gerados** , desmarque **criar métodos para enviar atualizações diretamente ao banco de dados (GenerateDBDirectMethods)** e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-129">On the **Choose Methods to Generate** page, uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="fef0b-130">Agora você concluiu a configuração da [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) ADO.net como fonte de dados para o relatório.</span><span class="sxs-lookup"><span data-stu-id="fef0b-130">You have now completed configuring the ADO.NET [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) as data source for your report.</span></span> <span data-ttu-id="fef0b-131">Na página Designer de Conjunto de Dados no Visual Studio, você verá a **DataTable** adicionada, listando as colunas especificadas na consulta.</span><span class="sxs-lookup"><span data-stu-id="fef0b-131">On the DataSet Designer page in Visual Studio, you should see the **DataTable** you added, listing the columns specified in the query.</span></span> <span data-ttu-id="fef0b-132">O DataSet2 contém os dados da tabela PurhcaseOrderDetail, com base na consulta.</span><span class="sxs-lookup"><span data-stu-id="fef0b-132">DataSet2 contains the data from the PurhcaseOrderDetail table, based on the query.</span></span>  
  
11. <span data-ttu-id="fef0b-133">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="fef0b-133">Save the file.</span></span>  
  
12. <span data-ttu-id="fef0b-134">Para visualizar os dados, clique em **Visualizar dados** no menu **dados** e clique em **Visualizar**.</span><span class="sxs-lookup"><span data-stu-id="fef0b-134">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="fef0b-135">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="fef0b-135">Next Task</span></span>  
 <span data-ttu-id="fef0b-136">Você criou uma conexão de dados e uma tabela de dados para o relatório filho.</span><span class="sxs-lookup"><span data-stu-id="fef0b-136">You have successfully created a data connection and data table for the child report.</span></span> <span data-ttu-id="fef0b-137">Em seguida, você criará o relatório filho usando o Assistente de Relatório.</span><span class="sxs-lookup"><span data-stu-id="fef0b-137">Next, you will design the child report using the Report Wizard.</span></span>  
  
  
