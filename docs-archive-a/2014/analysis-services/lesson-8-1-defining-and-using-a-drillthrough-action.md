---
title: Definindo e usando uma ação de detalhamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3765f865-2b93-44be-b290-28e3815d5ecb
author: minewiskan
ms.author: owend
ms.openlocfilehash: ea19a9721d87936bc88b5401c71ee550a47bc1ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680128"
---
# <a name="defining-and-using-a-drillthrough-action"></a><span data-ttu-id="0995a-102">Definindo e usando uma ação de detalhamento</span><span class="sxs-lookup"><span data-stu-id="0995a-102">Defining and Using a Drillthrough Action</span></span>
  <span data-ttu-id="0995a-103">Os dados de fato de dimensionamento em uma dimensão de fatos sem filtrar corretamente os dados que a consulta retorna podem causar lentidão no desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="0995a-103">Dimensioning fact data by a fact dimension without correctly filtering the data that the query returns can cause slow query performance.</span></span> <span data-ttu-id="0995a-104">Para evitar esse problema, defina uma ação de detalhamento que restrinja o número total de linhas que serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="0995a-104">To avoid this, you can define a drillthrough action that restricts the total number of rows that are returned.</span></span> <span data-ttu-id="0995a-105">Esse processo melhorará significativamente o desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="0995a-105">This will significantly improve query performance.</span></span>  
  
 <span data-ttu-id="0995a-106">Nas tarefas deste tópico, você definirá uma ação de detalhamento para retornar informações sobre os detalhes do pedido de vendas para clientes na Internet.</span><span class="sxs-lookup"><span data-stu-id="0995a-106">In the tasks in this topic, you define a drillthrough action to return order detail information for sales to customers over the Internet.</span></span>  
  
## <a name="defining-the-drillthrough-action-properties"></a><span data-ttu-id="0995a-107">Definindo as propriedades da ação de detalhamento</span><span class="sxs-lookup"><span data-stu-id="0995a-107">Defining the Drillthrough Action Properties</span></span>  
  
