---
title: Modificando a dimensão do cliente | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5b5aed99-1760-4bc7-b248-52ecb0b97ebc
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd5c5c47205a89f8429b0b6f0ba55da266d5e811
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576038"
---
# <a name="modifying-the-customer-dimension"></a><span data-ttu-id="6cb63-102">Modificando a dimensão Cliente</span><span class="sxs-lookup"><span data-stu-id="6cb63-102">Modifying the Customer Dimension</span></span>
  <span data-ttu-id="6cb63-103">Há várias formas de aumentar a facilidade de uso e melhorar a funcionalidade das dimensões em um cubo.</span><span class="sxs-lookup"><span data-stu-id="6cb63-103">There are many different ways that you can increase the usability and functionality of the dimensions in a cube.</span></span> <span data-ttu-id="6cb63-104">Nas tarefas deste tópico, você modificará a dimensão Customer.</span><span class="sxs-lookup"><span data-stu-id="6cb63-104">In the tasks in this topic, you modify the Customer dimension.</span></span>  
  
## <a name="renaming-attributes"></a><span data-ttu-id="6cb63-105">Renomeando atributos</span><span class="sxs-lookup"><span data-stu-id="6cb63-105">Renaming Attributes</span></span>  
 <span data-ttu-id="6cb63-106">Você pode alterar nomes de atributo na guia **Estrutura da Dimensão** do Designer de Dimensão.</span><span class="sxs-lookup"><span data-stu-id="6cb63-106">You can change attribute names with the **Dimension Structure** tab of Dimension Designer.</span></span>  
  
#### <a name="to-rename-an-attribute"></a><span data-ttu-id="6cb63-107">Para renomear um atributo</span><span class="sxs-lookup"><span data-stu-id="6cb63-107">To rename an attribute</span></span>  
  
1.  <span data-ttu-id="6cb63-108">Mude para o **Designer de Dimensão** da dimensão Cliente no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cb63-108">Switch to **Dimension Designer** for the Customer dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6cb63-109">Para fazer isso, clique duas vezes na dimensão **Cliente** no nó **Dimensões** do Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="6cb63-109">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="6cb63-110">No painel **Atributos** , clique com o botão direito do mouse em **Nome do País/Região em Inglês**e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-110">In the **Attributes** pane, right-click **English Country Region Name**, and then click **Rename**.</span></span> <span data-ttu-id="6cb63-111">Altere o nome do atributo para `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-111">Change the name of the attribute to `Country-Region`.</span></span>  
  
3.  <span data-ttu-id="6cb63-112">Altere os nomes dos seguintes atributos da mesma maneira:</span><span class="sxs-lookup"><span data-stu-id="6cb63-112">Change the names of the following attributes in the same manner:</span></span>  
  
    -   <span data-ttu-id="6cb63-113">Atributo de **educação em inglês** – alterar para`Education`</span><span class="sxs-lookup"><span data-stu-id="6cb63-113">**English Education** attribute - change to `Education`</span></span>  
  
    -   <span data-ttu-id="6cb63-114">Atributo de **ocupação em inglês** – alterar para`Occupation`</span><span class="sxs-lookup"><span data-stu-id="6cb63-114">**English Occupation** attribute - change to `Occupation`</span></span>  
  
    -   <span data-ttu-id="6cb63-115">Atributo de **nome da província do estado** – alterar para`State-Province`</span><span class="sxs-lookup"><span data-stu-id="6cb63-115">**State Province Name** attribute - change to `State-Province`</span></span>  
  
4.  <span data-ttu-id="6cb63-116">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="6cb63-117">Criando uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="6cb63-117">Creating a Hierarchy</span></span>  
 <span data-ttu-id="6cb63-118">Você pode criar uma nova hierarquia arrastando um atributo do painel **Atributos** até o painel **Hierarquias** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-118">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="6cb63-119">Para criar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="6cb63-119">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="6cb63-120">Arraste o `Country-Region` atributo do painel **atributos** até o painel **hierarquias** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-120">Drag the `Country-Region` attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="6cb63-121">Arraste o `State-Province` atributo do painel **atributos** até a **\<new level>** célula no painel **hierarquias** , sob o `Country-Region` nível.</span><span class="sxs-lookup"><span data-stu-id="6cb63-121">Drag the `State-Province` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `Country-Region` level.</span></span>  
  
