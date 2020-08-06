---
title: 'Tarefa 4 (opcional): combinação, correspondência e publicação de novo conjunto de dados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13a13f03-b307-4555-8e33-6d98c459d994
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ddcec19fa8b957bf77b6ea5269b4d033779bdf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569748"
---
# <a name="task-4-optional-combining-matching-and-publishing-new-set-of-data"></a><span data-ttu-id="fd279-102">Tarefa 4 (Opcional): Combinando, correspondendo e publicando o novo conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="fd279-102">Task 4 (Optional): Combining, Matching, and Publishing New Set of Data</span></span>
  <span data-ttu-id="fd279-103">Com o tempo, você desejará adicionar mais dados ao repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="fd279-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="fd279-104">Antes de adicionar dados, pode ser útil comparar os novos dados com os dados que já são gerenciados no MDS, para garantir que você não esteja adicionando dados duplicados ou imprecisos.</span><span class="sxs-lookup"><span data-stu-id="fd279-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure that you are not adding duplicate or inaccurate data.</span></span> <span data-ttu-id="fd279-105">No Suplemento Master Data Services para Excel, você pode combinar dados de duas planilhas e comparar esses dados para identificar e remover duplicatas antes de publicar os dados no MDS.</span><span class="sxs-lookup"><span data-stu-id="fd279-105">In the Master Data Services Add-in for Excel, you can combine data from two worksheets and the compare the data to identify and remove duplicates before publishing the data to MDS.</span></span> <span data-ttu-id="fd279-106">O recurso de correspondência do Suplemento MDS do Excel usa a funcionalidade correspondente do DQS para identificar correspondências nos dados.</span><span class="sxs-lookup"><span data-stu-id="fd279-106">The matching feature of MDS Excel Add-in uses the DQS matching functionality to identify matches in the data.</span></span> <span data-ttu-id="fd279-107">Nesta tarefa, você combinará dados de duas planilhas em uma e executará a atividade de correspondência para identificar e remover duplicatas antes de publicar no MDS.</span><span class="sxs-lookup"><span data-stu-id="fd279-107">In this task, you will combine data from a two worksheets into one and then perform the matching activity to identify and remove duplicates before publishing to MDS.</span></span> <span data-ttu-id="fd279-108">Consulte [correspondência de qualidade de dados nos tópicos suplemento MDS para Excel](https://msdn.microsoft.com/library/hh548681.aspx) e [combinar dados](https://msdn.microsoft.com/library/hh548680.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="fd279-108">See [Data Quality Matching in the MDS Add-in for Excel](https://msdn.microsoft.com/library/hh548681.aspx) and [Combine Data](https://msdn.microsoft.com/library/hh548680.aspx) topics for more details.</span></span>  
  
1.  <span data-ttu-id="fd279-109">Inicie a nova instância do **Excel**.</span><span class="sxs-lookup"><span data-stu-id="fd279-109">Launch new instance of **Excel**.</span></span> <span data-ttu-id="fd279-110">Clique em **Iniciar**, aponte para **executar**, digite **Excel**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd279-110">Click **Start**, point to **Run**, type **Excel**, and click **OK**.</span></span>  
  
2.  <span data-ttu-id="fd279-111">Alterne para a guia **dados mestres** clicando em **dados mestres** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="fd279-111">Switch to the **Master Data** tab by clicking **Master Data** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="fd279-112">Clique em **conectar** na faixa de **-se no grupo conectar e carregar** para se conectar ao **servidor MDS**.</span><span class="sxs-lookup"><span data-stu-id="fd279-112">Click **Connect** on the ribbon in the **Connect and Load** group to connect to the **MDS server**.</span></span> <span data-ttu-id="fd279-113">Você configurou essa conexão anteriormente nesta lição.</span><span class="sxs-lookup"><span data-stu-id="fd279-113">You have configured this connection earlier in this lesson.</span></span>  
  
     <span data-ttu-id="fd279-114">![Excel - Mostrar Botão do Explorer na guia Dados Mestre](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Mostrar Botão do Explorer na guia Dados Mestre")</span><span class="sxs-lookup"><span data-stu-id="fd279-114">![Excel - Show Explorer Button on Master Data Tabl](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Show Explorer Button on Master Data Tabl")</span></span>  
  
4.  <span data-ttu-id="fd279-115">Você deve ver o painel de **Data Explorer mestre** à direita.</span><span class="sxs-lookup"><span data-stu-id="fd279-115">You should see the **Master Data Explorer** pane to the right.</span></span> <span data-ttu-id="fd279-116">Se você não vir o Data Explorer mestre, clique no botão **Mostrar Explorer** na faixa de faixas.</span><span class="sxs-lookup"><span data-stu-id="fd279-116">If you do not see the Master Data Explorer, click **Show Explorer** button on the ribbon.</span></span>  
  
5.  <span data-ttu-id="fd279-117">Na janela de **Data Explorer mestre** , selecione **fornecedores** na lista suspensa para o **modelo**.</span><span class="sxs-lookup"><span data-stu-id="fd279-117">In the **Master Data Explorer** Window, select **Suppliers** in the drop-down list for the **Model**.</span></span> <span data-ttu-id="fd279-118">Você verá que o modelo tem uma entidade: **fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="fd279-118">You should see that the model has one entity: **Supplier**.</span></span>  
  
     <span data-ttu-id="fd279-119">![Excel - Janela Master Data Explorer](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Janela Master Data Explorer")</span><span class="sxs-lookup"><span data-stu-id="fd279-119">![Excel - Master Data Explorer Window](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Master Data Explorer Window")</span></span>  
  
6.  <span data-ttu-id="fd279-120">Clique duas vezes em **fornecedor** na lista de entidades para carregar os membros da entidade na planilha do Excel.</span><span class="sxs-lookup"><span data-stu-id="fd279-120">Double-click **Supplier** in the entity list to load the entity members into the Excel worksheet.</span></span>  
  
7.  <span data-ttu-id="fd279-121">Clique em **Planilha2** na parte inferior para alternar para a guia **Planilha2** . Se você não vir a **Planilha2**, adicione uma nova planilha.</span><span class="sxs-lookup"><span data-stu-id="fd279-121">Click **Sheet2** at the bottom to switch to the **Sheet2** tab. If you do not see **Sheet2**, add a new worksheet.</span></span>  
  
8.  <span data-ttu-id="fd279-122">Abra **Suppliers.xls** arquivo (o arquivo de entrada original que está incluído nos arquivos do tutorial) e copie todas as (três) linhas da planilha **CombineAndCleanse** para **Planilha2**.</span><span class="sxs-lookup"><span data-stu-id="fd279-122">Open **Suppliers.xls** file (the original input file that is included in the tutorial files) and copy all (three) rows from the **CombineAndCleanse** worksheet to **Sheet2**.</span></span>  
  
9. <span data-ttu-id="fd279-123">Volte para a planilha de **fornecedores** no **livro 1-Microsoft Excel** (não o Excel de lista de fornecedores com **limpeza e correspondência** ) que está conectado ao **MDS**.</span><span class="sxs-lookup"><span data-stu-id="fd279-123">Switch back to the **Supplier** sheet in the **Book 1 - Microsoft Excel** (not the **Cleansed and Matched Supplier List** Excel) that is connected to **MDS**.</span></span>  
  
10. <span data-ttu-id="fd279-124">Clique em **Dados Mestres** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="fd279-124">Click **Master Data** on the menu bar.</span></span>  
  
11. <span data-ttu-id="fd279-125">Clique em **combinar dados** na faixa de faixas.</span><span class="sxs-lookup"><span data-stu-id="fd279-125">Click **Combine Data** on the ribbon.</span></span> <span data-ttu-id="fd279-126">Você verá a caixa de diálogo **combinar dados** .</span><span class="sxs-lookup"><span data-stu-id="fd279-126">You will see the **Combine Data** dialog box.</span></span>  
  
12. <span data-ttu-id="fd279-127">Na caixa de diálogo **combinar dados** , clique no botão ao lado da caixa **de texto intervalo a ser combinado com dados do MDS** , conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd279-127">In the **Combine Data** dialog box, click the button next to **Range to combine with MDS data** text box as shown in the following image.</span></span>  
  
     <span data-ttu-id="fd279-128">![Excel - Caixa de diálogo Combinar Dados](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Caixa de diálogo Combinar Dados")</span><span class="sxs-lookup"><span data-stu-id="fd279-128">![Excel - Combine Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Combine Data Dialog Box")</span></span>  
  
13. <span data-ttu-id="fd279-129">Você deverá ver a caixa de diálogo reduzida agora.</span><span class="sxs-lookup"><span data-stu-id="fd279-129">You should see the shrunken dialog box now.</span></span> <span data-ttu-id="fd279-130">Agora, clique em **Planilha2** para alternar para a guia **Planilha2** que tem os novos dados de fornecedor com 4 linhas (incluindo uma linha de cabeçalho).</span><span class="sxs-lookup"><span data-stu-id="fd279-130">Now, click **Sheet2** to switch to the **Sheet2** tab that has the new supplier data with 4 rows (including one header row).</span></span>  
  
14. <span data-ttu-id="fd279-131">Na **Planilha2**, selecione **todas as linhas, incluindo a linha de cabeçalho** (mesmo que pareçam já estar selecionadas).</span><span class="sxs-lookup"><span data-stu-id="fd279-131">In the **Sheet2**, select **all rows including the header row** (even if they seem to be already selected).</span></span> <span data-ttu-id="fd279-132">Você deve ver o **intervalo a combinar com dados do MDS** é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fd279-132">You should see the **Range to combine with MDS data** is automatically updated.</span></span>  
  
     <span data-ttu-id="fd279-133">![Excel - Caixa de diálogo Combinar Dados - minimizada](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Caixa de diálogo Combinar Dados - minimizada")</span><span class="sxs-lookup"><span data-stu-id="fd279-133">![Excel - Combine Data Dialog Box - Minimized](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Combine Data Dialog Box - Minimized")</span></span>  
  
15. <span data-ttu-id="fd279-134">Volte para a guia **fornecedores** sem fechar a caixa de diálogo **combinar dados** .</span><span class="sxs-lookup"><span data-stu-id="fd279-134">Switch back to the **Suppliers** tab without closing the **Combine Data** dialog box.</span></span>  
  
16. <span data-ttu-id="fd279-135">Clique no **botão** ao lado da **caixa de texto**.</span><span class="sxs-lookup"><span data-stu-id="fd279-135">Click the **button** next to the **text box**.</span></span> <span data-ttu-id="fd279-136">Você deverá ver a caixa de diálogo expandida agora.</span><span class="sxs-lookup"><span data-stu-id="fd279-136">You should see that the dialog box is expanded now.</span></span> <span data-ttu-id="fd279-137">Você deve ver que todos os mapeamentos entre colunas da **entidade** do **fornecedor** MDS para colunas do **Excel** são populados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fd279-137">You should see all the mappings between columns of the **Supplier** MDS **entity** to **Excel** columns are automatically populated.</span></span>  
  
     <span data-ttu-id="fd279-138">![Excel - Caixa de diálogo Combinar Dados - preenchida com dados](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Caixa de diálogo Combinar Dados - preenchida com dados")</span><span class="sxs-lookup"><span data-stu-id="fd279-138">![Excel - Combine Data Dialog Box Filled with Data](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Combine Data Dialog Box Filled with Data")</span></span>  
  
17. <span data-ttu-id="fd279-139">Verifique se a coluna de entidade de **código** está mapeada para a coluna **CódigoDoFornecedor** na planilha e a coluna de entidade **CEP** está mapeada para a coluna **CEP** na planilha.</span><span class="sxs-lookup"><span data-stu-id="fd279-139">Ensure that **Code** entity column is mapped to the **SupplierID** column in the worksheet and **Zip Code** entity column is mapped to the **Zip Code** column in the worksheet.</span></span>  
  
18. <span data-ttu-id="fd279-140">Na caixa de diálogo **combinar dados** , clique em **combinar**.</span><span class="sxs-lookup"><span data-stu-id="fd279-140">On the **Combine Data** dialog box, click **Combine**.</span></span>  
  
19. <span data-ttu-id="fd279-141">Confirme se as três linhas de dados foram adicionadas à parte inferior da planilha e devem estar codificadas por cores.</span><span class="sxs-lookup"><span data-stu-id="fd279-141">Confirm that three data rows are added to the bottom of the worksheet and they should be color coded.</span></span>  
  
     <span data-ttu-id="fd279-142">![Excel - Novos elementos após combinação](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - Novos elementos após combinação")</span><span class="sxs-lookup"><span data-stu-id="fd279-142">![Excel - New Elements after Combining](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - New Elements after Combining")</span></span>  
  
20. <span data-ttu-id="fd279-143">Clique em **dados matemáticos** na faixa de faixas para identificar duplicatas.</span><span class="sxs-lookup"><span data-stu-id="fd279-143">Click **Math Data** on the ribbon to identify duplicates.</span></span> <span data-ttu-id="fd279-144">Esse recurso usa a funcionalidade de correspondência do DQS.</span><span class="sxs-lookup"><span data-stu-id="fd279-144">This feature uses the matching functionality of DQS.</span></span>  
  
21. <span data-ttu-id="fd279-145">Na caixa de diálogo **corresponder dados** , selecione **fornecedores** para a **base de dados de conhecimento do DQS**.</span><span class="sxs-lookup"><span data-stu-id="fd279-145">In the **Match Data** dialog box, select **Suppliers** for **DQS Knowledge Base**.</span></span>  
  
     <span data-ttu-id="fd279-146">![Excel - Caixa de diálogo Corresponder Dados](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Caixa de diálogo Corresponder Dados")</span><span class="sxs-lookup"><span data-stu-id="fd279-146">![Excel - Match Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Match Data Dialog Box")</span></span>  
  
22. <span data-ttu-id="fd279-147">Mapeie as colunas da planilha para domínios, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd279-147">Map worksheet columns to domains as shown in the following table.</span></span>  
  
    |<span data-ttu-id="fd279-148">Coluna da planilha</span><span class="sxs-lookup"><span data-stu-id="fd279-148">Worksheet Column</span></span>|<span data-ttu-id="fd279-149">Domínio</span><span class="sxs-lookup"><span data-stu-id="fd279-149">Domain</span></span>|  
    |----------------------|------------|  
    |<span data-ttu-id="fd279-150">Code (você carregou a Supplier ID como o Code da entidade Supplier no MDS)</span><span class="sxs-lookup"><span data-stu-id="fd279-150">Code (you uploaded Supplier ID as the Code for the Supplier entity in MDS)</span></span>|<span data-ttu-id="fd279-151">ID do Fornecedor</span><span class="sxs-lookup"><span data-stu-id="fd279-151">Supplier ID</span></span>|  
    |<span data-ttu-id="fd279-152">Name (você carregou o Supplier Name como o Name da entidade Supplier para o MDS)</span><span class="sxs-lookup"><span data-stu-id="fd279-152">Name (you uploaded Supplier Name as the Name for the Supplier entity to MDS)</span></span>|<span data-ttu-id="fd279-153">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="fd279-153">Supplier Name</span></span>|  
    |<span data-ttu-id="fd279-154">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="fd279-154">ContactEmailAddress</span></span>|<span data-ttu-id="fd279-155">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="fd279-155">ContactEmail</span></span>|  
  
23. <span data-ttu-id="fd279-156">Selecione **pré-requisito** para o mapeamento de coluna de **código** .</span><span class="sxs-lookup"><span data-stu-id="fd279-156">Select **Prerequisite** for the **Code** column mapping.</span></span>  
  
24. <span data-ttu-id="fd279-157">Insira **70%** como o **peso** do **nome do fornecedor** e **30%** como o **peso** do **email de contato** , conforme mostrado na imagem.</span><span class="sxs-lookup"><span data-stu-id="fd279-157">Enter **70%** as the **weight** for **Supplier Name** and **30%** as the **weight** for **Contact Email** as shown in the image.</span></span>  
  
25. <span data-ttu-id="fd279-158">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd279-158">Click **OK**.</span></span>  
  
26. <span data-ttu-id="fd279-159">O processo de correspondência deve identificar uma duplicata para o fornecedor com **código: S1**.</span><span class="sxs-lookup"><span data-stu-id="fd279-159">The matching process should identify one duplicate for the supplier with **Code: S1**.</span></span>  
  
     <span data-ttu-id="fd279-160">![Excel - Resultados de Correspondência](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Resultados de Correspondência")</span><span class="sxs-lookup"><span data-stu-id="fd279-160">![Excel - Matching Results](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Matching Results")</span></span>  
  
27. <span data-ttu-id="fd279-161">Selecione a **linha duplicada (laranja)**, clique com o botão direito do mouse e clique em **excluir** para excluir a linha.</span><span class="sxs-lookup"><span data-stu-id="fd279-161">Select the **duplicate row (orange)**, right-click, and click **Delete** to delete the row.</span></span>  
  
28. <span data-ttu-id="fd279-162">Exclua a coluna **CLUSTER_ID** , pois você não precisa mais dela.</span><span class="sxs-lookup"><span data-stu-id="fd279-162">Delete the **CLUSTER_ID** column since you don't need it anymore.</span></span>  
  
29. <span data-ttu-id="fd279-163">Clique em **publicar** para publicar os outros dois novos registros com os **códigos S66** e **s57** para MDS.</span><span class="sxs-lookup"><span data-stu-id="fd279-163">Click **Publish** to publish the other two new records with **Codes S66** and **S57** to MDS.</span></span>  
  
30. <span data-ttu-id="fd279-164">Na caixa de diálogo **publicar e anotar** , adicione uma **anotação**e clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="fd279-164">In the **Publish and Annotate** dialog box, add an **annotation**, and click **Publish**.</span></span>  
  
31. <span data-ttu-id="fd279-165">Alterne para o **aplicativo Web Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="fd279-165">Switch to the **Master Data Manager Web application**.</span></span>  
  
32. <span data-ttu-id="fd279-166">Na home page, verifique se **fornecedores** está selecionado para o **modelo**e clique em **Gerenciador**.</span><span class="sxs-lookup"><span data-stu-id="fd279-166">On the home page, ensure that **Suppliers** is selected for the **Model**, and click **Explorer**.</span></span> <span data-ttu-id="fd279-167">Se você já tiver o **Gerenciador** aberto, atualize o navegador da Internet.</span><span class="sxs-lookup"><span data-stu-id="fd279-167">If you already have the **Explorer** open, refresh the internet browser.</span></span>  
  
33. <span data-ttu-id="fd279-168">**Classifique** a lista por **código** e procure por registros com **s57** e **S66** como códigos.</span><span class="sxs-lookup"><span data-stu-id="fd279-168">**Sort** the list by **Code** and look for records with **S57** and **S66** as codes.</span></span> <span data-ttu-id="fd279-169">Você também pode usar o botão **Filtrar** na barra de ferramentas para procurar um registro específico na lista.</span><span class="sxs-lookup"><span data-stu-id="fd279-169">You can also use the **Filter** button on the toolbar to search for a specific record in the list.</span></span>  
  
34. <span data-ttu-id="fd279-170">Agora, feche a janela **book1-Microsoft Excel** sem salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="fd279-170">Now, close **Book1 - Microsoft Excel** window without saving the file.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="fd279-171">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="fd279-171">Next Step</span></span>  
 [<span data-ttu-id="fd279-172">Tarefa 5: Criando um atributo baseado em domínio no Excel</span><span class="sxs-lookup"><span data-stu-id="fd279-172">Task 5: Creating a Domain-Based Attribute from Excel</span></span>](../../2014/tutorials/task-5-creating-a-domain-based-attribute-from-excel.md)  
  
  