1.  <span data-ttu-id="0995a-108">No Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , clique na guia **Ações** .</span><span class="sxs-lookup"><span data-stu-id="0995a-108">In Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, click the **Actions** tab.</span></span>  
  
     <span data-ttu-id="0995a-109">A guia **Ações** inclui vários painéis.</span><span class="sxs-lookup"><span data-stu-id="0995a-109">The **Actions** tab includes several panes.</span></span> <span data-ttu-id="0995a-110">No lado esquerdo da guia estão os painéis **Organizador de Ações** e **Ferramentas de Cálculo** .</span><span class="sxs-lookup"><span data-stu-id="0995a-110">On the left side of the tab are the **Action Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="0995a-111">O painel à direita desses dois painéis está o painel **Exibição** , que contém os detalhes da ação selecionada no painel **Organizador de Ações** .</span><span class="sxs-lookup"><span data-stu-id="0995a-111">The pane to the right of these two panes is the **Display** pane, which contains the details of the action that is selected in the **Action Organizer** pane.</span></span>  
  
     <span data-ttu-id="0995a-112">A imagem a seguir mostra a guia **Ações** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="0995a-112">The following image shows the **Actions** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="0995a-113">![Guia Ações do Designer de Cubo](../../2014/tutorials/media/l8-action1.gif "Guia Ações do Designer de Cubo")</span><span class="sxs-lookup"><span data-stu-id="0995a-113">![Actions tab of Cube Designer](../../2014/tutorials/media/l8-action1.gif "Actions tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="0995a-114">Na barra de ferramentas da guia **Ações** , clique no botão **Nova Ação de Detalhamento** .</span><span class="sxs-lookup"><span data-stu-id="0995a-114">On the toolbar of the **Actions** tab, click the **New Drillthrough Action** button.</span></span>  
  
     <span data-ttu-id="0995a-115">Um modelo de ação em branco será exibido na tela.</span><span class="sxs-lookup"><span data-stu-id="0995a-115">A blank action template appears in the display pane.</span></span>  
  
     <span data-ttu-id="0995a-116">![Modelo de ação em branco no painel de exibição](../../2014/tutorials/media/l8-action2.gif "Modelo de ação em branco no painel de exibição")</span><span class="sxs-lookup"><span data-stu-id="0995a-116">![Blank Action template in the display pane](../../2014/tutorials/media/l8-action2.gif "Blank Action template in the display pane")</span></span>  
  
3.  <span data-ttu-id="0995a-117">Na caixa **nome** , altere o nome dessa ação para `Internet Sales Details Drillthrough Action` .</span><span class="sxs-lookup"><span data-stu-id="0995a-117">In the **Name** box, change the name of this action to `Internet Sales Details Drillthrough Action`.</span></span>  
  
4.  <span data-ttu-id="0995a-118">Na lista **Membros do grupo de medidas** , selecione **Vendas pela Internet**.</span><span class="sxs-lookup"><span data-stu-id="0995a-118">In the **Measure group members** list, select **Internet Sales**.</span></span>  
  
5.  <span data-ttu-id="0995a-119">Na caixa **Colunas de Detalhamento** , selecione **Detalhes de Pedidos de Vendas pela Internet** na lista **Dimensões** .</span><span class="sxs-lookup"><span data-stu-id="0995a-119">In the **Drillthrough Columns** box, select **Internet Sales Order Details** in the **Dimensions** list.</span></span>  
  
6.  <span data-ttu-id="0995a-120">Na lista **Retornar Colunas** , marque as caixas de seleção **Descrição do Item** e **Número do Pedido** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0995a-120">In the **Return Columns** list, select the **Item Description** and the **Order Number** check boxes, and then click **OK**.</span></span> <span data-ttu-id="0995a-121">A imagem a seguir mostra como o modelo Ação deve estar sendo exibido neste momento no procedimento.</span><span class="sxs-lookup"><span data-stu-id="0995a-121">The following image shows the Action template as it should appear at this point in this procedure.</span></span>  
  
     <span data-ttu-id="0995a-122">![Caixa Colunas de Detalhamento](../../2014/tutorials/media/l8-action3.gif "Caixa Colunas de Detalhamento")</span><span class="sxs-lookup"><span data-stu-id="0995a-122">![Drillthrough Columns box](../../2014/tutorials/media/l8-action3.gif "Drillthrough Columns box")</span></span>  
  
7.  <span data-ttu-id="0995a-123">Expanda a caixa **Propriedades Adicionais** , como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="0995a-123">Expand the **Additional Properties** box, as shown in the following image.</span></span>  
  
     <span data-ttu-id="0995a-124">![Caixa Propriedades Adicionais](../../2014/tutorials/media/l8-action4.gif "Caixa Propriedades Adicionais")</span><span class="sxs-lookup"><span data-stu-id="0995a-124">![Additional Properties box](../../2014/tutorials/media/l8-action4.gif "Additional Properties box")</span></span>  
  
8.  <span data-ttu-id="0995a-125">Na caixa **máximo de linhas** , digite `10` .</span><span class="sxs-lookup"><span data-stu-id="0995a-125">In the **Maximum Rows** box, type `10`.</span></span>  
  
9. <span data-ttu-id="0995a-126">Na caixa **legenda** , digite `Drillthrough to Order Details...` .</span><span class="sxs-lookup"><span data-stu-id="0995a-126">In the **Caption** box, type `Drillthrough to Order Details...`.</span></span>  
  
     <span data-ttu-id="0995a-127">Essas configurações limitam o número de linhas a serem retornadas e especificam a legenda que será exibida no menu do aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="0995a-127">These settings limit the number of rows returned and specify the caption that appears in the client application menu.</span></span> <span data-ttu-id="0995a-128">A imagem a seguir mostra essas configurações na caixa **Propriedades Adicionais** .</span><span class="sxs-lookup"><span data-stu-id="0995a-128">The following image shows these settings in the **AdditionalProperties** box.</span></span>  
  
     <span data-ttu-id="0995a-129">![Caixa Propriedades Adicionais](../../2014/tutorials/media/l8-action5.gif "Caixa Propriedades Adicionais")</span><span class="sxs-lookup"><span data-stu-id="0995a-129">![Additional Properties box](../../2014/tutorials/media/l8-action5.gif "Additional Properties box")</span></span>  
  
## <a name="using-the-drillthrough-action"></a><span data-ttu-id="0995a-130">Usando a ação de detalhamento</span><span class="sxs-lookup"><span data-stu-id="0995a-130">Using the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="0995a-131">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="0995a-131">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="0995a-132">Quando a implantação for concluída com êxito, clique na guia **Navegador** do Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique no botão **Reconectar** .</span><span class="sxs-lookup"><span data-stu-id="0995a-132">When deployment has successfully completed, click the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="0995a-133">Inicie o Excel.</span><span class="sxs-lookup"><span data-stu-id="0995a-133">Start Excel.</span></span>  
  
4.  <span data-ttu-id="0995a-134">Adicione a medida **Vendas pela Internet/Valor das Vendas** à área Valores.</span><span class="sxs-lookup"><span data-stu-id="0995a-134">Add the **Internet Sales-Sales Amount** measure to the Values area.</span></span>  
  
5.  <span data-ttu-id="0995a-135">Adicione a hierarquia definida pelo usuário **Geografia do Cliente** da pasta **Local** na dimensão **Customer** à área **Filtro de Relatório** .</span><span class="sxs-lookup"><span data-stu-id="0995a-135">Add the **Customer Geography** user-defined hierarchy from the **Location** folder in the **Customer** dimension to the **Report Filter** area.</span></span>  
  
6.  <span data-ttu-id="0995a-136">Na Tabela Dinâmica, em **Geografia do Cliente**, adicione um filtro que seleciona um único cliente.</span><span class="sxs-lookup"><span data-stu-id="0995a-136">On the PivotTable, in **Customer Geography**, add a filter that selects a single customer.</span></span> <span data-ttu-id="0995a-137">Expanda **Todos os clientes**, **Austrália**, **Queensland**, **Brisbane**e **4000**, marque a caixa de seleção **Adam Powell**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0995a-137">Expand **All Customers**, expand **Australia**, expand **Queensland**, expand **Brisbane**, expand **4000**, select the check box for **Adam Powell**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0995a-138">O total de vendas em produtos da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] obtido por Adam Powell será exibido na área de dados.</span><span class="sxs-lookup"><span data-stu-id="0995a-138">The total sales of products by [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] to Adam Powell are displayed in the data area.</span></span>  
  