3.  <span data-ttu-id="6cb63-122">Arraste o atributo **cidade** do painel **atributos** até a **\<new level>** célula no painel **hierarquias** , sob o `State-Province` nível.</span><span class="sxs-lookup"><span data-stu-id="6cb63-122">Drag the **City** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `State-Province` level.</span></span>  
  
4.  <span data-ttu-id="6cb63-123">No painel **hierarquias** da guia **estrutura da dimensão** , clique com o botão direito do mouse na barra de título da hierarquia **hierarquia** , selecione **renomear**e digite `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-123">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, select **Rename**, and then type `Customer Geography`.</span></span>  
  
     <span data-ttu-id="6cb63-124">O nome da hierarquia agora é `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-124">The name of the hierarchy is now `Customer Geography`.</span></span>  
  
5.  <span data-ttu-id="6cb63-125">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-125">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="6cb63-126">Adicionando um cálculo nomeado</span><span class="sxs-lookup"><span data-stu-id="6cb63-126">Adding a Named Calculation</span></span>  
 <span data-ttu-id="6cb63-127">É possível adicionar um cálculo nomeado, que é uma expressão SQL representada como uma coluna calculada, a uma tabela em uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6cb63-127">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="6cb63-128">A expressão se parece e se comporta como uma coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="6cb63-128">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="6cb63-129">Cálculos nomeados permitem que você estenda o esquema relacional de tabelas existentes em uma exibição da fonte de dados sem modificar a tabela na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="6cb63-129">Named calculations let you extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="6cb63-130">Para obter mais informações, consulte [Definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="6cb63-130">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="6cb63-131">Para adicionar um cálculo nomeado</span><span class="sxs-lookup"><span data-stu-id="6cb63-131">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="6cb63-132">Abra a exibição da fonte de dados do \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* clicando duas vezes nela na pasta **exibições da fonte de dados** em Gerenciador de soluções.</span><span class="sxs-lookup"><span data-stu-id="6cb63-132">Open the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view by double-clicking it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="6cb63-133">No painel **Tabelas** à esquerda, clique com o botão direito do mouse em **Cliente**e clique em **Novo Cálculo Nomeado**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-133">In the **Tables** pane on the left, right-click **Customer**, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="6cb63-134">Na caixa de diálogo **criar cálculo nomeado** , digite `FullName` a caixa **nome da coluna** e digite ou copie e cole a seguinte `CASE` instrução na caixa **expressão** :</span><span class="sxs-lookup"><span data-stu-id="6cb63-134">In the **Create Named Calculation** dialog box, type `FullName` in the **Column name** box, and then type or copy and paste the following `CASE` statement in the **Expression** box:</span></span>  
  
    ```  
    CASE  
       WHEN MiddleName IS NULL THEN  
       FirstName + ' ' + LastName  
       ELSE  
       FirstName + ' ' + MiddleName + ' ' + LastName  
    END  
    ```  
  
     <span data-ttu-id="6cb63-135">A `CASE` instrução concatena as colunas **FirstName**, **MiddleName**e **LastName** em uma única coluna que será usada na dimensão Customer como o nome exibido para o atributo **Customer** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-135">The `CASE` statement concatenates the **FirstName**, **MiddleName**, and **LastName** columns into a single column that you will use in the Customer dimension as the displayed name for the **Customer** attribute.</span></span>  
  
