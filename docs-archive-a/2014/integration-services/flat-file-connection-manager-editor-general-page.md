---
title: Editor do Gerenciador de conexões de arquivos simples (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.general.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 77296024-5c1a-4f6a-9665-0b50d45d744c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 478c7bcf56e300b47af93862bf66409a3c94b5f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570159"
---
# <a name="flat-file-connection-manager-editor-general-page"></a><span data-ttu-id="ba4e6-102">Editor do Gerenciador de Conexões de Arquivos Simples (página Geral)</span><span class="sxs-lookup"><span data-stu-id="ba4e6-102">Flat File Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="ba4e6-103">Use a página **Geral** da caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos Simples** para selecionar um arquivo e formato de dados.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-103">Use the **General** page of the **Flat File Connection Manager Editor** dialog box to select a file and data format.</span></span> <span data-ttu-id="ba4e6-104">Uma conexão de arquivos simples habilita um pacote a conectar-se com um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-104">A flat file connection enables a package to connect to a text file.</span></span>  
  
 <span data-ttu-id="ba4e6-105">Para obter mais informações sobre o gerenciador de conexões de Arquivo Simples, consulte [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ba4e6-105">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba4e6-106">Opções</span><span class="sxs-lookup"><span data-stu-id="ba4e6-106">Options</span></span>  
 <span data-ttu-id="ba4e6-107">**Nome do gerenciador de conexões**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-107">**Connection manager name**</span></span>  
 <span data-ttu-id="ba4e6-108">Forneça um nome exclusivo para a conexão de arquivos simples no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-108">Provide a unique name for the flat file connection in the workflow.</span></span> <span data-ttu-id="ba4e6-109">O nome fornecido será exibido no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba4e6-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="ba4e6-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-110">**Description**</span></span>  
 <span data-ttu-id="ba4e6-111">Descreva a conexão.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-111">Describe the connection.</span></span> <span data-ttu-id="ba4e6-112">Como prática recomendável, descreva a conexão em termos de objetivo, para tornar os pacotes autodocumentados e mais fáceis de manter.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="ba4e6-113">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-113">**File name**</span></span>  
 <span data-ttu-id="ba4e6-114">Digite o caminho e o nome do arquivo a ser usado na conexão de arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-114">Type the path and file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="ba4e6-115">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-115">**Browse**</span></span>  
 <span data-ttu-id="ba4e6-116">Localize o nome do arquivo a ser usado na conexão de arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-116">Locate the file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="ba4e6-117">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-117">**Locale**</span></span>  
 <span data-ttu-id="ba4e6-118">Especifique a localidade para fornecer informações de idioma específicas para solicitações e formatos de data e hora.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-118">Specify the locale to provide language-specific information for ordering and for date and time formats.</span></span>  
  
 <span data-ttu-id="ba4e6-119">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-119">**Unicode**</span></span>  
 <span data-ttu-id="ba4e6-120">Indique se deve ser usado o Unicode.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-120">Indicate whether to use Unicode.</span></span> <span data-ttu-id="ba4e6-121">Se você usar o Unicode, não poderá especificar uma página de código.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-121">If you use Unicode, you cannot specify a code page.</span></span>  
  
 <span data-ttu-id="ba4e6-122">**Página de código**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-122">**Code page**</span></span>  
 <span data-ttu-id="ba4e6-123">Especifique a página de código do texto não Unicode.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-123">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="ba4e6-124">**Formato**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-124">**Format**</span></span>  
 <span data-ttu-id="ba4e6-125">Indique se o arquivo usa formatação delimitada, de largura fixa ou irregular à direita.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-125">Indicate whether the file uses delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="ba4e6-126">Valor</span><span class="sxs-lookup"><span data-stu-id="ba4e6-126">Value</span></span>|<span data-ttu-id="ba4e6-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="ba4e6-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba4e6-128">Delimitado</span><span class="sxs-lookup"><span data-stu-id="ba4e6-128">Delimited</span></span>|<span data-ttu-id="ba4e6-129">As colunas são separadas por delimitadores, especificados na página **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="ba4e6-129">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="ba4e6-130">Largura fixa</span><span class="sxs-lookup"><span data-stu-id="ba4e6-130">Fixed width</span></span>|<span data-ttu-id="ba4e6-131">As colunas têm uma largura fixa.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-131">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="ba4e6-132">Irregular à direita</span><span class="sxs-lookup"><span data-stu-id="ba4e6-132">Ragged right</span></span>|<span data-ttu-id="ba4e6-133">Arquivos irregulares à direita são arquivos em que toda coluna tem uma largura fixa, à exceção da última coluna.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-133">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="ba4e6-134">Ela é delimitada pelo delimitador de linha.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-134">It is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="ba4e6-135">**Qualificador de texto**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-135">**Text qualifier**</span></span>  
 <span data-ttu-id="ba4e6-136">Especifique o qualificador de texto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-136">Specify the text qualifier to use.</span></span> <span data-ttu-id="ba4e6-137">Por exemplo, você pode especificar que os campos de texto fiquem entre aspas.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-137">For example, you can specify that text fields are enclosed in quotation marks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba4e6-138">Depois de selecionar um qualificador de texto, você não pode selecionar a opção **None** .</span><span class="sxs-lookup"><span data-stu-id="ba4e6-138">After you select a text qualifier, you cannot re-select the **None** option.</span></span> <span data-ttu-id="ba4e6-139">Digite **None** para anular a seleção do qualificador de texto.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-139">Type **None** to de-select the text qualifier.</span></span>  
  
 <span data-ttu-id="ba4e6-140">**Delimitador de linha de cabeçalho**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-140">**Header row delimiter**</span></span>  
 <span data-ttu-id="ba4e6-141">Selecione na lista de delimitadores de linhas de cabeçalho ou digite o texto do delimitador.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-141">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="ba4e6-142">Valor</span><span class="sxs-lookup"><span data-stu-id="ba4e6-142">Value</span></span>|<span data-ttu-id="ba4e6-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="ba4e6-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba4e6-144">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-144">**{CR}{LF}**</span></span>|<span data-ttu-id="ba4e6-145">A linha do cabeçalho é delimitada por uma combinação de retorno de carro e avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-145">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="ba4e6-146">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-146">**{CR}**</span></span>|<span data-ttu-id="ba4e6-147">A linha do cabeçalho é delimitada por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-147">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="ba4e6-148">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-148">**{LF}**</span></span>|<span data-ttu-id="ba4e6-149">A linha do cabeçalho é delimitada por um avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-149">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="ba4e6-150">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-150">**Semicolon {;}**</span></span>|<span data-ttu-id="ba4e6-151">A linha do cabeçalho é delimitada por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-151">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="ba4e6-152">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-152">**Colon {:}**</span></span>|<span data-ttu-id="ba4e6-153">A linha do cabeçalho é delimitada por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-153">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="ba4e6-154">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-154">**Comma {,}**</span></span>|<span data-ttu-id="ba4e6-155">A linha do cabeçalho é delimitada por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-155">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="ba4e6-156">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-156">**Tab {t}**</span></span>|<span data-ttu-id="ba4e6-157">A linha do cabeçalho é delimitada por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-157">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="ba4e6-158">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-158">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="ba4e6-159">A linha do cabeçalho é delimitada por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-159">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="ba4e6-160">**Linhas de cabeçalho a ignorar**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-160">**Header rows to skip**</span></span>  
 <span data-ttu-id="ba4e6-161">Especifique o número de linhas de cabeçalho ou linhas de dados iniciais a ignorar, caso existam.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-161">Specify the number of header rows or initial data rows to skip, if any.</span></span>  
  
 <span data-ttu-id="ba4e6-162">**Nomes de coluna na primeira linha de dados**</span><span class="sxs-lookup"><span data-stu-id="ba4e6-162">**Column names in the first data row**</span></span>  
 <span data-ttu-id="ba4e6-163">Indique se deseja esperar ou fornecer nomes de coluna na primeira linha de dados.</span><span class="sxs-lookup"><span data-stu-id="ba4e6-163">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4e6-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba4e6-164">See Also</span></span>  
 <span data-ttu-id="ba4e6-165">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ba4e6-165">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ba4e6-166">[Editor do Gerenciador de conexões de arquivos simples &#40;página colunas&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="ba4e6-166">[Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="ba4e6-167">[Editor do Gerenciador de conexões de arquivos simples &#40;página avançado&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="ba4e6-167">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="ba4e6-168">Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Visualização&#41;</span><span class="sxs-lookup"><span data-stu-id="ba4e6-168">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
