---
title: Ocultando e desabilitando hierarquias de atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095039c2-7104-414c-a9a6-327b03ce79df
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc043c68d2a83424a14707799fd90bf893abc12d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685962"
---
# <a name="hiding-and-disabling-attribute-hierarchies"></a><span data-ttu-id="206bb-102">Ocultando e desabilitando as hierarquias de atributo</span><span class="sxs-lookup"><span data-stu-id="206bb-102">Hiding and Disabling Attribute Hierarchies</span></span>
  <span data-ttu-id="206bb-103">Por padrão, uma hierarquia de atributo é criada para cada atributo em uma dimensão e cada hierarquia é disponibilizada para o dimensionamento de dados de fatos.</span><span class="sxs-lookup"><span data-stu-id="206bb-103">By default, an attribute hierarchy is created for every attribute in a dimension, and each hierarchy is available for dimensioning fact data.</span></span> <span data-ttu-id="206bb-104">Essa hierarquia é composta por um nível "Todos" e um nível de detalhe que contém todos os membros da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="206bb-104">This hierarchy consists of an "All" level and a detail level containing all members of the hierarchy.</span></span> <span data-ttu-id="206bb-105">Como você já aprendeu, é possível organizar atributos em hierarquias definidas pelo usuário para fornecer caminhos de navegação em um cubo.</span><span class="sxs-lookup"><span data-stu-id="206bb-105">As you have already learned, you can organize attributes into user-defined hierarchies to provide navigation paths in a cube.</span></span> <span data-ttu-id="206bb-106">Sob certas circunstâncias, talvez você queira desativar ou ocultar alguns atributos e suas hierarquias.</span><span class="sxs-lookup"><span data-stu-id="206bb-106">Under certain circumstances, you may want to disable or hide some attributes and their hierarchies.</span></span> <span data-ttu-id="206bb-107">Por exemplo, determinados atributos como um número de previdência social ou números de identificação nacional, taxas de pagamentos, datas de aniversário e informações de logon não são atributos pelos quais os usuários poderão dimensionar as informações do cubo.</span><span class="sxs-lookup"><span data-stu-id="206bb-107">For example, certain attributes such as social security numbers or national identification numbers, pay rates, birth dates, and login information are not attributes by which users will dimension cube information.</span></span> <span data-ttu-id="206bb-108">Em vez disso, geralmente essas informações são exibidas apenas como detalhes de um membro de atributo específico.</span><span class="sxs-lookup"><span data-stu-id="206bb-108">Instead, this information is generally only viewed as details of a particular attribute member.</span></span> <span data-ttu-id="206bb-109">É possível ocultar essas hierarquias de atributos, deixando os atributos visíveis apenas como propriedades de membro de um determinado atributo.</span><span class="sxs-lookup"><span data-stu-id="206bb-109">You may want to hide these attribute hierarchies, leaving the attributes visible only as member properties of a specific attribute.</span></span> <span data-ttu-id="206bb-110">Você também pode criar membros de outros atributos, como nomes de cliente ou CEPs, visíveis somente quando eles são exibidos através de uma hierarquia de usuário em vez de serem exibidos de forma independente através de uma hierarquia de atributo.</span><span class="sxs-lookup"><span data-stu-id="206bb-110">You may also want to make members of other attributes, such as customer names or postal codes, visible only when they are viewed through a user hierarchy instead of independently through an attribute hierarchy.</span></span> <span data-ttu-id="206bb-111">Uma razão para seguir esse procedimento pode ser o número absoluto de membros distintos na hierarquia de atributo.</span><span class="sxs-lookup"><span data-stu-id="206bb-111">One reason to do so may be the sheer number of distinct members in the attribute hierarchy.</span></span> <span data-ttu-id="206bb-112">Por fim, para melhorar o desempenho do processamento, será preciso desativar as hierarquias de atributo que não serão usadas pelos usuários na navegação.</span><span class="sxs-lookup"><span data-stu-id="206bb-112">Finally, to improve processing performance, you should disable attribute hierarchies that users will not use for browsing.</span></span>

 <span data-ttu-id="206bb-113">O valor da propriedade **AttributeHierarchyEnabled** determina se uma hierarquia de atributo é criada.</span><span class="sxs-lookup"><span data-stu-id="206bb-113">The value of the **AttributeHierarchyEnabled** property determines whether an attribute hierarchy is created.</span></span> <span data-ttu-id="206bb-114">Se essa propriedade for definida como **False**, a hierarquia de atributo não será criada e o atributo não poderá ser usado como um nível em uma hierarquia de usuário; a hierarquia de atributo existe apenas como uma propriedade de membro.</span><span class="sxs-lookup"><span data-stu-id="206bb-114">If this property is set to **False**, the attribute hierarchy is not created and the attribute cannot be used as a level in a user hierarchy; the attribute hierarchy exists as a member property only.</span></span> <span data-ttu-id="206bb-115">Entretanto, uma hierarquia de atributo desativada ainda pode ser usada para classificar os membros de outro atributo.</span><span class="sxs-lookup"><span data-stu-id="206bb-115">However, a disabled attribute hierarchy can still be used to order the members of another attribute.</span></span> <span data-ttu-id="206bb-116">Se o valor da propriedade **AttributeHierarchyEnabled** for definido como **True**, o valor da propriedade **AttributeHierarchyVisible** determinará se a hierarquia de atributo será visível, independentemente de seu uso em uma hierarquia definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="206bb-116">If the value of the **AttributeHierarchyEnabled** property is set to **True**, the value of the **AttributeHierarchyVisible** property determines whether the attribute hierarchy is visible independent of its use in a user-defined hierarchy.</span></span>

 <span data-ttu-id="206bb-117">Quando uma hierarquia de atributo é ativada, talvez você queira especificar valores para as três propriedades adicionais a seguir:</span><span class="sxs-lookup"><span data-stu-id="206bb-117">When an attribute hierarchy is enabled, you may want to specify values for the following three additional properties:</span></span>

