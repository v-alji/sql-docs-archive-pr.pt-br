---
title: Classificando membros de atributo com base em um atributo secundário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 67dacf68-9ab7-4524-8698-844d0f6e6c6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: b90888c331a1ae1f8dd886e88d5c84afebd99cf5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685957"
---
# <a name="sorting-attribute-members-based-on-a-secondary-attribute"></a><span data-ttu-id="0aa83-102">Classificando membros de atributo com base em um atributo secundário</span><span class="sxs-lookup"><span data-stu-id="0aa83-102">Sorting Attribute Members Based on a Secondary Attribute</span></span>
  <span data-ttu-id="0aa83-103">Na Lição 3, você aprendeu a classificar membros de atributo com base no nome ou valor de chave deles.</span><span class="sxs-lookup"><span data-stu-id="0aa83-103">In Lesson 3, you learned how to sort attribute members based on either their name or key value.</span></span> <span data-ttu-id="0aa83-104">Aprendeu também a usar uma chave de membro composta para afetar os membros de atributo e a ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="0aa83-104">You also learned how to use a composite member key to affect attribute members and sort order.</span></span> <span data-ttu-id="0aa83-105">Para obter mais informações, consulte [Modificando a dimensão de data](lesson-3-4-modifying-the-date-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="0aa83-105">For more information, see [Modifying the Date Dimension](lesson-3-4-modifying-the-date-dimension.md).</span></span> <span data-ttu-id="0aa83-106">No entanto, se nem o nome e nem a chave do atributo primário fornecerem a ordem de classificação desejada, você poderá usar um atributo secundário para obter a ordem desejada.</span><span class="sxs-lookup"><span data-stu-id="0aa83-106">However, if neither the name nor the key of the attribute provide the sort order that you want, you can use a secondary attribute to achieve the desired sort order.</span></span> <span data-ttu-id="0aa83-107">Com a definição de uma relação entre os atributos, você pode usar o segundo atributo para classificar os membros do primeiro atributo.</span><span class="sxs-lookup"><span data-stu-id="0aa83-107">By defining a relationship between the attributes, you can use the second attribute to sort the members of the first attribute.</span></span>  
  
 <span data-ttu-id="0aa83-108">As relações de atributos definem as relações ou dependências entre atributos.</span><span class="sxs-lookup"><span data-stu-id="0aa83-108">Attribute relationships define the relationships or dependencies between attributes.</span></span> <span data-ttu-id="0aa83-109">Em uma dimensão com base em apenas uma tabela relacional, todos os atributos são geralmente relacionados uns aos outros através do atributo de chave.</span><span class="sxs-lookup"><span data-stu-id="0aa83-109">In a dimension that is based on a single relational table, all attributes are typically related to each other through the key attribute.</span></span> <span data-ttu-id="0aa83-110">Isso acontece porque todos os atributos de uma dimensão fornecem informações sobre os membros vinculados pelo atributo de chave da dimensão aos fatos de uma tabela de fatos para cada grupo de medidas relacionado.</span><span class="sxs-lookup"><span data-stu-id="0aa83-110">This is because all the attributes for a dimension provide information about the members linked by the key attribute of the dimension to the facts in the fact table for each related measure group.</span></span> <span data-ttu-id="0aa83-111">Em uma dimensão com base em várias tabelas relacionais, os atributos são geralmente vinculados com base na chave de junção entre as tabelas.</span><span class="sxs-lookup"><span data-stu-id="0aa83-111">In a dimension that is based on multiple tables, attributes are typically linked based on the join key between the tables.</span></span> <span data-ttu-id="0aa83-112">Se os dados subjacentes derem suporte, os atributos relacionados poderão ser usados para especificar uma ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="0aa83-112">If the underlying data supports it, related attributes can be used to specify a sort order.</span></span> <span data-ttu-id="0aa83-113">Por exemplo, você pode criar um novo atributo que forneça a lógica de classificação para um atributo relacionado.</span><span class="sxs-lookup"><span data-stu-id="0aa83-113">For example, you might create a new attribute that provides the sort logic for a related attribute.</span></span>  
  
 <span data-ttu-id="0aa83-114">O Designer de Dimensão permite que você defina relações adicionais entre atributos ou altere as relações padrão para aumentar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="0aa83-114">Dimension Designer lets you define additional relationships between attributes or change the default relationships to increase performance.</span></span> <span data-ttu-id="0aa83-115">A principal restrição ao criar uma relação de atributo é certificar-se de que o atributo referenciado não possui mais que um valor para qualquer membro no atributo ao qual ele está relacionado.</span><span class="sxs-lookup"><span data-stu-id="0aa83-115">The main constraint when you create an attribute relationship is to make sure that the attribute referred to has no more than one value for any member in the attribute to which it is related.</span></span> <span data-ttu-id="0aa83-116">Ao definir uma relação entre dois atributos, você pode defini-la como rígida ou flexível dependendo se as relações entre os membros mudarem com o tempo.</span><span class="sxs-lookup"><span data-stu-id="0aa83-116">When you define a relationship between two attributes, you can define the relationship as rigid or flexible, based on whether the relationships between members will change over time.</span></span> <span data-ttu-id="0aa83-117">Por exemplo, um funcionário pode mudar para uma região de vendas diferente, mas uma cidade não mudará para um estado diferente.</span><span class="sxs-lookup"><span data-stu-id="0aa83-117">For example, an employee might move to a different sales region, but a city will not move to a different state.</span></span> <span data-ttu-id="0aa83-118">Se uma relação for definida como rígida, as agregações do atributo não serão recalculadas toda vez que a dimensão for processada de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="0aa83-118">If a relationship is defined as rigid, attribute aggregations are not recalculated every time the dimension is incrementally processed.</span></span> <span data-ttu-id="0aa83-119">Porém, se a relação entre membros mudar, a dimensão deve ser processada completamente.</span><span class="sxs-lookup"><span data-stu-id="0aa83-119">However, if the relationship between members does change, the dimension must be fully processed.</span></span> <span data-ttu-id="0aa83-120">Para obter mais informações, consulte [Relações de atributo](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md), [Definir relações de atributo](multidimensional-models/attribute-relationships-define.md), [Configurar propriedades de relação de atributo](multidimensional-models/attribute-relationships-configure-attribute-properties.md)e [Especificando relações de atributo entre atributos em uma hierarquia definida pelo usuário](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="0aa83-120">For more information, see [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md), [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md), [Configure Attribute Relationship Properties](multidimensional-models/attribute-relationships-configure-attribute-properties.md), and [Specifying Attribute Relationships Between Attributes in a User-Defined Hierarchy](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md).</span></span>  
  
 <span data-ttu-id="0aa83-121">Nas tarefas deste tópico, você definirá um novo atributo na dimensão **Data** com base em uma coluna existente na tabela de dimensão subjacente.</span><span class="sxs-lookup"><span data-stu-id="0aa83-121">In the tasks in this topic, you will define a new attribute in the **Date** dimension based on an existing column in the underlying dimension table.</span></span> <span data-ttu-id="0aa83-122">Você usará este novo atributo para classificar os membros mês do calendário cronologicamente, em vez de alfabeticamente.</span><span class="sxs-lookup"><span data-stu-id="0aa83-122">You will use this new attribute to sort calendar month members chronologically instead of alphabetically.</span></span> <span data-ttu-id="0aa83-123">Você também definirá um novo atributo na dimensão **Cliente** com base no cálculo nomeado que você usará para classificar os membros de atributo **Distância do Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-123">You will also define a new attribute in the **Customer** dimension based on the named calculation that you will use to sort the **Commute Distance** attribute members.</span></span> <span data-ttu-id="0aa83-124">Nas tarefas do próximo tópico, você aprenderá a usar relações de atributo para aumentar o desempenho de consulta.</span><span class="sxs-lookup"><span data-stu-id="0aa83-124">In the tasks in the next topic, you will learn to use attribute relationships to increase query performance.</span></span>  
  
## <a name="defining-an-attribute-relationship-and-sort-order-in-the-date-dimension"></a><span data-ttu-id="0aa83-125">Definindo uma relação de atributo e uma ordem de classificação na dimensão Data</span><span class="sxs-lookup"><span data-stu-id="0aa83-125">Defining an Attribute Relationship and Sort Order in the Date Dimension</span></span>  
  
1.  <span data-ttu-id="0aa83-126">Abra o Designer de Dimensão na dimensão **Data** e examine a propriedade **OrderBy** do atributo **Nome do Mês** na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="0aa83-126">Open Dimension Designer for the **Date** dimension, and then review the **OrderBy** property for the **Month Name** attribute in the Properties window.</span></span>  
  
     <span data-ttu-id="0aa83-127">Observe que os membros do atributo **Nome do Mês** são ordenados pelos seus valores de chave.</span><span class="sxs-lookup"><span data-stu-id="0aa83-127">Notice that the **Month Name** attribute members are ordered by their key values.</span></span>  
  
2.  <span data-ttu-id="0aa83-128">Mude para a guia **Navegador** , verifique se **Data do Calendário** está selecionada na lista **Hierarquia** e expanda os níveis da hierarquia definida pelo usuário para examinar a ordem de classificação dos meses do calendário.</span><span class="sxs-lookup"><span data-stu-id="0aa83-128">Switch to the **Browser** tab, verify that **Calendar Date** is selected in the **Hierarchy** list, and then expand the levels in the user-defined hierarchy to review the sort order for the calendar months.</span></span>  
  
     <span data-ttu-id="0aa83-129">Observe que os membros da hierarquia de atributo são classificados com base nos valores ASCII das chaves de membros deles, que são mês e ano.</span><span class="sxs-lookup"><span data-stu-id="0aa83-129">Notice that the members of the attribute hierarchy are sorted based on the ASCII values of their member keys, which are month and year.</span></span> <span data-ttu-id="0aa83-130">Nesse caso, classificar pelo nome ou pela chave do atributo não classifica os meses do calendário cronologicamente.</span><span class="sxs-lookup"><span data-stu-id="0aa83-130">In this case, sorting by the attribute name or key does not sort calendar months chronologically.</span></span> <span data-ttu-id="0aa83-131">Para resolver isso, você classificará os membros da hierarquia de atributo com base em um novo atributo, o atributo **MonthNumberOfYear** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-131">To solve this, you will sort the members of the attribute hierarchy based on a new attribute, the **MonthNumberOfYear** attribute.</span></span> <span data-ttu-id="0aa83-132">Você criará este atributo com base em uma coluna que existe convenientemente na tabela da dimensão **Data** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-132">You will create this attribute based on a column that conveniently exists in the **Date** dimension table.</span></span>  
  
3.  <span data-ttu-id="0aa83-133">Mude para a guia **Estrutura da Dimensão** da dimensão Data, clique com o botão direito do mouse em **MonthNumberOfYear** no painel **Exibição da Fonte de Dados** e clique em **Novo Atributo da Coluna**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-133">Switch to the **Dimension Structure** tab for the Date dimension, right-click **MonthNumberOfYear** in the **Data Source View** pane, and then click **New Attribute from Column**.</span></span>  
  
4.  <span data-ttu-id="0aa83-134">No painel **Atributos** , selecione **Número do Mês do Ano**e defina a propriedade **AttributeHierarchyEnabled** como **False** na janela Propriedades, a propriedade **AttributeHierarchyOptimizedState** como **NotOptimized**e a propriedade **AttributeHierarchyOrdered** como **False**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-134">In the **Attributes** pane, select **Month Number Of Year**, and then set the **AttributeHierarchyEnabled** property to **False** in the Properties window, set the **AttributeHierarchyOptimizedState** property to **NotOptimized**, and set the **AttributeHierarchyOrdered** property to **False**.</span></span>  
  
     <span data-ttu-id="0aa83-135">Essas configurações ocultarão o atributo dos usuários e melhorarão o tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="0aa83-135">These settings will hide the attribute from users and will improve processing time.</span></span> <span data-ttu-id="0aa83-136">Esse atributo não será usado para navegação.</span><span class="sxs-lookup"><span data-stu-id="0aa83-136">This attribute will not be used for browsing.</span></span> <span data-ttu-id="0aa83-137">Ele será usado apenas para classificar os membros de outro atributo.</span><span class="sxs-lookup"><span data-stu-id="0aa83-137">It will only be used for ordering the members of another attribute.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0aa83-138">Classificar as propriedades alfabeticamente na janela Propriedades simplificará esta tarefa, pois as três propriedades serão classificadas subjacentes umas às outras.</span><span class="sxs-lookup"><span data-stu-id="0aa83-138">Sorting properties in the Properties window alphabetically will simplify this task as these three properties will be sorted adjacent to each other.</span></span>  
  
5.  <span data-ttu-id="0aa83-139">Clique na guia **Relações de Atributo** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-139">Click the **Attribute Relationships** tab.</span></span>  
  
     <span data-ttu-id="0aa83-140">Observe que todos os atributos na dimensão **Data** estão relacionados diretamente ao atributo **Data** , que é uma chave de membro que relaciona os membros da dimensão aos fatos nos grupos de medidas relacionados.</span><span class="sxs-lookup"><span data-stu-id="0aa83-140">Notice that all the attributes in the **Date** dimension are related directly to the **Date** attribute, which is the member key that relates the dimension members to the facts in the related measure groups.</span></span> <span data-ttu-id="0aa83-141">Não há nenhuma relação definida entre os atributos **Nome do Mês** e **Número do Mês do Ano** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-141">There is no relationship defined between the **Month Name** attribute and the **Month Number Of Year** attribute.</span></span>  
  
6.  <span data-ttu-id="0aa83-142">No diagrama, clique com o botão direito do mouse no atributo **Nome do Mês** e selecione **Nova Relação de Atributo**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-142">In the diagram, right-click the **Month Name** attribute and then select **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="0aa83-143">Na caixa de diálogo **Criar Relação de Atributo** , o **Atributo de Origem** é **Nome do Mês**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-143">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Month Name**.</span></span> <span data-ttu-id="0aa83-144">Defina o **Atributo Relacionado** como **Número do Mês do Ano**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-144">Set the **Related Attribute** to **Month Number Of Year**.</span></span>  
  
8.  <span data-ttu-id="0aa83-145">Na lista **Tipo de relação** , defina o tipo de relação como **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-145">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="0aa83-146">As relações entre os membros dos atributos **Nome do Mês** e **Número do Mês do Ano** não mudarão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="0aa83-146">The relationships between the members of the **Month Name** attribute and the **Month Number Of Year** attribute will not change over time.</span></span> <span data-ttu-id="0aa83-147">Como resultado, o Analysis Services não descartará agregações para essa relação durante o processamento incremental.</span><span class="sxs-lookup"><span data-stu-id="0aa83-147">As a result, Analysis Services will not drop aggregations for this relationship during incremental processing.</span></span> <span data-ttu-id="0aa83-148">Se ocorrer uma mudança, um erro de processamento ocorrerá durante o processamento incremental e será necessário fazer um processamento completo da dimensão.</span><span class="sxs-lookup"><span data-stu-id="0aa83-148">If a change does occur, a processing error will occur during incremental processing and you will need to perform a full process of the dimension.</span></span> <span data-ttu-id="0aa83-149">Agora, você está pronto para definir a ordem de classificação dos membros de **Nome do Mês**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-149">You are now ready to set the sort order for the members of **Month Name**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="0aa83-150">Clique na guia **Estrutura da Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-150">Click the **Dimension Structure** tab.</span></span>  
  
11. <span data-ttu-id="0aa83-151">Selecione **Nome do Mês** no painel **Atributos** e altere o valor da propriedade **OrderBy** na janela Propriedades para **AttributeKey** e o valor da propriedade **OrderByAttribute** para **Número do Mês do Ano**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-151">Select **Month Name** in the **Attributes** pane, and then change the value of the **OrderBy** property in the Properties window to **AttributeKey** and change the value of the **OrderByAttribute** property to **Month Number Of Year**.</span></span>  
  
12. <span data-ttu-id="0aa83-152">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-152">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
13. <span data-ttu-id="0aa83-153">Quando a implantação for concluída com êxito, mude para a guia **Navegador** da dimensão Data, clique em **Reconectar**e procure as hierarquias de usuário **Data do Calendário** e **Data Fiscal** para verificar se os meses agora estão classificados em ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="0aa83-153">When deployment has successfully completed, switch to the **Browser** tab for the Date dimension, click **Reconnect**, and then browse the **Calendar Date** and **Fiscal Date** user hierarchies to verify that months now sort in chronological order.</span></span>  
  
     <span data-ttu-id="0aa83-154">Observe que os meses agora estão classificados em ordem cronológica, como mostra a imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="0aa83-154">Notice that the months are now sorted in chronological order, as shown in the following image.</span></span>  
  
     <span data-ttu-id="0aa83-155">![Hierarquia modificada pelo usuário em ordem cronológica](../../2014/tutorials/media/l4-memberproperties-3.gif "Hierarquia modificada pelo usuário em ordem cronológica")</span><span class="sxs-lookup"><span data-stu-id="0aa83-155">![Modified user hierarchy in chronological order](../../2014/tutorials/media/l4-memberproperties-3.gif "Modified user hierarchy in chronological order")</span></span>  
  
## <a name="defining-attribute-relationships-and-sort-order-in-the-customer-dimension"></a><span data-ttu-id="0aa83-156">Definindo relações de atributo e ordem de classificação na dimensão Cliente</span><span class="sxs-lookup"><span data-stu-id="0aa83-156">Defining Attribute Relationships and Sort Order in the Customer Dimension</span></span>  
  
1.  <span data-ttu-id="0aa83-157">Mude para a guia **Navegador** no Designer de Dimensão da dimensão Cliente e procure os membros da hierarquia de atributo **Distância do Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-157">Switch to the **Browser** tab in Dimension Designer for the Customer dimension, and then browse the members of the **Commute Distance** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="0aa83-158">Observe que os membros dessa hierarquia de atributo são classificados com base nos valores ASCII da chave de membro.</span><span class="sxs-lookup"><span data-stu-id="0aa83-158">Notice that the members of this attribute hierarchy are sorted based on the ASCII values of the member key.</span></span> <span data-ttu-id="0aa83-159">Nesse caso, classificar pelo nome ou chave do atributo não classifica as distâncias do trabalho da menor para a maior.</span><span class="sxs-lookup"><span data-stu-id="0aa83-159">In this case, sorting by the attribute name or key does not sort the commute distances from least to most.</span></span> <span data-ttu-id="0aa83-160">Nesta tarefa, você classifica os membros da hierarquia de atributo com base no cálculo nomeado **CommuteDistanceSort** que atribui o número de classificação apropriado a cada valor distinto na coluna.</span><span class="sxs-lookup"><span data-stu-id="0aa83-160">In this task, you sort the members of the attribute hierarchy based on the **CommuteDistanceSort** named calculation that ascribes the appropriate sort number to each distinct value in the column.</span></span> <span data-ttu-id="0aa83-161">Para economizar tempo, esse cálculo nomeado já foi adicionado à tabela **Cliente** na exibição da fonte de dados [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW.</span><span class="sxs-lookup"><span data-stu-id="0aa83-161">To save time, this named calculation has already been added to the **Customer** table in the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW data source view.</span></span> <span data-ttu-id="0aa83-162">Você pode alternar para essa exibição da fonte de dados para exibir o script SQL que é usado para esse cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="0aa83-162">You can switch to this data source view to view the SQL script that is used in this named calculation.</span></span> <span data-ttu-id="0aa83-163">Para obter mais informações, consulte [definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="0aa83-163">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md).</span></span>  
  
     <span data-ttu-id="0aa83-164">A imagem a seguir mostra os membros da hierarquia de atributo **Distância do Trabalho** , classificados pelos valores ASCII da chave de membro.</span><span class="sxs-lookup"><span data-stu-id="0aa83-164">The following image shows the members of the **Commute Distance** attribute hierarchy, sorted by the ASCII values of the member key.</span></span>  
  
     <span data-ttu-id="0aa83-165">![Hierarquia do atributo Distância do Trabalho](../../2014/tutorials/media/l4-memberproperties-4.gif "Hierarquia do atributo Distância do Trabalho")</span><span class="sxs-lookup"><span data-stu-id="0aa83-165">![Commute Distance attribute hierarchy](../../2014/tutorials/media/l4-memberproperties-4.gif "Commute Distance attribute hierarchy")</span></span>  
  
2.  <span data-ttu-id="0aa83-166">Mude para a guia **Estrutura da Dimensão** no Designer de Dimensão da dimensão Cliente, clique com o botão direito do mouse em **CommuteDistanceSort** na tabela **Cliente** do painel **Exibição da Fonte de Dados** e clique em **Novo Atributo da Coluna**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-166">Switch to the **Dimension Structure** tab in Dimension Designer for the Customer dimension, right-click **CommuteDistanceSort** in the **Customer** table in the **Data Source View** pane, and then click **New Attribute from Column**.</span></span>  
  
3.  <span data-ttu-id="0aa83-167">No painel **Atributos** , selecione **Classificação da Distância do Trabalho**e defina a propriedade **AttributeHierarchyEnabled** desse atributo como **False** na janela Propriedades, a propriedade **AttributeHierarchyOptimizedState** como **NotOptimized**e a propriedade **AttributeHierarchyOrdered** como **False**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-167">In the **Attributes** pane, select **Commute Distance Sort**, and then set the **AttributeHierarchyEnabled** property for this attribute to **False** in the Properties window, set the **AttributeHierarchyOptimizedState** property to **NotOptimized**, and set the **AttributeHierarchyOrdered** property to **False**.</span></span>  
  
     <span data-ttu-id="0aa83-168">Essas configurações ocultarão o atributo dos usuários e melhorarão o tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="0aa83-168">These settings will hide the attribute from users and will improve processing time.</span></span> <span data-ttu-id="0aa83-169">Esse atributo não será usado para navegação.</span><span class="sxs-lookup"><span data-stu-id="0aa83-169">This attribute will not be used for browsing.</span></span> <span data-ttu-id="0aa83-170">Ele será usado apenas para classificar os membros de outro atributo.</span><span class="sxs-lookup"><span data-stu-id="0aa83-170">It will only be used for ordering the members of another attribute.</span></span>  
  
4.  <span data-ttu-id="0aa83-171">Selecione **Geografia**e defina sua propriedade **AttributeHierarchyVisible** como **False** na janela Propriedades, a propriedade **AttributeHierarchyOptimizedState** como **NotOptimized**e a propriedade **AttributeHierarchyOrdered** como **False**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-171">Select **Geography**, and then set its **AttributeHierarchyVisible** property to **False** in the Properties window, set its **AttributeHierarchyOptimizedState** property to **NotOptimized**, and set its **AttributeHierarchyOrdered** property to **False**.</span></span>  
  
     <span data-ttu-id="0aa83-172">Essas configurações ocultarão o atributo dos usuários e melhorarão o tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="0aa83-172">These settings will hide the attribute from users and will improve processing time.</span></span> <span data-ttu-id="0aa83-173">Esse atributo não será usado para navegação.</span><span class="sxs-lookup"><span data-stu-id="0aa83-173">This attribute will not be used for browsing.</span></span> <span data-ttu-id="0aa83-174">Ele será usado apenas para ordenar os membros de outro atributo.</span><span class="sxs-lookup"><span data-stu-id="0aa83-174">It will be only be used for ordering the members of another attribute.</span></span> <span data-ttu-id="0aa83-175">Como **Geografia** tem propriedades de membro, sua propriedade **AttributeHierarchyEnabled** deve ser definida como **True**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-175">Because **Geography** has member properties, its **AttributeHierarchyEnabled** property must be set to **True**.</span></span> <span data-ttu-id="0aa83-176">Portanto, para ocultar o atributo, você define a propriedade **AttributeHierarchyVisible** como **False**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-176">Therefore, to hide the attribute, you set the **AttributeHierarchyVisible** property to **False**.</span></span>  
  
5.  <span data-ttu-id="0aa83-177">Clique na guia **Relações de Atributo** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-177">Click the **Attribute Relationships** tab.</span></span>  
  
6.  <span data-ttu-id="0aa83-178">Na lista de atributos, clique com o botão direito do mouse em **Distância do Trabalho** e selecione **Nova Relação de Atributo**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-178">In the attributes list, right-click the **Commute Distance** attribute and then select **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="0aa83-179">Na caixa de diálogo **Criar Relação de Atributo** , o **Atributo de Origem** é **Distância do Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-179">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Commute Distance**.</span></span> <span data-ttu-id="0aa83-180">Defina o **Atributo Relacionado** como **Classificação da Distância do Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-180">Set the **Related Attribute** to **Commute Distance Sort**.</span></span>  
  
8.  <span data-ttu-id="0aa83-181">Na lista **Tipo de relação** , defina o tipo de relação como **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-181">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="0aa83-182">A relação entre os membros dos atributos **Distância do Trabalho** e **Classificação da Distância do Trabalho** não mudará ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="0aa83-182">The relationship between the members of the **Commute Distance** attribute and the **Commute Distance Sort** attribute will not change over time.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="0aa83-183">Agora, você está pronto para definir a ordem de classificação do atributo **Distância do Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-183">You are now ready to set the sort order for the **Commute Distance** attribute.</span></span>  
  
10. <span data-ttu-id="0aa83-184">Clique na guia **Estrutura da Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-184">Click the **Dimension Structure** tab.</span></span>  
  
11. <span data-ttu-id="0aa83-185">No painel **Atributos** , selecione **Distância do Trabalho**e altere o valor da propriedade **OrderBy** para **AttributeKey**na janela Propriedades e o valor da propriedade **OrderByAttribute** para **Classificação da Distância do Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-185">In the **Attributes** pane, select **Commute Distance**, and then change the value of the **OrderBy** property in the Properties window to **AttributeKey**, and change the value of the **OrderByAttribute** property to **Commute Distance Sort**.</span></span>  
  
12. <span data-ttu-id="0aa83-186">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="0aa83-186">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
13. <span data-ttu-id="0aa83-187">Quando a implantação for concluída com êxito, mude para a guia **Navegador** no Designer de Dimensão da dimensão Cliente. Depois, clique em **Reconectar**e procure a hierarquia de atributo **Distância do Trabalho** .</span><span class="sxs-lookup"><span data-stu-id="0aa83-187">When deployment has successfully completed, switch to the **Browser** tab of Dimension Designer for the Customer dimension, click **Reconnect**, and then browse the **Commute Distance** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="0aa83-188">Observe que os membros da hierarquia de atributo agora estão classificados em ordem lógica com base no aumento da distância, como mostra a imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="0aa83-188">Notice that the attribute hierarchy members are now sorted in a logical order based on increasing distance, as shown in the following image.</span></span>  
  
     <span data-ttu-id="0aa83-189">![Hierarquia do atributo Distância do Trabalho reclassificada](../../2014/tutorials/media/l4-memberproperties-5.gif "Hierarquia do atributo Distância do Trabalho reclassificada")</span><span class="sxs-lookup"><span data-stu-id="0aa83-189">![Re-sorted Commute Distance attribute hierarchy](../../2014/tutorials/media/l4-memberproperties-5.gif "Re-sorted Commute Distance attribute hierarchy")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0aa83-190">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="0aa83-190">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0aa83-191">Especificando relações de atributo entre atributos em uma hierarquia definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="0aa83-191">Specifying Attribute Relationships Between Attributes in a User-Defined Hierarchy</span></span>](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md)  
  
  