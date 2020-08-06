---
title: Filtros geralmente usados (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- multivalued parameters [Reporting Services]
- single-valued parameters [Reporting Services]
- parameters [Reporting Services], multivalued
- valid values [Reporting Services]
ms.assetid: cb70d0cd-707b-4de5-b39f-e4eb57d316aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 201cf83d431d1b61e0f20e9d039b2016ad4f13e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574501"
---
# <a name="commonly-used-filters-report-builder-and-ssrs"></a><span data-ttu-id="c5214-102">Filtros comumente usados (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c5214-102">Commonly Used Filters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c5214-103">Para criar um filtro, é necessário especificar uma ou mais equações de filtro.</span><span class="sxs-lookup"><span data-stu-id="c5214-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="c5214-104">As equações de filtro incluem uma expressão, um tipo de dados, um operador e um valor.</span><span class="sxs-lookup"><span data-stu-id="c5214-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="c5214-105">Este tópico traz exemplos de filtros que são utilizados com frequência.</span><span class="sxs-lookup"><span data-stu-id="c5214-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="c5214-106">Exemplos de filtro</span><span class="sxs-lookup"><span data-stu-id="c5214-106">Filter Examples</span></span>  
 <span data-ttu-id="c5214-107">A tabela a seguir mostra exemplo de equações de filtro que usam diferentes tipos de dados e operadores.</span><span class="sxs-lookup"><span data-stu-id="c5214-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="c5214-108">O escopo da comparação é determinado pelo item de relatório para o qual é definido um filtro.</span><span class="sxs-lookup"><span data-stu-id="c5214-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="c5214-109">Por exemplo, no caso de um filtro definido em um conjunto de dados, **TOP % 10** representa os principais 10% de valores do conjunto de dados; no caso de um filtro definido em um grupo, **TOP % 10** são os principais 10% de valores do grupo.</span><span class="sxs-lookup"><span data-stu-id="c5214-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="c5214-110">Expressão simples</span><span class="sxs-lookup"><span data-stu-id="c5214-110">Simple Expression</span></span>|<span data-ttu-id="c5214-111">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="c5214-111">Data Type</span></span>|<span data-ttu-id="c5214-112">Operador</span><span class="sxs-lookup"><span data-stu-id="c5214-112">Operator</span></span>|<span data-ttu-id="c5214-113">Valor</span><span class="sxs-lookup"><span data-stu-id="c5214-113">Value</span></span>|<span data-ttu-id="c5214-114">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c5214-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="c5214-115">Inclui valores de dados maiores que 7.</span><span class="sxs-lookup"><span data-stu-id="c5214-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="c5214-116">Inclui os 10 principais valores de dados.</span><span class="sxs-lookup"><span data-stu-id="c5214-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="c5214-117">Inclui os principais 20% de valores de dados.</span><span class="sxs-lookup"><span data-stu-id="c5214-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="c5214-118">Inclui todos os valores do tipo System.Decimal (tipos de dados “money” do SQL) maiores que $100.</span><span class="sxs-lookup"><span data-stu-id="c5214-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2088-01-01`|<span data-ttu-id="c5214-119">Inclui todas as datas, desde 1º de janeiro de 2008 até a presente data.</span><span class="sxs-lookup"><span data-stu-id="c5214-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="c5214-120">Inclui as datas de 1o. de janeiro de 2008 até, e incluindo, 1º de fevereiro de 2008.</span><span class="sxs-lookup"><span data-stu-id="c5214-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="c5214-121">Todos os nomes de território que terminam com "leste".</span><span class="sxs-lookup"><span data-stu-id="c5214-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="c5214-122">Todos os nomes de território que incluem Norte e Sul no início do nome.</span><span class="sxs-lookup"><span data-stu-id="c5214-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="c5214-123">Todos os valores de subcategorias que começam com as letras B, C ou T.</span><span class="sxs-lookup"><span data-stu-id="c5214-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="examples-with-report-parameters"></a><span data-ttu-id="c5214-124">Exemplos com parâmetros de relatório</span><span class="sxs-lookup"><span data-stu-id="c5214-124">Examples with Report Parameters</span></span>  
 <span data-ttu-id="c5214-125">A tabela a seguir contém exemplos de expressão de filtro que inclui uma referência de parâmetro de um só valor ou multivalor.</span><span class="sxs-lookup"><span data-stu-id="c5214-125">The following table provides examples of filter expression that includes a single-value or multivalue parameter reference.</span></span>  
  
|<span data-ttu-id="c5214-126">Tipo de parâmetro</span><span class="sxs-lookup"><span data-stu-id="c5214-126">Parameter type</span></span>|<span data-ttu-id="c5214-127">Expressão (filtro)</span><span class="sxs-lookup"><span data-stu-id="c5214-127">(Filter) Expression</span></span>|<span data-ttu-id="c5214-128">Operador</span><span class="sxs-lookup"><span data-stu-id="c5214-128">Operator</span></span>|<span data-ttu-id="c5214-129">Valor</span><span class="sxs-lookup"><span data-stu-id="c5214-129">Value</span></span>|<span data-ttu-id="c5214-130">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="c5214-130">Data Type</span></span>|  
|--------------------|---------------------------|--------------|-----------|---------------|  
|<span data-ttu-id="c5214-131">Um único valor</span><span class="sxs-lookup"><span data-stu-id="c5214-131">Single value</span></span>|`[EmployeeID]`|=|`[@EmployeeID]`|<span data-ttu-id="c5214-132">Integer</span><span class="sxs-lookup"><span data-stu-id="c5214-132">Integer</span></span>|  
|<span data-ttu-id="c5214-133">Multivalor</span><span class="sxs-lookup"><span data-stu-id="c5214-133">Multivalue</span></span>|`[EmployeeID]`|<span data-ttu-id="c5214-134">IN</span><span class="sxs-lookup"><span data-stu-id="c5214-134">IN</span></span>|`[@EmployeeID]`|<span data-ttu-id="c5214-135">Integer</span><span class="sxs-lookup"><span data-stu-id="c5214-135">Integer</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5214-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5214-136">See Also</span></span>  
 <span data-ttu-id="c5214-137">[Parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="c5214-137">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="c5214-138">[Adicionar filtros de conjunto de dados, filtros de região e filtros de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="c5214-138">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="c5214-139">[Usos de expressão em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c5214-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c5214-140">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c5214-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c5214-141">Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c5214-141">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
