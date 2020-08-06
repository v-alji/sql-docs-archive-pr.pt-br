---
title: 'Lição 8: Criar um filtro de dados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19ccbdba-e3da-40a4-b652-32c628cf32e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c11d4cf83619e53cd7e8f00091c66cc8e50ad76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570508"
---
# <a name="lesson-8-create-a-data-filter"></a><span data-ttu-id="72578-102">Lição 8: Criar um filtro de dados</span><span class="sxs-lookup"><span data-stu-id="72578-102">Lesson 8: Create a Data Filter</span></span>
  <span data-ttu-id="72578-103">Após adicionar uma ação de detalhamento no relatório pai, a próxima etapa é criar um filtro de dados para a tabela de dados definida para o relatório filho.</span><span class="sxs-lookup"><span data-stu-id="72578-103">After you add a drillthrough action on the parent report, your next step is to create a data filter for the data table that you defined for the child report.</span></span>  
  
 <span data-ttu-id="72578-104">Você pode criar um filtro baseado em tabela **ou** um filtro de consulta para o relatório de detalhamento.</span><span class="sxs-lookup"><span data-stu-id="72578-104">You can create a table-based filter **or** a query filter for the drillthrough report.</span></span> <span data-ttu-id="72578-105">Esta lição fornece instruções para ambas as opções.</span><span class="sxs-lookup"><span data-stu-id="72578-105">This lesson provides instructions for both options.</span></span>  
  
## <a name="table-based-filter"></a><span data-ttu-id="72578-106">Filtro baseado em tabela</span><span class="sxs-lookup"><span data-stu-id="72578-106">Table-Based Filter</span></span>  
 <span data-ttu-id="72578-107">É necessário concluir as seguintes tarefas para implementar um filtro baseado em tabela.</span><span class="sxs-lookup"><span data-stu-id="72578-107">You need to complete the following tasks to implement a table-based filter.</span></span>  
  
-   <span data-ttu-id="72578-108">Adicione uma expressão de filtro ao tablix no relatório filho.</span><span class="sxs-lookup"><span data-stu-id="72578-108">Add a filter expression to the tablix in the child report.</span></span>  
  
-   <span data-ttu-id="72578-109">Crie uma função que seleciona dados não filtrados na tabela `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="72578-109">Create a function that selects unfiltered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="72578-110">Adicione um manipulador de eventos que associe a DataTable `PurchaseOrderDetail` ao relatório filho.</span><span class="sxs-lookup"><span data-stu-id="72578-110">Add an event handler that binds the `PurchaseOrderDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-add-a-filter-expression-to-the-tablix-in-the-child-report"></a><span data-ttu-id="72578-111">Para adicionar uma expressão de filtro ao tablix no relatório filho</span><span class="sxs-lookup"><span data-stu-id="72578-111">To add a filter expression to the tablix in the child report</span></span>  
  
1.  <span data-ttu-id="72578-112">Abra o relatório filho.</span><span class="sxs-lookup"><span data-stu-id="72578-112">Open the child report.</span></span>  
  
2.  <span data-ttu-id="72578-113">Selecione um título de coluna no Tablix, clique com o botão direito do mouse na célula cinza que aparece acima do título da coluna e clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="72578-113">Select a column heading in the tablix, right-click the gray cell that appears above the column heading, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="72578-114">Clique na página **filtros** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="72578-114">Click on the **Filters** page, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="72578-115">Na **expressão** registrada, clique `ProductID` na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="72578-115">In the **Expression** filed, click `ProductID` from the drop-down list.</span></span> <span data-ttu-id="72578-116">Esta é a coluna à qual você aplicará o filtro.</span><span class="sxs-lookup"><span data-stu-id="72578-116">This is the column to which you apply the filter.</span></span>  
  
5.  <span data-ttu-id="72578-117">Clique no operador EQUAL ( **=** ) na lista suspensa **operador** .</span><span class="sxs-lookup"><span data-stu-id="72578-117">Click the equal (**=**) operator in the **Operator** drop-down list.</span></span>  
  
