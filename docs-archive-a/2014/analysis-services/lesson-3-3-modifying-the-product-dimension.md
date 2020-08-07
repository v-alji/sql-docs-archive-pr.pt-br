---
title: Modificando a dimensão Produto | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8e3ffecd-7f40-41a8-8735-bc9858a310cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 04c0a778a73371dada92c9ff207a17366a2fbc7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575438"
---
# <a name="modifying-the-product-dimension"></a><span data-ttu-id="d9aca-102">Modificando a dimensão Produto</span><span class="sxs-lookup"><span data-stu-id="d9aca-102">Modifying the Product Dimension</span></span>
  <span data-ttu-id="d9aca-103">Nas tarefas deste tópico, você usará um cálculo nomeado para fornecer nomes mais descritivos às linhas de produto, definir uma hierarquia na dimensão Produto e especificar o nome do membro (Todos) para a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="d9aca-103">In the tasks in this topic, you use a named calculation to provide more descriptive names for the product lines, define a hierarchy in the Product dimension, and specify the (All) member name for the hierarchy.</span></span> <span data-ttu-id="d9aca-104">Você também agrupará atributos nas pastas de exibição.</span><span class="sxs-lookup"><span data-stu-id="d9aca-104">You also group attributes into display folders.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="d9aca-105">Adicionando um cálculo nomeado</span><span class="sxs-lookup"><span data-stu-id="d9aca-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="d9aca-106">Você pode adicionar um cálculo nomeado a uma tabela em uma exibição de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d9aca-106">You can add a named calculation to a table in a data source view.</span></span> <span data-ttu-id="d9aca-107">Na tarefa a seguir, você criará um cálculo nomeado que exibirá o nome completo da linha de produto.</span><span class="sxs-lookup"><span data-stu-id="d9aca-107">In the following task, you create a named calculation that displays the full product line name.</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="d9aca-108">Para adicionar um cálculo nomeado</span><span class="sxs-lookup"><span data-stu-id="d9aca-108">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="d9aca-109">Para abrir a exibição da fonte de dados **Adventure Works DW 2012** , clique duas vezes em **Adventure Works DW 2012** na pasta **Exibições da Fonte de Dados** no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="d9aca-109">To open the **Adventure Works DW 2012** data source view, double-click **Adventure Works DW 2012** in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="d9aca-110">Na parte inferior do painel de diagrama, clique com o botão direito do mouse no cabeçalho da tabela **Product** e clique em **Novo Cálculo Nomeado**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-110">In the bottom of the diagram pane, right-click the **Product** table header, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="d9aca-111">Na caixa de diálogo **criar cálculo nomeado** , digite `ProductLineName` a caixa **nome da coluna** .</span><span class="sxs-lookup"><span data-stu-id="d9aca-111">In the **Create Named Calculation** dialog box, type `ProductLineName` in the **Column name** box.</span></span>  
  
4.  <span data-ttu-id="d9aca-112">Na caixa **Expressão** , digite ou copie e cole a seguinte instrução **CASE** :</span><span class="sxs-lookup"><span data-stu-id="d9aca-112">In the **Expression** box, type or copy and paste the following **CASE** statement:</span></span>  
  
    ```  
    CASE ProductLine  
       WHEN 'M' THEN 'Mountain'  
       WHEN 'R' THEN 'Road'  
       WHEN 'S' THEN 'Accessory'  
       WHEN 'T' THEN 'Touring'  
       ELSE 'Components'  
    END  
    ```  
  
     <span data-ttu-id="d9aca-113">Essa instrução **CASE** cria nomes amigáveis para cada linha de produto no cubo.</span><span class="sxs-lookup"><span data-stu-id="d9aca-113">This **CASE** statement creates user-friendly names for each product line in the cube.</span></span>  
  
5.  <span data-ttu-id="d9aca-114">Clique em **OK** para criar o `ProductLineName` cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="d9aca-114">Click **OK** to create the `ProductLineName` named calculation.</span></span> <span data-ttu-id="d9aca-115">Talvez você precise esperar um pouco.</span><span class="sxs-lookup"><span data-stu-id="d9aca-115">You might need to wait.</span></span>  
  
