---
title: 'Lição 2: Definir uma conexão de dados e uma tabela de dados para o relatório pai | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f02dee0c-85ad-45d4-b707-10e9e8541db9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 045ff576061bf12d163668cb9a57651e591768a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569837"
---
# <a name="lesson-2-define-a-data-connection-and-data-table-for-parent-report"></a><span data-ttu-id="0ab79-102">Lição 2: Definir uma conexão de dados e uma tabela de dados para o relatório pai</span><span class="sxs-lookup"><span data-stu-id="0ab79-102">Lesson 2: Define a Data Connection and Data Table for Parent Report</span></span>
  <span data-ttu-id="0ab79-103">Depois que você criar um novo projeto de site usando o modelo de site ASP.NET para o Visual C #, a próxima etapa será criar uma conexão de dados e uma tabela de dados para o relatório pai.</span><span class="sxs-lookup"><span data-stu-id="0ab79-103">After you create a new website project using the ASP.NET website template for Visual C#, your next step is to create a data connection and a data table for the parent report.</span></span> <span data-ttu-id="0ab79-104">Neste tutorial, a conexão de dados é com o banco de dados AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="0ab79-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="0ab79-105">Você também tem a opção de se conectar ao banco de dados AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="0ab79-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-data-table-by-adding-a-dataset-for-parent-report"></a><span data-ttu-id="0ab79-106">Para definir uma conexão de dados e uma DataTable adicionando um DataSet (para o relatório pai)</span><span class="sxs-lookup"><span data-stu-id="0ab79-106">To define a data connection and Data Table by adding a DataSet (for parent report)</span></span>  
  
1.  <span data-ttu-id="0ab79-107">No menu **Site** , selecione **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-107">On the **Website** menu, select **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="0ab79-108">Na caixa de diálogo **Adicionar novo item** , selecione **conjunto** de um e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-108">In the **Add New Item** dialog box, select **DataSet** and click **Add**.</span></span> <span data-ttu-id="0ab79-109">Quando solicitado, você deve adicionar o item à pasta **App_Code** clicando em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-109">When prompted you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="0ab79-110">Isso adicionará um novo arquivo XSD **DataSet1.xsd** ao projeto e abrirá o Designer de Conjunto de Dados.</span><span class="sxs-lookup"><span data-stu-id="0ab79-110">This adds a new XSD file **DataSet1.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="0ab79-111">Na janela caixa de ferramentas, arraste um controle **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="0ab79-111">From the Toolbox window, drag a **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** control to the design surface.</span></span> <span data-ttu-id="0ab79-112">Isso inicializará o Assistente de Configuração do **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="0ab79-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="0ab79-113">Na página **escolher sua conexão de dados** , clique em **nova conexão**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="0ab79-114">Se esta for a primeira vez que você criou uma fonte de dados no Visual Studio, você verá a página **escolher fonte de dados** .</span><span class="sxs-lookup"><span data-stu-id="0ab79-114">If this is the first time you've created a data source in Visual Studio, you will see the **Choose Data Source** page.</span></span> <span data-ttu-id="0ab79-115">Na caixa **Fonte de Dados** , selecione **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-115">In the **Data Source** box, select **Microsoft SQL Server**.</span></span>  
  
6.  <span data-ttu-id="0ab79-116">Na caixa de diálogo **Adicionar Conexão** , realize as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="0ab79-116">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="0ab79-117">Na caixa **nome do servidor** , insira o servidor no qual o banco de dados **AdventureWorks2008** está localizado.</span><span class="sxs-lookup"><span data-stu-id="0ab79-117">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="0ab79-118">A instância padrão do SQL Server Express é **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-118">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="0ab79-119">Na seção **Fazer logon no servidor** , selecione a opção que lhe fornece acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="0ab79-119">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="0ab79-120">**Usar Autenticação do Windows** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="0ab79-120">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="0ab79-121">Na lista suspensa **selecionar ou digitar um nome de banco de dados** , clique em **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-121">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="0ab79-122">Clique em **OK** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-122">Click **OK**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="0ab79-123">Se você tiver selecionado **Usar Autenticação do SQL Server** na Etapa 6 (b), selecione a opção que especificará se os dados confidenciais serão incluídos na cadeia de caracteres ou defina as informações no código do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0ab79-123">If you selected **Use SQL Server Authentication** in the Step 6 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
8.  <span data-ttu-id="0ab79-124">Na página **salvar a cadeia de conexão no arquivo de configuração do aplicativo** , digite o nome da cadeia de conexão ou aceite o **AdventureWorks2008ConnectionString**padrão.</span><span class="sxs-lookup"><span data-stu-id="0ab79-124">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="0ab79-125">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-125">Click **Next**.</span></span>  
  