7.  <span data-ttu-id="0995a-139">Clique com o botão direito do mouse no valor de vendas, aponte para **Ações Adicionais**e clique em **Detalhamento até Detalhes do Pedido**.</span><span class="sxs-lookup"><span data-stu-id="0995a-139">Right-click on the sales amount, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="0995a-140">Os detalhes dos pedidos que foram enviados a Adam Powell são exibidos no **Visualizador de Exemplos de Dados**, como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="0995a-140">The details of the orders that were shipped to Adam Powell are displayed in the **Data Sample Viewer**, as shown in the following image.</span></span> <span data-ttu-id="0995a-141">Entretanto, alguns detalhes adicionais também seriam úteis, como a data do pedido, a data de vencimento e a data de envio.</span><span class="sxs-lookup"><span data-stu-id="0995a-141">However, some additional details would also be useful, such as the order date, due date, and ship date.</span></span> <span data-ttu-id="0995a-142">No próximo procedimento, você adicionará esses detalhes.</span><span class="sxs-lookup"><span data-stu-id="0995a-142">In the next procedure, you will add these additional details.</span></span>  
  
     <span data-ttu-id="0995a-143">![Pedidos enviados para Adam Powell](../../2014/tutorials/media/l8-action6.gif "Pedidos enviados para Adam Powell")</span><span class="sxs-lookup"><span data-stu-id="0995a-143">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action6.gif "Orders shipped to Adam Powell")</span></span>  
  
8.  <span data-ttu-id="0995a-144">Feche o Excel/</span><span class="sxs-lookup"><span data-stu-id="0995a-144">Close Excel/</span></span>  
  
## <a name="modifying-the-drillthrough-action"></a><span data-ttu-id="0995a-145">Modificando a ação de detalhamento</span><span class="sxs-lookup"><span data-stu-id="0995a-145">Modifying the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="0995a-146">Abra o Designer de Dimensão na dimensão **Detalhes do Pedido de Vendas pela Internet** .</span><span class="sxs-lookup"><span data-stu-id="0995a-146">Open Dimension Designer for the **Internet Sales Order Details** dimension.</span></span>  
  
     <span data-ttu-id="0995a-147">Observe que apenas três atributos foram definidos para essa dimensão.</span><span class="sxs-lookup"><span data-stu-id="0995a-147">Notice that only three attributes have been defined for this dimension.</span></span>  
  
