---
title: Definindo propriedades de atributo pai em uma hierarquia pai-filho | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d78fa73-a13b-4e12-bbd0-43e5307f760c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1dfa4340bdc161809cf3821e5cb1f0609399e1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575425"
---
# <a name="defining-parent-attribute-properties-in-a-parent-child-hierarchy"></a><span data-ttu-id="34459-102">Definindo propriedades de atributo pai em uma hierarquia pai-filho</span><span class="sxs-lookup"><span data-stu-id="34459-102">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>
  <span data-ttu-id="34459-103">Uma hierarquia pai-filho é uma hierarquia em uma dimensão que se baseia em duas colunas de tabela.</span><span class="sxs-lookup"><span data-stu-id="34459-103">A parent-child hierarchy is a hierarchy in a dimension that is based on two table columns.</span></span> <span data-ttu-id="34459-104">Juntas, essas colunas definem as relações hierárquicas entre os membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="34459-104">Together, these columns define the hierarchical relationships among the members of the dimension.</span></span> <span data-ttu-id="34459-105">A primeira coluna, chamada *coluna de chave de membro*, identifica cada membro da dimensão.</span><span class="sxs-lookup"><span data-stu-id="34459-105">The first column, called the *member key column*, identifies each dimension member.</span></span> <span data-ttu-id="34459-106">A outra coluna, chamada *coluna pai*, identifica o pai de cada membro da dimensão.</span><span class="sxs-lookup"><span data-stu-id="34459-106">The other column, called the *parent column*, identifies the parent of each dimension member.</span></span> <span data-ttu-id="34459-107">A propriedade **NamingTemplate** de um atributo pai determina o nome de cada nível na hierarquia pai-filho e a propriedade **MembersWithData** determina se os dados dos membros pai deverão ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="34459-107">The **NamingTemplate** property of a parent attribute determines the name of each level in the parent-child hierarchy, and the **MembersWithData** property determines whether data for parent members should be displayed.</span></span>

 <span data-ttu-id="34459-108">Para obter mais informações, consulte [hierarquia pai-filho](multidimensional-models/parent-child-dimension.md), [atributos em hierarquias pai-filho](multidimensional-models/parent-child-dimension-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="34459-108">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md), [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>

> [!NOTE]
>  <span data-ttu-id="34459-109">Ao usar o Assistente para Dimensões para criar uma dimensão, o assistente reconhece as tabelas que apresentam relações pai-filho e define automaticamente a hierarquia pai-filho.</span><span class="sxs-lookup"><span data-stu-id="34459-109">When you use the Dimension Wizard to create a dimension, the wizard recognizes the tables that have parent-child relationships and automatically defines the parent-child hierarchy for you.</span></span>

 <span data-ttu-id="34459-110">Nas tarefas deste tópico, você criará um modelo de nomeação que definirá o nome de cada nível na hierarquia pai-filho na dimensão **Funcionário** .</span><span class="sxs-lookup"><span data-stu-id="34459-110">In the tasks in this topic, you will create a naming template that defines the name for each level in the parent-child hierarchy in the **Employee** dimension.</span></span> <span data-ttu-id="34459-111">Em seguida, o atributo pai deverá ser configurado para ocultar todos os dados pai, de forma que sejam exibidas apenas as informações sobre as vendas de cada membro no nível folha.</span><span class="sxs-lookup"><span data-stu-id="34459-111">You will then configure the parent attribute to hide all parent data, so that only the sales for leaf-level members are displayed.</span></span>

## <a name="browsing-the-employee-dimension"></a><span data-ttu-id="34459-112">Navegando pela dimensão Funcionário</span><span class="sxs-lookup"><span data-stu-id="34459-112">Browsing the Employee Dimension</span></span>

1.  <span data-ttu-id="34459-113">No Gerenciador de Soluções, clique duas vezes em **Employee.dim** na pasta **Dimensões** para abrir o Designer de Dimensão na dimensão Funcionário.</span><span class="sxs-lookup"><span data-stu-id="34459-113">In Solution Explorer, double-click **Employee.dim** in the **Dimensions** folder to open Dimension Designer for the Employee dimension.</span></span>

2.  <span data-ttu-id="34459-114">Clique na guia **Navegador** , verifique se **Funcionários** está selecionado na lista **Hierarquia** e expanda o membro **Todos os Funcionários** .</span><span class="sxs-lookup"><span data-stu-id="34459-114">Click the **Browser** tab, verify that **Employees** is selected in the **Hierarchy** list, and then expand the **All Employees** member.</span></span>

     <span data-ttu-id="34459-115">Observe que **Pedro J. Martins** é o gerente de nível superior nesta hierarquia pai-filho.</span><span class="sxs-lookup"><span data-stu-id="34459-115">Notice that **Ken J. Sánchez** is the top-level manager in this parent-child hierarchy.</span></span>

3.  <span data-ttu-id="34459-116">Selecione o membro **Pedro J. Martins** .</span><span class="sxs-lookup"><span data-stu-id="34459-116">Select the **Ken J. Sánchez** member.</span></span>

     <span data-ttu-id="34459-117">Observe que o nome do nível para esse membro é **Nível 02**.</span><span class="sxs-lookup"><span data-stu-id="34459-117">Notice that the level name for this member is **Level 02**.</span></span> <span data-ttu-id="34459-118">(O nome do nível é exibido depois de **Nível atual:** logo acima do membro **Todos os Funcionários** .) Na próxima tarefa, você definirá nomes mais descritivos para cada nível.</span><span class="sxs-lookup"><span data-stu-id="34459-118">(The level name appears after **Current level:** immediately above the **All Employees** member.) In the next task, you will define more descriptive names for each level.</span></span>

4.  <span data-ttu-id="34459-119">Expanda **Pedro J. Martins** para exibir os nomes de funcionários subordinados a esse gerente e selecione **Vitor S. Barros** para exibir o nome desse nível.</span><span class="sxs-lookup"><span data-stu-id="34459-119">Expand **Ken J. Sánchez** to view the names of the employees who report to this manager, and then select **Brian S. Welcker** to view the name of this level.</span></span>

     <span data-ttu-id="34459-120">Observe que o nome do nível para esse membro é **Nível 03**.</span><span class="sxs-lookup"><span data-stu-id="34459-120">Notice that the level name for this member is **Level 03**.</span></span>

5.  <span data-ttu-id="34459-121">No Gerenciador de Soluções, clique duas vezes em **Analysis Services Tutorial.cube** na pasta **Cubos** para abrir o Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34459-121">In Solution Explorer, double-click **Analysis Services Tutorial.cube** in the **Cubes** folder to open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

6.  <span data-ttu-id="34459-122">Clique na guia **Navegador** .</span><span class="sxs-lookup"><span data-stu-id="34459-122">Click the **Browser** tab.</span></span>

7.  <span data-ttu-id="34459-123">Clique no ícone do Excel e clique em **Habilitar** quando for solicitado para habilitar conexões.</span><span class="sxs-lookup"><span data-stu-id="34459-123">Click the Excel icon, and then click **Enable** when prompted to enable connections.</span></span>

8.  <span data-ttu-id="34459-124">Na Lista de Campos da Tabela Dinâmica, expanda **Reseller Sales**.</span><span class="sxs-lookup"><span data-stu-id="34459-124">In the PivotTable Field List, expand **Reseller Sales**.</span></span> <span data-ttu-id="34459-125">Arraste **Vendas do Revendedor/Valor das Vendas para Valores** até a área Valores.</span><span class="sxs-lookup"><span data-stu-id="34459-125">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

9. <span data-ttu-id="34459-126">Na Lista Campos da Tabela Dinâmica, expanda **Funcionário**e arraste a hierarquia **Funcionários** até a área **Linhas** .</span><span class="sxs-lookup"><span data-stu-id="34459-126">In the PivotTable Field List, expand **Employee**, and then drag the **Employees** hierarchy to the **Rows** area.</span></span>

     <span data-ttu-id="34459-127">Todos os membros da hierarquia Employees são adicionados à coluna A do relatório da Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="34459-127">All the members of the Employees hierarchy are added to column A of the PivotTable report.</span></span>

     <span data-ttu-id="34459-128">A imagem a seguir mostra a hierarquia de Employees expandida.</span><span class="sxs-lookup"><span data-stu-id="34459-128">The following image shows the Employees hierarchy expanded.</span></span>

10. <span data-ttu-id="34459-129">![Tabela dinâmica que mostra a hierarquia Funcionários](../../2014/tutorials/media/l4-employee-1.gif "Tabela dinâmica que mostra a hierarquia Funcionários")</span><span class="sxs-lookup"><span data-stu-id="34459-129">![PivotTable showing Employees hierarchy](../../2014/tutorials/media/l4-employee-1.gif "PivotTable showing Employees hierarchy")</span></span>

     <span data-ttu-id="34459-130">Observe que as vendas de cada gerente no Nível 03 também são exibidas no Nível 04.</span><span class="sxs-lookup"><span data-stu-id="34459-130">Notice that the sales made by each manager in Level 03 are also displayed in Level 04.</span></span> <span data-ttu-id="34459-131">Isso é porque cada gerente também é funcionário de outro gerente.</span><span class="sxs-lookup"><span data-stu-id="34459-131">This is because each manager is also an employee of another manager.</span></span> <span data-ttu-id="34459-132">Na próxima tarefa, você ocultará os valores das vendas.</span><span class="sxs-lookup"><span data-stu-id="34459-132">In the next task, you will hide these sale amounts.</span></span>

## <a name="modifying-parent-attribute-properties-in-the-employee-dimension"></a><span data-ttu-id="34459-133">Modificando as propriedades de atributo pai na dimensão Funcionário</span><span class="sxs-lookup"><span data-stu-id="34459-133">Modifying Parent Attribute Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="34459-134">Mude para o Designer de Dimensão da dimensão **Funcionário** .</span><span class="sxs-lookup"><span data-stu-id="34459-134">Switch to Dimension Designer for the **Employee** dimension.</span></span>

2.  <span data-ttu-id="34459-135">Clique na guia **Estrutura de Dimensão** e selecione uma hierarquia de atributo **Funcionários** no painel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="34459-135">Click the **Dimension Structure** tab, and then select the **Employees** attribute hierarchy in the **Attributes** pane.</span></span>

     <span data-ttu-id="34459-136">Observe que ícone é exclusivo para esse atributo.</span><span class="sxs-lookup"><span data-stu-id="34459-136">Notice the unique icon for this attribute.</span></span> <span data-ttu-id="34459-137">Esse ícone indica que o atributo é a chave pai em uma hierarquia pai-filho.</span><span class="sxs-lookup"><span data-stu-id="34459-137">This icon signifies that the attribute is the parent key in a parent-child hierarchy.</span></span> <span data-ttu-id="34459-138">Observe também, na janela Propriedades, que a propriedade **Usage** do atributo é definida como **Pai**.</span><span class="sxs-lookup"><span data-stu-id="34459-138">Notice also, in the Properties window, that the **Usage** property for the attribute is defined as **Parent**.</span></span> <span data-ttu-id="34459-139">Essa propriedade foi definida pelo Assistente para Dimensões no momento em que a dimensão foi criada.</span><span class="sxs-lookup"><span data-stu-id="34459-139">This property was set by the Dimension Wizard when the dimension was designed.</span></span> <span data-ttu-id="34459-140">O assistente detectou a relação pai-filho automaticamente.</span><span class="sxs-lookup"><span data-stu-id="34459-140">The wizard automatically detected the parent-child relationship.</span></span>

3.  <span data-ttu-id="34459-141">Na janela Propriedades, clique no botão Procurar (**...**) na célula da propriedade **NamingTemplate** .</span><span class="sxs-lookup"><span data-stu-id="34459-141">In the Properties window, click the ellipsis button (**...**) in the **NamingTemplate** property cell.</span></span>

     <span data-ttu-id="34459-142">Na caixa de diálogo **Modelo de Nomeação de Nível** , você define o modelo de nomeação de nível que determina os nomes de nível na hierarquia pai-filho exibidos aos usuários à medida que eles procuram os cubos.</span><span class="sxs-lookup"><span data-stu-id="34459-142">In the **Level Naming Template** dialog box, you define the level naming template that determines the level names in the parent-child hierarchy that are displayed to users as they browse cubes.</span></span>

4.  <span data-ttu-id="34459-143">Na segunda linha, a **\*** linha, digite **nível \* de funcionário** na coluna **nome** e, em seguida, clique na terceira linha.</span><span class="sxs-lookup"><span data-stu-id="34459-143">In the second row, the **\*** row, type **Employee Level \*** in the **Name** column, and then click the third row.</span></span>

     <span data-ttu-id="34459-144">Observe agora que, abaixo de **Resultado** , cada nível é exibido nomeado como “Nível do Funcionário” seguido de números crescentes e consecutivos.</span><span class="sxs-lookup"><span data-stu-id="34459-144">Notice under **Result** that each level will now be named "Employee Level" followed by a sequentially increasing number.</span></span>

     <span data-ttu-id="34459-145">A imagem a seguir mostra as alterações na caixa de diálogo **Modelo de Nomeação de Nível** .</span><span class="sxs-lookup"><span data-stu-id="34459-145">The following image shows the changes in the **Level Naming Template** dialog box.</span></span>

     <span data-ttu-id="34459-146">![Caixa de diálogo modelo de nomeação de nível](../../2014/tutorials/media/l4-namingtemplate.gif "Caixa de diálogo Modelo de Nomeação de Nível")</span><span class="sxs-lookup"><span data-stu-id="34459-146">![Level Naming Template dialog box](../../2014/tutorials/media/l4-namingtemplate.gif "Level Naming Template dialog box")</span></span>

5.  <span data-ttu-id="34459-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="34459-147">Click **OK**.</span></span>

6.  <span data-ttu-id="34459-148">Na janela Propriedades do atributo **Funcionários** , na célula da propriedade **MembersWithData** , selecione **NonLeafDataHidden** para alterar o valor do atributo **Funcionários** .</span><span class="sxs-lookup"><span data-stu-id="34459-148">In the Properties window for the **Employees** attribute, in the **MembersWithData** property cell, select **NonLeafDataHidden** to change this value for the **Employees** attribute.</span></span>

     <span data-ttu-id="34459-149">Isso faz com que os dados relacionados aos membros de nível não folha na hierarquia pai-filho sejam ocultados.</span><span class="sxs-lookup"><span data-stu-id="34459-149">This will cause data that is related to non-leaf level members in the parent-child hierarchy to be hidden.</span></span>

## <a name="browsing-the-employee-dimension-with-the-modified-attributes"></a><span data-ttu-id="34459-150">Navegando pela dimensão Funcionário com atributos modificados</span><span class="sxs-lookup"><span data-stu-id="34459-150">Browsing the Employee Dimension with the Modified Attributes</span></span>

1.  <span data-ttu-id="34459-151">No menu **Compilar** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="34459-151">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="34459-152">Quando a implantação for concluída com êxito, mude para o Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e, na barra de ferramentas da guia **Navegador** , clique em **Reconectar** .</span><span class="sxs-lookup"><span data-stu-id="34459-152">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the toolbar of the **Browser** tab.</span></span>

3.  <span data-ttu-id="34459-153">Clique no ícone do Excel e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="34459-153">Click the Excel icon, and then click **Enable**.</span></span>

4.  <span data-ttu-id="34459-154">Arraste **Vendas do Revendedor/Valor das Vendas para Valores** até a área Valores.</span><span class="sxs-lookup"><span data-stu-id="34459-154">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

5.  <span data-ttu-id="34459-155">Arraste a hierarquia **Funcionários** até a área Rótulos de Linha.</span><span class="sxs-lookup"><span data-stu-id="34459-155">Drag the **Employees** hierarchy to the Row Labels area.</span></span>

     <span data-ttu-id="34459-156">A imagem a seguir mostra as alterações que foram realizadas na hierarquia Funcionários.</span><span class="sxs-lookup"><span data-stu-id="34459-156">The following image shows the changes that you made to the Employees hierarchy.</span></span> <span data-ttu-id="34459-157">Observe que Marcos Y. Azevedo não é exibido mais como um funcionário de si próprio.</span><span class="sxs-lookup"><span data-stu-id="34459-157">Notice that Stephen Y. Jiang no longer appears as an employee of himself.</span></span>

     <span data-ttu-id="34459-158">![Hierarquia Funcionários modificada](../../2014/tutorials/media/l4-employee-2.png "Hierarquia Funcionários modificada")</span><span class="sxs-lookup"><span data-stu-id="34459-158">![Modified Employees hierarchy](../../2014/tutorials/media/l4-employee-2.png "Modified Employees hierarchy")</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="34459-159">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="34459-159">Next Task in Lesson</span></span>
 [<span data-ttu-id="34459-160">Agrupando membros de atributo automaticamente</span><span class="sxs-lookup"><span data-stu-id="34459-160">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)

## <a name="see-also"></a><span data-ttu-id="34459-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34459-161">See Also</span></span>
 <span data-ttu-id="34459-162">Atributos de [hierarquia pai-filho](multidimensional-models/parent-child-dimension.md) [em hierarquias pai-filho](multidimensional-models/parent-child-dimension-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="34459-162">[Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>