-   <span data-ttu-id="206bb-118">**IsAggregatable**</span><span class="sxs-lookup"><span data-stu-id="206bb-118">**IsAggregatable**</span></span>

     <span data-ttu-id="206bb-119">Por padrão, o nível (Todos) é definido para todas as hierarquias de atributo.</span><span class="sxs-lookup"><span data-stu-id="206bb-119">By default, an (All) level is defined for all attribute hierarchies.</span></span> <span data-ttu-id="206bb-120">Para desabilitar o nível (Todos) de uma hierarquia de atributo habilitada, defina o valor dessa propriedade como **False**.</span><span class="sxs-lookup"><span data-stu-id="206bb-120">To disable the (All) level for an enabled attribute hierarchy, set the value for this property to **False**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="206bb-121">Um atributo que tem sua propriedade **IsAggregatable** definida como falsa só pode ser usado como a raiz de uma hierarquia definida pelo usuário e deve ter um membro padrão especificado (caso contrário, o mecanismo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] escolherá um valor para você).</span><span class="sxs-lookup"><span data-stu-id="206bb-121">An attribute that has its **IsAggregatable** property set to false can only be used as the root of a user-defined hierarchy and must have a default member specified (otherwise, one will be chosen for you by the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] engine).</span></span>

-   <span data-ttu-id="206bb-122">**AttributeHierarchyOrdered**</span><span class="sxs-lookup"><span data-stu-id="206bb-122">**AttributeHierarchyOrdered**</span></span>

     <span data-ttu-id="206bb-123">Por padrão, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] classifica os membros das hierarquias de atributo ativadas durante o processamento e armazena os membros por valor da propriedade **OrderBy** , como Name ou Key.</span><span class="sxs-lookup"><span data-stu-id="206bb-123">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] orders the members of enabled attribute hierarchies during processing, and then stores the members by the value of the **OrderBy** property, such as by Name or Key.</span></span> <span data-ttu-id="206bb-124">Se você não fizer questão da classificação, poderá melhorar o desempenho do processamento definindo o valor dessa propriedade como **False**.</span><span class="sxs-lookup"><span data-stu-id="206bb-124">If you do not care about ordering, you can increase processing performance by setting the value of this property to **False**.</span></span>