2.  <span data-ttu-id="0995a-148">No painel **Exibição da Fonte de Dados** , clique com o botão direito do mouse em uma área aberta e clique em **Mostrar Todas as Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="0995a-148">In the **Data Source View** pane, right-click an open area, and then click **Show All Tables**.</span></span>  
  
3.  <span data-ttu-id="0995a-149">No menu **Formatar** , aponte para **Layout Automático** e clique em **Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="0995a-149">On the **Format** menu, point to **Autolayout** and then click **Diagram**.</span></span>  
  
4.  <span data-ttu-id="0995a-150">Localize a tabela **InternetSales (dbo.FactInternetSales)** clicando com o botão direito do mouse em uma área aberta do painel **Exibição da Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="0995a-150">Locate the **InternetSales (dbo.FactInternetSales)** table by right-clicking in an open area of the **Data Source View** pane.</span></span> <span data-ttu-id="0995a-151">Em seguida, clique em **Localizar Tabela** , em **InternetSales** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0995a-151">Then click **Find Table,** click **InternetSales,** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="0995a-152">Crie novos atributos com base nas seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="0995a-152">Create new attributes based on the following columns:</span></span>  
  
    -   <span data-ttu-id="0995a-153">OrderDateKey</span><span class="sxs-lookup"><span data-stu-id="0995a-153">OrderDateKey</span></span>  
  
    -   <span data-ttu-id="0995a-154">DueDateKey</span><span class="sxs-lookup"><span data-stu-id="0995a-154">DueDateKey</span></span>  
  
    -   <span data-ttu-id="0995a-155">ShipDateKey</span><span class="sxs-lookup"><span data-stu-id="0995a-155">ShipDateKey</span></span>  
  
6.  <span data-ttu-id="0995a-156">Altere a propriedade **nome** do atributo de **chave de data do pedido** para, `Order Date` clique no botão procurar da propriedade **coluna de nome** e, na caixa de diálogo coluna de **nome** , selecione **Data** como a tabela de origem e selecione SimpleDate como a coluna de origem.</span><span class="sxs-lookup"><span data-stu-id="0995a-156">Change the **Name** property for the **Order Date Key** attribute to `Order Date` Then, click the browse button for the **Name Column** property, and in the **Name Column** dialog box, select **Date** as the source table and select SimpleDate as the source column.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="0995a-157">Altere a propriedade **nome** do atributo de **chave de data de vencimento** para `Due Date` e, em seguida, usando o mesmo método que o atributo de **chave de data do pedido** , altere a propriedade de coluna de **nome** desse atributo para **Date. SimpleDate (WCHAR)**.</span><span class="sxs-lookup"><span data-stu-id="0995a-157">Change the **Name** property for the **Due Date Key** attribute to `Due Date`, and then, by using the same method as the **Order Date Key** attribute, change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
8.  <span data-ttu-id="0995a-158">Altere a propriedade **Name** do atributo de **chave de data de envio** para `Ship Date` e altere a propriedade de **coluna de nome** desse atributo para **Date. SimpleDate (WCHAR)**.</span><span class="sxs-lookup"><span data-stu-id="0995a-158">Change the **Name** property for the **Ship Date Key** attribute to `Ship Date`, and then change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
9. <span data-ttu-id="0995a-159">Mude para a guia **Ações** do Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0995a-159">Switch to the **Actions** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
10. <span data-ttu-id="0995a-160">Na lista **Colunas de Detalhamento** , marque as caixas de seleção para adicionar as seguintes colunas à lista **Retornar Colunas** e clique em **OK**:</span><span class="sxs-lookup"><span data-stu-id="0995a-160">In the **Drillthrough Columns** box, select the check boxes to add the following columns to the **Return Columns** list, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="0995a-161">Data do Pedido</span><span class="sxs-lookup"><span data-stu-id="0995a-161">Order Date</span></span>  
  
    -   <span data-ttu-id="0995a-162">Due Date</span><span class="sxs-lookup"><span data-stu-id="0995a-162">Due Date</span></span>  
  
    -   <span data-ttu-id="0995a-163">Ship Date</span><span class="sxs-lookup"><span data-stu-id="0995a-163">Ship Date</span></span>  
  
     <span data-ttu-id="0995a-164">A imagem a seguir mostra essas colunas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="0995a-164">The following image shows these columns selected.</span></span>  
  
     <span data-ttu-id="0995a-165">![Caixa Colunas de Detalhamento](../../2014/tutorials/media/l8-action7.gif "Caixa Colunas de Detalhamento")</span><span class="sxs-lookup"><span data-stu-id="0995a-165">![Drillthrough Columns box](../../2014/tutorials/media/l8-action7.gif "Drillthrough Columns box")</span></span>  
  
