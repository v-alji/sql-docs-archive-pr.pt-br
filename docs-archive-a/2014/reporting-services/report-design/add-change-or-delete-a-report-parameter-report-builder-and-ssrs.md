---
title: Adicionar, alterar ou excluir um parâmetro de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d44a8e0a-10cf-4502-9391-09743ffc9bad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 231cd51d7ed0a481f004b39a2e8819df3fc33748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573771"
---
# <a name="add-change-or-delete-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="3ea47-102">Adicionar, alterar ou excluir um parâmetro de relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="3ea47-102">Add, Change, or Delete a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3ea47-103">Um parâmetro de relatório fornece uma maneira de escolher dados de relatório, conectar relatórios relacionados e variar a apresentação do relatório.</span><span class="sxs-lookup"><span data-stu-id="3ea47-103">A report parameter provides a way to choose report data, connect related reports together, and vary the report presentation.</span></span> <span data-ttu-id="3ea47-104">Você pode fornecer um valor padrão e uma lista de valores disponíveis e o usuário pode alterar a seleção.</span><span class="sxs-lookup"><span data-stu-id="3ea47-104">You can provide a default value and a list of available values, and the user can change the selection.</span></span>  
  
 <span data-ttu-id="3ea47-105">Depois de publicar um relatório, você poderá alterar os valores padrão, os valores disponíveis e outras propriedades para um parâmetro de relatório no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="3ea47-105">After you publish a report, you can change the default values, the available values, and other properties for a report parameter on the report server.</span></span> <span data-ttu-id="3ea47-106">Você pode fornecer vários conjuntos de valores de parâmetros padrão criando relatórios vinculados.</span><span class="sxs-lookup"><span data-stu-id="3ea47-106">You can provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="3ea47-107">Para obter mais informações, consulte "Setting Parameter Properties for a Published Report" na documentação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nos [Manuais Online do SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="3ea47-107">For more information, see "Setting Parameter Properties for a Published Report" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-or-edit-a-report-parameter"></a><span data-ttu-id="3ea47-108">Para adicionar ou editar um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="3ea47-108">To add or edit a report parameter</span></span>  
  
1.  <span data-ttu-id="3ea47-109">No painel **Dados do Relatório** , clique com o botão direito do mouse no nó **Parâmetros** e clique em **Adicionar Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="3ea47-109">In the **Report Data** pane, right-click the **Parameters** node and click **Add Parameter**.</span></span> <span data-ttu-id="3ea47-110">A caixa de diálogo **Propriedades do Parâmetro do Relatório** é aberta.</span><span class="sxs-lookup"><span data-stu-id="3ea47-110">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3ea47-111">Em **Nome**, digite o nome do parâmetro ou aceite o nome padrão.</span><span class="sxs-lookup"><span data-stu-id="3ea47-111">In **Name**, type the name of the parameter or accept the default name.</span></span>  
  
3.  <span data-ttu-id="3ea47-112">No **Prompt**, digite o texto que é exibido ao lado da caixa de texto do parâmetro quando o usuário executa o relatório.</span><span class="sxs-lookup"><span data-stu-id="3ea47-112">In **Prompt**, type the text that appears next to the parameter text box when the user runs the report.</span></span>  
  
4.  <span data-ttu-id="3ea47-113">Na lista **Tipo de dados**, selecione o tipo de dados do valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3ea47-113">In **Data type**, select the data type for the parameter value.</span></span>  
  
5.  <span data-ttu-id="3ea47-114">Se o parâmetro pode conter um valor em branco, selecione **Permitir valor em branco**.</span><span class="sxs-lookup"><span data-stu-id="3ea47-114">If the parameter can contain a blank value, select **Allow blank value**.</span></span>  
  
6.  <span data-ttu-id="3ea47-115">Se o parâmetro pode conter um valor nulo, selecione **Permitir valor nulo**.</span><span class="sxs-lookup"><span data-stu-id="3ea47-115">If the parameter can contain a null value, select **Allow null value**.</span></span>  
  
7.  <span data-ttu-id="3ea47-116">Para permitir que um usuário selecione mais de um valor do parâmetro, selecione **Permitir diversos valores**.</span><span class="sxs-lookup"><span data-stu-id="3ea47-116">To allow a user to select more than one value for the parameter, select **Allow multiple values**.</span></span>  
  
8.  <span data-ttu-id="3ea47-117">Defina a opção de visibilidade.</span><span class="sxs-lookup"><span data-stu-id="3ea47-117">Set the visibility option.</span></span>  
  
    -   <span data-ttu-id="3ea47-118">Para mostrar o parâmetro na barra de ferramentas na parte superior do relatório, selecione **Visível**.</span><span class="sxs-lookup"><span data-stu-id="3ea47-118">To show the parameter on the toolbar at the top of the report, select **Visible**.</span></span>  
  
    -   <span data-ttu-id="3ea47-119">Para ocultar o parâmetro para que ele não seja exibido na barra de ferramentas, selecione **Oculto**.</span><span class="sxs-lookup"><span data-stu-id="3ea47-119">To hide the parameter so that it does not display on the toolbar, select **Hidden**.</span></span>  
  
    -   <span data-ttu-id="3ea47-120">Para ocultar o parâmetro e impedi-lo de ser modificado no servidor de relatórios depois que o relatório é publicado, selecione **Interno**.</span><span class="sxs-lookup"><span data-stu-id="3ea47-120">To hide the parameter and protect it from being modified on the report server after the report is published, select **Internal**.</span></span> <span data-ttu-id="3ea47-121">O parâmetro de relatório só pode ser exibido na definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="3ea47-121">The report parameter can then only be viewed in the report definition.</span></span> <span data-ttu-id="3ea47-122">Para essa opção, você deve definir um valor padrão ou permitir que o parâmetro aceite um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="3ea47-122">For this option, you must set a default value or allow the parameter to accept a null value.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-report-parameter"></a><span data-ttu-id="3ea47-123">Para excluir um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="3ea47-123">To delete a report parameter</span></span>  
  
1.  <span data-ttu-id="3ea47-124">No painel **Dados do Relatório** , expanda o nó **Parâmetros** .</span><span class="sxs-lookup"><span data-stu-id="3ea47-124">In the **Report Data** pane, expand the **Parameters** node.</span></span>  
  
2.  <span data-ttu-id="3ea47-125">Clique com o botão direito do mouse no parâmetro do relatório e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="3ea47-125">Right-click the report parameter and click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea47-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ea47-126">See Also</span></span>  
 <span data-ttu-id="3ea47-127">[Adicionar, alterar ou excluir valores disponíveis para um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-127">[Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="3ea47-128">[Adicione, altere ou exclua valores padrão para um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-128">[Add, Change, or Delete Default Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="3ea47-129">[Alterar a ordem de um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-129">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3ea47-130">[Parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-130">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="3ea47-131">[Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-131">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="3ea47-132">[Adicionar parâmetros em cascata a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-132">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3ea47-133">[Tutorial: adicionar um parâmetro ao seu relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-133">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="3ea47-134">[TUTORIAIS &#40;Construtor de Relatórios&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-134">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="3ea47-135">[Adicionar filtros de conjunto de dados, filtros de região e filtros de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-135">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="3ea47-136">[Referências de coleção de parâmetros &#40;Construtor de Relatórios e SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="3ea47-136">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 [<span data-ttu-id="3ea47-137">Adicionar um parâmetro com vários valores a um relatório</span><span class="sxs-lookup"><span data-stu-id="3ea47-137">Add a multi-value parameter to a Report</span></span>](add-a-multi-value-parameter-to-a-report.md)  
  
  
