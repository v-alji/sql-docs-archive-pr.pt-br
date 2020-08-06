---
title: Criar uma dimensão de tipo de moeda | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], currency
- currency [Analysis Services]
- converting currency
- currency dimensions [Analysis Services]
ms.assetid: b1f037d1-ce47-4e47-a1c2-5ec9e781cff6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91123fb5fda898e90056057114295335fbd1d32c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680114"
---
# <a name="create-a-currency-type-dimension"></a><span data-ttu-id="f0295-102">Criar uma dimensão de tipo de moeda</span><span class="sxs-lookup"><span data-stu-id="f0295-102">Create a Currency type Dimension</span></span>
  <span data-ttu-id="f0295-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , uma dimensão de tipo de moeda é uma dimensão cujos atributos representam uma lista de moedas para fins de relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="f0295-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a currency type dimension is a dimension whose attributes represent a list of currencies for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="f0295-104">Uma dimensão de moeda permite a inclusão de recursos de conversão de moeda em um cubo do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0295-104">A currency dimension lets you add currency conversion capabilities to a cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="f0295-105">Para adicionar a conversão de moeda a um cubo, use o Assistente de Business Intelligence para definir um comando de script MDX que converte medidas monetárias nos valores apropriados para a localidade do aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="f0295-105">To add currency conversion to a cube, you use the Business Intelligence Wizard define a Multidimensional Expressions (MDX) script command that converts currency measures to values that are appropriate for the locale of the client application.</span></span> <span data-ttu-id="f0295-106">Para criar esse script MDX, o Assistente de Business Intelligence precisa das seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="f0295-106">To create this MDX script, the Business Intelligence Wizard needs the following information:</span></span>  
  
-   <span data-ttu-id="f0295-107">Uma dimensão de moeda que representa as moedas de origem.</span><span class="sxs-lookup"><span data-stu-id="f0295-107">A currency dimension that represents source currencies.</span></span> <span data-ttu-id="f0295-108">(Essa dimensão é a dimensão de moeda de origem.)</span><span class="sxs-lookup"><span data-stu-id="f0295-108">(This dimension is the source currency dimension.)</span></span>  
  
