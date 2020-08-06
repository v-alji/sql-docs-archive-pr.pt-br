---
title: Definir fórmulas de membro personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- members [Analysis Services], custom
- custom rollup formulas [Analysis Services]
- MDX [Analysis Services], custom rollup formulas
- custom member formulas [Analysis Services]
ms.assetid: 258304e2-d900-4013-97e3-871f51dfdce2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51649bea0c4134971b342b779c778b857343e62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685367"
---
# <a name="define-custom-member-formulas"></a><span data-ttu-id="95375-102">Definir fórmulas de membro personalizado</span><span class="sxs-lookup"><span data-stu-id="95375-102">Define Custom Member Formulas</span></span>
  <span data-ttu-id="95375-103">É possível definir uma expressão multidimensional (MDX), chamada fórmula de membro personalizado, para fornecer os valores aos membros de um atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="95375-103">You can define a Multidimensional Expressions (MDX) expression, called a custom member formula, to supply the values for the members of a specified attribute.</span></span> <span data-ttu-id="95375-104">Uma coluna em uma tabela da exibição da fonte de dados fornece, para cada membro de um atributo, a expressão usada para fornecer o valor para esse membro.</span><span class="sxs-lookup"><span data-stu-id="95375-104">A column in a table from a data source view provides, for each member in an attribute, the expression used to supply the value for that member.</span></span>  
  
 <span data-ttu-id="95375-105">As fórmulas de membro personalizado determinam os valores de células associados aos membros e substituem as funções de agregação de medidas.</span><span class="sxs-lookup"><span data-stu-id="95375-105">Custom member formulas determine the cell values that are associated with members and override the aggregate functions of measures.</span></span> <span data-ttu-id="95375-106">Fórmulas de membro personalizado são escritas no formato MDX.</span><span class="sxs-lookup"><span data-stu-id="95375-106">Custom member formulas are written in MDX.</span></span> <span data-ttu-id="95375-107">Cada fórmula de membro personalizado é válida para um único membro.</span><span class="sxs-lookup"><span data-stu-id="95375-107">Each custom member formula applies to a single member.</span></span> <span data-ttu-id="95375-108">As fórmulas de membro personalizado são armazenadas na tabela de dimensões ou em outra tabela que tenha uma relação de chave estrangeira com a tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="95375-108">Custom member formulas are stored in the dimension table or in another table that has a foreign key relationship with the dimension table.</span></span>  
  
 <span data-ttu-id="95375-109">A propriedade `CustomRollupColumn` de um atributo especifica a coluna que contém fórmulas de membro personalizado para os membros do atributo.</span><span class="sxs-lookup"><span data-stu-id="95375-109">The `CustomRollupColumn` property on an attribute specifies the column that contains custom member formulas for members of the attribute.</span></span> <span data-ttu-id="95375-110">Se uma linha da coluna estiver vazia, o valor de célula do membro será retornado normalmente.</span><span class="sxs-lookup"><span data-stu-id="95375-110">If a row in the column is empty, the cell value for the member is returned normally.</span></span> <span data-ttu-id="95375-111">Se a fórmula da coluna não for válida, ocorrerá um erro de tempo de execução sempre que o valor de uma célula que usa o membro for recuperado.</span><span class="sxs-lookup"><span data-stu-id="95375-111">If the formula in the column is not valid, a run-time error occurs whenever a cell value that uses the member is retrieved.</span></span>  
  
 <span data-ttu-id="95375-112">Antes de poder especificar fórmulas de membro personalizado para um atributo, confirme se a tabela de dimensões contém o atributo, ou uma tabela diretamente relacionada, possui uma coluna de cadeia de caracteres para armazenar as fórmulas de membro personalizado.</span><span class="sxs-lookup"><span data-stu-id="95375-112">Before you can specify custom member formulas for an attribute, make sure that the dimension table that contains the attribute, or a directly related table, has a string column to store the custom member formulas.</span></span> <span data-ttu-id="95375-113">Se esse for o caso, você poderá definir a `CustomRollupColumn` propriedade em um atributo manualmente ou usar o aprimoramento de definir fórmula de membro personalizado do assistente de Business Intelligence para habilitar uma fórmula de membro personalizado em um atributo.</span><span class="sxs-lookup"><span data-stu-id="95375-113">If this is the case, you can either set the `CustomRollupColumn` property on an attribute manually or use the Set Custom Member Formula enhancement of the Business Intelligence Wizard to enable a custom member formula on an attribute.</span></span> <span data-ttu-id="95375-114">Para obter mais informações sobre como usar essa melhoria, consulte [Definir fórmulas de membro personalizado para os atributos de uma dimensão](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="95375-114">For more information about how to use this enhancement, see [Set Custom Member Formulas for Attributes in a Dimension](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span></span>  
  
## <a name="evaluating-custom-member-formulas"></a><span data-ttu-id="95375-115">Avaliando fórmulas de membro personalizado</span><span class="sxs-lookup"><span data-stu-id="95375-115">Evaluating Custom Member Formulas</span></span>  
 <span data-ttu-id="95375-116">Fórmulas de membro personalizado são diferentes de membros calculados.</span><span class="sxs-lookup"><span data-stu-id="95375-116">Custom member formulas differ from calculated members.</span></span> <span data-ttu-id="95375-117">As fórmulas de membro personalizado aplicam-se a membros que existem em tabelas de dimensões e fornecem apenas o valor do membro.</span><span class="sxs-lookup"><span data-stu-id="95375-117">Custom member formulas apply to members that exist in dimension tables, and only provide the value of the member.</span></span> <span data-ttu-id="95375-118">Diferentemente, os membros calculados não são armazenados em tabelas de dimensões e as expressões de membros calculados definem os dados e os metadados para membros adicionais incluídos em uma dimensão ou hierarquia.</span><span class="sxs-lookup"><span data-stu-id="95375-118">In contrast, calculated members are not stored in dimension tables, and calculated member expressions define both data and metadata for additional members included in a dimension or hierarchy.</span></span>  
  
 <span data-ttu-id="95375-119">Fórmulas de membro personalizado substituem as funções de agregação associadas às medidas.</span><span class="sxs-lookup"><span data-stu-id="95375-119">Custom member formulas override the aggregate functions associated with measures.</span></span> <span data-ttu-id="95375-120">Por exemplo, antes que uma fórmula de membro personalizado seja especificada, uma medida que usa a função de agregação `Sum` possuirá os valores a seguir para os seguintes membros da dimensão Tempo:</span><span class="sxs-lookup"><span data-stu-id="95375-120">For example, before a custom member formula is specified, a measure using the `Sum` aggregate function has the following values for the following members of the Time dimension:</span></span>  
  
-   <span data-ttu-id="95375-121">2003: 2100</span><span class="sxs-lookup"><span data-stu-id="95375-121">2003: 2100</span></span>  
  
    -   <span data-ttu-id="95375-122">Trimestre 1: 700</span><span class="sxs-lookup"><span data-stu-id="95375-122">Quarter 1: 700</span></span>  
  
    -   <span data-ttu-id="95375-123">Trimestre 2: 500</span><span class="sxs-lookup"><span data-stu-id="95375-123">Quarter 2: 500</span></span>  
  
    -   <span data-ttu-id="95375-124">Trimestre 3: 100</span><span class="sxs-lookup"><span data-stu-id="95375-124">Quarter 3: 100</span></span>  
  
    -   <span data-ttu-id="95375-125">Trimestre 4: 800</span><span class="sxs-lookup"><span data-stu-id="95375-125">Quarter 4: 800</span></span>  
  
-   <span data-ttu-id="95375-126">2004: 1500</span><span class="sxs-lookup"><span data-stu-id="95375-126">2004: 1500</span></span>  
  
    -   <span data-ttu-id="95375-127">Trimestre 1: 600</span><span class="sxs-lookup"><span data-stu-id="95375-127">Quarter 1: 600</span></span>  
  
    -   <span data-ttu-id="95375-128">Trimestre 2: 200</span><span class="sxs-lookup"><span data-stu-id="95375-128">Quarter 2: 200</span></span>  
  
    -   <span data-ttu-id="95375-129">Trimestre 3: 300</span><span class="sxs-lookup"><span data-stu-id="95375-129">Quarter 3: 300</span></span>  
  
    -   <span data-ttu-id="95375-130">Trimestre 4: 400</span><span class="sxs-lookup"><span data-stu-id="95375-130">Quarter 4: 400</span></span>  
  
 <span data-ttu-id="95375-131">Com uma fórmula de membro personalizado, o valor do membro é fornecido pela fórmula de acúmulo personalizado.</span><span class="sxs-lookup"><span data-stu-id="95375-131">With a custom member formula, the value of the member is instead supplied by the custom rollup formula.</span></span> <span data-ttu-id="95375-132">Por exemplo, a fórmula de membro personalizado a seguir pode ser usada para fornecer o valor de 450 para o membro filho Trimestre 4 do membro 2004 da dimensão Tempo.</span><span class="sxs-lookup"><span data-stu-id="95375-132">For example, the following custom member formula can be used to supply the value for the Quarter 4 child member of the 2004 member in the Time dimension as 450.</span></span>  
  
```  
Time.[Quarter 3] * 1.5  
```  
  
 <span data-ttu-id="95375-133">As fórmulas de membro personalizado são armazenadas em uma coluna da tabela de dimensões.</span><span class="sxs-lookup"><span data-stu-id="95375-133">Custom member formulas are stored in a column of the dimension table.</span></span> <span data-ttu-id="95375-134">Habilite fórmulas de acúmulo personalizado configurando a propriedade `CustomRollupColumn` de um atributo.</span><span class="sxs-lookup"><span data-stu-id="95375-134">You enable custom rollup formulas by setting the `CustomRollupColumn` property on an attribute.</span></span>  
  
 <span data-ttu-id="95375-135">Para aplicar a mesma expressão MDX a todos os membros de um atributo, crie um cálculo nomeado na tabela de dimensões que retorne uma expressão MDX como cadeia de caracteres literal.</span><span class="sxs-lookup"><span data-stu-id="95375-135">To apply a single MDX expression to all members of an attribute, create a named calculation on the dimension table that returns an MDX expression as a literal string.</span></span> <span data-ttu-id="95375-136">Em seguida, especifique o cálculo nomeado configurando a propriedade `CustomRollupColumn` no atributo que você quer configurar.</span><span class="sxs-lookup"><span data-stu-id="95375-136">Then, specify the named calculation with the `CustomRollupColumn` property setting on the attribute that you want to configure.</span></span> <span data-ttu-id="95375-137">Um cálculo nomeado é uma coluna da tabela de exibição da fonte de dados que retorna os valores de linha definidos por uma expressão SQL.</span><span class="sxs-lookup"><span data-stu-id="95375-137">A named calculation is a column in a data source view table that returns row values defined by a SQL expression.</span></span> <span data-ttu-id="95375-138">Para obter mais informações sobre como construir cálculos nomeados, consulte [Definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="95375-138">For more information about constructing named calculations, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95375-139">Para aplicar uma expressão MDX aos membros de um determinado nível e não aos membros de todos os níveis com base em um atributo em particular, defina a expressão como um script MDX no nível.</span><span class="sxs-lookup"><span data-stu-id="95375-139">To apply an MDX expression to members of a particular level instead of to members of all levels based on a particular attribute, you can define the expression as an MDX script on the level.</span></span> <span data-ttu-id="95375-140">Para obter mais informações, consulte [Conceitos básicos do script MDX &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="95375-140">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
 <span data-ttu-id="95375-141">Se você usar membros calculados e fórmulas de acúmulo personalizado para os membros de um atributo, não deixe de ordenar a avaliação.</span><span class="sxs-lookup"><span data-stu-id="95375-141">If you use both calculated members and custom rollup formulas for members of an attribute, you should be aware of the order of evaluation.</span></span> <span data-ttu-id="95375-142">Membros calculados são resolvidos antes das fórmulas de acúmulo personalizado.</span><span class="sxs-lookup"><span data-stu-id="95375-142">Calculated members are resolved before custom rollup formulas are resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95375-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95375-143">See Also</span></span>  
 <span data-ttu-id="95375-144">[Atributos e hierarquias de atributo](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="95375-144">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 [<span data-ttu-id="95375-145">Definir fórmulas de membro personalizado para os atributos de uma dimensão</span><span class="sxs-lookup"><span data-stu-id="95375-145">Set Custom Member Formulas for Attributes in a Dimension</span></span>](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md)  
  
  
