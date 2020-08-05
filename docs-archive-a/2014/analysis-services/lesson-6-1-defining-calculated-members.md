---
title: Definindo membros calculados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 07f13e1c-0b20-4f9e-ad62-c438983f2785
author: minewiskan
ms.author: owend
ms.openlocfilehash: f2a054356613ebf3d4cf825c1fa4c238a5362ec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572789"
---
# <a name="defining-calculated-members"></a><span data-ttu-id="4dcb3-102">Definindo membros calculados</span><span class="sxs-lookup"><span data-stu-id="4dcb3-102">Defining Calculated Members</span></span>
  <span data-ttu-id="4dcb3-103">Membros calculados são membros de uma dimensão ou um grupo de medidas definidos com base em uma combinação de dados de cubo, operadores aritméticos, números e funções.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-103">Calculated members are members of a dimension or a measure group that are defined based on a combination of cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="4dcb3-104">Por exemplo, você pode criar um membro calculado que possa calcular a soma de duas medidas físicas no cubo.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-104">For example, you can create a calculated member that calculates the sum of two physical measures in the cube.</span></span> <span data-ttu-id="4dcb3-105">As definições de um membro calculado são armazenadas em cubos, mas seus valores são calculados no momento da consulta.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-105">Calculated member definitions are stored in cubes, but their values are calculated at query time.</span></span>  
  
 <span data-ttu-id="4dcb3-106">Para criar um membro calculado, use o comando **Novo Membro Calculado** na guia **Cálculos** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-106">To create a calculated member, use the **New Calculated Member** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="4dcb3-107">Um membro calculado pode ser criado em qualquer dimensão, inclusive a dimensão de medidas.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-107">You can create a calculated member within any dimension, including the measures dimension.</span></span> <span data-ttu-id="4dcb3-108">Você também pode colocar um membro calculado dentro de uma pasta de exibição na caixa de diálogo **Propriedades de Cálculo** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-108">You can also place a calculated member within a display folder in the **Calculation Properties** dialog box.</span></span> <span data-ttu-id="4dcb3-109">Para obter mais informações, consulte [Cálculos](multidimensional-models-olap-logical-cube-objects/calculations.md), [Cálculos em modelos multidimensionais](multidimensional-models/calculations-in-multidimensional-models.md), e [Criar membros calculados](multidimensional-models/create-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="4dcb3-109">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), [Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md), and [Create Calculated Members](multidimensional-models/create-calculated-members.md).</span></span>  
  
 <span data-ttu-id="4dcb3-110">Nas tarefas deste tópico, você definirá as medidas calculadas para permitir que os usuários visualizem o percentual da margem de lucro bruto e as taxas de vendas das vendas pela Internet, vendas do revendedor e de todas as vendas.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-110">In the tasks in this topic, you define calculated measures to let users view the gross profit margin percentage and sales ratios for Internet sales, reseller sales, and for all sales.</span></span>  
  
## <a name="defining-calculations-to-aggregate-physical-measures"></a><span data-ttu-id="4dcb3-111">Definindo cálculos para agregar medidas físicas</span><span class="sxs-lookup"><span data-stu-id="4dcb3-111">Defining Calculations to Aggregate Physical Measures</span></span>  
  