-   <span data-ttu-id="206bb-125">**AttributeHierarchyOptimizedState**</span><span class="sxs-lookup"><span data-stu-id="206bb-125">**AttributeHierarchyOptimizedState**</span></span>

     <span data-ttu-id="206bb-126">Por padrão, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cria um índice para cada hierarquia de atributo ativada durante o processamento para melhorar desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="206bb-126">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates an index for each enabled attribute hierarchy during processing, to improve query performance.</span></span> <span data-ttu-id="206bb-127">Porém, se uma hierarquia de atributo não for usada para pesquisa, você poderá melhorar o desempenho do processamento, definindo o valor dessa propriedade para **NotOptimized**.</span><span class="sxs-lookup"><span data-stu-id="206bb-127">If you do not plan to use an attribute hierarchy for browsing, you can increase processing performance by setting the value of this property to **NotOptimized**.</span></span> <span data-ttu-id="206bb-128">Entretanto, se uma hierarquia oculta for usada como o atributo de chave para a dimensão, ainda assim a criação de um índice de membros de atributo ajudará a melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="206bb-128">However, if you use a hidden hierarchy as the key attribute for the dimension, creating an index of the attribute members will still improve performance.</span></span>

 <span data-ttu-id="206bb-129">Essas propriedades não serão aplicadas se uma hierarquia de atributo estiver desativada.</span><span class="sxs-lookup"><span data-stu-id="206bb-129">These properties do not apply if an attribute hierarchy is disabled.</span></span>

 <span data-ttu-id="206bb-130">Nas tarefas deste tópico, você desativará o número de previdência social e outros atributos na dimensão Funcionário que não serão usados para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="206bb-130">In the tasks in this topic, you will disable social security numbers and other attributes in the Employee dimension that will not be used for browsing.</span></span> <span data-ttu-id="206bb-131">Você ocultará o nome do cliente e as hierarquias de atributo de CEPs na dimensão Cliente.</span><span class="sxs-lookup"><span data-stu-id="206bb-131">You will then hide the customer name and postal code attribute hierarchies in the Customer dimension.</span></span> <span data-ttu-id="206bb-132">Quanto maior o número de membros de atributo nas hierarquias, maior será o tempo de pesquisa nessas hierarquias, tornando a pesquisa mais lenta independentemente de uma hierarquia de usuário.</span><span class="sxs-lookup"><span data-stu-id="206bb-132">The large number of attribute members in these hierarchies will make browsing these hierarchies very slow independent of a user hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-employee-dimension"></a><span data-ttu-id="206bb-133">Definindo as propriedades da hierarquia de atributo na dimensão Funcionário</span><span class="sxs-lookup"><span data-stu-id="206bb-133">Setting Attribute Hierarchy Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="206bb-134">Alterne para o Designer de Dimensão para a dimensão Funcionário e clique na guia **Navegador** .</span><span class="sxs-lookup"><span data-stu-id="206bb-134">Switch to Dimension Designer for the Employee dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="206bb-135">Observe se as seguintes hierarquias de atributo aparecem na lista **Hierarquia** :</span><span class="sxs-lookup"><span data-stu-id="206bb-135">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="206bb-136">**Taxa Básica**</span><span class="sxs-lookup"><span data-stu-id="206bb-136">**Base Rate**</span></span>

    -   <span data-ttu-id="206bb-137">**Birth Date**</span><span class="sxs-lookup"><span data-stu-id="206bb-137">**Birth Date**</span></span>

    -   <span data-ttu-id="206bb-138">**ID de Logon**</span><span class="sxs-lookup"><span data-stu-id="206bb-138">**Login ID**</span></span>

    -   <span data-ttu-id="206bb-139">**Gerente SSN**</span><span class="sxs-lookup"><span data-stu-id="206bb-139">**Manager SSN**</span></span>

    -   <span data-ttu-id="206bb-140">**SSN**</span><span class="sxs-lookup"><span data-stu-id="206bb-140">**SSN**</span></span>

3.  <span data-ttu-id="206bb-141">Alterne para a guia **Estrutura da Dimensão** e selecione os atributos a seguir no painel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="206bb-141">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane.</span></span> <span data-ttu-id="206bb-142">Você pode selecionar várias medidas clicando em cada uma enquanto mantém pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="206bb-142">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>

    -   <span data-ttu-id="206bb-143">**Taxa Básica**</span><span class="sxs-lookup"><span data-stu-id="206bb-143">**Base Rate**</span></span>

    -   <span data-ttu-id="206bb-144">**Birth Date**</span><span class="sxs-lookup"><span data-stu-id="206bb-144">**Birth Date**</span></span>

    -   <span data-ttu-id="206bb-145">**ID de Logon**</span><span class="sxs-lookup"><span data-stu-id="206bb-145">**Login ID**</span></span>

    -   <span data-ttu-id="206bb-146">**Gerente SSN**</span><span class="sxs-lookup"><span data-stu-id="206bb-146">**Manager SSN**</span></span>

    -   <span data-ttu-id="206bb-147">**SSN**</span><span class="sxs-lookup"><span data-stu-id="206bb-147">**SSN**</span></span>

