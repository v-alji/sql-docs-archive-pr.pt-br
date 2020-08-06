---
title: Agrupando automaticamente membros de atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9fb2cda3-a122-4a4c-82e0-3454865eef04
author: minewiskan
ms.author: owend
ms.openlocfilehash: 820231263362a92584a15556e999d69f286349b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685972"
---
# <a name="automatically-grouping-attribute-members"></a><span data-ttu-id="f7289-102">Agrupando membros de atributo automaticamente</span><span class="sxs-lookup"><span data-stu-id="f7289-102">Automatically Grouping Attribute Members</span></span>
  <span data-ttu-id="f7289-103">Ao navegar em um cubo, você normalmente dimensiona os membros de uma hierarquia de atributo pelos membros de outra hierarquia de atributo.</span><span class="sxs-lookup"><span data-stu-id="f7289-103">When you browse a cube, you typically dimension the members of one attribute hierarchy by the members of another attribute hierarchy.</span></span> <span data-ttu-id="f7289-104">Por exemplo, você pode agrupar as vendas de cliente por cidade, produto comprado ou sexo.</span><span class="sxs-lookup"><span data-stu-id="f7289-104">For example, you might group customer sales by city, by product purchased, or by gender.</span></span> <span data-ttu-id="f7289-105">No entanto, com determinados tipos de atributos, é útil [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] criar automaticamente agrupamentos de membros de atributo com base na distribuição dos membros em uma hierarquia de atributo.</span><span class="sxs-lookup"><span data-stu-id="f7289-105">However, with certain types of attributes, it is useful to have [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] automatically create groupings of attribute members based on the distribution of the members within an attribute hierarchy.</span></span> <span data-ttu-id="f7289-106">Por exemplo, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] pode criar grupos de valores de renda anual para clientes.</span><span class="sxs-lookup"><span data-stu-id="f7289-106">For example, you can have [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] create groups of yearly income values for customers.</span></span> <span data-ttu-id="f7289-107">Ao fazer isso, os usuários que navegarem pela hierarquia de atributo verão o nome e os valores dos grupos em vez dos próprios membros.</span><span class="sxs-lookup"><span data-stu-id="f7289-107">When you do this, users who browse the attribute hierarchy will see the names and values of the groups instead of the members themselves.</span></span> <span data-ttu-id="f7289-108">Isso limita o número de níveis que são apresentados aos usuários, o que pode ser mais útil para a análise.</span><span class="sxs-lookup"><span data-stu-id="f7289-108">This limits the number of levels that are presented to users, which can be more useful for analysis.</span></span>

 <span data-ttu-id="f7289-109">A propriedade **DiscretizationMethod** determina se [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cria agrupamentos e determina o tipo de agrupamento feito.</span><span class="sxs-lookup"><span data-stu-id="f7289-109">The **DiscretizationMethod** property determines whether [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates groupings, and determines the type of grouping that is performed.</span></span> <span data-ttu-id="f7289-110">Por padrão, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] não faz nenhum agrupamento.</span><span class="sxs-lookup"><span data-stu-id="f7289-110">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] does not perform any groupings.</span></span> <span data-ttu-id="f7289-111">Ao habilitar agrupamentos automáticos, você pode permitir que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] determine automaticamente o melhor método de agrupamento com base na estrutura do atributo ou ainda escolher um dos algoritmos de agrupamento da lista a seguir para especificar o método de agrupamento:</span><span class="sxs-lookup"><span data-stu-id="f7289-111">When you enable automatic groupings, you can allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to automatically determine the best grouping method based on the structure of the attribute, or you can choose one of the grouping algorithms in the following list to specify the grouping method:</span></span>

 <span data-ttu-id="f7289-112">**EqualAreas** [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cria intervalos de grupo de forma que a população total de membros da dimensão seja distribuída igualmente pelos grupos.</span><span class="sxs-lookup"><span data-stu-id="f7289-112">**EqualAreas** [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates group ranges so that the total population of dimension members is distributed equally across the groups.</span></span>

 <span data-ttu-id="f7289-113">**Clusters** [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cria grupos executando clustering unidimensional nos valores de entrada usando o método de clustering K-means com distribuições gaussianas.</span><span class="sxs-lookup"><span data-stu-id="f7289-113">**Clusters** [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates groups by performing single-dimensional clustering on the input values by using the K-Means clustering method with Gaussian distributions.</span></span> <span data-ttu-id="f7289-114">Essa opção só é válida para colunas numéricas.</span><span class="sxs-lookup"><span data-stu-id="f7289-114">This option is valid only for numeric columns.</span></span>

 <span data-ttu-id="f7289-115">Depois de especificar um método de agrupamento, você deve especificar o número de grupos usando a propriedade **DiscretizationBucketCount** .</span><span class="sxs-lookup"><span data-stu-id="f7289-115">After you specify a grouping method, you must specify the number of groups, by using the **DiscretizationBucketCount** property.</span></span> <span data-ttu-id="f7289-116">Para obter mais informações, consulte [Agrupar membros de atributo &#40;discretização&#41;](multidimensional-models/attribute-properties-group-attribute-members.md)</span><span class="sxs-lookup"><span data-stu-id="f7289-116">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md)</span></span>

 <span data-ttu-id="f7289-117">Nas tarefas deste tópico, você habilitará tipos diferentes de agrupamentos para valores de renda anual na dimensão **Cliente** ; número de horas de dispensa médica dos funcionários na dimensão **Funcionários** ; e o número de horas de férias dos funcionários na dimensão **Funcionários** .</span><span class="sxs-lookup"><span data-stu-id="f7289-117">In the tasks in this topic, you will enable different types of groupings for the following: the yearly income values in the **Customer** dimension; the number of employee sick leave hours in the **Employees** dimension; and the number of employee vacation hours in the **Employees** dimension.</span></span> <span data-ttu-id="f7289-118">Depois, você processará e navegará no cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para exibir o efeito dos grupos de membros.</span><span class="sxs-lookup"><span data-stu-id="f7289-118">You will then process and browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube to view the effect of the member groups.</span></span> <span data-ttu-id="f7289-119">Finalmente, você modificará as propriedades do grupo de membros para ver o efeito da alteração no tipo de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="f7289-119">Finally, you will modify the member group properties to see the effect of the change in grouping type.</span></span>

## <a name="grouping-attribute-hierarchy-members-in-the-customer-dimension"></a><span data-ttu-id="f7289-120">Agrupando membros da hierarquia de atributo na dimensão Cliente</span><span class="sxs-lookup"><span data-stu-id="f7289-120">Grouping Attribute Hierarchy Members in the Customer Dimension</span></span>

1.  <span data-ttu-id="f7289-121">No Gerenciador de Soluções, clique duas vezes em **Cliente** na pasta **Dimensões** para abrir o Designer de Dimensão da dimensão Customer.</span><span class="sxs-lookup"><span data-stu-id="f7289-121">In Solution Explorer, double-click **Customer** in the **Dimensions** folder to open Dimension Designer for the Customer dimension.</span></span>

2.  <span data-ttu-id="f7289-122">No painel **Exibição da Fonte de Dados** , clique com o botão direito do mouse na tabela **Cliente** e clique em **Explorar Dados**.</span><span class="sxs-lookup"><span data-stu-id="f7289-122">In the **Data Source View** pane, right-click the **Customer** table, and then click **Explore Data**.</span></span>

     <span data-ttu-id="f7289-123">Observe o intervalo de valores da coluna **YearlyIncome** .</span><span class="sxs-lookup"><span data-stu-id="f7289-123">Notice the range of values for the **YearlyIncome** column.</span></span> <span data-ttu-id="f7289-124">Esses valores se tornam os membros da hierarquia de atributo **Renda Anual** , a menos que você habilite o agrupamento de membros.</span><span class="sxs-lookup"><span data-stu-id="f7289-124">These values become the members of the **Yearly Income** attribute hierarchy, unless you enable member grouping.</span></span>

3.  <span data-ttu-id="f7289-125">Feche a guia **Explorar Tabela Cliente** .</span><span class="sxs-lookup"><span data-stu-id="f7289-125">Close the **Explore Customer Table** tab.</span></span>

4.  <span data-ttu-id="f7289-126">No painel **Atributos** , selecione **Renda Anual**.</span><span class="sxs-lookup"><span data-stu-id="f7289-126">In the **Attributes** pane, select **Yearly Income**.</span></span>

5.  <span data-ttu-id="f7289-127">No janela Propriedades, altere o valor da propriedade **DiscretizationMethod** para **Automatic** e altere o valor para a propriedade **DiscretizationBucketCount** para `5` .</span><span class="sxs-lookup"><span data-stu-id="f7289-127">In the Properties window, change the value for the **DiscretizationMethod** property to **Automatic** and change the value for the **DiscretizationBucketCount** property to `5`.</span></span>

     <span data-ttu-id="f7289-128">A imagem a seguir mostra as propriedades modificadas para **Renda Anual**.</span><span class="sxs-lookup"><span data-stu-id="f7289-128">The following image shows the modified properties for **Yearly Income**.</span></span>

     <span data-ttu-id="f7289-129">![Propriedades modificadas para Renda Anual](../../2014/tutorials/media/l4-discretizationmethod-1.gif "Propriedades modificadas para Renda Anual")</span><span class="sxs-lookup"><span data-stu-id="f7289-129">![Modified properties for Yearly Income](../../2014/tutorials/media/l4-discretizationmethod-1.gif "Modified properties for Yearly Income")</span></span>

## <a name="grouping-attribute-hierarchy-members-in-the-employee-dimension"></a><span data-ttu-id="f7289-130">Agrupando membros da hierarquia de atributo na dimensão Funcionário</span><span class="sxs-lookup"><span data-stu-id="f7289-130">Grouping Attribute Hierarchy Members in the Employee Dimension</span></span>

1.  <span data-ttu-id="f7289-131">Alterne para o Designer de Dimensão da dimensão Funcionário.</span><span class="sxs-lookup"><span data-stu-id="f7289-131">Switch to Dimension Designer for the Employee dimension.</span></span>

2.  <span data-ttu-id="f7289-132">No painel **Exibição da Fonte de Dados** , clique com o botão direito do mouse na tabela **Funcionário** e clique em **Explorar Dados**.</span><span class="sxs-lookup"><span data-stu-id="f7289-132">In the **Data Source View** pane, right-click the **Employee** table, and then click **Explore Data**.</span></span>

     <span data-ttu-id="f7289-133">Observe os valores das colunas **SickLeaveHours** e **VacationHours** .</span><span class="sxs-lookup"><span data-stu-id="f7289-133">Notice the values for the **SickLeaveHours** column and the **VacationHours** column.</span></span>

3.  <span data-ttu-id="f7289-134">Feche a guia **Explorar Tabela Funcionário** .</span><span class="sxs-lookup"><span data-stu-id="f7289-134">Close the **Explore Employee Table** tab.</span></span>

4.  <span data-ttu-id="f7289-135">No painel **Atributos** , selecione **Horas de Dispensa Médica**.</span><span class="sxs-lookup"><span data-stu-id="f7289-135">In the **Attributes** pane, select **Sick Leave Hours**.</span></span>

5.  <span data-ttu-id="f7289-136">No janela Propriedades, altere o valor da propriedade **DiscretizationMethod** para **clusters** e altere o valor para a propriedade **DiscretizationBucketCount** para `5` .</span><span class="sxs-lookup"><span data-stu-id="f7289-136">In the Properties window, change the value for the **DiscretizationMethod** property to **Clusters** and change the value for the **DiscretizationBucketCount** property to `5`.</span></span>

6.  <span data-ttu-id="f7289-137">No painel **Atributos** , selecione **Horas de Férias**.</span><span class="sxs-lookup"><span data-stu-id="f7289-137">In the **Attributes** pane, select **Vacation Hours**.</span></span>

7.  <span data-ttu-id="f7289-138">No janela Propriedades, altere o valor da propriedade **DiscretizationMethod** para **áreas iguais** e altere o valor para a propriedade **DiscretizationBucketCount** para `5` .</span><span class="sxs-lookup"><span data-stu-id="f7289-138">In the Properties window, change the value for the **DiscretizationMethod** property to **Equal Areas** and change the value for the **DiscretizationBucketCount** property to `5`.</span></span>

## <a name="browsing-the-modified-attribute-hierarchies"></a><span data-ttu-id="f7289-139">Navegando nas hierarquias de atributo modificadas</span><span class="sxs-lookup"><span data-stu-id="f7289-139">Browsing the Modified Attribute Hierarchies</span></span>

1.  <span data-ttu-id="f7289-140">No menu **Compilar** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f7289-140">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="f7289-141">Quando a implantação finalizar com êxito, alterne para o Designer de Cubo do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e, em seguida, clique em **Reconectar** na guia **Navegador** .</span><span class="sxs-lookup"><span data-stu-id="f7289-141">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the **Browser** tab.</span></span>

3.  <span data-ttu-id="f7289-142">Clique no ícone do Excel e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="f7289-142">Click the Excel icon, and then click **Enable**.</span></span>

4.  <span data-ttu-id="f7289-143">Arraste a medida **Vendas pela Internet/Valor das Vendas** até a área Valores da Lista de Campos da Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="f7289-143">Drag the **Internet Sales-Sales Amount** measure to the Values area of the PivotTable Field List.</span></span>

5.  <span data-ttu-id="f7289-144">Na lista de campos, expanda a dimensão **Produto** e arraste a hierarquia de usuário **Linhas de Modelo do Produto** para a área **Rótulos de Linhas** da lista de campos.</span><span class="sxs-lookup"><span data-stu-id="f7289-144">In the field list, expand the **Product** dimension, and then drag the **Product Model Lines** user hierarchy to the **Row Labels** area of the field list.</span></span>

6.  <span data-ttu-id="f7289-145">Expanda a dimensão **Cliente** na lista de campos, expanda a pasta de exibição **Demográfico** e, em seguida, arraste a hierarquia de atributo **Renda Anual** para a área **Rótulos de Coluna** .</span><span class="sxs-lookup"><span data-stu-id="f7289-145">Expand the **Customer** dimension in the field list, expand the **Demographic** display folder, and then drag the **Yearly Income** attribute hierarchy to the **Column Labels** area.</span></span>

     <span data-ttu-id="f7289-146">Agora, os membros da hierarquia de atributo **Renda Anual** estão agrupados em seis buckets, incluindo um bucket de vendas para clientes cuja renda anual é desconhecida.</span><span class="sxs-lookup"><span data-stu-id="f7289-146">The members of the **Yearly Income** attribute hierarchy are now grouped into six buckets, including a bucket for sales to customers whose yearly income is unknown.</span></span> <span data-ttu-id="f7289-147">Nem todos os buckets são exibidos.</span><span class="sxs-lookup"><span data-stu-id="f7289-147">Not all buckets are displayed.</span></span>

7.  <span data-ttu-id="f7289-148">Remova a hierarquia de atributo **Renda Anual** da área de colunas e a medida **Vendas pela Internet/Valor das Vendas** da área **Valores** .</span><span class="sxs-lookup"><span data-stu-id="f7289-148">Remove the **Yearly Income** attribute hierarchy from the columns area and remove the **Internet Sales-Sales Amount** measure from the **Values** area.</span></span>

8.  <span data-ttu-id="f7289-149">Adicione a medida **Vendas do Revendedor/Valor das Vendas** à área de dados.</span><span class="sxs-lookup"><span data-stu-id="f7289-149">Add the **Reseller Sales-Sales Amount** measure to the data area.</span></span>

9. <span data-ttu-id="f7289-150">Na lista de campos, expanda a dimensão **Funcionário** , expanda **Organização**e, em seguida, arraste **Horas de Dispensa Médica** para **Rótulos de Coluna**.</span><span class="sxs-lookup"><span data-stu-id="f7289-150">In the field list, expand the **Employee** dimension, expand **Organization**, then drag **Sick Leave Hours** to **Column Labels**.</span></span>

     <span data-ttu-id="f7289-151">Observe que todas as vendas são feitas por funcionários dentro de um dos dois grupos.</span><span class="sxs-lookup"><span data-stu-id="f7289-151">Notice that all sales are made by employees within one of two groups.</span></span> <span data-ttu-id="f7289-152">Observe também que os funcionários com 32 a 42 horas de dispensa médica fizeram um número significativamente maior de compras que os funcionários com 20 a 31 horas de dispensa médica.</span><span class="sxs-lookup"><span data-stu-id="f7289-152">Notice also that the employees with 32 - 42 sick leave hours made significantly more sales than employees with 20 - 31 sick leave hours.</span></span>

     <span data-ttu-id="f7289-153">A imagem a seguir mostra as vendas dimensionadas pelas horas de dispensa médica dos funcionários:</span><span class="sxs-lookup"><span data-stu-id="f7289-153">The following image shows sales dimensioned by employee sick leave hours.</span></span>

     <span data-ttu-id="f7289-154">![Vendas dimensionadas pelas horas de dispensa médica dos funcionários](../../2014/tutorials/media/l4-discretizationmethod-2.gif "Vendas dimensionadas pelas horas de dispensa médica dos funcionários")</span><span class="sxs-lookup"><span data-stu-id="f7289-154">![Sales dimensioned by employee sick leave hours](../../2014/tutorials/media/l4-discretizationmethod-2.gif "Sales dimensioned by employee sick leave hours")</span></span>

10. <span data-ttu-id="f7289-155">Remova a hierarquia **Horas de Dispensa Médica** da área de coluna do painel **Dados** .</span><span class="sxs-lookup"><span data-stu-id="f7289-155">Remove the **Sick Leave Hours** attribute hierarchy from the column area of the **Data** pane.</span></span>

11. <span data-ttu-id="f7289-156">Adicione **Horas de Férias** à área de coluna do painel **Dados** .</span><span class="sxs-lookup"><span data-stu-id="f7289-156">Add **Vacation Hours** to the column area of the **Data** pane.</span></span>

     <span data-ttu-id="f7289-157">Observe que dois grupos são exibidos com base no método de agrupamento de áreas iguais.</span><span class="sxs-lookup"><span data-stu-id="f7289-157">Notice that two groups appear, based on the equal areas grouping method.</span></span> <span data-ttu-id="f7289-158">Os outros três outros grupos são ocultados, pois não contêm nenhum valor de dados.</span><span class="sxs-lookup"><span data-stu-id="f7289-158">Three other groups are hidden because they contain no data values.</span></span>

## <a name="modifying-grouping-properties-and-reviewing-the-effect-of-the-changes"></a><span data-ttu-id="f7289-159">Modificando as propriedades de agrupamento e revisando o efeito das alterações</span><span class="sxs-lookup"><span data-stu-id="f7289-159">Modifying Grouping Properties and Reviewing the Effect of the Changes</span></span>

1.  <span data-ttu-id="f7289-160">Alterne para o Designer de Dimensão da dimensão **Funcionário** e depois selecione **Horas de Férias** no painel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="f7289-160">Switch to Dimension Designer for the **Employee** dimension, and then select **Vacation Hours** in the **Attributes** pane.</span></span>

2.  <span data-ttu-id="f7289-161">Na janela Propriedades, altere o valor da propriedade **DiscretizationBucketCount** para **10.**</span><span class="sxs-lookup"><span data-stu-id="f7289-161">In the Properties window, change the value of the **DiscretizationBucketCount** property to **10.**</span></span>

3.  <span data-ttu-id="f7289-162">No menu **Compilar** do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f7289-162">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

4.  <span data-ttu-id="f7289-163">Quando a implantação for finalizada com êxito, volte para o Designer de Cubo do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7289-163">When deployment has successfully completed, switch back to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

5.  <span data-ttu-id="f7289-164">Clique em **Reconectar** na guia **Navegador** , clique no ícone do Excel e, em seguida, reconstrua a Tabela Dinâmica para que você possa exibir o efeito da alteração do método de agrupamento:</span><span class="sxs-lookup"><span data-stu-id="f7289-164">Click **Reconnect** on the **Browser** tab, click the Excel icon, and then reconstruct the PivotTable so that you can view the effect of the change to the grouping method:</span></span>

    1.  <span data-ttu-id="f7289-165">Arraste Vendas do Revendedor-Valor das Vendas para Valores</span><span class="sxs-lookup"><span data-stu-id="f7289-165">Drag Reseller Sales-Sales Amount to Values</span></span>

    2.  <span data-ttu-id="f7289-166">Arraste Horas de Férias (na pasta Organização de Funcionários) para Colunas</span><span class="sxs-lookup"><span data-stu-id="f7289-166">Drag Vacation Hours (in the Employees Organization folder) to Columns</span></span>

    3.  <span data-ttu-id="f7289-167">Arraste Linhas de Modelo de Produtos para Linhas</span><span class="sxs-lookup"><span data-stu-id="f7289-167">Drag Product Model Lines to Rows</span></span>

     <span data-ttu-id="f7289-168">Observe que, agora, há três grupos de membros do atributo **Horas de Férias** que contêm valores de vendas para produtos.</span><span class="sxs-lookup"><span data-stu-id="f7289-168">Notice that there are now three groups of members of the **Vacation Hours** attribute that have sales values for products.</span></span> <span data-ttu-id="f7289-169">(Os outros sete grupos contêm membros sem dados de vendas.)</span><span class="sxs-lookup"><span data-stu-id="f7289-169">(The other seven groups contain members with no sales data.)</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="f7289-170">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="f7289-170">Next Task in Lesson</span></span>
 [<span data-ttu-id="f7289-171">Ocultando e desabilitando as hierarquias de atributo</span><span class="sxs-lookup"><span data-stu-id="f7289-171">Hiding and Disabling Attribute Hierarchies</span></span>](lesson-4-4-hiding-and-disabling-attribute-hierarchies.md)

## <a name="see-also"></a><span data-ttu-id="f7289-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f7289-172">See Also</span></span>
 [<span data-ttu-id="f7289-173">Agrupar membros de atributo &#40;Discretização&#41;</span><span class="sxs-lookup"><span data-stu-id="f7289-173">Group Attribute Members &#40;Discretization&#41;</span></span>](multidimensional-models/attribute-properties-group-attribute-members.md)


