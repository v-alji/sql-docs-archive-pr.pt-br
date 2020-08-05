---
title: Formatar o texto em uma caixa de texto (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df0794b5-96b0-4034-bd17-1be7f31e29db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 522bc420f77b2e5e9d2163c28d3d688b7c47883c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572389"
---
# <a name="format-text-in-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="e7996-102">Formatar o texto em uma caixa de texto (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e7996-102">Format Text in a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e7996-103">Você pode formatar qualquer parte do texto dentro de uma caixa de texto de forma independente e mesclar texto de espaço reservado e texto estático em uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="e7996-103">You can format any part of the text within a text box independently, and mix placeholder text and static text in one text box.</span></span> <span data-ttu-id="e7996-104">Essa capacidade de mesclar formatos e adicionar texto de espaço reservado permite criar mesclagens de mensagens ou modelos de texto no seu relatório.</span><span class="sxs-lookup"><span data-stu-id="e7996-104">This ability to mix formats and add placeholder text enables you to create mail merges or templates for text in your report.</span></span> <span data-ttu-id="e7996-105">Qualquer expressão pode ser definida e formatada separadamente usando um espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="e7996-105">Any expression can be defined and formatted separately using a placeholder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-combine-multiple-formats-in-a-text-box"></a><span data-ttu-id="e7996-106">Para combinar vários formatos em uma caixa de texto</span><span class="sxs-lookup"><span data-stu-id="e7996-106">To combine multiple formats in a text box</span></span>  
  
1.  <span data-ttu-id="e7996-107">Na guia **Inserir** , clique em **Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="e7996-107">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="e7996-108">Clique na superfície de design e arraste-a para criar uma caixa com o tamanho desejado.</span><span class="sxs-lookup"><span data-stu-id="e7996-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
2.  <span data-ttu-id="e7996-109">Na caixa de texto, selecione o texto que deseja formatar.</span><span class="sxs-lookup"><span data-stu-id="e7996-109">Inside the text box, select the text you want to format.</span></span>  
  
3.  <span data-ttu-id="e7996-110">Clique com o botão direito do mouse no texto selecionado e clique em **Propriedades do Texto**.</span><span class="sxs-lookup"><span data-stu-id="e7996-110">Right-click the selected text, and click **Text Properties**.</span></span>  
  
4.  <span data-ttu-id="e7996-111">Defina as opções de formatação.</span><span class="sxs-lookup"><span data-stu-id="e7996-111">Set formatting options.</span></span> <span data-ttu-id="e7996-112">Por exemplo, na guia **Geral** :</span><span class="sxs-lookup"><span data-stu-id="e7996-112">For example, on the **General** tab:</span></span>  
  
    -   <span data-ttu-id="e7996-113">**Dica de Ferramenta** Digite um texto ou uma expressão que seja avaliada como uma Dica de Ferramenta.</span><span class="sxs-lookup"><span data-stu-id="e7996-113">**Tooltip** Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="e7996-114">A Dica de Ferramenta é exibida quando o usuário pausa o ponteiro sobre o item em um relatório</span><span class="sxs-lookup"><span data-stu-id="e7996-114">The ToolTip appears when the user pauses the pointer over the item in a report</span></span>  
  
    -   <span data-ttu-id="e7996-115">**Tipo de marcação** Selecione uma opção para indicar como o texto selecionado será renderizado:</span><span class="sxs-lookup"><span data-stu-id="e7996-115">**Markup type** Select an option to indicate how the selected text will be rendered:</span></span>  
  
         <span data-ttu-id="e7996-116">**Texto Sem Formatação** Exibe o texto selecionado como texto simples.</span><span class="sxs-lookup"><span data-stu-id="e7996-116">**Plain Text** Display the selected text as simple text.</span></span> <span data-ttu-id="e7996-117">O HTML será tratado como texto literal.</span><span class="sxs-lookup"><span data-stu-id="e7996-117">HTML will be treated as literal text.</span></span>  
  
         <span data-ttu-id="e7996-118">**HTML**  Exibe o texto selecionado como HTML.</span><span class="sxs-lookup"><span data-stu-id="e7996-118">**HTML**  Display the selected text as HTML.</span></span> <span data-ttu-id="e7996-119">Se o valor da expressão do espaço reservado contiver marcas HTML válidas, elas serão renderizadas como HTML.</span><span class="sxs-lookup"><span data-stu-id="e7996-119">If the expression value of the placeholder contains valid HTML tags, these tags will be rendered as HTML.</span></span> <span data-ttu-id="e7996-120">Para obter mais informações, consulte [Importando HTML para um relatório &#40;Construtor de Relatórios e SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e7996-120">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="e7996-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7996-121">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="e7996-122">Repita as etapas de 2 a 5 para cada texto restante que desejar formatar.</span><span class="sxs-lookup"><span data-stu-id="e7996-122">Repeat steps 2 through 5 for the remaining text you want to format.</span></span>  
  
### <a name="to-format-text-and-placeholders-differently-in-the-same-text-box"></a><span data-ttu-id="e7996-123">Para formatar o texto e os espaços reservados diferentemente na mesma caixa de texto</span><span class="sxs-lookup"><span data-stu-id="e7996-123">To format text and placeholders differently in the same text box</span></span>  
  
1.  <span data-ttu-id="e7996-124">Na guia **Inserir** , clique em **Lista**.</span><span class="sxs-lookup"><span data-stu-id="e7996-124">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="e7996-125">Clique na superfície de design e arraste-a para criar uma caixa com o tamanho desejado.</span><span class="sxs-lookup"><span data-stu-id="e7996-125">Click the design surface, and then drag to create a box that is the size you want.</span></span> <span data-ttu-id="e7996-126">A caixa de diálogo **Propriedades do Conjunto de Dados** é aberta.</span><span class="sxs-lookup"><span data-stu-id="e7996-126">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="e7996-127">Você pode usar um conjunto de dados compartilhado ou um conjunto de dados inserido em seu relatório.</span><span class="sxs-lookup"><span data-stu-id="e7996-127">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="e7996-128">Para obter mais informações, clique em [Caixa de diálogo Propriedades do Conjunto de Dados, Consulta &#40;Construtor de Relatórios&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) ou [Caixa de diálogo Propriedades do Conjunto de Dados, Consulta](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="e7996-128">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="e7996-129">Na guia **Inserir** , clique em **Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="e7996-129">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="e7996-130">Clique na lista e arraste-a para criar uma caixa com o tamanho desejado.</span><span class="sxs-lookup"><span data-stu-id="e7996-130">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="e7996-131">Digite um rótulo na caixa de texto – por exemplo, **Meu Campo**:.</span><span class="sxs-lookup"><span data-stu-id="e7996-131">Type a label in the text box - for example, **My Field**:.</span></span>  
  
4.  <span data-ttu-id="e7996-132">Arraste um campo do conjunto de dados para a caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="e7996-132">Drag a field from your dataset into the text box.</span></span> <span data-ttu-id="e7996-133">Será criado um espaço reservado para seu campo.</span><span class="sxs-lookup"><span data-stu-id="e7996-133">A placeholder is created for your field.</span></span>  
  
5.  <span data-ttu-id="e7996-134">Para formatação básica, selecione o texto do espaço reservado e clique em um das opções de formatação no grupo **Fonte** na guia **Página Inicial** . Por exemplo, clique no botão **Negrito**.</span><span class="sxs-lookup"><span data-stu-id="e7996-134">For basic formatting, select the placeholder text and then click one of the formatting options in the **Font** group on the **Home** tab. For example, click the **Bold** button.</span></span>  
  
     <span data-ttu-id="e7996-135">Para obter mais opções de formatação, clique com o botão direito do mouse no texto do espaço reservado e clique em **Propriedades do Espaço Reservado**.</span><span class="sxs-lookup"><span data-stu-id="e7996-135">For more formatting options, right-click the placeholder text, and then click **Placeholder Properties**.</span></span>  
  
6.  <span data-ttu-id="e7996-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7996-136">Click **OK**.</span></span> <span data-ttu-id="e7996-137">No modo de exibição de Design de relatório, a caixa de texto deverá conter "**Meu Campo**: [*FieldName*]", em que *FieldName* é o nome do seu campo.</span><span class="sxs-lookup"><span data-stu-id="e7996-137">In report design view, the text box should contain "**My Field**: [*FieldName*]", where *FieldName* is the name of your field.</span></span>  
  
7.  <span data-ttu-id="e7996-138">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e7996-138">Click **Run**.</span></span>  
  
 <span data-ttu-id="e7996-139">A lista é repetida uma vez para cada valor no campo e o espaço reservado *FieldName* é substituído sempre pelo valor daquele campo no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="e7996-139">The list repeats one time for every value in the field, and the *FieldName* placeholder is replaced each time by the value of that field in the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7996-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7996-140">See Also</span></span>  
 <span data-ttu-id="e7996-141">[Caixas de texto &#40;Construtor de Relatórios e SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7996-141">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e7996-142">[Formatando texto e espaços reservados &#40;Construtor de Relatórios e SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7996-142">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e7996-143">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7996-143">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e7996-144">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7996-144">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e7996-145">[Adicionar um HTML a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7996-145">[Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e7996-146">[Lista &#40;Construtor de Relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7996-146">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e7996-147">[Formatando números e datas &#40;Construtor de Relatórios e SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e7996-147">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e7996-148">Caixa de diálogo Propriedades do Espaço Reservado, Geral &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e7996-148">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
