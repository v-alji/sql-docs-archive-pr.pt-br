---
title: Editor de transformação não dinâmica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottransformation.f1
helpviewer_keywords:
- Unpivot Transformation Editor
ms.assetid: 72a36ef0-4070-4f6c-9c74-0720109617dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c3b93370b34440b73b4c9c78dc7d19fa4095275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570744"
---
# <a name="unpivot-transformation-editor"></a><span data-ttu-id="5c9d8-102">Editor de Transformação Não Dinâmica</span><span class="sxs-lookup"><span data-stu-id="5c9d8-102">Unpivot Transformation Editor</span></span>
  <span data-ttu-id="5c9d8-103">Use a caixa de diálogo **Editor de Transformação Não Dinâmica** para selecionar as colunas que serão dinamizadas em linhas, e para especificar as colunas de dados e a nova coluna de saída de valor dinâmico.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-103">Use the **Unpivot Transformation Editor** dialog box to select the columns to pivot into rows, and to specify the data column and the new pivot value output column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c9d8-104"> Este tópico se baseia no cenário Não Dinâmico descrito em [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) para ilustrar o uso das opções.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-104">This topic relies on the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) to illustrate the use of the options.</span></span>  
  
 <span data-ttu-id="5c9d8-105">Para saber mais sobre transformação não dinâmica, consulte [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="5c9d8-105">To learn more about the Unpivot transformation, see [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c9d8-106">Opções</span><span class="sxs-lookup"><span data-stu-id="5c9d8-106">Options</span></span>  
 <span data-ttu-id="5c9d8-107">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="5c9d8-107">**Available Input Columns**</span></span>  
 <span data-ttu-id="5c9d8-108">Usando as caixas de seleção, especifique as colunas que serão dinamizadas em linhas.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-108">Using the check boxes, specify the columns to pivot into rows.</span></span>  
  
 <span data-ttu-id="5c9d8-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5c9d8-109">**Name**</span></span>  
 <span data-ttu-id="5c9d8-110">Exiba o nome da coluna de entrada disponível.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-110">View the name of the available input column.</span></span>  
  
 <span data-ttu-id="5c9d8-111">**Passagem**</span><span class="sxs-lookup"><span data-stu-id="5c9d8-111">**Pass Through**</span></span>  
 <span data-ttu-id="5c9d8-112">Indique se a coluna deve ser incluída na saída não dinâmica.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-112">Indicate whether to include the column in the unpivoted output.</span></span>  
  
 <span data-ttu-id="5c9d8-113">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="5c9d8-113">**Input Column**</span></span>  
 <span data-ttu-id="5c9d8-114">Selecione colunas para cada linha na lista de colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-114">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="5c9d8-115">As seleções se refletem naquelas da caixa de seleção da tabela **Colunas de Entrada Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="5c9d8-115">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="5c9d8-116">No cenário Não Dinâmico descrito em [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), as Colunas de Entrada são as colunas **Ham**, **Soda**, **Milk**, **Beer**e **Chips** .</span><span class="sxs-lookup"><span data-stu-id="5c9d8-116">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Input Columns are the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns.</span></span>  
  
 <span data-ttu-id="5c9d8-117">**Coluna de Destino**</span><span class="sxs-lookup"><span data-stu-id="5c9d8-117">**Destination Column**</span></span>  
 <span data-ttu-id="5c9d8-118">Forneça um nome para a coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-118">Provide a name for the data column.</span></span>  
  
 <span data-ttu-id="5c9d8-119">No cenário Não Dinâmico descrito em [Transformação Não Dinâmica](data-flow/transformations/unpivot-transformation.md), a Coluna de Destino é a coluna de quantidade (**Qtd**).</span><span class="sxs-lookup"><span data-stu-id="5c9d8-119">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Destination Column is the quantity (**Qty**) column.</span></span>  
  
 <span data-ttu-id="5c9d8-120">**Valor de Chave Dinâmica**</span><span class="sxs-lookup"><span data-stu-id="5c9d8-120">**Pivot Key Value**</span></span>  
 <span data-ttu-id="5c9d8-121">Forneça um nome para o valor dinâmico.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-121">Provide a name for the pivot value.</span></span> <span data-ttu-id="5c9d8-122">O padrão é o nome da coluna de entrada; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-122">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="5c9d8-123">O valor dessa propriedade pode ser especificado com uma expressão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-123">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="5c9d8-124">No cenário Não Dinâmico descrito em [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), os valores dinâmicos aparecerão na nova coluna Product designada pela opção **Nome da Coluna de Valores de Chaves Dinâmicas** , como os valores de texto **Ham**, **Soda**, **Milk**, **Beer**e **Chips**.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-124">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Values will appear in the new Product column designated by the **Pivot Key Value Column Name** option, as the text values **Ham**, **Soda**, **Milk**, **Beer**, and **Chips**.</span></span>  
  
 <span data-ttu-id="5c9d8-125">**Nome da Coluna de Valores de Chaves Dinâmicas**</span><span class="sxs-lookup"><span data-stu-id="5c9d8-125">**Pivot Key Value Column Name**</span></span>  
 <span data-ttu-id="5c9d8-126">Forneça um nome para a coluna de valor dinâmico.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-126">Provide a name for the pivot value column.</span></span> <span data-ttu-id="5c9d8-127">O padrão é "Valor da Chave Dinâmica"; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-127">The default is "Pivot Key Value"; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="5c9d8-128">No cenário Não Dinâmico descrito em [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), o nome de coluna de chave dinâmica é **Product** e designa a nova coluna **Product** , na qual as colunas **Ham**, **Soda**, **Milk**, **Beer**e **Chips** são não dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="5c9d8-128">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Key Value Column Name is **Product** and designates the new **Product** column into which the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns are unpivoted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9d8-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c9d8-129">See Also</span></span>  
 <span data-ttu-id="5c9d8-130">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5c9d8-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="5c9d8-131">Transformação Dinâmica</span><span class="sxs-lookup"><span data-stu-id="5c9d8-131">Pivot Transformation</span></span>](data-flow/transformations/pivot-transformation.md)  
  
  
