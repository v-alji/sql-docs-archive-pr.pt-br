---
title: Agregar valores em um conjunto de dados por meio da transformação Agregação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Aggregate transformation [Integration Services]
- aggregate values [Integration Services]
- datasets [Integration Services], aggregate values
ms.assetid: 01b81c0f-d5e0-483b-81b2-73800a6945ac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de918c6c2adf194d5808ccd1b64c77a94a52e357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678878"
---
# <a name="aggregate-values-in-a-dataset-by-using-the-aggregate-transformation"></a><span data-ttu-id="77784-102">Agregar valores em um conjunto de dados por meio da transformação Agregação</span><span class="sxs-lookup"><span data-stu-id="77784-102">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>
  <span data-ttu-id="77784-103">Para adicionar e configurar uma transformação de Agregação, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma origem.</span><span class="sxs-lookup"><span data-stu-id="77784-103">To add and configure an Aggregate transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-aggregate-values-in-a-dataset"></a><span data-ttu-id="77784-104">Para agregar valores em um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="77784-104">To aggregate values in a dataset</span></span>  
  
1.  <span data-ttu-id="77784-105">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="77784-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="77784-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="77784-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="77784-107">Clique na guia **Fluxo de Dados** e na **Caixa de Ferramentas**, arraste a transformação Agregação para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="77784-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Aggregate transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="77784-108">Conecte a transformação Agregação ao fluxo de dados arrastando um conector da fonte ou transformação anterior para a transformação Agregação.</span><span class="sxs-lookup"><span data-stu-id="77784-108">Connect the Aggregate transformation to the data flow by dragging a connector from the source or the previous transformation to the Aggregate transformation.</span></span>  
  
5.  <span data-ttu-id="77784-109">Clique duas vezes na transformação.</span><span class="sxs-lookup"><span data-stu-id="77784-109">Double-click the transformation.</span></span>  
  
6.  <span data-ttu-id="77784-110">Na caixa de diálogo **Editor da Transformação Agregação** , clique na guia **Agregações** .</span><span class="sxs-lookup"><span data-stu-id="77784-110">In the **Aggregate Transformation Editor** dialog box, click the **Aggregations** tab.</span></span>  
  
7.  <span data-ttu-id="77784-111">Na lista **Colunas de Entrada Disponíveis** , marque a caixa de seleção ao lado das colunas nas quais deseja agregar os valores.</span><span class="sxs-lookup"><span data-stu-id="77784-111">In the **Available Input Columns** list, select the check box by the columns on which you want to aggregate values.</span></span> <span data-ttu-id="77784-112">As colunas selecionadas aparecem na tabela.</span><span class="sxs-lookup"><span data-stu-id="77784-112">The selected columns appear in the table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77784-113">É possível selecionar uma coluna diversas vezes, aplicando diversas transformações à coluna.</span><span class="sxs-lookup"><span data-stu-id="77784-113">You can select a column multiple times, applying multiple transformations to the column.</span></span> <span data-ttu-id="77784-114">Para identificar exclusivamente as agregações, um número é anexado ao nome padrão do alias de saída da coluna.</span><span class="sxs-lookup"><span data-stu-id="77784-114">To uniquely identify aggregations, a number is appended to the default name of the output alias of the column.</span></span>  
  
8.  <span data-ttu-id="77784-115">Como opção, modifique o valor nas colunas **Alias de Saída** .</span><span class="sxs-lookup"><span data-stu-id="77784-115">Optionally, modify the value in the **Output Alias** columns.</span></span>  
  
9. <span data-ttu-id="77784-116">Para alterar a operação de agregação padrão, **Agrupar por**selecione uma operação diferente na lista **Operação** .</span><span class="sxs-lookup"><span data-stu-id="77784-116">To change the default aggregation operation, **Group by**, select a different operation in the **Operation** list.</span></span>  
  
10. <span data-ttu-id="77784-117">Para alterar a comparação padrão, selecione os sinalizadores de comparação individuais listados na coluna **Sinalizadores de Comparação** .</span><span class="sxs-lookup"><span data-stu-id="77784-117">To change the default comparison, select the individual comparison flags listed in the **Comparison Flags** column.</span></span> <span data-ttu-id="77784-118">Por padrão, uma comparação ignora a diferença entre maiúsculas e minúsculas, tipo kana, caracteres sem-espaçamento e largura do caractere.</span><span class="sxs-lookup"><span data-stu-id="77784-118">By default, a comparison ignores case, kana type, non-spacing characters, and character width.</span></span>  
  
11. <span data-ttu-id="77784-119">Como opção, para a agregação **Distinção de contagem** , especifique um número exato de valores distintos na coluna **Chaves de Distinção de Contagem** ou selecione uma contagem aproximada na coluna **Escala de Distinção de Contagem** .</span><span class="sxs-lookup"><span data-stu-id="77784-119">Optionally, for the **Count distinct** aggregation, specify an exact number of distinct values in the **Count Distinct Keys** column, or select an approximate count in the **Count Distinct Scale** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77784-120">O fornecimento do número de valores distintos, exato ou aproximado, melhora o desempenho, pois a transformação pode alocar antecipadamente uma quantidade da memória para fazer seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="77784-120">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
12. <span data-ttu-id="77784-121">Como opção, clique em **Avançado** e atualize o nome da saída da transformação Agregação.</span><span class="sxs-lookup"><span data-stu-id="77784-121">Optionally, click **Advanced** and update the name of the Aggregate transformation output.</span></span> <span data-ttu-id="77784-122">Se as agregações incluírem uma `Group By` operação, você poderá selecionar uma contagem aproximada de valores de chave de agrupamento na coluna **escala de chaves** ou especificar um número exato de valores de chave de agrupamento na coluna **chaves** .</span><span class="sxs-lookup"><span data-stu-id="77784-122">If the aggregations include a `Group By` operation, you can select an approximate count of grouping key values in the **Keys Scale** column or specify an exact number of grouping key values in the **Keys** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77784-123">O fornecimento do número de valores distintos, exato ou aproximado, melhora o desempenho, pois a transformação pode alocar antecipadamente uma quantidade da memória para fazer seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="77784-123">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77784-124">As opções **Escala de Chaves** e **Chaves** são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="77784-124">The **Keys Scale** and **Keys** options are mutually exclusive.</span></span> <span data-ttu-id="77784-125">Se você digitar valores em ambas as colunas, o valor maior em **Escala de Chaves** ou **Chaves** será usado.</span><span class="sxs-lookup"><span data-stu-id="77784-125">If you enter values in both columns, the larger value in either **Keys Scale** or **Keys** is used.</span></span>  
  
13. <span data-ttu-id="77784-126">Como opção, clique na guia **Avançado** e defina os atributos que se aplicam à otimização de todas as operações realizadas pela transformação Agregação.</span><span class="sxs-lookup"><span data-stu-id="77784-126">Optionally, click the **Advanced** tab and set the attributes that apply to optimizing all the operations that the Aggregate transformation performs.</span></span>  
  
14. <span data-ttu-id="77784-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="77784-127">Click **OK**.</span></span>  
  
15. <span data-ttu-id="77784-128">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="77784-128">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77784-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77784-129">See Also</span></span>  
 <span data-ttu-id="77784-130">[Transformação Agregação](aggregate-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="77784-130">[Aggregate Transformation](aggregate-transformation.md) </span></span>  
 <span data-ttu-id="77784-131">[Transformações do Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="77784-131">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="77784-132">[Caminhos do Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="77784-132">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="77784-133">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="77784-133">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
