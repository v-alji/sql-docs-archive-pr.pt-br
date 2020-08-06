---
title: Editor do Gerenciador de conexões de vários arquivos simples (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.columns.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: ad0cb668-0df2-4d4e-9a20-d20692a0b67a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a7f4936f0722754b414076820eda7dcf2dc8dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570099"
---
# <a name="multiple-flat-files-connection-manager-editor-columns-page"></a><span data-ttu-id="bc834-102">Editor do Gerenciador de Conexões de Vários Arquivos Simples (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="bc834-102">Multiple Flat Files Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="bc834-103">Use o nó **Colunas** da caixa de diálogo **Editor do Gerenciador de Conexões de Vários Arquivos Simples** para especificar as informações da linha e da coluna e visualizar o primeiro arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="bc834-103">Use the **Columns** node of the **Multiple Flat Files Connection Manager Editor** dialog box to specify the row and column information, and to preview the first selected file.</span></span>  
  
 <span data-ttu-id="bc834-104">Para saber mais sobre o gerenciador de conexões de Vários Arquivos Simples, consulte [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="bc834-104">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="bc834-105">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="bc834-105">Static Options</span></span>  
 <span data-ttu-id="bc834-106">**Nome do gerenciador de conexões**</span><span class="sxs-lookup"><span data-stu-id="bc834-106">**Connection manager name**</span></span>  
 <span data-ttu-id="bc834-107">Forneça um nome exclusivo para a conexão de Vários Arquivos Simples no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bc834-107">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="bc834-108">O nome fornecido será exibido no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc834-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="bc834-109">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bc834-109">**Description**</span></span>  
 <span data-ttu-id="bc834-110">Descreva a conexão.</span><span class="sxs-lookup"><span data-stu-id="bc834-110">Describe the connection.</span></span> <span data-ttu-id="bc834-111">Como prática recomendável, descreva a conexão em termos de objetivo, para tornar os pacotes autodocumentados e mais fáceis de manter.</span><span class="sxs-lookup"><span data-stu-id="bc834-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="bc834-112">Opções dinâmicas do formato de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="bc834-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="bc834-113">Formato = Delimitado</span><span class="sxs-lookup"><span data-stu-id="bc834-113">Format = Delimited</span></span>  
 <span data-ttu-id="bc834-114">**Delimitador de linha**</span><span class="sxs-lookup"><span data-stu-id="bc834-114">**Row delimiter**</span></span>  
 <span data-ttu-id="bc834-115">Selecione na lista de delimitadores de linha disponíveis ou digite o texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="bc834-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="bc834-116">Valor</span><span class="sxs-lookup"><span data-stu-id="bc834-116">Value</span></span>|<span data-ttu-id="bc834-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc834-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc834-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc834-118">**{CR}{LF}**</span></span>|<span data-ttu-id="bc834-119">As linhas são delimitadas por uma combinação de retorno de carro e avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="bc834-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="bc834-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="bc834-120">**{CR}**</span></span>|<span data-ttu-id="bc834-121">As linhas são delimitadas por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="bc834-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="bc834-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc834-122">**{LF}**</span></span>|<span data-ttu-id="bc834-123">As linhas são delimitadas por um avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="bc834-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="bc834-124">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="bc834-124">**Semicolon {;}**</span></span>|<span data-ttu-id="bc834-125">As linhas são delimitadas por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="bc834-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="bc834-126">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="bc834-126">**Colon {:}**</span></span>|<span data-ttu-id="bc834-127">As linhas são delimitadas por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="bc834-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="bc834-128">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="bc834-128">**Comma {,}**</span></span>|<span data-ttu-id="bc834-129">As linhas são delimitadas por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="bc834-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="bc834-130">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="bc834-130">**Tab {t}**</span></span>|<span data-ttu-id="bc834-131">As linhas são delimitadas por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="bc834-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="bc834-132">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="bc834-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="bc834-133">As linhas são delimitadas por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="bc834-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="bc834-134">**Delimitador de coluna**</span><span class="sxs-lookup"><span data-stu-id="bc834-134">**Column delimiter**</span></span>  
 <span data-ttu-id="bc834-135">Selecione na lista de delimitadores de coluna disponíveis ou digite o texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="bc834-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="bc834-136">Valor</span><span class="sxs-lookup"><span data-stu-id="bc834-136">Value</span></span>|<span data-ttu-id="bc834-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc834-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc834-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc834-138">**{CR}{LF}**</span></span>|<span data-ttu-id="bc834-139">As colunas são delimitadas por uma combinação de retorno de carro e alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="bc834-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="bc834-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="bc834-140">**{CR}**</span></span>|<span data-ttu-id="bc834-141">As colunas são delimitadas por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="bc834-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="bc834-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc834-142">**{LF}**</span></span>|<span data-ttu-id="bc834-143">As colunas são delimitadas por uma alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="bc834-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="bc834-144">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="bc834-144">**Semicolon {;}**</span></span>|<span data-ttu-id="bc834-145">As colunas são delimitadas por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="bc834-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="bc834-146">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="bc834-146">**Colon {:}**</span></span>|<span data-ttu-id="bc834-147">As colunas são delimitadas por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="bc834-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="bc834-148">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="bc834-148">**Comma {,}**</span></span>|<span data-ttu-id="bc834-149">As colunas são delimitadas por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="bc834-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="bc834-150">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="bc834-150">**Tab {t}**</span></span>|<span data-ttu-id="bc834-151">As colunas são delimitadas por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="bc834-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="bc834-152">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="bc834-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="bc834-153">As colunas são delimitadas por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="bc834-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="bc834-154">**Redefinir Colunas**</span><span class="sxs-lookup"><span data-stu-id="bc834-154">**Reset Columns**</span></span>  
 <span data-ttu-id="bc834-155">Remova todas as colunas, exceto as originais, clicando em **Redefinir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="bc834-155">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="bc834-156">Formato = Largura fixa</span><span class="sxs-lookup"><span data-stu-id="bc834-156">Format = Fixed Width</span></span>  
 <span data-ttu-id="bc834-157">**Fonte**</span><span class="sxs-lookup"><span data-stu-id="bc834-157">**Font**</span></span>  
 <span data-ttu-id="bc834-158">Selecione a fonte em que os dados de visualização serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="bc834-158">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="bc834-159">**Colunas de dados de origem**</span><span class="sxs-lookup"><span data-stu-id="bc834-159">**Source data columns**</span></span>  
 <span data-ttu-id="bc834-160">Ajuste a largura da linha deslizando o marcador de linha vertical e ajuste a largura das colunas clicando na régua na parte superior da janela de visualização</span><span class="sxs-lookup"><span data-stu-id="bc834-160">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="bc834-161">**Largura da linha**</span><span class="sxs-lookup"><span data-stu-id="bc834-161">**Row width**</span></span>  
 <span data-ttu-id="bc834-162">Especifique o comprimento da linha antes de adicionar delimitadores para colunas individuais.</span><span class="sxs-lookup"><span data-stu-id="bc834-162">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="bc834-163">Você também pode arrastar a linha vertical na janela de visualização para marcar o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="bc834-163">Or, drag the vertical line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="bc834-164">O valor de largura da linha é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bc834-164">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="bc834-165">**Redefinir Colunas**</span><span class="sxs-lookup"><span data-stu-id="bc834-165">**Reset Columns**</span></span>  
 <span data-ttu-id="bc834-166">Remova todas as colunas, exceto as originais, clicando em **Redefinir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="bc834-166">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="bc834-167">Formato = Irregular à direita</span><span class="sxs-lookup"><span data-stu-id="bc834-167">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc834-168">Arquivos irregulares à direita são arquivos nos quais toda coluna tem uma largura fixa, à exceção da última coluna.</span><span class="sxs-lookup"><span data-stu-id="bc834-168">Ragged right files are those in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="bc834-169">Ela é delimitada pelo delimitador de linha.</span><span class="sxs-lookup"><span data-stu-id="bc834-169">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="bc834-170">**Fonte**</span><span class="sxs-lookup"><span data-stu-id="bc834-170">**Font**</span></span>  
 <span data-ttu-id="bc834-171">Selecione a fonte em que os dados de visualização serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="bc834-171">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="bc834-172">**Colunas de dados de origem**</span><span class="sxs-lookup"><span data-stu-id="bc834-172">**Source data columns**</span></span>  
 <span data-ttu-id="bc834-173">Ajuste a largura da linha deslizando o marcador de linha vertical e ajuste a largura das colunas clicando na régua na parte superior da janela de visualização</span><span class="sxs-lookup"><span data-stu-id="bc834-173">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="bc834-174">**Delimitador de linha**</span><span class="sxs-lookup"><span data-stu-id="bc834-174">**Row delimiter**</span></span>  
 <span data-ttu-id="bc834-175">Selecione na lista de delimitadores de linha disponíveis ou digite o texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="bc834-175">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="bc834-176">Valor</span><span class="sxs-lookup"><span data-stu-id="bc834-176">Value</span></span>|<span data-ttu-id="bc834-177">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc834-177">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc834-178">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc834-178">**{CR}{LF}**</span></span>|<span data-ttu-id="bc834-179">As linhas são delimitadas por uma combinação de retorno de carro e avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="bc834-179">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="bc834-180">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="bc834-180">**{CR}**</span></span>|<span data-ttu-id="bc834-181">As linhas são delimitadas por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="bc834-181">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="bc834-182">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc834-182">**{LF}**</span></span>|<span data-ttu-id="bc834-183">As linhas são delimitadas por um avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="bc834-183">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="bc834-184">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="bc834-184">**Semicolon {;}**</span></span>|<span data-ttu-id="bc834-185">As linhas são delimitadas por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="bc834-185">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="bc834-186">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="bc834-186">**Colon {:}**</span></span>|<span data-ttu-id="bc834-187">As linhas são delimitadas por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="bc834-187">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="bc834-188">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="bc834-188">**Comma {,}**</span></span>|<span data-ttu-id="bc834-189">As linhas são delimitadas por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="bc834-189">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="bc834-190">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="bc834-190">**Tab {t}**</span></span>|<span data-ttu-id="bc834-191">As linhas são delimitadas por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="bc834-191">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="bc834-192">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="bc834-192">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="bc834-193">As linhas são delimitadas por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="bc834-193">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="bc834-194">**Redefinir Colunas**</span><span class="sxs-lookup"><span data-stu-id="bc834-194">**Reset Columns**</span></span>  
 <span data-ttu-id="bc834-195">Remova todas as colunas, exceto as originais, clicando em **Redefinir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="bc834-195">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc834-196">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc834-196">See Also</span></span>  
 <span data-ttu-id="bc834-197">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bc834-197">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bc834-198">[Editor do Gerenciador de conexões de vários arquivos simples &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="bc834-198">[Multiple Flat Files Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="bc834-199">[Editor do Gerenciador de conexões de vários arquivos simples &#40;página avançado&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="bc834-199">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="bc834-200">Editor do Gerenciador de Conexões de Vários Arquivos Simples &#40;Página Visualização&#41;</span><span class="sxs-lookup"><span data-stu-id="bc834-200">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