4.  <span data-ttu-id="6cb63-136">Clique em **OK**e expanda **Cliente** no painel **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-136">Click **OK**, and then expand **Customer** in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="6cb63-137">O `FullName` cálculo nomeado aparece na lista de colunas na tabela Customer, com um ícone que indica que se trata de um cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="6cb63-137">The `FullName` named calculation appears in the list of columns in the Customer table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="6cb63-138">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-138">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="6cb63-139">No painel **Tabelas** , clique com o botão direito do mouse em **Cliente**e selecione **Explorar Dados**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-139">In the **Tables** pane, right-click **Customer**, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="6cb63-140">Examine a última coluna na exibição **Explorar Tabela Cliente** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-140">Review the last column in the **Explore Customer Table** view.</span></span>  
  
     <span data-ttu-id="6cb63-141">Observe que a `FullName` coluna aparece na exibição da fonte de dados, concatenando corretamente os dados de várias colunas da fonte de dados subjacente e sem modificar a fonte de dados original.</span><span class="sxs-lookup"><span data-stu-id="6cb63-141">Notice that the `FullName` column appears in the data source view, correctly concatenating data from several columns from the underlying data source and without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="6cb63-142">Feche a guia **Explorar Tabela Cliente** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-142">Close the **Explore Customer Table** tab.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="6cb63-143">Usando o cálculo nomeado para nomes de membros</span><span class="sxs-lookup"><span data-stu-id="6cb63-143">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="6cb63-144">Depois de criar um cálculo nomeado na exibição da fonte de dados, você pode usá-lo como propriedade para um atributo.</span><span class="sxs-lookup"><span data-stu-id="6cb63-144">After you have created a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="6cb63-145">Para usar o cálculo nomeado para nomes de membros</span><span class="sxs-lookup"><span data-stu-id="6cb63-145">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="6cb63-146">Alterne para o Designer de Dimensão da dimensão Cliente.</span><span class="sxs-lookup"><span data-stu-id="6cb63-146">Switch to Dimension Designer for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="6cb63-147">No painel **Atributos** da guia **Estrutura da Dimensão** , clique no atributo **Chave de Cliente** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-147">In the **Attributes** pane of the **Dimension Structure** tab, click the **Customer Key** attribute.</span></span>  
  
3.  <span data-ttu-id="6cb63-148">Abra a janela Propriedades e clique no botão **Ocultar Automaticamente** na barra de título de forma que ela permaneça aberta.</span><span class="sxs-lookup"><span data-stu-id="6cb63-148">Open the Properties window and click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="6cb63-149">No campo propriedade de **nome** , digite `Full Name` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-149">In the **Name** property field, type `Full Name`.</span></span>  
  
