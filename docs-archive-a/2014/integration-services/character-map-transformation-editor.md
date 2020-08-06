---
title: Editor de transformação mapa de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactermaptransformation.f1
helpviewer_keywords:
- Character Map Transformation Editor
ms.assetid: 3f1dbcf9-9cca-4606-bdcc-7ea6ad48cdf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c6cdcdba448dafc6ccf03774d4f611dee704b823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571510"
---
# <a name="character-map-transformation-editor"></a><span data-ttu-id="8a63b-102">Editor de Transformação Mapas de Caracteres</span><span class="sxs-lookup"><span data-stu-id="8a63b-102">Character Map Transformation Editor</span></span>
  <span data-ttu-id="8a63b-103">Use a caixa de diálogo **Editor de Transformação Mapas de Caracteres** para selecionar as funções de cadeia de caracteres a serem aplicadas aos dados de coluna, bem como para especificar se o mapeamento é uma alteração in-loco ou se deve ser adicionado como uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="8a63b-103">Use the **Character Map Transformation Editor** dialog box to select the string functions to apply to column data and to specify whether mapping is an in-place change or added as a new column.</span></span>  
  
 <span data-ttu-id="8a63b-104">Para saber mais sobre transformação Mapa de Caracteres, consulte [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8a63b-104">To learn more about the Character Map transformation, see [Character Map Transformation](data-flow/transformations/character-map-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8a63b-105">Opções</span><span class="sxs-lookup"><span data-stu-id="8a63b-105">Options</span></span>  
 <span data-ttu-id="8a63b-106">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="8a63b-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="8a63b-107">Use as caixas de seleção para selecionar as colunas a transformar, utilizando funções de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8a63b-107">Use the check boxes to select the columns to transform using string functions.</span></span> <span data-ttu-id="8a63b-108">Suas seleções aparecem na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="8a63b-108">Your selections appear in the table below.</span></span>  
  
 <span data-ttu-id="8a63b-109">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="8a63b-109">**Input Column**</span></span>  
 <span data-ttu-id="8a63b-110">Exibir colunas de entrada selecionadas na tabela acima.</span><span class="sxs-lookup"><span data-stu-id="8a63b-110">View input columns selected from the table above.</span></span> <span data-ttu-id="8a63b-111">Você também pode alterar ou remover uma seleção, por meio da lista de colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8a63b-111">You can also change or remove a selection by using the list of available input columns.</span></span>  
  
 <span data-ttu-id="8a63b-112">**Destino**</span><span class="sxs-lookup"><span data-stu-id="8a63b-112">**Destination**</span></span>  
 <span data-ttu-id="8a63b-113">Especifique entre salvar os resultados das operações de cadeia de caracteres no local, usando a coluna existente, ou salvar os dados modificados como uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="8a63b-113">Specify whether to save the results of the string operations in place, using the existing column, or to save the modified data as a new column.</span></span>  
  
|<span data-ttu-id="8a63b-114">Valor</span><span class="sxs-lookup"><span data-stu-id="8a63b-114">Value</span></span>|<span data-ttu-id="8a63b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="8a63b-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a63b-116">Nova coluna</span><span class="sxs-lookup"><span data-stu-id="8a63b-116">New column</span></span>|<span data-ttu-id="8a63b-117">Salve os dados em uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="8a63b-117">Save the data in a new column.</span></span> <span data-ttu-id="8a63b-118">Atribua o nome de coluna em **Alias de Saída**.</span><span class="sxs-lookup"><span data-stu-id="8a63b-118">Assign the column name under **Output Alias**.</span></span>|  
|<span data-ttu-id="8a63b-119">Alteração no local</span><span class="sxs-lookup"><span data-stu-id="8a63b-119">In-place change</span></span>|<span data-ttu-id="8a63b-120">Salve os dados modificados na coluna existente.</span><span class="sxs-lookup"><span data-stu-id="8a63b-120">Save the modified data in the existing column.</span></span>|  
  
 <span data-ttu-id="8a63b-121">**Operação**</span><span class="sxs-lookup"><span data-stu-id="8a63b-121">**Operation**</span></span>  
 <span data-ttu-id="8a63b-122">Selecione na lista as funções de cadeia de caracteres a aplicar aos dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="8a63b-122">Select from the list the string functions to apply to column data.</span></span>  
  
|<span data-ttu-id="8a63b-123">Valor</span><span class="sxs-lookup"><span data-stu-id="8a63b-123">Value</span></span>|<span data-ttu-id="8a63b-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="8a63b-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a63b-125">Letras minúsculas</span><span class="sxs-lookup"><span data-stu-id="8a63b-125">Lowercase</span></span>|<span data-ttu-id="8a63b-126">Converter para letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8a63b-126">Convert to lower case.</span></span>|  
|<span data-ttu-id="8a63b-127">Letras Maiúsculas</span><span class="sxs-lookup"><span data-stu-id="8a63b-127">Uppercase</span></span>|<span data-ttu-id="8a63b-128">Converter para letras maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="8a63b-128">Convert to upper case.</span></span>|  
|<span data-ttu-id="8a63b-129">Inversão de bytes</span><span class="sxs-lookup"><span data-stu-id="8a63b-129">Byte reversal</span></span>|<span data-ttu-id="8a63b-130">Converter invertendo a ordem de bytes.</span><span class="sxs-lookup"><span data-stu-id="8a63b-130">Convert by reversing byte order.</span></span>|  
|<span data-ttu-id="8a63b-131">Hiragana</span><span class="sxs-lookup"><span data-stu-id="8a63b-131">Hiragana</span></span>|<span data-ttu-id="8a63b-132">Converter caracteres japoneses de katakana em hiragana.</span><span class="sxs-lookup"><span data-stu-id="8a63b-132">Convert Japanese katakana characters to hiragana.</span></span>|  
|<span data-ttu-id="8a63b-133">Katakana</span><span class="sxs-lookup"><span data-stu-id="8a63b-133">Katakana</span></span>|<span data-ttu-id="8a63b-134">Converter caracteres japoneses de hiragana em katakana.</span><span class="sxs-lookup"><span data-stu-id="8a63b-134">Convert Japanese hiragana characters to katakana.</span></span>|  
|<span data-ttu-id="8a63b-135">Meia largura</span><span class="sxs-lookup"><span data-stu-id="8a63b-135">Half width</span></span>|<span data-ttu-id="8a63b-136">Converter caracteres de largura inteira em meia largura.</span><span class="sxs-lookup"><span data-stu-id="8a63b-136">Convert full-width characters to half width.</span></span>|  
|<span data-ttu-id="8a63b-137">Largura inteira</span><span class="sxs-lookup"><span data-stu-id="8a63b-137">Full width</span></span>|<span data-ttu-id="8a63b-138">Converter caracteres de meia largura em largura inteira.</span><span class="sxs-lookup"><span data-stu-id="8a63b-138">Convert half-width characters to full width.</span></span>|  
|<span data-ttu-id="8a63b-139">Caixas linguísticas</span><span class="sxs-lookup"><span data-stu-id="8a63b-139">Linguistic casing</span></span>|<span data-ttu-id="8a63b-140">Aplicar regras linguísticas de maiúsculas e minúsculas (mapeamento simples de maiúsculas e minúsculas Unicode para a Turquia e outras localidades), em vez das regras do sistema.</span><span class="sxs-lookup"><span data-stu-id="8a63b-140">Apply linguistic rules of casing (Unicode simple case mapping for Turkic and other locales) instead of the system rules.</span></span>|  
|<span data-ttu-id="8a63b-141">Chinês simplificado</span><span class="sxs-lookup"><span data-stu-id="8a63b-141">Simplified Chinese</span></span>|<span data-ttu-id="8a63b-142">Converter caracteres do chinês tradicional em caracteres do chinês simplificado.</span><span class="sxs-lookup"><span data-stu-id="8a63b-142">Convert traditional Chinese characters to simplified Chinese.</span></span>|  
|<span data-ttu-id="8a63b-143">Chinês tradicional</span><span class="sxs-lookup"><span data-stu-id="8a63b-143">Traditional Chinese</span></span>|<span data-ttu-id="8a63b-144">Converter caracteres do chinês simplificado em caracteres do chinês tradicional.</span><span class="sxs-lookup"><span data-stu-id="8a63b-144">Convert simplified Chinese characters to traditional Chinese.</span></span>|  
  
 <span data-ttu-id="8a63b-145">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="8a63b-145">**Output Alias**</span></span>  
 <span data-ttu-id="8a63b-146">Digite um alias para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="8a63b-146">Type an alias for each output column.</span></span> <span data-ttu-id="8a63b-147">O padrão é **Copiar de** seguido do nome da coluna de entrada; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8a63b-147">The default is **Copy of** followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="8a63b-148">**Configurar Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="8a63b-148">**Configure Error Output**</span></span>  
 <span data-ttu-id="8a63b-149">Use a caixa de diálogo [Configurar Saída de Erro](../../2014/integration-services/configure-error-output.md) para especificar opções de tratamento de erro para esta transformação.</span><span class="sxs-lookup"><span data-stu-id="8a63b-149">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for this transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a63b-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a63b-150">See Also</span></span>  
 [<span data-ttu-id="8a63b-151">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="8a63b-151">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
