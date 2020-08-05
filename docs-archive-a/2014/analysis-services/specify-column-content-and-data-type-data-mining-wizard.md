---
title: Especificar o tipo de conteúdo e de dados da coluna (Assistente de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0634be64-4c38-4381-9b19-fe9a5889306c
author: minewiskan
ms.author: owend
ms.openlocfilehash: e22f46808877391376f721bcab55ea4fd9074186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572723"
---
# <a name="specify-column-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="1d444-102">Especificar tipo de conteúdo e de dados da coluna (Assistente de Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="1d444-102">Specify Column Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="1d444-103">Use a página **Especificar Tipo de Conteúdo e de Dados da Coluna** para especificar o uso e o tipo de dados de cada coluna selecionada na página anterior do assistente.</span><span class="sxs-lookup"><span data-stu-id="1d444-103">Use the **Specify Column Content and Data Type** page to specify the usage and data type for each column that you selected on the previous page of the wizard.</span></span> <span data-ttu-id="1d444-104">Se desejar ignorar a coluna, clique em **Voltar** para voltar à página **Especificar os Dados de Treinamento**e desmarque todas as caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="1d444-104">If you want to ignore the column, click **Back** to return to the page **Specify the Training Data**, and clear all checkboxes.</span></span>  
  
 <span data-ttu-id="1d444-105">O uso de uma coluna indica como os dados serão usados no modelo.</span><span class="sxs-lookup"><span data-stu-id="1d444-105">The usage of a column indicates how the data will be used in the model.</span></span> <span data-ttu-id="1d444-106">Uma coluna pode ser usada como chave para identificar uma série, como um valor de entrada a ser usado na análise ou como o valor que você deseja prever.</span><span class="sxs-lookup"><span data-stu-id="1d444-106">A column can be used as a key to identify a series, as an input value to use in analysis, or as the value that you want to predict.</span></span> <span data-ttu-id="1d444-107">As colunas podem ser usadas tanto para previsão como para entrada.</span><span class="sxs-lookup"><span data-stu-id="1d444-107">Columns can be used for both prediction and input.</span></span>  
  
 <span data-ttu-id="1d444-108">O tipo de dados especifica detalhes adicionais sobre o tipo de dados contidos na coluna e como eles serão usados durante o treinamento.</span><span class="sxs-lookup"><span data-stu-id="1d444-108">The data type specifies additional detail about the type of data that is contained in the column, and how the data will be used during training.</span></span> <span data-ttu-id="1d444-109">Alguns tipos de conteúdo requerem um tipo de dados específico e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="1d444-109">Some content types require a specific data type, and vice versa.</span></span> <span data-ttu-id="1d444-110">Você também pode precisar especificar um tipo de dados específico, dependendo do algoritmo usado ao criar um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="1d444-110">You might also need to specify a particular data type depending on the algorithm that you use when you create a mining model.</span></span> <span data-ttu-id="1d444-111">Para obter informações sobre tipos de conteúdo e de dados em modelos e estruturas de mineração, consulte [Tipos de conteúdo &#40;Mineração de dados&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1d444-111">For information about content types and data types in mining models and structures, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="1d444-112">**Para obter mais informações:** [Estruturas de mineração &#40;Analysis Services – Mineração de dados&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Colunas do modelo de mineração](data-mining/mining-model-columns.md), [Assistente de Mineração de dados &#40;Analysis Services – Mineração de dados&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md) e [Criar uma estrutura de mineração relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="1d444-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="1d444-113">Opções</span><span class="sxs-lookup"><span data-stu-id="1d444-113">Options</span></span>  
 <span data-ttu-id="1d444-114">**Estrutura do modelo de mineração**</span><span class="sxs-lookup"><span data-stu-id="1d444-114">**Mining model structure**</span></span>  
 <span data-ttu-id="1d444-115">Exibe as colunas das exibições e tabelas aninhadas que você selecionou na página anterior do assistente.</span><span class="sxs-lookup"><span data-stu-id="1d444-115">Displays the columns from the views and nested tables that you selected on the previous page of the wizard.</span></span>  
  
 <span data-ttu-id="1d444-116">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="1d444-116">**Columns**</span></span>  
 <span data-ttu-id="1d444-117">Lista as colunas.</span><span class="sxs-lookup"><span data-stu-id="1d444-117">Lists the columns.</span></span>  
  
 <span data-ttu-id="1d444-118">**Tipo de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="1d444-118">**Content type**</span></span>  
 <span data-ttu-id="1d444-119">Especifique o tipo de conteúdo da coluna</span><span class="sxs-lookup"><span data-stu-id="1d444-119">Specify the content type for the column.</span></span> <span data-ttu-id="1d444-120">Se você especificou que a coluna é uma chave na página anterior do assistente, os seguintes valores estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="1d444-120">If you specified that the column is a key on the previous page of the wizard, the following values are available:</span></span>  
  
|<span data-ttu-id="1d444-121">Opção</span><span class="sxs-lookup"><span data-stu-id="1d444-121">Option</span></span>|<span data-ttu-id="1d444-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d444-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1d444-123">Chave</span><span class="sxs-lookup"><span data-stu-id="1d444-123">Key</span></span>|<span data-ttu-id="1d444-124">Especifique que a coluna contém um identificador exclusivo para a série de casos.</span><span class="sxs-lookup"><span data-stu-id="1d444-124">Specify that the column contains a unique identifier for the case series.</span></span>|  
|<span data-ttu-id="1d444-125">Key Sequence</span><span class="sxs-lookup"><span data-stu-id="1d444-125">Key Sequence</span></span>|<span data-ttu-id="1d444-126">Especifique que a coluna contém um identificador de sequência.</span><span class="sxs-lookup"><span data-stu-id="1d444-126">Specify that the column contains a sequence identifier.</span></span>|  
|<span data-ttu-id="1d444-127">Key Time</span><span class="sxs-lookup"><span data-stu-id="1d444-127">Key Time</span></span>|<span data-ttu-id="1d444-128">Especifique que a coluna contém uma data ou outro número contínuo exclusivo que é usado para identificar uma série de datas ou horários.</span><span class="sxs-lookup"><span data-stu-id="1d444-128">Specify that the column contains a date or other unique continuous number that is used to identify a date or time series.</span></span>|  
  
 <span data-ttu-id="1d444-129">Se você selecionou a coluna como uma coluna que não seja uma coluna de chave, os valores seguintes estarão disponíveis, dependendo do tipo de dados:</span><span class="sxs-lookup"><span data-stu-id="1d444-129">If you selected the column as a non-key column, the following values are available, depending on the data type:</span></span>  
  
|<span data-ttu-id="1d444-130">Opção</span><span class="sxs-lookup"><span data-stu-id="1d444-130">Option</span></span>|<span data-ttu-id="1d444-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d444-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1d444-132">Contínuo</span><span class="sxs-lookup"><span data-stu-id="1d444-132">Continuous</span></span>|<span data-ttu-id="1d444-133">Especifique que a coluna contém valores numéricos contínuos.</span><span class="sxs-lookup"><span data-stu-id="1d444-133">Specify that the column contains continuous numeric values.</span></span>|  
|<span data-ttu-id="1d444-134">Discretizado</span><span class="sxs-lookup"><span data-stu-id="1d444-134">Discretized</span></span>|<span data-ttu-id="1d444-135">Especifique que a coluna contém valores numéricos que foram tornados discretos ou podem ser tratados como valores discretos.</span><span class="sxs-lookup"><span data-stu-id="1d444-135">Specify that the column contains numeric values that either have been discretized, or can be treated as discrete values.</span></span>|  
|<span data-ttu-id="1d444-136">Discreto</span><span class="sxs-lookup"><span data-stu-id="1d444-136">Discrete</span></span>|<span data-ttu-id="1d444-137">Especifique que a coluna contém valores de texto ou outros valores não numéricos.</span><span class="sxs-lookup"><span data-stu-id="1d444-137">Specify that the column contains text or other nonnumeric values.</span></span>|  
  
 <span data-ttu-id="1d444-138">**Data type**</span><span class="sxs-lookup"><span data-stu-id="1d444-138">**Data type**</span></span>  
 <span data-ttu-id="1d444-139">Especifique o tipo de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="1d444-139">Specify the data type for the column.</span></span>  
  
 <span data-ttu-id="1d444-140">Os seguintes valores estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="1d444-140">The following values are available:</span></span>  
  
-   `Boolean`  
  
-   `Date`  
  
-   `Double`  
  
-   `Long`  
  
-   `Text`  
  
 <span data-ttu-id="1d444-141">**Detect**</span><span class="sxs-lookup"><span data-stu-id="1d444-141">**Detect**</span></span>  
 <span data-ttu-id="1d444-142">Analise uma amostra de dados em todas as colunas numéricas.</span><span class="sxs-lookup"><span data-stu-id="1d444-142">Analyze a sample of data in all numeric columns.</span></span> <span data-ttu-id="1d444-143">Substitui valores de **Tipo de conteúdo** especificados por um tipo de conteúdo recomendado.</span><span class="sxs-lookup"><span data-stu-id="1d444-143">Replaces specified **Content Type** values with a recommended content type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d444-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d444-144">See Also</span></span>  
 <span data-ttu-id="1d444-145">[Ajuda F1 do assistente de mineração de dados &#40;Analysis Services Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1d444-145">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="1d444-146">[Sugerir colunas relacionadas &#40;assistente de mineração de dados&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="1d444-146">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="1d444-147">[Especificar tipos de tabela &#40;assistente de mineração de dados&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="1d444-147">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="1d444-148">Especifique o tipo de conteúdo e de dados da coluna &#40;assistente de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="1d444-148">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