-   <span data-ttu-id="f0295-109">Um grupo de medidas que representa as taxas de câmbio que serão usadas.</span><span class="sxs-lookup"><span data-stu-id="f0295-109">A measure group that represents the exchange rates that will be used.</span></span>  
  
 <span data-ttu-id="f0295-110">Com essas informações, o Assistente de Business Intelligence criará o processo de conversão de moedas que identificará a dimensão da moeda de destino apropriada (a dimensão de moeda que representa as moedas de destino).</span><span class="sxs-lookup"><span data-stu-id="f0295-110">From this information, the Business Intelligence Wizard will design a currency conversion process that identifies the appropriate destination currency dimension (the currency dimension that represents destination currencies).</span></span> <span data-ttu-id="f0295-111">Dependendo do número de conversões de moeda que a solução de business intelligence precisar, o Assistente de Business Intelligence pode definir várias dimensões de moeda de destino.</span><span class="sxs-lookup"><span data-stu-id="f0295-111">Depending on the number of currency conversions that your business intelligence solution requires, the Business Intelligence Wizard can define multiple destination currency dimensions.</span></span> <span data-ttu-id="f0295-112">Para obter mais informações sobre como definir conversões de moeda, consulte [Conversões de moeda &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="f0295-112">For more information about defining currency conversions, see [Currency Conversions &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span></span>  
  
 <span data-ttu-id="f0295-113">Para identificar uma dimensão como dimensão de moeda, defina a propriedade `Type` da dimensão como `Currency`.</span><span class="sxs-lookup"><span data-stu-id="f0295-113">To identify a dimension as a currency dimension, set the `Type` property of the dimension to `Currency`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="f0295-114">Estrutura da Dimensão</span><span class="sxs-lookup"><span data-stu-id="f0295-114">Dimension Structure</span></span>  
 <span data-ttu-id="f0295-115">Uma dimensão de moeda contém, no mínimo, um atributo de chave que identifica cada moeda da tabela de dimensões da dimensão de moeda.</span><span class="sxs-lookup"><span data-stu-id="f0295-115">A currency dimension contains, at least, a key attribute identifying individual currencies in the dimension table for the currency dimension.</span></span> <span data-ttu-id="f0295-116">O valor do atributo de chave é diferente nas dimensões de moeda de origem e destino:</span><span class="sxs-lookup"><span data-stu-id="f0295-116">The value of the key attribute is different in both source and destination currency dimensions:</span></span>  
  
-   <span data-ttu-id="f0295-117">Para identificar um atributo como atributo de chave de uma dimensão de moeda de origem, defina a propriedade `Type` do atributo como `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="f0295-117">To identify an attribute as the key attribute of a source currency dimension, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="f0295-118">Para identificar um atributo como dimensão da moeda de destino, defina a propriedade `Type` do atributo como `CurrencyDestination`.</span><span class="sxs-lookup"><span data-stu-id="f0295-118">To identify an attribute as the destination currency dimension, set the `Type` property of the attribute to `CurrencyDestination`.</span></span>  
  
 <span data-ttu-id="f0295-119">Para geração de relatório, tanto a dimensão de moeda de origem como a de destino podem conter, opcionalmente, os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="f0295-119">For reporting purposes, both source and destination currency dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="f0295-120">Um atributo de nome da moeda.</span><span class="sxs-lookup"><span data-stu-id="f0295-120">A currency name attribute.</span></span>  
  
     <span data-ttu-id="f0295-121">Para identificar um atributo como nome da moeda, defina a propriedade `Type` do atributo como `CurrencyName`.</span><span class="sxs-lookup"><span data-stu-id="f0295-121">To identify an attribute as a currency name attribute, set the `Type` property of the attribute to `CurrencyName`.</span></span>  
  
-   <span data-ttu-id="f0295-122">Um atributo de origem da moeda.</span><span class="sxs-lookup"><span data-stu-id="f0295-122">A currency source attribute.</span></span>  
  
     <span data-ttu-id="f0295-123">Para identificar um atributo como atributo de origem da moeda, defina a propriedade `Type` do atributo como `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="f0295-123">To identify an attribute as a currency source attribute, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="f0295-124">Um código de moeda da Organização de Padronização Internacional (ISO).</span><span class="sxs-lookup"><span data-stu-id="f0295-124">A currency International Standards Organization (ISO) code.</span></span>  
  
     <span data-ttu-id="f0295-125">Para identificar um atributo como atributo de código ISO da moeda, defina a propriedade `Type` do atributo como `CurrencyIsoCode`.</span><span class="sxs-lookup"><span data-stu-id="f0295-125">To identify an attribute as a currency ISO code attribute, set the `Type` property of the attribute to `CurrencyIsoCode`.</span></span>  
  
 <span data-ttu-id="f0295-126">Para obter mais informações sobre tipos de atributos, consulte [Configurar tipos de atributo](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="f0295-126">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="f0295-127">Definindo inteligência de conta com o Assistente de Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="f0295-127">Defining Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="f0295-128">Depois de configurar a dimensão de conta e adicioná-la a um cubo, você pode usar o Assistente de Business Intelligence para adicionar à dimensão funcionalidades de inteligência de conta, como identificação e mapeamento de tipos de conta.</span><span class="sxs-lookup"><span data-stu-id="f0295-128">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to add account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="f0295-129">Para obter mais informações, consulte [Adicionar inteligência de conta a uma dimensão](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="f0295-129">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0295-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f0295-130">See Also</span></span>  
 <span data-ttu-id="f0295-131">[Atributos e hierarquias de atributo](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="f0295-131">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="f0295-132">[Ajuda F1 do assistente de Business Intelligence](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="f0295-132">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="f0295-133">Tipos de dimensão</span><span class="sxs-lookup"><span data-stu-id="f0295-133">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
