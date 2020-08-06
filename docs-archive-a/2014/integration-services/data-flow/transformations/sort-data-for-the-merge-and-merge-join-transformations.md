---
title: Classificar dados para as transformações Mesclagem e Junção de Mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- sort attributes [Integration Services]
- output columns [Integration Services]
ms.assetid: 22ce3f5d-8a88-4423-92c2-60a8f82cd4fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bb4e91ad84c6baa52e1d7fb4b0104d835b7e4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678865"
---
# <a name="sort-data-for-the-merge-and-merge-join-transformations"></a><span data-ttu-id="548a3-102">Classificar dados para as transformações Mesclagem e Junção de Mesclagem</span><span class="sxs-lookup"><span data-stu-id="548a3-102">Sort Data for the Merge and Merge Join Transformations</span></span>
  <span data-ttu-id="548a3-103">No [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], as transformações Mesclagem e Junção de Mesclagem exigem dados classificados para suas entradas.</span><span class="sxs-lookup"><span data-stu-id="548a3-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the Merge and Merge Join transformations require sorted data for their inputs.</span></span> <span data-ttu-id="548a3-104">Os dados de entrada devem ser classificados fisicamente e as opções de classificação devem ser definidas nas saídas e nas colunas de saída na origem ou na transformação upstream.</span><span class="sxs-lookup"><span data-stu-id="548a3-104">The input data must be sorted physically, and sort options must be set on the outputs and the output columns in the source or in the upstream transformation.</span></span> <span data-ttu-id="548a3-105">Se as opções de classificação indicarem que os dados estão classificados, mas os dados não estiverem efetivamente classificados, os resultados da operação de mesclagem ou junção de mesclagem são imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="548a3-105">If the sort options indicate that the data is sorted, but the data is not actually sorted, the results of the merge or merge join operation are unpredictable.</span></span>  
  
## <a name="sorting-the-data"></a><span data-ttu-id="548a3-106">Classificando os dados</span><span class="sxs-lookup"><span data-stu-id="548a3-106">Sorting the Data</span></span>  
 <span data-ttu-id="548a3-107">Você pode classificar os dados usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="548a3-107">You can sort this data by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="548a3-108">Na origem, use uma cláusula de ORDER BY na instrução utilizada para carregar os dados.</span><span class="sxs-lookup"><span data-stu-id="548a3-108">In the source, use an ORDER BY clause in the statement that is used to load the data.</span></span>  
  
-   <span data-ttu-id="548a3-109">No fluxo de dados, insira uma transformação Classificação antes da transformação Mesclagem ou Junção de Mesclagem.</span><span class="sxs-lookup"><span data-stu-id="548a3-109">In the data flow, insert a Sort transformation before the Merge or Merge Join transformation.</span></span>  
  
 <span data-ttu-id="548a3-110">Se os dados forem dados de cadeia de caracteres, as transformações Mesclagem e Junção de Mesclagem esperarão que os valores da cadeia de caracteres tenham sido classificados com o uso da ordenação do Windows.</span><span class="sxs-lookup"><span data-stu-id="548a3-110">If the data is string data, both the Merge and Merge Join transformations expect the string values to have been sorted by using Windows collation.</span></span> <span data-ttu-id="548a3-111">Para fornecer valores de cadeia de caracteres às transformações Mesclagem e Junção de Mesclagem classificadas com o uso da ordenação do Windows, use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="548a3-111">To provide string values to the Merge and Merge Join transformations that are sorted by using Windows collation, use the following procedure.</span></span>  
  
#### <a name="to-provide-string-values-that-are-sorted-by-using-windows-collation"></a><span data-ttu-id="548a3-112">Para fornecer valores da cadeia de caracteres que são classificados usando ordenação do Windows</span><span class="sxs-lookup"><span data-stu-id="548a3-112">To provide string values that are sorted by using Windows collation</span></span>  
  
