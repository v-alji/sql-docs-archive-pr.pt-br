---
title: Editor de transformação pesquisa (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.columns.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: 690ffef5-fd59-4e95-a27d-4fcf0d6b1c0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b768076d8acbcaef8cbff21783a7697020e027eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574108"
---
# <a name="lookup-transformation-editor-columns-page"></a><span data-ttu-id="45687-102">Editor da Transformação Pesquisa (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="45687-102">Lookup Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="45687-103">Use a página **Colunas** da caixa de diálogo **Editor da Transformação Pesquisa** para especificar a junção entre a tabela de origem e a tabela de referência, e para selecionar as colunas de pesquisa a partir da tabela de referência.</span><span class="sxs-lookup"><span data-stu-id="45687-103">Use the **Columns** page of the **Lookup Transformation Editor** dialog box to specify the join between the source table and the reference table, and to select lookup columns from the reference table.</span></span>  
  
 <span data-ttu-id="45687-104">Para saber mais sobre a transformação Pesquisa, consulte [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="45687-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="45687-105">Opções</span><span class="sxs-lookup"><span data-stu-id="45687-105">Options</span></span>  
 <span data-ttu-id="45687-106">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="45687-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="45687-107">Exiba a lista das colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="45687-107">View the list of available input columns.</span></span> <span data-ttu-id="45687-108">As colunas de entrada são as colunas no fluxo de dados de uma origem conectada.</span><span class="sxs-lookup"><span data-stu-id="45687-108">The input columns are the columns in the data flow from a connected source.</span></span> <span data-ttu-id="45687-109">As colunas de entrada e de pesquisa devem ter tipos de dados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="45687-109">The input columns and lookup column must have matching data types.</span></span>  
  
 <span data-ttu-id="45687-110">Use uma operação arrastar e soltar para mapear as colunas de entrada disponíveis para as colunas de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="45687-110">Use a drag-and-drop operation to map available input columns to lookup columns.</span></span>  
  
 <span data-ttu-id="45687-111">Você também pode mapear as colunas de entrada para as colunas de pesquisa usando o teclado, destacando a coluna na tabela **Colunas de Entrada Disponíveis** , pressionando a tecla Aplicativo e clicando em **Editar Mapeamentos**.</span><span class="sxs-lookup"><span data-stu-id="45687-111">You can also map input columns to lookup columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="45687-112">**Colunas de Pesquisa Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="45687-112">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="45687-113">Exiba a lista de colunas de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="45687-113">View the list of lookup columns.</span></span> <span data-ttu-id="45687-114">As colunas de pesquisa são as colunas na tabela de referência que permitem pesquisar os valores que correspondem às colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="45687-114">The lookup columns are columns in the reference table in which you want to look up values that match the input columns.</span></span>  
  
 <span data-ttu-id="45687-115">Use uma operação arrastar e soltar para mapear as colunas de pesquisa disponíveis para as colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="45687-115">Use a drag-and-drop operation to map available lookup columns to input columns.</span></span>  
  
 <span data-ttu-id="45687-116">Use as caixas de seleção para selecionar as colunas de pesquisa na tabela de referência nas quais serão executadas as operações de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="45687-116">Use the check boxes to select lookup columns in the reference table on which to perform lookup operations.</span></span>  
  
 <span data-ttu-id="45687-117">Você também pode mapear as colunas de pesquisa para as colunas de entrada usando o teclado, destacando a coluna na tabela **Colunas de Pesquisa Disponíveis** , pressionando a tecla Aplicativo e clicando em **Editar Mapeamentos**.</span><span class="sxs-lookup"><span data-stu-id="45687-117">You can also map lookup columns to input columns using the keyboard, by highlighting a column in the **Available Lookup Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="45687-118">**coluna de pesquisa**</span><span class="sxs-lookup"><span data-stu-id="45687-118">**Lookup Column**</span></span>  
 <span data-ttu-id="45687-119">Exiba as colunas de pesquisa selecionadas.</span><span class="sxs-lookup"><span data-stu-id="45687-119">View the selected lookup columns.</span></span> <span data-ttu-id="45687-120">As escolhas são refletidas nas caixas de seleção da tabela **Colunas de Pesquisa Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="45687-120">The selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span>  
  
 <span data-ttu-id="45687-121">**Operação de Pesquisa**</span><span class="sxs-lookup"><span data-stu-id="45687-121">**Lookup Operation**</span></span>  
 <span data-ttu-id="45687-122">Selecione uma operação de pesquisa da lista a ser executada na coluna de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="45687-122">Select a lookup operation from the list to perform on the lookup column.</span></span>  
  
 <span data-ttu-id="45687-123">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="45687-123">**Output Alias**</span></span>  
 <span data-ttu-id="45687-124">Digite um alias para a saída de cada coluna de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="45687-124">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="45687-125">O padrão é o nome da coluna de pesquisa; entretanto, é possível selecionar qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="45687-125">The default is the name of the lookup column; however, you can select any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45687-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45687-126">See Also</span></span>  
 <span data-ttu-id="45687-127">[Editor de transformação pesquisa &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="45687-127">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="45687-128">[Editor de transformação pesquisa &#40;página conexão&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="45687-128">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="45687-129">[Editor de transformação pesquisa &#40;página avançado&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="45687-129">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="45687-130">[Editor de transformação pesquisa &#40;página saída de erro&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="45687-130">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="45687-131">transformação Pesquisa Difusa</span><span class="sxs-lookup"><span data-stu-id="45687-131">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