## <a name="reviewing-the-modified-drillthrough-action"></a><span data-ttu-id="0995a-166">Revisando a ação de detalhamento modificada</span><span class="sxs-lookup"><span data-stu-id="0995a-166">Reviewing the Modified Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="0995a-167">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="0995a-167">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="0995a-168">Quando a implantação for concluída com êxito, mude para a guia **Navegador** do Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique no botão **Reconectar** .</span><span class="sxs-lookup"><span data-stu-id="0995a-168">When deployment has successfully completed, switch to the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="0995a-169">Inicie o Excel.</span><span class="sxs-lookup"><span data-stu-id="0995a-169">Start Excel.</span></span>  
  
4.  <span data-ttu-id="0995a-170">Recrie a Tabela Dinâmica usando **Vendas pela Internet/Valor das Vendas** na área Valores e **Geografia do Cliente** no Filtro de Relatório.</span><span class="sxs-lookup"><span data-stu-id="0995a-170">Recreate the PivotTable using **Internet Sales-Sales Amount** in the Values area and **Customer Geography** in the Report Filter.</span></span>  
  
     <span data-ttu-id="0995a-171">Adicione um filtro que seleciona de **Todos os Clientes**, **Austrália**, **Queensland**, **Brisbane**, **4000**e **Adam Powell**.</span><span class="sxs-lookup"><span data-stu-id="0995a-171">Add a filter that selects from **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, **Adam Powell**.</span></span>  
  
5.  <span data-ttu-id="0995a-172">Clique na célula de dados **Vendas pela Internet/Valor das Vendas** , aponte para **Ações Adicionais**e clique em **Detalhamento até Detalhes do Pedido**.</span><span class="sxs-lookup"><span data-stu-id="0995a-172">Click the **Internet Sales-Sales Amount** data cell, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="0995a-173">Os detalhes dos pedidos enviados a Adam Powell serão exibidos em uma planilha temporária.</span><span class="sxs-lookup"><span data-stu-id="0995a-173">The details of these orders shipped to Adam Powell are displayed in a temporary worksheet.</span></span> <span data-ttu-id="0995a-174">Isso inclui descrição do item, número do pedido, data do pedido, data de vencimento e data de envio, como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="0995a-174">This includes item description, order number, order date, due date, and ship date information, as shown in the following image.</span></span>  
  
     <span data-ttu-id="0995a-175">![Pedidos enviados para Adam Powell](../../2014/tutorials/media/l8-action8.gif "Pedidos enviados para Adam Powell")</span><span class="sxs-lookup"><span data-stu-id="0995a-175">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action8.gif "Orders shipped to Adam Powell")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0995a-176">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="0995a-176">Next Lesson</span></span>  
 [<span data-ttu-id="0995a-177">Lição 9: Como definir perspectivas e traduções</span><span class="sxs-lookup"><span data-stu-id="0995a-177">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="0995a-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0995a-178">See Also</span></span>  
 <span data-ttu-id="0995a-179">[Ações &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0995a-179">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0995a-180">[Ações em modelos multidimensionais](multidimensional-models/actions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="0995a-180">[Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="0995a-181">[Relações de dimensão](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="0995a-181">[Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 <span data-ttu-id="0995a-182">[Definindo uma relação de fatos](lesson-5-2-defining-a-fact-relationship.md) </span><span class="sxs-lookup"><span data-stu-id="0995a-182">[Defining a Fact Relationship](lesson-5-2-defining-a-fact-relationship.md) </span></span>  
 [<span data-ttu-id="0995a-183">Definir uma relação de fato e propriedades de relação de fato</span><span class="sxs-lookup"><span data-stu-id="0995a-183">Define a Fact Relationship and Fact Relationship Properties</span></span>](multidimensional-models/define-a-fact-relationship-and-fact-relationship-properties.md)  
  
  
