---
title: Propriedades personalizadas de arquivo bruto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7e81f7e1-fac0-4b57-b145-8f1b9e4720bf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7614c03fbf44f37597e586549e306d01c28b523d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571472"
---
# <a name="raw-file-custom-properties"></a><span data-ttu-id="27e3c-102">Propriedades personalizadas de arquivo bruto</span><span class="sxs-lookup"><span data-stu-id="27e3c-102">Raw File Custom Properties</span></span>
  <span data-ttu-id="27e3c-103">**Propriedades personalizadas de fontes**</span><span class="sxs-lookup"><span data-stu-id="27e3c-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="27e3c-104">A fonte Arquivo Bruto tem as propriedades personalizadas e as propriedades comuns a todos os componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="27e3c-104">The Raw File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="27e3c-105">A tabela a seguir descreve as propriedades personalizadas da fonte de Arquivo Bruto.</span><span class="sxs-lookup"><span data-stu-id="27e3c-105">The following table describes the custom properties of the Raw File source.</span></span> <span data-ttu-id="27e3c-106">Todas as propriedades são de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="27e3c-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="27e3c-107">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="27e3c-107">Property name</span></span>|<span data-ttu-id="27e3c-108">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="27e3c-108">Data Type</span></span>|<span data-ttu-id="27e3c-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="27e3c-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="27e3c-110">AccessMode</span><span class="sxs-lookup"><span data-stu-id="27e3c-110">AccessMode</span></span>|<span data-ttu-id="27e3c-111">Inteiro (enumeração)</span><span class="sxs-lookup"><span data-stu-id="27e3c-111">Integer (enumeration)</span></span>|<span data-ttu-id="27e3c-112">O modo usado para acessar os dados brutos.</span><span class="sxs-lookup"><span data-stu-id="27e3c-112">The mode used to access the raw data.</span></span> <span data-ttu-id="27e3c-113">Os valores possíveis são `File name` (0) e `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="27e3c-113">The possible values are `File name` (0) and `File name from variable` (1).</span></span> <span data-ttu-id="27e3c-114">O valor padrão é `File name` (0).</span><span class="sxs-lookup"><span data-stu-id="27e3c-114">The default value is `File name` (0).</span></span>|  
|<span data-ttu-id="27e3c-115">FileName</span><span class="sxs-lookup"><span data-stu-id="27e3c-115">FileName</span></span>|<span data-ttu-id="27e3c-116">String</span><span class="sxs-lookup"><span data-stu-id="27e3c-116">String</span></span>|<span data-ttu-id="27e3c-117">O caminho e o nome do arquivo do arquivo de origem.</span><span class="sxs-lookup"><span data-stu-id="27e3c-117">The path and file name of the source file.</span></span>|  
  
 <span data-ttu-id="27e3c-118">A saída e as colunas de saída da fonte Arquivo Bruto não têm nenhuma propriedade personalizada.</span><span class="sxs-lookup"><span data-stu-id="27e3c-118">The output and the output columns of the Raw File source have no custom properties.</span></span>  
  
 <span data-ttu-id="27e3c-119">Para obter mais informações, consulte [Raw File Source](raw-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="27e3c-119">For more information, see [Raw File Source](raw-file-source.md).</span></span>  
  
 <span data-ttu-id="27e3c-120">**Propriedades personalizadas de destino**</span><span class="sxs-lookup"><span data-stu-id="27e3c-120">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="27e3c-121">O destino Arquivo Bruto tem propriedades personalizadas e propriedades comuns a todos os componentes de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="27e3c-121">The Raw File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="27e3c-122">A tabela a seguir descreve as propriedades personalizadas do destino Arquivo Bruto.</span><span class="sxs-lookup"><span data-stu-id="27e3c-122">The following table describes the custom properties of the Raw File destination.</span></span> <span data-ttu-id="27e3c-123">Todas as propriedades são de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="27e3c-123">All properties are read/write.</span></span>  
  
|<span data-ttu-id="27e3c-124">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="27e3c-124">Property name</span></span>|<span data-ttu-id="27e3c-125">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="27e3c-125">Data Type</span></span>|<span data-ttu-id="27e3c-126">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="27e3c-126">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="27e3c-127">AccessMode</span><span class="sxs-lookup"><span data-stu-id="27e3c-127">AccessMode</span></span>|<span data-ttu-id="27e3c-128">Inteiro (enumeração)</span><span class="sxs-lookup"><span data-stu-id="27e3c-128">Integer (enumeration)</span></span>|<span data-ttu-id="27e3c-129">Um valor que especifica se a propriedade FileName contém um nome de arquivo ou o nome de uma variável que contenha um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="27e3c-129">A value that specifies whether the FileName property contains a file name, or the name of a variable that contains a file name.</span></span> <span data-ttu-id="27e3c-130">As opções são `File name` (0) e `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="27e3c-130">The options are `File name` (0) and `File name from variable` (1).</span></span>|  
|<span data-ttu-id="27e3c-131">FileName</span><span class="sxs-lookup"><span data-stu-id="27e3c-131">FileName</span></span>|<span data-ttu-id="27e3c-132">String</span><span class="sxs-lookup"><span data-stu-id="27e3c-132">String</span></span>|<span data-ttu-id="27e3c-133">O nome do arquivo no qual o destino Arquivo Bruto grava.</span><span class="sxs-lookup"><span data-stu-id="27e3c-133">The name of the file to which the Raw File destination writes.</span></span>|  
|<span data-ttu-id="27e3c-134">WriteOption</span><span class="sxs-lookup"><span data-stu-id="27e3c-134">WriteOption</span></span>|<span data-ttu-id="27e3c-135">Inteiro (enumeração)</span><span class="sxs-lookup"><span data-stu-id="27e3c-135">Integer (enumeration)</span></span>|<span data-ttu-id="27e3c-136">Um valor que especifica se o destino Arquivo Bruto exclui um arquivo existente de mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="27e3c-136">A value that specifies whether the Raw File destination deletes an existing file that has the same name.</span></span> <span data-ttu-id="27e3c-137">As opções são `Create Always` (0), `Create Once` (1), `Truncate and Append` (3) e `Append` (2).</span><span class="sxs-lookup"><span data-stu-id="27e3c-137">The options are `Create Always` (0), `Create Once` (1), `Truncate and Append` (3), and `Append` (2).</span></span> <span data-ttu-id="27e3c-138">O valor padrão dessa propriedade é `Create Always` (0).</span><span class="sxs-lookup"><span data-stu-id="27e3c-138">The default value of this property is `Create Always` (0).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="27e3c-139">Uma operação de acréscimo requer que os metadados dos dados acrescentados correspondam aos metadados dos dados já existentes no arquivo.</span><span class="sxs-lookup"><span data-stu-id="27e3c-139">An append operation requires the metadata of the appended data to match the metadata of the data already present in the file.</span></span>  
  
 <span data-ttu-id="27e3c-140">A entrada e as colunas de entrada do destino Arquivo Bruto não têm nenhuma propriedade personalizada.</span><span class="sxs-lookup"><span data-stu-id="27e3c-140">The input and the input columns of the Raw File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="27e3c-141">Para obter mais informações, consulte [Raw File Destination](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="27e3c-141">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e3c-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27e3c-142">See Also</span></span>  
 [<span data-ttu-id="27e3c-143">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="27e3c-143">Common Properties</span></span>](../common-properties.md)  
  
  
