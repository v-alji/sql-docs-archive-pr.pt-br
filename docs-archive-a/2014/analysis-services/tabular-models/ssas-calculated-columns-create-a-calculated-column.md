---
title: Criar uma coluna calculada (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.as.daxref.CreataCalculatedColumn.f1
ms.assetid: 59440510-2d76-41dc-9b55-edc15259f9da
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdb56ffb2b42aa8225b7eff76b11315ea511fd81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678293"
---
# <a name="create-a-calculated-column-ssas-tabular"></a><span data-ttu-id="94911-102">Criar uma coluna calculada (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="94911-102">Create a Calculated Column (SSAS Tabular)</span></span>
  <span data-ttu-id="94911-103">Colunas calculadas permitem adicionar novos dados a seu modelo.</span><span class="sxs-lookup"><span data-stu-id="94911-103">Calculated columns allow you to add new data to your model.</span></span> <span data-ttu-id="94911-104">Em vez de colar ou importar valores para a coluna, você cria uma fórmula DAX que define os valores de nível de linha da coluna.</span><span class="sxs-lookup"><span data-stu-id="94911-104">Instead of pasting or importing values into the column, you create a DAX formula that defines the column's row level values.</span></span> <span data-ttu-id="94911-105">Os valores em cada linha de uma coluna calculada são calculados e preenchidos quando você cria uma fórmula válida e, em seguida, clica em ENTER.</span><span class="sxs-lookup"><span data-stu-id="94911-105">The values in each row of a calculated column are calculated and populated when you create a valid formula and then click ENTER.</span></span> <span data-ttu-id="94911-106">A coluna calculada pode ser então adicionada a um relatório ou aplicativo de análise da mesma maneira que qualquer outra coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="94911-106">The calculated column can then be added to a reporting or analysis application just as would any other column of data.</span></span> <span data-ttu-id="94911-107">Este tópico descreve como criar uma nova coluna calculada usando a barra de fórmulas DAX no designer modelo.</span><span class="sxs-lookup"><span data-stu-id="94911-107">This topic describes how to create a new calculated column by using the DAX formula bar in the model designer.</span></span>  
  
#### <a name="to-create-a-new-calculated-column"></a><span data-ttu-id="94911-108">Para criar uma nova coluna calculada</span><span class="sxs-lookup"><span data-stu-id="94911-108">To create a new calculated column</span></span>  
  
1.  <span data-ttu-id="94911-109">No designer de modelo, na Exibição de Dados, selecione a tabela à qual você quer adicionar uma coluna calculada, clique no menu **Coluna** e clique em **Adicionar Coluna**.</span><span class="sxs-lookup"><span data-stu-id="94911-109">In the model designer, in Data View, select the table to which you want to add a calculated column, then click the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="94911-110">**Adicionar Coluna** é realçado na coluna vazia mais à direita, e o cursor se move para a barra de fórmulas.</span><span class="sxs-lookup"><span data-stu-id="94911-110">**Add Column** is highlighted over the empty rightmost column, and the cursor moves to the formula bar.</span></span>  
  
     <span data-ttu-id="94911-111">Para criar uma nova coluna entre duas colunas existentes, clique com o botão direito do mouse em uma coluna existente e clique em **Inserir Coluna**.</span><span class="sxs-lookup"><span data-stu-id="94911-111">To create a new column between two existing columns, right-click an existing column, and then click **Insert Column**.</span></span>  
  
2.  <span data-ttu-id="94911-112">Na barra de fórmulas, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="94911-112">In the formula bar, do one of the following:</span></span>  
  
    -   <span data-ttu-id="94911-113">Digite um sinal de igual seguido por uma fórmula.</span><span class="sxs-lookup"><span data-stu-id="94911-113">Type an equal sign followed by a formula.</span></span>  
  
    -   <span data-ttu-id="94911-114">Digite um sinal de igual, seguido por uma função DAX, seguida por argumentos e parâmetros, conforme exigido pela função.</span><span class="sxs-lookup"><span data-stu-id="94911-114">Type an equal sign, followed by a DAX function, followed by arguments and parameters as required by the function.</span></span>  
  
    -   <span data-ttu-id="94911-115">Clique no botão de função (**fx**) e, na caixa de diálogo **Inserir Função** , selecione uma categoria e uma função, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="94911-115">Click the function button (**fx**), then in the **Insert Function** dialog box, select a category and function, and then click **OK**.</span></span> <span data-ttu-id="94911-116">Na barra de fórmulas, digite os argumentos e os parâmetros restantes conforme exigido pela função.</span><span class="sxs-lookup"><span data-stu-id="94911-116">In the formula bar, type the remaining arguments and parameters as required by the function.</span></span>  
  
3.  <span data-ttu-id="94911-117">Pressione ENTER para aceitar a fórmula.</span><span class="sxs-lookup"><span data-stu-id="94911-117">Press ENTER to accept the formula.</span></span>  
  
     <span data-ttu-id="94911-118">A coluna inteira é preenchida com a fórmula, e um valor é calculado para cada linha.</span><span class="sxs-lookup"><span data-stu-id="94911-118">The entire column is populated with the formula, and a value is calculated for each row.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="94911-119">É possível usar a opção AutoCompletar Fórmula DAX no meio de uma fórmula existente com funções aninhadas.</span><span class="sxs-lookup"><span data-stu-id="94911-119">You can use DAX Formula AutoComplete in the middle of an existing formula with nested functions.</span></span> <span data-ttu-id="94911-120">O texto pouco antes do ponto de inserção é usado para exibir valores na lista suspensa, e todo o texto depois do ponto de inserção permanece inalterado.</span><span class="sxs-lookup"><span data-stu-id="94911-120">The text immediately before the insertion point is used to display values in the drop-down list, and all of the text after the insertion point remains unchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94911-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94911-121">See Also</span></span>  
 <span data-ttu-id="94911-122">[Colunas calculadas &#40;SSAS de tabela&#41;](ssas-calculated-columns.md) </span><span class="sxs-lookup"><span data-stu-id="94911-122">[Calculated Columns &#40;SSAS Tabular&#41;](ssas-calculated-columns.md) </span></span>  
 [<span data-ttu-id="94911-123">Medidas &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="94911-123">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
