---
title: Modificando a dimensão de data | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4689d780-4bf6-4cf8-8fde-eb3f15dd668a
author: minewiskan
ms.author: owend
ms.openlocfilehash: b4978e9fe3acd93ddfdca707d2c2353bf171ba12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575439"
---
# <a name="modifying-the-date-dimension"></a><span data-ttu-id="abdfb-102">Modificando a dimensão de data</span><span class="sxs-lookup"><span data-stu-id="abdfb-102">Modifying the Date Dimension</span></span>
  <span data-ttu-id="abdfb-103">Na tarefa deste tópico, você criará uma hierarquia definida pelo usuário e alterará os nomes de membro exibidos nos atributos Date, Month, Calendar Quarter e Calendar Semester.</span><span class="sxs-lookup"><span data-stu-id="abdfb-103">In the tasks in this topic, you create a user-defined hierarchy and change the member names that are displayed for the Date, Month, Calendar Quarter, and Calendar Semester attributes.</span></span> <span data-ttu-id="abdfb-104">Você também definirá as chaves compostas para atributos, controlará a ordem de classificação dos membros de dimensão e definirá relações de atributo.</span><span class="sxs-lookup"><span data-stu-id="abdfb-104">You also define composite keys for attributes, control the sort order of dimension members, and define attribute relationships.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="abdfb-105">Adicionando um cálculo nomeado</span><span class="sxs-lookup"><span data-stu-id="abdfb-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="abdfb-106">É possível adicionar um cálculo nomeado, que é uma expressão SQL representada como uma coluna calculada, a uma tabela em uma exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="abdfb-106">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="abdfb-107">A expressão se parece e se comporta como uma coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="abdfb-107">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="abdfb-108">Os cálculos nomeados permitem que você estenda o esquema relacional de tabelas existentes em uma exibição de fonte de dados sem modificar a tabela na fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="abdfb-108">Named calculations enable you to extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="abdfb-109">Para obter mais informações, consulte [Definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="abdfb-109">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="abdfb-110">Para adicionar um cálculo nomeado</span><span class="sxs-lookup"><span data-stu-id="abdfb-110">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="abdfb-111">Para abrir a exibição de fonte de dados do **Adventure Works DW 2012** , clique duas vezes nela na pasta **Exibições da Fonte de Dados** do Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="abdfb-111">To open the **Adventure Works DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="abdfb-112">Próximo à parte inferior do painel **tabelas** , clique com o botão direito do mouse em `Date` e clique em **novo cálculo nomeado**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-112">Near the bottom of the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="abdfb-113">Na caixa de diálogo **criar cálculo nomeado** , digite `SimpleDate` a caixa **nome da coluna** e digite ou copie e cole a seguinte `DATENAME` instrução na caixa **expressão** :</span><span class="sxs-lookup"><span data-stu-id="abdfb-113">In the **Create Named Calculation** dialog box, type `SimpleDate` in the **Column name** box, and then type or copy and paste the following `DATENAME` statement in the **Expression** box:</span></span>  
  
    ```  
    DATENAME(mm, FullDateAlternateKey) + ' ' +  
    DATENAME(dd, FullDateAlternateKey) + ', ' +  
    DATENAME(yy, FullDateAlternateKey)  
    ```  
  
     <span data-ttu-id="abdfb-114">A instrução `DATENAME` extrai os valores de ano, mês e dia da coluna FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="abdfb-114">The `DATENAME` statement extracts the year, month, and day values from the FullDateAlternateKey column.</span></span> <span data-ttu-id="abdfb-115">Essa nova coluna poderá ser usada como o nome exibido para o atributo FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="abdfb-115">You will use this new column as the displayed name for the FullDateAlternateKey attribute.</span></span>  
  