4.  <span data-ttu-id="206bb-148">Na janela Propriedades, defina o valor da propriedade **AttributeHierarchyEnabled** como **False** para os atributos selecionados.</span><span class="sxs-lookup"><span data-stu-id="206bb-148">In the Properties window, set the value of the **AttributeHierarchyEnabled** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="206bb-149">Observe no painel **Atributos** que o ícone dos atributos mudou, indicando que o atributo não está ativado.</span><span class="sxs-lookup"><span data-stu-id="206bb-149">Notice in the **Attributes** pane that the icon for each attribute has changed to indicate that the attribute is not enabled.</span></span>

     <span data-ttu-id="206bb-150">A imagem a seguir mostra a propriedade **AttributeHierarchyEnabled** definida como False para os atributos selecionados.</span><span class="sxs-lookup"><span data-stu-id="206bb-150">The following image shows the **AttributeHierarchyEnabled** property set to False for the selected attributes.</span></span>

     <span data-ttu-id="206bb-151">![Propriedade AttributeHierarchyEnabled definida como False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "Propriedade AttributeHierarchyEnabled definida como False")</span><span class="sxs-lookup"><span data-stu-id="206bb-151">![AttributeHierarchyEnabled property set to False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "AttributeHierarchyEnabled property set to False")</span></span>

5.  <span data-ttu-id="206bb-152">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="206bb-152">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

6.  <span data-ttu-id="206bb-153">Quando o processamento tiver sido concluído com êxito, alterne para a guia **Navegador** e clique no botão **Reconectar**. Em seguida, tente navegar pelas hierarquias de atributo modificadas.</span><span class="sxs-lookup"><span data-stu-id="206bb-153">When processing has successfully completed, switch to the **Browser** tab, click **Reconnect**, and then try to browse the modified attribute hierarchies.</span></span>

     <span data-ttu-id="206bb-154">Observe que os membros dos atributos modificados não estão disponíveis para pesquisa como hierarquias de atributo na lista **Hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="206bb-154">Notice that the members of the modified attributes are not available for browsing as attribute hierarchies in the **Hierarchy** list.</span></span> <span data-ttu-id="206bb-155">Se tentar adicionar uma das hierarquias de atributo desativadas como um nível em uma hierarquia de usuário, você receberá um erro notificando que a hierarquia de atributo deve ser ativada para que possa fazer parte da hierarquia definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="206bb-155">If you try to add one of the disabled attribute hierarchies as a level in a user hierarchy, you will receive an error notifying you that the attribute hierarchy must be enabled to participate in a user-defined hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-customer-dimension"></a><span data-ttu-id="206bb-156">Definindo as propriedades da hierarquia de atributo na dimensão Cliente</span><span class="sxs-lookup"><span data-stu-id="206bb-156">Setting Attribute Hierarchy Properties in the Customer Dimension</span></span>

1.  <span data-ttu-id="206bb-157">Alterne para o Designer de Dimensão para a dimensão Cliente e clique na guia **Navegador** .</span><span class="sxs-lookup"><span data-stu-id="206bb-157">Switch to Dimension Designer for the Customer dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="206bb-158">Observe se as seguintes hierarquias de atributo aparecem na lista **Hierarquia** :</span><span class="sxs-lookup"><span data-stu-id="206bb-158">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="206bb-159">**Nome completo**</span><span class="sxs-lookup"><span data-stu-id="206bb-159">**Full Name**</span></span>

    -   <span data-ttu-id="206bb-160">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="206bb-160">**Postal Code**</span></span>

3.  <span data-ttu-id="206bb-161">Alterne para a guia **Estrutura da Dimensão** e selecione os seguintes atributos no painel **Atributos** usando a tecla CTRL para selecionar vários atributos ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="206bb-161">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane by using the CTRL key to select multiple attributes at the same time:</span></span>

    -   <span data-ttu-id="206bb-162">**Nome completo**</span><span class="sxs-lookup"><span data-stu-id="206bb-162">**Full Name**</span></span>

    -   <span data-ttu-id="206bb-163">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="206bb-163">**Postal Code**</span></span>