-   <span data-ttu-id="548a3-113">Use uma transformação Classificação para classificar os dados.</span><span class="sxs-lookup"><span data-stu-id="548a3-113">Use a Sort transformation to sort the data.</span></span>  
  
     <span data-ttu-id="548a3-114">A transformação Classificação usa a ordenação do Windows para classificar valores de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="548a3-114">The Sort transformation uses Windows collation to sort string values.</span></span>  
  
     <span data-ttu-id="548a3-115">-ou-</span><span class="sxs-lookup"><span data-stu-id="548a3-115">-or-</span></span>  
  
-   <span data-ttu-id="548a3-116">Primeiro use o operador CAST Transact-SQL para converter os valores `varchar` em valores `nvarchar` e, em seguida, use a cláusula ORDER BY Transact-SQL para classificar os dados.</span><span class="sxs-lookup"><span data-stu-id="548a3-116">Use the Transact-SQL CAST operator to first cast `varchar` values to `nvarchar` values, and then use the Transact-SQL ORDER BY clause to sort the data.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="548a3-117">Não é possível usar a cláusula ORDER BY sozinha porque ela utiliza uma ordenação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para classificar valores de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="548a3-117">You cannot use the ORDER BY clause alone because the ORDER BY clause uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation to sort string values.</span></span> <span data-ttu-id="548a3-118">O uso da ordenação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pode resultar em uma ordem de classificação diferente da ordenação do Windows, o que pode fazer com que a transformação Mesclar ou Junção de Mesclagem produza resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="548a3-118">The use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation might result in a different sort order than Windows collation, which can cause the Merge or Merge Join transformation to produce unexpected results.</span></span>  
  
## <a name="setting-sort-options-on-the-data"></a><span data-ttu-id="548a3-119">Definindo opções de classificação nos dados</span><span class="sxs-lookup"><span data-stu-id="548a3-119">Setting Sort Options on the Data</span></span>  
 <span data-ttu-id="548a3-120">Há duas propriedades de classificação importantes que devem ser definidas para a transformação de origem ou upstream que fornece dados às transformações Mesclar e Junção de Mesclagem:</span><span class="sxs-lookup"><span data-stu-id="548a3-120">There are two important sort properties that must be set for the source or upstream transformation that supplies data to the Merge and Merge Join transformations:</span></span>  
  
-   <span data-ttu-id="548a3-121">A propriedade `IsSorted` da saída que indica se os dados foram classificados.</span><span class="sxs-lookup"><span data-stu-id="548a3-121">The `IsSorted` property of the output that indicates whether the data has been sorted.</span></span> <span data-ttu-id="548a3-122">Essa propriedade deve ser definida como `True`.</span><span class="sxs-lookup"><span data-stu-id="548a3-122">This property must be set to `True`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="548a3-123">Definir o valor da propriedade `IsSorted` como `True` não classifica os dados.</span><span class="sxs-lookup"><span data-stu-id="548a3-123">Setting the value of the `IsSorted` property to `True` does not sort the data.</span></span> <span data-ttu-id="548a3-124">Esta propriedade apenas fornece uma dica aos componentes downstream de que os dados foram classificados previamente.</span><span class="sxs-lookup"><span data-stu-id="548a3-124">This property only provides a hint to downstream components that the data has been previously sorted.</span></span>  
  