4.  <span data-ttu-id="abdfb-116">Clique em **OK**e, em seguida, expanda `Date` no painel **tabelas** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-116">Click **OK**, and then expand `Date` in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="abdfb-117">O `SimpleDate` cálculo nomeado aparece na lista de colunas na tabela Date, com um ícone que indica que se trata de um cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="abdfb-117">The `SimpleDate` named calculation appears in the list of columns in the Date table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="abdfb-118">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-118">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="abdfb-119">No painel **tabelas** , clique com o botão direito do mouse em `Date` e clique em **explorar dados**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-119">In the **Tables** pane, right-click `Date`, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="abdfb-120">Role a tela para a direita para examinar a última coluna da exibição **Explorar Tabela Date** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-120">Scroll to the right to review the last column in the **Explore Date Table** view.</span></span>  
  
     <span data-ttu-id="abdfb-121">Observe que a `SimpleDate` coluna aparece na exibição da fonte de dados, concatenando corretamente os dados de várias colunas da fonte de dados subjacente, sem modificar a fonte de dados original.</span><span class="sxs-lookup"><span data-stu-id="abdfb-121">Notice that the `SimpleDate` column appears in the data source view, correctly concatenating data from several columns from the underlying data source, without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="abdfb-122">Feche a exibição **Explorar Tabela Date** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-122">Close the **Explore Date Table** view.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="abdfb-123">Usando o cálculo nomeado para nomes de membros</span><span class="sxs-lookup"><span data-stu-id="abdfb-123">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="abdfb-124">Após criar um cálculo nomeado na exibição da fonte de dados, você pode usá-lo como propriedade de um atributo.</span><span class="sxs-lookup"><span data-stu-id="abdfb-124">After you create a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="abdfb-125">Para usar o cálculo nomeado para nomes de membros</span><span class="sxs-lookup"><span data-stu-id="abdfb-125">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="abdfb-126">Abra o **Designer de Dimensão** da dimensão Date no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abdfb-126">Open **Dimension Designer** for the Date dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="abdfb-127">Para fazer isso, clique duas vezes na `Date` dimensão no nó **dimensões** de **Gerenciador de soluções**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-127">To do this, double-click the `Date` dimension in the **Dimensions** node of **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="abdfb-128">No painel **Atributos** da guia **Estrutura da Dimensão** , clique no atributo **Date Key** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-128">In the **Attributes** pane of the **Dimension Structure** tab, click the **Date Key** attribute.</span></span>  
  
3.  <span data-ttu-id="abdfb-129">Se a janela Propriedades não estiver aberta, abra-a e clique no botão **Ocultar Automaticamente** na barra de título para que ela permaneça aberta.</span><span class="sxs-lookup"><span data-stu-id="abdfb-129">If the Properties window is not open, open the Properties window, and then click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="abdfb-130">Clique no campo de propriedade **NameColumn** próximo à parte inferior da janela e clique no botão de navegação de reticências (**...**) para abrir a caixa de diálogo **coluna de nome** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-130">Click the **NameColumn** property field near the bottom of the window, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
5.  <span data-ttu-id="abdfb-131">Selecione `SimpleDate` na parte inferior da lista **coluna de origem** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-131">Select `SimpleDate` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="abdfb-132">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-132">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="abdfb-133">Criando uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="abdfb-133">Creating a Hierarchy</span></span>  
 <span data-ttu-id="abdfb-134">Você pode criar uma nova hierarquia arrastando um atributo do painel **Atributos** até o painel **Hierarquias** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-134">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="abdfb-135">Para criar uma hierarquia</span><span class="sxs-lookup"><span data-stu-id="abdfb-135">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="abdfb-136">Na guia **estrutura** da dimensão do designer de dimensão da `Date` dimensão, arraste o atributo **ano civil** do painel **atributos** até o painel **hierarquias** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-136">In **Dimension Structure** tab of the Dimension Designer for the `Date` dimension, drag the **Calendar Year** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="abdfb-137">Arraste o atributo **Semestre do Calendário** do painel **Atributos** até a célula **\<new level>** do painel **Hierarquias** , sob o nível **Ano do Calendário** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-137">Drag the **Calendar Semester** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Year** level.</span></span>  
  
3.  <span data-ttu-id="abdfb-138">Arraste o atributo **Trimestre do Calendário** do painel **Atributos** até a célula **\<new level>** do painel **Hierarquias** , sob o nível **Semestre do Calendário** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-138">Drag the **Calendar Quarter** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Semester** level.</span></span>  
  
4.  <span data-ttu-id="abdfb-139">Arraste o atributo **Nome do Mês em Inglês** do painel **Atributos** até a célula **\<new level>** do painel **Hierarquias** , sob o nível **Trimestre do Calendário** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-139">Drag the **English Month Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Quarter** level.</span></span>  
  
5.  <span data-ttu-id="abdfb-140">Arraste o atributo **Chave de Data** do painel **Atributos** até a célula **\<new level>** do painel **Hierarquias** , sob o nível **Nome do Mês em Inglês** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-140">Drag the **Date Key** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **English Month Name** level.</span></span>  
  
