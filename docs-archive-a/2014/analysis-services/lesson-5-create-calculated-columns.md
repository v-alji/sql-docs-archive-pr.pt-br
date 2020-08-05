---
title: 'Lição 6: criar colunas calculadas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d126766a-5699-4e9f-8213-8c7eea0fc14e
author: minewiskan
ms.author: owend
ms.openlocfilehash: dcebf61955e230c9e61c955683b897026553cb52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572798"
---
# <a name="lesson-6-create-calculated-columns"></a><span data-ttu-id="43ff9-102">Lição 6: Criar colunas calculadas</span><span class="sxs-lookup"><span data-stu-id="43ff9-102">Lesson 6: Create Calculated Columns</span></span>
  <span data-ttu-id="43ff9-103">Nesta lição, você criará novos dados no modelo adicionando colunas calculadas.</span><span class="sxs-lookup"><span data-stu-id="43ff9-103">In this lesson, you will create new data in your model by adding calculated columns.</span></span> <span data-ttu-id="43ff9-104">Uma coluna calculada se baseia nos dados que já existem no modelo.</span><span class="sxs-lookup"><span data-stu-id="43ff9-104">A calculated column is based on data that already exists in the model.</span></span> <span data-ttu-id="43ff9-105">Para saber mais, consulte [Colunas calculadas &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns.md).</span><span class="sxs-lookup"><span data-stu-id="43ff9-105">To learn more, see [Calculated Columns &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns.md).</span></span>  
  
 <span data-ttu-id="43ff9-106">Você criará cinco novas colunas calculadas em três tabelas diferentes.</span><span class="sxs-lookup"><span data-stu-id="43ff9-106">You will create five new calculated columns in three different tables.</span></span> <span data-ttu-id="43ff9-107">As etapas são ligeiramente diferentes para cada tarefa.</span><span class="sxs-lookup"><span data-stu-id="43ff9-107">The steps are slightly different for each task.</span></span> <span data-ttu-id="43ff9-108">O objetivo disso é mostrar que há vários modos de criar novas colunas, renomeá-las e colocá-las em vários locais em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="43ff9-108">This is to show you there are several ways to create new columns, rename them, and place them in various locations in a table.</span></span>  
  
 <span data-ttu-id="43ff9-109">Tempo estimado para conclusão desta lição: **15 minutos**</span><span class="sxs-lookup"><span data-stu-id="43ff9-109">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="43ff9-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="43ff9-110">Prerequisites</span></span>  
 <span data-ttu-id="43ff9-111">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="43ff9-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="43ff9-112">Antes de realizar as tarefas desta lição, você deverá ter concluído a lição anterior: [Lição 5: Criar relações](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="43ff9-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
## <a name="create-calculated-columns"></a><span data-ttu-id="43ff9-113">Criar colunas calculadas</span><span class="sxs-lookup"><span data-stu-id="43ff9-113">Create Calculated Columns</span></span>  
  
#### <a name="create-a-month-calendar-calculated-column-in-the-date-table"></a><span data-ttu-id="43ff9-114">Criar uma coluna calculada Month Calendar na tabela Date</span><span class="sxs-lookup"><span data-stu-id="43ff9-114">Create a Month Calendar calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="43ff9-115">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Modelo** , aponte para **Exibição de Modelo**e clique em **Exibição de Dados**.</span><span class="sxs-lookup"><span data-stu-id="43ff9-115">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Model View**, and then click **Data View**.</span></span>  
  
     <span data-ttu-id="43ff9-116">Colunas calculadas só podem ser criadas usando o designer de modelos na exibição de dados.</span><span class="sxs-lookup"><span data-stu-id="43ff9-116">Calculated columns can only be created by using the model designer in Data View.</span></span>  
  
2.  <span data-ttu-id="43ff9-117">No designer de modelos, clique na tabela **Data** (guia).</span><span class="sxs-lookup"><span data-stu-id="43ff9-117">In the model designer, click the **Date** table (tab).</span></span>  
  
3.  <span data-ttu-id="43ff9-118">Clique com o botão direito do mouse na coluna **calendário trimestre** e clique em **Inserir coluna**.</span><span class="sxs-lookup"><span data-stu-id="43ff9-118">Right-click the **Calendar Quarter** column, and then click **Insert Column**.</span></span>  
  
     <span data-ttu-id="43ff9-119">Uma nova coluna chamada **CalculatedColumn1** é inserida à esquerda da coluna **calendário Quarter** .</span><span class="sxs-lookup"><span data-stu-id="43ff9-119">A new column named **CalculatedColumn1** is inserted to the left of the **Calendar Quarter** column.</span></span>  
  
