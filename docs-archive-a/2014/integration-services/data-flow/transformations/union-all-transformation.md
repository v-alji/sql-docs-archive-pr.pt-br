---
title: Transformação Unir Tudo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 942e4b90-9c41-4e9c-a6f3-80b3afe57f2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eaaab1abf2587979e947cc1be24cbedf8f61b6e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582032"
---
# <a name="union-all-transformation"></a><span data-ttu-id="605fd-102">transformação Unir Tudo</span><span class="sxs-lookup"><span data-stu-id="605fd-102">Union All Transformation</span></span>
  <span data-ttu-id="605fd-103">A transformação Union All combina várias entradas em apenas uma saída.</span><span class="sxs-lookup"><span data-stu-id="605fd-103">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="605fd-104">Por exemplo, as saídas provenientes de cinco origens de Arquivo Simples diferentes podem ser aplicadas à transformação Unir Tudo e combinadas em apenas uma saída.</span><span class="sxs-lookup"><span data-stu-id="605fd-104">For example, the outputs from five different Flat File sources can be inputs to the Union All transformation and combined into one output.</span></span>  
  
## <a name="inputs-and-outputs"></a><span data-ttu-id="605fd-105">Entradas e saídas</span><span class="sxs-lookup"><span data-stu-id="605fd-105">Inputs and Outputs</span></span>  
 <span data-ttu-id="605fd-106">As entradas da transformação são adicionadas à saída da transformação uma após a outra, sem reordenação das linhas.</span><span class="sxs-lookup"><span data-stu-id="605fd-106">The transformation inputs are added to the transformation output one after the other; no reordering of rows occurs.</span></span> <span data-ttu-id="605fd-107">Se o pacote requerer uma saída ordenada, você deve usar a transformação Merge em vez da Union All.</span><span class="sxs-lookup"><span data-stu-id="605fd-107">If the package requires a sorted output, you should use the Merge transformation instead of the Union All transformation.</span></span>  
  
 <span data-ttu-id="605fd-108">A primeira entrada que você conectar à transformação Union All será a entrada da qual a transformação criará a saída.</span><span class="sxs-lookup"><span data-stu-id="605fd-108">The first input that you connect to the Union All transformation is the input from which the transformation creates the transformation output.</span></span> <span data-ttu-id="605fd-109">As colunas nas entradas que você conectar subsequentemente à transformação serão mapeadas para as colunas, na saída da transformação.</span><span class="sxs-lookup"><span data-stu-id="605fd-109">The columns in the inputs you subsequently connect to the transformation are mapped to the columns in the transformation output.</span></span>  
  
 <span data-ttu-id="605fd-110">Para mesclar as entradas, você deve mapear as colunas nas entradas para as colunas na saída.</span><span class="sxs-lookup"><span data-stu-id="605fd-110">To merge inputs, you map columns in the inputs to columns in the output.</span></span> <span data-ttu-id="605fd-111">Uma coluna com pelo menos uma entrada deve ser mapeada para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="605fd-111">A column from at least one input must be mapped to each output column.</span></span> <span data-ttu-id="605fd-112">O mapeamento entre duas colunas requer que seus metadados tenham correspondência.</span><span class="sxs-lookup"><span data-stu-id="605fd-112">The mapping between two columns requires that the metadata of the columns match.</span></span> <span data-ttu-id="605fd-113">Por exemplo, as colunas mapeadas devem ter o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="605fd-113">For example, the mapped columns must have the same data type.</span></span>  
  
 <span data-ttu-id="605fd-114">Se as colunas mapeadas contiverem dados de cadeia de caracteres e a coluna de saída for mais curta que a de entrada, a coluna da saída será aumentada automaticamente para comportar a coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="605fd-114">If the mapped columns contain string data and the output column is shorter in length than the input column, the output column is automatically increased in length to contain the input column.</span></span> <span data-ttu-id="605fd-115">As colunas de entrada que não forem mapeadas para as de saída serão definidas com valores nulos nas colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="605fd-115">Input columns that are not mapped to output columns are set to null values in the output columns.</span></span>  
  
 <span data-ttu-id="605fd-116">Essa transformação tem várias entradas e apenas uma saída.</span><span class="sxs-lookup"><span data-stu-id="605fd-116">This transformation has multiple inputs and one output.</span></span> <span data-ttu-id="605fd-117">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="605fd-117">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-union-all-transformation"></a><span data-ttu-id="605fd-118">Configuração da transformação Unir Tudo</span><span class="sxs-lookup"><span data-stu-id="605fd-118">Configuration of the Union All Transformation</span></span>  
 <span data-ttu-id="605fd-119">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="605fd-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="605fd-120">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Union All** , consulte [Editor de Transformação Union All](../../union-all-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="605fd-120">For more information about the properties that you can set in the **Union All Transformation Editor** dialog box, see [Union All Transformation Editor](../../union-all-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="605fd-121">Para obter mais informações sobre as propriedades que podem ser definidas programaticamente, consulte [Common Properties](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="605fd-121">For more information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
 <span data-ttu-id="605fd-122">Para obter mais informações sobre como definir propriedades, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="605fd-122">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="605fd-123">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="605fd-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="605fd-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="605fd-124">Related Tasks</span></span>  
 [<span data-ttu-id="605fd-125">Mesclar dados por meio da transformação Unir Tudo</span><span class="sxs-lookup"><span data-stu-id="605fd-125">Merge Data by Using the Union All Transformation</span></span>](union-all-transformation.md)  
  
  
