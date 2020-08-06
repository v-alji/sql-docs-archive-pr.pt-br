---
title: Criar conjuntos nomeados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculations [Analysis Services], named sets
- named sets [Analysis Services]
- members [Analysis Services], named sets
ms.assetid: 03cf97a4-1a18-45f3-acb0-35123bd619be
author: minewiskan
ms.author: owend
ms.openlocfilehash: e92984102ceb8ad0ac049c15870e9f1efd6090fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679063"
---
# <a name="create-named-sets"></a><span data-ttu-id="991be-102">Criar conjuntos nomeados</span><span class="sxs-lookup"><span data-stu-id="991be-102">Create Named Sets</span></span>
  <span data-ttu-id="991be-103">Um conjunto nomeado é um conjunto de membros ou uma expressão de conjunto que é criado(a) para ser reutilizado(a), por exemplo, em consultas multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="991be-103">A named set is a set of dimension members or a set expression that is created for reuse, for example in Multidimensional Expressions (MDX) queries.</span></span> <span data-ttu-id="991be-104">É possível criar conjuntos nomeados combinando dados de cubo, operadores aritméticos, números e funções.</span><span class="sxs-lookup"><span data-stu-id="991be-104">You can create named sets by combining cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="991be-105">Por exemplo, você pode criar um conjunto nomeado chamado Dez Maiores Fábricas que contém os dez membros da dimensão Fábricas com os valores mais altos para a medida Produção.</span><span class="sxs-lookup"><span data-stu-id="991be-105">For example, you can create a named set called Top Ten Factories that contains the ten members of the Factories dimension that have the highest values for the Production measure.</span></span> <span data-ttu-id="991be-106">Os usuários finais podem usar o conjunto Dez Maiores Fábricas em consultas.</span><span class="sxs-lookup"><span data-stu-id="991be-106">Top Ten Factories can then be used in queries by end users.</span></span> <span data-ttu-id="991be-107">Por exemplo, um usuário final pode colocar o conjunto Dez Maiores Fábricas em um eixo e a dimensão Medidas, incluindo Produção, em outro.</span><span class="sxs-lookup"><span data-stu-id="991be-107">For example, an end user can place Top Ten Factories on one axis and the Measures dimension, including Production, on another axis.</span></span> <span data-ttu-id="991be-108">Para obter mais informações, consulte [Cálculos em modelos multidimensionais](calculations-in-multidimensional-models.md), e [Criando conjuntos nomeados em MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="991be-108">For more information, see [Calculations in Multidimensional Models](calculations-in-multidimensional-models.md), and [Building Named Sets in MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="991be-109">Para criar um conjunto nomeado, use o comando **Novo Conjunto Nomeado** da guia **Cálculos** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="991be-109">To create a named set, use the **New Named Set** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="991be-110">Esse comando pode ser chamado pelo menu **Cubo** na barra de ferramentas da guia **Cálculos** .</span><span class="sxs-lookup"><span data-stu-id="991be-110">This command can be invoked on the **Cube** menu on the **Calculations** tab toolbar.</span></span> <span data-ttu-id="991be-111">Ele exibe um formulário para você especificar as seguintes opções para o conjunto nomeado:</span><span class="sxs-lookup"><span data-stu-id="991be-111">This command displays a form to specify the following options for the named set:</span></span>  
  
 <span data-ttu-id="991be-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="991be-112">**Name**</span></span>  
 <span data-ttu-id="991be-113">Selecione o nome do conjunto nomeado.</span><span class="sxs-lookup"><span data-stu-id="991be-113">Select the name of the named set.</span></span> <span data-ttu-id="991be-114">Ele aparecerá para os usuários finais quando eles procurarem o cubo.</span><span class="sxs-lookup"><span data-stu-id="991be-114">This name appears to end users when they browse the cube.</span></span>  
  
 <span data-ttu-id="991be-115">**Expression**</span><span class="sxs-lookup"><span data-stu-id="991be-115">**Expression**</span></span>  
 <span data-ttu-id="991be-116">Especifique a expressão que produz o conjunto nomeado.</span><span class="sxs-lookup"><span data-stu-id="991be-116">Specify the expression that produces the named set.</span></span> <span data-ttu-id="991be-117">Pode ser escrita em MDX.</span><span class="sxs-lookup"><span data-stu-id="991be-117">This expression can be written in MDX.</span></span> <span data-ttu-id="991be-118">A expressão pode conter uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="991be-118">The expression can contain any of the following:</span></span>  
  
-   <span data-ttu-id="991be-119">Expressões de dados que representam componentes de cubo, como dimensões, níveis, medidas, etc.</span><span class="sxs-lookup"><span data-stu-id="991be-119">Data expressions that represent cube components such as dimensions, levels, measures, and so on.</span></span>  
  
-   <span data-ttu-id="991be-120">Operadores aritméticos.</span><span class="sxs-lookup"><span data-stu-id="991be-120">Arithmetic operators.</span></span>  
  
-   <span data-ttu-id="991be-121">Números.</span><span class="sxs-lookup"><span data-stu-id="991be-121">Numbers.</span></span>  
  
-   <span data-ttu-id="991be-122">Funções.</span><span class="sxs-lookup"><span data-stu-id="991be-122">Functions.</span></span>  
  
 <span data-ttu-id="991be-123">É possível copiar ou arrastar os componentes do cubo da guia **Metadados** no painel **Ferramentas de Cálculo** para a caixa **Expressão** do painel **Editor de Formulário de Conjunto de Nomeado** .</span><span class="sxs-lookup"><span data-stu-id="991be-123">You can copy or drag cube components from the **Metadata** tab of the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span> <span data-ttu-id="991be-124">É possível copiar ou arrastar as funções da guia **Funções** no painel **Ferramentas de Cálculo** para a caixa **Expressão** do painel **Editor de Formulário de Conjunto de Nomeado** .</span><span class="sxs-lookup"><span data-stu-id="991be-124">You can copy or drag functions from the **Functions** tab in the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="991be-125">Se você criar a expressão de conjunto nomeando explicitamente os membros no conjunto, coloque a lista de membros em um par de chaves ( {} ).</span><span class="sxs-lookup"><span data-stu-id="991be-125">If you create the set expression by explicitly naming the members in the set, enclose the list of members in a pair of braces ({}).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991be-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="991be-126">See Also</span></span>  
 [<span data-ttu-id="991be-127">Cálculos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="991be-127">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)  
  
  
