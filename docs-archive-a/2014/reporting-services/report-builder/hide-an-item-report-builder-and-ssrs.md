---
title: Ocultar um item (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.visibility.f1
- "10503"
ms.assetid: 9d78f8de-959b-456f-8947-687fa6e2ba91
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56e834204698369687528c622cf6167a492766f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571840"
---
# <a name="hide-an-item-report-builder-and-ssrs"></a><span data-ttu-id="c2049-102">Ocultar um item (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c2049-102">Hide an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c2049-103">Defina a visibilidade de um item de relatório quando quiser ocultar condicionalmente um item com base em um parâmetro de relatório ou alguma outra expressão que você especificar.</span><span class="sxs-lookup"><span data-stu-id="c2049-103">Set the visibility of a report item when you want to conditionally hide an item based on a report parameter or some other expression that you specify.</span></span>

 <span data-ttu-id="c2049-104">Você também pode desenvolver um relatório para permitir que o usuário alterne a visibilidade dos itens de relatório clicando nas caixas de texto no relatório, por exemplo, em um relatório de busca detalhada.</span><span class="sxs-lookup"><span data-stu-id="c2049-104">You can also design a report to allow the user to toggle the visibility of report items based on clicking text boxes in the report, for example, for a drilldown report.</span></span> <span data-ttu-id="c2049-105">Para obter mais informações, consulte [Adicionar uma ação de expandir/recolher a um item &#40;Construtor de Relatórios e SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c2049-105">For more information, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="c2049-106">Os procedimentos a seguir descrevem como mostrar ou ocultar um item de relatório em um relatório renderizado com base em uma constante ou expressão.</span><span class="sxs-lookup"><span data-stu-id="c2049-106">The following procedures describe how to show or hide a report item in a rendered report based on a constant or an expression.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-hide-a-report-item"></a><span data-ttu-id="c2049-107">Para ocultar um item de relatório</span><span class="sxs-lookup"><span data-stu-id="c2049-107">To hide a report item</span></span>

1.  <span data-ttu-id="c2049-108">No modo de exibição de Design do relatório, clique com o botão direito do mouse no item de relatório e abra a página **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="c2049-108">In report design view, right-click the report item and open its **Properties** page.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c2049-109">Para selecionar uma tabela ou uma região de dados tablix inteira, clique na região de dados para selecioná-la, clique com o botão direito do mouse em uma linha, coluna ou alça de canto e, em seguida, clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="c2049-109">To select an entire table or matrix data region, click in the data region to select it, right-click a row, column, or corner handle, and then click **Tablix Properties**.</span></span>

2.  <span data-ttu-id="c2049-110">Clique em **visibilidade.**</span><span class="sxs-lookup"><span data-stu-id="c2049-110">Click **Visibility.**</span></span>

3.  <span data-ttu-id="c2049-111">Em **Quando o relatório for executado inicialmente**, especifique se deseja ocultar o item quando exibir o relatório pela primeira vez:</span><span class="sxs-lookup"><span data-stu-id="c2049-111">In **When the report is initially run**, specify whether to hide the item when you first view the report:</span></span>

    -   <span data-ttu-id="c2049-112">Para exibir o item, clique em **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="c2049-112">To display the item, click **Show**.</span></span>

    -   <span data-ttu-id="c2049-113">Para ocultar o item, clique em **Ocultar**.</span><span class="sxs-lookup"><span data-stu-id="c2049-113">To hide the item, click **Hide**.</span></span>

    -   <span data-ttu-id="c2049-114">Para especificar uma expressão que seja avaliada em tempo de execução, clique em **Mostrar ou ocultar com base em uma expressão**.</span><span class="sxs-lookup"><span data-stu-id="c2049-114">To specify an expression that is evaluated at run-time, click **Show or hide based on an expression**.</span></span> <span data-ttu-id="c2049-115">Digite a expressão ou clique no botão de expressão (**fx**) para criar a expressão na caixa de diálogo **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="c2049-115">Type the expression or click the expression (**fx**) button to create the expression in the **Expression** dialog box.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="c2049-116">Quando você especifica uma expressão para visibilidade, você está configurando a propriedade Hidden do item de relatório, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="c2049-116">When you specify an expression for visibility, you are setting the Hidden property of the report item, as shown in the following image.</span></span> <span data-ttu-id="c2049-117">A expressão avaliada mostra o item de relatório quando o valor é False e oculta o item de relatório quando o valor é True.</span><span class="sxs-lookup"><span data-stu-id="c2049-117">The evaluated expression shows the report item when the value is False, and hides the report item when the value is True.</span></span> 
        > <span data-ttu-id="c2049-118">![Caixa de diálogo Properties_Visibility e propriedade oculta](../media/hiddenproperty-propertiesvisibility.png "Caixa de diálogo Properties_Visibility e propriedade oculta")</span><span class="sxs-lookup"><span data-stu-id="c2049-118">![Properties_Visibility dialog and Hidden property](../media/hiddenproperty-propertiesvisibility.png "Properties_Visibility dialog and Hidden property")</span></span>

4.  <span data-ttu-id="c2049-119">Clique em **OK** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="c2049-119">Click **OK** twice.</span></span>

### <a name="to-hide-static-rows-in-a-table-matrix-or-list"></a><span data-ttu-id="c2049-120">Para ocultar linhas estáticas em uma tabela, matriz ou lista</span><span class="sxs-lookup"><span data-stu-id="c2049-120">To hide static rows in a table, matrix, or list</span></span>

1.  <span data-ttu-id="c2049-121">Na modo Design do relatório, clique na tabela, matriz ou lista para exibir as alças de coluna e linha.</span><span class="sxs-lookup"><span data-stu-id="c2049-121">In report design view, click the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="c2049-122">Clique com o botão direito do mouse na alça da linha e clique em **Visibilidade da Linha**.</span><span class="sxs-lookup"><span data-stu-id="c2049-122">Right-click the row handle, and then click **Row Visibility**.</span></span> <span data-ttu-id="c2049-123">A caixa de diálogo **Visibilidade da Linha** é aberta.</span><span class="sxs-lookup"><span data-stu-id="c2049-123">The **Row Visibility** dialog box opens.</span></span>

3.  <span data-ttu-id="c2049-124">Para definir a visibilidade, siga as etapas 3 e 4 do primeiro procedimento.</span><span class="sxs-lookup"><span data-stu-id="c2049-124">To set the visibility, follow steps 3 and 4 in the first procedure.</span></span>

### <a name="to-hide-static-columns-in-a-table-matrix-or-list"></a><span data-ttu-id="c2049-125">Para ocultar colunas estáticas em uma tabela, matriz ou lista</span><span class="sxs-lookup"><span data-stu-id="c2049-125">To hide static columns in a table, matrix, or list</span></span>

1.  <span data-ttu-id="c2049-126">Na exibição Design, selecione a tabela, matriz ou lista para exibir as alças de coluna e linha.</span><span class="sxs-lookup"><span data-stu-id="c2049-126">In Design view, select the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="c2049-127">Clique com o botão direito do mouse na alça da coluna e clique em **Visibilidade da Coluna**.</span><span class="sxs-lookup"><span data-stu-id="c2049-127">Right-click the column handle, and then click **Column Visibility**.</span></span>

3.  <span data-ttu-id="c2049-128">Na caixa de diálogo **Visibilidade da Coluna** , siga as etapas 3 e 4 do primeiro procedimento.</span><span class="sxs-lookup"><span data-stu-id="c2049-128">In the **Column Visibility** dialog box, follow steps 3 and 4 in the first procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2049-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2049-129">See Also</span></span>
 <span data-ttu-id="c2049-130">[Ação de busca detalhada &#40;Construtor de relatórios e SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Adicionar uma ação de expandir ou recolher a um item &#40;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) exemplos de expressão Construtor de relatórios e SSRS&#41;&#40;Construtor de relatórios [e SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="c2049-130">[Drilldown Action &#40;Report Builder and SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span></span>