4.  <span data-ttu-id="206bb-164">Na janela Propriedades, defina o valor da propriedade **AttributeHierarchyVisible** como **False** para os atributos selecionados.</span><span class="sxs-lookup"><span data-stu-id="206bb-164">In the Properties window, set the value of the **AttributeHierarchyVisible** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="206bb-165">Como os membros dessas hierarquias de atributo serão usados para dimensionar dados de fatos, classificar e otimizar os membros dessas hierarquias melhorará o desempenho.</span><span class="sxs-lookup"><span data-stu-id="206bb-165">Because the members of these attribute hierarchies will be used for dimensioning fact data, ordering and optimizing the members of these attribute hierarchies will improve performance.</span></span> <span data-ttu-id="206bb-166">Além disso, as propriedades desses atributos não devem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="206bb-166">Therefore, the properties of these attributes should not be changed.</span></span>

     <span data-ttu-id="206bb-167">A imagem a seguir mostra a propriedade **AttributeHierarchyVisible** definida como False.</span><span class="sxs-lookup"><span data-stu-id="206bb-167">The following image shows the **AttributeHierarchyVisible** property set to False.</span></span>

     <span data-ttu-id="206bb-168">![Propriedade AttributeHierarchyVisible definida como False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "Propriedade AttributeHierarchyVisible definida como False")</span><span class="sxs-lookup"><span data-stu-id="206bb-168">![AttributeHierarchyVisible property set to False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "AttributeHierarchyVisible property set to False")</span></span>

5.  <span data-ttu-id="206bb-169">Arraste o atributo **CEP** do painel **Atributos** para a hierarquia de usuário **Geografia do Cliente** no painel **Hierarquias e Níveis** , imediatamente abaixo do nível **Cidade** .</span><span class="sxs-lookup"><span data-stu-id="206bb-169">Drag the **Postal Code** attribute from the **Attributes** pane into the **Customer Geography** user hierarchy in the **Hierarchies and Levels** pane, immediately under the **City** level.</span></span>

     <span data-ttu-id="206bb-170">Observe que um atributo oculto ainda pode se tornar um nível em uma hierarquia de usuário.</span><span class="sxs-lookup"><span data-stu-id="206bb-170">Notice that a hidden attribute can still become a level in a user hierarchy.</span></span>

6.  <span data-ttu-id="206bb-171">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="206bb-171">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

7.  <span data-ttu-id="206bb-172">Quando a implantação for concluída com êxito, alterne para a guia **Navegador** da dimensão Cliente e clique em **Reconectar**.</span><span class="sxs-lookup"><span data-stu-id="206bb-172">When deployment has successfully completed, switch to the **Browser** tab for the Customer dimension, and then click **Reconnect**.</span></span>

8.  <span data-ttu-id="206bb-173">Tente selecionar qualquer uma das hierarquias de atributo modificadas da lista **Hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="206bb-173">Try to select either of the modified attribute hierarchies from the **Hierarchy** list.</span></span>

     <span data-ttu-id="206bb-174">Observe que nenhuma das hierarquias de atributo modificadas aparece na lista **Hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="206bb-174">Notice that neither of the modified attribute hierarchies appears in the **Hierarchy** list.</span></span>

9. <span data-ttu-id="206bb-175">Na lista **Hierarquia** , selecione **Geografia do Cliente**e navegue pelos níveis no painel do navegador.</span><span class="sxs-lookup"><span data-stu-id="206bb-175">In the **Hierarchy** list, select **Customer Geography**, and then browse each level in the browser pane.</span></span>

     <span data-ttu-id="206bb-176">Observe que os níveis ocultos, **CEP** e **Nome Completo**, estão visíveis na hierarquia definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="206bb-176">Notice that the hidden levels, **Postal Code** and **Full Name**, are visible in the user-defined hierarchy.</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="206bb-177">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="206bb-177">Next Task in Lesson</span></span>
 [<span data-ttu-id="206bb-178">Classificando membros de atributo com base em um atributo secundário</span><span class="sxs-lookup"><span data-stu-id="206bb-178">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)