6.  <span data-ttu-id="72578-118">Clique no botão de expressão ao lado do campo **valor** , clique em **parâmetros** na área **categoria** e clique duas vezes `productid` na área **valores** .</span><span class="sxs-lookup"><span data-stu-id="72578-118">Click the expression button next to the **Value** field, click **Parameters** in the **Category** area, and then double-click `productid` in the **Values** area.</span></span> <span data-ttu-id="72578-119">O campo **Definir expressão para: Valor** agora deve conter uma expressão semelhante a **=Parameters!productid.Value**.</span><span class="sxs-lookup"><span data-stu-id="72578-119">The **Set expression for: Value** field should now contain expression similar to **=Parameters!productid.Value**.</span></span>  
  
7.  <span data-ttu-id="72578-120">Clique em **OK** e em **OK** novamente na caixa de diálogo **Propriedades do Tablix** .</span><span class="sxs-lookup"><span data-stu-id="72578-120">Click **OK,** and **OK** again in the **Tablix Properties** dialog box.</span></span>  
  
8.  <span data-ttu-id="72578-121">Salve o arquivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="72578-121">Save the .rdlc file.</span></span>  
  
#### <a name="to-create-a-function-that-selects-unfiltered-data-from-the-purchaseordedetail-table"></a><span data-ttu-id="72578-122">Para criar uma função que seleciona dados não filtrados na tabela PurchaseOrdeDetail.</span><span class="sxs-lookup"><span data-stu-id="72578-122">To create a function that selects unfiltered data from the PurchaseOrdeDetail table</span></span>  
  
