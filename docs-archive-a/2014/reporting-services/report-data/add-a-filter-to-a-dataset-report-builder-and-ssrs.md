---
title: Adicionar um filtro a um conjunto de dados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eed37e74-6a43-4d7c-9959-2d5fa6a6aba9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f51411d31d8ee29bf0f163085077dcee8fd79bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569145"
---
# <a name="add-a-filter-to-a-dataset-report-builder-and-ssrs"></a><span data-ttu-id="5cea7-102">Adicionar um filtro a um conjunto de dados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5cea7-102">Add a Filter to a Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5cea7-103">Adicione um filtro a um conjunto de dados para limitar os dados em um relatório depois que os dados forem recuperados de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="5cea7-103">Add a filter to a dataset to limit the data in a report after the data is retrieved from an external data source.</span></span> <span data-ttu-id="5cea7-104">Quando você adiciona um filtro a um conjunto de dados, todas as partes de relatório ou regiões de dados usam somente dados que correspondem às condições de filtro.</span><span class="sxs-lookup"><span data-stu-id="5cea7-104">When you add a filter to a dataset, all report parts or data regions use only data that matches the filter conditions.</span></span>  
  
 <span data-ttu-id="5cea7-105">Para um conjunto de dados compartilhado, um filtro que se aplica a todos os itens dependentes deve fazer parte da definição de banco de dados compartilhada no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5cea7-105">For a shared dataset, a filter that applies to all dependent items must be part of the shared dataset definition on the report server.</span></span> <span data-ttu-id="5cea7-106">Um relatório ou parte de relatório que contém uma instância de um conjunto de dados compartilhado pode criar um filtro adicional que se aplica somente à instância.</span><span class="sxs-lookup"><span data-stu-id="5cea7-106">A report or report part that contains an instance of a shared dataset can create an additional filter that applies only to the instance.</span></span>  
  
 <span data-ttu-id="5cea7-107">Para adicionar um filtro, é necessário especificar uma ou mais condições que são equações de filtro.</span><span class="sxs-lookup"><span data-stu-id="5cea7-107">To add a filter, you must specify one or more conditions that are filter equations.</span></span> <span data-ttu-id="5cea7-108">Uma equação de filtro é composta por uma expressão que identifica os dados que você deseja filtrar, um operador, e o valor para comparação.</span><span class="sxs-lookup"><span data-stu-id="5cea7-108">A filter equation consists of an expression that identifies the data that you want to filter, an operator, and the value to compare to.</span></span> <span data-ttu-id="5cea7-109">Os tipos de dados dos dados filtrados e o valor devem coincidir.</span><span class="sxs-lookup"><span data-stu-id="5cea7-109">The data types of the filtered data and the value must match.</span></span> <span data-ttu-id="5cea7-110">Não há suporte para filtragem de valores de agregação para um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="5cea7-110">Filtering on aggregate values for a dataset is not supported.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-filter-to-a-shared-dataset"></a><span data-ttu-id="5cea7-111">Para adicionar um filtro a um banco de dados compartilhado</span><span class="sxs-lookup"><span data-stu-id="5cea7-111">To add a filter to a shared dataset</span></span>  
  
1.  <span data-ttu-id="5cea7-112">Abra um conjunto de dados compartilhado em modo compartilhado.</span><span class="sxs-lookup"><span data-stu-id="5cea7-112">Open a shared dataset in shared dataset mode.</span></span>  
  
2.  <span data-ttu-id="5cea7-113">Na guia **Página Inicial** , no grupo **Conjunto de Dados Compartilhado** , clique em Conjunto de Dados.</span><span class="sxs-lookup"><span data-stu-id="5cea7-113">On the **Home** tab, in the **Shared Datasets** group, click Datasets.</span></span> <span data-ttu-id="5cea7-114">A caixa de diálogo **Propriedades do Conjunto de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="5cea7-114">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="5cea7-115">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="5cea7-115">Click **Filters**.</span></span> <span data-ttu-id="5cea7-116">Isso exibirá a lista atual de equações de filtros.</span><span class="sxs-lookup"><span data-stu-id="5cea7-116">This displays the current list of filter equations.</span></span> <span data-ttu-id="5cea7-117">Por padrão, a lista está vazia.</span><span class="sxs-lookup"><span data-stu-id="5cea7-117">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="5cea7-118">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5cea7-118">Click **Add**.</span></span> <span data-ttu-id="5cea7-119">Uma nova equação de filtro em branco é exibida.</span><span class="sxs-lookup"><span data-stu-id="5cea7-119">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="5cea7-120">Em **Expressão**, digite ou selecione a expressão do campo a ser filtrada.</span><span class="sxs-lookup"><span data-stu-id="5cea7-120">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="5cea7-121">Para editar a expressão, clique no botão de expressão (*fx*).</span><span class="sxs-lookup"><span data-stu-id="5cea7-121">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="5cea7-122">Na caixa de lista, selecione o tipo de dados que corresponde ao tipo de dados da expressão criada na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="5cea7-122">From the list box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="5cea7-123">Na caixa **Operador** , selecione o operador que você deseja que o filtro use para comparar os valores nas caixas **Expressão** e **Valor** .</span><span class="sxs-lookup"><span data-stu-id="5cea7-123">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="5cea7-124">O operador escolhido determinará o número de valores que serão usados na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="5cea7-124">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="5cea7-125">Na caixa **Valor** , digite a expressão ou o valor em relação ao qual você deseja que o filtro avalie o valor em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="5cea7-125">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="5cea7-126">Para obter exemplos de equações de filtro, consulte [Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5cea7-126">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-filter-to-an-embedded-dataset-or-a-shared-dataset-instance"></a><span data-ttu-id="5cea7-127">Para adicionar um filtro a um conjunto de dados inserido ou uma instância de conjunto de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="5cea7-127">To add a filter to an embedded dataset or a shared dataset instance</span></span>  
  
