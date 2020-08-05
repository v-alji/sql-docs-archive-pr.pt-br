---
title: Caixa de diálogo Inserir função (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- SQL12.ASVS.BIDTOOLSET.INSERTFUNCTIONDB.F1
ms.assetid: c4b36d8f-2328-45f7-8bd4-cc0111571e25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0d92dd34e671dc026215d79e7eaed88bebfac15f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574404"
---
# <a name="insert-function-dialog-box-ssas"></a><span data-ttu-id="8e847-102">Caixa de diálogo Inserir Função (SSAS)</span><span class="sxs-lookup"><span data-stu-id="8e847-102">Insert Function Dialog Box (SSAS)</span></span>
  <span data-ttu-id="8e847-103">A caixa de diálogo **Inserir Função** o habilita a escolher de uma lista de funções que podem ser usadas na criação de fórmulas.</span><span class="sxs-lookup"><span data-stu-id="8e847-103">The **Insert Function** dialog box enables you to choose from a list of functions that can be used when building formulas.</span></span> <span data-ttu-id="8e847-104">Para acessar essa caixa de diálogo no designer modelo, ou na barra de fórmula na parte superior de cada tabela, clique no botão de função (**fx**).</span><span class="sxs-lookup"><span data-stu-id="8e847-104">To access this dialog box from the model designer, in the formula bar above each table, click the function (**fx**) button.</span></span> <span data-ttu-id="8e847-105">Para obter mais informações sobre como escolher funções a serem usadas em fórmulas, consulte Apresentação de DAX e Criar uma Fórmula.</span><span class="sxs-lookup"><span data-stu-id="8e847-105">For more information about choosing functions to use in formulas, see DAX Introduction and Build a Formula.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e847-106">Item</span><span class="sxs-lookup"><span data-stu-id="8e847-106">Item</span></span>|<span data-ttu-id="8e847-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e847-107">Description</span></span>|  
|<span data-ttu-id="8e847-108">**Selecionar uma categoria**</span><span class="sxs-lookup"><span data-stu-id="8e847-108">**Select a category**</span></span>|<span data-ttu-id="8e847-109">Se você souber o tipo de função de que precisa, escolha uma categoria na lista; ou selecione **Tudo** para exibir uma lista alfabética de funções.</span><span class="sxs-lookup"><span data-stu-id="8e847-109">If you have a general idea which kind of function you need, choose a category from the list; or select **All** to view an alphabetical list of functions.</span></span>|  
|<span data-ttu-id="8e847-110">**Definir uma função**</span><span class="sxs-lookup"><span data-stu-id="8e847-110">**Select a function**</span></span>|<span data-ttu-id="8e847-111">Exibe uma lista das funções na categoria selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e847-111">Displays a list of the functions in the selected category.</span></span>|  
|<span data-ttu-id="8e847-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8e847-112">**Description**</span></span>|<span data-ttu-id="8e847-113">Exibe uma descrição do que a função faz, junto com os argumentos obrigatórios ou opcionais, como nomes de coluna e expressões.</span><span class="sxs-lookup"><span data-stu-id="8e847-113">Displays a description of what the function does, together with any required or optional arguments, such as column names and expressions.</span></span>|  
  
## <a name="function-categories"></a><span data-ttu-id="8e847-114">Categorias de função</span><span class="sxs-lookup"><span data-stu-id="8e847-114">Function Categories</span></span>  
 <span data-ttu-id="8e847-115">A linguagem DAX fornece os tipos de categorias de função a seguir na caixa de diálogo **Inserir Funções** .</span><span class="sxs-lookup"><span data-stu-id="8e847-115">Data Analysis Expressions (DAX) provides the following types of function categories in the **Insert Functions** dialog box.</span></span>  
  
 <span data-ttu-id="8e847-116">Tudo</span><span class="sxs-lookup"><span data-stu-id="8e847-116">All</span></span>  
  
 <span data-ttu-id="8e847-117">Data e Hora</span><span class="sxs-lookup"><span data-stu-id="8e847-117">Date & Time</span></span>  
  
 <span data-ttu-id="8e847-118">Filtrar</span><span class="sxs-lookup"><span data-stu-id="8e847-118">Filter</span></span>  
  
 <span data-ttu-id="8e847-119">Lógica</span><span class="sxs-lookup"><span data-stu-id="8e847-119">Logical</span></span>  
  
 <span data-ttu-id="8e847-120">Matemática e Trigonometria</span><span class="sxs-lookup"><span data-stu-id="8e847-120">Math & Trig</span></span>  
  
 <span data-ttu-id="8e847-121">Estatística</span><span class="sxs-lookup"><span data-stu-id="8e847-121">Statistical</span></span>  
  
 <span data-ttu-id="8e847-122">Texto</span><span class="sxs-lookup"><span data-stu-id="8e847-122">Text</span></span>  
  
## <a name="measures-and-formulas"></a><span data-ttu-id="8e847-123">Medidas e fórmulas</span><span class="sxs-lookup"><span data-stu-id="8e847-123">Measures and Formulas</span></span>  
 <span data-ttu-id="8e847-124">A caixa de diálogo **Inserir Função** está disponível apenas quando você está criando uma fórmula.</span><span class="sxs-lookup"><span data-stu-id="8e847-124">The **Insert Function** dialog box is available only when you are building a formula.</span></span> <span data-ttu-id="8e847-125">Você pode criar cálculos em uma coluna calculada, ou em uma Tabela Dinâmica ou um Gráfico Dinâmico.</span><span class="sxs-lookup"><span data-stu-id="8e847-125">You can create calculations either in a calculated column, or in a PivotTable or PivotChart.</span></span> <span data-ttu-id="8e847-126">As fórmulas que você cria expressamente para uso em uma Tabela Dinâmica também são chamadas de *medidas*.</span><span class="sxs-lookup"><span data-stu-id="8e847-126">Formulas that you build expressly for use in a PivotTable are also called *measures*.</span></span> <span data-ttu-id="8e847-127">Para obter mais informações, consulte [Criar uma coluna calculada &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) e [Criar e gerenciar medidas &#40;SSAS Tabular&#41;](tabular-models/measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="8e847-127">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) and [Create and Manage Measures &#40;SSAS Tabular&#41;](tabular-models/measures-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e847-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e847-128">See Also</span></span>  
 [<span data-ttu-id="8e847-129">Cálculos &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="8e847-129">Calculations &#40;SSAS Tabular&#41;</span></span>](tabular-models/calculations-ssas-tabular.md)  
  
  