5.  <span data-ttu-id="6cb63-150">Clique no campo de propriedade **NameColumn** na parte inferior e, em seguida, clique no botão procurar (**...**) para abrir a caixa de diálogo **coluna de nome** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-150">Click in the **NameColumn** property field at the bottom, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
6.  <span data-ttu-id="6cb63-151">Selecione `FullName` na parte inferior da lista **coluna de origem** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-151">Select `FullName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="6cb63-152">Na guia estrutura de dimensões, arraste o `Full Name` atributo do painel **atributos** para a **\<new level>** célula do painel **hierarquias** , sob o nível **cidade** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-152">In the Dimensions Structure tab, drag the `Full Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **City** level.</span></span>  
  
8.  <span data-ttu-id="6cb63-153">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-153">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-display-folders"></a><span data-ttu-id="6cb63-154">Definindo pastas de exibição</span><span class="sxs-lookup"><span data-stu-id="6cb63-154">Defining Display Folders</span></span>  
 <span data-ttu-id="6cb63-155">Você pode usar pastas de exibição para agrupar hierarquias de usuário e atributo em estruturas de pastas, a fim de aumentar a facilidade de uso.</span><span class="sxs-lookup"><span data-stu-id="6cb63-155">You can use display folders to group user and attribute hierarchies into folder structures to increase usability.</span></span>  
  
#### <a name="to-define-display-folders"></a><span data-ttu-id="6cb63-156">Para definir pastas de exibição</span><span class="sxs-lookup"><span data-stu-id="6cb63-156">To define display folders</span></span>  
  
1.  <span data-ttu-id="6cb63-157">Abra a guia **Estrutura da Dimensão** da dimensão Cliente.</span><span class="sxs-lookup"><span data-stu-id="6cb63-157">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="6cb63-158">No painel **Atributos** , selecione os seguintes atributos pressionando e mantendo a tecla CTRL pressionada enquanto clica em cada um deles:</span><span class="sxs-lookup"><span data-stu-id="6cb63-158">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="6cb63-159">**Cidade**</span><span class="sxs-lookup"><span data-stu-id="6cb63-159">**City**</span></span>  
  
    -   `Country-Region`  
  
    -   <span data-ttu-id="6cb63-160">**Código postal**</span><span class="sxs-lookup"><span data-stu-id="6cb63-160">**Postal Code**</span></span>  
  
    -   `State-Province`  
  
3.  <span data-ttu-id="6cb63-161">No janela Propriedades, clique no campo de propriedade **AttributeHierarchyDisplayFolder** na parte superior (talvez seja necessário apontar para ele para ver o nome completo) e, em seguida, digite `Location` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-161">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top (you might need to point to it to see the full name), and then type `Location`.</span></span>  
  
4.  <span data-ttu-id="6cb63-162">No painel **hierarquias** , clique em `Customer Geography` e, na janela Propriedades à direita, selecione `Location` como o valor da propriedade **DisplayFolder** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-162">In the **Hierarchies** pane, click `Customer Geography`, and then in the Properties window on the right, select `Location` as the value of the **DisplayFolder** property.</span></span>  
  
5.  <span data-ttu-id="6cb63-163">No painel **Atributos** , selecione os seguintes atributos pressionando e mantendo a tecla CTRL pressionada enquanto clica em cada um deles:</span><span class="sxs-lookup"><span data-stu-id="6cb63-163">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="6cb63-164">**Distância do Trabalho**</span><span class="sxs-lookup"><span data-stu-id="6cb63-164">**Commute Distance**</span></span>  
  
    -   `Education`  
  
    -   <span data-ttu-id="6cb63-165">**Sexo**</span><span class="sxs-lookup"><span data-stu-id="6cb63-165">**Gender**</span></span>  
  
    -   <span data-ttu-id="6cb63-166">**Sinalizador do Proprietário da Casa**</span><span class="sxs-lookup"><span data-stu-id="6cb63-166">**House Owner Flag**</span></span>  
  
    -   <span data-ttu-id="6cb63-167">**Estado Civil**</span><span class="sxs-lookup"><span data-stu-id="6cb63-167">**Marital Status**</span></span>  
  
    -   <span data-ttu-id="6cb63-168">**Número de Carros**</span><span class="sxs-lookup"><span data-stu-id="6cb63-168">**Number Cars Owned**</span></span>  
  
    -   <span data-ttu-id="6cb63-169">**Número de filhos em casa**</span><span class="sxs-lookup"><span data-stu-id="6cb63-169">**Number Children At Home**</span></span>  
  
    -   `Occupation`  
  
    -   <span data-ttu-id="6cb63-170">**Total de Filhos**</span><span class="sxs-lookup"><span data-stu-id="6cb63-170">**Total Children**</span></span>  
  
    -   <span data-ttu-id="6cb63-171">**Renda Anual**</span><span class="sxs-lookup"><span data-stu-id="6cb63-171">**Yearly Income**</span></span>  
  
6.  <span data-ttu-id="6cb63-172">No janela Propriedades, clique no campo de propriedade **AttributeHierarchyDisplayFolder** na parte superior e, em seguida, digite `Demographic` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-172">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top, and then type `Demographic`.</span></span>  
  
7.  <span data-ttu-id="6cb63-173">No painel **Atributos** , selecione os seguintes atributos pressionando e mantendo a tecla CTRL pressionada enquanto clica em cada um deles:</span><span class="sxs-lookup"><span data-stu-id="6cb63-173">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="6cb63-174">**Endereço de Email**</span><span class="sxs-lookup"><span data-stu-id="6cb63-174">**Email Address**</span></span>  
  
    -   <span data-ttu-id="6cb63-175">**Telemóvel**</span><span class="sxs-lookup"><span data-stu-id="6cb63-175">**Phone**</span></span>  
  
8.  <span data-ttu-id="6cb63-176">Na janela Propriedades, clique no campo de propriedade **AttributeHierarchyDisplayFolder** e digite `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-176">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field and type `Contacts`.</span></span>  
  
