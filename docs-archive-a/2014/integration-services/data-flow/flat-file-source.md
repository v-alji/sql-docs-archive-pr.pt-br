---
title: Origem do arquivo simples | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Flat File
- text file reading [Integration Services]
- flat files
- Flat File source
ms.assetid: 4a64f7f3-f25d-4db0-93b3-a29496030e58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b1ca0f38c457256b3f2ed2ddb81bfbd0dc06b6c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685854"
---
# <a name="flat-file-source"></a><span data-ttu-id="7bd5b-102">Fonte de Arquivo Simples</span><span class="sxs-lookup"><span data-stu-id="7bd5b-102">Flat File Source</span></span>
  <span data-ttu-id="7bd5b-103">A fonte de Arquivo Simples lê dados de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-103">The Flat File source reads data from a text file.</span></span> <span data-ttu-id="7bd5b-104">O arquivo de texto pode ser delimitado, ter largura fixa ou formato misto.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-104">The text file can be in delimited, fixed width, or mixed format.</span></span>  
  
-   <span data-ttu-id="7bd5b-105">O formato delimitado usa delimitadores de coluna e linha para definir colunas e linhas.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-105">Delimited format uses column and row delimiters to define columns and rows.</span></span>  
  
-   <span data-ttu-id="7bd5b-106">O formato de largura fixa utiliza a largura para definir colunas e linhas.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-106">Fixed width format uses width to define columns and rows.</span></span> <span data-ttu-id="7bd5b-107">Esse formato também inclui um caractere para preenchimento de campos na capacidade máxima de sua largura.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-107">This format also includes a character for padding fields to their maximum width.</span></span>  
  
-   <span data-ttu-id="7bd5b-108">O formato irregular à direita utiliza largura para definir todas as colunas, exceto a última, que é delimitada pelo delimitador de linha.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-108">Ragged right format uses width to define all columns, except for the last column, which is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="7bd5b-109">Você pode configurar a fonte de Arquivo Simples das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="7bd5b-109">You can configure the Flat File source in the following ways:</span></span>  
  
-   <span data-ttu-id="7bd5b-110">Adicione uma coluna à saída de transformação que contém o nome do arquivo de texto do qual a fonte de Arquivo Simples extrai os dados.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-110">Add a column to the transformation output that contains the name of the text file from which the Flat File source extracts data.</span></span>  
  
