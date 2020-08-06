---
title: Tipos de dimensão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- time dimensions [Analysis Services]
- quantitative dimensions [Analysis Services]
- BillOfMaterials dimension [Analysis Services]
- geography dimensions
- utility dimensions [Analysis Services]
- channel dimensions
- dimensions [Analysis Services], types
- products dimensions [Analysis Services]
- account dimensions [Analysis Services]
- organization dimensions
- currency dimensions [Analysis Services]
- rates dimensions
- promotion dimensions
- scenario dimensions [Analysis Services]
- customers dimensions [Analysis Services]
- Type property
ms.assetid: bd3195da-e762-4c98-b643-34c76e842343
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5e0c16a57081aa1d9ed3cc6964d1f17fa7135986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583862"
---
# <a name="dimension-types"></a><span data-ttu-id="148fa-102">Tipos de dimensão</span><span class="sxs-lookup"><span data-stu-id="148fa-102">Dimension Types</span></span>
  <span data-ttu-id="148fa-103">A configuração da propriedade `Type` fornece informações sobre os conteúdos de uma dimensão para servidor e aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="148fa-103">The `Type` property setting provides information about the contents of a dimension to server and client applications.</span></span> <span data-ttu-id="148fa-104">Em alguns casos, a configuração `Type` fornece somente orientação para aplicativos cliente e é opcional.</span><span class="sxs-lookup"><span data-stu-id="148fa-104">In some cases, the `Type` setting only provides guidance for client applications and is optional.</span></span> <span data-ttu-id="148fa-105">Em outros casos, como as dimensões `Accounts` ou `Time`, as configurações de propriedade `Type` da dimensão e seus atributos determinam comportamentos específicos baseados em servidor e podem ser necessários para implantar determinados comportamentos no cubo.</span><span class="sxs-lookup"><span data-stu-id="148fa-105">In other cases, such as `Accounts` or `Time` dimensions, the `Type` property settings for the dimension and its attributes determine specific server-based behaviors and may be required to implement certain behaviors in the cube.</span></span> <span data-ttu-id="148fa-106">Por exemplo, a propriedade `Type` de uma dimensão pode ser configurada como `Accounts` para indicar a aplicativos cliente que a dimensão padrão contém atributos de conta.</span><span class="sxs-lookup"><span data-stu-id="148fa-106">For example, the `Type` property of a dimension can be set to `Accounts` to indicate to client applications that the standard dimension contains account attributes.</span></span> <span data-ttu-id="148fa-107">Para obter mais informações sobre dimensões de tempo, conta e moeda, consulte [criar uma dimensão de tipo de data](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [criar uma conta de finanças da dimensão de tipo pai-filho](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md)e [criar uma dimensão de tipo de moeda](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="148fa-107">For more information about time, account, and currency dimensions, see [Create a Date type Dimension](../multidimensional-models/database-dimensions-create-a-date-type-dimension.md), [Create a Finance Account of parent-child type Dimension](../multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md), and [Create a Currency type Dimension](../multidimensional-models/database-dimensions-create-a-currency-type-dimension.md).</span></span>  
  
 <span data-ttu-id="148fa-108">A configuração padrão para o tipo de dimensão é `Regular` que não faz nenhuma suposição sobre o conteúdo da dimensão.</span><span class="sxs-lookup"><span data-stu-id="148fa-108">The default setting for the dimension type is `Regular`, which makes no assumptions about the contents of the dimension.</span></span> <span data-ttu-id="148fa-109">Essa é a configuração padrão para todas as dimensões quando você define inicialmente uma dimensão a menos que você especifique`Time` ao definir a dimensão usando o Assistente de Dimensão.</span><span class="sxs-lookup"><span data-stu-id="148fa-109">This is the default setting for all dimensions when you initially define a dimension unless you specify `Time` when defining the dimension using the Dimension Wizard.</span></span> <span data-ttu-id="148fa-110">Você também deve deixar o `Regular` como o tipo de dimensão, se o Assistente de Dimensão não oferecer um tipo de dimensão apropriado.</span><span class="sxs-lookup"><span data-stu-id="148fa-110">You should also leave `Regular` as the dimension type if the Dimension Wizard does not list an appropriate type for Dimension type.</span></span>  
  
## <a name="available-dimension-types"></a><span data-ttu-id="148fa-111">Tipos de dimensão disponíveis</span><span class="sxs-lookup"><span data-stu-id="148fa-111">Available Dimension Types</span></span>  
 <span data-ttu-id="148fa-112">A tabela a seguir descreve os tipos de dimensão disponíveis no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="148fa-112">The following table describes the dimension types available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="148fa-113">Tipo de dimensão</span><span class="sxs-lookup"><span data-stu-id="148fa-113">Dimension type</span></span>|<span data-ttu-id="148fa-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="148fa-114">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="148fa-115">Regular</span><span class="sxs-lookup"><span data-stu-id="148fa-115">Regular</span></span>|<span data-ttu-id="148fa-116">Uma dimensão cujo tipo não foi definido como um tipo de dimensão especial.</span><span class="sxs-lookup"><span data-stu-id="148fa-116">A dimension whose type has not been set to a special dimension type.</span></span>|  
|<span data-ttu-id="148fa-117">Hora</span><span class="sxs-lookup"><span data-stu-id="148fa-117">Time</span></span>|<span data-ttu-id="148fa-118">Uma dimensão cujos atributos representam períodos, como anos, semestres, trimestres, meses e dias.</span><span class="sxs-lookup"><span data-stu-id="148fa-118">A dimension whose attributes represent time periods, such as years, semesters, quarters, months, and days.</span></span>|  
|<span data-ttu-id="148fa-119">Organização</span><span class="sxs-lookup"><span data-stu-id="148fa-119">Organization</span></span>|<span data-ttu-id="148fa-120">Uma dimensão cujos atributos representam informações organizacionais, como funcionários ou subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="148fa-120">A dimension whose attributes represent organizational information, such as employees or subsidiaries.</span></span>|  
|<span data-ttu-id="148fa-121">painel Geografia do app&#39;s selecionado</span><span class="sxs-lookup"><span data-stu-id="148fa-121">Geography</span></span>|<span data-ttu-id="148fa-122">Uma dimensão cujos atributos representam informações geográficas, como cidades ou códigos postais.</span><span class="sxs-lookup"><span data-stu-id="148fa-122">A dimension whose attributes represent geographic information, such as cities or postal codes.</span></span>|  
|<span data-ttu-id="148fa-123">BillOfMaterials</span><span class="sxs-lookup"><span data-stu-id="148fa-123">BillOfMaterials</span></span>|<span data-ttu-id="148fa-124">Uma dimensão cujos atributos representam informações de estoque ou manufatura, como listas de peças para produtos.</span><span class="sxs-lookup"><span data-stu-id="148fa-124">A dimension whose attributes represent inventory or manufacturing information, such as parts lists for products.</span></span>|  
|<span data-ttu-id="148fa-125">Contas</span><span class="sxs-lookup"><span data-stu-id="148fa-125">Accounts</span></span>|<span data-ttu-id="148fa-126">Uma dimensão cujos atributos representam um plano de contas para fins de geração de relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="148fa-126">A dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>|  
|<span data-ttu-id="148fa-127">Clientes</span><span class="sxs-lookup"><span data-stu-id="148fa-127">Customers</span></span>|<span data-ttu-id="148fa-128">Uma dimensão cujos atributos representam informações do cliente ou de contato.</span><span class="sxs-lookup"><span data-stu-id="148fa-128">A dimension whose attributes represent customer or contact information.</span></span>|  
|<span data-ttu-id="148fa-129">Produtos</span><span class="sxs-lookup"><span data-stu-id="148fa-129">Products</span></span>|<span data-ttu-id="148fa-130">Uma dimensão cujos atributos representam informações de produto.</span><span class="sxs-lookup"><span data-stu-id="148fa-130">A dimension whose attributes represent product information.</span></span>|  
|<span data-ttu-id="148fa-131">Cenário</span><span class="sxs-lookup"><span data-stu-id="148fa-131">Scenario</span></span>|<span data-ttu-id="148fa-132">Uma dimensão cujos atributos representam informações de planejamento ou de análise estratégica.</span><span class="sxs-lookup"><span data-stu-id="148fa-132">A dimension whose attributes represent planning or strategic analysis information.</span></span>|  
|<span data-ttu-id="148fa-133">Quantitative</span><span class="sxs-lookup"><span data-stu-id="148fa-133">Quantitative</span></span>|<span data-ttu-id="148fa-134">Uma dimensão cujos atributos representam informações quantitativas.</span><span class="sxs-lookup"><span data-stu-id="148fa-134">A dimension whose attributes represent quantitative information.</span></span>|  
|<span data-ttu-id="148fa-135">Utilitário</span><span class="sxs-lookup"><span data-stu-id="148fa-135">Utility</span></span>|<span data-ttu-id="148fa-136">Uma dimensão cujos atributos representam informações diversas.</span><span class="sxs-lookup"><span data-stu-id="148fa-136">A dimension whose attributes represent miscellaneous information.</span></span>|  
|<span data-ttu-id="148fa-137">Currency</span><span class="sxs-lookup"><span data-stu-id="148fa-137">Currency</span></span>|<span data-ttu-id="148fa-138">Este tipo de dimensão contém dados e metadados de moeda.</span><span class="sxs-lookup"><span data-stu-id="148fa-138">This type of dimension contains currency data and metadata.</span></span>|  
|<span data-ttu-id="148fa-139">Rates</span><span class="sxs-lookup"><span data-stu-id="148fa-139">Rates</span></span>|<span data-ttu-id="148fa-140">Uma dimensão cujos atributos representam informações de taxa de moeda.</span><span class="sxs-lookup"><span data-stu-id="148fa-140">A dimension whose attributes represent currency rate information.</span></span>|  
|<span data-ttu-id="148fa-141">Canal</span><span class="sxs-lookup"><span data-stu-id="148fa-141">Channel</span></span>|<span data-ttu-id="148fa-142">Uma dimensão cujos atributos representam informações de canal.</span><span class="sxs-lookup"><span data-stu-id="148fa-142">A dimension whose attributes represent channel information.</span></span>|  
|<span data-ttu-id="148fa-143">Promoção</span><span class="sxs-lookup"><span data-stu-id="148fa-143">Promotion</span></span>|<span data-ttu-id="148fa-144">Uma dimensão cujos atributos representam informações de promoções de marketing.</span><span class="sxs-lookup"><span data-stu-id="148fa-144">A dimension whose attributes represent marketing promotion information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="148fa-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="148fa-145">See Also</span></span>  
 <span data-ttu-id="148fa-146">[Criar uma dimensão usando uma tabela existente](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="148fa-146">[Create a Dimension by Using an Existing Table](../multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="148fa-147">Dimensões &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="148fa-147">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