1.  <span data-ttu-id="72578-123">No Gerenciador de Soluções, expanda Default.aspx e clique duas vezes em Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="72578-123">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="72578-124">Crie uma nova função que aceite um parâmetro, `productid` , do tipo inteiro, retorne um `datatable` objeto e faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="72578-124">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object, and does the following.</span></span>  
  
    1.  <span data-ttu-id="72578-125">Cria uma instância do conjunto de dados, `DataSet2` , que foi criada na etapa 2 da [lição 4: definir uma conexão de dados e uma data Table para o relatório filho](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="72578-125">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="72578-126">Crie uma conexão com o banco de dados SQL Server para executar a consulta definida na **Lição 4: Definir uma conexão de dados e uma DataTable para o relatório filho**.</span><span class="sxs-lookup"><span data-stu-id="72578-126">Create a connection to the SqlServer database to execute the query defined in **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="72578-127">A consulta deve retornará dados não filtrados.</span><span class="sxs-lookup"><span data-stu-id="72578-127">The query will return unfiltered data.</span></span>  
  
    4.  <span data-ttu-id="72578-128">Preencha a instância do DataSet com os dados não filtrados executando a consulta.</span><span class="sxs-lookup"><span data-stu-id="72578-128">Fill the DataSet instance with the unfiltered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="72578-129">Retorne a DataTable `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="72578-129">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="72578-130">A função terá aparência similar à mostrada abaixo (Isso é apenas para fins de referência.</span><span class="sxs-lookup"><span data-stu-id="72578-130">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="72578-131">Você pode seguir o padrão desejado para buscar os dados necessários ao relatório filho).</span><span class="sxs-lookup"><span data-stu-id="72578-131">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table, fetch the  
            /// unfiltered data and bind it with the Child report  
            /// </summary>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail()  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail ", sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-binds-the-purchaseorderdetail-datatable-to-the-child-report"></a><span data-ttu-id="72578-132">Para adicionar um manipulador de eventos que associe a DataTable PurchaseOrderDetail ao relatório filho.</span><span class="sxs-lookup"><span data-stu-id="72578-132">To add an event handler that binds the PurchaseOrderDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="72578-133">Abra o Default.aspx</span><span class="sxs-lookup"><span data-stu-id="72578-133">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="72578-134">Clique com o botão direito do mouse no controle ReportViewer e clique em **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="72578-134">Right click the ReportViewer control, and then click **Properties.**</span></span>  
  
3.  <span data-ttu-id="72578-135">Na página **Propriedades** , clique no ícone **eventos** .</span><span class="sxs-lookup"><span data-stu-id="72578-135">On the **Properties** page, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="72578-136">Clique duas vezes no evento de **detalhamento** .</span><span class="sxs-lookup"><span data-stu-id="72578-136">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="72578-137">Isso adicionará uma seção do manipulador de eventos ao código, que será semelhante ao bloco abaixo.</span><span class="sxs-lookup"><span data-stu-id="72578-137">This will add an event handler section in the code, which will look similar to the below block.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="72578-138">Conclua o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="72578-138">Complete the event handler.</span></span> <span data-ttu-id="72578-139">Ela deve incluir a funcionalidade a seguir.</span><span class="sxs-lookup"><span data-stu-id="72578-139">It should include the following functionalty.</span></span>  
  
    1.  <span data-ttu-id="72578-140">Busque a referência de objeto do relatório filho no parâmetro *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="72578-140">Fetch the child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="72578-141">Chame a função,`GetPurchaseOrderDetail`</span><span class="sxs-lookup"><span data-stu-id="72578-141">Call the function, `GetPurchaseOrderDetail`</span></span>  
  
    3.  <span data-ttu-id="72578-142">Associe a DataTable `PurchaseOrderDetail` à fonte de dados correspondente do relatório.</span><span class="sxs-lookup"><span data-stu-id="72578-142">Bind the `PurchaseOrderDetail` DataTable with the report's corresponding data source.</span></span>  
  
         <span data-ttu-id="72578-143">O código completo do manipulador de eventos será semelhante ao conteúdo seguinte.</span><span class="sxs-lookup"><span data-stu-id="72578-143">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                     //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                     //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail()));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="72578-144">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="72578-144">Save the file.</span></span>  
  
## <a name="query-filter"></a><span data-ttu-id="72578-145">Filtro de consulta</span><span class="sxs-lookup"><span data-stu-id="72578-145">Query Filter</span></span>  
 <span data-ttu-id="72578-146">É necessário concluir as seguintes tarefas para implementar um filtro de consulta.</span><span class="sxs-lookup"><span data-stu-id="72578-146">You need to complete the following tasks to implement a query filter.</span></span>  
  
-   <span data-ttu-id="72578-147">Crie uma função que tenha selecionado dados filtrados na tabela `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="72578-147">Create a function that selected filtered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="72578-148">Adicione um manipulador de eventos que recupere valores de parâmetro e associe a DataTable `PurchaseOrdeDetail` ao relatório filho.</span><span class="sxs-lookup"><span data-stu-id="72578-148">Add an event handler that retrieves parameter values and binds the `PurchaseOrdeDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-create-a-function-that-selects-filtered-data-from-the-purchaseorderdetail-table"></a><span data-ttu-id="72578-149">Para criar uma função que selecione dados filtrados na tabela PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="72578-149">To create a function that selects filtered data from the PurchaseOrderDetail table</span></span>  
  
1.  <span data-ttu-id="72578-150">No Gerenciador de Soluções, expanda Default.aspx e clique duas vezes em Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="72578-150">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="72578-151">Crie uma nova função que aceite um parâmetro, `productid`, do tipo inteiro e retorne um objeto `datatable`, e faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="72578-151">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object and does the following.</span></span>  
  
    1.  <span data-ttu-id="72578-152">Cria uma instância do conjunto de dados, `DataSet2` , que foi criada na etapa 2 da [lição 4: definir uma conexão de dados e uma data Table para o relatório filho](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="72578-152">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="72578-153">Crie uma conexão com o banco de dados SQL Server para executar a consulta definida na **Lição 4: Definir uma conexão de dados e uma DataTable para o relatório filho**.</span><span class="sxs-lookup"><span data-stu-id="72578-153">Create a connection to the SqlServer database to execute the query defined **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="72578-154">A consulta incluirá um parâmetro, `productid`, assegurar que os dados retornados serão filtrados com base na `ProductID` selecionada no relatório pai.</span><span class="sxs-lookup"><span data-stu-id="72578-154">The query will include a parameter, `productid`, to make sure the data returned is filtered based on the `ProductID` selected in the parent report.</span></span>  
  
    4.  <span data-ttu-id="72578-155">Preencha a instância do DataSet com os dados filtrados executando a consulta.</span><span class="sxs-lookup"><span data-stu-id="72578-155">Fill the DataSet instance with the filtered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="72578-156">Retorne a DataTable `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="72578-156">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="72578-157">A função terá aparência similar à mostrada abaixo (Isso é apenas para fins de referência.</span><span class="sxs-lookup"><span data-stu-id="72578-157">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="72578-158">Você pode seguir o padrão desejado para buscar os dados necessários ao relatório filho).</span><span class="sxs-lookup"><span data-stu-id="72578-158">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table and filter the  
            /// data for a specific ProductID selected in the Parent report.  
            /// </summary>  
            /// <param name="productid">Parameter passed from the Parent report to filter data.</param>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail(int productid)  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail where ProductID = " + productid, sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-retrieves-parameter-values-and-binds-the-purchaseordedetail-datatable-to-the-child-report"></a><span data-ttu-id="72578-159">Para adicionar um manipulador de eventos que recupere valores de parâmetro e associe a DataTable PurchaseOrdeDetail ao relatório filho</span><span class="sxs-lookup"><span data-stu-id="72578-159">To add an event handler that retrieves parameter values and binds the PurchaseOrdeDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="72578-160">Abra o Default.aspx</span><span class="sxs-lookup"><span data-stu-id="72578-160">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="72578-161">Clique com o botão direito do mouse no controle ReportViewer e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="72578-161">Right-click the ReportViewer control, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="72578-162">No painel **Propriedades** , clique no ícone **eventos** .</span><span class="sxs-lookup"><span data-stu-id="72578-162">On the **Properties** pane, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="72578-163">Clique duas vezes no evento de **detalhamento** .</span><span class="sxs-lookup"><span data-stu-id="72578-163">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="72578-164">Isso adicionará uma seção do manipulador de eventos ao código, que será semelhante ao conteúdo abaixo.</span><span class="sxs-lookup"><span data-stu-id="72578-164">This will add an event handler section in the code that will look similar to the following.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="72578-165">Conclua o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="72578-165">Complete the event handler.</span></span> <span data-ttu-id="72578-166">Ele deve incluir a seguinte funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="72578-166">It should include the following functionality.</span></span>  
  
    1.  <span data-ttu-id="72578-167">Busque a referência de objeto do relatório filho no parâmetro *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="72578-167">Fetch the Child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="72578-168">Obtenha a lista de parâmetros do relatório filho no objeto do relatório filho buscado.</span><span class="sxs-lookup"><span data-stu-id="72578-168">Get the child report parameter list from the child report object fetched.</span></span>  
  
    3.  <span data-ttu-id="72578-169">Itere pela coleção do parâmetro e recupere o valor do parâmetro `ProductID` passado pelo relatório pai.</span><span class="sxs-lookup"><span data-stu-id="72578-169">Iterate through the parameter's collection and retrieve the value for the parameter, `ProductID`, passed from the parent report.</span></span>  
  
    4.  <span data-ttu-id="72578-170">Chame a função `GetPurchaseOrderDetail` e passe o valor para o parâmetro `ProductID`.</span><span class="sxs-lookup"><span data-stu-id="72578-170">Call the function, `GetPurchaseOrderDetail`, and pass the value for parameter `ProductID`.</span></span>  
  
    5.  <span data-ttu-id="72578-171">Associar a `PurchaseOrderDetail` DataTable à fonte de dados correspondente do relatório.</span><span class="sxs-lookup"><span data-stu-id="72578-171">Bind the `PurchaseOrderDetail` DataTable with the Report's corresponding data source.</span></span>  
  
         <span data-ttu-id="72578-172">O código completo do manipulador de eventos será semelhante ao conteúdo seguinte.</span><span class="sxs-lookup"><span data-stu-id="72578-172">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                    //Variable to store the parameter value passed from the MainReport.  
                    int productid = 0;  
  
                    //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                    //Get all the parameters passed from the main report to the target report.  
                    //OriginalParametersToDrillthrough actually returns a Generic list of   
                    //type ReportParameter.  
                    IList<ReportParameter> list = report.OriginalParametersToDrillthrough;  
  
                    //Parse through each parameters to fetch the values passed along with them.  
                    foreach (ReportParameter param in list)  
                    {  
                        //Since we know the report has only one parameter and it is not a multivalued,   
                        //we can directly fetch the first value from the Values array.  
                        productid = Convert.ToInt32(param.Values[0].ToString());  
                    }  
  
                    //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail(productid)));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="72578-173">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="72578-173">Save the file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="72578-174">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="72578-174">Next Task</span></span>  
 <span data-ttu-id="72578-175">Você criou, com êxito, um filtro de dados para a tabela de dados definida para o relatório filho.</span><span class="sxs-lookup"><span data-stu-id="72578-175">You have successfully created a data filter for the data table that you defined for the child report.</span></span> <span data-ttu-id="72578-176">Em seguida, você compilará e executará o aplicativo de site.</span><span class="sxs-lookup"><span data-stu-id="72578-176">Next, you will build and run the website application.</span></span>  
  
  
