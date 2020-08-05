---
title: Criar e gerenciar medidas (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: edc1a4b2-96d3-4f34-bb70-6cacec79e819
author: minewiskan
ms.author: owend
ms.openlocfilehash: da507bf48b285a1414ffb85ba79da50508a2ae2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572213"
---
# <a name="create-and-manage-measures-ssas-tabular"></a><span data-ttu-id="de759-102">Criar e Gerenciar medidas (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="de759-102">Create and Manage Measures (SSAS Tabular)</span></span>
  <span data-ttu-id="de759-103">Medida é uma fórmula criada para ser usada em um relatório ou Tabela Dinâmica (ou Gráfico Dinâmico) do Excel.</span><span class="sxs-lookup"><span data-stu-id="de759-103">A measure is a formula that is created for use in a report or Excel PivotTable (or PivotChart).</span></span> <span data-ttu-id="de759-104">As medidas podem se basear em funções de agregação padrão, como COUNT ou SUM, ou é possível definir sua própria fórmula usando-se o DAX.</span><span class="sxs-lookup"><span data-stu-id="de759-104">Measures can be based on standard aggregation functions, such as COUNT or SUM, or you can define your own formula by using DAX.</span></span> <span data-ttu-id="de759-105">As tarefas neste tópico descrevem como criar e gerenciar medidas usando a grade de medida de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="de759-105">The tasks in this topic describe how to create and manage measures by using a table's measure grid.</span></span>  
  
 <span data-ttu-id="de759-106">Este tópico inclui as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="de759-106">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="de759-107">Para criar uma medida usando uma fórmula de agregação padrão</span><span class="sxs-lookup"><span data-stu-id="de759-107">To create a measure using a standard aggregation formula</span></span>](#bkmk_create_stand)  
  
-   [<span data-ttu-id="de759-108">Para criar uma medida usando uma fórmula personalizada</span><span class="sxs-lookup"><span data-stu-id="de759-108">To create a measure using a custom formula</span></span>](#bkmk_create_custom)  
  
-   [<span data-ttu-id="de759-109">Para editar propriedades de medida</span><span class="sxs-lookup"><span data-stu-id="de759-109">To edit measure properties</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="de759-110">Para renomear uma medida</span><span class="sxs-lookup"><span data-stu-id="de759-110">To rename a measure</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="de759-111">Para excluir uma medida</span><span class="sxs-lookup"><span data-stu-id="de759-111">To delete a measure</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="de759-112">Tarefas</span><span class="sxs-lookup"><span data-stu-id="de759-112">Tasks</span></span>  
 <span data-ttu-id="de759-113">Para criar e gerenciar medidas, você usará a grade de medida de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="de759-113">To create and manage measures, you will use a table's measure grid.</span></span> <span data-ttu-id="de759-114">Você só pode exibir a grade de medida para uma tabela no designer de modelos em Exibição de Dados.</span><span class="sxs-lookup"><span data-stu-id="de759-114">You can view the measure grid for a table in the model designer in Data View only.</span></span> <span data-ttu-id="de759-115">Você não pode criar medidas ou exibir a grade de medida quando estiver na Exibição de Diagrama; porém, você pode exibir medidas existentes na Exibição de Diagrama.</span><span class="sxs-lookup"><span data-stu-id="de759-115">You cannot create measures or view the measure grid when in Diagram View; however, you can view existing measures in Diagram View.</span></span> <span data-ttu-id="de759-116">Para mostrar a grade de medida para uma tabela, clique no menu **Tabela** e em **Mostrar Grade de Medida**.</span><span class="sxs-lookup"><span data-stu-id="de759-116">To show the measure grid for a table, click the **Table** menu, and then click **Show Measure Grid**.</span></span>  
  
###  <a name="to-create-a-measure-using-a-standard-aggregation-formula"></a><a name="bkmk_create_stand"></a><span data-ttu-id="de759-117">Para criar uma medida usando uma fórmula de agregação padrão</span><span class="sxs-lookup"><span data-stu-id="de759-117">To create a measure using a standard aggregation formula</span></span>  
  
-   <span data-ttu-id="de759-118">Clique na coluna para a qual você deseja criar a medida, clique no menu **Coluna** , aponte para **AutoSoma**e clique em um tipo de agregação.</span><span class="sxs-lookup"><span data-stu-id="de759-118">Click on the column for which you want to create the measure, then click the **Column** menu, then point to **AutoSum**, and then click an aggregation type.</span></span>  
  
     <span data-ttu-id="de759-119">A medida será criada automaticamente com um nome padrão, seguido pela fórmula na primeira célula na grade de medida diretamente abaixo da coluna.</span><span class="sxs-lookup"><span data-stu-id="de759-119">The measure will be created automatically with a default name, followed by the formula in the first cell in the measure grid directly beneath the column.</span></span>  
  
###  <a name="to-create-a-measure-using-a-custom-formula"></a><a name="bkmk_create_custom"></a> <span data-ttu-id="de759-120">Para criar uma medida usando uma fórmula personalizada</span><span class="sxs-lookup"><span data-stu-id="de759-120">To create a measure using a custom formula</span></span>  
  
-   <span data-ttu-id="de759-121">Na grade de medida, abaixo da coluna para a qual você deseja criar a medida, clique em uma célula e, na barra de fórmula, digite um nome, seguido por dois-pontos (:), seguido por um sinal de igualdade (=), seguido pela fórmula.</span><span class="sxs-lookup"><span data-stu-id="de759-121">In the measure grid, beneath the column for which you want to create the measure, click a cell, then in the formula bar, type a name, followed by a colon (:), followed by an equals sign (=), followed by the formula.</span></span> <span data-ttu-id="de759-122">Pressione ENTER para aceitar a fórmula.</span><span class="sxs-lookup"><span data-stu-id="de759-122">Press ENTER to accept the formula.</span></span>  
  
###  <a name="to-edit-measure-properties"></a><a name="bkmk_edit"></a><span data-ttu-id="de759-123">Para editar propriedades de medida</span><span class="sxs-lookup"><span data-stu-id="de759-123">To edit measure properties</span></span>  
  
-   <span data-ttu-id="de759-124">Na grade de medida, clique em uma medida e, na janela **Propriedades** , digite ou selecione um valor de propriedade diferente.</span><span class="sxs-lookup"><span data-stu-id="de759-124">In the measure grid, click a measure, and then In the **Properties** window, type or select a different property value.</span></span>  
  
###  <a name="to-rename-a-measure"></a><a name="bkmk_rename"></a><span data-ttu-id="de759-125">Para renomear uma medida</span><span class="sxs-lookup"><span data-stu-id="de759-125">To rename a measure</span></span>  
  
-   <span data-ttu-id="de759-126">Na grade de medida, clique em uma medida e, na janela **Propriedades** , em **Nome da Medida**, digite um novo nome e clique em ENTER.</span><span class="sxs-lookup"><span data-stu-id="de759-126">In the measure grid, click on a measure, and then In the **Properties** window, in **Measure Name**, type a new name, and then click ENTER.</span></span>  
  
     <span data-ttu-id="de759-127">Você também pode renomear uma medida na barra de fórmula.</span><span class="sxs-lookup"><span data-stu-id="de759-127">You can also rename a measure in the formula bar.</span></span> <span data-ttu-id="de759-128">O nome da medida precede a fórmula, seguido por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="de759-128">The measure name precedes the formula, followed by a colon.</span></span>  
  
###  <a name="to-delete-a-measure"></a><a name="bkmk_delete"></a><span data-ttu-id="de759-129">Para excluir uma medida</span><span class="sxs-lookup"><span data-stu-id="de759-129">To delete a measure</span></span>  
  
-   <span data-ttu-id="de759-130">Na Grade de Medida, clique com o botão direito do mouse em uma medida e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="de759-130">In the measure grid, right-click a measure, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de759-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de759-131">See Also</span></span>  
 <span data-ttu-id="de759-132">[Medidas &#40;&#41;de tabela do SSAS](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="de759-132">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 <span data-ttu-id="de759-133">[KPIs &#40;SSAS de tabela&#41;](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="de759-133">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="de759-134">Colunas calculadas &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="de759-134">Calculated Columns &#40;SSAS Tabular&#41;</span></span>](ssas-calculated-columns.md)  
  
  