9. <span data-ttu-id="0ab79-126">Na página **escolher um tipo de comando** , selecione **usar instruções SQL**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-126">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="0ab79-127">Na página **Inserir uma instrução SQL** , insira a seguinte consulta TRANSACT-SQL para recuperar dados do banco de **AdventureWorks2008** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-127">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT ProductID, Name, ProductNumber, SafetyStockLevel, ReorderPoint FROM  Production.Product Order By ProductID  
    ```  
  
     <span data-ttu-id="0ab79-128">Você também pode criar a consulta clicando em **Construtor de consultas**e, em seguida, verificar a consulta clicando em **Executar consulta**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-128">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query**.</span></span> <span data-ttu-id="0ab79-129">Se a consulta não retornar os dados esperados, talvez você esteja usando uma versão anterior do AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0ab79-129">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="0ab79-130">Para obter mais informações sobre como instalar a versão **AdventureWorks2008** do AdventureWorks, consulte [passo a passos: Instalando o banco de dados AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="0ab79-130">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
11. <span data-ttu-id="0ab79-131">Na página **escolher os métodos a serem gerados** , não se esqueça de desmarcar **criar métodos para enviar atualizações diretamente ao banco de dados (GenerateDBDirectMethods)** e, em seguida, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-131">On the **Choose Methods to Generate** page, be sure to uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="0ab79-132">Verifique se desmarcou Criar</span><span class="sxs-lookup"><span data-stu-id="0ab79-132">Be sure to uncheck Create</span></span>  
  
     <span data-ttu-id="0ab79-133">Agora você concluiu a configuração do objeto DataTable do ADO.NET como fonte de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="0ab79-133">You have now completed configuring the ADO.NET DataTable object as the data source for your report.</span></span> <span data-ttu-id="0ab79-134">Na página Designer de Conjunto de Dados no Visual Studio, você verá a DataTable o objeto DataTable que adicionou, listando as colunas especificadas na consulta.</span><span class="sxs-lookup"><span data-stu-id="0ab79-134">On the DataSet Designer page in Visual Studio, you should see the DataTable object you added, listing the columns specified in the query.</span></span> <span data-ttu-id="0ab79-135">O DataSet1 contém os dados da tabela Product, com base na consulta.</span><span class="sxs-lookup"><span data-stu-id="0ab79-135">DataSet1 contains the data from the Product table, based on the query.</span></span>  
  
12. <span data-ttu-id="0ab79-136">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="0ab79-136">Save the file.</span></span>  
  
13. <span data-ttu-id="0ab79-137">Para visualizar os dados, clique em **Visualizar dados** no menu **dados** e clique em **Visualizar**.</span><span class="sxs-lookup"><span data-stu-id="0ab79-137">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="0ab79-138">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="0ab79-138">Next Task</span></span>  
 <span data-ttu-id="0ab79-139">Você criou uma conexão de dados e uma tabela de dados para o relatório pai.</span><span class="sxs-lookup"><span data-stu-id="0ab79-139">You have successfully created a data connection and a data table for the parent report.</span></span> <span data-ttu-id="0ab79-140">Em seguida, você criará o relatório pai usando o Assistente de Relatório.</span><span class="sxs-lookup"><span data-stu-id="0ab79-140">Next, you will design the parent report using the Report Wizard.</span></span>  
  
  
