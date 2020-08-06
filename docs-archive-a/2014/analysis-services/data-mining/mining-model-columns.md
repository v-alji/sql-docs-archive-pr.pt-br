---
title: Colunas do modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining model columns
- columns [data mining]
- REGRESSOR column
- columns [data mining], modeling flags
- modeling flags [data mining]
- MODEL_EXISTENCE_ONLY column
- usage property [data mining]
ms.assetid: fab47643-5bfd-424e-a0f7-69e665db6bab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f936f3f4e0b8f65326e9a6e84f75e6f4e82657f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680719"
---
# <a name="mining-model-columns"></a><span data-ttu-id="caef7-102">Colunas do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="caef7-102">Mining Model Columns</span></span>
  <span data-ttu-id="caef7-103">Um modelo de mineração de dados aplica um algoritmo de modelo de mineração aos dados que são representados por uma estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="caef7-103">A data mining model applies a mining model algorithm to the data that is represented by a mining structure.</span></span> <span data-ttu-id="caef7-104">Como a estrutura de mineração, o modelo de mineração contém colunas.</span><span class="sxs-lookup"><span data-stu-id="caef7-104">Like the mining structure, the mining model contains columns.</span></span> <span data-ttu-id="caef7-105">Um modelo de mineração reside na estrutura de mineração e herda todos os valores das propriedades que são definidos pela estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="caef7-105">A mining model is contained within the mining structure, and inherits all the values of the properties that are defined by the mining structure.</span></span> <span data-ttu-id="caef7-106">O modelo pode usar todas as colunas contidas na estrutura de mineração ou um subconjunto das colunas.</span><span class="sxs-lookup"><span data-stu-id="caef7-106">The model can use all the columns that the mining structure contains or a subset of the columns.</span></span>  
  
 <span data-ttu-id="caef7-107">Você pode definir duas informações adicionais em uma coluna de modelo de mineração: uso e sinalizadores de modelagem.</span><span class="sxs-lookup"><span data-stu-id="caef7-107">You can define two additional pieces of information on a mining model column: usage, and modeling flags.</span></span>  
  
-   <span data-ttu-id="caef7-108">**Uso** é uma propriedade que define como o modelo usa a coluna.</span><span class="sxs-lookup"><span data-stu-id="caef7-108">**Usage** is a property that defines how the model uses the column.</span></span> <span data-ttu-id="caef7-109">As colunas podem ser usadas como colunas de entrada, colunas de chave ou colunas previsíveis.</span><span class="sxs-lookup"><span data-stu-id="caef7-109">Columns can be used as input columns, key columns, or predictable columns.</span></span>  
  
-   <span data-ttu-id="caef7-110">Os**sinalizadores de modelagem** fornecem o algoritmo com informações adicionais sobre os dados definidos na tabela de casos, de forma que o algoritmo possa criar um modelo mais preciso.</span><span class="sxs-lookup"><span data-stu-id="caef7-110">**Modeling flags** provide the algorithm with additional information about the data that is defined in the case table, so that the algorithm can build a more accurate model.</span></span> <span data-ttu-id="caef7-111">Você pode definir sinalizadores de modelagem programaticamente usando a linguagem DMX (Data Mining Extensions) ou no **Designer de Mineração de Dados** em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="caef7-111">You can define modeling flags programmatically by using the Data Mining Extensions (DMX) language, or in **Data Mining Designer** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="caef7-112">A lista a seguir descreve os sinalizadores de modelagem que você pode definir em uma coluna de modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="caef7-112">The following list describes the modeling flags that you can define on a mining model column.</span></span>  
  
 `MODEL_EXISTENCE_ONLY`  
 <span data-ttu-id="caef7-113">Indica que a presença do atributo é mais importante que os valores da coluna de atributo.</span><span class="sxs-lookup"><span data-stu-id="caef7-113">Indicates that the presence of the attribute is more important than the values that are in the attribute column.</span></span> <span data-ttu-id="caef7-114">Por exemplo, considere a tabela de casos que contém uma lista de itens do pedido que são associados a um cliente específico.</span><span class="sxs-lookup"><span data-stu-id="caef7-114">For example, consider a case table that contains a list of order items that are associated with a particular customer.</span></span> <span data-ttu-id="caef7-115">Os dados da tabela incluem o tipo de produto, ID e custo de cada item.</span><span class="sxs-lookup"><span data-stu-id="caef7-115">The table data includes the product type, ID, and cost of each item.</span></span> <span data-ttu-id="caef7-116">Para fins de modelagem, o fato que o cliente comprou um item do pedido em particular pode ser mais importante que o custo em si do item do pedido.</span><span class="sxs-lookup"><span data-stu-id="caef7-116">For modeling purposes, the fact that the customer purchased a particular order item may be more important than the cost of the order item itself.</span></span> <span data-ttu-id="caef7-117">Neste caso, a coluna de custo deveria ser marcada como `MODEL_EXISTENCE_ONLY`.</span><span class="sxs-lookup"><span data-stu-id="caef7-117">In this case, the cost column should be marked as `MODEL_EXISTENCE_ONLY`.</span></span>  
  
 `REGRESSOR`  
 <span data-ttu-id="caef7-118">Indica que o algoritmo pode usar a coluna especificada na fórmula de regressão de algoritmos de regressão.</span><span class="sxs-lookup"><span data-stu-id="caef7-118">Indicates that the algorithm can use the specified column in the regression formula of regression algorithms.</span></span> <span data-ttu-id="caef7-119">Há suporte para esse sinalizador nos algoritmos das Árvores de Decisão do [!INCLUDE[msCoName](../../includes/msconame-md.md)] e Série Temporal do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="caef7-119">This flag is supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series algorithms.</span></span>  
  
 <span data-ttu-id="caef7-120">Para obter mais informações sobre a configuração da propriedade de uso e definição dos sinalizadores de modelagem programaticamente com DMX, consulte [CRIAR UM MODELO DE MINERAÇÃO &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span><span class="sxs-lookup"><span data-stu-id="caef7-120">For more information about setting the usage property and defining modeling flags programmatically with DMX, see [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span></span> <span data-ttu-id="caef7-121">Para obter mais informações sobre a configuração da propriedade de uso e definição dos sinalizadores de modelagem no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], consulte [Movendo objetos de mineração de dados](moving-data-mining-objects.md).</span><span class="sxs-lookup"><span data-stu-id="caef7-121">For more information about setting the usage property and defining modeling flags in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Moving Data Mining Objects](moving-data-mining-objects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caef7-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="caef7-122">See Also</span></span>  
 <span data-ttu-id="caef7-123">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="caef7-123">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="caef7-124">[Estruturas de mineração &#40;Analysis Services de mineração de dados&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="caef7-124">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="caef7-125">[Alterar as propriedades de um modelo de mineração](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="caef7-125">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="caef7-126">[Excluir uma coluna de um modelo de mineração](exclude-a-column-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="caef7-126">[Exclude a Column from a Mining Model](exclude-a-column-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="caef7-127">Colunas da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="caef7-127">Mining Structure Columns</span></span>](mining-structure-columns.md)  
  
  