6.  <span data-ttu-id="d9aca-116">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="modifying-the-namecolumn-property-of-an-attribute"></a><span data-ttu-id="d9aca-117">Modificando a propriedade NameColumn de um atributo</span><span class="sxs-lookup"><span data-stu-id="d9aca-117">Modifying the NameColumn Property of an Attribute</span></span>  
  
#### <a name="to-modify-the-namecolumn-property-value-of-an-attribute"></a><span data-ttu-id="d9aca-118">Para modificar a propriedade NameColumn de um atributo</span><span class="sxs-lookup"><span data-stu-id="d9aca-118">To modify the NameColumn property value of an attribute</span></span>  
  
1.  <span data-ttu-id="d9aca-119">Alterne para o Designer de Dimensão da dimensão Produto.</span><span class="sxs-lookup"><span data-stu-id="d9aca-119">Switch to Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="d9aca-120">Para fazer isso, clique duas vezes na dimensão **Produto** no nó **Dimensões** do Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="d9aca-120">To do this, double-click the **Product** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="d9aca-121">No painel **Atributos** da guia **Estrutura da Dimensão** , selecione **Linha de Produto**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-121">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Line**.</span></span>  
  
3.  <span data-ttu-id="d9aca-122">Na janela Propriedades no lado direito da tela, clique no campo de propriedade **NameColumn** na parte inferior da janela e, em seguida, clique no botão procurar (**...**) para abrir a caixa de diálogo **coluna de nome** .</span><span class="sxs-lookup"><span data-stu-id="d9aca-122">In the Properties window on the right side of the screen, click the **NameColumn** property field at the bottom of the window, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span> <span data-ttu-id="d9aca-123">(Talvez seja necessário clicar na guia **Propriedades** à direita da tela para abrir a janela Propriedades.)</span><span class="sxs-lookup"><span data-stu-id="d9aca-123">(You might need to click the **Properties** tab on the right side of the screen to open the Properties window.</span></span>  
  
4.  <span data-ttu-id="d9aca-124">Selecione `ProductLineName` na parte inferior da lista **coluna de origem** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-124">Select `ProductLineName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d9aca-125">O campo NameColumn agora contém o texto **Product.ProductLineName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-125">The NameColumn field now contains the text, **Product.ProductLineName (WChar)**.</span></span> <span data-ttu-id="d9aca-126">Os membros da hierarquia do atributo **Product Line** agora exibirão o nome completo da linha de produto, em vez do nome abreviado.</span><span class="sxs-lookup"><span data-stu-id="d9aca-126">The members of the **Product Line** attribute hierarchy now display the full name of the product line instead of an abbreviated product line name.</span></span>  
  
5.  <span data-ttu-id="d9aca-127">No painel **Atributos** da guia **Estrutura da Dimensão** , selecione **Chave do Produto (Product Key)**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-127">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Key**.</span></span>  
  
6.  <span data-ttu-id="d9aca-128">No janela Propriedades, clique no campo de propriedade **NameColumn** e, em seguida, clique no botão procurar (**...**) para abrir a caixa de diálogo **coluna de nome** .</span><span class="sxs-lookup"><span data-stu-id="d9aca-128">In the Properties window, click the **NameColumn** property field, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
7.  <span data-ttu-id="d9aca-129">Selecione **EnglishProductName** na lista **Coluna de origem** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-129">Select **EnglishProductName** in the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d9aca-130">O campo NameColumn agora contém o texto **Product.EnglishProductName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-130">The NameColumn field now contains the text, **Product.EnglishProductName (WChar)**.</span></span>  
  
8.  <span data-ttu-id="d9aca-131">No janela Propriedades, role para cima, clique no campo de propriedade **nome** e digite `Product Name` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-131">In the Properties window, scroll up, click the **Name** property field, and then type `Product Name`.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="d9aca-132">Criando uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="d9aca-132">Creating a Hierarchy</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="d9aca-133">Para criar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="d9aca-133">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="d9aca-134">Arraste o atributo **Product Line** do painel **Atributos** até o painel **Hierarquias** .</span><span class="sxs-lookup"><span data-stu-id="d9aca-134">Drag the **Product Line** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="d9aca-135">Arraste o atributo **Model Name** do painel **Atributos** até a célula **\<new level>** do painel **Hierarquias** , sob o nível **Linha de Produto** .</span><span class="sxs-lookup"><span data-stu-id="d9aca-135">Drag the **Model Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Product Line** level.</span></span>  
  
3.  <span data-ttu-id="d9aca-136">Arraste o `Product Name` atributo do painel **atributos** até a **\<new level>** célula no painel **hierarquias** , sob o nível **nome do modelo** .</span><span class="sxs-lookup"><span data-stu-id="d9aca-136">Drag the `Product Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Model Name** level.</span></span> <span data-ttu-id="d9aca-137">(Você renomeou Product Key para Product Name na seção anterior.)</span><span class="sxs-lookup"><span data-stu-id="d9aca-137">(You renamed Product Key to Product Name in the previous section.)</span></span>  
  
4.  <span data-ttu-id="d9aca-138">No painel **hierarquias** da guia **estrutura da dimensão** , clique com o botão direito do mouse na barra de título da hierarquia **hierarquia** , clique em **renomear**e digite `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-138">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Product Model Lines`.</span></span>  
  
     <span data-ttu-id="d9aca-139">O nome da hierarquia agora é `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-139">The name of the hierarchy is now `Product Model Lines`.</span></span>  
  
5.  <span data-ttu-id="d9aca-140">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-140">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="specifying-folder-names-and-all-member-names"></a><span data-ttu-id="d9aca-141">Especificando nomes de pastas e de todos os membros</span><span class="sxs-lookup"><span data-stu-id="d9aca-141">Specifying Folder Names and All Member Names</span></span>  
  
#### <a name="to-specify-the-folder-and-member-names"></a><span data-ttu-id="d9aca-142">Para especificar os nomes de pasta e membro</span><span class="sxs-lookup"><span data-stu-id="d9aca-142">To specify the folder and member names</span></span>  
  
1.  <span data-ttu-id="d9aca-143">No painel **Atributos** , selecione os seguintes atributos pressionando e mantendo a tecla CTRL pressionada enquanto clica em cada um deles:</span><span class="sxs-lookup"><span data-stu-id="d9aca-143">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="d9aca-144">**Classe**</span><span class="sxs-lookup"><span data-stu-id="d9aca-144">**Class**</span></span>  
  
    -   <span data-ttu-id="d9aca-145">**Cor**</span><span class="sxs-lookup"><span data-stu-id="d9aca-145">**Color**</span></span>  
  
    -   <span data-ttu-id="d9aca-146">**Dias para fabricação**</span><span class="sxs-lookup"><span data-stu-id="d9aca-146">**Days To Manufacture**</span></span>  
  
    -   <span data-ttu-id="d9aca-147">**Reorder Point**</span><span class="sxs-lookup"><span data-stu-id="d9aca-147">**Reorder Point**</span></span>  
  
    -   <span data-ttu-id="d9aca-148">**Safety Stock Level**</span><span class="sxs-lookup"><span data-stu-id="d9aca-148">**Safety Stock Level**</span></span>  
  
    -   <span data-ttu-id="d9aca-149">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="d9aca-149">**Size**</span></span>  
  
    -   <span data-ttu-id="d9aca-150">**Size Range**</span><span class="sxs-lookup"><span data-stu-id="d9aca-150">**Size Range**</span></span>  
  
    -   <span data-ttu-id="d9aca-151">**Estilo**</span><span class="sxs-lookup"><span data-stu-id="d9aca-151">**Style**</span></span>  
  
    -   <span data-ttu-id="d9aca-152">**Weight**</span><span class="sxs-lookup"><span data-stu-id="d9aca-152">**Weight**</span></span>  
  
2.  <span data-ttu-id="d9aca-153">No campo de propriedade **AttributeHierarchyDisplayFolder** na janela Propriedades, digite `Stocking` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-153">In the **AttributeHierarchyDisplayFolder** property field in the Properties window, type `Stocking`.</span></span>  
  
     <span data-ttu-id="d9aca-154">Você acaba de agrupar esses atributos em uma única pasta de exibição.</span><span class="sxs-lookup"><span data-stu-id="d9aca-154">You have now grouped these attributes into a single display folder.</span></span>  
  
3.  <span data-ttu-id="d9aca-155">No painel **Atributos** , selecione os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="d9aca-155">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="d9aca-156">**Preço do Revendedor**</span><span class="sxs-lookup"><span data-stu-id="d9aca-156">**Dealer Price**</span></span>  
  
    -   <span data-ttu-id="d9aca-157">**Preço da Lista**</span><span class="sxs-lookup"><span data-stu-id="d9aca-157">**List Price**</span></span>  
  
    -   <span data-ttu-id="d9aca-158">**Custo Padrão**</span><span class="sxs-lookup"><span data-stu-id="d9aca-158">**Standard Cost**</span></span>  
  
4.  <span data-ttu-id="d9aca-159">Na célula da propriedade **AttributeHierarchyDisplayFolder** na janela Propriedades, digite `Financial` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-159">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `Financial`.</span></span>  
  
     <span data-ttu-id="d9aca-160">Você acaba de agrupar esses atributos em uma segunda pasta de exibição.</span><span class="sxs-lookup"><span data-stu-id="d9aca-160">You have now grouped these attributes into a second display folder.</span></span>  
  
5.  <span data-ttu-id="d9aca-161">No painel **Atributos** , selecione os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="d9aca-161">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="d9aca-162">**Data de Término**</span><span class="sxs-lookup"><span data-stu-id="d9aca-162">**End Date**</span></span>  
  
    -   <span data-ttu-id="d9aca-163">**Data de Início**</span><span class="sxs-lookup"><span data-stu-id="d9aca-163">**Start Date**</span></span>  
  
    -   <span data-ttu-id="d9aca-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="d9aca-164">**Status**</span></span>  
  
6.  <span data-ttu-id="d9aca-165">Na célula da propriedade **AttributeHierarchyDisplayFolder** na janela Propriedades, digite `History` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-165">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `History`.</span></span>  
  
     <span data-ttu-id="d9aca-166">Você acaba de agrupar esses atributos em uma terceira pasta de exibição.</span><span class="sxs-lookup"><span data-stu-id="d9aca-166">You have now grouped these attributes into a third display folder.</span></span>  
  
7.  <span data-ttu-id="d9aca-167">Selecione a `Product Model Lines` hierarquia no painel **hierarquias** e altere a propriedade **membroname** no janela Propriedades para `All Products` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-167">Select the `Product Model Lines` hierarchy in the **Hierarchies** pane, and then change the **AllMemberName** property in the Properties window to `All Products`.</span></span>  
  
8.  <span data-ttu-id="d9aca-168">Clique em uma área aberta do painel **hierarquias** e altere a propriedade **AttributeAllMemberName** na parte superior da janela Propriedades para `All Products` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-168">Click an open area of the **Hierarchies** pane, and then change the **AttributeAllMemberName** property at the top of the Properties window to `All Products`.</span></span>  
  
     <span data-ttu-id="d9aca-169">Clicar em uma área aberta permite que você modifique propriedades da própria dimensão Produto.</span><span class="sxs-lookup"><span data-stu-id="d9aca-169">Clicking an open area lets you modify properties of the Product dimension itself.</span></span> <span data-ttu-id="d9aca-170">Você também pode clicar em **Produto** na parte superior da lista de atributos no painel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="d9aca-170">You could also click **Product** at the top of the attributes list in the **Attributes** pane.</span></span>  
  
9. <span data-ttu-id="d9aca-171">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-171">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="d9aca-172">Definindo relações de atributo</span><span class="sxs-lookup"><span data-stu-id="d9aca-172">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="d9aca-173">Se os dados subjacentes permitirem, você também deve definir relações de atributo entre atributos.</span><span class="sxs-lookup"><span data-stu-id="d9aca-173">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="d9aca-174">Definir relações de atributo acelera o processamento de dimensões, partições e consultas.</span><span class="sxs-lookup"><span data-stu-id="d9aca-174">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="d9aca-175">Para obter mais informações, consulte [Definir relações de atributo](multidimensional-models/attribute-relationships-define.md) e [Relações de atributo](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d9aca-175">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="d9aca-176">Para definir relações de atributo</span><span class="sxs-lookup"><span data-stu-id="d9aca-176">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="d9aca-177">No **Designer de Dimensão** da dimensão Produto, clique na guia **Relações de Atributo** .</span><span class="sxs-lookup"><span data-stu-id="d9aca-177">In the **Dimension Designer** for the Product dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="d9aca-178">No diagrama, clique com o botão direito do mouse no atributo **Nome do Modelo** e clique em **Nova Relação de Atributo**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-178">In the diagram, right-click the **Model Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="d9aca-179">Na caixa de diálogo **Criar Relação de Atributo** , o **Atributo de Origem** é **Model Name**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-179">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Model Name**.</span></span> <span data-ttu-id="d9aca-180">Defina o **Atributo Relacionado** como **Linha de Produto**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-180">Set the **Related Attribute** to **Product Line**.</span></span>  
  
     <span data-ttu-id="d9aca-181">Na lista **Tipo de relação** , deixe o tipo de relação definido como **Flexível** porque as relações entre os membros podem mudar com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="d9aca-181">In the **Relationship type** list, leave the relationship type set to **Flexible** because relationships between the members might change over time.</span></span> <span data-ttu-id="d9aca-182">Por exemplo, um modelo de produto pode ser movido para uma linha de produto diferente.</span><span class="sxs-lookup"><span data-stu-id="d9aca-182">For example, a product model might eventually be moved to a different product line.</span></span>  
  
4.  <span data-ttu-id="d9aca-183">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-183">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="d9aca-184">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="reviewing-product-dimension-changes"></a><span data-ttu-id="d9aca-185">Revisando as alterações na dimensão Produto</span><span class="sxs-lookup"><span data-stu-id="d9aca-185">Reviewing Product Dimension Changes</span></span>  
  
#### <a name="to-review-the-product-dimension-changes"></a><span data-ttu-id="d9aca-186">Para revisar as alterações na dimensão Produto</span><span class="sxs-lookup"><span data-stu-id="d9aca-186">To review the Product dimension changes</span></span>  
  
1.  <span data-ttu-id="d9aca-187">No menu **Compilar** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="d9aca-187">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="d9aca-188">Depois de receber a mensagem **Implantação Concluída com Êxito** , clique na guia **Navegador** do **Designer de Dimensão** da dimensão **Produto** e clique no botão Reconectar na barra de ferramentas do designer.</span><span class="sxs-lookup"><span data-stu-id="d9aca-188">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the **Product** dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="d9aca-189">Verifique se `Product Model Lines` está selecionado na lista **hierarquia** e, em seguida, expanda `All Products` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-189">Verify that `Product Model Lines` is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>  
  
     <span data-ttu-id="d9aca-190">Observe que o nome do membro **All** é exibido como `All Products` .</span><span class="sxs-lookup"><span data-stu-id="d9aca-190">Notice that the name of the **All** member appears as `All Products`.</span></span> <span data-ttu-id="d9aca-191">Isso ocorre porque você alterou a propriedade de todos os **Membros** da hierarquia para a `All Products` anterior na lição.</span><span class="sxs-lookup"><span data-stu-id="d9aca-191">This is because you changed the **AllMemberName** property for the hierarchy to `All Products` earlier in the lesson.</span></span> <span data-ttu-id="d9aca-192">Além disso, os membros do nível **Linha de Produto** agora têm nomes amigáveis, em vez de abreviações de apenas uma letra.</span><span class="sxs-lookup"><span data-stu-id="d9aca-192">Also, the members of the **Product Line** level now have user-friendly names, instead of single-letter abbreviations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d9aca-193">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="d9aca-193">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d9aca-194">Modificando a dimensão de data</span><span class="sxs-lookup"><span data-stu-id="d9aca-194">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="d9aca-195">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9aca-195">See Also</span></span>  
 <span data-ttu-id="d9aca-196">[Definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d9aca-196">[Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span></span>  
 <span data-ttu-id="d9aca-197">[Criar hierarquias definidas pelo usuário](multidimensional-models/user-defined-hierarchies-create.md) </span><span class="sxs-lookup"><span data-stu-id="d9aca-197">[Create User-Defined Hierarchies](multidimensional-models/user-defined-hierarchies-create.md) </span></span>  
 [<span data-ttu-id="d9aca-198">Configurar o nível &#40;All&#41; para hierarquias de atributo</span><span class="sxs-lookup"><span data-stu-id="d9aca-198">Configure the &#40;All&#41; Level for Attribute Hierarchies</span></span>](multidimensional-models/database-dimensions-configure-the-all-level-for-attribute-hierarchies.md)  
  
  
