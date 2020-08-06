---
title: Colunas classificadas (mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content types [data mining]
- STDEV column
- VARIANCE column
- PROBABLILITY column
- PROBABILITY_STDEV column
- columns [data mining], classified
- classified columns [data mining]
- PROBABILITY_VARIANCE column
- SUPPORT column
ms.assetid: 68bf3b78-dc12-497c-898f-b43a45646123
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c264dfb6a97b8b8f576966e8929f6b0dc51e4ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581625"
---
# <a name="classified-columns-data-mining"></a><span data-ttu-id="1fff4-102">Colunas classificadas [mineração de dados]</span><span class="sxs-lookup"><span data-stu-id="1fff4-102">Classified Columns (Data Mining)</span></span>
  <span data-ttu-id="1fff4-103">Quando você define uma coluna classificada, cria uma relação entre a coluna atual e outra coluna na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="1fff4-103">When you define a classified column, you create a relationship between the current column and another column in the mining structure.</span></span> <span data-ttu-id="1fff4-104">Os dados na coluna da estrutura de mineração que você designa como a coluna classificada contém informações categóricas que descrevem os valores em outra coluna na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="1fff4-104">The data in the mining structure column that you designate as the classified column contains categorical information that describes the values in another column in the mining structure.</span></span>  
  
 <span data-ttu-id="1fff4-105">Por exemplo, suponha que você tenha duas colunas com dados numéricos: uma coluna, [Compras Anuais], contém as compras anuais totais por cliente durante um ano civil específico e a outra coluna, [Desvios Padrão], contém os desvios padrão para obter esses valores.</span><span class="sxs-lookup"><span data-stu-id="1fff4-105">For example, suppose you have two columns with numerical data: one column, [Yearly Purchases], contains the total yearly purchases per customer for a specific calendar year, and the other column, [Standard Deviations], contains the standard deviations for those values.</span></span> <span data-ttu-id="1fff4-106">Neste caso, você pode designar a coluna [Compras Anuais] como a coluna classificada e o modelo poderia usar esta relação na análise.</span><span class="sxs-lookup"><span data-stu-id="1fff4-106">In this case you could designate the [Yearly Purchases] column as the classified column, and the model would be able to use this relationship in analysis.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1fff4-107">Os algoritmos fornecidos no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não dão suporte ao uso de colunas classificadas; este recurso é fornecido para uso na criação de algoritmos personalizados.</span><span class="sxs-lookup"><span data-stu-id="1fff4-107">The algorithms provided in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not support the use of classified columns; this feature is provided for use in creating custom algorithms.</span></span>  
  
## <a name="defining-a-classified-column"></a><span data-ttu-id="1fff4-108">Definindo uma coluna classificada</span><span class="sxs-lookup"><span data-stu-id="1fff4-108">Defining a Classified Column</span></span>  
 <span data-ttu-id="1fff4-109">O tipo de dados de uma coluna classificada deve ser `Long` ou `Double`.</span><span class="sxs-lookup"><span data-stu-id="1fff4-109">The data type of a classified column must be either `Long` or `Double`.</span></span>  
  
 <span data-ttu-id="1fff4-110">A lista a seguir descreve os tipos de conteúdo para os quais o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] oferece suporte para colunas classificadas.</span><span class="sxs-lookup"><span data-stu-id="1fff4-110">The following list describes the content types that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports for classified columns.</span></span>  
  
 <span data-ttu-id="1fff4-111">**PROBABILIDADE**</span><span class="sxs-lookup"><span data-stu-id="1fff4-111">**PROBABILITY**</span></span>  
 <span data-ttu-id="1fff4-112">O valor na coluna é a probabilidade do valor associado e é um número entre 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="1fff4-112">The value in the column is the probability of the associated value, and is a number between 0 and 1.</span></span>  
  
 <span data-ttu-id="1fff4-113">**VARIA**</span><span class="sxs-lookup"><span data-stu-id="1fff4-113">**VARIANCE**</span></span>  
 <span data-ttu-id="1fff4-114">O valor na coluna é a variância do valor associado.</span><span class="sxs-lookup"><span data-stu-id="1fff4-114">The value in the column is the variance of the associated value.</span></span>  
  
 <span data-ttu-id="1fff4-115">**STDEV**</span><span class="sxs-lookup"><span data-stu-id="1fff4-115">**STDEV**</span></span>  
 <span data-ttu-id="1fff4-116">O valor na coluna é o desvio padrão do valor associado.</span><span class="sxs-lookup"><span data-stu-id="1fff4-116">The value in the column is the standard deviation of the associated value.</span></span>  
  
 <span data-ttu-id="1fff4-117">**PROBABILITY_VARIANCE**</span><span class="sxs-lookup"><span data-stu-id="1fff4-117">**PROBABILITY_VARIANCE**</span></span>  
 <span data-ttu-id="1fff4-118">O valor na coluna é a variância da probabilidade para o valor associado.</span><span class="sxs-lookup"><span data-stu-id="1fff4-118">The value in the column is the variance of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="1fff4-119">**PROBABILITY_STDEV**</span><span class="sxs-lookup"><span data-stu-id="1fff4-119">**PROBABILITY_STDEV**</span></span>  
 <span data-ttu-id="1fff4-120">O valor na coluna é o desvio padrão da probabilidade para o valor associado.</span><span class="sxs-lookup"><span data-stu-id="1fff4-120">The value in the column is the standard deviation of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="1fff4-121">**SUPPORT**</span><span class="sxs-lookup"><span data-stu-id="1fff4-121">**SUPPORT**</span></span>  
 <span data-ttu-id="1fff4-122">O valor na coluna é o peso ou o fator de replicação do caso do valor associado.</span><span class="sxs-lookup"><span data-stu-id="1fff4-122">The value in the column is the weight, or case replication factor, of the associated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fff4-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1fff4-123">See Also</span></span>  
 <span data-ttu-id="1fff4-124">[Tipos de conteúdo &#40;mineração de dados&#41;](content-types-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1fff4-124">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) </span></span>  
 <span data-ttu-id="1fff4-125">[Estruturas de mineração &#40;Analysis Services de mineração de dados&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1fff4-125">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="1fff4-126">Tipos de dados &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="1fff4-126">Data Types &#40;Data Mining&#41;</span></span>](data-types-data-mining.md)  
  
  
