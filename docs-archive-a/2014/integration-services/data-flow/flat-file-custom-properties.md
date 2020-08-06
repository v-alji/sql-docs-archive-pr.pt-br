---
title: Propriedades personalizadas de arquivo simples | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f2caeab-784c-4b0c-9b3e-6a88d1ccdbf9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b906e9268bf3a74ffcf5661953397ad7a24b77a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685856"
---
# <a name="flat-file-custom-properties"></a><span data-ttu-id="da855-102">Propriedades personalizadas de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="da855-102">Flat File Custom Properties</span></span>
  <span data-ttu-id="da855-103">**Propriedades personalizadas de fontes**</span><span class="sxs-lookup"><span data-stu-id="da855-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="da855-104">A fonte de Arquivo Simples tem as propriedades personalizadas e as propriedades comuns a todos os componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="da855-104">The Flat File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="da855-105">A tabela a seguir descreve as propriedades personalizadas da fonte de Arquivo Simples.</span><span class="sxs-lookup"><span data-stu-id="da855-105">The following table describes the custom properties of the Flat File source.</span></span> <span data-ttu-id="da855-106">Todas as propriedades são de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="da855-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="da855-107">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="da855-107">Property name</span></span>|<span data-ttu-id="da855-108">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="da855-108">Data Type</span></span>|<span data-ttu-id="da855-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="da855-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="da855-110">FileNameColumnName</span><span class="sxs-lookup"><span data-stu-id="da855-110">FileNameColumnName</span></span>|<span data-ttu-id="da855-111">String</span><span class="sxs-lookup"><span data-stu-id="da855-111">String</span></span>|<span data-ttu-id="da855-112">O nome de uma coluna de saída que contém o nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="da855-112">The name of an output column that contains the file name.</span></span> <span data-ttu-id="da855-113">Se nenhum nome for especificado, nenhuma coluna de saída que contém o nome de arquivo será gerada.</span><span class="sxs-lookup"><span data-stu-id="da855-113">If no name is specified, no output column containing the file name will be generated.</span></span><br /><br /> <span data-ttu-id="da855-114">Observação: essa propriedade não está disponível no **Editor de Fonte de Arquivo Simples**, mas pode ser definida por meio do **Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="da855-114">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="da855-115">RetainNulls</span><span class="sxs-lookup"><span data-stu-id="da855-115">RetainNulls</span></span>|<span data-ttu-id="da855-116">Boolean</span><span class="sxs-lookup"><span data-stu-id="da855-116">Boolean</span></span>|<span data-ttu-id="da855-117">Um valor que especifica se os valores Nulos do arquivo de origem devem ser retidos como valores Nulos quando os dados forem processados pelo mecanismo Pipeline de Transformação de Dados.</span><span class="sxs-lookup"><span data-stu-id="da855-117">A value that specifies whether to retain Null values from the source file as Null values when the data is processed by the Data Transformation Pipeline engine.</span></span> <span data-ttu-id="da855-118">O valor padrão dessa propriedade é `False`.</span><span class="sxs-lookup"><span data-stu-id="da855-118">The default value of this property is `False`.</span></span>|  
  
 <span data-ttu-id="da855-119">A saída da fonte de Arquivo Simples não tem nenhuma propriedade personalizada.</span><span class="sxs-lookup"><span data-stu-id="da855-119">The output of the Flat File source has no custom properties.</span></span>  
  
 <span data-ttu-id="da855-120">A tabela a seguir descreve as propriedades personalizadas das colunas de saída da fonte de Arquivo Simples.</span><span class="sxs-lookup"><span data-stu-id="da855-120">The following table describes the custom properties of the output columns of the Flat File source.</span></span> <span data-ttu-id="da855-121">Todas as propriedades são de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="da855-121">All properties are read/write.</span></span>  
  
