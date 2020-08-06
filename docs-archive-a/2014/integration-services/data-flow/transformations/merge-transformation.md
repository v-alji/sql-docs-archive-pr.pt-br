---
title: Transformação Mesclar | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergetrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- merging data [Integration Services]
- Merge transformation
- combining datasets
- datasets [Integration Services], merging
ms.assetid: cff8690c-07ac-46a0-aab5-20bd4848c677
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7d1d35e92b5978016b6a53956e5b6f1f6642f5ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684813"
---
# <a name="merge-transformation"></a><span data-ttu-id="d7dba-102">Transformação Mesclar</span><span class="sxs-lookup"><span data-stu-id="d7dba-102">Merge Transformation</span></span>
  <span data-ttu-id="d7dba-103">A Transformação Mesclagem combina dois conjuntos de dados classificados em um único conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="d7dba-103">The Merge transformation combines two sorted datasets into a single dataset.</span></span> <span data-ttu-id="d7dba-104">As linhas de cada conjunto de dados estão inseridas na saída com base em valores de suas colunas-chave.</span><span class="sxs-lookup"><span data-stu-id="d7dba-104">The rows from each dataset are inserted into the output based on values in their key columns.</span></span>  
  
 <span data-ttu-id="d7dba-105">Incluindo a Transformação Mesclar em um fluxo de dados, você poderá executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="d7dba-105">By including the Merge transformation in a data flow, you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="d7dba-106">Mesclar dados de duas fontes de dados, tais como tabelas e arquivos.</span><span class="sxs-lookup"><span data-stu-id="d7dba-106">Merge data from two data sources, such as tables and files.</span></span>  
  
-   <span data-ttu-id="d7dba-107">Criar conjuntos de dados complexos aninhando transformações de Mesclar.</span><span class="sxs-lookup"><span data-stu-id="d7dba-107">Create complex datasets by nesting Merge transformations.</span></span>  
  
-   <span data-ttu-id="d7dba-108">Volte a mesclar as filas depois de corrigir erros nos dados.</span><span class="sxs-lookup"><span data-stu-id="d7dba-108">Remerge rows after correcting errors in the data.</span></span>  
  
 <span data-ttu-id="d7dba-109">A Transformação Mesclar é semelhante às transformações do Union All.</span><span class="sxs-lookup"><span data-stu-id="d7dba-109">The Merge transformation is similar to the Union All transformations.</span></span> <span data-ttu-id="d7dba-110">Use a transformação do Union All em vez da Transformação Mesclar nas situações seguintes:</span><span class="sxs-lookup"><span data-stu-id="d7dba-110">Use the Union All transformation instead of the Merge transformation in the following situations:</span></span>  
  
-   <span data-ttu-id="d7dba-111">As entradas de transformação não estão ordenadas.</span><span class="sxs-lookup"><span data-stu-id="d7dba-111">The transformation inputs are not sorted.</span></span>  
  
-   <span data-ttu-id="d7dba-112">A saída combinada não precisa ser classificada.</span><span class="sxs-lookup"><span data-stu-id="d7dba-112">The combined output does not need to be sorted.</span></span>  
  
-   <span data-ttu-id="d7dba-113">A transformação tem mais de duas entradas.</span><span class="sxs-lookup"><span data-stu-id="d7dba-113">The transformation has more than two inputs.</span></span>  
  
## <a name="input-requirements"></a><span data-ttu-id="d7dba-114">Requisitos de entrada</span><span class="sxs-lookup"><span data-stu-id="d7dba-114">Input Requirements</span></span>  
 <span data-ttu-id="d7dba-115">A Transformação Mesclar requer dados classificados para suas entradas.</span><span class="sxs-lookup"><span data-stu-id="d7dba-115">The Merge Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="d7dba-116">Para obter mais informações sobre este requisito importante, consulte [Classificar dados para as transformações Mesclagem e Junção de Mesclagem](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="d7dba-116">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="d7dba-117">A Transformação Mesclar também requer que as colunas mescladas em suas entradas tenham metadados coincidentes.</span><span class="sxs-lookup"><span data-stu-id="d7dba-117">The Merge transformation also requires that the merged columns in its inputs have matching metadata.</span></span> <span data-ttu-id="d7dba-118">Por exemplo, você não pode mesclar uma coluna que tenha um tipo de dados numéricos com uma coluna que tenha um tipo de dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d7dba-118">For example, you cannot merge a column that has a numeric data type with a column that has a character data type.</span></span> <span data-ttu-id="d7dba-119">Se os dados tiverem um tipo de dados de cadeia de caracteres, o comprimento da coluna na segunda entrada deve ser menor, ou igual, ao comprimento da coluna na primeira entrada com a qual é intercalado.</span><span class="sxs-lookup"><span data-stu-id="d7dba-119">If the data has a string data type, the length of the column in the second input must be less than or equal to the length of the column in the first input with which it is merged.</span></span>  
  
 <span data-ttu-id="d7dba-120">No Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , a interface do usuário para a transformação Mesclar mapeia automaticamente as colunas que contém os mesmos metadados.</span><span class="sxs-lookup"><span data-stu-id="d7dba-120">In the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the user interface for the Merge transformation automatically maps columns that have the same metadata.</span></span> <span data-ttu-id="d7dba-121">É possível então mapear manualmente outras colunas que tenham tipos de dados compatíveis.</span><span class="sxs-lookup"><span data-stu-id="d7dba-121">You can then manually map other columns that have compatible data types.</span></span>  
  
 <span data-ttu-id="d7dba-122">Esta transformação tem duas entradas e uma saída.</span><span class="sxs-lookup"><span data-stu-id="d7dba-122">This transformation has two inputs and one output.</span></span> <span data-ttu-id="d7dba-123">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="d7dba-123">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-merge-transformation"></a><span data-ttu-id="d7dba-124">Configuração da Transformação Mesclar</span><span class="sxs-lookup"><span data-stu-id="d7dba-124">Configuration of the Merge Transformation</span></span>  
 <span data-ttu-id="d7dba-125">Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="d7dba-125">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d7dba-126">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Mesclar** , consulte [Editor de Transformação Mesclar](../../merge-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="d7dba-126">For more information about the properties that you can set in the **Merge Transformation Editor** dialog box, see [Merge Transformation Editor](../../merge-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="d7dba-127">Para obter mais informações sobre as propriedades que podem ser definidas programaticamente, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="d7dba-127">For more information about the properties that you can programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d7dba-128">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="d7dba-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="d7dba-129">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="d7dba-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="d7dba-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d7dba-130">Related Tasks</span></span>  
 <span data-ttu-id="d7dba-131">Para obter detalhes sobre como definir propriedades, consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="d7dba-131">For details about how to set properties, see the following topics:</span></span>  
  
-   [<span data-ttu-id="d7dba-132">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d7dba-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="d7dba-133">Classificar dados para as transformações Mesclagem e Junção de Mesclagem</span><span class="sxs-lookup"><span data-stu-id="d7dba-133">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7dba-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7dba-134">See Also</span></span>  
 <span data-ttu-id="d7dba-135">[Transformação Junção de Mesclagem](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="d7dba-135">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="d7dba-136">[Transformação Unir Tudo](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="d7dba-136">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="d7dba-137">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="d7dba-137">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="d7dba-138">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="d7dba-138">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
