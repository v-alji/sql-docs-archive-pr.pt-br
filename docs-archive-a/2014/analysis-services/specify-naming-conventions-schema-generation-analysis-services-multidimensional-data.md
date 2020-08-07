---
title: Especificar convenções de nomenclatura (Assistente de geração de esquema) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.namingconventions.f1
ms.assetid: 02d830ea-5b1f-4485-9f94-d64b8bea592b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e9588b49331934041cad888142d29d189fc1a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581503"
---
# <a name="specify-naming-conventions-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="63051-102">Especificar Convenções de Nomenclatura (Assistente de Geração de Esquema) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="63051-102">Specify Naming Conventions (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="63051-103">Use a página **Especificar Convenções de Nomenclatura** para definir as convenções de nomenclatura que o Assistente de Geração de Esquema usará ao criar objetos de esquema.</span><span class="sxs-lookup"><span data-stu-id="63051-103">Use the **Specify Naming Conventions** page to define the naming conventions that the Schema Generation Wizard uses when creating schema objects.</span></span>  
  
## <a name="options"></a><span data-ttu-id="63051-104">Opções</span><span class="sxs-lookup"><span data-stu-id="63051-104">Options</span></span>  
 <span data-ttu-id="63051-105">**Opção**</span><span class="sxs-lookup"><span data-stu-id="63051-105">**Option**</span></span>  
 <span data-ttu-id="63051-106">Especifique as convenções de nomenclatura para uso do assistente.</span><span class="sxs-lookup"><span data-stu-id="63051-106">Specify the naming conventions for the wizard to use.</span></span> <span data-ttu-id="63051-107">A tabela a seguir descreve as opções que podem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="63051-107">The following table describes the options you can specify.</span></span>  
  
|<span data-ttu-id="63051-108">Opção</span><span class="sxs-lookup"><span data-stu-id="63051-108">Option</span></span>|<span data-ttu-id="63051-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="63051-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="63051-110">**Separador**</span><span class="sxs-lookup"><span data-stu-id="63051-110">**Separator**</span></span>|<span data-ttu-id="63051-111">Especifica o caractere que separa palavras em um nome de objeto.</span><span class="sxs-lookup"><span data-stu-id="63051-111">Specifies the character that separates words in an object name.</span></span> <span data-ttu-id="63051-112">Na coluna **Valor** , selecione **Sublinhado**, **Espaço**ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="63051-112">In the **Value** column, select **Underscore**, **Space**, or **None**.</span></span> <span data-ttu-id="63051-113">O padrão é **Sublinhado**.</span><span class="sxs-lookup"><span data-stu-id="63051-113">The default is **Underscore**.</span></span>|  
|<span data-ttu-id="63051-114">**Prefixo da coluna de chave primária**</span><span class="sxs-lookup"><span data-stu-id="63051-114">**Primary key column prefix**</span></span>|<span data-ttu-id="63051-115">Especifica a cadeia de caracteres a ser usada como prefixo do nome de cada coluna de chave primária.</span><span class="sxs-lookup"><span data-stu-id="63051-115">Specifies the string to prefix the name of each primary key column.</span></span> <span data-ttu-id="63051-116">O padrão é **PK**.</span><span class="sxs-lookup"><span data-stu-id="63051-116">The default is **PK**.</span></span>|  
|<span data-ttu-id="63051-117">**Prefixo da coluna de chave estrangeira**</span><span class="sxs-lookup"><span data-stu-id="63051-117">**Foreign key column prefix**</span></span>|<span data-ttu-id="63051-118">Especifica a cadeia de caracteres a ser usada como prefixo do nome de cada coluna de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="63051-118">Specifies the string to prefix the name of each foreign key column.</span></span> <span data-ttu-id="63051-119">O padrão é **FK**.</span><span class="sxs-lookup"><span data-stu-id="63051-119">The default is **FK**.</span></span>|  
|<span data-ttu-id="63051-120">**Sufixo do nome de atributo**</span><span class="sxs-lookup"><span data-stu-id="63051-120">**Attribute name suffix**</span></span>|<span data-ttu-id="63051-121">Especifica a cadeia de caracteres a ser acrescentada ao nome de cada coluna de atributo.</span><span class="sxs-lookup"><span data-stu-id="63051-121">Specifies the string to be appended to the name of each attribute column.</span></span> <span data-ttu-id="63051-122">O padrão é **Nome**.</span><span class="sxs-lookup"><span data-stu-id="63051-122">The default is **Name**.</span></span>|  
|<span data-ttu-id="63051-123">**Sufixo de acúmulo personalizado**</span><span class="sxs-lookup"><span data-stu-id="63051-123">**Custom rollup suffix**</span></span>|<span data-ttu-id="63051-124">Especifica a cadeia de caracteres a ser acrescentada ao nome de cada coluna de acúmulo.</span><span class="sxs-lookup"><span data-stu-id="63051-124">Specifies the string to be appended to the name of each rollup column.</span></span> <span data-ttu-id="63051-125">O padrão é **CustomRollup**.</span><span class="sxs-lookup"><span data-stu-id="63051-125">The default is **CustomRollup**.</span></span>|  
|<span data-ttu-id="63051-126">**Sufixo de propriedades de acúmulo personalizado**</span><span class="sxs-lookup"><span data-stu-id="63051-126">**Custom rollup Properties suffix**</span></span>|<span data-ttu-id="63051-127">Especifica a cadeia de caracteres a ser acrescentada ao nome de cada coluna de propriedade de acúmulo.</span><span class="sxs-lookup"><span data-stu-id="63051-127">Specifies the string to be appended to the name of each rollup property column.</span></span> <span data-ttu-id="63051-128">O padrão é **CustomRollupProperties**.</span><span class="sxs-lookup"><span data-stu-id="63051-128">The default is **CustomRollupProperties**.</span></span>|  
|<span data-ttu-id="63051-129">**Sufixo de operador unário**</span><span class="sxs-lookup"><span data-stu-id="63051-129">**Unary operator suffix**</span></span>|<span data-ttu-id="63051-130">Especifica a cadeia de caracteres a ser acrescentada ao nome de cada coluna de operador unário.</span><span class="sxs-lookup"><span data-stu-id="63051-130">Specifies the string to be appended to the name of each unary operator column.</span></span> <span data-ttu-id="63051-131">O padrão é **UnaryOperator**.</span><span class="sxs-lookup"><span data-stu-id="63051-131">The default is **UnaryOperator**.</span></span>|  
  
 <span data-ttu-id="63051-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="63051-132">**Value**</span></span>  
 <span data-ttu-id="63051-133">Especifique um valor para a opção especificada em **Opção** a ser usado quando o esquema for gerado.</span><span class="sxs-lookup"><span data-stu-id="63051-133">Specify a value for the option specified in **Option** that you want to use when the schema is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63051-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63051-134">See Also</span></span>  
 <span data-ttu-id="63051-135">[Ajuda F1 do assistente de geração de esquema &#40;Analysis Services dados multidimensionais&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="63051-135">[Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="63051-136">Analysis Services assistentes &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="63051-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
