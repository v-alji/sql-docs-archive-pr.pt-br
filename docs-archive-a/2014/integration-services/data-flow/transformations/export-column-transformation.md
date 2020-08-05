---
title: Transformação Exportar Colunas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exportcolumntrans.f1
helpviewer_keywords:
- exporting data
- append options [Integration Services]
- Export Column transformation [Integration Services]
- columns [Integration Services], exporting
- inserting data
- truncate options [Integration Services]
ms.assetid: 678d2dfc-e40c-4fbb-b2cc-42fffc44478a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7ed2bef02d75b72870514e2333d2fa58720fb60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570784"
---
# <a name="export-column-transformation"></a><span data-ttu-id="16e93-102">Transformação Exportar Colunas</span><span class="sxs-lookup"><span data-stu-id="16e93-102">Export Column Transformation</span></span>
  <span data-ttu-id="16e93-103">A transformação Exportar Coluna lê dados em um fluxo de dados e os insere em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="16e93-103">The Export Column transformation reads data in a data flow and inserts the data into a file.</span></span> <span data-ttu-id="16e93-104">Por exemplo, se o fluxo de dados contiver informações de produtos, como uma imagem de cada produto, você poderá usar a transformação Exportar Coluna para salvar essas imagens em arquivos.</span><span class="sxs-lookup"><span data-stu-id="16e93-104">For example, if the data flow contains product information, such as a picture of each product, you could use the Export Column transformation to save the images to files.</span></span>  
  
## <a name="append-and-truncate-options"></a><span data-ttu-id="16e93-105">Opções de anexar e truncar</span><span class="sxs-lookup"><span data-stu-id="16e93-105">Append and Truncate Options</span></span>  
 <span data-ttu-id="16e93-106">A tabela seguinte descreve como as definições das opções anexar e truncar afetam os resultados.</span><span class="sxs-lookup"><span data-stu-id="16e93-106">The following table describes how the settings for the append and truncate options affect results.</span></span>  
  
