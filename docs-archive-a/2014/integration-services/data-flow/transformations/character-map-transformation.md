---
title: Transformação Mapa de Caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.charactertrans.f1
helpviewer_keywords:
- mutually exclusive mapping [Integration Services]
- mapping data [Integration Services]
- string functions
- Character Map transformation [Integration Services]
ms.assetid: e0f50eb6-b893-400f-bb8c-fb3072cc2620
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5fc31e1a3500a7a7b023e43a968e70e5b438dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575248"
---
# <a name="character-map-transformation"></a><span data-ttu-id="eb63c-102">Transformação Mapas de Caracteres</span><span class="sxs-lookup"><span data-stu-id="eb63c-102">Character Map Transformation</span></span>
  <span data-ttu-id="eb63c-103">A transformação Mapa de Caracteres aplica funções de cadeia de caracteres, como a conversão de letra minúscula em maiúscula, em dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb63c-103">The Character Map transformation applies string functions, such as conversion from lowercase to uppercase, to character data.</span></span> <span data-ttu-id="eb63c-104">Essa transformação funciona apenas em dados de coluna com um tipo de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb63c-104">This transformation operates only on column data with a string data type.</span></span>  
  
 <span data-ttu-id="eb63c-105">A transformação Mapa de Caracteres pode converter dados de coluna existentes ou adicionar uma coluna à saída de transformação e colocar os dados convertidos na coluna nova.</span><span class="sxs-lookup"><span data-stu-id="eb63c-105">The Character Map transformation can convert column data in place or add a column to the transformation output and put the converted data in the new column.</span></span> <span data-ttu-id="eb63c-106">Você pode aplicar conjuntos diferentes de operações de mapeamento na mesma coluna de entrada e colocar os resultados em colunas diferentes.</span><span class="sxs-lookup"><span data-stu-id="eb63c-106">You can apply different sets of mapping operations to the same input column and put the results in different columns.</span></span> <span data-ttu-id="eb63c-107">Por exemplo, é possível converter a mesma coluna em maiúsculas e minúsculas e colocar os resultados em duas colunas diferentes.</span><span class="sxs-lookup"><span data-stu-id="eb63c-107">For example, you can convert the same column to uppercase and lowercase and put the results in two different columns.</span></span>  
  
 <span data-ttu-id="eb63c-108">O mapeamento pode, em algumas circunstâncias, fazer com que os dados fiquem truncados.</span><span class="sxs-lookup"><span data-stu-id="eb63c-108">Mapping can, under some circumstances, cause data to be truncated.</span></span> <span data-ttu-id="eb63c-109">Por exemplo, o truncamento pode acontecer quando caracteres de byte único são mapeados para caracteres com representação de vários bytes.</span><span class="sxs-lookup"><span data-stu-id="eb63c-109">For example, truncation can occur when single-byte characters are mapped to characters with a multibyte representation.</span></span> <span data-ttu-id="eb63c-110">A transformação Mapa de Caracteres inclui uma saída de erro, que pode ser usada para direcionar dados truncados para uma saída separada.</span><span class="sxs-lookup"><span data-stu-id="eb63c-110">The Character Map transformation includes an error output, which can be used to direct truncated data to separate output.</span></span> <span data-ttu-id="eb63c-111">Para obter mais informações, consulte [Tratamento de erros em dados](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="eb63c-111">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="eb63c-112">Essa transformação tem uma entrada, uma saída e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="eb63c-112">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="mapping-operations"></a><span data-ttu-id="eb63c-113">Mapeando operações</span><span class="sxs-lookup"><span data-stu-id="eb63c-113">Mapping Operations</span></span>  
 <span data-ttu-id="eb63c-114">A tabela a seguir descreve as operações de mapeamento suportadas pela transformação Mapa de Caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb63c-114">The following table describes the mapping operations that the Character Map transformation supports.</span></span>  
  
|<span data-ttu-id="eb63c-115">Operação</span><span class="sxs-lookup"><span data-stu-id="eb63c-115">Operation</span></span>|<span data-ttu-id="eb63c-116">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="eb63c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb63c-117">Inversão de bytes</span><span class="sxs-lookup"><span data-stu-id="eb63c-117">Byte reversal</span></span>|<span data-ttu-id="eb63c-118">Inverte a ordem de bytes.</span><span class="sxs-lookup"><span data-stu-id="eb63c-118">Reverses byte order.</span></span>|  
|<span data-ttu-id="eb63c-119">Largura inteira</span><span class="sxs-lookup"><span data-stu-id="eb63c-119">Full width</span></span>|<span data-ttu-id="eb63c-120">Mapeia caracteres de meia largura para caracteres de largura inteira.</span><span class="sxs-lookup"><span data-stu-id="eb63c-120">Maps half-width characters to full-width characters.</span></span>|  
|<span data-ttu-id="eb63c-121">Meia largura</span><span class="sxs-lookup"><span data-stu-id="eb63c-121">Half width</span></span>|<span data-ttu-id="eb63c-122">Mapeia caracteres de largura inteira para caracteres de meia largura.</span><span class="sxs-lookup"><span data-stu-id="eb63c-122">Maps full-width characters to half-width characters.</span></span>|  
|<span data-ttu-id="eb63c-123">Hiragana</span><span class="sxs-lookup"><span data-stu-id="eb63c-123">Hiragana</span></span>|<span data-ttu-id="eb63c-124">Mapeia caracteres katakana para caracteres hiragana.</span><span class="sxs-lookup"><span data-stu-id="eb63c-124">Maps katakana characters to hiragana characters.</span></span>|  
|<span data-ttu-id="eb63c-125">Katakana</span><span class="sxs-lookup"><span data-stu-id="eb63c-125">Katakana</span></span>|<span data-ttu-id="eb63c-126">Mapeia caracteres hiragana para caracteres katakana.</span><span class="sxs-lookup"><span data-stu-id="eb63c-126">Maps hiragana characters to katakana characters.</span></span>|  
|<span data-ttu-id="eb63c-127">Caixas linguísticas</span><span class="sxs-lookup"><span data-stu-id="eb63c-127">Linguistic casing</span></span>|<span data-ttu-id="eb63c-128">Aplica caixas linguísticas em vez de regras do sistema.</span><span class="sxs-lookup"><span data-stu-id="eb63c-128">Applies linguistic casing instead of the system rules.</span></span> <span data-ttu-id="eb63c-129">As caixas linguísticas se referem à funcionalidade fornecida pela API do Win32 para mapeamento de maiúsculas/minúsculas simples de Unicode de idiomas turcomanos e de outras localidades.</span><span class="sxs-lookup"><span data-stu-id="eb63c-129">Linguistic casing refers to functionality provided by the Win32 API for Unicode simple case mapping of Turkic and other locales.</span></span>|  
|<span data-ttu-id="eb63c-130">Letras minúsculas</span><span class="sxs-lookup"><span data-stu-id="eb63c-130">Lowercase</span></span>|<span data-ttu-id="eb63c-131">Converte caracteres em minúsculas.</span><span class="sxs-lookup"><span data-stu-id="eb63c-131">Converts characters to lowercase.</span></span>|  
|<span data-ttu-id="eb63c-132">Chinês simplificado</span><span class="sxs-lookup"><span data-stu-id="eb63c-132">Simplified Chinese</span></span>|<span data-ttu-id="eb63c-133">Mapeia caracteres de chinês tradicional para caracteres de chinês simplificado.</span><span class="sxs-lookup"><span data-stu-id="eb63c-133">Maps traditional Chinese characters to simplified Chinese characters.</span></span>|  
|<span data-ttu-id="eb63c-134">Chinês tradicional</span><span class="sxs-lookup"><span data-stu-id="eb63c-134">Traditional Chinese</span></span>|<span data-ttu-id="eb63c-135">Mapeia caracteres de chinês simplificado para caracteres de chinês tradicional.</span><span class="sxs-lookup"><span data-stu-id="eb63c-135">Maps simplified Chinese characters to traditional Chinese characters.</span></span>|  
|<span data-ttu-id="eb63c-136">Letras Maiúsculas</span><span class="sxs-lookup"><span data-stu-id="eb63c-136">Uppercase</span></span>|<span data-ttu-id="eb63c-137">Converte caracteres em maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="eb63c-137">Converts characters to uppercase.</span></span>|  
  
## <a name="mutually-exclusive-mapping-operations"></a><span data-ttu-id="eb63c-138">Operações de mapeamento mutuamente exclusivas</span><span class="sxs-lookup"><span data-stu-id="eb63c-138">Mutually Exclusive Mapping Operations</span></span>  
 <span data-ttu-id="eb63c-139">Mais de uma operação pode ser executada em uma transformação.</span><span class="sxs-lookup"><span data-stu-id="eb63c-139">More than one operation can be performed in a transformation.</span></span> <span data-ttu-id="eb63c-140">Entretanto, algumas operações de mapeamento são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="eb63c-140">However, some mapping operations are mutually exclusive.</span></span> <span data-ttu-id="eb63c-141">A tabela a seguir relaciona restrições que se aplicam quando você usa várias operações na mesma coluna.</span><span class="sxs-lookup"><span data-stu-id="eb63c-141">The following table lists restrictions that apply when you use multiple operations on the same column.</span></span> <span data-ttu-id="eb63c-142">As operações nas colunas Operação A e Operação B são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="eb63c-142">Operations in the columns Operation A and Operation B are mutually exclusive.</span></span>  
  
|<span data-ttu-id="eb63c-143">Operação A</span><span class="sxs-lookup"><span data-stu-id="eb63c-143">Operation A</span></span>|<span data-ttu-id="eb63c-144">Operação B</span><span class="sxs-lookup"><span data-stu-id="eb63c-144">Operation B</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="eb63c-145">Letras minúsculas</span><span class="sxs-lookup"><span data-stu-id="eb63c-145">Lowercase</span></span>|<span data-ttu-id="eb63c-146">Letras Maiúsculas</span><span class="sxs-lookup"><span data-stu-id="eb63c-146">Uppercase</span></span>|  
|<span data-ttu-id="eb63c-147">Hiragana</span><span class="sxs-lookup"><span data-stu-id="eb63c-147">Hiragana</span></span>|<span data-ttu-id="eb63c-148">Katakana</span><span class="sxs-lookup"><span data-stu-id="eb63c-148">Katakana</span></span>|  
|<span data-ttu-id="eb63c-149">Meia largura</span><span class="sxs-lookup"><span data-stu-id="eb63c-149">Half width</span></span>|<span data-ttu-id="eb63c-150">Largura inteira</span><span class="sxs-lookup"><span data-stu-id="eb63c-150">Full width</span></span>|  
|<span data-ttu-id="eb63c-151">Chinês tradicional</span><span class="sxs-lookup"><span data-stu-id="eb63c-151">Traditional Chinese</span></span>|<span data-ttu-id="eb63c-152">Chinês simplificado</span><span class="sxs-lookup"><span data-stu-id="eb63c-152">Simplified Chinese</span></span>|  
|<span data-ttu-id="eb63c-153">Letras minúsculas</span><span class="sxs-lookup"><span data-stu-id="eb63c-153">Lowercase</span></span>|<span data-ttu-id="eb63c-154">Hiragana, katakana, meia largura, largura inteira</span><span class="sxs-lookup"><span data-stu-id="eb63c-154">Hiragana, katakana, half width, full width</span></span>|  
|<span data-ttu-id="eb63c-155">Letras Maiúsculas</span><span class="sxs-lookup"><span data-stu-id="eb63c-155">Uppercase</span></span>|<span data-ttu-id="eb63c-156">Hiragana, katakana, meia largura, largura inteira</span><span class="sxs-lookup"><span data-stu-id="eb63c-156">Hiragana, katakana, half width, full width</span></span>|  
  
## <a name="configuration-of-the-character-map-transformation"></a><span data-ttu-id="eb63c-157">Configuração da transformação Mapa de Caracteres</span><span class="sxs-lookup"><span data-stu-id="eb63c-157">Configuration of the Character Map Transformation</span></span>  
 <span data-ttu-id="eb63c-158">Você pode configurar a transformação Mapa de Caracteres das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="eb63c-158">You configure the Character Map transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="eb63c-159">Especificando as colunas a serem convertidas.</span><span class="sxs-lookup"><span data-stu-id="eb63c-159">Specify the columns to convert.</span></span>  
  
-   <span data-ttu-id="eb63c-160">Especificando as operações a serem aplicadas em cada coluna.</span><span class="sxs-lookup"><span data-stu-id="eb63c-160">Specify the operations to apply to each column.</span></span>  
  
 <span data-ttu-id="eb63c-161">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="eb63c-161">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="eb63c-162">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação de Mapas de Caracteres** , consulte [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="eb63c-162">For more information about the properties that you can set in the **Character Map Transformation Editor** dialog box, see [Character Map Transformation Editor](../../character-map-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="eb63c-163">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="eb63c-163">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="eb63c-164">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="eb63c-164">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="eb63c-165">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="eb63c-165">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="eb63c-166">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="eb63c-166">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="eb63c-167">Para obter mais informações sobre como definir propriedades, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="eb63c-167">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="eb63c-168">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="eb63c-168">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="eb63c-169">Classificar dados para as transformações Mesclagem e Junção de Mesclagem</span><span class="sxs-lookup"><span data-stu-id="eb63c-169">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
  