4.  <span data-ttu-id="43ff9-120">Na barra de fórmulas acima da tabela, digite a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="43ff9-120">In the formula bar above the table, type the following formula.</span></span> <span data-ttu-id="43ff9-121">O Preenchimento Automático ajuda você a digitar os nomes totalmente qualificados de colunas e tabelas e lista as funções que estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="43ff9-121">AutoComplete helps you type the fully qualified names of columns and tables, and lists the functions that are available.</span></span>  
  
     `=RIGHT(" " & FORMAT([Month],"#0"), 2) & " - " & [Month Name]`  
  
     <span data-ttu-id="43ff9-122">Ao concluir a criação da fórmula, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="43ff9-122">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="43ff9-123">Os valores são populados para todas as linhas na coluna calculada.</span><span class="sxs-lookup"><span data-stu-id="43ff9-123">Values are then populated for all the rows in the calculated column.</span></span> <span data-ttu-id="43ff9-124">Se você rolar para baixo na tabela, você verá que linhas podem ter valores diferentes para esta coluna, com base nos dados que estão em cada linha.</span><span class="sxs-lookup"><span data-stu-id="43ff9-124">If you scroll down through the table, you will see that rows can have different values for this column, based on the data that is in each row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43ff9-125">Se você receber um erro, verifique se os nomes de coluna na fórmula correspondem aos nomes de coluna alterados na [Lição 3: Renomear colunas](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="43ff9-125">If you receive an error, verify the column names in the formula match the column names you changed in [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
5.  <span data-ttu-id="43ff9-126">Renomeie esta coluna como `Month Calendar` .</span><span class="sxs-lookup"><span data-stu-id="43ff9-126">Rename this column to `Month Calendar`.</span></span>  
  
 <span data-ttu-id="43ff9-127">A coluna calculada Month Calendar fornece um nome classificável para o mês.</span><span class="sxs-lookup"><span data-stu-id="43ff9-127">The Month Calendar calculated column provides a sortable name for Month.</span></span>  
  
#### <a name="create-a-day-of-week-calculated-column-in-the-date-table"></a><span data-ttu-id="43ff9-128">Criar uma coluna calculada Day of Week na tabela Date</span><span class="sxs-lookup"><span data-stu-id="43ff9-128">Create a Day of Week calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="43ff9-129">Com a tabela **Date** ainda ativa, clique no menu **Coluna** e em **Adicionar Coluna**.</span><span class="sxs-lookup"><span data-stu-id="43ff9-129">With the **Date** table still active, click on the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="43ff9-130">Uma nova coluna é adicionada à extrema direita da tabela.</span><span class="sxs-lookup"><span data-stu-id="43ff9-130">A new column is added to the far right of the table</span></span>  
  
2.  <span data-ttu-id="43ff9-131">Na barra de fórmulas, digite a seguinte fórmula:</span><span class="sxs-lookup"><span data-stu-id="43ff9-131">In the formula bar, type the following formula:</span></span>  
  
     `=RIGHT(" " & FORMAT([Day Number Of Week],"#0"), 2) & " - " & [Day Name]`  
  
     <span data-ttu-id="43ff9-132">Ao concluir a criação da fórmula, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="43ff9-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="43ff9-133">Renomeie a coluna para `Day of Week` .</span><span class="sxs-lookup"><span data-stu-id="43ff9-133">Rename the column to `Day of Week`.</span></span>  
  
4.  <span data-ttu-id="43ff9-134">Clique no título de coluna e arraste a coluna entre as colunas **Day Name** e **Day of Month** .</span><span class="sxs-lookup"><span data-stu-id="43ff9-134">Click on the column heading, and then drag the column between the **Day Name** column and the **Day of Month** column.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="43ff9-135">A movimentação das colunas na tabela facilita a navegação.</span><span class="sxs-lookup"><span data-stu-id="43ff9-135">Moving columns in your table makes it easier to navigate.</span></span>  
  
 <span data-ttu-id="43ff9-136">A coluna calculada Day of Week fornece um nome classificável para o dia de semana.</span><span class="sxs-lookup"><span data-stu-id="43ff9-136">The Day of Week calculated column provides a sortable name for the day of week.</span></span>  
  
#### <a name="create-a-product-subcategory-name-calculated-column-in-the-product-table"></a><span data-ttu-id="43ff9-137">Criar uma coluna calculada Product Subcategory Name na tabela Product</span><span class="sxs-lookup"><span data-stu-id="43ff9-137">Create a Product Subcategory Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="43ff9-138">No designer de modelos, selecione a tabela **Product** .</span><span class="sxs-lookup"><span data-stu-id="43ff9-138">In the model designer, select the **Product** table.</span></span>  
  
2.  <span data-ttu-id="43ff9-139">Role a tela para a extrema direita da tabela.</span><span class="sxs-lookup"><span data-stu-id="43ff9-139">Scroll to the far right of the table.</span></span> <span data-ttu-id="43ff9-140">Observe que a coluna mais à direita é denominada **Adicionar Coluna** (em itálico), clique no título de coluna.</span><span class="sxs-lookup"><span data-stu-id="43ff9-140">Notice the right-most column is named **Add Column** (italicized), click the column heading.</span></span>  
  