|<span data-ttu-id="16e93-107">Acrescentar</span><span class="sxs-lookup"><span data-stu-id="16e93-107">Append</span></span>|<span data-ttu-id="16e93-108">Truncate</span><span class="sxs-lookup"><span data-stu-id="16e93-108">Truncate</span></span>|<span data-ttu-id="16e93-109">O arquivo existe</span><span class="sxs-lookup"><span data-stu-id="16e93-109">File exists</span></span>|<span data-ttu-id="16e93-110">Resultados</span><span class="sxs-lookup"><span data-stu-id="16e93-110">Results</span></span>|  
|------------|--------------|-----------------|-------------|  
|<span data-ttu-id="16e93-111">Falso</span><span class="sxs-lookup"><span data-stu-id="16e93-111">False</span></span>|<span data-ttu-id="16e93-112">Falso</span><span class="sxs-lookup"><span data-stu-id="16e93-112">False</span></span>|<span data-ttu-id="16e93-113">Não</span><span class="sxs-lookup"><span data-stu-id="16e93-113">No</span></span>|<span data-ttu-id="16e93-114">A transformação cria um novo arquivo e grava os dados nele.</span><span class="sxs-lookup"><span data-stu-id="16e93-114">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="16e93-115">True</span><span class="sxs-lookup"><span data-stu-id="16e93-115">True</span></span>|<span data-ttu-id="16e93-116">Falso</span><span class="sxs-lookup"><span data-stu-id="16e93-116">False</span></span>|<span data-ttu-id="16e93-117">Não</span><span class="sxs-lookup"><span data-stu-id="16e93-117">No</span></span>|<span data-ttu-id="16e93-118">A transformação cria um novo arquivo e grava os dados nele.</span><span class="sxs-lookup"><span data-stu-id="16e93-118">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="16e93-119">Falso</span><span class="sxs-lookup"><span data-stu-id="16e93-119">False</span></span>|<span data-ttu-id="16e93-120">True</span><span class="sxs-lookup"><span data-stu-id="16e93-120">True</span></span>|<span data-ttu-id="16e93-121">Não</span><span class="sxs-lookup"><span data-stu-id="16e93-121">No</span></span>|<span data-ttu-id="16e93-122">A transformação cria um novo arquivo e grava os dados nele.</span><span class="sxs-lookup"><span data-stu-id="16e93-122">The transformation creates a new file and writes the data to the file.</span></span>|  
|<span data-ttu-id="16e93-123">True</span><span class="sxs-lookup"><span data-stu-id="16e93-123">True</span></span>|<span data-ttu-id="16e93-124">True</span><span class="sxs-lookup"><span data-stu-id="16e93-124">True</span></span>|<span data-ttu-id="16e93-125">Não</span><span class="sxs-lookup"><span data-stu-id="16e93-125">No</span></span>|<span data-ttu-id="16e93-126">A transformação falha na validação do tempo de design.</span><span class="sxs-lookup"><span data-stu-id="16e93-126">The transformation fails design time validation.</span></span> <span data-ttu-id="16e93-127">Ela não é válida para definir ambas as propriedades como `true`.</span><span class="sxs-lookup"><span data-stu-id="16e93-127">It is not valid to set both properties to `true`.</span></span>|  
|<span data-ttu-id="16e93-128">Falso</span><span class="sxs-lookup"><span data-stu-id="16e93-128">False</span></span>|<span data-ttu-id="16e93-129">Falso</span><span class="sxs-lookup"><span data-stu-id="16e93-129">False</span></span>|<span data-ttu-id="16e93-130">Sim</span><span class="sxs-lookup"><span data-stu-id="16e93-130">Yes</span></span>|<span data-ttu-id="16e93-131">Ocorre um erro em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="16e93-131">A run-time error occurs.</span></span> <span data-ttu-id="16e93-132">O arquivo existe, mas a transformação não pode ser gravada nele.</span><span class="sxs-lookup"><span data-stu-id="16e93-132">The file exists, but the transformation cannot write to it.</span></span>|  
|<span data-ttu-id="16e93-133">Falso</span><span class="sxs-lookup"><span data-stu-id="16e93-133">False</span></span>|<span data-ttu-id="16e93-134">True</span><span class="sxs-lookup"><span data-stu-id="16e93-134">True</span></span>|<span data-ttu-id="16e93-135">Sim</span><span class="sxs-lookup"><span data-stu-id="16e93-135">Yes</span></span>|<span data-ttu-id="16e93-136">A transformação exclui e recria o arquivo e grava os dados nele.</span><span class="sxs-lookup"><span data-stu-id="16e93-136">The transformation deletes and re-creates the file and writes the data to the file.</span></span>|  
|<span data-ttu-id="16e93-137">True</span><span class="sxs-lookup"><span data-stu-id="16e93-137">True</span></span>|<span data-ttu-id="16e93-138">Falso</span><span class="sxs-lookup"><span data-stu-id="16e93-138">False</span></span>|<span data-ttu-id="16e93-139">Sim</span><span class="sxs-lookup"><span data-stu-id="16e93-139">Yes</span></span>|<span data-ttu-id="16e93-140">A transformação abre o arquivo e grava os dados no final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="16e93-140">The transformation opens the file and writes the data at the end of the file.</span></span>|  
|<span data-ttu-id="16e93-141">True</span><span class="sxs-lookup"><span data-stu-id="16e93-141">True</span></span>|<span data-ttu-id="16e93-142">True</span><span class="sxs-lookup"><span data-stu-id="16e93-142">True</span></span>|<span data-ttu-id="16e93-143">Sim</span><span class="sxs-lookup"><span data-stu-id="16e93-143">Yes</span></span>|<span data-ttu-id="16e93-144">A transformação falha na validação do tempo de design.</span><span class="sxs-lookup"><span data-stu-id="16e93-144">The transformation fails design time validation.</span></span> <span data-ttu-id="16e93-145">Ela não é válida para definir ambas as propriedades como `true`.</span><span class="sxs-lookup"><span data-stu-id="16e93-145">It is not valid to set both properties to `true`.</span></span>|  
  