-   <span data-ttu-id="548a3-125">A propriedade `SortKeyPosition` das colunas de saída que indica se uma coluna está classificada, a ordem de classificação da coluna e a sequência na qual várias colunas são classificadas.</span><span class="sxs-lookup"><span data-stu-id="548a3-125">The `SortKeyPosition` property of output columns that indicates whether a column is sorted, the column's sort order, and the sequence in which multiple columns are sorted.</span></span> <span data-ttu-id="548a3-126">Esta propriedade deve ser definida para cada coluna de dados classificados.</span><span class="sxs-lookup"><span data-stu-id="548a3-126">This property must be set for each column of sorted data.</span></span>  
  
 <span data-ttu-id="548a3-127">Se você usar a transformação Classificação para classificar os dados, essa transformação define ambas as propriedades como necessárias para a transformação Mesclar ou Junção de Mesclagem.</span><span class="sxs-lookup"><span data-stu-id="548a3-127">If you use a Sort transformation to sort the data, the Sort transformation sets both of these properties as required by the Merge or Merge Join transformation.</span></span> <span data-ttu-id="548a3-128">Ou seja, a transformação Classificação define a propriedade `IsSorted` de sua saída para `True` e as propriedades `SortKeyPosition` de suas colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="548a3-128">That is, the Sort transformation sets the `IsSorted` property of its output to `True`, and sets the `SortKeyPosition` properties of its output columns.</span></span>  
  
 <span data-ttu-id="548a3-129">No entanto, se você não usar uma transformação Classificação para classificar os dados, defina essas propriedades de classificação manualmente na transformação de origem ou upstream.</span><span class="sxs-lookup"><span data-stu-id="548a3-129">However, if you do not use a Sort transformation to sort the data, you must set these sort properties manually on the source or the upstream transformation.</span></span> <span data-ttu-id="548a3-130">Para definir as propriedades de classificação manualmente na transformação de origem ou upstream, siga o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="548a3-130">To manually set the sort properties on the source or upstream transformation, use the following procedure.</span></span>  
  
#### <a name="to-manually-set-sort-attributes-on-a-source-or-transformation-component"></a><span data-ttu-id="548a3-131">Para definir atributos de classificação manualmente em um componente de origem ou transformação</span><span class="sxs-lookup"><span data-stu-id="548a3-131">To manually set sort attributes on a source or transformation component</span></span>  
  
1.  <span data-ttu-id="548a3-132">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="548a3-132">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="548a3-133">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="548a3-133">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="548a3-134">Na guia **Fluxo de Dados** , localize a transformação apropriada de origem ou upstream ou arraste-a da **Caixa de Ferramentas** para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="548a3-134">On the **Data Flow** tab, locate the appropriate source or upstream transformation, or drag it from the **Toolbox** to the design surface.</span></span>  
  
4.  <span data-ttu-id="548a3-135">Clique com o botão direito do mouse no componente e clique em **Mostrar Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="548a3-135">Right-click the component and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="548a3-136">Clique na guia **Propriedades de Entrada e Saída** .</span><span class="sxs-lookup"><span data-stu-id="548a3-136">Click the **Input and Output Properties** tab.</span></span>  
  
6.  <span data-ttu-id="548a3-137">Clique em \*\* \<component name> saída\*\*e defina a `IsSorted` propriedade como `True` .</span><span class="sxs-lookup"><span data-stu-id="548a3-137">Click **\<component name> Output**, and set the `IsSorted` property to `True`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="548a3-138">Se você definir manualmente a propriedade `IsSorted` da saída como `True` e os dados não forem classificados, ausências de dados ou comparações de dados inválidas poderão ocorrer na transformação Mesclagem ou Junção de Mesclagem de downstream durante a execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="548a3-138">If you manually set the `IsSorted` property of the output to `True` and the data is not sorted, there might be missing data or bad data comparisons in the downstream Merge or Merge Join transformation when you run the package.</span></span>  
  
7.  <span data-ttu-id="548a3-139">Expanda **Colunas de Saída**.</span><span class="sxs-lookup"><span data-stu-id="548a3-139">Expand **Output Columns**.</span></span>  
  