-   <span data-ttu-id="7bd5b-111">Especifique se a fonte de Arquivo Simples interpreta cadeias de caracteres de comprimento zero em colunas com valores nulos.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-111">Specify whether the Flat File source interprets zero-length strings in columns as null values.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7bd5b-112">O gerenciador de conexões de Arquivo Simples que a fonte de Arquivo Simples utiliza deve ser configurado para usar um formato delimitado para interpretar cadeias de caracteres de comprimento zero como nulas.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-112">The Flat File connection manager that the Flat File source uses must be configured to use a delimited format to interpret zero-length strings as nulls.</span></span> <span data-ttu-id="7bd5b-113">Se o gerenciador de conexões usar largura fixa ou formatos à direita irregulares, os dados que consistem em espaços não poderão ser interpretados como valores nulos.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-113">If the connection manager uses the fixed width or ragged right formats, data that consists of spaces cannot be interpreted as null values.</span></span>  
  
 <span data-ttu-id="7bd5b-114">As colunas na saída da origem Arquivo Simples incluem a propriedade FastParse.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-114">The output columns in the output of the Flat File source include the FastParse property.</span></span> <span data-ttu-id="7bd5b-115">FastParse indica se a coluna usa as rotinas de análise mais rápidas, mas sem distinção de localidade, que são fornecidas pelo [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , ou as rotinas de análise padrão com distinção de localidade.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-115">FastParse indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="7bd5b-116">Para obter mais informações, consulte [Fast Parse](../fast-parse.md) e [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="7bd5b-116">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span>  
  
 <span data-ttu-id="7bd5b-117">Colunas de saída também incluem a propriedade UseBinaryFormat.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-117">Output columns also include the UseBinaryFormat property.</span></span> <span data-ttu-id="7bd5b-118">Use esta propriedade para implementar o suporte a dados binários, como dados com o formato decimal compactado, em arquivos.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-118">You use this property to implement support for binary data, such as data with the packed decimal format, in files.</span></span> <span data-ttu-id="7bd5b-119">Por padrão, UseBinaryFormat é definido como `false` .</span><span class="sxs-lookup"><span data-stu-id="7bd5b-119">By default UseBinaryFormat is set to `false`.</span></span> <span data-ttu-id="7bd5b-120">Se você quiser usar um formato binário, defina UseBinaryFormat como `true` e o tipo de dados na coluna de saída como `DT_BYTES` .</span><span class="sxs-lookup"><span data-stu-id="7bd5b-120">If you want to use a binary format, set UseBinaryFormat to `true` and the data type on the output column to `DT_BYTES`.</span></span> <span data-ttu-id="7bd5b-121">Ao fazer isso, a fonte de Arquivo Simples ignora a conversão de dados e transfere os dados para a coluna de saída como estão.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-121">When you do this, the Flat File source skips the data conversion and passes the data to the output column as is.</span></span> <span data-ttu-id="7bd5b-122">Você pode usar uma transformação, como Colunas Derivadas ou Conversão de Dados para lançar os dados `DT_BYTES` a um tipo de dados diferente ou pode escrever scripts personalizados em uma transformação de scripts para interpretar os dados.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-122">You can then use a transformation such as the Derived Column or Data Conversion to cast the `DT_BYTES` data to a different data type, or you can write custom script in a Script transformation to interpret the data.</span></span> <span data-ttu-id="7bd5b-123">Você também pode escrever um componente de fluxo de dados personalizado para interpretar os dados.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-123">You can also write a custom data flow component to interpret the data.</span></span> <span data-ttu-id="7bd5b-124">Para obter mais informações sobre quais tipos de dados você pode converter `DT_BYTES` , consulte [Cast &#40;SSIS Expression&#41;](../expressions/cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="7bd5b-124">For more information about which data types you can cast `DT_BYTES` to, see [Cast &#40;SSIS Expression&#41;](../expressions/cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="7bd5b-125">Essa fonte utiliza um gerenciador de conexões de arquivos simples para acessar o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-125">This source uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="7bd5b-126">Definindo propriedades no gerenciador de conexões de arquivos simples, você pode fornecer informações sobre o arquivo e cada coluna nele contido, e especificar como a fonte de Arquivo Simples deverá tratar os dados no arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-126">By setting properties on the Flat File connection manager, you can provide information about the file and each column in it, and specify how the Flat File source should handle the data in the text file.</span></span> <span data-ttu-id="7bd5b-127">Por exemplo, você pode especificar os caracteres que delimitam colunas e linhas no arquivo e o tipo de dados e o comprimento de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-127">For example, you can specify the characters that delimit columns and rows in the file, and the data type and the length of each column.</span></span> <span data-ttu-id="7bd5b-128">Para obter mais informações, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7bd5b-128">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="7bd5b-129">Essa fonte tem uma saída e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-129">This source has one output and one error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-source"></a><span data-ttu-id="7bd5b-130">Configuração da origem Arquivo Simples</span><span class="sxs-lookup"><span data-stu-id="7bd5b-130">Configuration of the Flat File Source</span></span>  
 <span data-ttu-id="7bd5b-131">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7bd5b-132">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Fonte de Arquivo Simples**, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7bd5b-132">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7bd5b-133">Editor de Fonte de Arquivo Simples &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="7bd5b-133">Flat File Source Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="7bd5b-134">Editor de Fonte de Arquivo Simples &#40;Página Colunas&#41;</span><span class="sxs-lookup"><span data-stu-id="7bd5b-134">Flat File Source Editor &#40;Columns Page&#41;</span></span>](../flat-file-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="7bd5b-135">Editor de Fonte de Arquivo Simples &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="7bd5b-135">Flat File Source Editor &#40;Error Output Page&#41;</span></span>](../flat-file-source-editor-error-output-page.md)  
  
 <span data-ttu-id="7bd5b-136">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="7bd5b-136">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="7bd5b-137">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7bd5b-137">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7bd5b-138">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="7bd5b-138">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="7bd5b-139">Propriedades personalizadas de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="7bd5b-139">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="7bd5b-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7bd5b-140">Related Tasks</span></span>  
 <span data-ttu-id="7bd5b-141">Para obter detalhes sobre como definir as propriedades de um componente de fluxo de dados, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="7bd5b-141">For details about how to set properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd5b-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7bd5b-142">See Also</span></span>  
 <span data-ttu-id="7bd5b-143">[Destino de arquivo simples](flat-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="7bd5b-143">[Flat File Destination](flat-file-destination.md) </span></span>  
 [<span data-ttu-id="7bd5b-144">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="7bd5b-144">Data Flow</span></span>](data-flow.md)  
  
  
