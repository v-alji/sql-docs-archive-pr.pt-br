---
title: Criar um grupo de hierarquias recursivas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8b830ba5-4d64-4348-a2b1-76b9338a1462
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf86c3989170ed8cd452168a558ead348258331e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572435"
---
# <a name="create-a-recursive-hierarchy-group-report-builder-and-ssrs"></a><span data-ttu-id="91cfb-102">Criar um grupo de hierarquia recursiva (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="91cfb-102">Create a Recursive Hierarchy Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="91cfb-103">Um grupo de hierarquia recursiva organiza dados de um único conjunto de dados de relatório que contém vários níveis hierárquicos, como a estrutura de subordinação para relações gerente-funcionários em uma hierarquia organizacional.</span><span class="sxs-lookup"><span data-stu-id="91cfb-103">A recursive hierarchy group organizes data from a single report dataset that includes multiple hierarchical levels, such as the report-to structure for manager-employee relationships in an organizational hierarchy.</span></span>  
  
 <span data-ttu-id="91cfb-104">Antes de poder organizar os dados em uma tabela como um grupo de hierarquia recursiva, é preciso que haja um único conjunto de dados contendo todos os dados hierárquicos, campos separados para o item a ser agrupado e para o item pelo qual agrupar.</span><span class="sxs-lookup"><span data-stu-id="91cfb-104">Before you can organize data in a table as a recursive hierarchy group, you must have a single dataset that contains all the hierarchical data, You must have separate fields for the item to group and for the item to group by.</span></span> <span data-ttu-id="91cfb-105">Por exemplo, um conjunto de dados no qual você deseja agrupar os funcionários recursivamente sob o gerente pode conter um nome, um nome de funcionário, uma ID de funcionário e uma ID de gerente.</span><span class="sxs-lookup"><span data-stu-id="91cfb-105">For example, a dataset where you want to group employees recursively under their manager might contain a name, an employee name, an employee ID, and a manager ID.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-recursive-hierarchy-group"></a><span data-ttu-id="91cfb-106">Para criar um grupo de hierarquia recursiva</span><span class="sxs-lookup"><span data-stu-id="91cfb-106">To create a recursive hierarchy group</span></span>  
  
1.  <span data-ttu-id="91cfb-107">Na exibição de Design, adicione uma tabela e arraste os campos do conjunto de dados que serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="91cfb-107">In Design view, add a table, and drag the dataset fields to display.</span></span> <span data-ttu-id="91cfb-108">Normalmente, o campo que você deseja mostrar como uma hierarquia está na primeira coluna.</span><span class="sxs-lookup"><span data-stu-id="91cfb-108">Typically, the field that you want to show as a hierarchy is in the first column.</span></span>  
  
2.  <span data-ttu-id="91cfb-109">Clique com o botão direito do mouse em qualquer lugar da tabela para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="91cfb-109">Right-click anywhere in the table to select it.</span></span> <span data-ttu-id="91cfb-110">O painel Agrupamento exibe o grupo de detalhes da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="91cfb-110">The Grouping pane displays the details group for the selected table.</span></span> <span data-ttu-id="91cfb-111">No painel Grupos de Linhas, clique com o botão direito do mouse no grupo **Detalhes**e clique em **Editar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="91cfb-111">In the Row Groups pane, right-click **Details**, and then click **Edit Group**.</span></span> <span data-ttu-id="91cfb-112">A caixa de diálogo **Propriedades do Grupo** é aberta.</span><span class="sxs-lookup"><span data-stu-id="91cfb-112">The **Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="91cfb-113">Em **Expressões de grupo**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="91cfb-113">In **Group expressions**, click **Add**.</span></span> <span data-ttu-id="91cfb-114">Uma nova linha aparece na grade.</span><span class="sxs-lookup"><span data-stu-id="91cfb-114">A new row appears in the grid.</span></span>  
  
4.  <span data-ttu-id="91cfb-115">Na lista **Agrupar em** , digite ou selecione o campo a ser agrupado.</span><span class="sxs-lookup"><span data-stu-id="91cfb-115">In the **Group on** list, type or select the field to group.</span></span>  
  