8.  <span data-ttu-id="548a3-140">Clique na coluna que você deseja indicar que está classificada e defina sua propriedade `SortKeyPosition` como um valor inteiro diferente de zero, de acordo com estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="548a3-140">Click the column that you want to indicate is sorted and set its `SortKeyPosition` property to a nonzero integer value by following these guidelines:</span></span>  
  
    -   <span data-ttu-id="548a3-141">O valor do número inteiro deve representar uma sequência numérica, começando com 1 e incrementado em 1.</span><span class="sxs-lookup"><span data-stu-id="548a3-141">The integer value must represent a numeric sequence, starting with 1 and incremented by 1.</span></span>  
  
    -   <span data-ttu-id="548a3-142">Um valor inteiro positivo indica uma ordem de classificação crescente.</span><span class="sxs-lookup"><span data-stu-id="548a3-142">A positive integer value indicates an ascending sort order.</span></span>  
  
    -   <span data-ttu-id="548a3-143">Um valor inteiro negativo indica uma ordem de classificação decrescente.</span><span class="sxs-lookup"><span data-stu-id="548a3-143">A negative integer value indicates a descending sort order.</span></span> <span data-ttu-id="548a3-144">(Se definido com um número negativo, o valor absoluto do número determinará a posição da coluna na sequência de classificação.)</span><span class="sxs-lookup"><span data-stu-id="548a3-144">(If set to a negative number, the absolute value of the number determines the column's position in the sort sequence.)</span></span>  
  
    -   <span data-ttu-id="548a3-145">O valor padrão de 0 indica que a coluna não está classificada.</span><span class="sxs-lookup"><span data-stu-id="548a3-145">The default value of 0 indicates that the column is not sorted.</span></span> <span data-ttu-id="548a3-146">Deixe o valor de 0 para colunas de saída que não participam da classificação.</span><span class="sxs-lookup"><span data-stu-id="548a3-146">Leave the value of 0 for output columns that do not participate in the sort.</span></span>  
  
     <span data-ttu-id="548a3-147">Como exemplo de como definir a propriedade `SortKeyPosition`, considere a seguinte instrução Transact-SQL que carrega os dados em uma origem:</span><span class="sxs-lookup"><span data-stu-id="548a3-147">As an example of how to set the `SortKeyPosition` property, consider the following Transact-SQL statement that loads data in a source:</span></span>  
  
     `SELECT * FROM MyTable ORDER BY ColumnA, ColumnB DESC, ColumnC`  
  
     <span data-ttu-id="548a3-148">Para esta instrução, você definirá a propriedade `SortKeyPosition` de cada coluna da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="548a3-148">For this statement, you would set the `SortKeyPosition` property for each column as follows:</span></span>  
  
    -   <span data-ttu-id="548a3-149">Defina a propriedade `SortKeyPosition` da Coluna A como 1.</span><span class="sxs-lookup"><span data-stu-id="548a3-149">Set the `SortKeyPosition` property of ColumnA to 1.</span></span> <span data-ttu-id="548a3-150">Isso indica que a Coluna A é a primeira a ser classificada e é classificada em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="548a3-150">This indicates that ColumnA is the first column to be sorted and is sorted in ascending order.</span></span>  
  
    -   <span data-ttu-id="548a3-151">Defina a propriedade `SortKeyPosition` da Coluna B como -2.</span><span class="sxs-lookup"><span data-stu-id="548a3-151">Set the `SortKeyPosition` property of ColumnB to -2.</span></span> <span data-ttu-id="548a3-152">Isso indica que a Coluna B é a segunda a ser classificada e é classificada em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="548a3-152">This indicates that ColumnB is the second column to be sorted and is sorted in descending order</span></span>  
  
    -   <span data-ttu-id="548a3-153">Defina a propriedade `SortKeyPosition` da Coluna C como 3.</span><span class="sxs-lookup"><span data-stu-id="548a3-153">Set the `SortKeyPosition` property of ColumnC to 3.</span></span> <span data-ttu-id="548a3-154">Isso indica que a Coluna C é a terceira a ser classificada e é classificada em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="548a3-154">This indicates that ColumnC is the third column to be sorted and is sorted in ascending order.</span></span>  
  
9. <span data-ttu-id="548a3-155">Repita a etapa 8 para cada coluna classificada.</span><span class="sxs-lookup"><span data-stu-id="548a3-155">Repeat step 8 for each sorted column.</span></span>  
  
10. <span data-ttu-id="548a3-156">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="548a3-156">Click **OK**.</span></span>  
  
11. <span data-ttu-id="548a3-157">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="548a3-157">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548a3-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="548a3-158">See Also</span></span>  
 <span data-ttu-id="548a3-159">[Transformação Mesclar](merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="548a3-159">[Merge Transformation](merge-transformation.md) </span></span>  
 <span data-ttu-id="548a3-160">[Transformação Junção de Mesclagem](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="548a3-160">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="548a3-161">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="548a3-161">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="548a3-162">[Caminhos do Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="548a3-162">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="548a3-163">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="548a3-163">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
