---
title: Editor de transformação pesquisa (página saída de erro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.erroroutput.f1
ms.assetid: 15d53bb0-8be1-46fb-b459-04a397e75fac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cd78f40a0072f7f0c5c923cdd51431873402f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574104"
---
# <a name="lookup-transformation-editor-error-output-page"></a><span data-ttu-id="dcaf3-102">Editor da Transformação Pesquisa (página Saída de Erro)</span><span class="sxs-lookup"><span data-stu-id="dcaf3-102">Lookup Transformation Editor (Error Output Page)</span></span>
  <span data-ttu-id="dcaf3-103">Use a página **Saída de Erro** da caixa de diálogo **Editor da Transformação Pesquisa** para especificar as opções de tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-103">Use the **Error Output** page of the **Lookup Transformation Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="dcaf3-104">Para saber mais sobre a transformação Pesquisa, consulte [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="dcaf3-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dcaf3-105">Opções</span><span class="sxs-lookup"><span data-stu-id="dcaf3-105">Options</span></span>  
 <span data-ttu-id="dcaf3-106">**Entrada/Saída**</span><span class="sxs-lookup"><span data-stu-id="dcaf3-106">**Input/Output**</span></span>  
 <span data-ttu-id="dcaf3-107">Visualize o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-107">View the name of the input.</span></span>  
  
 <span data-ttu-id="dcaf3-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dcaf3-108">**Column**</span></span>  
 <span data-ttu-id="dcaf3-109">Não usado.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-109">Not used.</span></span>  
  
 <span data-ttu-id="dcaf3-110">**Erro**</span><span class="sxs-lookup"><span data-stu-id="dcaf3-110">**Error**</span></span>  
 <span data-ttu-id="dcaf3-111">Especifique que tipo de erro pode ocorrer ao lidar com linhas com entradas sem correspondência no conjunto de dados de referência:</span><span class="sxs-lookup"><span data-stu-id="dcaf3-111">Specify what type of error should occur when handling rows without matching entries in the reference dataset:</span></span>  
  
-   <span data-ttu-id="dcaf3-112">Ignorar falha e direcionar linhas para uma saída.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-112">Ignore the failure and direct the rows to an output.</span></span>  
  
-   <span data-ttu-id="dcaf3-113">Redirecionar linhas para uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-113">Redirect the rows to an error output.</span></span>  
  
-   <span data-ttu-id="dcaf3-114">Falha no componente.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-114">Fail the component.</span></span>  
  
 <span data-ttu-id="dcaf3-115">Esta opção não estará disponível ao selecionar **Redirecionar linhas para uma saída sem-correspondência** na lista **Especificar como lidar com linhas com entradas sem-correspondência** .</span><span class="sxs-lookup"><span data-stu-id="dcaf3-115">This option is not available when you select **Redirect rows to no match output** in the **Specify how to handle rows with no matching entries** list.</span></span> <span data-ttu-id="dcaf3-116">Essa lista está na página **Geral** da caixa de diálogo **Editor da Transformação Pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="dcaf3-116">This list is on the **General** page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="dcaf3-117">**Tópicos relacionados:** [Tratamento de erro em dados](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="dcaf3-117">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="dcaf3-118">**Truncation**</span><span class="sxs-lookup"><span data-stu-id="dcaf3-118">**Truncation**</span></span>  
 <span data-ttu-id="dcaf3-119">Especifique o que deve acontecer quando ocorrer um truncamento de dados:</span><span class="sxs-lookup"><span data-stu-id="dcaf3-119">Specify what should happen when data truncation occurs:</span></span>  
  
-   <span data-ttu-id="dcaf3-120">Ignorar falha.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-120">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="dcaf3-121">Redirecionar linha.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-121">Redirect the row.</span></span>  
  
-   <span data-ttu-id="dcaf3-122">Falha no componente.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-122">Fail the component.</span></span>  
  
 <span data-ttu-id="dcaf3-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="dcaf3-123">**Description**</span></span>  
 <span data-ttu-id="dcaf3-124">Visualize a descrição da operação.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-124">View the description of the operation.</span></span>  
  
 <span data-ttu-id="dcaf3-125">**Definir células selecionadas com esse valor**</span><span class="sxs-lookup"><span data-stu-id="dcaf3-125">**Set selected cells to this value**</span></span>  
 <span data-ttu-id="dcaf3-126">Especifique o que deve acontecer com todas as células selecionadas quando ocorrer um erro ou truncamento:</span><span class="sxs-lookup"><span data-stu-id="dcaf3-126">Specify what should happen to all the selected cells when an error or truncation occurs:</span></span>  
  
-   <span data-ttu-id="dcaf3-127">Ignorar falha.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-127">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="dcaf3-128">Redirecionar linha.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-128">Redirect the row.</span></span>  
  
-   <span data-ttu-id="dcaf3-129">Falha no componente.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-129">Fail the component.</span></span>  
  
 <span data-ttu-id="dcaf3-130">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="dcaf3-130">**Apply**</span></span>  
 <span data-ttu-id="dcaf3-131">Aplique a opção de tratamento de erros às células selecionadas.</span><span class="sxs-lookup"><span data-stu-id="dcaf3-131">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcaf3-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dcaf3-132">See Also</span></span>  
 [<span data-ttu-id="dcaf3-133">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="dcaf3-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