5.  <span data-ttu-id="91cfb-116">Clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="91cfb-116">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="91cfb-117">Na lista **Pai Recursivo** , insira ou selecione o campo pelo qual agrupar.</span><span class="sxs-lookup"><span data-stu-id="91cfb-117">In the **Recursive Parent** list, enter or select the field to group on.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="91cfb-118">Execute o relatório.</span><span class="sxs-lookup"><span data-stu-id="91cfb-118">Run the report.</span></span> <span data-ttu-id="91cfb-119">O relatório exibe o grupo de hierarquia recursiva, embora não haja recuo para mostrar a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="91cfb-119">The report displays the recursive hierarchy group, although there is no indent to show the hierarchy</span></span>  
  
### <a name="to-format-a-recursive-hierarchy-group-with-indent-levels"></a><span data-ttu-id="91cfb-120">Para formatar um grupo de hierarquia recursiva com níveis de recuo</span><span class="sxs-lookup"><span data-stu-id="91cfb-120">To format a recursive hierarchy group with indent levels</span></span>  
  
1.  <span data-ttu-id="91cfb-121">Clique na caixa de texto que contém o campo ao qual você deseja adicionar níveis de recuo para exibir um formato de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="91cfb-121">Click the text box that contains the field to which you want to add indent levels to display a hierarchy format.</span></span> <span data-ttu-id="91cfb-122">As propriedades da caixa de texto aparecem no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="91cfb-122">The properties for the text box appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91cfb-123">Se o painel Propriedades não for exibido, clique em **Propriedades** na guia **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="91cfb-123">If you do not see the Properties pane, click **Properties** on the **View** tab.</span></span>  
  
2.  <span data-ttu-id="91cfb-124">No painel Propriedades, expanda o `Padding` nó, clique em **esquerda**e, na lista suspensa, selecione **\<Expression...>** .</span><span class="sxs-lookup"><span data-stu-id="91cfb-124">In the Properties pane, expand the `Padding` node, click **Left**, and from the drop-down list, select **\<Expression...>**.</span></span>  
  
3.  <span data-ttu-id="91cfb-125">No painel Expressão, digite a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="91cfb-125">In the Expression pane, type the following expression:</span></span>  
  
     `=CStr(2 + (Level()*10)) + "pt"`  
  
     <span data-ttu-id="91cfb-126">Todas as propriedades de Preenchimento requerem uma cadeia de caracteres no formato *nnyy*, sendo que *nn* é um número e *yy* é a unidade de medida.</span><span class="sxs-lookup"><span data-stu-id="91cfb-126">The Padding properties all require a string in the format *nnyy*, where *nn* is a number and *yy* is the unit of measure.</span></span> <span data-ttu-id="91cfb-127">O exemplo de expressão cria uma cadeia de caracteres que usa a função `Level` para aumentar o tamanho do preenchimento com base no nível de recursão.</span><span class="sxs-lookup"><span data-stu-id="91cfb-127">The example expression builds a string that uses the `Level` function to increase the size of the padding based on recursion level.</span></span> <span data-ttu-id="91cfb-128">Por exemplo, uma linha com um nível de 1 resultaria em um preenchimento de (2 + (1\*10))=12 pt, e uma linha com um nível de 3 resultaria em um preenchimento de (2 + (3\*10))=32 pt.</span><span class="sxs-lookup"><span data-stu-id="91cfb-128">For example, a row that has a level of 1 would result in a padding of (2 + (1\*10))=12pt, and a row that has a level of 3 would result in a padding of (2 + (3\*10))=32pt.</span></span> <span data-ttu-id="91cfb-129">Para obter informações sobre a `Level` função, consulte [Level](report-builder-functions-level-function.md).</span><span class="sxs-lookup"><span data-stu-id="91cfb-129">For information about the `Level` function, see [Level](report-builder-functions-level-function.md).</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="91cfb-130">Execute o relatório.</span><span class="sxs-lookup"><span data-stu-id="91cfb-130">Run the report.</span></span> <span data-ttu-id="91cfb-131">O relatório exibe uma exibição hierárquica dos dados agrupados.</span><span class="sxs-lookup"><span data-stu-id="91cfb-131">The report displays a hierarchical view of the grouped data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91cfb-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91cfb-132">See Also</span></span>  
 <span data-ttu-id="91cfb-133">[Criar grupos de hierarquia recursiva &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91cfb-133">[Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91cfb-134">[Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91cfb-134">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91cfb-135">[Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span><span class="sxs-lookup"><span data-stu-id="91cfb-135">[Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span></span>  
 <span data-ttu-id="91cfb-136">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91cfb-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91cfb-137">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91cfb-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="91cfb-138">[Listas &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="91cfb-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="91cfb-139">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="91cfb-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