6.  <span data-ttu-id="abdfb-141">No painel **hierarquias** , clique com o botão direito do mouse na barra de título da hierarquia **hierarquia** , clique em **renomear**e digite `Calendar Date` .</span><span class="sxs-lookup"><span data-stu-id="abdfb-141">In the **Hierarchies** pane, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Calendar Date`.</span></span>  
  
7.  <span data-ttu-id="abdfb-142">Usando o menu de contexto de clique com o botão direito do mouse, na `Calendar Date` hierarquia, renomeie o nível de **nome do mês em inglês** como `Calendar Month` e renomeie o nível de **chave de data** como `Date` .</span><span class="sxs-lookup"><span data-stu-id="abdfb-142">By using the right-click context menu, in the `Calendar Date` hierarchy, rename the **English Month Name** level to `Calendar Month`, and then rename the **Date Key** level to `Date`.</span></span>  
  
8.  <span data-ttu-id="abdfb-143">Exclua o atributo **Full Date Alternate Key** do painel **Atributos** , pois você não precisará mais dele.</span><span class="sxs-lookup"><span data-stu-id="abdfb-143">Delete the **Full Date Alternate Key** attribute from the **Attributes** pane because you will not be using it.</span></span> <span data-ttu-id="abdfb-144">Clique em **OK** na janela de confirmação **Excluir Objetos** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-144">Click **OK** in the **Delete Objects** confirmation window.</span></span>  
  
9. <span data-ttu-id="abdfb-145">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-145">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="abdfb-146">Definindo relações de atributo</span><span class="sxs-lookup"><span data-stu-id="abdfb-146">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="abdfb-147">Se os dados subjacentes permitirem, você também deve definir relações de atributo entre atributos.</span><span class="sxs-lookup"><span data-stu-id="abdfb-147">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="abdfb-148">Definir relações de atributo acelera o processamento de dimensões, partições e consultas.</span><span class="sxs-lookup"><span data-stu-id="abdfb-148">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="abdfb-149">Para definir relações de atributo</span><span class="sxs-lookup"><span data-stu-id="abdfb-149">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="abdfb-150">No **Designer de dimensão** da `Date` dimensão, clique na guia **relações de atributo** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-150">In the **Dimension Designer** for the `Date` dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="abdfb-151">No diagrama, clique com o botão direito do mouse no atributo **English Month Name** e clique em **Nova Relação de Atributo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-151">In the diagram, right-click the **English Month Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="abdfb-152">Na caixa de diálogo **Criar Relação de Atributo** , o **Atributo de Origem** é **English Month Name**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-152">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **English Month Name**.</span></span> <span data-ttu-id="abdfb-153">Defina o **Atributo Relacionado** como **Trimestre do Calendário**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-153">Set the **Related Attribute** to **Calendar Quarter**.</span></span>  
  
4.  <span data-ttu-id="abdfb-154">Na lista **Tipo de relação** , defina o tipo de relação como **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-154">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="abdfb-155">O tipo de relação é **Rígida** porque as relações entre os membros não mudarão com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="abdfb-155">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span>  
  
5.  <span data-ttu-id="abdfb-156">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-156">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="abdfb-157">No diagrama, clique com o botão direito do mouse no atributo **Calendar Quarter** e clique em **Nova Relação de Atributo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-157">In the diagram, right-click the **Calendar Quarter** attribute, and then click **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="abdfb-158">Na caixa de diálogo **Criar Relação de Atributo** , o **Atributo de Origem** é **Trimestre Calendário**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-158">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Quarter**.</span></span> <span data-ttu-id="abdfb-159">Defina o **Atributo Relacionado** como **Semestre do Calendário**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-159">Set the **Related Attribute** to **Calendar Semester**.</span></span>  
  
8.  <span data-ttu-id="abdfb-160">Na lista **Tipo de relação** , defina o tipo de relação como **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-160">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="abdfb-161">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-161">Click **OK**.</span></span>  
  
10. <span data-ttu-id="abdfb-162">No diagrama, clique com o botão direito do mouse no atributo **Calendar Semester** e clique em **Nova Relação de Atributo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-162">In the diagram, right-click the **Calendar Semester** attribute, and then click **New Attribute Relationship**.</span></span>  
  
11. <span data-ttu-id="abdfb-163">Na caixa de diálogo **Criar Relação de Atributo** , o **Atributo de Origem** é **Semestre do Calendário**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-163">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Semester**.</span></span> <span data-ttu-id="abdfb-164">Defina o **Atributo Relacionado** como **Ano Civil**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-164">Set the **Related Attribute** to **Calendar Year**.</span></span>  
  
12. <span data-ttu-id="abdfb-165">Na lista **Tipo de relação** , defina o tipo de relação como **Rígida**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-165">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
13. <span data-ttu-id="abdfb-166">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-166">Click **OK**.</span></span>  
  
14. <span data-ttu-id="abdfb-167">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-167">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="providing-unique-dimension-member-names"></a><span data-ttu-id="abdfb-168">Fornecendo nomes de membro de dimensão exclusivos</span><span class="sxs-lookup"><span data-stu-id="abdfb-168">Providing Unique Dimension Member Names</span></span>  
 <span data-ttu-id="abdfb-169">Nesta tarefa, você criará colunas de nomes amigáveis que serão usadas pelos atributos **EnglishMonthName**, **CalendarQuarter**e **CalendarSemester** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-169">In this task, you will create user-friendly name columns that will be used by the **EnglishMonthName**, **CalendarQuarter**, and **CalendarSemester** attributes.</span></span>  
  
#### <a name="to-provide-unique-dimension-member-names"></a><span data-ttu-id="abdfb-170">Para fornecer nomes de membro de dimensão exclusivos</span><span class="sxs-lookup"><span data-stu-id="abdfb-170">To provide unique dimension member names</span></span>  
  
1.  <span data-ttu-id="abdfb-171">Para alternar para a exibição da fonte de dados do \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* , clique duas vezes nela na pasta **exibições da fonte de dados** em Gerenciador de soluções.</span><span class="sxs-lookup"><span data-stu-id="abdfb-171">To switch to the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="abdfb-172">No painel **tabelas** , clique com o botão direito do mouse em `Date` e clique em **novo cálculo nomeado**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-172">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="abdfb-173">Na caixa de diálogo **criar cálculo nomeado** , digite `MonthName` a caixa **nome da coluna** e digite ou copie e cole a seguinte instrução na caixa **expressão** :</span><span class="sxs-lookup"><span data-stu-id="abdfb-173">In the **Create Named Calculation** dialog box, type `MonthName` in the **Column name** box, and then type or copy and paste the following statement in the **Expression** box:</span></span>  
  
    ```  
    EnglishMonthName+' '+ CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="abdfb-174">A instrução concatena o mês e o ano para cada mês na tabela em uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="abdfb-174">The statement concatenates the month and year for each month in the table into a new column.</span></span>  
  
