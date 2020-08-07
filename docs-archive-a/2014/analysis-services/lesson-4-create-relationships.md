---
title: 'Lição 5: criar relações | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: abac1a00-f827-4c3e-a473-6db5c8a3a66f
author: minewiskan
ms.author: owend
ms.openlocfilehash: f622f88d4d400fedf24e99059eda94882b1bcc3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681891"
---
# <a name="lesson-5-create-relationships"></a><span data-ttu-id="2bbfd-102">Lição 5: Criar Relações</span><span class="sxs-lookup"><span data-stu-id="2bbfd-102">Lesson 5: Create Relationships</span></span>
  <span data-ttu-id="2bbfd-103">Nesta lição, você aprenderá a verificar as relações que foram criadas automaticamente quando os dados foram importados e adicionará novas relações entre tabelas diferentes.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-103">In this lesson, you will verify the relationships that were created automatically when you imported data and add new relationships between different tables.</span></span> <span data-ttu-id="2bbfd-104">Uma relação é uma conexão criada entre duas tabelas que estabelece como os dados dessas tabelas devem ser correlacionados.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-104">A relationship is a connection between two tables that establishes how the data in those tables should be correlated.</span></span> <span data-ttu-id="2bbfd-105">Por exemplo, as tabelas Product e Product Subcategory têm uma relação baseada no fato de que cada produto pertence a uma subcategoria.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-105">For example, the Product table and the Product Subcategory table have a relationship based on the fact that each product belongs to a subcategory.</span></span> <span data-ttu-id="2bbfd-106">Para obter mais informações, consulte [Relações &#40;SSAS Tabular&#41;](tabular-models/relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="2bbfd-106">To learn more, see [Relationships &#40;SSAS Tabular&#41;](tabular-models/relationships-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="2bbfd-107">Tempo estimado para conclusão desta lição: **10 minutos**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-107">Estimated time to complete this lesson: **10 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2bbfd-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2bbfd-108">Prerequisites</span></span>  
 <span data-ttu-id="2bbfd-109">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="2bbfd-110">Antes de executar as tarefas desta lição, você deverá ter concluído a lição anterior: [Lição 3: Renomear colunas](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="2bbfd-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
## <a name="review-existing-relationships-and-add-new-relationships"></a><span data-ttu-id="2bbfd-111">Revisar relações existentes e adicionar novas relações</span><span class="sxs-lookup"><span data-stu-id="2bbfd-111">Review Existing Relationships and Add New Relationships</span></span>  
 <span data-ttu-id="2bbfd-112">Ao importar dados usando o Assistente de Importação de Tabela, você importou sete tabelas do banco de dados AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-112">When you imported data by using the Table Import Wizard, you imported seven tables from the AdventureWorksDW database.</span></span> <span data-ttu-id="2bbfd-113">Geralmente, se você importar dados de uma fonte relacional, os banco de dados existentes são importados automaticamente junto com os dados.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-113">Generally, if you import data from a relational source, existing relationships are automatically imported together with the data.</span></span> <span data-ttu-id="2bbfd-114">No entanto, antes de prosseguir com a criação de seu modelo, você deve verificar se essas relações entre tabelas foram criadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-114">However, before you proceed with authoring your model you should verify those relationships between tables were created properly.</span></span> <span data-ttu-id="2bbfd-115">Para este tutorial, você adicionará também três novas relações.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-115">For this tutorial, you will also add three new relationships.</span></span>  
  
#### <a name="to-review-existing-relationships"></a><span data-ttu-id="2bbfd-116">Para examinar relações existentes</span><span class="sxs-lookup"><span data-stu-id="2bbfd-116">To review existing relationships</span></span>  
  
1.  <span data-ttu-id="2bbfd-117">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Modelo** , aponte para **Exibição de Modelo**e clique em **Exibição de Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
     <span data-ttu-id="2bbfd-118">Agora, o designer de modelos aparece em Exibição de Diagrama, um formato gráfico que exibe todas as tabelas que você importou com linhas entre elas.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-118">The model designer now appears in Diagram View, a graphical format displaying all of the tables you imported with lines between them.</span></span> <span data-ttu-id="2bbfd-119">As linhas entre tabelas indicam as relações que foram criadas automaticamente quando você importar os dados.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-119">The lines between tables indicate the relationships that were automatically created when you imported the data.</span></span>  
  
     <span data-ttu-id="2bbfd-120">Use os controles de minimapa no canto superior direito do designer de modelos para ajustar a exibição de modo que ela inclua o máximo de tabelas possível.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-120">Use the minimap controls in the upper-right corner of the model designer to adjust the view to include as many of the tables as possible.</span></span> <span data-ttu-id="2bbfd-121">Você também pode clicar e arrastar tabelas para locais diferentes, colocando-as mais próximas umas das outras ou colocando-as em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-121">You can also click and drag tables to different locations, bringing tables closer together, or putting them in a particular order.</span></span> <span data-ttu-id="2bbfd-122">A movimentação de tabelas não afeta as relações já existentes entre elas.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-122">Moving tables does not affect the relationships already between the tables.</span></span> <span data-ttu-id="2bbfd-123">Para exibir todas as colunas em uma tabela específica, clique e arraste em uma borda de tabela expandi-la ou reduzi-la.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-123">To view all of the columns in a particular table, click and drag on a table edge to expand or make it smaller.</span></span>  
  
2.  <span data-ttu-id="2bbfd-124">Clique na linha sólida entre as tabelas **Cliente** e **Geografia** .</span><span class="sxs-lookup"><span data-stu-id="2bbfd-124">Click on the solid line between the **Customer** table and the **Geography** table.</span></span> <span data-ttu-id="2bbfd-125">A linha sólida entre essas duas tabelas mostra que essa relação está ativa, ou seja, ela é usada por padrão durante o cálculo das fórmulas DAX.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-125">The solid line between these two tables show this relationship is active, that is, it is used by default when calculating DAX formulas.</span></span>  
  
     <span data-ttu-id="2bbfd-126">Observe que, agora, a coluna **ID da Geografia** da tabela **Cliente** e a coluna **ID da Geografia** da tabela **Geografia** são exibidas cada uma dentro de uma caixa.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-126">Notice the **Geography Id** column in the **Customer** table and the **Geography Id** column in the **Geography** table now both each appear within a box.</span></span> <span data-ttu-id="2bbfd-127">Isso mostra que essas são as colunas usadas na relação.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-127">This shows these are the columns used in the relationship.</span></span> <span data-ttu-id="2bbfd-128">As propriedades da relação agora também aparecem na janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="2bbfd-128">The relationship's properties now also appear in the **Properties** window.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="2bbfd-129">Além de usar o designer de modelos na exibição de diagrama, você também pode usar a caixa de diálogo **gerenciar relações** para mostrar as relações entre todas as tabelas em um formato de tabela.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-129">In addition to using the model designer in diagram view, you can also use the **Manage Relationships** dialog box to show the relationships between all tables in a table format.</span></span> <span data-ttu-id="2bbfd-130">Clique no menu **Tabela** e clique em **Gerenciar Relações**.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-130">Click on the **Table** menu, and then click **Manage Relationships**.</span></span> <span data-ttu-id="2bbfd-131">A caixa de diálogo **Gerenciar Relações** mostra as relações que foram criadas automaticamente quando os dados foram importados.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-131">The **Manage Relationships** dialog box shows the relationships that were automatically created when you imported data.</span></span>  
  
3.  <span data-ttu-id="2bbfd-132">Use o designer de modelos na exibição de diagrama ou a caixa de diálogo **Gerenciar Relações** para verificar se as seguintes relações foram criadas quando cada uma das tabelas foi importada do banco de dados AdventureWorksDW:</span><span class="sxs-lookup"><span data-stu-id="2bbfd-132">Use the model designer in diagram view, or the **Manage Relationships** dialog box, to verify the following relationships were created when each of the tables were imported from the AdventureWorksDW database:</span></span>  
  
    |<span data-ttu-id="2bbfd-133">Ativo</span><span class="sxs-lookup"><span data-stu-id="2bbfd-133">Active</span></span>|<span data-ttu-id="2bbfd-134">Tabela</span><span class="sxs-lookup"><span data-stu-id="2bbfd-134">Table</span></span>|<span data-ttu-id="2bbfd-135">Tabela de Pesquisa Relacionada</span><span class="sxs-lookup"><span data-stu-id="2bbfd-135">Related Lookup Table</span></span>|  
    |------------|-----------|--------------------------|  
    |<span data-ttu-id="2bbfd-136">Sim</span><span class="sxs-lookup"><span data-stu-id="2bbfd-136">Yes</span></span>|<span data-ttu-id="2bbfd-137">**Customer [Geography Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-137">**Customer [Geography Id]**</span></span>|<span data-ttu-id="2bbfd-138">**Geography [Geography Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-138">**Geography [Geography Id]**</span></span>|  
    |<span data-ttu-id="2bbfd-139">Sim</span><span class="sxs-lookup"><span data-stu-id="2bbfd-139">Yes</span></span>|<span data-ttu-id="2bbfd-140">**Product [Product Subcategory Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-140">**Product [Product Subcategory Id]**</span></span>|<span data-ttu-id="2bbfd-141">**Product Subcategory [Product Subcategory Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-141">**Product Subcategory [Product Subcategory Id]**</span></span>|  
    |<span data-ttu-id="2bbfd-142">Sim</span><span class="sxs-lookup"><span data-stu-id="2bbfd-142">Yes</span></span>|<span data-ttu-id="2bbfd-143">**Product Subcategory [Product Category Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-143">**Product Subcategory [Product Category Id]**</span></span>|<span data-ttu-id="2bbfd-144">**Product Category [Product Category Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-144">**Product Category [Product Category Id]**</span></span>|  
    |<span data-ttu-id="2bbfd-145">Sim</span><span class="sxs-lookup"><span data-stu-id="2bbfd-145">Yes</span></span>|<span data-ttu-id="2bbfd-146">**Internet Sales [Customer Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-146">**Internet Sales [Customer Id]**</span></span>|<span data-ttu-id="2bbfd-147">**Customer [Customer Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-147">**Customer [Customer Id]**</span></span>|  
    |<span data-ttu-id="2bbfd-148">Sim</span><span class="sxs-lookup"><span data-stu-id="2bbfd-148">Yes</span></span>|<span data-ttu-id="2bbfd-149">**Internet Sales [Product Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-149">**Internet Sales [Product Id]**</span></span>|<span data-ttu-id="2bbfd-150">**Product [Product Id]**</span><span class="sxs-lookup"><span data-stu-id="2bbfd-150">**Product [Product Id]**</span></span>|  
  
 <span data-ttu-id="2bbfd-151">Se qualquer uma das relações na tabela acima estiver ausente, verifique se o modelo inclui as tabelas a seguir: Customer, Date, Geography, Product, Product Category, Product Subcategory e Internet Sales.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-151">If any of the relationships in the table above are missing, verify that your model includes the following tables: Customer, Date, Geography, Product, Product Category, Product Subcategory, and Internet Sales.</span></span> <span data-ttu-id="2bbfd-152">Se as tabelas da mesma conexão de fonte de dados forem importadas em momentos distintos, eventuais relações entre essas tabelas não serão criadas e deverão ser criadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-152">If tables from the same data source connection are imported at separate times, any relationships between those tables will not be created and must be created manually.</span></span>  
  
 <span data-ttu-id="2bbfd-153">Em alguns casos, talvez seja necessário criar relações adicionais entre tabelas no modelo para dar suporte a determinadas lógicas de negócios.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-153">In some cases, you may need to create additional relationships between tables in your model to support certain business logic.</span></span> <span data-ttu-id="2bbfd-154">Para este tutorial, você precisa criar três relações adicionais entre as tabelas Internet Sales e Date.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-154">For this tutorial, you need to create three additional relationships between the Internet Sales table and the Date table.</span></span>  
  
#### <a name="to-add-new-relationships-between-tables"></a><span data-ttu-id="2bbfd-155">Para adicionar novas relações entre tabelas</span><span class="sxs-lookup"><span data-stu-id="2bbfd-155">To add new relationships between tables</span></span>  
  
1.  <span data-ttu-id="2bbfd-156">No designer de modelos, na tabela **Vendas pela Internet** , clique e mantenha o botão do mouse pressionado na coluna **Data do Pedido** , arraste o cursor até a coluna **Data** da tabela **Data** e solte o botão.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-156">In the model designer, in the **Internet Sales** table, click and hold on the **Order Date** column, then drag the cursor to the **Date** column in the **Date** table, and then release.</span></span>  
  
     <span data-ttu-id="2bbfd-157">Uma linha sólida aparece, indicando que você criou uma relação ativa entre a coluna **Data do Pedido** da tabela **Vendas pela Internet** e a coluna **Data** da tabela **Data** .</span><span class="sxs-lookup"><span data-stu-id="2bbfd-157">A solid line appears showing you have created an active relationship between the **Order Date** column in the **Internet Sales** table and the **Date** column in the **Date** table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2bbfd-158">Ao criar relações, a ordem entre a tabela primária e a tabela de pesquisa relacionada é colocada automaticamente na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-158">When creating relationships, the order between the primary table and the related lookup table is automatically put in the correct order.</span></span>  
  
2.  <span data-ttu-id="2bbfd-159">No designer de modelos, na tabela **Vendas pela Internet** , clique e mantenha o botão do mouse pressionado na coluna **Data de Conclusão** , arraste o cursor até a coluna **Data** na tabela **Data** e solte o botão.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-159">In the **Internet Sales** table, click and hold on the **Due Date** column, then drag the cursor to the **Date** column in the **Date** table, and then release.</span></span>  
  
     <span data-ttu-id="2bbfd-160">Uma linha pontilhada aparece, indicando que você criou uma relação inativa entre a coluna **Data de Conclusão** na tabela **Vendas pela Internet** e a coluna **Data** na tabela **Data** .</span><span class="sxs-lookup"><span data-stu-id="2bbfd-160">A dotted line appears showing you have created an inactive relationship between the **Due Date** column in the **Internet Sales** table and the **Date** column in the **Date** table.</span></span> <span data-ttu-id="2bbfd-161">Você pode ter várias relações entre tabelas, mas somente uma relação pode estar ativa por vez.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-161">You can have multiple relationships between tables, but only one relationship can be active at a time.</span></span>  
  
3.  <span data-ttu-id="2bbfd-162">Por fim, crie mais uma relação; na tabela **Vendas pela Internet** , clique e mantenha o botão do mouse pressionado na coluna **Data de Remessa** , arraste o cursor até a coluna **Data** na tabela **Data** e solte o botão.</span><span class="sxs-lookup"><span data-stu-id="2bbfd-162">Finally, create one more relationship; in the **Internet Sales** table, click and hold on the **Ship Date** column, then drag the cursor to the **Date** column in the **Date** table, and then release.</span></span>  
  
     <span data-ttu-id="2bbfd-163">Uma linha pontilhada aparece, indicando que você criou uma relação inativa entre a coluna **Data de Remessa** na tabela **Vendas pela Internet** e a coluna **Data** na tabela **Data** .</span><span class="sxs-lookup"><span data-stu-id="2bbfd-163">A dotted line appears showing you have created an inactive relationship between the **Ship Date** column in the **Internet Sales** table and the **Date** column in the **Date** table.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="2bbfd-164">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2bbfd-164">Next Step</span></span>  
 <span data-ttu-id="2bbfd-165">Para continuar esta lição, vá para a próxima lição: [Lição 6: Criar colunas calculadas](lesson-5-create-calculated-columns.md).</span><span class="sxs-lookup"><span data-stu-id="2bbfd-165">To continue this lesson, go to the next lesson: [Lesson 6: Create Calculated Columns](lesson-5-create-calculated-columns.md).</span></span>  
  
  