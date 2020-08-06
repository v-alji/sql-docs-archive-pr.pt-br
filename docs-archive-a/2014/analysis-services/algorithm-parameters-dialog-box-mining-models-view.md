---
title: Caixa de diálogo parâmetros de algoritmo (exibição de modelos de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.models.algorithmparameters.f1
helpviewer_keywords:
- Algorithm Parameters dialog box
ms.assetid: 57f9f6f8-8ca4-4a6e-8f18-85f0571b7060
author: minewiskan
ms.author: owend
ms.openlocfilehash: 303d8b5bd3437690c65873e106a94cf2ce8eb9f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571225"
---
# <a name="algorithm-parameters-dialog-box-mining-models-view"></a><span data-ttu-id="da6a0-102">Caixa de diálogo Parâmetros de Algoritmo (Exibição de Modelos de Mineração)</span><span class="sxs-lookup"><span data-stu-id="da6a0-102">Algorithm Parameters Dialog Box (Mining Models View)</span></span>
  <span data-ttu-id="da6a0-103">Use a caixa de diálogo **Parâmetros de Algoritmo** para ajustar os parâmetros de algoritmo que sejam específicos ao modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="da6a0-103">Use the **Algorithm Parameters** dialog box to adjust algorithm parameters that are specific to the selected model.</span></span> <span data-ttu-id="da6a0-104">A alteração de um parâmetro de algoritmo geralmente altera os resultados do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="da6a0-104">When you change an algorithm parameter, you will usually change the results of the mining model.</span></span> <span data-ttu-id="da6a0-105">O modo como cada parâmetro afeta os resultados, depende do algoritmo que está sendo usado e dos dados.</span><span class="sxs-lookup"><span data-stu-id="da6a0-105">The way that each parameter affects the results depends on the algorithm you are using, and on your data.</span></span> <span data-ttu-id="da6a0-106">Para obter mais informações, consulte [Personalizar os modelos de mineração e a estrutura](data-mining/customize-mining-models-and-structure.md).</span><span class="sxs-lookup"><span data-stu-id="da6a0-106">For more information, see [Customize Mining Models and Structure](data-mining/customize-mining-models-and-structure.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="da6a0-107">Opções</span><span class="sxs-lookup"><span data-stu-id="da6a0-107">Options</span></span>  
 <span data-ttu-id="da6a0-108">**Parâmetros**</span><span class="sxs-lookup"><span data-stu-id="da6a0-108">**Parameters**</span></span>  
 <span data-ttu-id="da6a0-109">Lista os parâmetros disponíveis para o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="da6a0-109">Lists the parameters that are available for the selected mining model.</span></span>  
  
 <span data-ttu-id="da6a0-110">A lista a seguir descreve as colunas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="da6a0-110">The following list describes the available columns.</span></span>  
  
|<span data-ttu-id="da6a0-111">Column</span><span class="sxs-lookup"><span data-stu-id="da6a0-111">Column</span></span>|<span data-ttu-id="da6a0-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="da6a0-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="da6a0-113">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="da6a0-113">**Parameter**</span></span>|<span data-ttu-id="da6a0-114">Liste o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="da6a0-114">List the name of the parameter.</span></span>|  
|<span data-ttu-id="da6a0-115">**Valor**</span><span class="sxs-lookup"><span data-stu-id="da6a0-115">**Value**</span></span>|<span data-ttu-id="da6a0-116">Digite um valor somente se desejar alterar o valor padrão do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="da6a0-116">Enter a value only if you want to change the default value of the parameter.</span></span>|  
|<span data-ttu-id="da6a0-117">**Default**</span><span class="sxs-lookup"><span data-stu-id="da6a0-117">**Default**</span></span>|<span data-ttu-id="da6a0-118">Liste um valor padrão do parâmetro que o algoritmo utilizará caso você não forneça um valor na coluna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="da6a0-118">List the default value of the parameter that the algorithm will use if you do not supply a value in the **Value** column.</span></span>|  
|<span data-ttu-id="da6a0-119">**Range**</span><span class="sxs-lookup"><span data-stu-id="da6a0-119">**Range**</span></span>|<span data-ttu-id="da6a0-120">Liste o intervalo de possíveis valores que se pode digitar na coluna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="da6a0-120">List the range of possible values that you can enter into the **Value** column.</span></span> <span data-ttu-id="da6a0-121">Os intervalos podem ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="da6a0-121">The ranges can be one of the following:</span></span><br /><br /> <span data-ttu-id="da6a0-122">Uma lista discreta, como 1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="da6a0-122">A discrete list, such as 1, 2, 3</span></span><br /><br /> <span data-ttu-id="da6a0-123">Um intervalo inclusivo, como [0, 100]</span><span class="sxs-lookup"><span data-stu-id="da6a0-123">An inclusive range, such as [0, 100]</span></span><br /><br /> <span data-ttu-id="da6a0-124">Um intervalo exclusivo, como (0,...)</span><span class="sxs-lookup"><span data-stu-id="da6a0-124">An exclusive range, such as (0,...)</span></span><br /><br /> <span data-ttu-id="da6a0-125">Uma combinação, como [0,...)</span><span class="sxs-lookup"><span data-stu-id="da6a0-125">A combination, such as [0,...)</span></span>|  
  
 <span data-ttu-id="da6a0-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="da6a0-126">**Description**</span></span>  
 <span data-ttu-id="da6a0-127">Descreve o parâmetro selecionado na lista **Parâmetros** .</span><span class="sxs-lookup"><span data-stu-id="da6a0-127">Describes the selected parameter in the **Parameters** list.</span></span>  
  
 <span data-ttu-id="da6a0-128">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="da6a0-128">**Add**</span></span>  
 <span data-ttu-id="da6a0-129">Clique para adicionar à lista os parâmetros específicos ao algoritmo complementar.</span><span class="sxs-lookup"><span data-stu-id="da6a0-129">Click to add additional, algorithm specific-parameters to the list.</span></span> <span data-ttu-id="da6a0-130">Após adicionar o parâmetro, você pode digitar o nome correto na coluna **Parâmetro** e fornecer um valor na coluna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="da6a0-130">After adding the parameter, you can enter the correct name in the **Parameter** column and provide a value in the **Value** column.</span></span>  
  
 <span data-ttu-id="da6a0-131">**Remover**</span><span class="sxs-lookup"><span data-stu-id="da6a0-131">**Remove**</span></span>  
 <span data-ttu-id="da6a0-132">Clique para excluir um parâmetro personalizado da lista.</span><span class="sxs-lookup"><span data-stu-id="da6a0-132">Click to delete a custom parameter from the list.</span></span>  
  
 <span data-ttu-id="da6a0-133">Se você excluir da lista um dos parâmetros de algoritmo do Analysis Services padrão, o parâmetro ainda será usado no modelo, mas com os valores padrão daquele parâmetro.</span><span class="sxs-lookup"><span data-stu-id="da6a0-133">If you delete one of the standard Analysis Services algorithm parameters from the list, the parameter will still be used in the model, but with the default values for that parameter.</span></span> <span data-ttu-id="da6a0-134">O parâmetro não é excluído permanentemente e aparecerá da próxima vez que você abrir a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="da6a0-134">The parameter is not permanently deleted and will appear the next time that you open the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da6a0-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da6a0-135">See Also</span></span>  
 <span data-ttu-id="da6a0-136">[Algoritmos de mineração de dados &#40;mineração de dados Analysis Services&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="da6a0-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="da6a0-137">[Exibição de modelos de mineração &#40;designer de modelo de mineração de dados&#41;](mining-models-view-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="da6a0-137">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="da6a0-138">Movendo objetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="da6a0-138">Moving Data Mining Objects</span></span>](data-mining/moving-data-mining-objects.md)  
  
  