1.  <span data-ttu-id="4dcb3-112">Abra o Designer de Cubo para o cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique na guia **Cálculos** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-112">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="4dcb3-113">Observe o comando padrão CALCULATE no painel **Expressões de Cálculos** e no painel **Organizador de Script** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-113">Notice the default CALCULATE command in the **Calculation Expressions** pane and in the **Script Organizer** pane.</span></span> <span data-ttu-id="4dcb3-114">Esse comando especifica que a medida no cubo deve ser agregada de acordo com o valor especificado por suas propriedades AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-114">This command specifies that the measures in the cube should be aggregated according to the value that is specified by their AggregateFunction properties.</span></span> <span data-ttu-id="4dcb3-115">Geralmente, os valores de medida são somados, mas também podem ser contados ou agregados em alguma outra forma.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-115">Measure values are generally summed, but may also be counted or aggregated in some other manner.</span></span>  
  
     <span data-ttu-id="4dcb3-116">A imagem a seguir mostra a guia **Cálculos** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-116">The following image shows the **Calculations** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="4dcb3-117">![Guia Cálculos do Designer de Cubo](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Guia Cálculos do Designer de Cubo")</span><span class="sxs-lookup"><span data-stu-id="4dcb3-117">![Calculations tab of Cube Designer](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Calculations tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="4dcb3-118">Na barra de ferramentas da guia **Cálculos** , clique em **Novo Membro Calculado**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-118">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="4dcb3-119">Um novo formulário aparece no painel **Expressões de Cálculos** no qual foram definidas as propriedades desse novo membro calculado.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-119">A new form appears in the **Calculation Expressions** pane within which you define the properties of this new calculated member.</span></span> <span data-ttu-id="4dcb3-120">O novo membro também aparece no painel **Organizador de Script** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-120">The new member also appears in the **Script Organizer** pane.</span></span>  
  
     <span data-ttu-id="4dcb3-121">A imagem a seguir mostra o formulário que aparece no painel **Expressões de Cálculos** quando você clica em **Novo Membro Calculado**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-121">The following image shows the form that appears in the **Calculation Expressions** pane when you click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="4dcb3-122">![Formulário de painel Expressões de Cálculo](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Formulário de painel Expressões de Cálculo")</span><span class="sxs-lookup"><span data-stu-id="4dcb3-122">![Calculation Expressions pane form](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Calculation Expressions pane form")</span></span>  
  
3.  <span data-ttu-id="4dcb3-123">Na caixa **nome** , altere o nome da medida calculada para `[Total Sales Amount]` .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-123">In the **Name** box, change the name of the calculated measure to `[Total Sales Amount]`.</span></span>  
  
     <span data-ttu-id="4dcb3-124">Se o nome de um membro calculado tiver algum espaço, ele deverá ser colocado entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-124">If the name of a calculated member contains a space, the calculated member name must be enclosed in square brackets.</span></span>  
  
     <span data-ttu-id="4dcb3-125">Observe na lista **Hierarquia pai** que, por padrão, um novo membro calculado é criado na dimensão **Medidas** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-125">Notice in the **Parent hierarchy** list that, by default, a new calculated member is created in the **Measures** dimension.</span></span> <span data-ttu-id="4dcb3-126">Um membro calculado na dimensão Medidas também é conhecido como uma medida calculada.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-126">A calculated member in the Measures dimension is also frequently called a calculated measure.</span></span>  
  
4.  <span data-ttu-id="4dcb3-127">Na guia **Metadados** no painel **Ferramentas de Cálculo** da guia **Cálculos** , expanda **Medidas** e **Vendas pela Internet** para exibir os metadados do grupo de medidas **Vendas pela Internet** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-127">On the **Metadata** tab in the **Calculation Tools** pane of the **Calculations** tab, expand **Measures** and then expand **Internet Sales** to view the metadata for the **Internet Sales** measure group.</span></span>  
  
     <span data-ttu-id="4dcb3-128">Você pode arrastar os elementos de metadados do painel **Ferramentas de Cálculo** até a caixa **Expressão** e adicione operadores e outros elementos para criar expressões MDX.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-128">You can drag metadata elements from the **Calculation Tools** pane into the **Expression** box and then add operators and other elements to create Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="4dcb3-129">Como alternativa, é possível digitar uma expressão MDX diretamente na caixa **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-129">Alternatively, you can type the MDX expression directly into the **Expression** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4dcb3-130">Se não houver nenhum metadados no painel **Ferramentas de Cálculo** , clique em **Reconectar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-130">If you cannot view any metadata in the **Calculation Tools** pane, click **Reconnect** on the toolbar.</span></span> <span data-ttu-id="4dcb3-131">Se isso não funcionar, talvez seja preciso processar o cubo ou iniciar a instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dcb3-131">If this does not work, you may have to process the cube or start the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="4dcb3-132">Arraste **Vendas pela Internet/Valor das Vendas** da guia **Metadados** no painel **Ferramentas de Cálculo** até a caixa **Expressão** no painel **Expressões de Cálculo** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-132">Drag **Internet Sales-Sales Amount** from the **Metadata** tab in the **Calculation Tools** pane into the **Expression** box in the **Calculation Expressions** pane.</span></span>  
  
6.  <span data-ttu-id="4dcb3-133">Na caixa **Expressão** , digite um sinal de adição (`+`) depois de **[Medidas].[Vendas pela Internet/Valor das Vendas]**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-133">In the **Expression** box, type a plus sign (`+`) after **[Measures].[Internet Sales-Sales Amount]**.</span></span>  
  
7.  <span data-ttu-id="4dcb3-134">Na guia **Metadados** do painel **Ferramentas de Cálculo** , expanda **Vendas do Revendedor**e arraste **Vendas do Revendedor/Valor das Vendas** até a caixa **Expressão** no painel **Expressões de Cálculos** após o sinal de adição (+).</span><span class="sxs-lookup"><span data-stu-id="4dcb3-134">On the **Metadata** tab in the **Calculation Tools** pane, expand **Reseller Sales**, and then drag **Reseller Sales-Sales Amount** into the **Expression** box in the **Calculation Expressions** pane after the plus sign (+).</span></span>  
  
8.  <span data-ttu-id="4dcb3-135">Na lista **cadeia de caracteres de formato** , selecione **"moeda".**</span><span class="sxs-lookup"><span data-stu-id="4dcb3-135">In the **Format string** list, select **"Currency".**</span></span>  
  
9. <span data-ttu-id="4dcb3-136">Na lista **Comportamento Não Vazio** , marque as caixas de seleção **Vendas pela Internet/Valor das Vendas** e **Vendas do Revendedor/Valor das Vendas**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-136">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4dcb3-137">As medidas especificadas na lista **Comportamento não vazio** serão usadas para resolver consultas NON EMPTY no MDX.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-137">The measures you specify in the **Non-empty behavior** list are used to resolve NON EMPTY queries in MDX.</span></span> <span data-ttu-id="4dcb3-138">Ao especificar uma ou mais medidas na lista **Comportamento não vazio** , o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] tratará o membro calculado como vazio se todas as medidas especificadas estiverem vazias.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-138">When you specify one or more measures in the **Non-empty behavior** list, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] treats the calculated member as empty if all the specified measures are empty.</span></span> <span data-ttu-id="4dcb3-139">Se a propriedade **Comportamento não vazio** estiver em branco, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] deverá avaliar o membro calculado para determinar se o membro está vazio.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-139">If the **Non-empty behavior** property is blank, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] must evaluate the calculated member itself to determine whether the member is empty.</span></span>  
  
     <span data-ttu-id="4dcb3-140">A imagem a seguir mostra o painel **Expressões de Cálculos** preenchido com as configurações que você especificou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-140">The following image shows the **Calculation Expressions** pane populated with the settings that you specified in the previous steps.</span></span>  
  
     <span data-ttu-id="4dcb3-141">![Painel Expressões de Cálculo populado](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Painel Expressões de Cálculo populado")</span><span class="sxs-lookup"><span data-stu-id="4dcb3-141">![Populated Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Populated Calculation Expressions pane")</span></span>  
  