## <a name="configuration-of-the-export-column-transformation"></a><span data-ttu-id="16e93-146">Configuração da transformação Exportar Coluna</span><span class="sxs-lookup"><span data-stu-id="16e93-146">Configuration of the Export Column Transformation</span></span>  
 <span data-ttu-id="16e93-147">Pode-se configurar a transformação Exportar Coluna com os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="16e93-147">You can configure the Export Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="16e93-148">Especifique as colunas de dados e as colunas que contêm o caminho dos arquivos onde os dados são gravados.</span><span class="sxs-lookup"><span data-stu-id="16e93-148">Specify the data columns and the columns that contain the path of files to which to write the data.</span></span>  
  
-   <span data-ttu-id="16e93-149">Especificar se a operação de inserção de dados anexa ou trunca arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="16e93-149">Specify whether the data-insertion operation appends or truncates existing files.</span></span>  
  
-   <span data-ttu-id="16e93-150">Especificar se uma BOM (marca de ordem de byte) é gravada no arquivo.</span><span class="sxs-lookup"><span data-stu-id="16e93-150">Specify whether a byte-order mark (BOM) is written to the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16e93-151">Uma BOM só é gravada quando os dados não são anexados a um arquivo existente e eles são do tipo DT_NTEXT.</span><span class="sxs-lookup"><span data-stu-id="16e93-151">A BOM is written only when the data is not appended to an existing file and the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="16e93-152">A transformação usa pares de colunas de entrada; uma coluna contém um nome de arquivo e a outra contém os dados.</span><span class="sxs-lookup"><span data-stu-id="16e93-152">The transformation uses pairs of input columns: One column contains a file name, and the other column contains data.</span></span> <span data-ttu-id="16e93-153">Cada linha no conjunto de dados pode especificar um arquivo diferente.</span><span class="sxs-lookup"><span data-stu-id="16e93-153">Each row in the data set can specify a different file.</span></span> <span data-ttu-id="16e93-154">Como a transformação processa uma linha, os dados são inseridos no arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="16e93-154">As the transformation processes a row, the data is inserted into the specified file.</span></span> <span data-ttu-id="16e93-155">No tempo de execução, a transformação cria os arquivos caso eles ainda não existam e, posteriormente, grava os dados nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="16e93-155">At run time, the transformation creates the files, if they do not already exist, and then the transformation writes the data to the files.</span></span> <span data-ttu-id="16e93-156">Os dados a serem gravados devem ser do tipo DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="16e93-156">The data to be written must have a DT_TEXT, DT_NTEXT, or DT_IMAGE data type.</span></span> <span data-ttu-id="16e93-157">Para obter mais informações, consulte [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="16e93-157">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="16e93-158">Essa transformação tem uma entrada, uma saída e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="16e93-158">This transformation has one input, one output, and one error output.</span></span>  
  
 <span data-ttu-id="16e93-159">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="16e93-159">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="16e93-160">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Transformação Coluna de Exportação**, consulte [Editor de Transformação Colunas de Exportação &#40;Página Colunas&#41;](../../export-column-transformation-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="16e93-160">For more information about the properties that you can set in the **Export Column Transformation Editor** dialog box, see [Export Column Transformation Editor &#40;Columns Page&#41;](../../export-column-transformation-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="16e93-161">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="16e93-161">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="16e93-162">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="16e93-162">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="16e93-163">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="16e93-163">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="16e93-164">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="16e93-164">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="16e93-165">Para obter mais informações sobre como definir as propriedades, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="16e93-165">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
