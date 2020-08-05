---
title: Adicionar, alterar ou excluir valores disponíveis para um parâmetro de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportparameters.availablevalues.f1
- "10455"
- "10071"
ms.assetid: 0e03264c-523f-4c59-b71b-ceef600f75f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 985ab3e8dc1d74f94e7242ff57f46ffe4fba9586
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573759"
---
# <a name="add-change-or-delete-available-values-for-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="bc390-102">Adicionar, alterar ou excluir valores disponíveis para um parâmetro de relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bc390-102">Add, Change, or Delete Available Values for a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bc390-103">Depois de criar um parâmetro de relatório, você poderá especificar uma lista de valores disponíveis a ser exibida para o usuário.</span><span class="sxs-lookup"><span data-stu-id="bc390-103">After you create a report parameter, you can specify a list of available values to display to the user.</span></span> <span data-ttu-id="bc390-104">Uma lista de valores disponíveis limita as escolhas do usuário aos valores válidos para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bc390-104">An available values list limits the choices a user can make to only valid values for the parameter.</span></span>  
  
 <span data-ttu-id="bc390-105">Os valores disponíveis são exibidos em uma lista suspensa ao lado do parâmetro de relatório na barra de ferramentas quando o relatório é executado.</span><span class="sxs-lookup"><span data-stu-id="bc390-105">Available values appear in a drop-down list next to the report parameter on the toolbar when the report runs.</span></span> <span data-ttu-id="bc390-106">Os parâmetros de relatório podem representar um valor ou diversos valores.</span><span class="sxs-lookup"><span data-stu-id="bc390-106">Report parameters can represent one value or multiple values.</span></span> <span data-ttu-id="bc390-107">No caso de diversos valores, a lista começa com um recurso **Selecionar Tudo** , através do qual o usuário pode selecionar ou desmarcar todos os valores com um só clique.</span><span class="sxs-lookup"><span data-stu-id="bc390-107">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span>  
  
 <span data-ttu-id="bc390-108">É possível fornecer uma lista de valores estática ou uma lista baseada em um conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="bc390-108">You can provide a static list of values or a list from a report dataset.</span></span> <span data-ttu-id="bc390-109">Se preferir, você pode especificar um nome amigável para os valores usando um campo de rótulo.</span><span class="sxs-lookup"><span data-stu-id="bc390-109">You can optionally provide a friendly name for values by specifying a label field.</span></span> <span data-ttu-id="bc390-110">Por exemplo, no caso de um parâmetro baseado em um campo `ProductID` , você pode exibir o campo `ProductName` no rótulo do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bc390-110">For example, for a parameter based on a `ProductID` field, you can display the `ProductName` field in the parameter label.</span></span> <span data-ttu-id="bc390-111">Quando o relatório é executado, o usuário pode escolher uma opção entre os nomes de produto, mas o valor efetivamente escolhido é o `ProductID`correspondente.</span><span class="sxs-lookup"><span data-stu-id="bc390-111">When the report runs, the user can choose from the product names, but the actual chosen value is the corresponding `ProductID`.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="bc390-112">Depois de publicar um relatório, você poderá sobrescrever os valores que você definiu no relatório na ferramenta de criação de relatório, configurando os valores de propriedade de parâmetro no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="bc390-112">After you publish a report, you can override the available values that you define in the report in the report authoring tool, by setting parameter property values on the report server.</span></span> <span data-ttu-id="bc390-113">Para obter mais informações, consulte [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="bc390-113">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md).</span></span>  
  
