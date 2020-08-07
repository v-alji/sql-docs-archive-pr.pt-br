---
title: Transformação Divisão Condicional | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittrans.f1
helpviewer_keywords:
- Conditional Split transformation
- route rows to different outputs [Integration Services]
ms.assetid: 3f8b5825-226f-413c-ba8f-0bb931ca3770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96ff4b177992c329908ebc93df8f6220168e634d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575246"
---
# <a name="conditional-split-transformation"></a><span data-ttu-id="d811b-102">Transformação Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="d811b-102">Conditional Split Transformation</span></span>
  <span data-ttu-id="d811b-103">A transformação Divisão Condicional pode rotear linhas de dados para saídas diferentes, dependendo do conteúdo dos dados.</span><span class="sxs-lookup"><span data-stu-id="d811b-103">The Conditional Split transformation can route data rows to different outputs depending on the content of the data.</span></span> <span data-ttu-id="d811b-104">A implementação da transformação de divisão condicional é semelhante a uma estrutura de decisão CASE em uma linguagem de programação.</span><span class="sxs-lookup"><span data-stu-id="d811b-104">The implementation of the Conditional Split transformation is similar to a CASE decision structure in a programming language.</span></span> <span data-ttu-id="d811b-105">A transformação avalia expressões e, com base nos resultados, direciona a linha de dados para a saída especificada.</span><span class="sxs-lookup"><span data-stu-id="d811b-105">The transformation evaluates expressions, and based on the results, directs the data row to the specified output.</span></span> <span data-ttu-id="d811b-106">Essa transformação também fornece uma saída padrão, para que se uma linha não corresponder a nenhuma expressão ela seja direcionada para a saída padrão.</span><span class="sxs-lookup"><span data-stu-id="d811b-106">This transformation also provides a default output, so that if a row matches no expression it is directed to the default output.</span></span>  
  
## <a name="configuration-of-the-conditional-split-transformation"></a><span data-ttu-id="d811b-107">Configuração da transformação Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="d811b-107">Configuration of the Conditional Split Transformation</span></span>  
 <span data-ttu-id="d811b-108">É possível configurar a transformação Divisão Condicional do seguinte modo:</span><span class="sxs-lookup"><span data-stu-id="d811b-108">You can configure the Conditional Split transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="d811b-109">Para cada condição a ser testada pela transformação, forneça uma expressão a ser avaliada pelo Booleano.</span><span class="sxs-lookup"><span data-stu-id="d811b-109">Provide an expression that evaluates to a Boolean for each condition you want the transformation to test.</span></span>  
  
-   <span data-ttu-id="d811b-110">Especifique a ordem na qual as condições são avaliadas.</span><span class="sxs-lookup"><span data-stu-id="d811b-110">Specify the order in which the conditions are evaluated.</span></span> <span data-ttu-id="d811b-111">A ordem é importante, pois uma linha é enviada à saída correspondente para a primeira condição avaliada como true.</span><span class="sxs-lookup"><span data-stu-id="d811b-111">Order is significant, because a row is sent to the output corresponding to the first condition that evaluates to true.</span></span>  
  
-   <span data-ttu-id="d811b-112">Especifique a saída padrão para transformação.</span><span class="sxs-lookup"><span data-stu-id="d811b-112">Specify the default output for the transformation.</span></span> <span data-ttu-id="d811b-113">É necessário especificar uma saída padrão para a transformação.</span><span class="sxs-lookup"><span data-stu-id="d811b-113">The transformation requires that a default output be specified.</span></span>  
  
 <span data-ttu-id="d811b-114">Cada linha de entrada pode ser enviada a apenas uma saída, sendo esta saída a primeira condição avaliada como true.</span><span class="sxs-lookup"><span data-stu-id="d811b-114">Each input row can be sent to only one output, that being the output for the first condition that evaluates to true.</span></span> <span data-ttu-id="d811b-115">Por exemplo, as condições a seguir direcionam todas as linhas da coluna **FirstName** que começam com a letra *A* para uma saída, as linhas que começam com a letra *B* para uma saída diferente e todas as outras linhas para uma saída padrão.</span><span class="sxs-lookup"><span data-stu-id="d811b-115">For example, the following conditions direct any rows in the **FirstName** column that begin with the letter *A* to one output, rows that begin with the letter *B* to a different output, and all other rows to the default output.</span></span>  
  
 <span data-ttu-id="d811b-116">Saída 1</span><span class="sxs-lookup"><span data-stu-id="d811b-116">Output 1</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "A"`  
  
 <span data-ttu-id="d811b-117">Saída 2</span><span class="sxs-lookup"><span data-stu-id="d811b-117">Output 2</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "B"`  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="d811b-118">inclui funções e operadores que podem ser usados para criar as expressões que avaliam dados de entrada e direcionar dados de saída.</span><span class="sxs-lookup"><span data-stu-id="d811b-118">includes functions and operators that you can use to create the expressions that evaluate input data and direct output data.</span></span> <span data-ttu-id="d811b-119">Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d811b-119">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="d811b-120">A transformação Divisão Condicional inclui a propriedade personalizada `FriendlyExpression`.</span><span class="sxs-lookup"><span data-stu-id="d811b-120">The Conditional Split transformation includes the `FriendlyExpression` custom property.</span></span> <span data-ttu-id="d811b-121">Essa propriedade pode ser atualizada por uma expressão de propriedade quando o pacote é carregado.</span><span class="sxs-lookup"><span data-stu-id="d811b-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="d811b-122">Para obter mais informações, consulte [Usar expressões de propriedade em pacotes](../../expressions/use-property-expressions-in-packages.md) e [Propriedades personalizadas da transformação](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d811b-122">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="d811b-123">Esta transformação tem uma entrada, uma ou mais saídas e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="d811b-123">This transformation has one input, one or more outputs, and one error output.</span></span>  
  
 <span data-ttu-id="d811b-124">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="d811b-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d811b-125">Para obter mais informações sobre as propriedades que você quer definir na caixa de diálogo **Editor de Transformação Divisão Condicional** , consulte [Editor de Transformação Divisão Condicional](../../conditional-split-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="d811b-125">For more information about the properties that you can set in the **Conditional Split Transformation Editor** dialog box, see [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="d811b-126">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="d811b-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="d811b-127">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d811b-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d811b-128">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="d811b-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="d811b-129">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="d811b-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="d811b-130">Para obter mais informações sobre como definir propriedades, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d811b-130">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d811b-131">Dividir um conjunto de dados por meio da transformação Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="d811b-131">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
-   [<span data-ttu-id="d811b-132">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d811b-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="d811b-133">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d811b-133">Related Tasks</span></span>  
 [<span data-ttu-id="d811b-134">Dividir um conjunto de dados por meio da transformação Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="d811b-134">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
## <a name="see-also"></a><span data-ttu-id="d811b-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d811b-135">See Also</span></span>  
 <span data-ttu-id="d811b-136">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="d811b-136">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="d811b-137">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="d811b-137">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