|<span data-ttu-id="da855-122">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="da855-122">Property name</span></span>|<span data-ttu-id="da855-123">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="da855-123">Data Type</span></span>|<span data-ttu-id="da855-124">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="da855-124">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="da855-125">FastParse</span><span class="sxs-lookup"><span data-stu-id="da855-125">FastParse</span></span>|<span data-ttu-id="da855-126">Boolean</span><span class="sxs-lookup"><span data-stu-id="da855-126">Boolean</span></span>|<span data-ttu-id="da855-127">Um valor que indica se as colunas usam as rotinas de análise mais rápidas, mas que não fazem distinção entre localidades, fornecido pelo DTS, ou as rotinas de análise padrão que fazem distinção entre localidades.</span><span class="sxs-lookup"><span data-stu-id="da855-127">A value that indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that DTS provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="da855-128">Para obter mais informações, consulte [Fast Parse](../fast-parse.md) e [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="da855-128">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span> <span data-ttu-id="da855-129">O valor padrão dessa propriedade é `False`.</span><span class="sxs-lookup"><span data-stu-id="da855-129">The default value of this property is `False`.</span></span><br /><br /> <span data-ttu-id="da855-130">Observação: essa propriedade não está disponível no **Editor de Fonte de Arquivo Simples**, mas pode ser definida por meio do **Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="da855-130">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
  
 <span data-ttu-id="da855-131">Para obter mais informações, consulte [Flat File Source](flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="da855-131">For more information, see [Flat File Source](flat-file-source.md).</span></span>  
  
 <span data-ttu-id="da855-132">**Propriedades personalizadas de destino**</span><span class="sxs-lookup"><span data-stu-id="da855-132">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="da855-133">O destino Arquivo Simples tem propriedades personalizadas e propriedades comuns a todos os componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="da855-133">The Flat File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="da855-134">A tabela a seguir descreve as propriedades personalizadas do destino Arquivo Simples.</span><span class="sxs-lookup"><span data-stu-id="da855-134">The following table describes the custom properties of the Flat File destination.</span></span> <span data-ttu-id="da855-135">Todas as propriedades são de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="da855-135">All properties are read/write.</span></span>  
  
|<span data-ttu-id="da855-136">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="da855-136">Property name</span></span>|<span data-ttu-id="da855-137">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="da855-137">Data Type</span></span>|<span data-ttu-id="da855-138">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="da855-138">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="da855-139">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="da855-139">Header</span></span>|<span data-ttu-id="da855-140">String</span><span class="sxs-lookup"><span data-stu-id="da855-140">String</span></span>|<span data-ttu-id="da855-141">Um bloco de texto inserido no arquivo antes que qualquer dado seja gravado.</span><span class="sxs-lookup"><span data-stu-id="da855-141">A block of text that is inserted in the file before any data is written.</span></span><br /><br /> <span data-ttu-id="da855-142">O valor dessa propriedade pode ser especificado com uma expressão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="da855-142">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="da855-143">Overwrite</span><span class="sxs-lookup"><span data-stu-id="da855-143">Overwrite</span></span>|<span data-ttu-id="da855-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="da855-144">Boolean</span></span>|<span data-ttu-id="da855-145">Um valor que especifica se será substituído ou adicionado a um arquivo de destino existente de mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="da855-145">A value that specifies whether to overwrite or append to an existing destination file that has the same name.</span></span> <span data-ttu-id="da855-146">O valor padrão dessa propriedade é `True`.</span><span class="sxs-lookup"><span data-stu-id="da855-146">The default value of this property is `True`.</span></span>|  
  
 <span data-ttu-id="da855-147">A entrada e as colunas de entrada do destino Arquivo Simples não têm nenhuma propriedade personalizada.</span><span class="sxs-lookup"><span data-stu-id="da855-147">The input and the input columns of the Flat File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="da855-148">Para obter mais informações, consulte [Flat File Destination](flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="da855-148">For more information, see [Flat File Destination](flat-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da855-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da855-149">See Also</span></span>  
 [<span data-ttu-id="da855-150">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="da855-150">Common Properties</span></span>](../common-properties.md)  
  
  
