---
title: Editor de transformação pesquisa de termos (guia pesquisa de termos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.termlookup.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 245d3466-d51f-4073-978a-694a8d9dfaec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bb8c0bd0477d9883640cc3e4d3cb25c2a3a8b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583155"
---
# <a name="term-lookup-transformation-editor-term-lookup-tab"></a><span data-ttu-id="d1433-102">Editor de Transformação Pesquisa de Termos (guia Pesquisa de Termos)</span><span class="sxs-lookup"><span data-stu-id="d1433-102">Term Lookup Transformation Editor (Term Lookup Tab)</span></span>
  <span data-ttu-id="d1433-103">Use a guia **Pesquisa de Termos** na caixa de diálogo **Editor de Transformação Pesquisa de Termos** para mapear uma coluna de entrada para uma coluna de pesquisa em uma tabela de referência e fornecer um alias para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="d1433-103">Use the **Term Lookup** tab of the **Term Lookup Transformation Editor** dialog box to map an input column to a lookup column in a reference table and to provide an alias for each output column.</span></span>  
  
 <span data-ttu-id="d1433-104">Para saber mais sobre a transformação Pesquisa de Termos, consulte [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="d1433-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d1433-105">Opções</span><span class="sxs-lookup"><span data-stu-id="d1433-105">Options</span></span>  
 <span data-ttu-id="d1433-106">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="d1433-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="d1433-107">Usando as caixas de seleção, selecione colunas de entrada para passar para a saída inalteradas.</span><span class="sxs-lookup"><span data-stu-id="d1433-107">Using the check boxes, select input columns to pass through to the output unchanged.</span></span> <span data-ttu-id="d1433-108">Arraste uma coluna de entrada para a lista **Colunas de Referência Disponíveis** para mapeá-la para uma coluna de pesquisa na tabela de referência.</span><span class="sxs-lookup"><span data-stu-id="d1433-108">Drag an input column to the **Available Reference Columns** list to map it to a lookup column in the reference table.</span></span> <span data-ttu-id="d1433-109">As colunas de entrada e de pesquisa devem ter tipos de dados correspondentes e que tenham suporte no DT_NTEXT ou DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="d1433-109">The input and lookup columns must have matching, supported data types, either DT_NTEXT or DT_WSTR.</span></span> <span data-ttu-id="d1433-110">Selecione uma linha de mapeamento e clique com o botão direito do mouse para editar os mapeamentos na caixa de diálogo [Criar Relações](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="d1433-110">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="d1433-111">**Colunas de Referência Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="d1433-111">**Available Reference Columns**</span></span>  
 <span data-ttu-id="d1433-112">Exiba as colunas disponíveis na tabela de referência.</span><span class="sxs-lookup"><span data-stu-id="d1433-112">View the available columns in the reference table.</span></span> <span data-ttu-id="d1433-113">Escolha a coluna que contém a lista de termos a corresponder.</span><span class="sxs-lookup"><span data-stu-id="d1433-113">Choose the column that contains the list of terms to match.</span></span>  
  
 <span data-ttu-id="d1433-114">**Coluna de Passagem**</span><span class="sxs-lookup"><span data-stu-id="d1433-114">**Pass-Through Column**</span></span>  
 <span data-ttu-id="d1433-115">Selecione na lista de colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d1433-115">Select from the list of available input columns.</span></span> <span data-ttu-id="d1433-116">As seleções se refletem naquelas da caixa de seleção da tabela **Colunas de Entrada Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="d1433-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="d1433-117">**Alias de Coluna de Saída**</span><span class="sxs-lookup"><span data-stu-id="d1433-117">**Output Column Alias**</span></span>  
 <span data-ttu-id="d1433-118">Digite um alias para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="d1433-118">Type an alias for each output column.</span></span> <span data-ttu-id="d1433-119">O padrão é o nome da coluna; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d1433-119">The default is the name of the column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="d1433-120">**Configurar Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="d1433-120">**Configure Error Output**</span></span>  
 <span data-ttu-id="d1433-121">Use a caixa de diálogo [Configurar Saída de Erro](../../2014/integration-services/configure-error-output.md) para especificar as opções de tratamento de erro em linhas que causam erros.</span><span class="sxs-lookup"><span data-stu-id="d1433-121">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1433-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1433-122">See Also</span></span>  
 <span data-ttu-id="d1433-123">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d1433-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d1433-124">[Editor de transformação pesquisa de termos &#40;guia tabela de referência&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="d1433-124">[Term Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 <span data-ttu-id="d1433-125">[Editor de transformação pesquisa de termos &#40;guia Avançado&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="d1433-125">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="d1433-126">Transformação Extração de Termos</span><span class="sxs-lookup"><span data-stu-id="d1433-126">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
