---
title: Definindo o membro desconhecido e as propriedades de processamento nulo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d9abb09c-9bfa-4e32-b530-8590e4383566
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdd6504bec4f129f64d9bef6f6b0138e917888e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572818"
---
# <a name="defining-the-unknown-member-and-null-processing-properties"></a><span data-ttu-id="3d19d-102">Definindo o membro desconhecido e as propriedades de processamento nulo</span><span class="sxs-lookup"><span data-stu-id="3d19d-102">Defining the Unknown Member and Null Processing Properties</span></span>
  <span data-ttu-id="3d19d-103">Quando o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] processa uma dimensão, todos os valores distintos das colunas subjacentes nas tabelas, ou nas exibições da fonte de dados, populam os atributos na dimensão.</span><span class="sxs-lookup"><span data-stu-id="3d19d-103">When [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] processes a dimension, all the distinct values from the underlying columns in the tables, or views in the data source view, populate the attributes in the dimension.</span></span> <span data-ttu-id="3d19d-104">Por padrão, se o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] detecta um valor nulo durante o processamento, ele converte o valor nulo em zero no caso de colunas numéricas ou em cadeia vazia no caso de colunas de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3d19d-104">If [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] encounters a null value during processing, by default, it converts this null to a zero for numeric columns or to an empty string for string columns.</span></span> <span data-ttu-id="3d19d-105">Você pode modificar as configurações padrão ou converter valores nulos em seu processo de extração, transformação e carregamento (caso haja algum) do data warehouse relacional subjacente.</span><span class="sxs-lookup"><span data-stu-id="3d19d-105">You can modify the default settings or convert null values in your extract, transform, and load process (if any) of the underlying relational data warehouse.</span></span> <span data-ttu-id="3d19d-106">Além disso, você pode usar o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para converter o valor nulo em um valor designado, configurando três propriedades: **UnknownMember** e **UnknownMemberName** para a dimensão e **NullProcessing** para o atributo de chave da dimensão.</span><span class="sxs-lookup"><span data-stu-id="3d19d-106">Additionally, you can have [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] convert the null value to a designated value by configuring three properties: the **UnknownMember** and **UnknownMemberName** properties for the dimension, and the **NullProcessing** property for the dimension's key attribute.</span></span>

 <span data-ttu-id="3d19d-107">O Assistente para Dimensões e o Assistente para Cubos habilitarão essas propriedades com base no fato de o atributo de chave de uma dimensão permitir um valor nulo ou de o atributo raiz de uma dimensão floco de neve ter base em uma coluna que permite um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="3d19d-107">The Dimension Wizard and the Cube Wizard will enable these properties for you based on whether the key attribute of a dimension is nullable or the root attribute of a snowflake dimension is based on a nullable column.</span></span> <span data-ttu-id="3d19d-108">Nesses casos, a propriedade **NullProcessing** do atributo de chave será definida como **UnknownMember** e a propriedade **UnknownMember** será configurada como **Visível**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-108">In these cases, the **NullProcessing** property of the key attribute will be set to **UnknownMember** and the **UnknownMember** property will be set to **Visible**.</span></span>

 <span data-ttu-id="3d19d-109">Entretanto, ao criar dimensões floco de neve de forma incremental, como estamos fazendo na dimensão Product, ou ao definir dimensões usando o Designer de Dimensão e incorporar essas dimensões existentes em um cubo, talvez as propriedades **UnknownMember** e **NullProcessing** precisem ser definidas manualmente.</span><span class="sxs-lookup"><span data-stu-id="3d19d-109">However, when you build snowflaked dimensions incrementally, as we are doing with the Product dimension in this tutorial, or when you define dimensions using Dimension Designer and then incorporate these existing dimensions into a cube, the **UnknownMember** and **NullProcessing** properties might need to be set manually.</span></span>

 <span data-ttu-id="3d19d-110">Nas tarefas deste tópico, você adicionará os atributos da categoria e subcategoria de produto à dimensão Produto das tabelas floco de neve que você adicionará à exibição da fonte de dados [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW.</span><span class="sxs-lookup"><span data-stu-id="3d19d-110">In the tasks in this topic, you will add the product category and product subcategory attributes to the Product dimension from snowflaked tables that you will add to the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW data source view.</span></span> <span data-ttu-id="3d19d-111">Em seguida, você habilitará a propriedade **UnknownMember** para a dimensão produto, especificará `Assembly Components` como o valor da propriedade **UnknownMemberName** , relacionará os `Subcategory` `Category` atributos e ao atributo nome do produto e, em seguida, definirá o tratamento de erro personalizado para o atributo de chave de membro que vincula as tabelas floco de neve.</span><span class="sxs-lookup"><span data-stu-id="3d19d-111">You will then enable the **UnknownMember** property for the Product dimension, specify `Assembly Components` as the value for the **UnknownMemberName** property, relate the `Subcategory` and `Category` attributes to the product name attribute, and then define custom error handling for the member key attribute that links the snowflaked tables.</span></span>

> [!NOTE]
>  <span data-ttu-id="3d19d-112">Caso tenha adicionado os atributos Subcategoria e Categoria durante a definição do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usando o Assistente para Cubos, estas etapas foram feitas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3d19d-112">If you have added the Subcategory and Category attributes when you originally defined the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube using the Cube Wizard, these steps would have been performed for you automatically.</span></span>

## <a name="reviewing-error-handling-and-unknown-member-properties-in-the-product-dimension"></a><span data-ttu-id="3d19d-113">Revisando propriedades de tratamento de erros e de membro desconhecido na dimensão Produto</span><span class="sxs-lookup"><span data-stu-id="3d19d-113">Reviewing Error Handling and Unknown Member Properties in the Product Dimension</span></span>

1.  <span data-ttu-id="3d19d-114">Mude para o Designer de Dimensão da dimensão **Produto** , clique na guia **Estrutura da Dimensão** e selecione **Produto** no painel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-114">Switch to Dimension Designer for the **Product** dimension, click the **Dimension Structure** tab, and then select **Product** in the **Attributes** pane.</span></span>

     <span data-ttu-id="3d19d-115">Isso permite que você exiba e modifique as propriedades da própria dimensão.</span><span class="sxs-lookup"><span data-stu-id="3d19d-115">This enables you to view and modify the properties of the dimension itself.</span></span>

2.  <span data-ttu-id="3d19d-116">Na janela Propriedades, examine as propriedades **UnknownMember** e **UnknownMemberName** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-116">In the Properties window, review the **UnknownMember** and **UnknownMemberName** properties.</span></span>

     <span data-ttu-id="3d19d-117">Observe que a propriedade **UnknownMember** não está habilitada porque seu valor está definido como **Nenhum** em vez de **Visível** ou **Oculto**e que não há nenhum nome especificado para a propriedade **UnknownMemberName** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-117">Notice that the **UnknownMember** property is not enabled, because its value is set to **None** instead of **Visible** or **Hidden**, and that no name is specified for the **UnknownMemberName** property.</span></span>

3.  <span data-ttu-id="3d19d-118">Na janela Propriedades, selecione **(personalizado)** na célula da propriedade **ErrorConfiguration** e expanda a coleção de propriedades **ErrorConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-118">In the Properties window, select **(custom)** in the **ErrorConfiguration** property cell, and then expand the **ErrorConfiguration** properties collection.</span></span>

     <span data-ttu-id="3d19d-119">Definir a propriedade **ErrorConfiguration** como **(personalizado)** permite que você exiba as definições de configuração de erro padrão; isso não altera as configurações.</span><span class="sxs-lookup"><span data-stu-id="3d19d-119">Setting the **ErrorConfiguration** property to **(custom)** allows you to view the default error configuration settings - it does not change any settings.</span></span>

4.  <span data-ttu-id="3d19d-120">Revise as propriedades de chave e de configuração de erro de chave nula, mas não faça nenhuma alteração.</span><span class="sxs-lookup"><span data-stu-id="3d19d-120">Review the key and null key error configuration properties, but do not make any changes.</span></span>

     <span data-ttu-id="3d19d-121">Observe que, por padrão, quando as chaves nulas são convertidas para o membro desconhecido, o erro de processamento associado a essa conversão é ignorado</span><span class="sxs-lookup"><span data-stu-id="3d19d-121">Notice that, by default, when null keys are converted to the unknown member and the processing error associated with this conversion is ignored.</span></span>

     <span data-ttu-id="3d19d-122">A imagem a seguir mostra as configurações de propriedade da coleção de propriedades **ErrorConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-122">The following image shows the property settings for the **ErrorConfiguration** properties collection.</span></span>

     <span data-ttu-id="3d19d-123">![Coleção de propriedades ErrorConfiguration](../../2014/tutorials/media/l4-productdimensionerrorconfig-1.gif "Coleção de propriedades ErrorConfiguration")</span><span class="sxs-lookup"><span data-stu-id="3d19d-123">![ErrorConfiguration property collection](../../2014/tutorials/media/l4-productdimensionerrorconfig-1.gif "ErrorConfiguration property collection")</span></span>

5.  <span data-ttu-id="3d19d-124">Clique na guia **navegador** , verifique se **linhas de modelo de produto** está selecionada na lista **hierarquia** e, em seguida, expanda `All Products` .</span><span class="sxs-lookup"><span data-stu-id="3d19d-124">Click the **Browser** tab, verify that **Product Model Lines** is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>

     <span data-ttu-id="3d19d-125">Observe os cinco membros do nível Linha de Produto.</span><span class="sxs-lookup"><span data-stu-id="3d19d-125">Notice the five members of the Product Line level.</span></span>

6.  <span data-ttu-id="3d19d-126">Expanda **Componentes**e expanda o membro não rotulado do nível **Nome do Modelo** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-126">Expand **Components**, and then expand the unlabeled member of the **Model Name** level.</span></span>

     <span data-ttu-id="3d19d-127">Esse nível contém os componentes do assembly que são usados para criar outros componentes, começando com o produto **Corrida Ajustável** , como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="3d19d-127">This level contains the assembly components that are used when building other components, starting with the **Adjustable Race** product, as shown in the following image.</span></span>

     <span data-ttu-id="3d19d-128">![Componentes de assembly usados para criar outros componentes](../../2014/tutorials/media/l4-productdimensionerrorconfig-2.gif "Componentes de assembly usados para criar outros componentes")</span><span class="sxs-lookup"><span data-stu-id="3d19d-128">![Assembly components used to build other components](../../2014/tutorials/media/l4-productdimensionerrorconfig-2.gif "Assembly components used to build other components")</span></span>

## <a name="defining-attributes-from-snowflaked-tables-and-a-product-category-user-defined-hierarchy"></a><span data-ttu-id="3d19d-129">Definindo atributos das tabelas floco de neve e uma hierarquia definida pelo usuário Categoria do Produto</span><span class="sxs-lookup"><span data-stu-id="3d19d-129">Defining Attributes from Snowflaked Tables and a Product Category User-Defined Hierarchy</span></span>

1.  <span data-ttu-id="3d19d-130">Abra o Designer de Exibição da Fonte de Dados da exibição da fonte de dados do [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW, selecione **Compras do Revendedor** no painel **Organizador de Diagramas** e clique em **Adicionar/Remover Objetos** no menu **Exibição da Fonte de Dados** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d19d-130">Open Data Source View Designer for the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW data source view, select **Reseller Sales** in the **Diagram Organizer** pane, and then click **Add/Remove Objects** on the **Data Source View** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>

     <span data-ttu-id="3d19d-131">A caixa de diálogo **Adicionar/Remover Tabelas** é aberta.</span><span class="sxs-lookup"><span data-stu-id="3d19d-131">The **Add/Remove Tables** dialog box opens.</span></span>

2.  <span data-ttu-id="3d19d-132">Na lista **Objetos incluídos** , selecione **DimProduct (dbo)** e clique em **Adicionar Tabelas Relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-132">In the **Included objects** list, select **DimProduct (dbo)**, and then click **Add Related Tables**.</span></span>

     <span data-ttu-id="3d19d-133">São adicionados **DimProductSubcategory (dbo)** e **FactProductInventory (dbo)** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-133">Both **DimProductSubcategory (dbo)** and **FactProductInventory (dbo)** are added.</span></span> <span data-ttu-id="3d19d-134">Remova **FactProductInventory (dbo)** de forma que apenas a tabela **DimProductSubcategory (dbo)** seja adicionada à lista **Objetos incluídos** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-134">Remove **FactProductInventory (dbo)** so that just the **DimProductSubcategory (dbo)** table is added to the **Included objects** list.</span></span>

3.  <span data-ttu-id="3d19d-135">Com a tabela **DimProductSubcategory (dbo)** selecionada por padrão como a tabela adicionada mais recentemente, clique em **Adicionar Tabelas Relacionadas** novamente.</span><span class="sxs-lookup"><span data-stu-id="3d19d-135">With the **DimProductSubcategory (dbo)** table selected by default as the table most recently added, click **Add Related Tables** again.</span></span>

     <span data-ttu-id="3d19d-136">A tabela **DimProductCategory (dbo)** é adicionada à lista **Objetos incluídos** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-136">The **DimProductCategory (dbo)** table is added to the **Included objects** list.</span></span>

4.  <span data-ttu-id="3d19d-137">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-137">Click **OK**.</span></span>

5.  <span data-ttu-id="3d19d-138">No menu **Formatar** do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], aponte para **Layout Automático**e clique em **Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-138">On the **Format** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], point to **Auto Layout**, and then click **Diagram**.</span></span>

     <span data-ttu-id="3d19d-139">Observe que as tabelas **DimProductSubcategory (dbo)** e **DimProductCategory (dbo)** são vinculadas uma a outra e também à tabela **ResellerSales** por meio da tabela **Product** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-139">Notice that the **DimProductSubcategory (dbo)** table and **DimProductCategory (dbo)** table are linked to each other, and also to the **ResellerSales** table through the **Product** table.</span></span>

6.  <span data-ttu-id="3d19d-140">Mude para o Designer de Dimensão da dimensão **Produto** e clique na guia **Estrutura da Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-140">Switch to Dimension Designer for the **Product** dimension, and then click the **Dimension Structure** tab.</span></span>

7.  <span data-ttu-id="3d19d-141">Clique com o botão direito do mouse em qualquer lugar no painel **Exibição da Fonte de Dados** e clique em **Mostrar Todas as Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-141">Right-click anywhere in the **Data Source View** pane, and then click **Show All Tables**.</span></span>

8.  <span data-ttu-id="3d19d-142">No painel **Exibição da Fonte de Dados** , localize a tabela **DimProductCategory** , clique com o botão direito do mouse em **ProductCategoryKey** nessa tabela e clique em **Novo Atributo da Coluna**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-142">In the **Data Source View** pane, locate the **DimProductCategory** table, right-click **ProductCategoryKey** in that table, and then click **New Attribute from Column**.</span></span>

9. <span data-ttu-id="3d19d-143">No painel **atributos** , altere o nome desse novo atributo para `Category` .</span><span class="sxs-lookup"><span data-stu-id="3d19d-143">In the **Attributes** pane, change the name of this new attribute to `Category`.</span></span>

10. <span data-ttu-id="3d19d-144">No janela Propriedades, clique no campo de propriedade **NameColumn** e, em seguida, clique no botão procurar (**...**) para abrir a caixa de diálogo **coluna de nome** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-144">In the Properties window, click in the **NameColumn** property field and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span>

11. <span data-ttu-id="3d19d-145">Selecione **EnglishProductCategoryName** na lista **Coluna de origem** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-145">Select **EnglishProductCategoryName** in the **Source column** list and then click **OK**.</span></span>

12. <span data-ttu-id="3d19d-146">No painel **Exibição da Fonte de Dados** , localize a tabela **DimProductSubcategory** , clique com o botão direito do mouse em **ProductSubcategoryKey** na tabela e clique em **Novo Atributo da Coluna**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-146">In the **Data Source View** pane, locate the **DimProductSubcategory** table, right-click **ProductSubcategoryKey** in that table, and then click **New Attribute from Column**.</span></span>

13. <span data-ttu-id="3d19d-147">No painel **atributos** , altere o nome desse novo atributo para `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="3d19d-147">In the **Attributes** pane, change the name of this new attribute to `Subcategory`.</span></span>

14. <span data-ttu-id="3d19d-148">No janela Propriedades, clique no campo de propriedade **NameColumn** e, em seguida, clique no botão procurar **(...)** para abrir a caixa de diálogo **coluna de nome** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-148">In the Properties window, click in the **NameColumn** property field and then click the browse **(...)** button to open the **Name Column** dialog box.</span></span>

15. <span data-ttu-id="3d19d-149">Selecione **EnglishProductSubcategoryName** na lista **Coluna de origem** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-149">Select **EnglishProductSubcategoryName** in the **Source column** list and then click **OK**.</span></span>

16. <span data-ttu-id="3d19d-150">Crie uma nova hierarquia definida pelo usuário chamada **categorias de produto** com os seguintes níveis, em ordem de cima para baixo: `Category` , `Subcategory` e **nome do produto**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-150">Create a new user-defined hierarchy called **Product Categories** with the following levels, in order from top to bottom: `Category`, `Subcategory`, and **Product Name**.</span></span>

17. <span data-ttu-id="3d19d-151">Especifique `All Products` como o valor para a propriedade de todos os **Membros** da hierarquia definida pelo usuário categorias de produtos.</span><span class="sxs-lookup"><span data-stu-id="3d19d-151">Specify `All Products` as the value for the **AllMemberName** property of the Product Categories user-defined hierarchy.</span></span>

## <a name="browsing-the-user-defined-hierarchies-in-the-product-dimension"></a><span data-ttu-id="3d19d-152">Navegando nas hierarquias definidas pelo usuário na dimensão Produto</span><span class="sxs-lookup"><span data-stu-id="3d19d-152">Browsing the User-Defined Hierarchies in the Product Dimension</span></span>

1.  <span data-ttu-id="3d19d-153">Na barra de ferramentas da guia **Estrutura da Dimensão** do **Designer de Dimensão** da dimensão **Produto** , clique em **Processo**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-153">On the toolbar of the **Dimension Structure** tab of **Dimension Designer** for the **Product** dimension, click **Process**.</span></span>

2.  <span data-ttu-id="3d19d-154">Clique em **Sim** para criar e implantar o projeto. Depois, clique em **Executar** para processar a dimensão **Produto** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-154">Click **Yes** to build and deploy the project, and then click **Run** to process the **Product** dimension.</span></span>

3.  <span data-ttu-id="3d19d-155">Quando o processamento for concluído com êxito, expanda **Processamento da dimensão ‘Produto’ concluído com êxito** na caixa de diálogo **Progresso do Processo** , **Processamento do atributo de dimensão ‘Nome do Produto’ concluído**e, por fim, expanda **Consultas SQL 1**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-155">When processing has succeeded, expand **Processing Dimension 'Product' completed successfully** in the **Process Progress** dialog box, expand **Processing Dimension Attribute 'Product Name' completed**, and then expand **SQL queries 1**.</span></span>

4.  <span data-ttu-id="3d19d-156">Clique na consulta SELECT DISTINCT e em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-156">Click the SELECT DISTINCT query and then click **View Details**.</span></span>

     <span data-ttu-id="3d19d-157">Observe que uma cláusula WHERE foi adicionada à cláusula SELECT DISTINCT que remove os produtos que não têm nenhum valor na coluna ProductSubcategoryKey, como mostra a imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="3d19d-157">Notice that a WHERE clause has been added to the SELECT DISTINCT clause that removes those products that have no value in the ProductSubcategoryKey column, as shown in the following image.</span></span>

     <span data-ttu-id="3d19d-158">![Cláusula SELECT DISTINCT que mostra a cláusula WHERE](../../2014/tutorials/media/l4-productnametraceline-1.gif "Cláusula SELECT DISTINCT que mostra a cláusula WHERE")</span><span class="sxs-lookup"><span data-stu-id="3d19d-158">![SELECT DISTINCT clause showing WHERE clause](../../2014/tutorials/media/l4-productnametraceline-1.gif "SELECT DISTINCT clause showing WHERE clause")</span></span>

5.  <span data-ttu-id="3d19d-159">Clique em **Fechar** três vezes para fechar todas as caixas de diálogo em processamento.</span><span class="sxs-lookup"><span data-stu-id="3d19d-159">Click **Close** three times to close all processing dialog boxes.</span></span>

6.  <span data-ttu-id="3d19d-160">Clique na guia **Navegador** do Designer de Dimensão da dimensão **Produto** e clique em **Reconectar**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-160">Click the **Browser** tab in Dimension Designer for the **Product** dimension, and then click **Reconnect**.</span></span>

7.  <span data-ttu-id="3d19d-161">Verifique se **as linhas de modelo do produto** aparecem na lista **hierarquia** , expanda `All Products` e expanda **componentes**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-161">Verify that **Product Model Lines** appears in the **Hierarchy** list, expand `All Products`, and then expand **Components**.</span></span>

8.  <span data-ttu-id="3d19d-162">Selecione **categorias de produtos** na lista **hierarquia** , expanda `All Products` e expanda **componentes**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-162">Select **Product Categories** in the **Hierarchy** list, expand `All Products`, and then expand **Components**.</span></span>

     <span data-ttu-id="3d19d-163">Observe que nenhum dos componentes do assembly é exibido.</span><span class="sxs-lookup"><span data-stu-id="3d19d-163">Notice that none of the assembly components appear.</span></span>

 <span data-ttu-id="3d19d-164">Para modificar o comportamento mencionado na tarefa anterior, você habilitará a propriedade **UnknownMember** da dimensão Products, definirá um valor para a propriedade **UnknownMemberName** , definirá a propriedade **NullProcessing** para os atributos de `Subcategory` nome de **modelo** e como **UnknownMember**, definirá o `Category` atributo como um atributo relacionado do `Subcategory` atributo e, em seguida, definirá o atributo de **linha de produto** como um atributo relacionado do atributo de nome de **modelo** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-164">To modify the behavior mentioned in the previous task, you will enable the **UnknownMember** property of the Products dimension, set a value for the **UnknownMemberName** property, set the **NullProcessing** property for the `Subcategory` and **Model Name** attributes to **UnknownMember**, define the `Category` attribute as a related attribute of the `Subcategory` attribute, and then define the **Product Line** attribute as a related attribute of the **Model Name** attribute.</span></span> <span data-ttu-id="3d19d-165">Essas ações farão com que o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] use o valor do nome do membro desconhecido para cada produto que não tem um valor para a coluna **SubcategoryKey** , como você verá na próxima tarefa.</span><span class="sxs-lookup"><span data-stu-id="3d19d-165">These steps will cause [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to use the unknown member name value for each product that does not have a value for the **SubcategoryKey** column, as you will see in the following task.</span></span>

## <a name="enabling-the-unknown-member-defining-attribute-relationships-and-specifying-custom-processing-properties-for-nulls"></a><span data-ttu-id="3d19d-166">Ativando o membro desconhecido, definindo relações de atributo e especificando as propriedades de processamento personalizado como nulas</span><span class="sxs-lookup"><span data-stu-id="3d19d-166">Enabling the Unknown Member, Defining Attribute Relationships, and Specifying Custom Processing Properties for Nulls</span></span>

1.  <span data-ttu-id="3d19d-167">Clique na guia **Estrutura de Dimensão** no Designer de Dimensão da dimensão **Produto** e selecione **Produto** no painel **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-167">Click the **Dimension Structure** tab in Dimension Designer for the **Product** dimension, and then select **Product** in the **Attributes** pane.</span></span>

2.  <span data-ttu-id="3d19d-168">Na janela **Propriedades** , altere a propriedade **UnknownMember** para **visível**e, em seguida, altere o valor da propriedade **UnknownMemberName** para `Assembly Components` .</span><span class="sxs-lookup"><span data-stu-id="3d19d-168">In the **Properties** window, change the **UnknownMember** property to **Visible**, and then change the value for the **UnknownMemberName** property to `Assembly Components`.</span></span>

     <span data-ttu-id="3d19d-169">Alterar a propriedade **UnknownMember** para **Visível** ou **Oculto** habilita a propriedade **UnknownMember** da dimensão.</span><span class="sxs-lookup"><span data-stu-id="3d19d-169">Changing the **UnknownMember** property to either **Visible** or **Hidden** enables the **UnknownMember** property for the dimension.</span></span>

3.  <span data-ttu-id="3d19d-170">Clique na guia **Relações de Atributo** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-170">Click the **Attribute Relationships** tab.</span></span>

4.  <span data-ttu-id="3d19d-171">No diagrama, clique com o botão direito do mouse no `Subcategory` atributo e selecione **nova relação de atributo**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-171">In the diagram, right-click the `Subcategory` attribute and then select **New Attribute Relationship**.</span></span>

5.  <span data-ttu-id="3d19d-172">Na caixa de diálogo **criar relação de atributo** , o **atributo de origem** é `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="3d19d-172">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is `Subcategory`.</span></span> <span data-ttu-id="3d19d-173">Defina o **atributo relacionado** como `Category` .</span><span class="sxs-lookup"><span data-stu-id="3d19d-173">Set the **Related Attribute** to `Category`.</span></span> <span data-ttu-id="3d19d-174">Deixe o tipo de relação definido como **Flexível**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-174">Leave the relationship type set to **Flexible**.</span></span>

6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

7.  <span data-ttu-id="3d19d-175">No painel **Atributos** , selecione **Subcategoria**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-175">In the **Attributes** pane, select **Subcategory.**</span></span>

8.  <span data-ttu-id="3d19d-176">Na janela Propriedades, expanda a propriedade **KeyColumns** e depois a propriedade **DimProductSubcategory.ProductSubcategoryKey (Integer)** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-176">In the Properties window, expand the **KeyColumns** property and then expand the **DimProductSubcategory.ProductSubcategoryKey (Integer)** property.</span></span>

9. <span data-ttu-id="3d19d-177">Altere a propriedade **NullProcessing** para **UnknownMember**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-177">Change the **NullProcessing** property to **UnknownMember**.</span></span>

10. <span data-ttu-id="3d19d-178">No painel **Atributos** , selecione **Nome do Modelo**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-178">In the **Attributes** pane, select **Model Name**.</span></span>

11. <span data-ttu-id="3d19d-179">Na janela Propriedades, expanda a propriedade **KeyColumns** e depois a propriedade **Product.ModelName (WChar)** .</span><span class="sxs-lookup"><span data-stu-id="3d19d-179">In the Properties window, expand the **KeyColumns** property and then expand the **Product.ModelName (WChar)** property.</span></span>

12. <span data-ttu-id="3d19d-180">Altere a propriedade **NullProcessing** para **UnknownMember**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-180">Change the **NullProcessing** property to **UnknownMember**.</span></span>

     <span data-ttu-id="3d19d-181">Devido a essas alterações, quando o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] encontra um valor nulo para o `Subcategory` atributo ou o atributo de **nome do modelo** durante o processamento, o valor do membro desconhecido será substituído como o valor da chave e as hierarquias definidas pelo usuário serão construídas corretamente.</span><span class="sxs-lookup"><span data-stu-id="3d19d-181">Because of these changes, when [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] encounters a null value for the `Subcategory` attribute or the **Model Name** attribute during processing, the unknown member value will be substituted as the key value, and the user-defined hierarchies will be constructed correctly.</span></span>

