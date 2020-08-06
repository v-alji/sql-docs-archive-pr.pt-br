---
title: Definindo e procurando perspectivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 766004b9-6578-4914-a445-6f44843a5fb0
author: minewiskan
ms.author: owend
ms.openlocfilehash: c9658098180618c2d5d6d6d9e00e7a7e4a6c4231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681890"
---
# <a name="defining-and-browsing-perspectives"></a><span data-ttu-id="f6b6a-102">Definindo e procurando perspectivas</span><span class="sxs-lookup"><span data-stu-id="f6b6a-102">Defining and Browsing Perspectives</span></span>
  <span data-ttu-id="f6b6a-103">Uma perspectiva pode simplificar a exibição de um cubo para propósitos específicos.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-103">A perspective can simplify the view of a cube for specific purposes.</span></span> <span data-ttu-id="f6b6a-104">Por padrão, os usuários podem ver todos os elementos em um cubo para o qual têm permissões.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-104">By default, users can see all of the elements in a cube to which they have permissions.</span></span> <span data-ttu-id="f6b6a-105">O quê os usuários visualizam ao exibir um cubo completo do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] é a perspectiva padrão para o cubo.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-105">What users are viewing when they view an entire [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube is the default perspective for the cube.</span></span> <span data-ttu-id="f6b6a-106">Uma exibição de todo o cubo pode ser muito complexa para os usuários pesquisarem, principalmente para usuários que precisam apenas interagir com uma pequena parte do cubo para satisfazer seus requisitos de inteligência empresarial e geração de relatórios.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-106">A view of the whole cube can be very complex for users to navigate, especially for users who only need to interact with a small part of the cube to satisfy their business intelligence and reporting requirements.</span></span>  
  
 <span data-ttu-id="f6b6a-107">Para reduzir a aparente complexidade de um cubo, você pode criar subconjuntos visíveis do cubo, chamados *perspectivas*, que mostram aos usuários somente uma parte dos grupos de medidas, medidas, dimensões, atributos, hierarquias, KPIs (Indicadores Chave de Desempenho), ações e membros calculados no cubo.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-107">To reduce the apparent complexity of a cube, you can create viewable subsets of the cube, called *perspectives*, which show users only a part of the measure groups, measures, dimensions, attributes, hierarchies, Key Performance Indicators (KPIs), actions, and calculated members in the cube.</span></span> <span data-ttu-id="f6b6a-108">Isso pode ser particularmente útil para trabalhar com aplicativos cliente que foram escritos em uma versão anterior do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6b6a-108">This can be particularly useful for working with client applications that were written for a previous release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f6b6a-109">Esses clientes não têm conceito de exibição de pastas ou perspectivas, por exemplo, mas uma perspectiva é exibida para clientes antigos como se fosse um cubo.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-109">These clients have no concept of display folders or perspectives, for example, but a perspective appears to older clients as if it were a cube.</span></span> <span data-ttu-id="f6b6a-110">Para obter mais informações, consulte [Perspectivas](multidimensional-models-olap-logical-cube-objects/perspectives.md)e [Perspectivas em modelos multidimensionais](multidimensional-models/perspectives-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="f6b6a-110">For more information, see [Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md), and [Perspectives in Multidimensional Models](multidimensional-models/perspectives-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6b6a-111">Uma perspectiva não é um mecanismo de segurança; é na verdade uma ferramenta que fornece uma experiência melhor ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-111">A perspective is not a security mechanism, but instead is a tool for providing a better user experience.</span></span> <span data-ttu-id="f6b6a-112">Toda a segurança de uma perspectiva é herdada do cubo subjacente.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-112">All security for a perspective is inherited from the underlying cube.</span></span>  
  
 <span data-ttu-id="f6b6a-113">Nas tarefas deste tópico, você definirá várias perspectivas diferentes e depois navegará no cubo usando essas novas perspectivas.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-113">In the tasks in this topic, you will define several different perspectives and then browse the cube through each of these new perspectives.</span></span>  
  
## <a name="defining-an-internet-sales-perspective"></a><span data-ttu-id="f6b6a-114">Definindo uma perspectiva Vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="f6b6a-114">Defining an Internet Sales Perspective</span></span>  
  
1.  <span data-ttu-id="f6b6a-115">Abra o Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e clique na guia **Perspectivas** .</span><span class="sxs-lookup"><span data-stu-id="f6b6a-115">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Perspectives** tab.</span></span>  
  
     <span data-ttu-id="f6b6a-116">Todos os objetos e seus tipos de objeto são exibidos no painel **Perspectivas** , como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-116">All the objects and their object types appear in the **Perspectives** pane, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f6b6a-117">![Painel Perspectivas do Designer de Cubo](../../2014/tutorials/media/l9-perspectives-1.gif "Painel Perspectivas do Designer de Cubo")</span><span class="sxs-lookup"><span data-stu-id="f6b6a-117">![Perspectives pane of Cube Designer](../../2014/tutorials/media/l9-perspectives-1.gif "Perspectives pane of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="f6b6a-118">Na barra de ferramentas da guia **Perspectivas** , clique no botão **Nova Perspectiva** .</span><span class="sxs-lookup"><span data-stu-id="f6b6a-118">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
     <span data-ttu-id="f6b6a-119">Uma nova perspectiva é exibida na coluna **Nome da Perspectiva** com o nome padrão **Perspectiva**, como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-119">A new perspective appears in the **Perspective Name** column with a default name of **Perspective**, as shown in the following image.</span></span> <span data-ttu-id="f6b6a-120">Observe que a caixa de seleção de cada objeto está selecionada. Até que você desmarque a caixa de seleção de um objeto, essa perspectiva é idêntica à perspectiva padrão deste cubo.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-120">Notice that the check box for every object is selected; until you clear the check box for an object, this perspective is identical to the default perspective of this cube.</span></span>  
  
     <span data-ttu-id="f6b6a-121">![Nova perspectiva na coluna Nome da Perspectiva](../../2014/tutorials/media/l9-perspectives-2.gif "Nova perspectiva na coluna Nome da Perspectiva")</span><span class="sxs-lookup"><span data-stu-id="f6b6a-121">![New perspective in Perspective Name column](../../2014/tutorials/media/l9-perspectives-2.gif "New perspective in Perspective Name column")</span></span>  
  
3.  <span data-ttu-id="f6b6a-122">Altere o nome da perspectiva para `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="f6b6a-122">Change the perspective name to `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="f6b6a-123">Na próxima linha, defina DefaultMeasure como **Vendas pela Internet/Valor das Vendas**.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-123">On the next row, set the DefaultMeasure to **Internet Sales-Sales Amount**.</span></span>  
  
     <span data-ttu-id="f6b6a-124">Quando os usuários procurarem no cubo usando essa perspectiva, esta será a medida que eles verão, a menos que especifiquem alguma outra medida.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-124">When users browse the cube by using this perspective, this will be the measure that the users see unless they specify some other measure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6b6a-125">Também é possível definir a medida padrão para todo o cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] na guia **Estrutura do Cubo** na janela Propriedades do cubo.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-125">You can also set the default measure for the whole [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube in the Properties window on the **Cube Structure** tab for the cube.</span></span>  
  
5.  <span data-ttu-id="f6b6a-126">Desmarque a caixa de seleção dos seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="f6b6a-126">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="f6b6a-127">`Reseller Sales`grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="f6b6a-127">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-128">Grupo de medidas**Cotas de Vendas**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-128">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-129">Grupo de medidas**Cotas de Vendas 1**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-129">**Sales Quotas 1** measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-130">Dimensão de cubo**Revendedor**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-130">**Reseller** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-131">Dimensão de cubo**Geografia do Revendedor**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-131">**Reseller Geography** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-132">Dimensão de cubo**Região de Vendas**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-132">**Sales Territory** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-133">Dimensão de cubo**Funcionário**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-133">**Employee** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-134">Dimensão de cubo**Promoção**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-134">**Promotion** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-135">**Receita do Revendedor**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-135">**Reseller Revenue** KPI</span></span>  
  
    -   <span data-ttu-id="f6b6a-136">Conjunto nomeado**Grandes Revendedores**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-136">**Large Resellers** named set</span></span>  
  
    -   <span data-ttu-id="f6b6a-137">Membro calculado**Valor Total das Vendas**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-137">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-138">Membro calculado**Custo Total do Produto**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-138">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-139">Membro calculado**MLB do Revendedor**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-139">**Reseller GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-140">Membro calculado**MLB Total**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-140">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-141">Membro calculado**Índice de Vendas do Revendedor para Todos os Produtos**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-141">**Reseller Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-142">Membro calculado**Índice Total de Vendas para Todos os Produtos**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-142">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="f6b6a-143">Esses objetos não estão relacionados às vendas pela Internet.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-143">These objects do not relate to Internet sales.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6b6a-144">Dentro de cada dimensão, você também pode selecionar individualmente as hierarquias e atributos definidos pelos usuários que você quer que apareçam na perspectiva.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-144">Within each dimension, you can also individually select the user-defined hierarchies and attributes that you want to appear in a perspective.</span></span>  
  
## <a name="defining-a-reseller-sales-perspective"></a><span data-ttu-id="f6b6a-145">Definindo a perspectiva Vendas do Revendedor</span><span class="sxs-lookup"><span data-stu-id="f6b6a-145">Defining a Reseller Sales Perspective</span></span>  
  
1.  <span data-ttu-id="f6b6a-146">Na barra de ferramentas da guia **Perspectivas** , clique no botão **Nova Perspectiva** .</span><span class="sxs-lookup"><span data-stu-id="f6b6a-146">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="f6b6a-147">Altere o nome da nova perspectiva para `Reseller Sales` .</span><span class="sxs-lookup"><span data-stu-id="f6b6a-147">Change the name of the new perspective to `Reseller Sales`.</span></span>  
  
3.  <span data-ttu-id="f6b6a-148">Defina **Vendas do Revendedor/Valor das Vendas** como a medida padrão.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-148">Set **Reseller Sales-Sales Amount** as the default measure.</span></span>  
  
     <span data-ttu-id="f6b6a-149">Quando os usuários navegarem pelo cubo usando essa perspectiva, essa será a medida que eles verão, a menos que especifiquem alguma outra medida.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-149">When users browse the cube by using this perspective, this measure will be the measure that the users will see unless they specify some other measure.</span></span>  
  
4.  <span data-ttu-id="f6b6a-150">Desmarque a caixa de seleção dos seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="f6b6a-150">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="f6b6a-151">`Internet Sales`grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="f6b6a-151">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-152">Grupo de medidas**Motivo de Vendas pela Internet**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-152">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-153">Dimensão de cubo**Cliente**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-153">**Customer** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-154">Dimensão de cubo**Detalhes do Pedido de Vendas pela Internet**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-154">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-155">Dimensão de cubo**Motivo de Vendas**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-155">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-156">Ação de detalhamento**Ação de Detalhamento Detalhes de Vendas pela Internet**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-156">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
    -   <span data-ttu-id="f6b6a-157">Membro calculado**Valor Total das Vendas**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-157">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-158">Membro calculado**Custo Total do Produto**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-158">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-159">Membro calculado**MLB pela Internet**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-159">**Internet GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-160">Membro calculado**MLB Total**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-160">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-161">Membro calculado**Índice de Vendas pela Internet para Todos os Produtos**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-161">**Internet Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="f6b6a-162">Membro calculado**Índice Total de Vendas para Todos os Produtos**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-162">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="f6b6a-163">Esses objetos não estão relacionados às vendas do revendedor.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-163">These objects do not relate to resellers sales.</span></span>  
  
## <a name="defining-a-sales-summary-perspective"></a><span data-ttu-id="f6b6a-164">Definindo uma perspectiva Resumo das Vendas</span><span class="sxs-lookup"><span data-stu-id="f6b6a-164">Defining a Sales Summary Perspective</span></span>  
  
1.  <span data-ttu-id="f6b6a-165">Na barra de ferramentas da guia **Perspectivas** , clique no botão **Nova Perspectiva** .</span><span class="sxs-lookup"><span data-stu-id="f6b6a-165">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="f6b6a-166">Altere o nome da nova perspectiva para `Sales Summary` .</span><span class="sxs-lookup"><span data-stu-id="f6b6a-166">Change the name of the new perspective to `Sales Summary`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6b6a-167">Você não pode especificar uma medida calculada como a medida padrão.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-167">You cannot specify a calculated measure as the default measure.</span></span>  
  
3.  <span data-ttu-id="f6b6a-168">Desmarque a caixa de seleção dos seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="f6b6a-168">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="f6b6a-169">`Internet Sales`grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="f6b6a-169">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-170">`Reseller Sales`grupo de medidas</span><span class="sxs-lookup"><span data-stu-id="f6b6a-170">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-171">Grupo de medidas**Motivo de Vendas pela Internet**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-171">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-172">Grupo de medidas**Cotas de Vendas**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-172">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-173">Grupo de medidas**Cotas de Vendas1**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-173">**Sales Quotas1** measure group</span></span>  
  
    -   <span data-ttu-id="f6b6a-174">Dimensão de cubo**Detalhes do Pedido de Vendas pela Internet**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-174">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-175">Dimensão de cubo**Motivo de Vendas**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-175">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="f6b6a-176">Ação de detalhamento**Ação de Detalhamento Detalhes de Vendas pela Internet**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-176">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
4.  <span data-ttu-id="f6b6a-177">Selecione a caixa de seleção dos seguintes objetos:</span><span class="sxs-lookup"><span data-stu-id="f6b6a-177">Select the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="f6b6a-178">Medida**Contagem das Vendas pela Internet**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-178">**Internet Sales Count** measure</span></span>  
  
    -   <span data-ttu-id="f6b6a-179">Medida**Contagem das Vendas do Revendedor**</span><span class="sxs-lookup"><span data-stu-id="f6b6a-179">**Reseller Sales Count** measure</span></span>  
  
## <a name="browsing-the-cube-through-each-perspective"></a><span data-ttu-id="f6b6a-180">Navegando no cubo usando cada perspectiva</span><span class="sxs-lookup"><span data-stu-id="f6b6a-180">Browsing the Cube Through Each Perspective</span></span>  
  
1.  <span data-ttu-id="f6b6a-181">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-181">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="f6b6a-182">Quando a implantação for concluída com êxito, mude para a guia **Navegador** e clique no botão **Reconectar** .</span><span class="sxs-lookup"><span data-stu-id="f6b6a-182">When deployment has successfully completed, switch to the **Browser** tab, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="f6b6a-183">Inicie o Excel.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-183">Start Excel.</span></span>  
  
4.  <span data-ttu-id="f6b6a-184">A análise no Excel avisa para você escolher quais perspectivas devem ser usadas ao procurar o modelo no Excel, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-184">Analyze in Excel prompts you to choose which perspective to use when browsing the model in Excel, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f6b6a-185">![Objetos para a perspectiva Vendas pela Internet](../../2014/tutorials/media/l9-perspectives-3.gif "Objetos para a perspectiva Vendas pela Internet")</span><span class="sxs-lookup"><span data-stu-id="f6b6a-185">![Objects for the Internet Sales perspective](../../2014/tutorials/media/l9-perspectives-3.gif "Objects for the Internet Sales perspective")</span></span>  
  
5.  <span data-ttu-id="f6b6a-186">Como alternativa, você pode iniciar o Excel no menu Iniciar do Windows, definir uma conexão com o banco de dados de tutorial do Analysis Services no localhost, e pode escolher uma perspectiva no assistente de Conexão de Dados, como mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-186">Alternatively, you can start Excel from the Windows Start menu, define a connection to the Analysis Services Tutorial database on localhost, and choose a perspective in the Data Connection wizard, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f6b6a-187">![Assistente de Conexão de Dados no Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Assistente de Conexão de Dados no Excel")</span><span class="sxs-lookup"><span data-stu-id="f6b6a-187">![Data Connection wizard in Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Data Connection wizard in Excel")</span></span>  
  
6.  <span data-ttu-id="f6b6a-188">Selecione `Internet Sales` na lista **perspectiva** e, em seguida, examine as medidas e dimensões no painel metadados.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-188">Select `Internet Sales` in the **Perspective** list and then review the measures and dimensions in the metadata pane.</span></span>  
  
     <span data-ttu-id="f6b6a-189">Observe que somente aqueles objetos especificados na perspectiva Vendas pela Internet são exibidos.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-189">Notice that only those objects that are specified for the Internet Sales perspective appear.</span></span>  
  
7.  <span data-ttu-id="f6b6a-190">No painel de metadados, expanda **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-190">In the metadata pane, expand **Measures**.</span></span>  
  
     <span data-ttu-id="f6b6a-191">Observe que apenas o `Internet Sales` grupo de medidas aparece, junto com o **GPM da Internet** e a taxa de **vendas pela Internet para** membros calculados de todos os produtos.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-191">Notice that only the `Internet Sales` measure group appears, together with the **Internet GPM** and **Internet Sales Ratio to All Products** calculated members.</span></span>  
  
8.  <span data-ttu-id="f6b6a-192">No modelo, selecione Excel novamente.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-192">In the model, select Excel again.</span></span> <span data-ttu-id="f6b6a-193">Selecione `Sales Summary`.</span><span class="sxs-lookup"><span data-stu-id="f6b6a-193">Select `Sales Summary`.</span></span>  
  
     <span data-ttu-id="f6b6a-194">Observe que em cada grupo de medidas, somente uma medida é exibida, como mostra a imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="f6b6a-194">Notice that in each of these measure groups, only a single measure appears, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f6b6a-195">![Medidas Vendas pela Internet e Vendas do Revendedor](../../2014/tutorials/media/l9-perspectives-4.gif "Medidas Vendas pela Internet e Vendas do Revendedor")</span><span class="sxs-lookup"><span data-stu-id="f6b6a-195">![Internet Sales and Reseller Sales measures](../../2014/tutorials/media/l9-perspectives-4.gif "Internet Sales and Reseller Sales measures")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f6b6a-196">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="f6b6a-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f6b6a-197">Definindo e procurando traduções</span><span class="sxs-lookup"><span data-stu-id="f6b6a-197">Defining and Browsing Translations</span></span>](lesson-9-2-defining-and-browsing-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6b6a-198">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6b6a-198">See Also</span></span>  
 <span data-ttu-id="f6b6a-199">[Perspectivas](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span><span class="sxs-lookup"><span data-stu-id="f6b6a-199">[Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span></span>  
 [<span data-ttu-id="f6b6a-200">Perspectivas em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="f6b6a-200">Perspectives in Multidimensional Models</span></span>](multidimensional-models/perspectives-in-multidimensional-models.md)  
  
  