10. <span data-ttu-id="4dcb3-142">Na barra de ferramentas da guia **Cálculos** , clique em **Exibição de Script**e verifique o script de cálculo no painel **Expressões de Cálculos** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-142">On the toolbar of the **Calculations** tab, click **Script View**, and then review the calculation script in the **Calculation Expressions** pane.</span></span>  
  
     <span data-ttu-id="4dcb3-143">Observe que o novo cálculo é adicionado à expressão CALCULATE inicial; cada cálculo individual é separado por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-143">Notice that the new calculation is added to the initial CALCULATE expression; each individual calculation is separated by a semicolon.</span></span> <span data-ttu-id="4dcb3-144">Observe também que é exibido um comentário no começo do script de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-144">Notice also that a comment appears at the beginning of the calculation script.</span></span> <span data-ttu-id="4dcb3-145">Adicionar comentários a um script de cálculo em grupos de cálculos é uma boa prática para ajudar você e outros desenvolvedores a compreenderem os scripts de cálculos complexos.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-145">Adding comments within the calculation script for groups of calculations is a good practice, to help you and other developers understand complex calculation scripts.</span></span>  
  
11. <span data-ttu-id="4dcb3-146">Adicione uma nova linha ao script de cálculo após o comando **Calculate;** e antes do script de cálculo adicionado recentemente. Em seguida, adicione o seguinte texto ao script, na própria linha:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-146">Add a new line in the calculation script after the **Calculate;** command and before the newly added calculation script, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to aggregate Internet Sales and Reseller Sales measures */  
    ```  
  
     <span data-ttu-id="4dcb3-147">A imagem a seguir mostra como os scripts de cálculos devem ser exibidos no painel **Expressões de Cálculos** neste ponto do tutorial.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-147">The following image shows the calculation scripts as they should appear in the **Calculation Expressions** pane at this point in the tutorial.</span></span>  
  
     <span data-ttu-id="4dcb3-148">![Scripts no painel Expressões de Cálculo](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts no painel Expressões de Cálculo")</span><span class="sxs-lookup"><span data-stu-id="4dcb3-148">![Scripts in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts in Calculation Expressions pane")</span></span>  
  
12. <span data-ttu-id="4dcb3-149">Na barra de ferramentas da guia **cálculos** , clique em **exibição de formulário**, verifique se `[Total Sales Amount]` está selecionado no painel **organizador de script** e clique em **novo membro calculado**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-149">On the toolbar of the **Calculations** tab, click **Form View**, verify that `[Total Sales Amount]` is selected in the **Script Organizer** pane, and then click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="4dcb3-150">Altere o nome desse novo membro calculado para `[Total Product Cost]` e, em seguida, crie a seguinte expressão na caixa **expressão** :</span><span class="sxs-lookup"><span data-stu-id="4dcb3-150">Change the name of this new calculated member to `[Total Product Cost]`, and then create the following expression in the **Expression** box:</span></span>  
  
    ```  
    [Measures].[Internet Sales-Total Product Cost] + [Measures].[Reseller Sales-Total Product Cost]  
    ```  
  
14. <span data-ttu-id="4dcb3-151">Na lista **Cadeia de caracteres de formato** , selecione **"Moeda"**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-151">In the **Format string** list, select **"Currency"**.</span></span>  
  
15. <span data-ttu-id="4dcb3-152">Na lista **Comportamento não vazio** , marque as caixas de seleção **Vendas pela Internet-Custo Total do Produto** e **Vendas do Revendedor-Custo Total do Produto**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-152">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Total Product Cost** and **Reseller Sales-Total Product Cost**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4dcb3-153">Agora estão definidos dois membros calculados, ambos visíveis no painel **Organizador de Script** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-153">You have now defined two calculated members, both of which are visible in the **Script Organizer** pane.</span></span> <span data-ttu-id="4dcb3-154">Esses membros calculados podem ser usados por outros cálculos que são definidos posteriormente no script de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-154">These calculated members can be used by other calculations that you define later in the calculation script.</span></span> <span data-ttu-id="4dcb3-155">É possível exibir a definição de qualquer membro calculado selecionando-o no painel **Organizador de Script** . A definição do membro calculado será exibida no painel **Expressões de Cálculos** na exibição Formulário.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-155">You can view the definition of any calculated member by selecting the calculated member in the **Script Organizer** pane; the definition of the calculated member will appear in the **Calculation Expressions** pane in the Form view.</span></span> <span data-ttu-id="4dcb3-156">Os membros calculados definidos recentemente não serão exibidos no painel **Ferramentas de Cálculo** enquanto esses objetos não forem implantados.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-156">Newly defined calculated members will not appear in the **Calculation Tools** pane until these objects have been deployed.</span></span> <span data-ttu-id="4dcb3-157">Os cálculos não exigem processamento.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-157">Calculations do not require processing.</span></span>  
  
## <a name="defining-gross-profit-margin-calculations"></a><span data-ttu-id="4dcb3-158">Definindo cálculos de margem de lucro bruto</span><span class="sxs-lookup"><span data-stu-id="4dcb3-158">Defining Gross Profit Margin Calculations</span></span>  
  
1.  <span data-ttu-id="4dcb3-159">Verifique se `[Total Product Cost]` está selecionado no painel **organizador de script** e, em seguida, clique em **novo membro calculado** na barra de ferramentas da guia **cálculos** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-159">Verify that `[Total Product Cost]` is selected in the **Script Organizer** pane, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
2.  <span data-ttu-id="4dcb3-160">Na caixa **nome** , altere o nome dessa nova medida calculada para `[Internet GPM]` .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-160">In the **Name** box, change the name of this new calculated measure to `[Internet GPM]`.</span></span>  
  
3.  <span data-ttu-id="4dcb3-161">Na caixa **Expressão** , crie a seguinte expressão MDX:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-161">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Internet Sales-Sales Amount] -   
    [Measures].[Internet Sales-Total Product Cost]) /  
    [Measures].[Internet Sales-Sales Amount]  
    ```  
  