## <a name="browsing-the-product-dimension-again"></a><span data-ttu-id="3d19d-182">Navegando na dimensão Produto novamente</span><span class="sxs-lookup"><span data-stu-id="3d19d-182">Browsing the Product Dimension Again</span></span>

1.  <span data-ttu-id="3d19d-183">No menu **Compilar** , clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-183">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="3d19d-184">Quando a implantação for concluída com êxito, clique na guia **Navegador** do Designer de Dimensão da dimensão **Produto** e clique no botão **Reconectar**.</span><span class="sxs-lookup"><span data-stu-id="3d19d-184">When deployment has successfully completed, click the **Browser** tab in Dimension Designer for the **Product** dimension, and then click **Reconnect**.</span></span>

3.  <span data-ttu-id="3d19d-185">Verifique se **categorias de produto** está selecionada na lista **hierarquia** e, em seguida, expanda `All Products` .</span><span class="sxs-lookup"><span data-stu-id="3d19d-185">Verify that **Product Categories** is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>

     <span data-ttu-id="3d19d-186">Observe que Componentes do Assembly aparece como um novo membro do nível Categoria.</span><span class="sxs-lookup"><span data-stu-id="3d19d-186">Notice that Assembly Components appears as a new member of the Category level.</span></span>

4.  <span data-ttu-id="3d19d-187">Expanda o `Assembly Components` membro do `Category` nível e expanda o `Assembly Components` membro do `Subcategory` nível.</span><span class="sxs-lookup"><span data-stu-id="3d19d-187">Expand the `Assembly Components` member of the `Category` level and then expand the `Assembly Components` member of the `Subcategory` level.</span></span>

     <span data-ttu-id="3d19d-188">Observe que todos os componentes do assembly agora são exibidos no nível **Nome do Produto** , como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="3d19d-188">Notice that all the assembly components now appear at the **Product Name** level, as shown in the following image.</span></span>

     <span data-ttu-id="3d19d-189">![Nível Nome do Produto mostrando componentes de assembly](../../2014/tutorials/media/l4-assemblycomponents-1.gif "Nível Nome do Produto mostrando componentes de assembly")</span><span class="sxs-lookup"><span data-stu-id="3d19d-189">![Product Name level showing assembly components](../../2014/tutorials/media/l4-assemblycomponents-1.gif "Product Name level showing assembly components")</span></span>

## <a name="next-lesson"></a><span data-ttu-id="3d19d-190">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="3d19d-190">Next Lesson</span></span>
 [<span data-ttu-id="3d19d-191">Lição 5: Como definir relações entre grupos de medidas e dimensões</span><span class="sxs-lookup"><span data-stu-id="3d19d-191">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>](lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)