9. <span data-ttu-id="6cb63-177">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-177">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns"></a><span data-ttu-id="6cb63-178">Definindo KeyColumns compostos</span><span class="sxs-lookup"><span data-stu-id="6cb63-178">Defining Composite KeyColumns</span></span>  
 <span data-ttu-id="6cb63-179">A propriedade **KeyColumns** contém a coluna ou as colunas que representam a chave do atributo.</span><span class="sxs-lookup"><span data-stu-id="6cb63-179">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="6cb63-180">Nesta lição, você criará uma chave composta para a **cidade** e os `State-Province` atributos.</span><span class="sxs-lookup"><span data-stu-id="6cb63-180">In this lesson, you create a composite key for the **City** and `State-Province` attributes.</span></span> <span data-ttu-id="6cb63-181">As chaves compostas podem ser úteis quando você precisa identificar com exclusividade um atributo.</span><span class="sxs-lookup"><span data-stu-id="6cb63-181">Composite keys can be helpful when you need to uniquely identify an attribute.</span></span> <span data-ttu-id="6cb63-182">Por exemplo, quando você define relações de atributo posteriormente neste tutorial, um atributo **City** deve identificar exclusivamente um `State-Province` atributo.</span><span class="sxs-lookup"><span data-stu-id="6cb63-182">For example, when you define attribute relationships later in this tutorial, a **City** attribute must uniquely identify a `State-Province` attribute.</span></span> <span data-ttu-id="6cb63-183">Porém, pode haver várias cidades com o mesmo nome em estados diferentes.</span><span class="sxs-lookup"><span data-stu-id="6cb63-183">However, there could be several cities with the same name in different states.</span></span> <span data-ttu-id="6cb63-184">Por isso, você criará uma chave composta formada pelas colunas **StateProvinceName** e **City** para o atributo **Cidade** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-184">For this reason, you will create a composite key that is composed of the **StateProvinceName** and **City** columns for the **City** attribute.</span></span> <span data-ttu-id="6cb63-185">Para obter mais informações, consulte [Modificar a propriedade KeyColumn de um atributo](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="6cb63-185">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-city-attribute"></a><span data-ttu-id="6cb63-186">Para definir KeyColumns compostos para o atributo Cidade</span><span class="sxs-lookup"><span data-stu-id="6cb63-186">To define composite KeyColumns for the City attribute</span></span>  
  
1.  <span data-ttu-id="6cb63-187">Abra a guia **Estrutura da Dimensão** da dimensão Cliente.</span><span class="sxs-lookup"><span data-stu-id="6cb63-187">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="6cb63-188">No painel **Atributos** , clique no atributo **Cidade** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-188">In the **Attributes** pane, click the **City** attribute.</span></span>  
  
3.  <span data-ttu-id="6cb63-189">Na janela **Propriedades** , clique no campo **KeyColumns** próximo ao final e clique no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="6cb63-189">In the **Properties** window, click in the **KeyColumns** field near the bottom, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="6cb63-190">Na caixa de diálogo **Colunas de Chave** , na lista **Colunas Disponíveis** , selecione a coluna **StateProvinceName**e clique no botão **>** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-190">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **StateProvinceName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="6cb63-191">As colunas **City** e **StateProvinceName** agora são exibidas na lista **Colunas de Chave** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-191">The **City** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="6cb63-192">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-192">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="6cb63-193">Para definir a propriedade **NameColumn** do atributo **Cidade** , clique no campo **NameColumn** na janela Propriedades e clique no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="6cb63-193">To set the **NameColumn** property of the **City** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="6cb63-194">Na caixa de diálogo **Coluna de Nome** , na lista **Coluna de origem** , selecione **Cidade**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-194">In the **Name Column** dialog box, in the **Source column** list, select **City**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="6cb63-195">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-195">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-state-province-attribute"></a><span data-ttu-id="6cb63-196">Para definir KeyColumns compostos para o atributo State-Province</span><span class="sxs-lookup"><span data-stu-id="6cb63-196">To define composite KeyColumns for the State-Province attribute</span></span>  
  
1.  <span data-ttu-id="6cb63-197">Verifique se a guia **Estrutura da Dimensão** da dimensão Customer está aberta.</span><span class="sxs-lookup"><span data-stu-id="6cb63-197">Make sure the **Dimension Structure** tab for the Customer dimension is open.</span></span>  
  
2.  <span data-ttu-id="6cb63-198">No painel **atributos** , clique no `State-Province` atributo.</span><span class="sxs-lookup"><span data-stu-id="6cb63-198">In the **Attributes** pane, click the `State-Province` attribute.</span></span>  
  