4.  <span data-ttu-id="4dcb3-162">Na lista **Cadeia de caracteres de formato** , selecione **"Porcentagem"**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-162">In the **Format string** list, select **"Percent"**.</span></span>  
  
5.  <span data-ttu-id="4dcb3-163">Na lista **Comportamento Não Vazio** , marque a caixa de seleção **Vendas pela Internet/Valor das Vendas**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-163">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="4dcb3-164">Na barra de ferramentas da guia **Cálculos** , clique em **Novo Membro Calculado**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-164">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
7.  <span data-ttu-id="4dcb3-165">Na caixa **nome** , altere o nome dessa nova medida calculada para `[Reseller GPM]` .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-165">In the **Name** box, change the name of this new calculated measure to `[Reseller GPM]`.</span></span>  
  
8.  <span data-ttu-id="4dcb3-166">Na caixa **Expressão** , crie a seguinte expressão MDX:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-166">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Reseller Sales-Sales Amount] -   
    [Measures].[Reseller Sales-Total Product Cost]) /  
    [Measures].[Reseller Sales-Sales Amount]  
    ```  
  
9. <span data-ttu-id="4dcb3-167">Na lista **Cadeia de caracteres de formato** , selecione **"Porcentagem"**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-167">In the **Format string** list, select **"Percent"**.</span></span>  
  
10. <span data-ttu-id="4dcb3-168">Na lista **Comportamento Não Vazio** , marque a caixa de seleção **Vendas do Revendedor/Valor das Vendas**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-168">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="4dcb3-169">Na barra de ferramentas da guia **Cálculos** , clique em **Novo Membro Calculado**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-169">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
12. <span data-ttu-id="4dcb3-170">Na caixa **nome** , altere o nome dessa medida calculada para `[Total GPM]` .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-170">In the **Name** box, change the name of this calculated measure to `[Total GPM]`.</span></span>  
  
13. <span data-ttu-id="4dcb3-171">Na caixa **Expressão** , crie a seguinte expressão MDX:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-171">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Total Sales Amount] -   
    [Measures].[Total Product Cost]) /  
    [Measures].[Total Sales Amount]  
    ```  
  
     <span data-ttu-id="4dcb3-172">Observe que esse membro calculado faz referência a outros membros calculados.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-172">Notice that this calculated member is referencing other calculated members.</span></span> <span data-ttu-id="4dcb3-173">Como esse membro calculado será calculado após os membros aos quais ele faz referência, trata-se de um membro calculado válido.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-173">Because this calculated member will be calculated after the calculated members that it references, this is a valid calculated member.</span></span>  
  
