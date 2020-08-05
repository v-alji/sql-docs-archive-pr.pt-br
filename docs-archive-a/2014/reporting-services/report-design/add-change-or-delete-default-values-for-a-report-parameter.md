---
title: Adicionar, alterar ou excluir valores padrão para um parâmetro de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10460"
- sql12.rtp.rptdesigner.reportparameters.defaultvalues.f1
- "10072"
ms.assetid: 6a87e069-b3a9-47b6-bcec-afcdd8aff65f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1d50fdbbe42a656ef839785c0968b36c8c829e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573765"
---
# <a name="add-change-or-delete-default-values-for-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="33d56-102">Adicionar, alterar ou excluir valores padrão de um parâmetro de relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="33d56-102">Add, Change, or Delete Default Values for a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="33d56-103">Depois de criar um parâmetro de relatório, você poderá fornecer uma lista de valores padrão.</span><span class="sxs-lookup"><span data-stu-id="33d56-103">After you create a report parameter, you can provide a list of default values.</span></span> <span data-ttu-id="33d56-104">Se todos os parâmetros tiverem um valor padrão válido, o relatório será executado automaticamente na primeira vez em que ele for exibido ou visualizado.</span><span class="sxs-lookup"><span data-stu-id="33d56-104">If all parameters have a valid default value, the report runs automatically when you first view or preview it.</span></span>  
  
 <span data-ttu-id="33d56-105">Os parâmetros de relatório podem representar um valor ou diversos valores.</span><span class="sxs-lookup"><span data-stu-id="33d56-105">Report parameters can represent one value or multiple values.</span></span> <span data-ttu-id="33d56-106">Para valores únicos, é possível fornecer um literal ou expressão.</span><span class="sxs-lookup"><span data-stu-id="33d56-106">For single values, you can provide a literal or expression.</span></span> <span data-ttu-id="33d56-107">Para vários valores, é possível fornecer uma lista estática ou uma lista de um conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="33d56-107">For multiple values, you can provide a static list or a list from a report dataset.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="33d56-108">Depois de publicar um relatório, você poderá sobrescrever os valores padrão que você definiu no relatório na ferramenta de criação de relatório, configurando os valores de propriedade de parâmetro no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="33d56-108">After you publish a report, you can override the default values that you define in the report in the report authoring tool, by setting parameter property values on the report server.</span></span> <span data-ttu-id="33d56-109">Você também pode fornecer vários conjuntos de valores de parâmetros padrão criando relatórios vinculados.</span><span class="sxs-lookup"><span data-stu-id="33d56-109">You can also provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="33d56-110">Para obter mais informações, consulte  [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="33d56-110">For more information, see  [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md)</span></span>  
  
### <a name="to-add-or-change-the-default-values-for-a-report-parameter"></a><span data-ttu-id="33d56-111">Para adicionar ou alterar valores padrão de um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="33d56-111">To add or change the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="33d56-112">No painel de dados do relatório, expanda o nó **Parâmetros** .</span><span class="sxs-lookup"><span data-stu-id="33d56-112">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="33d56-113">Clique com o botão direito do mouse no parâmetro e escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="33d56-113">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="33d56-114">A caixa de diálogo **Propriedades do Parâmetro do Relatório** é aberta.</span><span class="sxs-lookup"><span data-stu-id="33d56-114">The **Report Parameter Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33d56-115">Se o painel Dados do Relatório não estiver visível, clique em **Exibir** e em **Dados do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="33d56-115">If the Report Data pane is not visible, click **View** and then click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="33d56-116">Clique em **Valores Padrão**.</span><span class="sxs-lookup"><span data-stu-id="33d56-116">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="33d56-117">Selecione uma opção padrão:</span><span class="sxs-lookup"><span data-stu-id="33d56-117">Select a default option:</span></span>  
  
    -   <span data-ttu-id="33d56-118">Para fornecer manualmente um valor ou uma lista de valores, clique em **Especificar valores**.</span><span class="sxs-lookup"><span data-stu-id="33d56-118">To manually provide a value or list of values, click **Specify values**.</span></span> <span data-ttu-id="33d56-119">Clique em **Adicionar** e na caixa de texto **Valor** , digite um valor.</span><span class="sxs-lookup"><span data-stu-id="33d56-119">Click **Add** and then enter the value in the **Value** text box.</span></span> <span data-ttu-id="33d56-120">Você pode gravar uma expressão para um valor.</span><span class="sxs-lookup"><span data-stu-id="33d56-120">You can write an expression for a value.</span></span> <span data-ttu-id="33d56-121">O tipo de dados deve coincidir com o tipo de dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="33d56-121">The data type must match the data type of the parameter.</span></span> <span data-ttu-id="33d56-122">Os nomes de campo não podem ser usados em uma expressão para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="33d56-122">Field names cannot be used in an expression for a parameter.</span></span>  
  
         <span data-ttu-id="33d56-123">Para parâmetros de vários valores, repita esta etapa para todos os valores que deseja fornecer.</span><span class="sxs-lookup"><span data-stu-id="33d56-123">For multivalue parameters, repeat this step for as many values as you want to provide.</span></span> <span data-ttu-id="33d56-124">A ordem dos itens que você vê nesta lista determina a ordem em que o usuário os vê na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="33d56-124">The order of items you see in this list determines the order that the user sees them in the drop-down list.</span></span> <span data-ttu-id="33d56-125">Para alterar a ordem de um item na lista, clique na caixa de texto **Valor** para selecionar o item desejado e use os botões de seta para cima e para baixo para movê-lo para cima ou para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="33d56-125">To change the order of an item in the list, click the **Value** text box to select the item, and then use the up and down arrow buttons to move the item higher or lower in the list.</span></span>  
  
    -   <span data-ttu-id="33d56-126">Para fornecer o nome de um conjunto de dados existente que recupera os valores, clique em **Obter valores de uma consulta**.</span><span class="sxs-lookup"><span data-stu-id="33d56-126">To provide the name of an existing dataset that retrieves the values, click **Get values from a query**.</span></span> <span data-ttu-id="33d56-127">Em **Conjunto de dados**, escolha o nome do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="33d56-127">In **Dataset**, choose the name of the dataset.</span></span>  
  
         <span data-ttu-id="33d56-128">No campo **Valor**, escolha o nome do campo que fornece os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="33d56-128">In **Value field**, choose the name of the field that provides parameter values.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-the-default-values-for-a-report-parameter"></a><span data-ttu-id="33d56-129">Para remover ou alterar valores padrão de um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="33d56-129">To remove the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="33d56-130">No painel de dados do relatório, expanda o nó **Parâmetros** .</span><span class="sxs-lookup"><span data-stu-id="33d56-130">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="33d56-131">Clique com o botão direito do mouse no parâmetro e escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="33d56-131">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="33d56-132">A caixa de diálogo **Propriedades do Parâmetro do Relatório** é aberta.</span><span class="sxs-lookup"><span data-stu-id="33d56-132">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="33d56-133">Clique em **Valores Padrão**.</span><span class="sxs-lookup"><span data-stu-id="33d56-133">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="33d56-134">Em **Selecione uma das seguintes opções**, clique em **Nenhum valor padrão**.</span><span class="sxs-lookup"><span data-stu-id="33d56-134">In **Select from one of the following options**, click **No default value**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33d56-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33d56-135">See Also</span></span>  
 <span data-ttu-id="33d56-136">[Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="33d56-136">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="33d56-137">[Adicionar parâmetros em cascata a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="33d56-137">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="33d56-138">[Tutorial: Adicionar um parâmetro ao relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="33d56-138">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="33d56-139">[Adicionar filtros de conjunto de dados, de região de dados e de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="33d56-139">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="33d56-140">[Referências de coleção de parâmetros &#40;Construtor de Relatórios e SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="33d56-140">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 <span data-ttu-id="33d56-141">[Alterar a ordem de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="33d56-141">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="33d56-142">[Adicionar, alterar ou excluir um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="33d56-142">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="33d56-143">Expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="33d56-143">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
