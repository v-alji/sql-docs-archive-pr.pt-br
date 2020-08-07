---
title: Preparando dados para exibição em uma região de dados Tablix (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fbb00dc6-7887-480c-b771-cab6fecb8dcc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 72ac150f2dcd227b1e3afb624a5ca5866fb4c360
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582300"
---
# <a name="preparing-data-for-display-in-a-tablix-data-region-report-builder-and-ssrs"></a><span data-ttu-id="cc0b6-102">Preparando dados para exibição em uma região de dados Tablix (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="cc0b6-102">Preparing Data for Display in a Tablix Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cc0b6-103">Uma região de dados tablix exibe dados de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-103">A tablix data region displays data from a dataset.</span></span> <span data-ttu-id="cc0b6-104">É possível exibir todos os dados recuperados do conjunto de dados ou criar filtros para exibir apenas um subconjunto dos dados.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-104">You can view all the data retrieved for the dataset or you can create filters so that you see only a subset of the data.</span></span> <span data-ttu-id="cc0b6-105">Você também pode adicionar expressões condicionais para preencher valores nulos ou modificar a consulta de um conjunto de dados para incluir colunas que identificam a ordem de classificação de uma coluna existente.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-105">You can also add conditional expressions to fill in null values or modify the query for a dataset to include columns that define the sort order for an existing column.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="working-with-nulls-and-blanks-in-field-values"></a><span data-ttu-id="cc0b6-106">Trabalhando com nulos e espaços em branco em valores de campo</span><span class="sxs-lookup"><span data-stu-id="cc0b6-106">Working with Nulls and Blanks in Field Values</span></span>  
 <span data-ttu-id="cc0b6-107">Entre os dados da coleção de campos em um conjunto de dados estão todos os valores recuperados da fonte de dados em tempo de execução, inclusive valores nulos e espaços em branco.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-107">Data for the field collection in a dataset includes all values retrieved from the data source at run time, including null values and blanks.</span></span> <span data-ttu-id="cc0b6-108">Valores nulos e espaços em branco costumam ser indistinguíveis.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-108">Normally null values and blanks are indistinguishable.</span></span> <span data-ttu-id="cc0b6-109">Na maioria dos casos, trata-se do comportamento desejado.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-109">In most cases, this is the desired behavior.</span></span> <span data-ttu-id="cc0b6-110">Por exemplo, funções de agregação numéricas como [Sum](report-builder-functions-sum-function.md) e [Avg](report-builder-functions-avg-function.md) ignoram valores nulos.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-110">For example, Numeric aggregate functions like [Sum](report-builder-functions-sum-function.md) and [Avg](report-builder-functions-avg-function.md) ignore null values.</span></span> <span data-ttu-id="cc0b6-111">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="cc0b6-111">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
 <span data-ttu-id="cc0b6-112">Caso você queira tratar valores nulos de maneira diferente, é possível usar expressões condicionais ou o código personalizado para substituir um valor personalizado do valor nulo.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-112">If you do want to handle null values differently, you can use conditional expressions or custom code to substitute a custom value for the null value.</span></span> <span data-ttu-id="cc0b6-113">Por exemplo, a seguinte expressão substitui o texto `Null` independentemente de onde o valor nulo ocorra no campo `[Size]`.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-113">For example, the following expression substitutes the text `Null` wherever a null value occurs in the field `[Size]`.</span></span>  
  
```  
=IIF(Fields!Size.Value IS NOTHING,"Null",Fields!Size.Value)  
```  
  
 <span data-ttu-id="cc0b6-114">Para obter mais informações sobre como eliminar nulos dos dados antes de recuperá-los por meio de uma fonte de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o uso de consultas do [!INCLUDE[tsql](../../includes/tsql-md.md)] , consulte "Valores nulos" e "Valores nulos e junções" na documentação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nos [Manuais Online do SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="cc0b6-114">For more information about eliminating nulls in your data before retrieving the data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source using [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, see "Null Values" and "Null Values and Joins" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
## <a name="handling-null-field-names"></a><span data-ttu-id="cc0b6-115">Tratando nomes de campo nulos</span><span class="sxs-lookup"><span data-stu-id="cc0b6-115">Handling Null Field Names</span></span>  
 <span data-ttu-id="cc0b6-116">Não há problemas em testar valores nulos em uma expressão contanto que o próprio campo esteja no conjunto de resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-116">Testing for null values in an expression is fine as long as the field itself exists in the query result set.</span></span> <span data-ttu-id="cc0b6-117">Usando código personalizado, é possível testar se o próprio campo está presente nos campos da coleção retornados da fonte de dados em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-117">From custom code, you can test whether the field itself is present in the collection fields returned from the data source at run time.</span></span> <span data-ttu-id="cc0b6-118">Para obter mais informações, consulte [Referências de coleções de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="cc0b6-118">For more information, see [Dataset Fields Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span></span>  
  
## <a name="adding-a-sort-order-column"></a><span data-ttu-id="cc0b6-119">Adicionando uma coluna de ordem de classificação</span><span class="sxs-lookup"><span data-stu-id="cc0b6-119">Adding a Sort Order Column</span></span>  
 <span data-ttu-id="cc0b6-120">Por padrão, é possível classificar valores de um campo de conjunto de dados por ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-120">By default, you can alphabetically sort values in a dataset field.</span></span> <span data-ttu-id="cc0b6-121">Para classificar em uma ordem diferente, é possível adicionar uma nova coluna ao conjunto de dados que define a ordem de classificação desejada em uma região de dados.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-121">To sort in a different order, you can add a new column to your dataset that defines the sort order you want in a data region.</span></span> <span data-ttu-id="cc0b6-122">Por exemplo, para classificar o campo `[Color]` e os itens branco e preto primeiro, é possível adicionar uma coluna `[ColorSortOrder]`, mostrada na seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="cc0b6-122">For example, to sort on the field `[Color]` and sort white and black items first, you can add a column `[ColorSortOrder]`, shown in the following query:</span></span>  
  
```  
SELECT ProductID, p.Name, Color,  
   CASE  
      WHEN p.Color = 'White' THEN 1  
      WHEN p.Color = 'Black' THEN 2  
      WHEN p.Color = 'Blue' THEN 3  
      WHEN p.Color = 'Yellow' THEN 4  
      ELSE 5  
   END As ColorSortOrder  
FROM Production.Product p  
```  
  
 <span data-ttu-id="cc0b6-123">Para classificar uma região de dados de tabela de acordo com essa ordem de classificação, defina a expressão de classificação no grupo detalhado como `=Fields!ColorSortOrder.Value`.</span><span class="sxs-lookup"><span data-stu-id="cc0b6-123">To sort a table data region according to this sort order, set the sort expression on the detail group to `=Fields!ColorSortOrder.Value`.</span></span> <span data-ttu-id="cc0b6-124">Para obter mais informações, consulte [Classificar dados em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cc0b6-124">For more information, see [Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0b6-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc0b6-125">See Also</span></span>  
 <span data-ttu-id="cc0b6-126">[Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cc0b6-126">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cc0b6-127">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cc0b6-127">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="cc0b6-128">Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cc0b6-128">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