14. <span data-ttu-id="4dcb3-174">Na lista **Cadeia de caracteres de formato** , selecione **"Porcentagem"**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-174">In the **Format string** list, select **"Percent"**.</span></span>  
  
15. <span data-ttu-id="4dcb3-175">Na lista **Comportamento Não Vazio** , marque as caixas de seleção **Vendas pela Internet/Valor das Vendas** e **Vendas do Revendedor/Valor das Vendas**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-175">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="4dcb3-176">Na barra de ferramentas da guia **Cálculos** , clique em **Exibição de Script** e verifique os três cálculos que foram adicionados ao script de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-176">On the toolbar of the **Calculations** tab, click **Script View** and review the three calculations you just added to the calculation script.</span></span>  
  
17. <span data-ttu-id="4dcb3-177">Adicione uma nova linha no script de cálculo imediatamente antes do `[Internet GPM]` cálculo e, em seguida, adicione o seguinte texto ao script em sua própria linha:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-177">Add a new line in the calculation script immediately before the `[Internet GPM]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate gross profit margin */  
    ```  
  
     <span data-ttu-id="4dcb3-178">A imagem a seguir mostra o painel **Expressões** com os três novos cálculos.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-178">The following image shows the **Expressions** pane with the three new calculations.</span></span>  
  
     <span data-ttu-id="4dcb3-179">![Novos cálculos no painel Expressões de Cálculo](../../2014/tutorials/media/l6-calculatedmembers-05.gif "Novos cálculos no painel Expressões de Cálculo")</span><span class="sxs-lookup"><span data-stu-id="4dcb3-179">![New calculations in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-05.gif "New calculations in Calculation Expressions pane")</span></span>  
  
## <a name="defining-the-percent-of-total-calculations"></a><span data-ttu-id="4dcb3-180">Definindo o percentual de cálculos totais</span><span class="sxs-lookup"><span data-stu-id="4dcb3-180">Defining the Percent of Total Calculations</span></span>  
  
1.  <span data-ttu-id="4dcb3-181">Na barra de ferramentas da guia **Cálculos** , clique em **Exibição de Formulário**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-181">On the toolbar of the **Calculations** tab, click **Form View**.</span></span>  
  
2.  <span data-ttu-id="4dcb3-182">No painel **organizador de script** , selecione `[Total GPM]` e, em seguida, clique em **novo membro calculado** na barra de ferramentas da guia **cálculos** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-182">In the **Script Organizer** pane, select `[Total GPM]`, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="4dcb3-183">Se você clicar no membro calculado final no painel **Organizador de Script** antes de clicar em **Novo Membro Calculado** , o novo membro calculado será inserido no final do script.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-183">Clicking the final calculated member in the **Script Organizer** pane before you click **New Calculated Member** guarantees that the new calculated member will be entered at the end of the script.</span></span> <span data-ttu-id="4dcb3-184">Os scripts são executados na ordem em que aparecem no painel **Organizador de Script** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-184">Scripts execute in the order that they appear in the **Script Organizer** pane.</span></span>  
  
3.  <span data-ttu-id="4dcb3-185">Altere o nome desse novo membro calculado para `[Internet Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-185">Change the name of this new calculated member to `[Internet Sales Ratio to All Products]`.</span></span>  
  
4.  <span data-ttu-id="4dcb3-186">Na caixa **Expressão** , digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-186">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Internet Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Internet Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Internet Sales-Sales Amount] )  
        End  
    ```  
  
     <span data-ttu-id="4dcb3-187">Essa expressão MDX calcula a contribuição para totalizar as vendas pela Internet de cada produto.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-187">This MDX expression calculates the contribution to total Internet sales of each product.</span></span> <span data-ttu-id="4dcb3-188">A instrução Case junto com a função IS EMPTY garante que não ocorra um erro de divisão por zero quando um produto não for vendido.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-188">The Case statement together with the IS EMPTY function ensures that a divide by zero error does not occur when a product has no sales.</span></span>  
  
5.  <span data-ttu-id="4dcb3-189">Na lista **Cadeia de caracteres de formato** , selecione **"Porcentagem"**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-189">In the **Format string** list, select **"Percent"**.</span></span>  
  
6.  <span data-ttu-id="4dcb3-190">Na lista **Comportamento Não Vazio** , marque a caixa de seleção **Vendas pela Internet/Valor das Vendas**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-190">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="4dcb3-191">Na barra de ferramentas da guia **Cálculos** , clique em **Novo Membro Calculado**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-191">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
8.  <span data-ttu-id="4dcb3-192">Altere o nome deste membro calculado para `[Reseller Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-192">Change the name of this calculated member to `[Reseller Sales Ratio to All Products]`.</span></span>  
  
9. <span data-ttu-id="4dcb3-193">Na caixa **Expressão** , digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-193">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Reseller Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Reseller Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Reseller Sales-Sales Amount] )  
        End  
    ```  
  
10. <span data-ttu-id="4dcb3-194">Na lista **Cadeia de caracteres de formato** , selecione **"Porcentagem"**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-194">In the **Format string** list, select **"Percent"**.</span></span>  
  
11. <span data-ttu-id="4dcb3-195">Na lista **Comportamento Não Vazio** , marque a caixa de seleção **Vendas do Revendedor/Valor das Vendas**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-195">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="4dcb3-196">Na barra de ferramentas da guia **Cálculos** , clique em **Novo Membro Calculado**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-196">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="4dcb3-197">Altere o nome deste membro calculado para `[Total Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-197">Change the name of this calculated member to `[Total Sales Ratio to All Products]`.</span></span>  
  
14. <span data-ttu-id="4dcb3-198">Na caixa **Expressão** , digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-198">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Total Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Total Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Total Sales Amount] )  
        End  
    ```  
  
15. <span data-ttu-id="4dcb3-199">Na lista **Cadeia de caracteres de formato** , selecione **"Porcentagem"**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-199">In the **Format string** list, select **"Percent"**.</span></span>  
  
16. <span data-ttu-id="4dcb3-200">Na lista **Comportamento Não Vazio** , marque as caixas de seleção **Vendas pela Internet/Valor das Vendas** e **Vendas do Revendedor/Valor das Vendas**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-200">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="4dcb3-201">Na barra de ferramentas da guia **Cálculos** , clique em **Exibição de Script**e verifique os três cálculos que foram adicionados ao script de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-201">On the toolbar of the **Calculations** tab, click **Script View**, and then review the three calculations that you just added to the calculation script.</span></span>  
  
18. <span data-ttu-id="4dcb3-202">Adicione uma nova linha no script de cálculo imediatamente antes do `[Internet Sales Ratio to All Products]` cálculo e, em seguida, adicione o seguinte texto ao script em sua própria linha:</span><span class="sxs-lookup"><span data-stu-id="4dcb3-202">Add a new line in the calculation script immediately before the `[Internet Sales Ratio to All Products]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate percentage of product to total product sales */  
    ```  
  
     <span data-ttu-id="4dcb3-203">Agora estão definidos oito membros calculados e todos eles estarão visíveis no painel **Organizador de Script** quando você estiver na exibição Formulário.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-203">You have now defined a total of eight calculated members, which are visible in the **Script Organizer** pane when you are in Form view.</span></span>  
  
## <a name="browsing-the-new-calculated-members"></a><span data-ttu-id="4dcb3-204">Navegando pelos novos membros calculados</span><span class="sxs-lookup"><span data-stu-id="4dcb3-204">Browsing the New Calculated Members</span></span>  
  
1.  <span data-ttu-id="4dcb3-205">No menu **Compilar** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-205">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="4dcb3-206">Quando a implantação tiver sido concluída com êxito, alterne para a guia **Navegador** e clique no botão **Reconectar**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-206">When deployment has successfully completed, switch to the **Browser** tab, click **Reconnect**.</span></span>  
  
3.  <span data-ttu-id="4dcb3-207">Clique no ícone do Excel e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-207">Click the Excel icon, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="4dcb3-208">No painel **Lista de Campos da Tabela Dinâmica** , expanda a pasta **Valores** para exibir os novos membros calculados na dimensão Medidas.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-208">In the **PivotTable Field List** pane, expand **Values** folder to view the new calculated members in the Measures dimension.</span></span>  
  
5.  <span data-ttu-id="4dcb3-209">Arraste o **Valor de Vendas Total** , para a área de Valores e analise os resultados.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-209">Drag the **Total Sales Amount** to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="4dcb3-210">Arraste as medidas **Vendas pela Internet/Valor das Vendas** e **Vendas do Revendedor/Valor das Vendas** dos grupos de medidas **Vendas pela Internet** e **Vendas de revendedor** até a área Valores.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-210">Drag **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount** measures from the **Internet Sales** and **Reseller Sales** measure groups to the Values area.</span></span>  
  
     <span data-ttu-id="4dcb3-211">Observe que a medida **Valor de Vendas Total** é a soma da medida **Vendas pela Internet/Valor das Vendas** e da medida **Vendas do Revendedor/Valor das Vendas** .</span><span class="sxs-lookup"><span data-stu-id="4dcb3-211">Notice that the **Total Sales Amount** measure is the sum of the **Internet Sales-Sales Amount** measure and the **Reseller Sales-Sales Amount** measure.</span></span>  
  
6.  <span data-ttu-id="4dcb3-212">Adicione a hierarquia definida pelo usuário **Categorias do Produto** à área de filtros da área **Filtro de Relatório** e filtre os dados por **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-212">Add the **Product Categories** user-defined hierarchy to the filter area of the **Report Filter** area, and then filter the data by **Mountain Bikes**.</span></span>  
  
     <span data-ttu-id="4dcb3-213">Observe que a medida **Valor de Vendas Total** é calculada para a categoria **Mountain Bikes** de vendas do produto com base nas medidas **Vendas pela Internet/Valor das Vendas** e **Vendas do Revendedor/Valor das Vendas** para **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-213">Notice that the **Total Sales Amount** measure is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
7.  <span data-ttu-id="4dcb3-214">Adicione a hierarquia definida pelo usuário **Date.Calendar Date** à área de rótulos de linhas e examine os resultados.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-214">Add the **Date.Calendar Date** user-defined hierarchy to the Row labels area, and then review the results.</span></span>  
  
     <span data-ttu-id="4dcb3-215">Observe que a medida **Valor de Vendas Total** para cada no civil é calculada para a categoria **Mountain Bikes** de vendas do produto com base nas medidas **Vendas pela Internet/Valor das Vendas** e **Vendas do Revendedor/Valor das Vendas** para **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-215">Notice that the **Total Sales Amount** measure for each calendar year is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
8.  <span data-ttu-id="4dcb3-216">Adicione as medidas **MLB Total**, **MLB pela Internet**e **MLB do Revendedor** à área de Valores e analise os resultados.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-216">Add the **Total GPM**, **Internet GPM**, and **Reseller GPM** measures to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="4dcb3-217">Observe que a margem de lucro bruto das vendas do revendedor é significativamente mais baixa que as vendas pela Internet, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-217">Notice that the gross profit margin for reseller sales is significantly lower than for sales over the Internet, as shown in the following image.</span></span>  
  
     <span data-ttu-id="4dcb3-218">![Painel Dados que mostra as vendas do revendedor](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Painel Dados que mostra as vendas do revendedor")</span><span class="sxs-lookup"><span data-stu-id="4dcb3-218">![Data pane showing reseller sales](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Data pane showing reseller sales")</span></span>  
  
9. <span data-ttu-id="4dcb3-219">Adicione as medidas **Taxa de Vendas Total para Todos os Produtos**, **Taxa de Vendas pela Internet para Todos os Produtos**e **Taxa de Vendas do Revendedor para Todos os Produtos** à área de Valores.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-219">Add the **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**, and **Reseller Sales Ratio to All Products** measures to the Values area.</span></span>  
  
     <span data-ttu-id="4dcb3-220">Observe que, com o passar do tempo, a taxa de vendas de Mountain Bikes para todos os produtos aumentou com relação às vendas pela Internet, mas reduziu com relação às vendas do revendedor.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-220">Notice that the ratio of the sales of mountain bikes to all products has increased over time for Internet sales, but is decreasing over time for reseller sales.</span></span> <span data-ttu-id="4dcb3-221">Observe também que a taxa de vendas de Mountain Bikes para todos os produtos é mais baixa a partir das vendas do revendedor do que as vendas pela Internet.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-221">Notice also that the ratio of the sale of mountain bikes to all products is lower from sales through resellers than it is for sales over the Internet.</span></span>  
  
10. <span data-ttu-id="4dcb3-222">Altere o filtro de **Mountain Bikes** para **Bikes**e analise os resultados.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-222">Change the filter from **Mountain Bikes** to **Bikes**, and review the results.</span></span>  
  
     <span data-ttu-id="4dcb3-223">Observe que a margem de lucro bruto para todas as bicicletas vendidas pelos revendedores é negativa, pois as bicicletas de passeio e de competição estão sendo vendidas com prejuízos.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-223">Notice that the gross profit margin for all bikes sold through resellers is negative, because touring bikes and road bikes are being sold at a loss.</span></span>  
  
11. <span data-ttu-id="4dcb3-224">Altere o filtro para **Acessórios**e analise os resultados.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-224">Change the filter to **Accessories**, and then review the results.</span></span>  
  
     <span data-ttu-id="4dcb3-225">Observe que a venda de acessórios aumentou com o passar do tempo, mas essas vendas equivalem a apenas uma pequena fração do total de vendas.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-225">Notice that the sale of accessories is increasing over time, but that these sales make up only a small fraction of total sales.</span></span> <span data-ttu-id="4dcb3-226">Observe também que a margem de lucro bruto de vendas de acessórios é mais alta do que a de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="4dcb3-226">Notice also that the gross profit margin for sales of accessories is higher than for bikes.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4dcb3-227">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="4dcb3-227">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4dcb3-228">Definindo conjuntos nomeados</span><span class="sxs-lookup"><span data-stu-id="4dcb3-228">Defining Named Sets</span></span>](lesson-6-2-defining-named-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="4dcb3-229">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4dcb3-229">See Also</span></span>  
 <span data-ttu-id="4dcb3-230">[Cálculos](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="4dcb3-230">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="4dcb3-231">[Cálculos em modelos multidimensionais](multidimensional-models/calculations-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="4dcb3-231">[Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="4dcb3-232">Criar membros calculados</span><span class="sxs-lookup"><span data-stu-id="4dcb3-232">Create Calculated Members</span></span>](multidimensional-models/create-calculated-members.md)  
  
  
