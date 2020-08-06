---
title: 'Lição 2: Modificando as propriedades de fonte de dados de relatório | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c962b0ff-ce8a-4742-8262-dc730901afcf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05e56a58ce28ee1e1e450d3af012cbd1ffe668ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570529"
---
# <a name="lesson-2-modifying-the-report-data-source-properties"></a><span data-ttu-id="a0c15-102">Lesson 2: Modifying the Report Data Source Properties</span><span class="sxs-lookup"><span data-stu-id="a0c15-102">Lesson 2: Modifying the Report Data Source Properties</span></span>
  <span data-ttu-id="a0c15-103">Nesta lição, você usará o Gerenciador de Relatórios para selecionar um relatório que será entregue a destinatários.</span><span class="sxs-lookup"><span data-stu-id="a0c15-103">In this lesson, you will use Report Manager to select a report that will be delivered to recipients.</span></span> <span data-ttu-id="a0c15-104">A assinatura controlada por dados que será definida distribuirá o relatório **Pedidos de Vendas** criado no tutorial [Criar um relatório de tabela básico &#40;Tutorial do SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="a0c15-104">The data-driven subscription that you will define will distribute the **Sales Order** report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span></span> <span data-ttu-id="a0c15-105">Nas etapas a seguir, você modificará as informações da conexão de fonte de dados usadas pelo relatório para obter dados.</span><span class="sxs-lookup"><span data-stu-id="a0c15-105">In the steps that follow, you will modify the data source connection information used by the report to get data.</span></span> <span data-ttu-id="a0c15-106">Somente relatórios que usam **credenciais armazenadas** para acessar uma fonte de dados de relatório podem ser distribuídos por uma assinatura controlada por dados.</span><span class="sxs-lookup"><span data-stu-id="a0c15-106">Only reports that use **stored credentials** to access a report data source can be distributed through a data-driven subscription.</span></span> <span data-ttu-id="a0c15-107">Credenciais armazenadas são necessárias para o processamento de relatório autônomo.</span><span class="sxs-lookup"><span data-stu-id="a0c15-107">Stored credentials are necessary for unattended report processing.</span></span>

 <span data-ttu-id="a0c15-108">Você também modificará o conjunto de dados e relatório para usar um parâmetro para filtrar o relatório no `[Order]` para que a assinatura possa produzir instâncias diferentes do relatório para pedidos específicos e formatos de renderização.</span><span class="sxs-lookup"><span data-stu-id="a0c15-108">You will also modify the dataset and report to use a parameter to filter the report on the `[Order]` so the subscription can output different instances of the report for specific orders and rendering formats.</span></span>

 <span data-ttu-id="a0c15-109">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="a0c15-109">**In this topic:**</span></span>

-   [<span data-ttu-id="a0c15-110">Para modificar as propriedades de fonte de dados</span><span class="sxs-lookup"><span data-stu-id="a0c15-110">To Modify the Data Source Properties</span></span>](#bkmk_modify_datasource)

-   [<span data-ttu-id="a0c15-111">Para modificar o AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="a0c15-111">To Modify the AdventureWorksDataset</span></span>](#bkmk_modify_dataset)

-   [<span data-ttu-id="a0c15-112">Para adicionar um parâmetro de relatório e republicar o relatório</span><span class="sxs-lookup"><span data-stu-id="a0c15-112">To Add a Report Parameter and Republish the Report</span></span>](#bkmk_add_reportparameter)

-   [<span data-ttu-id="a0c15-113">Para reimplantar o relatório</span><span class="sxs-lookup"><span data-stu-id="a0c15-113">To Re-deploy the Report</span></span>](#bkmk_redeploy)

##  <a name="to-modify-the-data-source-properties"></a><a name="bkmk_modify_datasource"></a><span data-ttu-id="a0c15-114">Para modificar as propriedades da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="a0c15-114">To Modify the Data Source Properties</span></span>

1.  <span data-ttu-id="a0c15-115">Inicie [Report Manager &#40;modo nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) com privilégios de administrador, por exemplo, clique com o botão direito do mouse no ícone do Internet Explorer e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>

2.  <span data-ttu-id="a0c15-116">Navegue até a pasta que contém o relatório **Pedidos de Vendas** e, no menu de contexto do relatório, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-116">Browse to the folder containing the **Sales Orders** report and in the context menu of the report, click **Manage**.</span></span>

     <span data-ttu-id="a0c15-117">![Abrir o menu de contexto de relatório e selecionar gerenciar](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Abrir o menu de contexto de relatório e selecionar gerenciar")</span><span class="sxs-lookup"><span data-stu-id="a0c15-117">![Open the report context menu and select manage](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Open the report context menu and select manage")</span></span>

3.  <span data-ttu-id="a0c15-118">Clique na guia **Fontes de Dados** .</span><span class="sxs-lookup"><span data-stu-id="a0c15-118">Click the **Data Sources** tab.</span></span>

4.  <span data-ttu-id="a0c15-119">Para **Tipo de conexão**, selecione **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-119">For **Connection Type**, select **Microsoft SQL Server**.</span></span>

5.  <span data-ttu-id="a0c15-120">A cadeia de conexão da fonte de dados personalizada será a seguinte e presumirá que o banco de dados de exemplo esteja em um servidor de banco de dados local:</span><span class="sxs-lookup"><span data-stu-id="a0c15-120">The custom data source connection string will be the following and it assumes that the sample database is on a local database server:</span></span>

    ```
    Data source=localhost; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="a0c15-121">Clique em **Credenciais armazenadas com segurança no servidor de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-121">Click **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="a0c15-122">Digite seu nome de usuário (use o formato *domain\user*) e a senha.</span><span class="sxs-lookup"><span data-stu-id="a0c15-122">Type your user name (use the format *domain\user*) and password.</span></span> <span data-ttu-id="a0c15-123">Se você não tiver permissão para acessar o banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , especifique um logon que tenha tal permissão.</span><span class="sxs-lookup"><span data-stu-id="a0c15-123">If you do not have permission to access the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database, specify a login that does.</span></span>

8.  <span data-ttu-id="a0c15-124">Clique em **Usar as credenciais do Windows ao conectar-se à fonte de dados**e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-124">Click **Use as windows credentials when connecting to the data source**, and then click **OK**.</span></span> <span data-ttu-id="a0c15-125">Se não estiver usando uma conta de domínio (se você estiver um logon do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], por exemplo), não marque essa caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="a0c15-125">If you are not using a domain account (for example, if you are using a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login), do not click this checkbox.</span></span>

9. <span data-ttu-id="a0c15-126">Clique em **Testar Conexão** para verificar se é possível conectar-se à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a0c15-126">Click **Test Connection** to verify you can connect to the data source.</span></span>

10. <span data-ttu-id="a0c15-127">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-127">Click **Apply**.</span></span>

11. <span data-ttu-id="a0c15-128">Exiba o relatório para verificar se o relatório está sendo executado com as credenciais especificadas.</span><span class="sxs-lookup"><span data-stu-id="a0c15-128">View the report to verify that the report runs with the credentials you specified.</span></span> <span data-ttu-id="a0c15-129">Para exibir o relatório, clique na guia **Exibir** . Observe que, quando o relatório estiver aberto, você deverá selecionar um nome de funcionário e clicar no botão **Exibir relatório** para exibir o relatório.</span><span class="sxs-lookup"><span data-stu-id="a0c15-129">To view the report, click the **View** tab. Note that once the report is open, you must select an Employee name and then click the **View Report** button to view the report.</span></span>

##  <a name="to-modify-the-adventureworksdataset"></a><a name="bkmk_modify_dataset"></a><span data-ttu-id="a0c15-130">Para modificar o AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="a0c15-130">To Modify the AdventureWorksDataset</span></span>

1.  <span data-ttu-id="a0c15-131">Abra o relatório Pedidos de Vendas no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0c15-131">Open the Sales Orders report in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span></span>

2.  <span data-ttu-id="a0c15-132">Clique com o botão direito do mouse no conjunto de dados `AdventureWorksDataset` e clique em **Propriedades do Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-132">Right-click the dataset `AdventureWorksDataset` and click **Dataset Properties**.</span></span>

3.  <span data-ttu-id="a0c15-133">Adicione a instrução `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` antes da instrução `Group By` .</span><span class="sxs-lookup"><span data-stu-id="a0c15-133">Add the statement `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` before the `Group By` statement.</span></span> <span data-ttu-id="a0c15-134">A sintaxe da consulta completa é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="a0c15-134">The full query syntax is the following:</span></span>

    ```
    SELECT soh.OrderDate AS Date, soh.SalesOrderNumber AS [Order], pps.Name AS Subcat, pp.Name AS Product, SUM(sd.OrderQty) AS Qty, SUM(sd.LineTotal)  AS LineTotal
    FROM Sales.SalesPerson AS sp INNER JOIN
      Sales.SalesOrderHeader AS soh ON sp.BusinessEntityID = soh.SalesPersonID INNER JOIN
       Sales.SalesOrderDetail AS sd ON sd.SalesOrderID = soh.SalesOrderID INNER JOIN
       Production.Product AS pp ON sd.ProductID = pp.ProductID
    INNER JOIN
       Production.ProductSubcategory AS pps ON pp.ProductSubcategoryID = pps.ProductSubcategoryID 
    INNER JOIN
        Production.ProductCategory AS ppc ON ppc.ProductCategoryID = pps.ProductCategoryID

    WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)

    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name, soh.SalesPersonID
    HAVING (ppc.Name = 'Clothing')
    ```

4.  <span data-ttu-id="a0c15-135">Clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="a0c15-135">Click **OK**</span></span>

##  <a name="to-add-a-report-parameter-and-republish-the-report"></a><a name="bkmk_add_reportparameter"></a><span data-ttu-id="a0c15-136">Para adicionar um parâmetro de relatório e republicar o relatório</span><span class="sxs-lookup"><span data-stu-id="a0c15-136">To Add a Report Parameter and Republish the Report</span></span>

1.  <span data-ttu-id="a0c15-137">No painel **Dados do Relatório** , clique em **Novo** e em **Parâmetro...**</span><span class="sxs-lookup"><span data-stu-id="a0c15-137">In the **Report Data** pane click **New** and then click **Parameter...**</span></span>

2.  <span data-ttu-id="a0c15-138">Em **Nome**, digite `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="a0c15-138">In **Name**, type `OrderNumber`.</span></span>

3.  <span data-ttu-id="a0c15-139">Em **Aviso**, digite `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="a0c15-139">In **Prompt**, type `OrderNumber`.</span></span>

4.  <span data-ttu-id="a0c15-140">Selecione **Permitir valor em branco ("")**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-140">Select **Allow blank value ("")**.</span></span>

5.  <span data-ttu-id="a0c15-141">Selecione **Permitir valor nulo**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-141">Select **Allow null value**.</span></span>

6.  <span data-ttu-id="a0c15-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-142">Click **OK**.</span></span> <span data-ttu-id="a0c15-143">O parâmetro será adicionado ao **Painel Dados do Relatório** e ele se parecerá com a seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="a0c15-143">The parameter will be added to the **Report Data pane** and it will look like the following image:</span></span>

     <span data-ttu-id="a0c15-144">![O novo parâmetro é adicionado ao painel de dados do relatório](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "O novo parâmetro é adicionado ao painel de dados do relatório")</span><span class="sxs-lookup"><span data-stu-id="a0c15-144">![The new parameter is added to the Report Data pane](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "The new parameter is added to the Report Data pane")</span></span>

7.  <span data-ttu-id="a0c15-145">Clique na guia **Visualização** para executar o relatório. Observe a caixa de entrada de parâmetro na parte superior do relatório.</span><span class="sxs-lookup"><span data-stu-id="a0c15-145">Click the **Preview** tab to run the report.Note the parameter input box at the top of the report.</span></span> <span data-ttu-id="a0c15-146">Você pode:</span><span class="sxs-lookup"><span data-stu-id="a0c15-146">You can either:</span></span>

    -   <span data-ttu-id="a0c15-147">Clicar em Exibir Relatório para ver o relatório completo sem usar um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a0c15-147">Click View Report to see the full report without using a parameter.</span></span>

    -   <span data-ttu-id="a0c15-148">Cancelar a seleção da opção Nula e digitar um número de pedido, por exemplo so71949 para exibir somente este pedido no relatório.</span><span class="sxs-lookup"><span data-stu-id="a0c15-148">Unselect the Null option and type an order number, for example so71949 to view only the one order in the report.</span></span>

         <span data-ttu-id="a0c15-149">![Visualizador de Relatórios com área de parâmetro visível](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Visualizador de Relatórios com área de parâmetro visível")</span><span class="sxs-lookup"><span data-stu-id="a0c15-149">![Report viewer with parameter area visible](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Report viewer with parameter area visible")</span></span>

8.  <span data-ttu-id="a0c15-150">Reimplantar o relatório para que a configuração de assinatura na próxima lição possa utilizar as alterações que você fez nesta lição.</span><span class="sxs-lookup"><span data-stu-id="a0c15-150">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="a0c15-151">Para obter mais informações sobre as propriedades do projeto usadas no tutorial de tabela, consulte a seção ' para publicar o relatório no servidor de relatório (opcional) ' da [lição 6: adicionando agrupamentos e totais &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a0c15-151">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

##  <a name="to-re-deploy-the-report"></a><a name="bkmk_redeploy"></a><span data-ttu-id="a0c15-152">Para reimplantar o relatório</span><span class="sxs-lookup"><span data-stu-id="a0c15-152">To Re-deploy the Report</span></span>

1.  <span data-ttu-id="a0c15-153">Reimplantar o relatório para que a configuração de assinatura na próxima lição possa utilizar as alterações que você fez nesta lição.</span><span class="sxs-lookup"><span data-stu-id="a0c15-153">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="a0c15-154">Para obter mais informações sobre as propriedades do projeto usadas no tutorial de tabela, consulte a seção ' para publicar o relatório no servidor de relatório (opcional) ' da [lição 6: adicionando agrupamentos e totais &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a0c15-154">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

2.  <span data-ttu-id="a0c15-155">Na barra de ferramentas, clique em **Compilar** e, em seguida, em **Implantar tutorial**.</span><span class="sxs-lookup"><span data-stu-id="a0c15-155">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0c15-156">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a0c15-156">Next Steps</span></span>
 <span data-ttu-id="a0c15-157">Você configurou o relatório com êxito para obter dados usando credenciais armazenadas.</span><span class="sxs-lookup"><span data-stu-id="a0c15-157">You successfully configured the report to get data using stored credentials.</span></span> <span data-ttu-id="a0c15-158">Depois, especifique a assinatura usando as páginas de Assinatura Controlada por Dados no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="a0c15-158">Next, you specify the subscription using the Data-Driven Subscription pages in Report Manager.</span></span> <span data-ttu-id="a0c15-159">Consulte [Lição 3: Definindo uma assinatura controlada por dados](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="a0c15-159">See [Lesson 3: Defining a Data-Driven Subscription](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0c15-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0c15-160">See Also</span></span>
 <span data-ttu-id="a0c15-161">[Gerenciar fontes de dados de relatório](report-data/manage-report-data-sources.md) [especificar informações de credenciais e de conexão para fontes de dados de relatório](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [criar uma assinatura controlada por dados &#40;tutorial do SSRS&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [criar um relatório de tabela básico &#40;tutorial do SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="a0c15-161">[Manage Report Data Sources](report-data/manage-report-data-sources.md) [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span></span>


