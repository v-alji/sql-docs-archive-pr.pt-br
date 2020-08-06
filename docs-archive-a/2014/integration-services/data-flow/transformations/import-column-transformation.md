---
title: Importar Transformação de Coluna | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.importcolumntrans.f1
helpviewer_keywords:
- Import Column transformation [Integration Services]
- columns [Integration Services], importing
- importing data, SSIS packages
- inserting data
ms.assetid: ac3b74c1-ef54-4297-8062-1734324fffcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4330438614cce7892e74dc9a1dcbb6680b72972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582047"
---
# <a name="import-column-transformation"></a><span data-ttu-id="af421-102">Transformação Importar Coluna</span><span class="sxs-lookup"><span data-stu-id="af421-102">Import Column Transformation</span></span>
  <span data-ttu-id="af421-103">A transformação Importar Coluna lê dados em arquivos e adiciona esses dados à colunas em um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="af421-103">The Import Column transformation reads data from files and adds the data to columns in a data flow.</span></span> <span data-ttu-id="af421-104">Usando essa transformação, um pacote pode adicionar texto e imagens armazenados em arquivos separados a um fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="af421-104">Using this transformation, a package can add text and images stored in separate files to a data flow.</span></span> <span data-ttu-id="af421-105">Por exemplo, um fluxo de dados que carrega dados em uma tabela que armazena informações de produto pode incluir a transformação Importar Coluna para importar revisões de clientes de cada produto a partir de arquivos e adicionar as revisões ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="af421-105">For example, a data flow that loads data into a table that stores product information can include the Import Column transformation to import customer reviews of each product from files and add the reviews to the data flow.</span></span>  
  
 <span data-ttu-id="af421-106">É possível configurar a transformação Importar Coluna com os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="af421-106">You can configure the Import Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="af421-107">Especificando as colunas às quais a transformação adiciona dados.</span><span class="sxs-lookup"><span data-stu-id="af421-107">Specify the columns to which the transformation adds data.</span></span>  
  
-   <span data-ttu-id="af421-108">Especificando se a transformação espera uma marca de ordem de byte (BOM).</span><span class="sxs-lookup"><span data-stu-id="af421-108">Specify whether the transformation expects a byte-order mark (BOM).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="af421-109">Uma BOM só será esperada se os dados tiverem o tipo de dados de DT_NTEXT.</span><span class="sxs-lookup"><span data-stu-id="af421-109">A BOM is only expected if the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="af421-110">Uma coluna na entrada de transformação contém os nomes de arquivos que mantêm os dados.</span><span class="sxs-lookup"><span data-stu-id="af421-110">A column in the transformation input contains the names of files that hold the data.</span></span> <span data-ttu-id="af421-111">Cada linha do conjunto de dados pode especificar um arquivo diferente.</span><span class="sxs-lookup"><span data-stu-id="af421-111">Each row in the dataset can specify a different file.</span></span> <span data-ttu-id="af421-112">Quando a transformação Importar Coluna processa uma linha, ela lê o nome de arquivo, abre o arquivo correspondente no sistema de arquivos, e carrega o conteúdo do arquivo em uma coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="af421-112">When the Import Column transformation processes a row, it reads the file name, opens the corresponding file in the file system, and loads the file content into an output column.</span></span> <span data-ttu-id="af421-113">O tipo de dados da coluna de saída deve ser DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="af421-113">The data type of the output column must be DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span> <span data-ttu-id="af421-114">Para obter mais informações, consulte [Integration Services Data Types](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="af421-114">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="af421-115">Essa transformação tem uma entrada, uma saída e uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="af421-115">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="configuration-of-the-import-column-transformation"></a><span data-ttu-id="af421-116">Configuração da transformação Importar Coluna</span><span class="sxs-lookup"><span data-stu-id="af421-116">Configuration of the Import Column Transformation</span></span>  
 <span data-ttu-id="af421-117">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="af421-117">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="af421-118">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="af421-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="af421-119">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="af421-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="af421-120">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="af421-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="af421-121">Propriedades personalizadas de Transformação</span><span class="sxs-lookup"><span data-stu-id="af421-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="af421-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="af421-122">Related Tasks</span></span>  
 <span data-ttu-id="af421-123">Para obter informações sobre como definir as propriedades deste componente, consulte [Definir as propriedades de um componente de fluxo de dados](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="af421-123">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af421-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af421-124">See Also</span></span>  
 <span data-ttu-id="af421-125">[Transformação Exportar Colunas](export-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="af421-125">[Export Column Transformation](export-column-transformation.md) </span></span>  
 <span data-ttu-id="af421-126">[Fluxo de Dados](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="af421-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="af421-127">Transformações do Integration Services</span><span class="sxs-lookup"><span data-stu-id="af421-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
