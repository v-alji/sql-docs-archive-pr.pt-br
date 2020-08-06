---
title: 'Lição 10: criar hierarquias | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e2561d3-4890-4495-a9cd-84eb88508938
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d0982a05c37c28167e44e3f9f082ea5113b59bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680703"
---
# <a name="lesson-10-create-hierarchies"></a><span data-ttu-id="c0554-102">Lição 10: Criar hierarquias</span><span class="sxs-lookup"><span data-stu-id="c0554-102">Lesson 10: Create Hierarchies</span></span>
  <span data-ttu-id="c0554-103">Nesta lição, você criará hierarquias.</span><span class="sxs-lookup"><span data-stu-id="c0554-103">In this lesson, you will create hierarchies.</span></span> <span data-ttu-id="c0554-104">Hierarquias são grupos de colunas organizados em níveis; por exemplo, uma hierarquia Geografia poderia ter subníveis para País, Estado, Município e Cidade.</span><span class="sxs-lookup"><span data-stu-id="c0554-104">Hierarchies are groups of columns arranged in levels; for example, a Geography hierarchy might have sub-levels for Country, State, County, and City.</span></span> <span data-ttu-id="c0554-105">As hierarquias podem aparecer separadas de outras colunas em uma lista de campos de aplicativo cliente de relatório, facilitando sua navegação e inclusão em um relatório pelos usuários do cliente.</span><span class="sxs-lookup"><span data-stu-id="c0554-105">Hierarchies can appear separate from other columns in a reporting client application field list, making them easier for client users to navigate and include in a report.</span></span> <span data-ttu-id="c0554-106">Para saber mais, consulte [Hierarquias &#40;SSAS Tabular&#41;](tabular-models/hierarchies-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c0554-106">To learn more, see [Hierarchies &#40;SSAS Tabular&#41;](tabular-models/hierarchies-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="c0554-107">Para criar hierarquias, você usará o designer de modelos na *Exibição de Diagrama*.</span><span class="sxs-lookup"><span data-stu-id="c0554-107">To create hierarchies, you will use the model designer in *Diagram View*.</span></span> <span data-ttu-id="c0554-108">Não há suporte para a criação e o gerenciamento de hierarquias no designer de modelos na Exibição de Dados.</span><span class="sxs-lookup"><span data-stu-id="c0554-108">Creating and managing hierarchies is not supported in the model designer in Data View.</span></span>  
  
 <span data-ttu-id="c0554-109">Tempo estimado para conclusão desta lição: **20 minutos**</span><span class="sxs-lookup"><span data-stu-id="c0554-109">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c0554-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c0554-110">Prerequisites</span></span>  
 <span data-ttu-id="c0554-111">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="c0554-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="c0554-112">Antes de realizar as tarefas desta lição, você deverá ter concluído a lição anterior: [Lição 9: Criar perspectivas](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="c0554-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
## <a name="create-hierarchies"></a><span data-ttu-id="c0554-113">Criar hierarquias</span><span class="sxs-lookup"><span data-stu-id="c0554-113">Create Hierarchies</span></span>  
  
#### <a name="to-create-a-category-hierarchy-in-the-product-table"></a><span data-ttu-id="c0554-114">Para criar uma hierarquia Categoria na tabela Produto</span><span class="sxs-lookup"><span data-stu-id="c0554-114">To create a Category hierarchy in the Product table</span></span>  
  
1.  <span data-ttu-id="c0554-115">No designer de modelos, clique no `Model` menu, aponte para exibição de **modelo**e clique em exibição de **diagrama**.</span><span class="sxs-lookup"><span data-stu-id="c0554-115">In the model designer, click on the `Model` menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="c0554-116">Use os controles do Minimapa no lado superior direito do designer de modelos para alterar o modo de exibição dos objetos em Exibição de Diagrama.</span><span class="sxs-lookup"><span data-stu-id="c0554-116">Use the Minimap controls at the top-right of the model designer to change how you can view objects in Diagram View.</span></span> <span data-ttu-id="c0554-117">Se você reposicionar objetos na Exibição de Diagrama, essa exibição será retida quando você salvar o projeto.</span><span class="sxs-lookup"><span data-stu-id="c0554-117">If you reposition objects in Diagram View, that view will be retained when you save the project.</span></span>  
  
2.  <span data-ttu-id="c0554-118">No designer de modelo, clique com o botão direito do mouse na `Product` tabela e clique em **criar hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="c0554-118">In the model designer, right-click the `Product` table, and then click **Create Hierarchy**.</span></span> <span data-ttu-id="c0554-119">A nova hierarquia aparece na parte inferior da janela de tabela.</span><span class="sxs-lookup"><span data-stu-id="c0554-119">A new hierarchy appears at the bottom of the table window.</span></span>  
  
3.  <span data-ttu-id="c0554-120">No nome da hierarquia, renomeie a hierarquia digitando `Category` e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="c0554-120">In the hierarchy name, rename the hierarchy by typing `Category`, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="c0554-121">Na `Product` tabela, clique na coluna **nome da categoria do produto** , arraste-a para a `Category` hierarquia e, em seguida, solte na parte superior do `Category` nome.</span><span class="sxs-lookup"><span data-stu-id="c0554-121">In the `Product` table, click the **Product Category Name** column, then drag it to the `Category` hierarchy, and then release on top of the `Category` name.</span></span>  
  
5.  <span data-ttu-id="c0554-122">Na `Category` hierarquia, clique com o botão direito do mouse na coluna **nome da categoria do produto** , clique em **renomear**e digite `Category` .</span><span class="sxs-lookup"><span data-stu-id="c0554-122">In the `Category` hierarchy, right-click the **Product Category Name** column, then click **Rename**, and then type `Category`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0554-123">A renomeação de uma coluna em uma hierarquia não renomeia essa coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="c0554-123">Renaming a column in a hierarchy does not rename that column in the table.</span></span> <span data-ttu-id="c0554-124">Uma coluna em uma hierarquia é apenas uma representação da coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="c0554-124">A column in a hierarchy is just a representation of the column in the table.</span></span>  
  
6.  <span data-ttu-id="c0554-125">Na `Product` tabela, clique com o botão direito do mouse na coluna **nome da subcategoria do produto** e, no menu de contexto, aponte para **Adicionar à hierarquia**e clique em `Category` .</span><span class="sxs-lookup"><span data-stu-id="c0554-125">In the `Product` table, right-click the **Product Subcategory Name** column, then in the context menu, point to **Add to Hierarchy**, and then click `Category`.</span></span>  
  
7.  <span data-ttu-id="c0554-126">Renomeie o **nome da subcategoria do produto** para `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="c0554-126">Rename **Product Subcategory Name** to `Subcategory`.</span></span>  
  
8.  <span data-ttu-id="c0554-127">Usando clicar e arrastar, ou usando o comando **Adicionar à hierarquia** no menu de contexto, adicione as colunas nome **do modelo** e **nome do produto** (em ordem) e coloque-as abaixo da coluna nome da **subcategoria do produto** .</span><span class="sxs-lookup"><span data-stu-id="c0554-127">By using click and drag, or by using the **Add to Hierarchy** command in the context menu, add the **Model Name** and **Product Name** columns (in order) and place them beneath the **Product Subcategory Name** column.</span></span> <span data-ttu-id="c0554-128">Renomeie essas colunas `Model` e `Product` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c0554-128">Rename these columns `Model` and `Product`, respectively.</span></span>  
  
#### <a name="to-create-hierarchies-in-the-date-table"></a><span data-ttu-id="c0554-129">Para criar hierarquias na tabela Data</span><span class="sxs-lookup"><span data-stu-id="c0554-129">To create hierarchies in the Date table</span></span>  
  
1.  <span data-ttu-id="c0554-130">No designer de modelos, clique com o botão direito do mouse na tabela **Data** e clique em **Criar Hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="c0554-130">In the model designer, right-click the **Date** table, and then click **Create Hierarchy**.</span></span>  
  
2.  <span data-ttu-id="c0554-131">Renomeie a hierarquia como **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="c0554-131">Rename the hierarchy to **Calendar**.</span></span>  
  
3.  <span data-ttu-id="c0554-132">Adicione as seguintes colunas, na ordem, e renomeie-as:</span><span class="sxs-lookup"><span data-stu-id="c0554-132">Add the following columns, in-order, and then rename them:</span></span>  
  
    |<span data-ttu-id="c0554-133">Column</span><span class="sxs-lookup"><span data-stu-id="c0554-133">Column</span></span>|<span data-ttu-id="c0554-134">Renomear para:</span><span class="sxs-lookup"><span data-stu-id="c0554-134">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="c0554-135">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="c0554-135">Calendar Year</span></span>|<span data-ttu-id="c0554-136">Ano</span><span class="sxs-lookup"><span data-stu-id="c0554-136">Year</span></span>|  
    |<span data-ttu-id="c0554-137">Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="c0554-137">Calendar Semester</span></span>|<span data-ttu-id="c0554-138">Semester</span><span class="sxs-lookup"><span data-stu-id="c0554-138">Semester</span></span>|  
    |<span data-ttu-id="c0554-139">Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="c0554-139">Calendar Quarter</span></span>|<span data-ttu-id="c0554-140">Trimestre</span><span class="sxs-lookup"><span data-stu-id="c0554-140">Quarter</span></span>|  
    |<span data-ttu-id="c0554-141">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="c0554-141">Month Calendar</span></span>|<span data-ttu-id="c0554-142">Month</span><span class="sxs-lookup"><span data-stu-id="c0554-142">Month</span></span>|  
    |<span data-ttu-id="c0554-143">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="c0554-143">Day Of Month</span></span>|<span data-ttu-id="c0554-144">Dia</span><span class="sxs-lookup"><span data-stu-id="c0554-144">Day</span></span>|  
  
4.  <span data-ttu-id="c0554-145">Na tabela **Date** , repita as etapas acima, criando a hierarquia **Fiscal** , incluindo as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="c0554-145">In the **Date** table, repeat the above steps, creating a **Fiscal** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="c0554-146">Column</span><span class="sxs-lookup"><span data-stu-id="c0554-146">Column</span></span>|<span data-ttu-id="c0554-147">Renomear para:</span><span class="sxs-lookup"><span data-stu-id="c0554-147">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="c0554-148">Fiscal Year</span><span class="sxs-lookup"><span data-stu-id="c0554-148">Fiscal Year</span></span>|<span data-ttu-id="c0554-149">Ano</span><span class="sxs-lookup"><span data-stu-id="c0554-149">Year</span></span>|  
    |<span data-ttu-id="c0554-150">Fiscal Semester</span><span class="sxs-lookup"><span data-stu-id="c0554-150">Fiscal Semester</span></span>|<span data-ttu-id="c0554-151">Semester</span><span class="sxs-lookup"><span data-stu-id="c0554-151">Semester</span></span>|  
    |<span data-ttu-id="c0554-152">Fiscal Quarter</span><span class="sxs-lookup"><span data-stu-id="c0554-152">Fiscal Quarter</span></span>|<span data-ttu-id="c0554-153">Trimestre</span><span class="sxs-lookup"><span data-stu-id="c0554-153">Quarter</span></span>|  
    |<span data-ttu-id="c0554-154">Month Calendar</span><span class="sxs-lookup"><span data-stu-id="c0554-154">Month Calendar</span></span>|<span data-ttu-id="c0554-155">Month</span><span class="sxs-lookup"><span data-stu-id="c0554-155">Month</span></span>|  
    |<span data-ttu-id="c0554-156">Day Of Month</span><span class="sxs-lookup"><span data-stu-id="c0554-156">Day Of Month</span></span>|<span data-ttu-id="c0554-157">Dia</span><span class="sxs-lookup"><span data-stu-id="c0554-157">Day</span></span>|  
  
5.  <span data-ttu-id="c0554-158">Por fim, na tabela **Date** , repita as etapas acima, criando a hierarquia **Calendário de Produção** , incluindo as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="c0554-158">Finally, in the **Date** table, repeat the above steps, creating a **Production Calendar** hierarchy, including the following columns:</span></span>  
  
    |<span data-ttu-id="c0554-159">Column</span><span class="sxs-lookup"><span data-stu-id="c0554-159">Column</span></span>|<span data-ttu-id="c0554-160">Renomear para:</span><span class="sxs-lookup"><span data-stu-id="c0554-160">Rename to:</span></span>|  
    |------------|----------------|  
    |<span data-ttu-id="c0554-161">Calendar Year</span><span class="sxs-lookup"><span data-stu-id="c0554-161">Calendar Year</span></span>|<span data-ttu-id="c0554-162">Ano</span><span class="sxs-lookup"><span data-stu-id="c0554-162">Year</span></span>|  
    |<span data-ttu-id="c0554-163">Week Number Of Year</span><span class="sxs-lookup"><span data-stu-id="c0554-163">Week Number Of Year</span></span>|<span data-ttu-id="c0554-164">Semana</span><span class="sxs-lookup"><span data-stu-id="c0554-164">Week</span></span>|  
    |<span data-ttu-id="c0554-165">Day Of Week</span><span class="sxs-lookup"><span data-stu-id="c0554-165">Day Of Week</span></span>|<span data-ttu-id="c0554-166">Dia</span><span class="sxs-lookup"><span data-stu-id="c0554-166">Day</span></span>|  
  
## <a name="next-steps"></a><span data-ttu-id="c0554-167">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c0554-167">Next Steps</span></span>  
 <span data-ttu-id="c0554-168">Para continuar este tutorial, vá para a próxima lição: [Lição 11: Criar partições](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="c0554-168">To continue this tutorial, go to the next lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
  