3.  <span data-ttu-id="43ff9-141">Na barra de fórmulas, digite a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="43ff9-141">In the formula bar, type the following formula.</span></span>  
  
     `=RELATED('Product Subcategory'[Product Subcategory Name])`  
  
     <span data-ttu-id="43ff9-142">Ao concluir a criação da fórmula, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="43ff9-142">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="43ff9-143">Renomeie a coluna para `Product Subcategory Name` .</span><span class="sxs-lookup"><span data-stu-id="43ff9-143">Rename the column to `Product Subcategory Name`.</span></span>  
  
 <span data-ttu-id="43ff9-144">A coluna calculada Product Subcategory Name é usada para criar uma hierarquia na tabela Product que inclui dados da coluna Product Subcategory Name na tabela Product Subcategory.</span><span class="sxs-lookup"><span data-stu-id="43ff9-144">The Product Subcategory Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Subcategory Name column in the Product Subcategory table.</span></span> <span data-ttu-id="43ff9-145">Hierarquias não podem abranger mais de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="43ff9-145">Hierarchies cannot span more than one table.</span></span> <span data-ttu-id="43ff9-146">Você criará hierarquias posteriormente na lição 7.</span><span class="sxs-lookup"><span data-stu-id="43ff9-146">You will create hierarchies later in Lesson 7.</span></span>  
  
#### <a name="create-a-product-category-name-calculated-column-in-the-product-table"></a><span data-ttu-id="43ff9-147">Criar uma coluna calculada Product Category Name na tabela Product</span><span class="sxs-lookup"><span data-stu-id="43ff9-147">Create a Product Category Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="43ff9-148">Com a tabela **Product** ainda ativa, clique no menu **Coluna** e em **Adicionar Coluna**.</span><span class="sxs-lookup"><span data-stu-id="43ff9-148">With the **Product** table still active, click the **Column** menu, and then click **Add Column**.</span></span>  
  
2.  <span data-ttu-id="43ff9-149">Na barra de fórmulas, digite a seguinte fórmula:</span><span class="sxs-lookup"><span data-stu-id="43ff9-149">In the formula bar, type the following formula:</span></span>  
  
     `=RELATED('Product Category'[Product Category Name])`  
  
     <span data-ttu-id="43ff9-150">Ao concluir a criação da fórmula, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="43ff9-150">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="43ff9-151">Renomeie a coluna para `Product Category Name` .</span><span class="sxs-lookup"><span data-stu-id="43ff9-151">Rename the column to `Product Category Name`.</span></span>  
  
 <span data-ttu-id="43ff9-152">A coluna calculada Product Category Name é usada para criar uma hierarquia na tabela Product que inclui dados da coluna Product Category Name na tabela Product Category.</span><span class="sxs-lookup"><span data-stu-id="43ff9-152">The Product Category Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Category Name column in the Product Category table.</span></span> <span data-ttu-id="43ff9-153">Hierarquias não podem abranger mais de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="43ff9-153">Hierarchies cannot span more than one table.</span></span>  
  
#### <a name="create-a-margin-calculated-column-in-the-internet-sales-table"></a><span data-ttu-id="43ff9-154">Criar uma coluna calculada Margin na tabela Internet Sales</span><span class="sxs-lookup"><span data-stu-id="43ff9-154">Create a Margin calculated column in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="43ff9-155">No designer de modelos, selecione a tabela **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="43ff9-155">In the model designer, select the **Internet Sales** table.</span></span>  
  
2.  <span data-ttu-id="43ff9-156">Adicione uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="43ff9-156">Add a new column.</span></span>  
  
3.  <span data-ttu-id="43ff9-157">Na barra de fórmulas, digite a seguinte fórmula:</span><span class="sxs-lookup"><span data-stu-id="43ff9-157">In the formula bar, type the following formula:</span></span>  
  
     `=[Sales Amount]-[Total Product Cost]`  
  
     <span data-ttu-id="43ff9-158">Ao concluir a criação da fórmula, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="43ff9-158">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="43ff9-159">Renomeie a coluna para `Margin` .</span><span class="sxs-lookup"><span data-stu-id="43ff9-159">Rename the column to `Margin`.</span></span>  
  
5.  <span data-ttu-id="43ff9-160">Arraste a coluna entre as colunas **Sales Amount** e **Tax Amt** .</span><span class="sxs-lookup"><span data-stu-id="43ff9-160">Drag the column between the **Sales Amount** column and the **Tax Amt** column.</span></span>  
  
 <span data-ttu-id="43ff9-161">A coluna calculada Margin é usada para analisar margens de lucro para cada linha (produto).</span><span class="sxs-lookup"><span data-stu-id="43ff9-161">The Margin calculated column is used to analyze profit margins for each (product) row.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="43ff9-162">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="43ff9-162">Next Step</span></span>  
 <span data-ttu-id="43ff9-163">Para continuar esta lição, vá para a próxima lição: [Lição 7: Criar medidas](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="43ff9-163">To continue this lesson, go to the next lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
  