3.  <span data-ttu-id="6cb63-199">Na janela **Propriedades** , clique no campo **KeyColumns** e no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="6cb63-199">In the **Properties** window, click in the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="6cb63-200">Na caixa de diálogo **Colunas de Chave** , na lista **Colunas Disponíveis** , selecione a coluna **EnglishCountryRegionName**e clique no botão **>** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-200">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **EnglishCountryRegionName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="6cb63-201">As colunas **EnglishCountryRegionName** e **StateProvinceName** agora são exibidas na lista **Colunas de Chave** .</span><span class="sxs-lookup"><span data-stu-id="6cb63-201">The **EnglishCountryRegionName** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="6cb63-202">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-202">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="6cb63-203">Para definir a propriedade **NameColumn** do `State-Province` atributo, clique no campo **NameColumn** na janela Propriedades e, em seguida, clique no botão procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="6cb63-203">To set the **NameColumn** property of the `State-Province` attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="6cb63-204">Na caixa de diálogo **Coluna de Nome** , na lista **Coluna de origem** , selecione **StateProvinceName**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-204">In the **Name Column** dialog box, in the **Source column** list, select **StateProvinceName**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="6cb63-205">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-205">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="6cb63-206">Definindo relações de atributo</span><span class="sxs-lookup"><span data-stu-id="6cb63-206">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="6cb63-207">Se os dados subjacentes permitirem, você também deve definir relações de atributo entre atributos.</span><span class="sxs-lookup"><span data-stu-id="6cb63-207">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="6cb63-208">Definir relações de atributo acelera o processamento de dimensões, partições e consultas.</span><span class="sxs-lookup"><span data-stu-id="6cb63-208">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="6cb63-209">Para obter mais informações, consulte [Definir relações de atributo](multidimensional-models/attribute-relationships-define.md) e [Relações de atributo](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="6cb63-209">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="6cb63-210">Para definir relações de atributo</span><span class="sxs-lookup"><span data-stu-id="6cb63-210">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="6cb63-211">No **Designer de dimensão** da dimensão cliente, clique na guia **relações de atributo** . Talvez seja necessário aguardar.</span><span class="sxs-lookup"><span data-stu-id="6cb63-211">In the **Dimension Designer** for the Customer dimension, click the **Attribute Relationships** tab. You might need to wait.</span></span>  
  
2.  <span data-ttu-id="6cb63-212">No diagrama, clique com o botão direito do mouse no atributo **Cidade** e clique em **Nova Relação de Atributo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-212">In the diagram, right-click the **City** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="6cb63-213">Na caixa de diálogo **Criar Relação de Atributo** , o **Atributo de Origem** é **Cidade**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-213">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **City**.</span></span> <span data-ttu-id="6cb63-214">Defina o **atributo relacionado** como `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-214">Set the **Related Attribute** to `State-Province`.</span></span>  
  
4.  <span data-ttu-id="6cb63-215">Na lista **Tipo de relação** , defina o tipo de relação como **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-215">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="6cb63-216">O tipo de relação é **Rígida** porque as relações entre os membros não mudarão com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="6cb63-216">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span> <span data-ttu-id="6cb63-217">Por exemplo, não seria comum uma cidade se tornar parte de um estado ou província diferente.</span><span class="sxs-lookup"><span data-stu-id="6cb63-217">For example, it would be unusual for a city to become part of a different state or province.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="6cb63-218">No diagrama, clique com o botão direito do mouse no `State-Province` atributo e selecione **nova relação de atributo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-218">In the diagram, right-click the `State-Province` attribute and then select **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="6cb63-219">Na caixa de diálogo **criar relação de atributo** , o **atributo de origem** é `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-219">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is `State-Province`.</span></span> <span data-ttu-id="6cb63-220">Defina o **atributo relacionado** como `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="6cb63-220">Set the **Related Attribute** to `Country-Region`.</span></span>  
  
8.  <span data-ttu-id="6cb63-221">Na lista **Tipo de relação** , defina o tipo de relação como **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-221">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="6cb63-222">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-222">Click **OK**.</span></span>  
  
10. <span data-ttu-id="6cb63-223">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-223">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-changes-processing-the-objects-and-viewing-the-changes"></a><span data-ttu-id="6cb63-224">Implantando alterações, processando objetos e exibindo alterações</span><span class="sxs-lookup"><span data-stu-id="6cb63-224">Deploying Changes, Processing the Objects, and Viewing the Changes</span></span>  
 <span data-ttu-id="6cb63-225">Depois de alterar atributos e hierarquias, você deve implantar as alterações e processar novamente os objetos relacionados para poder exibir as alterações.</span><span class="sxs-lookup"><span data-stu-id="6cb63-225">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-the-changes-process-the-objects-and-view-the-changes"></a><span data-ttu-id="6cb63-226">Para implantar alterações, processar objetos e exibir alterações</span><span class="sxs-lookup"><span data-stu-id="6cb63-226">To deploy the changes, process the objects, and view the changes</span></span>  
  
1.  <span data-ttu-id="6cb63-227">No menu **Compilar** do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-227">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="6cb63-228">Depois de receber a mensagem **Implantação Concluída com Êxito** , clique na guia **Navegador** do Designer de Dimensão da dimensão Customer e clique no botão Reconectar à esquerda da barra de ferramentas do designer.</span><span class="sxs-lookup"><span data-stu-id="6cb63-228">After you receive the **Deployment Completed Successfully** message, click the **Browser** tab of Dimension Designer for the Customer dimension, and then click the Reconnect button on the left side of the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="6cb63-229">Verifique se `Customer Geography` está selecionado na lista **hierarquia** e, no painel navegador, expanda **tudo**, **Austrália**, **novo Sul Gales**e, em seguida, clique em **COFF Harbour**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-229">Verify that `Customer Geography` is selected in the **Hierarchy** list, and then in the browser pane, expand **All**, expand **Australia**, expand **New South Wales**, and then expand **Coffs Harbour**.</span></span>  
  
     <span data-ttu-id="6cb63-230">O navegador exibe os clientes nesta cidade.</span><span class="sxs-lookup"><span data-stu-id="6cb63-230">The browser displays the customers in the city.</span></span>  
  
4.  <span data-ttu-id="6cb63-231">Mude para o **Designer de Cubo** do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cb63-231">Switch to **Cube Designer** for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="6cb63-232">Para fazer isso, clique duas vezes no cubo **Tutorial do Analysis Services** no nó **Cubos** do **Gerenciador de Soluções**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-232">To do this, double-click the **Analysis Services Tutorial** cube in the **Cubes** node of **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="6cb63-233">Clique na guia **Navegador** e no ícone Reconectar da barra de ferramentas do designer.</span><span class="sxs-lookup"><span data-stu-id="6cb63-233">Click the **Browser** tab, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
6.  <span data-ttu-id="6cb63-234">No painel **Grupo de Medidas** , expanda **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-234">In the **Measure Group** pane, expand **Customer**.</span></span>  
  
     <span data-ttu-id="6cb63-235">Observe que em vez de um longa lista de atributos, somente as pastas de exibição e os atributos que não têm valores de pasta de exibição aparecem sob Cliente.</span><span class="sxs-lookup"><span data-stu-id="6cb63-235">Notice that instead of a long list of attributes, only the display folders and the attributes that do not have display folder values appear underneath Customer.</span></span>  
  
7.  <span data-ttu-id="6cb63-236">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6cb63-236">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6cb63-237">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="6cb63-237">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6cb63-238">Modificando a dimensão Produto</span><span class="sxs-lookup"><span data-stu-id="6cb63-238">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="6cb63-239">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6cb63-239">See Also</span></span>  
 <span data-ttu-id="6cb63-240">[Referência de propriedades de atributo de dimensão](multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6cb63-240">[Dimension Attribute Properties Reference](multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="6cb63-241">[Remover um atributo de uma dimensão](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="6cb63-241">[Remove an Attribute from a Dimension](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span></span>  
 <span data-ttu-id="6cb63-242">[Renomear um atributo](multidimensional-models/attribute-properties-rename-an-attribute.md) </span><span class="sxs-lookup"><span data-stu-id="6cb63-242">[Rename an Attribute](multidimensional-models/attribute-properties-rename-an-attribute.md) </span></span>  
 [<span data-ttu-id="6cb63-243">Definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6cb63-243">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