4.  <span data-ttu-id="abdfb-175">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-175">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="abdfb-176">No painel **tabelas** , clique com o botão direito do mouse em `Date` e clique em **novo cálculo nomeado**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-176">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="abdfb-177">Na caixa de diálogo **criar cálculo nomeado** , digite `CalendarQuarterDesc` a caixa **nome da coluna** e, em seguida, digite ou copie e cole o seguinte script SQL na caixa **expressão** :</span><span class="sxs-lookup"><span data-stu-id="abdfb-177">In the **Create Named Calculation** dialog box, type `CalendarQuarterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    'Q' + CONVERT(CHAR (1), CalendarQuarter) +' '+ 'CY ' +  
    CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="abdfb-178">Esse script de SQL concatena o trimestre e o ano para cada trimestre na tabela em uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="abdfb-178">This SQL script concatenates the calendar quarter and year for each quarter in the table into a new column.</span></span>  
  
7.  <span data-ttu-id="abdfb-179">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-179">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="abdfb-180">No painel **tabelas** , clique com o botão direito do mouse em `Date` e clique em **novo cálculo nomeado**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-180">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
9. <span data-ttu-id="abdfb-181">Na caixa de diálogo **criar cálculo nomeado** , digite `CalendarSemesterDesc` a caixa **nome da coluna** e, em seguida, digite ou copie e cole o seguinte script SQL na caixa **expressão** :</span><span class="sxs-lookup"><span data-stu-id="abdfb-181">In the **Create Named Calculation** dialog box, type `CalendarSemesterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    CASE  
    WHEN CalendarSemester = 1 THEN 'H1' + ' ' + 'CY' + ' '   
           + CONVERT(CHAR(4), CalendarYear)  
    ELSE  
    'H2' + ' ' + 'CY' + ' ' + CONVERT(CHAR(4), CalendarYear)  
    END  
    ```  
  
     <span data-ttu-id="abdfb-182">Esse script de SQL concatena o semestre e o ano para cada semestre na tabela em uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="abdfb-182">This SQL script concatenates the calendar semester and year for each semester in the table into a new column.</span></span>  
  
10. <span data-ttu-id="abdfb-183">Clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="abdfb-183">Click **OK.**</span></span>  
  
11. <span data-ttu-id="abdfb-184">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns-and-setting-the-name-column"></a><span data-ttu-id="abdfb-185">Definindo o composto KeyColumns e configurando a Coluna de Nome</span><span class="sxs-lookup"><span data-stu-id="abdfb-185">Defining Composite KeyColumns and Setting the Name Column</span></span>  
 <span data-ttu-id="abdfb-186">A propriedade **KeyColumns** contém a coluna ou as colunas que representam a chave do atributo.</span><span class="sxs-lookup"><span data-stu-id="abdfb-186">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="abdfb-187">Nesta tarefa, você definirá a composição **KeyColumns**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-187">In this task, you will define composite **KeyColumns**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-english-month-name-attribute"></a><span data-ttu-id="abdfb-188">Para definir o composto KeyColumns para o atributo Nome do Mês em Inglês</span><span class="sxs-lookup"><span data-stu-id="abdfb-188">To define composite KeyColumns for the English Month Name attribute</span></span>  
  
1.  <span data-ttu-id="abdfb-189">Abra a guia **Estrutura da Dimensão** da dimensão Date.</span><span class="sxs-lookup"><span data-stu-id="abdfb-189">Open the **Dimension Structure** tab for the Date dimension.</span></span>  
  
2.  <span data-ttu-id="abdfb-190">No painel **Atributos** , clique no atributo **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-190">In the **Attributes** pane, click the **English Month Name** attribute.</span></span>  
  
3.  <span data-ttu-id="abdfb-191">Na janela **Propriedades** , clique no campo **KeyColumns** e clique no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="abdfb-191">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="abdfb-192">Na caixa de diálogo **colunas de chave** , na lista **colunas disponíveis** , selecione a coluna **CalendarYear**e clique no **>** botão.</span><span class="sxs-lookup"><span data-stu-id="abdfb-192">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
5.  <span data-ttu-id="abdfb-193">Agora, as colunas **EnglishMonthName** e **CalendarYear** são exibidas na lista **Colunas de Chave** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-193">The **EnglishMonthName** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
6.  <span data-ttu-id="abdfb-194">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-194">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="abdfb-195">Para definir a propriedade **NameColumn** do atributo **EnglishMonthName** , clique no campo **NameColumn** na janela Propriedades e clique no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="abdfb-195">To set the **NameColumn** property of the **EnglishMonthName** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
8.  <span data-ttu-id="abdfb-196">Na caixa de diálogo **coluna de nome** , na lista **coluna de origem** , selecione `MonthName` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-196">In the **Name Column** dialog box, in the **Source Column** list, select `MonthName`, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="abdfb-197">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-197">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-quarter-attribute"></a><span data-ttu-id="abdfb-198">Para definir o composto KeyColumns para o atributo Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="abdfb-198">To define composite KeyColumns for the Calendar Quarter attribute</span></span>  
  
1.  <span data-ttu-id="abdfb-199">No painel **Atributos** , clique no atributo **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-199">In the **Attributes** pane, click the **Calendar Quarter** attribute.</span></span>  
  
2.  <span data-ttu-id="abdfb-200">Na janela **Propriedades** , clique no campo **KeyColumns** e clique no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="abdfb-200">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="abdfb-201">Na caixa de diálogo **colunas de chave** , na lista **colunas disponíveis** , selecione a coluna **CalendarYear**e clique no **>** botão.</span><span class="sxs-lookup"><span data-stu-id="abdfb-201">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="abdfb-202">Agora, as colunas **CalendarQuarter** e **CalendarYear** são exibidas na lista **Colunas de Chave** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-202">The **CalendarQuarter** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="abdfb-203">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-203">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="abdfb-204">Para definir a propriedade **NameColumn** do atributo **Calendar Quarter** , clique no campo **NameColumn** na janela Propriedades e clique no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="abdfb-204">To set the **NameColumn** property of the **Calendar Quarter** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="abdfb-205">Na caixa de diálogo **coluna de nome** , na lista **coluna de origem** , selecione `CalendarQuarterDesc` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-205">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarQuarterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="abdfb-206">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-206">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-semester-attribute"></a><span data-ttu-id="abdfb-207">Para definir o composto KeyColumns para o atributo Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="abdfb-207">To define composite KeyColumns for the Calendar Semester attribute</span></span>  
  
1.  <span data-ttu-id="abdfb-208">No painel **Atributos** , clique no atributo **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-208">In the **Attributes** pane, click the **Calendar Semester** attribute.</span></span>  
  
2.  <span data-ttu-id="abdfb-209">Na janela **Propriedades** , clique no campo **KeyColumns** e clique no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="abdfb-209">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="abdfb-210">Na caixa de diálogo **Colunas de Chave** , na lista **Colunas Disponíveis** , selecione a coluna **CalendarYear**e clique no botão **>** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-210">In the **Key Columns** dialog box, in the **Available Columns** list, select the column, **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="abdfb-211">Agora, as colunas **CalendarSemester** e **CalendarYear** são exibidas na lista **Colunas de Chave** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-211">The **CalendarSemester** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="abdfb-212">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-212">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="abdfb-213">Para definir a propriedade **NameColumn** do atributo **Calendar Semester** , clique no campo **NameColumn** na janela Propriedades e clique no botão Procurar (**...**).</span><span class="sxs-lookup"><span data-stu-id="abdfb-213">To set the **NameColumn** property of the **Calendar Semester** attribute, click the **NameColumn** field in the property window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="abdfb-214">Na caixa de diálogo **coluna de nome** , na lista **coluna de origem** , selecione `CalendarSemesterDesc` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-214">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarSemesterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="abdfb-215">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-215">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-and-viewing-the-changes"></a><span data-ttu-id="abdfb-216">Implantando e exibindo as alterações</span><span class="sxs-lookup"><span data-stu-id="abdfb-216">Deploying and Viewing the Changes</span></span>  
 <span data-ttu-id="abdfb-217">Depois de alterar atributos e hierarquias, você deve implantar as alterações e processar novamente os objetos relacionados para poder exibir as alterações.</span><span class="sxs-lookup"><span data-stu-id="abdfb-217">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-and-view-the-changes"></a><span data-ttu-id="abdfb-218">Para implantar e exibir as alterações</span><span class="sxs-lookup"><span data-stu-id="abdfb-218">To deploy and view the changes</span></span>  
  
1.  <span data-ttu-id="abdfb-219">No menu **Compilar** do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-219">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="abdfb-220">Depois de ter recebido a mensagem **implantação concluída com êxito** , clique na guia **navegador** do **Designer de dimensão** da `Date` dimensão e, em seguida, clique no botão Reconectar na barra de ferramentas do designer.</span><span class="sxs-lookup"><span data-stu-id="abdfb-220">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the `Date` dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="abdfb-221">Selecione **Calendar Quarter** na lista **Hierarquia** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-221">Select **Calendar Quarter** from the **Hierarchy** list.</span></span> <span data-ttu-id="abdfb-222">Examine os membros da hierarquia de atributo **Calendar Quarter** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-222">Review the members in the **Calendar Quarter** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="abdfb-223">Observe que os nomes dos membros da hierarquia de atributo **Calendar Quarter** são mais claros e fáceis de serem usados porque você criou um cálculo nomeado para ser usado como o nome.</span><span class="sxs-lookup"><span data-stu-id="abdfb-223">Notice that the names of the members of the **Calendar Quarter** attribute hierarchy are clearer and easier to use because you created a named calculation to use as the name.</span></span> <span data-ttu-id="abdfb-224">Agora, existem membros na hierarquia de atributo **Calendar Quarter** para cada trimestre do ano.</span><span class="sxs-lookup"><span data-stu-id="abdfb-224">Members now exist in the **Calendar Quarter** attribute hierarchy for each quarter in each year.</span></span> <span data-ttu-id="abdfb-225">Os membros não são classificados em ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="abdfb-225">The members are not sorted in chronological order.</span></span> <span data-ttu-id="abdfb-226">Em vez disso, eles são classificados por trimestre e, depois, por ano.</span><span class="sxs-lookup"><span data-stu-id="abdfb-226">Instead they are sorted by quarter and then by year.</span></span> <span data-ttu-id="abdfb-227">Na próxima tarefa deste tópico, você modificará esse comportamento para classificar os membros da hierarquia de atributo por ano e, depois, por trimestre.</span><span class="sxs-lookup"><span data-stu-id="abdfb-227">In the next task in this topic, you will modify this behavior to sort the members of this attribute hierarchy by year and then by quarter.</span></span>  
  
4.  <span data-ttu-id="abdfb-228">Examine os membros das hierarquias de atributo **English Month Name** e **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-228">Review the members of the **English Month Name** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="abdfb-229">Observe que os membros dessas hierarquias também não são classificados em ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="abdfb-229">Notice that the members of these hierarchies are also not sorted in chronological order.</span></span> <span data-ttu-id="abdfb-230">Em vez disso, eles são classificados por mês ou semestre, respectivamente, e, então, por ano.</span><span class="sxs-lookup"><span data-stu-id="abdfb-230">Instead, they are sorted by month or semester, respectively, and then by year.</span></span> <span data-ttu-id="abdfb-231">Na próxima tarefa deste tópico, você modificará esse comportamento com o objetivo de alterar essa ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="abdfb-231">In the next task in this topic, you will modify this behavior to change this sort order.</span></span>  
  
## <a name="changing-the-sort-order-by-modifying-composite-key-member-order"></a><span data-ttu-id="abdfb-232">Alterando a ordem de classificação modificando ordem de membro de chave composta</span><span class="sxs-lookup"><span data-stu-id="abdfb-232">Changing the Sort Order by Modifying Composite Key Member Order</span></span>  
 <span data-ttu-id="abdfb-233">Nesta tarefa, você poderá alterar a ordem de classificação alterando a ordem das chaves que criam a chave composta.</span><span class="sxs-lookup"><span data-stu-id="abdfb-233">In this task, you will change the sort order by changing the order of the keys that make up the composite key.</span></span>  
  
#### <a name="to-modify-the-composite-key-member-order"></a><span data-ttu-id="abdfb-234">Para modificar a ordem de membro de chave composta</span><span class="sxs-lookup"><span data-stu-id="abdfb-234">To modify the composite key member order</span></span>  
  
1.  <span data-ttu-id="abdfb-235">Abra a guia **estrutura da dimensão** do designer de dimensão da `Date` dimensão e, em seguida, selecione **semestre do calendário** no painel **atributos** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-235">Open the **Dimension Structure** tab of Dimension Designer for the `Date` dimension, and then select **Calendar Semester** in the **Attributes** pane.</span></span>  
  
2.  <span data-ttu-id="abdfb-236">Na janela Propriedades, examine o valor da propriedade **OrderBy** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-236">In the Properties window, review the value for the **OrderBy** property.</span></span> <span data-ttu-id="abdfb-237">Ela está definida como **Chave**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-237">It is set to **Key**.</span></span>  
  
     <span data-ttu-id="abdfb-238">Os membros da hierarquia de atributo **Calendar Semester** são classificados por seus valores chave.</span><span class="sxs-lookup"><span data-stu-id="abdfb-238">The members of the **Calendar Semester** attribute hierarchy are sorted by their key value.</span></span> <span data-ttu-id="abdfb-239">Em uma chave composta, a ordem das chaves de membro baseia-se primeiro no valor da primeira chave de membro e, depois, no valor da segunda chave de membro.</span><span class="sxs-lookup"><span data-stu-id="abdfb-239">With a composite key, the ordering of the member keys is based first on the value of the first member key, and then on the value of the second member key.</span></span> <span data-ttu-id="abdfb-240">Em outras palavras, os membros da hierarquia de atributo **Calendar Semester** são classificados primeiro por semestre e depois por ano.</span><span class="sxs-lookup"><span data-stu-id="abdfb-240">In other words, the members of the **Calendar Semester** attribute hierarchy are sorted first by semester and then by year.</span></span>  
  
3.  <span data-ttu-id="abdfb-241">Na janela Propriedades, clique no botão Procurar (**...**) para alterar o valor da propriedade **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-241">In the Properties window, click the ellipsis browse button (**...**) to change the **KeyColumns** property value.</span></span>  
  
4.  <span data-ttu-id="abdfb-242">Na lista **Colunas de Chave** da caixa de diálogo **Colunas de Chave** , verifique se a opção **CalendarSemester** está selecionada e clique na seta para baixo para inverter a ordem dos membros dessa chave composta.</span><span class="sxs-lookup"><span data-stu-id="abdfb-242">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarSemester** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="abdfb-243">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-243">Click **OK**.</span></span>  
  
     <span data-ttu-id="abdfb-244">Agora, os membros da hierarquia de atributo são classificados primeiro por ano e, depois, por semestre.</span><span class="sxs-lookup"><span data-stu-id="abdfb-244">The members of the attribute hierarchy are now sorted first by year and then by semester.</span></span>  
  
5.  <span data-ttu-id="abdfb-245">Selecione **Calendar Quarter** no painel **Atributos** e clique no botão Procurar (**...**) da propriedade **KeyColumns** na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="abdfb-245">Select **Calendar Quarter** in the **Attributes** pane, and then click the ellipsis browse button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
6.  <span data-ttu-id="abdfb-246">Na lista **Colunas de Chave** da caixa de diálogo **Colunas de Chave** , verifique se o atributo **CalendarQuarter** está selecionado e clique na seta para baixo para inverter a ordem dos membros desta chave composta.</span><span class="sxs-lookup"><span data-stu-id="abdfb-246">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarQuarter** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="abdfb-247">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-247">Click **OK**.</span></span>  
  
     <span data-ttu-id="abdfb-248">Agora, os membros da hierarquia de atributo são classificados primeiro por ano e, depois, por trimestre.</span><span class="sxs-lookup"><span data-stu-id="abdfb-248">The members of the attribute hierarchy are now sorted first by year and then by quarter.</span></span>  
  
7.  <span data-ttu-id="abdfb-249">Selecione **English Month Name** no painel **Atributos** e clique no botão Procurar (**...**) da propriedade **KeyColumns** na janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="abdfb-249">Select **English Month Name** in the **Attributes** pane, and then click the ellipsis button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
8.  <span data-ttu-id="abdfb-250">Na lista **Colunas de Chave** da caixa de diálogo **Colunas de Chave** , verifique se o atributo **EnglishMonthName** está selecionado e clique na seta para baixo para inverter a ordem dos membros dessa chave composta.</span><span class="sxs-lookup"><span data-stu-id="abdfb-250">In the **Key Columns** list of the **Key Columns** dialog box, verify that **EnglishMonthName** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="abdfb-251">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-251">Click **OK**.</span></span>  
  
     <span data-ttu-id="abdfb-252">Agora, os membros da hierarquia de atributo são classificados primeiro por ano e, depois, por mês.</span><span class="sxs-lookup"><span data-stu-id="abdfb-252">The members of the attribute hierarchy are now sorted first by year and then by month.</span></span>  
  
9. <span data-ttu-id="abdfb-253">No menu **Compilar** do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique em **Implantar Tutorial do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="abdfb-253">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span> <span data-ttu-id="abdfb-254">Quando a implantação for concluída com êxito, clique na guia **navegador** do designer de dimensão da `Date` dimensão.</span><span class="sxs-lookup"><span data-stu-id="abdfb-254">When deployment has successfully completed, click the **Browser** tab in Dimension Designer for the `Date` dimension.</span></span>  
  
10. <span data-ttu-id="abdfb-255">Na barra de ferramentas da guia **Navegador** , clique no botão Reconectar.</span><span class="sxs-lookup"><span data-stu-id="abdfb-255">On the toolbar of the **Browser** tab, click the Reconnect button.</span></span>  
  
11. <span data-ttu-id="abdfb-256">Examine os membros das hierarquias de atributo **Calendar Quarter** e **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-256">Review the members of the **Calendar Quarter** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="abdfb-257">Observe que agora os membros dessas hierarquias são classificados em ordem cronológica, por ano e, depois, por trimestre ou semestre, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="abdfb-257">Notice that the members of these hierarchies are now sorted in chronological order, by year and then by quarter or semester, respectively.</span></span>  
  
12. <span data-ttu-id="abdfb-258">Examine os membros da hierarquia de atributo **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="abdfb-258">Review the members of the **English Month Name** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="abdfb-259">Observe que agora os membros da hierarquia são classificados primeiro por ano e, depois, por mês (em ordem alfabética).</span><span class="sxs-lookup"><span data-stu-id="abdfb-259">Notice that the members of the hierarchy are now sorted first by year and then alphabetically by month.</span></span> <span data-ttu-id="abdfb-260">Isso ocorre porque o tipo de dados da coluna EnglishCalendarMonth na exibição da fonte de dados é uma coluna da cadeia de caracteres que se baseia no tipo de dados nvarchar no banco de dados relacional subjacente.</span><span class="sxs-lookup"><span data-stu-id="abdfb-260">This is because the data type for the EnglishCalendarMonth column in the data source view is a string column, based on the nvarchar data type in the underlying relational database.</span></span> <span data-ttu-id="abdfb-261">Para obter informações sobre como habilitar os meses a serem classificados em ordem cronológica em cada ano, consulte [Classificando membros de atributo com base em um atributo secundário](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="abdfb-261">For information about how to enable the months to be sorted chronologically within each year, see [Sorting Attribute Members Based on a Secondary Attribute](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="abdfb-262">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="abdfb-262">Next Task in Lesson</span></span>  
 [<span data-ttu-id="abdfb-263">Navegando no cubo implantado</span><span class="sxs-lookup"><span data-stu-id="abdfb-263">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="abdfb-264">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="abdfb-264">See Also</span></span>  
 [<span data-ttu-id="abdfb-265">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="abdfb-265">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
