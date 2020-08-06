---
title: 'Lição 11: criar partições | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 92eb21a8-5fc4-4999-ad37-1332ce26431d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4db5edd5d47fe424ef6e6ad2a822106110209059
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568852"
---
# <a name="lesson-11-create-partitions"></a><span data-ttu-id="824a0-102">Lição 11: Criar partições</span><span class="sxs-lookup"><span data-stu-id="824a0-102">Lesson 11: Create Partitions</span></span>
  <span data-ttu-id="824a0-103">Nesta lição, você criará partições para dividir a tabela Internet Sales em partes lógicas menores que podem ser processadas (Atualizadas) independentemente de outras partições.</span><span class="sxs-lookup"><span data-stu-id="824a0-103">In this lesson, you will create partitions to divide the Internet Sales table into smaller logical parts that can be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="824a0-104">Por padrão, cada tabela que você inclui em seu modelo tem uma partição que inclui todas as colunas e linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="824a0-104">By default, every table you include in your model has one partition which includes all of the table's columns and rows.</span></span> <span data-ttu-id="824a0-105">Para a tabela vendas pela Internet, desejamos dividir os dados por ano; uma partição para cada um dos cinco anos da tabela.</span><span class="sxs-lookup"><span data-stu-id="824a0-105">For the Internet Sales table, we want to divide the data by year; one partition for each of the table's five years.</span></span>  <span data-ttu-id="824a0-106">Cada partição pode ser processada independentemente.</span><span class="sxs-lookup"><span data-stu-id="824a0-106">Each partition can then be processed independently.</span></span> <span data-ttu-id="824a0-107">Para obter mais informações, consulte [Partições &#40;SSAS Tabular&#41;](tabular-models/partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="824a0-107">To learn more, see [Partitions &#40;SSAS Tabular&#41;](tabular-models/partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="824a0-108">Tempo estimado para conclusão desta lição: **15 minutos**</span><span class="sxs-lookup"><span data-stu-id="824a0-108">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="824a0-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="824a0-109">Prerequisites</span></span>  
 <span data-ttu-id="824a0-110">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="824a0-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="824a0-111">Antes de realizar as tarefas desta lição, você deverá ter concluído a lição anterior: [Lição 10: Criar hierarquias](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="824a0-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
## <a name="create-partitions"></a><span data-ttu-id="824a0-112">Criar partições</span><span class="sxs-lookup"><span data-stu-id="824a0-112">Create Partitions</span></span>  
  
#### <a name="to-create-partitions-in-the-internet-sales-table"></a><span data-ttu-id="824a0-113">Para criar partições na tabela Internet Sales</span><span class="sxs-lookup"><span data-stu-id="824a0-113">To create partitions in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="824a0-114">No designer de modelos, clique na tabela **Internet Sales** , clique no menu **Tabela** e em **Partições**.</span><span class="sxs-lookup"><span data-stu-id="824a0-114">In the model designer, click on the **Internet Sales** table, then click on the **Table** menu, and then click **Partitions**.</span></span>  
  
     <span data-ttu-id="824a0-115">A caixa de diálogo **Gerenciador de Partições** é aberta.</span><span class="sxs-lookup"><span data-stu-id="824a0-115">The **Partition Manager** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="824a0-116">Na caixa de diálogo **Gerenciador de partições** , em **partições**, clique na partição **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="824a0-116">In the **Partition Manager** dialog box, in **Partitions**, click the **Internet Sales** partition.</span></span>  
  
3.  <span data-ttu-id="824a0-117">Em **nome da partição**, altere o nome para `Internet Sales 2005` .</span><span class="sxs-lookup"><span data-stu-id="824a0-117">In **Partition Name**, change the name to `Internet Sales 2005`.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="824a0-118">Antes de passar para a próxima etapa, observe que os nomes de coluna na janela Visualização de Tabela exibem essas colunas incluídas na tabela de modelo (marcada) com os nomes de coluna da origem.</span><span class="sxs-lookup"><span data-stu-id="824a0-118">Before continuing to the next step, notice the column names in the Table Preview window display those columns included in the model table (checked) with the column names from the source.</span></span> <span data-ttu-id="824a0-119">Isso acontece porque a janela Visualização de Tabela exibe colunas da tabela de origem, e não da tabela de modelo.</span><span class="sxs-lookup"><span data-stu-id="824a0-119">This is because the Table Preview window displays columns from the source table, not from the model table.</span></span>  
  
4.  <span data-ttu-id="824a0-120">Selecione o botão **Editor de Consultas** logo acima do lado direito da janela de visualização.</span><span class="sxs-lookup"><span data-stu-id="824a0-120">Select the **Query Editor** button just above the right side of the preview window.</span></span>  
  
     <span data-ttu-id="824a0-121">Como você deseja que a partição inclua apenas essas linhas em um certo período, você deve incluir uma cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="824a0-121">Because you want the partition to include only those rows within a certain period, you must include a WHERE clause.</span></span> <span data-ttu-id="824a0-122">Você só pode criar uma cláusula WHERE usando uma Instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="824a0-122">You can only create a WHERE clause by using a SQL Statement.</span></span>  
  
5.  <span data-ttu-id="824a0-123">No campo **Instrução SQL** , substitua a instrução existente colando a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="824a0-123">In the **SQL Statement** field, replace the existing statement by pasting in the following statement:</span></span>  
  
    ```  
    SELECT   
    [dbo].[FactInternetSales].[ProductKey],  
    [dbo].[FactInternetSales].[CustomerKey],  
    [dbo].[FactInternetSales].[PromotionKey],  
    [dbo].[FactInternetSales].[CurrencyKey],  
    [dbo].[FactInternetSales].[SalesTerritoryKey],  
    [dbo].[FactInternetSales].[SalesOrderNumber],  
    [dbo].[FactInternetSales].[SalesOrderLineNumber],  
    [dbo].[FactInternetSales].[RevisionNumber],  
    [dbo].[FactInternetSales].[OrderQuantity],  
    [dbo].[FactInternetSales].[UnitPrice],  
    [dbo].[FactInternetSales].[ExtendedAmount],  
    [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
    [dbo].[FactInternetSales].[DiscountAmount],  
    [dbo].[FactInternetSales].[ProductStandardCost],  
    [dbo].[FactInternetSales].[TotalProductCost],  
    [dbo].[FactInternetSales].[SalesAmount],  
    [dbo].[FactInternetSales].[TaxAmt],  
    [dbo].[FactInternetSales].[Freight],  
    [dbo].[FactInternetSales].[CarrierTrackingNumber],  
    [dbo].[FactInternetSales].[CustomerPONumber],  
    [dbo].[FactInternetSales].[OrderDate],  
    [dbo].[FactInternetSales].[DueDate],  
    [dbo].[FactInternetSales].[ShipDate]   
    FROM [dbo].[FactInternetSales]  
    WHERE (([OrderDate] >= N'2005-01-01 00:00:00') AND ([OrderDate] < N'2006-01-01 00:00:00'))  
    ```  
  
     <span data-ttu-id="824a0-124">Essa instrução especifica que a partição deve incluir todos os dados nas linhas onde OrderDate refere-se ao ano civil 2005 conforme especificado na cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="824a0-124">This statement specifies the partition should include all of the data in those rows where the OrderDate is for the 2005 calendar year as specified in the WHERE clause.</span></span>  
  
6.  <span data-ttu-id="824a0-125">Clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="824a0-125">Click **Validate**.</span></span>  
  
     <span data-ttu-id="824a0-126">Observe que um aviso é exibido, declarando que determinadas colunas não estão presentes na origem.</span><span class="sxs-lookup"><span data-stu-id="824a0-126">Notice a warning is displayed stating that certain columns are not present in source.</span></span> <span data-ttu-id="824a0-127">Isso ocorre porque, na [lição 3: renomear colunas](rename-columns.md), você renomeou essas colunas na tabela vendas pela Internet no modelo para serem diferentes daquelas mesmas colunas na origem.</span><span class="sxs-lookup"><span data-stu-id="824a0-127">This is because in [Lesson 3: Rename Columns](rename-columns.md), you renamed those columns in the Internet Sales table in the model to be different from those same columns at the source.</span></span>  
  
#### <a name="to-create-a-partition-for-the-2006-year-in-the-internet-sales-table"></a><span data-ttu-id="824a0-128">Para criar uma partição para o ano de 2006 na tabela vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="824a0-128">To create a partition for the 2006 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="824a0-129">Na caixa de diálogo **Gerenciador de partições** , em **partições**, clique na `Internet Sales 2005` partição que você acabou de criar e, em seguida, **Copie**.</span><span class="sxs-lookup"><span data-stu-id="824a0-129">In the **Partition Manager** dialog box, in **Partitions**, click the `Internet Sales 2005` partition you just created, and then **Copy**.</span></span>  
  
2.  <span data-ttu-id="824a0-130">Em **nome da partição**, digite `Internet Sales 2006` .</span><span class="sxs-lookup"><span data-stu-id="824a0-130">In **Partition Name**, type `Internet Sales 2006`.</span></span>  
  
3.  <span data-ttu-id="824a0-131">Na instrução SQL, para que a partição inclua somente as linhas do ano 2006, substitua a cláusula WHERE pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="824a0-131">In the SQL Statement, in-order for the partition to include only those rows for the 2006 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2006-01-01 00:00:00') AND ([OrderDate] < N'2007-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2007-year-in-the-internet-sales-table"></a><span data-ttu-id="824a0-132">Para criar uma partição para o ano de 2007 na tabela vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="824a0-132">To create a partition for the 2007 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="824a0-133">Na caixa de diálogo **Gerenciador de Partições** , clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="824a0-133">In the **Partition Manager** dialog box, click **Copy**.</span></span>  
  
2.  <span data-ttu-id="824a0-134">Em **nome da partição**, digite `Internet Sales 2007` .</span><span class="sxs-lookup"><span data-stu-id="824a0-134">In **Partition Name**, type `Internet Sales 2007`.</span></span>  
  
3.  <span data-ttu-id="824a0-135">Em **alternar para**, selecione **Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="824a0-135">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="824a0-136">Na instrução SQL, para que a partição inclua somente as linhas do ano 2007, substitua a cláusula WHERE pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="824a0-136">In the SQL Statement, in-order for the partition to include only those rows for the 2007 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2007-01-01 00:00:00') AND ([OrderDate] < N'2008-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2008-year-in-the-internet-sales-table"></a><span data-ttu-id="824a0-137">Para criar uma partição para o ano de 2008 na tabela vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="824a0-137">To create a partition for the 2008 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="824a0-138">Na caixa de diálogo **Gerenciador de Partições** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="824a0-138">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="824a0-139">Em **nome da partição**, digite `Internet Sales 2008` .</span><span class="sxs-lookup"><span data-stu-id="824a0-139">In **Partition Name**, type `Internet Sales 2008`.</span></span>  
  
3.  <span data-ttu-id="824a0-140">Em **alternar para**, selecione **Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="824a0-140">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="824a0-141">Na instrução SQL, para que a partição inclua somente as linhas do ano 2008, substitua a cláusula WHERE pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="824a0-141">In the SQL Statement, in-order for the partition to include only those rows for the 2008 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2008-01-01 00:00:00') AND ([OrderDate] < N'2009-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2009-year-in-the-internet-sales-table"></a><span data-ttu-id="824a0-142">Para criar uma partição para o ano 2009 na tabela Internet Sales</span><span class="sxs-lookup"><span data-stu-id="824a0-142">To create a partition for the 2009 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="824a0-143">Na caixa de diálogo **Gerenciador de Partições** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="824a0-143">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="824a0-144">Em **nome da partição**, digite `Internet Sales 2009` .</span><span class="sxs-lookup"><span data-stu-id="824a0-144">In **Partition Name**, type `Internet Sales 2009`.</span></span>  
  
3.  <span data-ttu-id="824a0-145">Em **alternar para**, selecione **Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="824a0-145">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="824a0-146">Na Instrução SQL, para que a partição inclua somente as linhas do ano 2009, substitua a cláusula WHERE pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="824a0-146">In the SQL Statement, in-order for the partition to include only those rows for the 2009 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2009-01-01 00:00:00') AND ([OrderDate] < N'2010-01-01 00:00:00'))  
    ```  
  
## <a name="process-partitions"></a><span data-ttu-id="824a0-147">Processar partições</span><span class="sxs-lookup"><span data-stu-id="824a0-147">Process Partitions</span></span>  
 <span data-ttu-id="824a0-148">Na caixa de diálogo **Gerenciador de Partições** , observe o asterisco (**\***) ao lado dos nomes de partição de cada nova partição que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="824a0-148">In the **Partition Manager** dialog box, notice the asterisk (**\***) next to the partition names for each of the new partitions you just created.</span></span> <span data-ttu-id="824a0-149">Isso indica que a partição não foi processada (atualizada).</span><span class="sxs-lookup"><span data-stu-id="824a0-149">This indicates that the partition has not been processed (refreshed).</span></span> <span data-ttu-id="824a0-150">Quando você cria novas partições, deve executar a operação Processar Partições ou Processar Tabela para atualizar os dados nessas partições.</span><span class="sxs-lookup"><span data-stu-id="824a0-150">When you create new partitions, you should run a Process Partitions or Process Table operation to refresh the data in those partitions.</span></span>  
  
#### <a name="to-process-internet-sales-partitions"></a><span data-ttu-id="824a0-151">Para processar partições Internet Sales</span><span class="sxs-lookup"><span data-stu-id="824a0-151">To process Internet Sales partitions</span></span>  
  
1.  <span data-ttu-id="824a0-152">Clique em **OK** para fechar a caixa de diálogo **Gerenciador de Partições** .</span><span class="sxs-lookup"><span data-stu-id="824a0-152">Click **OK** to close the **Partition Manager** dialog box.</span></span>  
  
2.  <span data-ttu-id="824a0-153">No designer de modelos, clique na tabela **Internet Sales** , clique no menu **Modelo** , aponte para **Processar** (Atualizar) e clique em **Processar Partições**.</span><span class="sxs-lookup"><span data-stu-id="824a0-153">In the model designer, click the **Internet Sales** table, then click the **Model** menu, then point to **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
3.  <span data-ttu-id="824a0-154">Na caixa de diálogo **Processar Partições** , verifique se o **Modo** está definido como **Processo Padrão**.</span><span class="sxs-lookup"><span data-stu-id="824a0-154">In the **Process Partitions** dialog box, verify the **Mode** is set to **Process Default**.</span></span>  
  
4.  <span data-ttu-id="824a0-155">Selecione a caixa de seleção na coluna **Processo** para cada uma das cinco partições criadas e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="824a0-155">Select the checkbox in the **Process** column for each of the five partitions you created, and then click **OK**.</span></span>  
  
     <span data-ttu-id="824a0-156">Se você for solicitado a fornecer credenciais de Representação, insira o nome de usuário e a senha do Windows que especificou na Lição 2, etapa 6.</span><span class="sxs-lookup"><span data-stu-id="824a0-156">If you are prompted for Impersonation credentials, enter the Windows user name and password you specified in Lesson 2, step 6.</span></span>  
  
     <span data-ttu-id="824a0-157">A caixa de diálogo **processo de dados** é exibida e exibe os detalhes do processo para cada partição.</span><span class="sxs-lookup"><span data-stu-id="824a0-157">The **Data Process** dialog box then appears and displays process details for each partition.</span></span> <span data-ttu-id="824a0-158">Observe que um número diferente de linhas para cada partição é transferido.</span><span class="sxs-lookup"><span data-stu-id="824a0-158">Notice that a different number of rows for each partition are transferred.</span></span> <span data-ttu-id="824a0-159">Isso acontece porque cada partição inclui somente as linhas referentes ao ano especificado na cláusula WHERE da Instrução SQL:</span><span class="sxs-lookup"><span data-stu-id="824a0-159">This is because each partition includes only those rows for the year specified in the WHERE clause in the SQL Statement.</span></span> <span data-ttu-id="824a0-160">Não há nenhum dado para o ano 2010.</span><span class="sxs-lookup"><span data-stu-id="824a0-160">There is no data for the 2010 year.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="824a0-161">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="824a0-161">Next Steps</span></span>  
 <span data-ttu-id="824a0-162">Para continuar este tutorial, vá para a próxima lição: [Lição 12: Criar funções](lesson-11-create-roles.md).</span><span class="sxs-lookup"><span data-stu-id="824a0-162">To continue this tutorial, go to the next lesson: Lesson: [Lesson 12: Create Roles](lesson-11-create-roles.md).</span></span>  
  
  
