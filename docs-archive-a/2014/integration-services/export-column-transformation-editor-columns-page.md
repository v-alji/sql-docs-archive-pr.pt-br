---
title: Editor de transformação exportar coluna (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileextractortransformation.columns.f1
helpviewer_keywords:
- Export Column Transformation Editor
ms.assetid: b659a5c2-5509-4b5b-9c82-136c971d5c7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 404b404e2328228049ae46fb1c3089b0b4089f0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572125"
---
# <a name="export-column-transformation-editor-columns-page"></a><span data-ttu-id="dcad0-102">Editor de Transformação Exportar Colunas (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="dcad0-102">Export Column Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="dcad0-103">Use a página **Colunas** da caixa de diálogo **Exportar Editor de Transformação Colunas** para especificar as colunas no fluxo de dados a serem extraídas para arquivos.</span><span class="sxs-lookup"><span data-stu-id="dcad0-103">Use the **Columns** page of the **Export Column Transformation Editor** dialog box to specify columns in the data flow to extract to files.</span></span> <span data-ttu-id="dcad0-104">Você pode especificar se a transformação Exportar Coluna acrescenta dados a um arquivo ou substitui um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="dcad0-104">You can specify whether the Export Column transformation appends data to a file or overwrites an existing file.</span></span>  
  
 <span data-ttu-id="dcad0-105">Para saber mais sobre a transformação Exportar Coluna, consulte [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="dcad0-105">To learn more about the Export Column transformation, see [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dcad0-106">Opções</span><span class="sxs-lookup"><span data-stu-id="dcad0-106">Options</span></span>  
 <span data-ttu-id="dcad0-107">**Extrair Coluna**</span><span class="sxs-lookup"><span data-stu-id="dcad0-107">**Extract Column**</span></span>  
 <span data-ttu-id="dcad0-108">Selecione na lista de colunas de entrada que contêm dados de texto ou de imagem.</span><span class="sxs-lookup"><span data-stu-id="dcad0-108">Select from the list of input columns that contain text or image data.</span></span> <span data-ttu-id="dcad0-109">Todas as linhas devem ter definições para **Extrair Coluna** e **Coluna de Caminho de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="dcad0-109">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="dcad0-110">**Coluna de Caminho de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="dcad0-110">**File Path Column**</span></span>  
 <span data-ttu-id="dcad0-111">Selecione na lista de colunas de entrada que contêm caminhos e nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="dcad0-111">Select from the list of input columns that contain file paths and file names.</span></span> <span data-ttu-id="dcad0-112">Todas as linhas devem ter definições para **Extrair Coluna** e **Coluna de Caminho de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="dcad0-112">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="dcad0-113">**Permitir Acréscimo**</span><span class="sxs-lookup"><span data-stu-id="dcad0-113">**Allow Append**</span></span>  
 <span data-ttu-id="dcad0-114">Especifique se a transformação acrescenta dados a arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="dcad0-114">Specify whether the transformation appends data to existing files.</span></span> <span data-ttu-id="dcad0-115">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="dcad0-115">The default is `false`.</span></span>  
  
 <span data-ttu-id="dcad0-116">**Forçar Truncamento**</span><span class="sxs-lookup"><span data-stu-id="dcad0-116">**Force Truncate**</span></span>  
 <span data-ttu-id="dcad0-117">Especifique se a transformação exclui o conteúdo dos arquivos existentes antes de gravar dados.</span><span class="sxs-lookup"><span data-stu-id="dcad0-117">Specify whether the transformation deletes the contents of existing files before writing data.</span></span> <span data-ttu-id="dcad0-118">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="dcad0-118">The default is `false`.</span></span>  
  
 <span data-ttu-id="dcad0-119">**Gravar BOM**</span><span class="sxs-lookup"><span data-stu-id="dcad0-119">**Write BOM**</span></span>  
 <span data-ttu-id="dcad0-120">Especifique se deve ser gravada uma BOM (marca de ordem de byte) no arquivo.</span><span class="sxs-lookup"><span data-stu-id="dcad0-120">Specify whether to write a byte-order mark (BOM) to the file.</span></span> <span data-ttu-id="dcad0-121">Uma BOM só é gravada se os dados forem do tipo `DT_NTEXT`ou DT_WSTR e não estiverem anexados a um arquivo de dados existente.</span><span class="sxs-lookup"><span data-stu-id="dcad0-121">A BOM is only written if the data has the `DT_NTEXT` or DT_WSTR data type and is not appended to an existing data file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcad0-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dcad0-122">See Also</span></span>  
 <span data-ttu-id="dcad0-123">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dcad0-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="dcad0-124">Exportar Editor de Transformação Colunas &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="dcad0-124">Export Column Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/export-column-transformation-editor-error-output-page.md)  
  
  
