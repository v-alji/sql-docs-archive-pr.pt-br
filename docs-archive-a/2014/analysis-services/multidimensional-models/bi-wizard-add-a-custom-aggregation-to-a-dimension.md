---
title: Adicionar uma agregação personalizada a uma dimensão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], custom aggregations
- aggregations [Analysis Services], custom
- unary operators
- custom aggregations [Analysis Services]
ms.assetid: 3199a6c2-a06d-47b9-bd1c-604dbb085318
author: minewiskan
ms.author: owend
ms.openlocfilehash: ed843b8b0005ff62f05b13ebd20024d528857388
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569703"
---
# <a name="add-a-custom-aggregation-to-a-dimension"></a><span data-ttu-id="e3775-102">Adicionar uma agregação personalizada a uma dimensão</span><span class="sxs-lookup"><span data-stu-id="e3775-102">Add a Custom Aggregation to a Dimension</span></span>
  <span data-ttu-id="e3775-103">Adicione um aprimoramento de agregação personalizada a um cubo ou dimensão para substituir as agregações padrão associadas a um membro da dimensão por outro operador unário.</span><span class="sxs-lookup"><span data-stu-id="e3775-103">Add a custom aggregation enhancement to a cube or dimension to replace the default aggregations that are associated with a dimension member with a different unary operator.</span></span> <span data-ttu-id="e3775-104">Esse aprimoramento especifica uma coluna de operador unário na tabela de dimensões que define o acúmulo de membros em uma hierarquia pai-filho.</span><span class="sxs-lookup"><span data-stu-id="e3775-104">This enhancement specifies a unary operator column in the dimension table that defines rollup for members in a parent-child hierarchy.</span></span> <span data-ttu-id="e3775-105">O operador unário age no atributo pai em uma hierarquia pai-filho.</span><span class="sxs-lookup"><span data-stu-id="e3775-105">The unary operator acts on the parent attribute in a parent-child hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3775-106">Uma agregação personalizada estará disponível somente para dimensões baseadas em fontes de dados existentes.</span><span class="sxs-lookup"><span data-stu-id="e3775-106">A custom aggregation is available only for dimensions that are based on existing data sources.</span></span> <span data-ttu-id="e3775-107">Para dimensões que foram criadas sem usar uma fonte de dados, execute o Assistente de Geração de Esquema para criar uma exibição da fonte de dados antes de adicionar a agregação personalizada.</span><span class="sxs-lookup"><span data-stu-id="e3775-107">For dimensions that were created without using a data source, you must run the Schema Generation Wizard to create a data source view before adding the custom aggregation.</span></span>  
  
 <span data-ttu-id="e3775-108">Para adicionar uma agregação personalizada, use o Assistente de Business Intelligence e selecione a opção **Especificar um operador unário** na página **Escolher Aprimoramento** .</span><span class="sxs-lookup"><span data-stu-id="e3775-108">To add a custom aggregation, you use the Business Intelligence Wizard, and select the **Specify a unary operator** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="e3775-109">Esse assistente orientará você durante as etapas para selecionar a dimensão à qual você deseja aplicar uma agregação personalizada e para identificar a agregação personalizada.</span><span class="sxs-lookup"><span data-stu-id="e3775-109">This wizard then guides you through the steps of selecting a dimension to which you want to apply a custom aggregation and identifying the custom aggregation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3775-110">Antes de executar o Assistente de Business Intelligence para adicionar uma agregação personalizada, confirme se a dimensão que você deseja aprimorar contém uma hierarquia de atributo pai-filho.</span><span class="sxs-lookup"><span data-stu-id="e3775-110">Before you run the Business Intelligence Wizard to add a custom aggregation, make sure that the dimension that you want to enhance contains a parent-child attribute hierarchy.</span></span> <span data-ttu-id="e3775-111">Para obter mais informações, consulte [hierarquia pai-filho](parent-child-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="e3775-111">For more information, see [Parent-Child Hierarchy](parent-child-dimension.md).</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="e3775-112">Selecionando uma dimensão</span><span class="sxs-lookup"><span data-stu-id="e3775-112">Selecting a Dimension</span></span>  
 <span data-ttu-id="e3775-113">Na primeira página **Especificar um Operador Unário** do assistente, especifique a dimensão à qual você deseja aplicar uma agregação personalizada.</span><span class="sxs-lookup"><span data-stu-id="e3775-113">On the first **Specify a Unary Operator** page of the wizard, you specify the dimension to which you want to apply a custom aggregation.</span></span> <span data-ttu-id="e3775-114">A agregação personalizada adicionada à dimensão selecionada fará alterações na dimensão.</span><span class="sxs-lookup"><span data-stu-id="e3775-114">The custom aggregation added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="e3775-115">Essas alterações serão herdadas por todos os cubos que tiverem a dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="e3775-115">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="adding-custom-aggregation-unary-operator"></a><span data-ttu-id="e3775-116">Adicionando agregação personalizada (operador unário)</span><span class="sxs-lookup"><span data-stu-id="e3775-116">Adding Custom Aggregation (Unary Operator)</span></span>  
 <span data-ttu-id="e3775-117">Na segunda página **Especificar um Operador Unário** do assistente, especifique o atributo pai desejado para a agregação personalizada e a coluna de origem da tabela de dimensões para o operador unário.</span><span class="sxs-lookup"><span data-stu-id="e3775-117">On the second **Specify a Unary Operator** page, you specify the parent attribute that you want for the custom aggregation and the source column in the dimension table for the unary operator.</span></span> <span data-ttu-id="e3775-118">O **atributo pai** lista os atributos que têm sua `Usage` propriedade definida como `Parent` .</span><span class="sxs-lookup"><span data-stu-id="e3775-118">**Parent attribute** lists attributes that have their `Usage` property set to `Parent`.</span></span> <span data-ttu-id="e3775-119">Se houver mais de um atributo pai, escolha o atributo pai que corresponde à relação pai-filho que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="e3775-119">If there is more than one parent attribute, choose the parent attribute that corresponds to the parent-child relationship that you want to use.</span></span> <span data-ttu-id="e3775-120">Se não houver um atributo pai listado, a dimensão não possui uma hierarquia pai-filho válida.</span><span class="sxs-lookup"><span data-stu-id="e3775-120">If there is no parent attribute listed, then the dimension does not have a valid parent-child hierarchy.</span></span>  
  
 <span data-ttu-id="e3775-121">Em **Coluna de origem**, selecione a coluna de cadeia de caracteres que contém os operadores unários.</span><span class="sxs-lookup"><span data-stu-id="e3775-121">In **Source column**, you select the string column that contains the unary operators.</span></span> <span data-ttu-id="e3775-122">(Essa seleção define a `UnaryOperatorColumn` propriedade no atributo pai.) A tabela de dimensões também deve ter uma coluna de cadeia de caracteres que especifica o operador de rollup unário.</span><span class="sxs-lookup"><span data-stu-id="e3775-122">(This selection sets the `UnaryOperatorColumn` property on the parent attribute.) The dimension table should also have a string column that specifies the unary rollup operator.</span></span> <span data-ttu-id="e3775-123">Os valores da cadeia de caracteres dessa coluna devem conter operadores de agregação válidos.</span><span class="sxs-lookup"><span data-stu-id="e3775-123">The string values in this column should contain valid aggregation operators.</span></span> <span data-ttu-id="e3775-124">Se houver uma linha vazia, o membro correspondente será calculado normalmente.</span><span class="sxs-lookup"><span data-stu-id="e3775-124">If a row is empty, the corresponding member is calculated normally.</span></span> <span data-ttu-id="e3775-125">Se a fórmula de uma coluna não for válida, ocorrerá um erro de tempo de execução quando o valor de uma célula que usa o membro for recuperado.</span><span class="sxs-lookup"><span data-stu-id="e3775-125">If the formula in a column is not valid, a run-time error occurs when a cell value that uses the member is retrieved.</span></span> <span data-ttu-id="e3775-126">Para obter mais informações, consulte [Operadores unários nas dimensões pai-filho](parent-child-dimension-attributes-unary-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e3775-126">For more information, see [Unary Operators in Parent-Child Dimensions](parent-child-dimension-attributes-unary-operators.md).</span></span>  
  
  