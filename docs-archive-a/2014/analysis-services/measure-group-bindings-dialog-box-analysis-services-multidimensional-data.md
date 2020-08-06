---
title: Caixa de diálogo associações de grupo de medidas (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.dimensionusage.definerelationship.measuregroupbindings.f1
helpviewer_keywords:
- Measure Group Bindings dialog box
ms.assetid: ed642780-5350-438e-af73-b9ceab3f876d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 78693901a5898b140d6efeed16b6f0eaa7577e69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685378"
---
# <a name="measure-group-bindings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="54549-102">Caixa de diálogo Associações de Grupos de Medidas (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="54549-102">Measure Group Bindings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="54549-103">Use a caixa de diálogo **Associações de Grupos de Medidas** para criar e modificar relações diretas entre atributos de não granularidade em uma dimensão de cubo e colunas em um grupo de medidas para uma relação de dimensão normal, bem como para especificar opções de processamento nulo para qualquer atributo em uma dimensão de cubo na caixa de diálogo **Definir Relação** .</span><span class="sxs-lookup"><span data-stu-id="54549-103">Use the **Measure Group Bindings** dialog box to create and modify direct relationships between non-granularity attributes in a cube dimension and columns in a measure group for a regular dimension relationship, as well as to specify null processing options for any attribute in a cube dimension, from the **Define Relationship** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="54549-104">Opções</span><span class="sxs-lookup"><span data-stu-id="54549-104">Options</span></span>  
 <span data-ttu-id="54549-105">**Tabela de grupos de medidas**</span><span class="sxs-lookup"><span data-stu-id="54549-105">**Measure group table**</span></span>  
 <span data-ttu-id="54549-106">Exibe o nome da tabela de fatos do grupo de medidas selecionado.</span><span class="sxs-lookup"><span data-stu-id="54549-106">Displays the name of the fact table for the selected measure group.</span></span>  
  
 <span data-ttu-id="54549-107">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="54549-107">**Attributes**</span></span>  
 <span data-ttu-id="54549-108">Exibe uma grade de atributos e tabelas de dimensões.</span><span class="sxs-lookup"><span data-stu-id="54549-108">Displays a grid of attributes and dimension tables.</span></span> <span data-ttu-id="54549-109">Selecione um atributo para criar ou modificar propriedades em **Relação** para o atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="54549-109">Select an attribute to create or modify properties in **Relationship** for the selected attribute.</span></span> <span data-ttu-id="54549-110">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="54549-110">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="54549-111">Opção</span><span class="sxs-lookup"><span data-stu-id="54549-111">Option</span></span>|<span data-ttu-id="54549-112">Definição</span><span class="sxs-lookup"><span data-stu-id="54549-112">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="54549-113">**Nome do atributo**</span><span class="sxs-lookup"><span data-stu-id="54549-113">**Attribute Name**</span></span>|<span data-ttu-id="54549-114">Exibe o nome do atributo.</span><span class="sxs-lookup"><span data-stu-id="54549-114">Displays the name of the attribute.</span></span>|  
|<span data-ttu-id="54549-115">**Tabela de Dimensão**</span><span class="sxs-lookup"><span data-stu-id="54549-115">**Dimension Table**</span></span>|<span data-ttu-id="54549-116">Exibe o nome da tabela de dimensões na qual o atributo é baseado.</span><span class="sxs-lookup"><span data-stu-id="54549-116">Displays the name of the dimension table on which the attribute is based.</span></span>|  
  
 <span data-ttu-id="54549-117">**Relação**</span><span class="sxs-lookup"><span data-stu-id="54549-117">**Relationship**</span></span>  
 <span data-ttu-id="54549-118">Exibe uma grade de relações entre colunas da tabela de dimensões para o atributo selecionado e as colunas da tabela de fatos para o grupo de medidas selecionado, bem como a opção de processamento nulo da relação.</span><span class="sxs-lookup"><span data-stu-id="54549-118">Displays a grid of relationships between dimension table columns for the selected attribute and fact table columns for the selected measure group as well as the null processing option for the relationship.</span></span> <span data-ttu-id="54549-119">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="54549-119">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="54549-120">Opção</span><span class="sxs-lookup"><span data-stu-id="54549-120">Option</span></span>|<span data-ttu-id="54549-121">Definição</span><span class="sxs-lookup"><span data-stu-id="54549-121">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="54549-122">**Colunas de Dimensão**</span><span class="sxs-lookup"><span data-stu-id="54549-122">**Dimension Columns**</span></span>|<span data-ttu-id="54549-123">Exibe as colunas da tabela de dimensões na qual o atributo selecionado em **Atributos** é baseado.</span><span class="sxs-lookup"><span data-stu-id="54549-123">Displays the columns from the dimension table on which the attribute selected in **Attributes** is based.</span></span>|  
|<span data-ttu-id="54549-124">**Colunas de Grupos de Medidas**</span><span class="sxs-lookup"><span data-stu-id="54549-124">**Measure Group Columns**</span></span>|<span data-ttu-id="54549-125">Selecione a opção **Herdado da dimensão** para usar a relação do grupo de medidas herdada da dimensão ou selecione uma coluna da tabela de fatos na qual o grupo de medidas é baseado para definir uma relação explicitamente.</span><span class="sxs-lookup"><span data-stu-id="54549-125">Select either **Inherited from dimension** to use the measure group relationship inherited from the dimension, or select a column from the fact table on which the measure group is based to explicitly define a relationship.</span></span>|  
|<span data-ttu-id="54549-126">**Processamento Nulo**</span><span class="sxs-lookup"><span data-stu-id="54549-126">**Null Processing**</span></span>|<span data-ttu-id="54549-127">Selecione uma opção de processamento nulo para o atributo.</span><span class="sxs-lookup"><span data-stu-id="54549-127">Select a null processing option for the attribute.</span></span> <span data-ttu-id="54549-128">Para obter mais informações sobre as opções de processamento nulo, consulte [Elemento NullProcessing &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span><span class="sxs-lookup"><span data-stu-id="54549-128">For more information about null processing options, see [NullProcessing Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54549-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54549-129">See Also</span></span>  
 <span data-ttu-id="54549-130">[Caixa de diálogo Definir relação &#40;Analysis Services-dados multidimensionais&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="54549-130">[Define Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="54549-131">Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="54549-131">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
