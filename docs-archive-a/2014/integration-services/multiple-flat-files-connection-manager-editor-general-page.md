---
title: Editor do Gerenciador de conexões de vários arquivos simples (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.general.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: 00129d43-2772-413b-bdf8-ac5de81cf4a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f30a422794723f216d30e05f0750fb1e974e0920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683596"
---
# <a name="multiple-flat-files-connection-manager-editor-general-page"></a><span data-ttu-id="3027c-102">Editor do Gerenciador de Conexões de Vários Arquivos Simples (página Geral)</span><span class="sxs-lookup"><span data-stu-id="3027c-102">Multiple Flat Files Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="3027c-103">Use a página **Geral** da caixa de diálogo do **Editor do Gerenciador de Conexões de Vários Arquivos Simples** para selecionar um grupo de arquivos que têm o mesmo formato de dados e para especificar seu formato de dados.</span><span class="sxs-lookup"><span data-stu-id="3027c-103">Use the **General** page of the **Multiple Flat Files Connection Manager Editor** dialog box to select a group of files that have the same data format, and to specify their data format.</span></span> <span data-ttu-id="3027c-104">Uma conexão de vários arquivos simples habilita um pacote a conectar-se com um grupo de arquivos de texto que têm o mesmo formato.</span><span class="sxs-lookup"><span data-stu-id="3027c-104">A multiple flat files connection enables a package to connect to a group of text files that have the same format.</span></span>  
  
 <span data-ttu-id="3027c-105">Para saber mais sobre o gerenciador de conexões de Vários Arquivos Simples, consulte [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="3027c-105">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3027c-106">Opções</span><span class="sxs-lookup"><span data-stu-id="3027c-106">Options</span></span>  
 <span data-ttu-id="3027c-107">**Nome do gerenciador de conexões**</span><span class="sxs-lookup"><span data-stu-id="3027c-107">**Connection manager name**</span></span>  
 <span data-ttu-id="3027c-108">Forneça um nome exclusivo para a conexão de Vários Arquivos Simples no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3027c-108">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="3027c-109">O nome fornecido será exibido no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3027c-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="3027c-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3027c-110">**Description**</span></span>  
 <span data-ttu-id="3027c-111">Descreva a conexão.</span><span class="sxs-lookup"><span data-stu-id="3027c-111">Describe the connection.</span></span> <span data-ttu-id="3027c-112">Como prática recomendável, descreva a conexão em termos de objetivo, para tornar os pacotes autodocumentados e mais fáceis de manter.</span><span class="sxs-lookup"><span data-stu-id="3027c-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="3027c-113">**Nomes de arquivo**</span><span class="sxs-lookup"><span data-stu-id="3027c-113">**File names**</span></span>  
 <span data-ttu-id="3027c-114">Digite o caminho e o nome de arquivos para usar na conexão de vários arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="3027c-114">Type the path and file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="3027c-115">Você pode especificar vários arquivos usando curingas, como no exemplo “C:\\*.txt”, ou usando o caractere de barra vertical (|) para separar vários nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3027c-115">You can specify multiple files by using wildcard characters, as in the example "C:\\*.txt", or by using the vertical pipe character (|) to separate multiple file names.</span></span> <span data-ttu-id="3027c-116">Todos os arquivos devem ter o mesmo formato de dados.</span><span class="sxs-lookup"><span data-stu-id="3027c-116">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="3027c-117">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="3027c-117">**Browse**</span></span>  
 <span data-ttu-id="3027c-118">Procure os nomes de arquivo para usar na conexão de vários arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="3027c-118">Browse the file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="3027c-119">Você pode selecionar vários arquivos.</span><span class="sxs-lookup"><span data-stu-id="3027c-119">You can select multiple files.</span></span> <span data-ttu-id="3027c-120">Todos os arquivos devem ter o mesmo formato de dados.</span><span class="sxs-lookup"><span data-stu-id="3027c-120">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="3027c-121">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="3027c-121">**Locale**</span></span>  
 <span data-ttu-id="3027c-122">Especifique a localidade para fornecer informações de classificação e de conversão de data e hora.</span><span class="sxs-lookup"><span data-stu-id="3027c-122">Specify the location to provide information for ordering and for date and time conversion.</span></span>  
  
 <span data-ttu-id="3027c-123">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="3027c-123">**Unicode**</span></span>  
 <span data-ttu-id="3027c-124">Indique se deve ser usado o Unicode.</span><span class="sxs-lookup"><span data-stu-id="3027c-124">Indicate whether to use Unicode.</span></span> <span data-ttu-id="3027c-125">O uso do Unicode impede a especificação de uma página de código.</span><span class="sxs-lookup"><span data-stu-id="3027c-125">Using Unicode precludes specifying a code page.</span></span>  
  
 <span data-ttu-id="3027c-126">**Página de código**</span><span class="sxs-lookup"><span data-stu-id="3027c-126">**Code page**</span></span>  
 <span data-ttu-id="3027c-127">Especifique a página de código do texto não Unicode.</span><span class="sxs-lookup"><span data-stu-id="3027c-127">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="3027c-128">**Formato**</span><span class="sxs-lookup"><span data-stu-id="3027c-128">**Format**</span></span>  
 <span data-ttu-id="3027c-129">Indique se será usada formatação delimitada, de largura fixa ou irregular à direita.</span><span class="sxs-lookup"><span data-stu-id="3027c-129">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span> <span data-ttu-id="3027c-130">Todos os arquivos devem ter o mesmo formato de dados.</span><span class="sxs-lookup"><span data-stu-id="3027c-130">All files must have the same data format.</span></span>  
  
|<span data-ttu-id="3027c-131">Valor</span><span class="sxs-lookup"><span data-stu-id="3027c-131">Value</span></span>|<span data-ttu-id="3027c-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="3027c-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3027c-133">Delimitado</span><span class="sxs-lookup"><span data-stu-id="3027c-133">Delimited</span></span>|<span data-ttu-id="3027c-134">As colunas são separadas por delimitadores, especificados na página **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="3027c-134">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="3027c-135">Largura fixa</span><span class="sxs-lookup"><span data-stu-id="3027c-135">Fixed width</span></span>|<span data-ttu-id="3027c-136">As colunas têm uma largura fixa, especificada arrastando as linhas do marcador na página **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="3027c-136">Columns have a fixed width, specified by dragging marker lines on the **Columns** page.</span></span>|  
|<span data-ttu-id="3027c-137">Irregular à direita</span><span class="sxs-lookup"><span data-stu-id="3027c-137">Ragged right</span></span>|<span data-ttu-id="3027c-138">Em arquivos irregulares à direita, todas as colunas têm uma largura fixa, com exceção da última, que é delimitada pelo delimitador de linha especificado na página **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="3027c-138">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter, specified on the **Columns** page.</span></span>|  
  
 <span data-ttu-id="3027c-139">**Qualificador de texto**</span><span class="sxs-lookup"><span data-stu-id="3027c-139">**Text qualifier**</span></span>  
 <span data-ttu-id="3027c-140">Especifique o qualificador de texto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="3027c-140">Specify the text qualifier to use.</span></span> <span data-ttu-id="3027c-141">Por exemplo, você pode especificar incluir o texto entre aspas.</span><span class="sxs-lookup"><span data-stu-id="3027c-141">For example, you can specify to enclose text with quotation marks.</span></span>  
  
 <span data-ttu-id="3027c-142">**Delimitador de linha de cabeçalho**</span><span class="sxs-lookup"><span data-stu-id="3027c-142">**Header row delimiter**</span></span>  
 <span data-ttu-id="3027c-143">Selecione na lista de delimitadores de linhas de cabeçalho ou digite o texto do delimitador.</span><span class="sxs-lookup"><span data-stu-id="3027c-143">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="3027c-144">Valor</span><span class="sxs-lookup"><span data-stu-id="3027c-144">Value</span></span>|<span data-ttu-id="3027c-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="3027c-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3027c-146">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="3027c-146">**{CR}{LF}**</span></span>|<span data-ttu-id="3027c-147">A linha do cabeçalho é delimitada por uma combinação de retorno de carro e avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="3027c-147">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="3027c-148">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="3027c-148">**{CR}**</span></span>|<span data-ttu-id="3027c-149">A linha do cabeçalho é delimitada por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="3027c-149">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="3027c-150">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="3027c-150">**{LF}**</span></span>|<span data-ttu-id="3027c-151">A linha do cabeçalho é delimitada por um avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="3027c-151">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="3027c-152">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="3027c-152">**Semicolon {;}**</span></span>|<span data-ttu-id="3027c-153">A linha do cabeçalho é delimitada por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="3027c-153">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="3027c-154">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="3027c-154">**Colon {:}**</span></span>|<span data-ttu-id="3027c-155">A linha do cabeçalho é delimitada por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="3027c-155">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="3027c-156">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="3027c-156">**Comma {,}**</span></span>|<span data-ttu-id="3027c-157">A linha do cabeçalho é delimitada por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="3027c-157">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="3027c-158">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="3027c-158">**Tab {t}**</span></span>|<span data-ttu-id="3027c-159">A linha do cabeçalho é delimitada por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="3027c-159">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="3027c-160">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="3027c-160">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="3027c-161">A linha do cabeçalho é delimitada por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="3027c-161">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="3027c-162">**Linhas de cabeçalho a ignorar**</span><span class="sxs-lookup"><span data-stu-id="3027c-162">**Header rows to skip**</span></span>  
 <span data-ttu-id="3027c-163">Especifique o número de linhas de cabeçalho a ignorar, caso existam.</span><span class="sxs-lookup"><span data-stu-id="3027c-163">Specify the number of header rows to skip, if any.</span></span>  
  
 <span data-ttu-id="3027c-164">**Nomes de coluna na primeira linha de dados**</span><span class="sxs-lookup"><span data-stu-id="3027c-164">**Column names in the first data row**</span></span>  
 <span data-ttu-id="3027c-165">Indique se deseja esperar ou fornecer nomes de coluna na primeira linha de dados.</span><span class="sxs-lookup"><span data-stu-id="3027c-165">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3027c-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3027c-166">See Also</span></span>  
 <span data-ttu-id="3027c-167">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3027c-167">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="3027c-168">[Editor do Gerenciador de conexões de vários arquivos simples &#40;página colunas&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="3027c-168">[Multiple Flat Files Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="3027c-169">[Editor do Gerenciador de conexões de vários arquivos simples &#40;página avançado&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="3027c-169">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="3027c-170">Editor do Gerenciador de Conexões de Vários Arquivos Simples &#40;Página Visualização&#41;</span><span class="sxs-lookup"><span data-stu-id="3027c-170">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