### <a name="to-add-or-change-the-available-values-for-a-report-parameter"></a><span data-ttu-id="bc390-114">Para adicionar ou alterar os valores disponíveis para um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="bc390-114">To add or change the available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="bc390-115">No painel de dados do relatório, expanda o nó Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="bc390-115">In the Report Data pane, expand the Parameters node.</span></span> <span data-ttu-id="bc390-116">Clique com o botão direito do mouse no parâmetro e clique em **Propriedades do Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="bc390-116">Right-click the parameter and click **Parameter Properties**.</span></span> <span data-ttu-id="bc390-117">A caixa de diálogo **Propriedades do Parâmetro do Relatório** é aberta.</span><span class="sxs-lookup"><span data-stu-id="bc390-117">The **Report Parameter Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc390-118">Se o painel Dados do Relatório não estiver visível, clique em **Exibir** e em **Dados do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="bc390-118">If the Report Data pane is not visible, click **View** and then click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="bc390-119">Clique em **Valores Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="bc390-119">Click **Available Values**.</span></span> <span data-ttu-id="bc390-120">Selecione uma opção de valores disponíveis:</span><span class="sxs-lookup"><span data-stu-id="bc390-120">Select an available values option:</span></span>  
  
    -   <span data-ttu-id="bc390-121">Clique em **Especificar valores** para fornecer a lista de valores manualmente e, se desejar, nomes amigáveis (rótulos) para os valores.</span><span class="sxs-lookup"><span data-stu-id="bc390-121">Click **Specify values** to manually provide a list of values, and optionally, friendly names (the labels) for the values.</span></span>  
  
         <span data-ttu-id="bc390-122">Clique em **Adicionar** , insira o valor na caixa de texto **Valor** e, opcionalmente, o rótulo na caixa de texto **Rótulo** .</span><span class="sxs-lookup"><span data-stu-id="bc390-122">Click **Add** and then enter the value in the **Value** text box, and optionally, the label in the **Label** text box.</span></span> <span data-ttu-id="bc390-123">Se você não fornecer um rótulo, será usado o valor.</span><span class="sxs-lookup"><span data-stu-id="bc390-123">If you do not provide a label, the value is used.</span></span> <span data-ttu-id="bc390-124">Você pode gravar uma expressão para um valor.</span><span class="sxs-lookup"><span data-stu-id="bc390-124">You can write an expression for a value.</span></span> <span data-ttu-id="bc390-125">O tipo de dados deve coincidir com o tipo de dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bc390-125">The data type must match the data type of the parameter.</span></span> <span data-ttu-id="bc390-126">Os nomes de campo não podem ser usados em uma expressão para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bc390-126">Field names cannot be used in an expression for a parameter.</span></span> <span data-ttu-id="bc390-127">Para obter exemplos, consulte [Filtros geralmente usados &#40;Construtor de Relatórios e SSRS&#41;](commonly-used-filters-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bc390-127">For examples, see [Commonly Used Filters &#40;Report Builder and SSRS&#41;](commonly-used-filters-report-builder-and-ssrs.md).</span></span>  
  
         <span data-ttu-id="bc390-128">Repita esta etapa para todos os valores quantos você deseja fornecer.</span><span class="sxs-lookup"><span data-stu-id="bc390-128">Repeat this step for as many values as you want to provide.</span></span> <span data-ttu-id="bc390-129">A ordem dos itens que você vê nesta lista determina a ordem em que o usuário os vê na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="bc390-129">The order of items you see in this list determines the order that the user sees them in the drop-down list.</span></span> <span data-ttu-id="bc390-130">Para alterar a ordem de um item da lista, clique em uma caixa de texto **Valor** ou **Rótulo** para selecionar o item desejado e use os botões de seta para cima e para baixo para colocar o item no início ou no final da lista.</span><span class="sxs-lookup"><span data-stu-id="bc390-130">To change the order of an item in the list, click a **Value** or **Label** text box to select the item, and then use the up and down arrow buttons to move the item higher or lower in the list.</span></span>  
  
    -   <span data-ttu-id="bc390-131">Clique em **Obter valores de uma consulta** para fornecer o nome de um conjunto de dados existente que recupera os valores e, opcionalmente, os nomes amigáveis deste parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bc390-131">Click **Get values from a query** to provide the name of an existing dataset that retrieves the values, and optionally, the friendly names for this parameter.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="bc390-132">Se o mesmo conjunto de dados contiver o parâmetro de consulta correspondente ao parâmetro de relatórios, o relatório exibirá uma mensagem de erro quando tentar executá-lo.</span><span class="sxs-lookup"><span data-stu-id="bc390-132">If the same dataset contains the corresponding query parameter for the report parameter, the report will display an error message when you try to run it.</span></span> <span data-ttu-id="bc390-133">Você pode solucionar esse erro usando um conjunto de dados diferente para recuperar os valores.</span><span class="sxs-lookup"><span data-stu-id="bc390-133">You resolve this error by using a different dataset to retrieve the values.</span></span>  
  
         <span data-ttu-id="bc390-134">Em **Conjunto de dados**, escolha o nome do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="bc390-134">In **Dataset**, choose the name of the dataset.</span></span>  
  
         <span data-ttu-id="bc390-135">No campo **Valor**, escolha o nome do campo que fornece os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bc390-135">In **Value field**, choose the name of the field that provides parameter values.</span></span>  
  
         <span data-ttu-id="bc390-136">No **campo Rótulo**, escolha o nome do campo que fornece os nomes amigáveis do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bc390-136">In **Label field**, choose the name of the field that provides the friendly names for the parameter.</span></span> <span data-ttu-id="bc390-137">Se não houver um campo separado para nomes amigáveis, escolha o mesmo campo escolhido para **Valor** .</span><span class="sxs-lookup"><span data-stu-id="bc390-137">If there is no separate field for friendly names, choose the same field as you chose for the **Value** field.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="bc390-138">Quando visualiza o relatório, você vê uma lista suspensa dos valores disponíveis para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bc390-138">When you preview the report, you see a drop-down list of available values for the parameter.</span></span>  
  
### <a name="to-remove-the-available-values-for-a-report-parameter"></a><span data-ttu-id="bc390-139">Para remover os valores disponíveis para um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="bc390-139">To remove the available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="bc390-140">No painel de dados do relatório, expanda o nó Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="bc390-140">In the Report Data pane, expand the Parameters node.</span></span> <span data-ttu-id="bc390-141">Clique com o botão direito do mouse no parâmetro e clique em **Propriedades do Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="bc390-141">Right-click the parameter and click **Parameter Properties**.</span></span> <span data-ttu-id="bc390-142">A caixa de diálogo **Parâmetros de Relatório** é exibida.</span><span class="sxs-lookup"><span data-stu-id="bc390-142">The **Report Parameters** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="bc390-143">Clique em **Valores Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="bc390-143">Click **Available Values**.</span></span>  
  
3.  <span data-ttu-id="bc390-144">Em **Selecione uma das seguintes opções**, clique em **Nenhuma**.</span><span class="sxs-lookup"><span data-stu-id="bc390-144">In **Select from one of the following options**, click **None**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="bc390-145">Quando você visualiza o relatório, a lista suspensa dos valores disponíveis para o parâmetro não aparece mais.</span><span class="sxs-lookup"><span data-stu-id="bc390-145">When you preview the report, you the drop-down list of available values for the parameter no longer appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc390-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc390-146">See Also</span></span>  
 <span data-ttu-id="bc390-147">[Alterar a ordem de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc390-147">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bc390-148">[Adicionar, alterar ou excluir um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc390-148">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bc390-149">[Adicionar parâmetros em cascata a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc390-149">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bc390-150">[Adicionar, alterar ou excluir valores padrão de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="bc390-150">[Add, Change, or Delete Default Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="bc390-151">[Referências de coleção de parâmetros &#40;Construtor de Relatórios e SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="bc390-151">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 <span data-ttu-id="bc390-152">[Tutorial: Adicionar um parâmetro ao relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="bc390-152">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 [<span data-ttu-id="bc390-153">Expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc390-153">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
