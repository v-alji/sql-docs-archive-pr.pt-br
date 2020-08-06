---
title: Criar relações | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.createrelationships.f1
ms.assetid: 6ebd305f-ffd2-4a1d-b24c-e28c151b94f5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a1095e193587ae7d416311031e5297a035ca37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571464"
---
# <a name="create-relationships"></a><span data-ttu-id="8f93b-102">Criar Relações</span><span class="sxs-lookup"><span data-stu-id="8f93b-102">Create Relationships</span></span>
  <span data-ttu-id="8f93b-103">Use a caixa de diálogo **Criar Relações** para editar mapeamentos entre as colunas de origem e as colunas da tabela de pesquisa que você configurou no Editor de Transformação Pesquisa Difusa, no Editor de Transformação Pesquisa e no Editor de Transformação Pesquisa de Termos.</span><span class="sxs-lookup"><span data-stu-id="8f93b-103">Use the **Create Relationships** dialog box to edit mappings between the source columns and the lookup table columns that you configured in the Fuzzy Lookup Transformation Editor, the Lookup Transformation Editor, and the Term Lookup Transformation Editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f93b-104">A caixa de diálogo **Criar Relações** exibe só as listas de **Coluna de Entrada** e **Coluna de Pesquisa** quando invocada do Editor de Transformação Pesquisa de Termos.</span><span class="sxs-lookup"><span data-stu-id="8f93b-104">The **Create Relationships** dialog box displays only the **Input Column** and **Lookup Column** lists when invoked from the Term Lookup Transformation Editor.</span></span>  
  
 <span data-ttu-id="8f93b-105">Para saber mais sobre as transformações que usam a caixa de diálogo **Criar Relações** , consulte [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md)e [Term Lookup Transformation](term-lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8f93b-105">To learn more about the transformations that use the **Create Relationships** dialog box, see [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md), and [Term Lookup Transformation](term-lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8f93b-106">Opções</span><span class="sxs-lookup"><span data-stu-id="8f93b-106">Options</span></span>  
 <span data-ttu-id="8f93b-107">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="8f93b-107">**Input Column**</span></span>  
 <span data-ttu-id="8f93b-108">Selecione na lista de colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8f93b-108">Select from the list of available input columns.</span></span>  
  
 <span data-ttu-id="8f93b-109">**coluna de pesquisa**</span><span class="sxs-lookup"><span data-stu-id="8f93b-109">**Lookup Column**</span></span>  
 <span data-ttu-id="8f93b-110">Selecione na lista de colunas de pesquisa disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8f93b-110">Select from the list of available lookup columns.</span></span>  
  
 <span data-ttu-id="8f93b-111">**Tipo de Mapeamento**</span><span class="sxs-lookup"><span data-stu-id="8f93b-111">**Mapping Type**</span></span>  
 <span data-ttu-id="8f93b-112">Selecione correspondência difusa ou exata.</span><span class="sxs-lookup"><span data-stu-id="8f93b-112">Select fuzzy or exact matching.</span></span>  
  
 <span data-ttu-id="8f93b-113">Quando é usada correspondência difusa, as linhas serão consideradas duplicatas se forem suficientemente semelhantes em todas as colunas que têm tipo de correspondência difusa.</span><span class="sxs-lookup"><span data-stu-id="8f93b-113">When you use fuzzy matching, rows are considered duplicates if they are sufficiently similar across all columns that have a fuzzy match type.</span></span> <span data-ttu-id="8f93b-114">Para obter resultados melhores na correspondência difusa, você pode especificar que algumas colunas devem usar a correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="8f93b-114">To obtain better results from fuzzy matching, you can specify that some columns should use exact matching instead of fuzzy matching.</span></span> <span data-ttu-id="8f93b-115">Por exemplo, se souber que certa coluna não contém nenhum erro ou inconsistência, você poderá especificar correspondência exata para ela, de forma que só as linhas que contêm valores idênticos nessa coluna sejam consideradas como possíveis duplicatas.</span><span class="sxs-lookup"><span data-stu-id="8f93b-115">For example, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column, so that only rows which contain identical values in this column are considered as possible duplicates.</span></span> <span data-ttu-id="8f93b-116">Isso aumenta a exatidão da correspondência difusa em outras colunas.</span><span class="sxs-lookup"><span data-stu-id="8f93b-116">This increases the accuracy of fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="8f93b-117">**Sinalizadores de Comparação**</span><span class="sxs-lookup"><span data-stu-id="8f93b-117">**Comparison Flags**</span></span>  
 <span data-ttu-id="8f93b-118">Para obter mais informações sobre as opções de comparação de cadeias de caracteres, consulte [Comparando dados de cadeia de caracteres](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="8f93b-118">For information about the string comparison options, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="8f93b-119">**Similaridade Mínima**</span><span class="sxs-lookup"><span data-stu-id="8f93b-119">**Minimum Similarity**</span></span>  
 <span data-ttu-id="8f93b-120">Defina o limite de similaridade no nível de coluna usando o controle deslizante.</span><span class="sxs-lookup"><span data-stu-id="8f93b-120">Set the similarity threshold at the column level by using the slider.</span></span> <span data-ttu-id="8f93b-121">Quanto mais próximo de 1 for o valor, maior deverá ser a semelhança entre o valor de pesquisa e o valor da origem para a qualificação de correspondências.</span><span class="sxs-lookup"><span data-stu-id="8f93b-121">The closer the value is to 1, the more the lookup value must resemble the source value to qualify as a match.</span></span> <span data-ttu-id="8f93b-122">Aumentar o limite pode melhorar a velocidade de correspondência, pois menos registros candidatos precisam ser considerados.</span><span class="sxs-lookup"><span data-stu-id="8f93b-122">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="8f93b-123">**Alias de Saída de Similaridade**</span><span class="sxs-lookup"><span data-stu-id="8f93b-123">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="8f93b-124">Especifique o nome da nova coluna de saída que conterá as pontuações de similaridade da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="8f93b-124">Specify the name for a new output column that contains the similarity scores for the selected column.</span></span> <span data-ttu-id="8f93b-125">Se você deixar este valor vazio, a coluna de saída não será criada.</span><span class="sxs-lookup"><span data-stu-id="8f93b-125">If you leave this value empty, the output column is not created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f93b-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f93b-126">See Also</span></span>  
 <span data-ttu-id="8f93b-127">[Referência de mensagens e erros do Integration Services](../../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8f93b-127">[Integration Services Error and Message Reference](../../integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8f93b-128">[Editor de Transformação Pesquisa Difusa &#40;guia Colunas&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="8f93b-128">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 <span data-ttu-id="8f93b-129">[Editor de Transformação Pesquisa &#40;Guia Colunas&#41;](../../lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="8f93b-129">[Lookup Transformation Editor &#40;Columns Page&#41;](../../lookup-transformation-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="8f93b-130">Editor de Transformação Pesquisa de Termos &#40;Guia Pesquisa de Termos&#41;</span><span class="sxs-lookup"><span data-stu-id="8f93b-130">Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;</span></span>](../../term-lookup-transformation-editor-term-lookup-tab.md)  
  
  
