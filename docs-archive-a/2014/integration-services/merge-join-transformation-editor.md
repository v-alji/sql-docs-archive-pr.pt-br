---
title: Editor de transformação junção de mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergejointransformation.f1
helpviewer_keywords:
- Merge Join Transformation Editor
ms.assetid: ac06f419-30b3-42aa-8b34-42000bec4285
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0d15d1233c2e0ff836e9dbd17459e56c48183f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575208"
---
# <a name="merge-join-transformation-editor"></a><span data-ttu-id="367f2-102">Editor de Transformação Mesclagem</span><span class="sxs-lookup"><span data-stu-id="367f2-102">Merge Join Transformation Editor</span></span>
  <span data-ttu-id="367f2-103">Use a caixa de diálogo **Editor de Transformação Mesclar Junção** para especificar o tipo de junção, as colunas de junção e as colunas de saída para mesclar duas entradas combinadas por uma junção.</span><span class="sxs-lookup"><span data-stu-id="367f2-103">Use the **Merge Join Transformation Editor** dialog box to specify the join type, the join columns, and the output columns for merging two inputs combined by a join.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="367f2-104">A Transformação Junção de Mesclagem requer dados classificados para suas entradas.</span><span class="sxs-lookup"><span data-stu-id="367f2-104">The Merge Join Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="367f2-105">Para obter mais informações sobre este requisito importante, consulte [Classificar dados para as transformações Mesclagem e Junção de Mesclagem](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="367f2-105">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="367f2-106">Para saber mais sobre transformação Mesclagem de Junção, consulte [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="367f2-106">To learn more about the Merge Join transformation, see [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="367f2-107">Opções</span><span class="sxs-lookup"><span data-stu-id="367f2-107">Options</span></span>  
 <span data-ttu-id="367f2-108">**Tipo de junção**</span><span class="sxs-lookup"><span data-stu-id="367f2-108">**Join type**</span></span>  
 <span data-ttu-id="367f2-109">Especifique se você quer usar uma junção interna, externa esquerda ou completa.</span><span class="sxs-lookup"><span data-stu-id="367f2-109">Specify whether you want to use an inner join, left outer join, or full join.</span></span>  
  
 <span data-ttu-id="367f2-110">**Trocar Entradas**</span><span class="sxs-lookup"><span data-stu-id="367f2-110">**Swap Inputs**</span></span>  
 <span data-ttu-id="367f2-111">Troque a ordem entre entradas usando o botão **Trocar Entradas** .</span><span class="sxs-lookup"><span data-stu-id="367f2-111">Switch the order between inputs by using the **Swap Inputs** button.</span></span> <span data-ttu-id="367f2-112">Essa seleção pode ser útil com a opção de Junção externa esquerda.</span><span class="sxs-lookup"><span data-stu-id="367f2-112">This selection may be useful with the Left outer join option.</span></span>  
  
 <span data-ttu-id="367f2-113">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="367f2-113">**Input**</span></span>  
 <span data-ttu-id="367f2-114">Para cada coluna que você desejar na saída mesclada, selecione primeiro na lista de entradas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="367f2-114">For each column that you want in the merged output, first select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="367f2-115">São exibidas entradas em duas tabelas separadas.</span><span class="sxs-lookup"><span data-stu-id="367f2-115">Inputs are displayed in two separate tables.</span></span> <span data-ttu-id="367f2-116">Selecione colunas a serem incluídas na saída.</span><span class="sxs-lookup"><span data-stu-id="367f2-116">Select columns to include in the output.</span></span> <span data-ttu-id="367f2-117">Arraste colunas para criar uma junção entre as tabelas.</span><span class="sxs-lookup"><span data-stu-id="367f2-117">Drag columns to create a join between the tables.</span></span> <span data-ttu-id="367f2-118">Para excluir uma junção, selecione-a e pressione a tecla DELETE.</span><span class="sxs-lookup"><span data-stu-id="367f2-118">To delete a join, select it and then press the DELETE key.</span></span>  
  
 <span data-ttu-id="367f2-119">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="367f2-119">**Input Column**</span></span>  
 <span data-ttu-id="367f2-120">Selecione uma coluna a incluir na saída mesclada da lista de colunas disponíveis na entrada selecionada.</span><span class="sxs-lookup"><span data-stu-id="367f2-120">Select a column to include in the merged output from the list of available columns on the selected input.</span></span>  
  
 <span data-ttu-id="367f2-121">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="367f2-121">**Output Alias**</span></span>  
 <span data-ttu-id="367f2-122">Digite um alias para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="367f2-122">Type an alias for each output column.</span></span> <span data-ttu-id="367f2-123">O padrão é o nome da coluna de entrada; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="367f2-123">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367f2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="367f2-124">See Also</span></span>  
 <span data-ttu-id="367f2-125">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="367f2-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="367f2-126">[Classificar dados para as transformações mesclagem e junção de mesclagem](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="367f2-126">[Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span></span>  
 <span data-ttu-id="367f2-127">[Estender um conjunto de um DataSet usando a transformação junção de mesclagem](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="367f2-127">[Extend a Dataset by Using the Merge Join Transformation](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span></span>  
 <span data-ttu-id="367f2-128">[Transformação Mesclar](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="367f2-128">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="367f2-129">Transformação Unir Tudo</span><span class="sxs-lookup"><span data-stu-id="367f2-129">Union All Transformation</span></span>](data-flow/transformations/union-all-transformation.md)  
  
  
