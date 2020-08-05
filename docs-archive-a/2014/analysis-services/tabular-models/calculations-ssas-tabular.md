---
title: Cálculos (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 738816e3-0e1d-44a5-8d1b-81068dce8ac0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2da86ae5c5652c8b2614cae4bbb721802700d973
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572717"
---
# <a name="calculations-ssas-tabular"></a><span data-ttu-id="d6764-102">Cálculos (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="d6764-102">Calculations (SSAS Tabular)</span></span>
  <span data-ttu-id="d6764-103">Depois de importar dados para o modelo, será possível adicionar cálculos para agregar, filtrar, estender, combinar e proteger esses dados.</span><span class="sxs-lookup"><span data-stu-id="d6764-103">After you have imported data into your model, you can add calculations to aggregate, filter, extend, combine, and secure that data.</span></span> <span data-ttu-id="d6764-104">Os modelos tabulares usam o DAX (Data Analysis Expressions), uma linguagem de fórmula para criar cálculos personalizados.</span><span class="sxs-lookup"><span data-stu-id="d6764-104">Tabular models use Data Analysis Expressions (DAX), a formula language for creating custom calculations.</span></span> <span data-ttu-id="d6764-105">Nos modelos de tabela, os cálculos que você cria usando fórmulas DAX são usados em *Colunas Calculadas*, *Medidas*e *Filtros de Linha*.</span><span class="sxs-lookup"><span data-stu-id="d6764-105">In tabular models, the calculations you create by using DAX formulas are used in *Calculated Columns*, *Measures*, and *Row Filters*.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6764-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d6764-106">In This Section</span></span>  
  
|<span data-ttu-id="d6764-107">Tópico</span><span class="sxs-lookup"><span data-stu-id="d6764-107">Topic</span></span>|<span data-ttu-id="d6764-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="d6764-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d6764-109">Noções básicas sobre DAX em modelos de tabela &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="d6764-109">Understanding DAX in Tabular Models &#40;SSAS Tabular&#41;</span></span>](understanding-dax-in-tabular-models-ssas-tabular.md)|<span data-ttu-id="d6764-110">Descreve a linguagem de fórmula DAX usada para criar cálculos para colunas calculadas, medidas e filtros de linha em modelos de tabela.</span><span class="sxs-lookup"><span data-stu-id="d6764-110">Describes the Data Analysis Expressions (DAX) formula language used to create calculations for calculated columns, measures, and row filters in tabular models.</span></span>|  
|[<span data-ttu-id="d6764-111">Compatibilidade de fórmulas no modo DirectQuery</span><span class="sxs-lookup"><span data-stu-id="d6764-111">Formula Compatibility in DirectQuery Mode</span></span>](../dax-formula-compatibility-in-directquery-mode-ssas-2014.md)|<span data-ttu-id="d6764-112">Descreve as diferenças, lista as funções que não têm suporte no modo DirectQuery e lista as funções com suporte, mas que poderiam retornar resultados diferentes.</span><span class="sxs-lookup"><span data-stu-id="d6764-112">Describes the differences, lists the functions that are not supported in DirectQuery mode, and lists the functions that are supported but could return different results.</span></span>|  
|[<span data-ttu-id="d6764-113">Expressões de análise de dados &#40;referência de&#41; DAX</span><span class="sxs-lookup"><span data-stu-id="d6764-113">Data Analysis Expressions &#40;DAX&#41; Reference</span></span>](/dax/data-analysis-expressions-dax-reference)|<span data-ttu-id="d6764-114">Esta seção fornece descrições detalhadas de sintaxe DAX, operadores e funções.</span><span class="sxs-lookup"><span data-stu-id="d6764-114">This section provides detailed descriptions of DAX syntax, operators, and functions.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="d6764-115">Esta seção não contém tarefas passo a passo para criar cálculos.</span><span class="sxs-lookup"><span data-stu-id="d6764-115">Step-by-step tasks for creating calculations are not provided in this section.</span></span> <span data-ttu-id="d6764-116">Como os cálculos são especificados em colunas calculadas, medidas e filtros de linha (em funções), as instruções sobre onde criar fórmulas DAX são fornecidas em tarefas relacionadas a esses recursos.</span><span class="sxs-lookup"><span data-stu-id="d6764-116">Because calculations are specified in calculated columns, measures, and row filters (in roles), instructions on where to create DAX formulas are provided in tasks related to those features.</span></span> <span data-ttu-id="d6764-117">Para obter mais informações, consulte [Criar uma coluna calculada &#40;SSAS de Tabela&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Criar e gerenciar medidas &#40;SSAS de Tabela&#41;](measures-ssas-tabular.md) e [Criar e gerenciar funções &#40;SSAS de Tabela&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d6764-117">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md), and [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6764-118">Apesar de o DAX também poder ser usado para consultar um modelo de tabela, tópicos desta seção destacam especificamente o uso de fórmulas DAX para criar cálculos.</span><span class="sxs-lookup"><span data-stu-id="d6764-118">While DAX can also be used to query a tabular model, topics in this section focus specifically on using DAX formulas to create calculations.</span></span>  
  
  
