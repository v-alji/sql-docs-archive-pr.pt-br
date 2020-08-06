---
title: Especificar chave e tipo de dimensão (Assistente para dimensões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionkeyandtype.f1
ms.assetid: d7d5db55-36c3-45f6-ade3-29aa516589c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc08584ed12de8597b8289fd223cc47945d7d087
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581510"
---
# <a name="specify-dimension-key-and-type-dimension-wizard"></a><span data-ttu-id="496dc-102">Especificar Chave e Tipo de Dimensão (Assistente para Dimensões)</span><span class="sxs-lookup"><span data-stu-id="496dc-102">Specify Dimension Key and Type (Dimension Wizard)</span></span>
  <span data-ttu-id="496dc-103">Use a página **Especificar Chave e Tipo de Dimensão** para definir o atributo de chave da dimensão e indicar se a dimensão é uma SCD (dimensão de alteração lenta).</span><span class="sxs-lookup"><span data-stu-id="496dc-103">Use the **Specify Dimension Key and Type** page to define the key attribute of the dimension and to indicate whether the dimension is a slowly changing dimension (SCD).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="496dc-104">Essa página será exibida apenas se você tiver selecionado **Criar a dimensão sem usar uma fonte de dados** na página **Selecionar Método de Criação** e **Dimensão padrão** na página **Selecionar o Tipo de Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="496dc-104">This page is displayed only if you selected **Build the dimension without using a data source** on the **Select Build Method** page and if you selected **Standard dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="496dc-105">Opções</span><span class="sxs-lookup"><span data-stu-id="496dc-105">Options</span></span>  
 <span data-ttu-id="496dc-106">**Atributo de chave**</span><span class="sxs-lookup"><span data-stu-id="496dc-106">**Key attribute**</span></span>  
 <span data-ttu-id="496dc-107">Selecione o atributo que será o atributo de chave da dimensão.</span><span class="sxs-lookup"><span data-stu-id="496dc-107">Select the attribute that will be the key attribute for the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="496dc-108">Se nenhum atributo tiver sido definido para a dimensão, o único valor disponível para essa opção será **Criar atributo de chave automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="496dc-108">If no attributes have been defined for the dimension, the only value available for this option is **Create key attribute automatically.**</span></span> <span data-ttu-id="496dc-109">Esse valor não estará disponível se qualquer atributo estiver definido para a dimensão.</span><span class="sxs-lookup"><span data-stu-id="496dc-109">This value is not available if any attributes are defined for the dimension.</span></span>  
  
 <span data-ttu-id="496dc-110">**Esta é uma dimensão variável**</span><span class="sxs-lookup"><span data-stu-id="496dc-110">**This is a changing dimension**</span></span>  
 <span data-ttu-id="496dc-111">Selecione para indicar que a dimensão é uma dimensão de alteração lenta.</span><span class="sxs-lookup"><span data-stu-id="496dc-111">Select to indicate that the dimension is a slowly changing dimension.</span></span> <span data-ttu-id="496dc-112">A seleção dessa opção criará colunas e atributos adicionais que podem ser usados para acompanhar o movimento de membros dentro das hierarquias da dimensão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="496dc-112">Selecting this option will create additional columns and attributes that can be used to track the movement of members within the hierarchies of the dimension over time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="496dc-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="496dc-113">See Also</span></span>  
 <span data-ttu-id="496dc-114">[Ajuda F1 do assistente para dimensões](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="496dc-114">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="496dc-115">[Dimensões &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="496dc-115">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="496dc-116">Dimensões em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="496dc-116">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