1.  <span data-ttu-id="5cea7-128">Abra um relatório no modo de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="5cea7-128">Open a report in report design mode.</span></span>  
  
2.  <span data-ttu-id="5cea7-129">Clique com o botão direito do mouse no painel **Dados do Relatório** e clique em **Propriedades do Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="5cea7-129">Right-click a dataset in the **Report Data** pane and then click **Dataset Properties**.</span></span> <span data-ttu-id="5cea7-130">A caixa de diálogo **Propriedades do Conjunto de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="5cea7-130">The **Dataset Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="5cea7-131">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="5cea7-131">Click **Filters**.</span></span> <span data-ttu-id="5cea7-132">Isso exibirá a lista atual de equações de filtros.</span><span class="sxs-lookup"><span data-stu-id="5cea7-132">This displays the current list of filter equations.</span></span> <span data-ttu-id="5cea7-133">Por padrão, a lista está vazia.</span><span class="sxs-lookup"><span data-stu-id="5cea7-133">By default, the list is empty.</span></span>  
  
4.  <span data-ttu-id="5cea7-134">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5cea7-134">Click **Add**.</span></span> <span data-ttu-id="5cea7-135">Uma nova equação de filtro em branco é exibida.</span><span class="sxs-lookup"><span data-stu-id="5cea7-135">A new blank filter equation appears.</span></span>  
  
5.  <span data-ttu-id="5cea7-136">Em **Expressão**, digite ou selecione a expressão do campo a ser filtrada.</span><span class="sxs-lookup"><span data-stu-id="5cea7-136">In **Expression**, type or select the expression for the field to filter.</span></span> <span data-ttu-id="5cea7-137">Para editar a expressão, clique no botão de expressão (*fx*).</span><span class="sxs-lookup"><span data-stu-id="5cea7-137">To edit the expression, click the expression (*fx*) button.</span></span>  
  
6.  <span data-ttu-id="5cea7-138">Na caixa suspensa, selecione o tipo de dados que coincide com o tipo de dados da expressão criada na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="5cea7-138">From the drop-down box, select the data type that matches the type of data in the expression you created in step 5.</span></span>  
  
7.  <span data-ttu-id="5cea7-139">Na caixa **Operador** , selecione o operador que você deseja que o filtro use para comparar os valores nas caixas **Expressão** e **Valor** .</span><span class="sxs-lookup"><span data-stu-id="5cea7-139">In the **Operator** box, select the operator that you want the filter to use to compare the values in the **Expression** box and the **Value** box.</span></span> <span data-ttu-id="5cea7-140">O operador escolhido determinará o número de valores que serão usados na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="5cea7-140">The operator you choose determines the number of values that are used from the next step.</span></span>  
  
8.  <span data-ttu-id="5cea7-141">Na caixa **Valor** , digite a expressão ou o valor em relação ao qual você deseja que o filtro avalie o valor em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="5cea7-141">In the **Value** box, type the expression or value against which you want the filter to evaluate the value in **Expression**.</span></span>  
  
     <span data-ttu-id="5cea7-142">Para obter exemplos de equações de filtro, consulte [Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5cea7-142">For examples of filter equations, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](../report-design/filter-equation-examples-report-builder-and-ssrs.md).</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5cea7-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5cea7-143">See Also</span></span>  
 <span data-ttu-id="5cea7-144">[Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="5cea7-144">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](../report-design/add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="5cea7-145">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5cea7-145">[Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5cea7-146">Adicionar um filtro &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5cea7-146">Add a Filter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/add-a-filter-report-builder-and-ssrs.md)  
  
  
