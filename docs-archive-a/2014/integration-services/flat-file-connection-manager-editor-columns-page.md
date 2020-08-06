---
title: Editor do Gerenciador de conexões de arquivos simples (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.columns.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 40ce7537-abd0-4973-97fd-6ccb90fddfa0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6ce579f73922d2eaa2c48e98a98f52cd5836f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570157"
---
# <a name="flat-file-connection-manager-editor-columns-page"></a><span data-ttu-id="2ab4e-102">Editor do Gerenciador de Conexões de Arquivos Simples (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="2ab4e-102">Flat File Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="2ab4e-103">Use a página **Colunas** da caixa de diálogo **Editor do Gerenciador de Conexões de Arquivos Simples** para especificar a linha e informações da coluna, e visualizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-103">Use the **Columns** page of the **Flat File Connection Manager Editor** dialog box to specify the row and column information, and to preview the file.</span></span>  
  
 <span data-ttu-id="2ab4e-104">Para obter mais informações sobre o gerenciador de conexões de Arquivo Simples, consulte [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2ab4e-104">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="2ab4e-105">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="2ab4e-105">Static Options</span></span>  
 <span data-ttu-id="2ab4e-106">**Nome do gerenciador de conexões**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-106">**Connection manager name**</span></span>  
 <span data-ttu-id="2ab4e-107">Forneça um nome exclusivo para a conexão de Arquivo Simples no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-107">Provide a unique name for the Flat File connection in the workflow.</span></span> <span data-ttu-id="2ab4e-108">O nome fornecido será exibido no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ab4e-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="2ab4e-109">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-109">**Description**</span></span>  
 <span data-ttu-id="2ab4e-110">Descreva a conexão.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-110">Describe the connection.</span></span> <span data-ttu-id="2ab4e-111">Como prática recomendável, descreva a conexão em termos de objetivo, para tornar os pacotes autodocumentados e mais fáceis de manter.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="2ab4e-112">Opções dinâmicas do formato de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="2ab4e-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="2ab4e-113">Formato = Delimitado</span><span class="sxs-lookup"><span data-stu-id="2ab4e-113">Format = Delimited</span></span>  
 <span data-ttu-id="2ab4e-114">**Delimitador de linha**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-114">**Row delimiter**</span></span>  
 <span data-ttu-id="2ab4e-115">Selecione na lista de delimitadores de linha disponíveis ou digite o texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="2ab4e-116">Valor</span><span class="sxs-lookup"><span data-stu-id="2ab4e-116">Value</span></span>|<span data-ttu-id="2ab4e-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ab4e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ab4e-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-118">**{CR}{LF}**</span></span>|<span data-ttu-id="2ab4e-119">As linhas são delimitadas por uma combinação de retorno de carro e avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="2ab4e-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-120">**{CR}**</span></span>|<span data-ttu-id="2ab4e-121">As linhas são delimitadas por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="2ab4e-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-122">**{LF}**</span></span>|<span data-ttu-id="2ab4e-123">As linhas são delimitadas por um avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="2ab4e-124">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-124">**Semicolon {;}**</span></span>|<span data-ttu-id="2ab4e-125">As linhas são delimitadas por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="2ab4e-126">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-126">**Colon {:}**</span></span>|<span data-ttu-id="2ab4e-127">As linhas são delimitadas por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="2ab4e-128">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-128">**Comma {,}**</span></span>|<span data-ttu-id="2ab4e-129">As linhas são delimitadas por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="2ab4e-130">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-130">**Tab {t}**</span></span>|<span data-ttu-id="2ab4e-131">As linhas são delimitadas por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="2ab4e-132">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="2ab4e-133">As linhas são delimitadas por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="2ab4e-134">**Delimitador de coluna**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-134">**Column delimiter**</span></span>  
 <span data-ttu-id="2ab4e-135">Selecione na lista de delimitadores de coluna disponíveis ou digite o texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="2ab4e-136">Valor</span><span class="sxs-lookup"><span data-stu-id="2ab4e-136">Value</span></span>|<span data-ttu-id="2ab4e-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ab4e-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ab4e-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-138">**{CR}{LF}**</span></span>|<span data-ttu-id="2ab4e-139">As colunas são delimitadas por uma combinação de retorno de carro e alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="2ab4e-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-140">**{CR}**</span></span>|<span data-ttu-id="2ab4e-141">As colunas são delimitadas por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="2ab4e-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-142">**{LF}**</span></span>|<span data-ttu-id="2ab4e-143">As colunas são delimitadas por uma alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="2ab4e-144">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-144">**Semicolon {;}**</span></span>|<span data-ttu-id="2ab4e-145">As colunas são delimitadas por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="2ab4e-146">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-146">**Colon {:}**</span></span>|<span data-ttu-id="2ab4e-147">As colunas são delimitadas por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="2ab4e-148">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-148">**Comma {,}**</span></span>|<span data-ttu-id="2ab4e-149">As colunas são delimitadas por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="2ab4e-150">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-150">**Tab {t}**</span></span>|<span data-ttu-id="2ab4e-151">As colunas são delimitadas por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="2ab4e-152">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="2ab4e-153">As colunas são delimitadas por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="2ab4e-154">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-154">**Refresh**</span></span>  
 <span data-ttu-id="2ab4e-155">Exiba o efeito de alterar os delimitadores a serem ignorados clicando em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-155">View the effect of changing the delimiters to skip by clicking **Refresh**.</span></span> <span data-ttu-id="2ab4e-156">Esse botão só ficará visível após você alterar outras opções de conexão.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-156">This button only becomes visible after you have changed other connection options.</span></span>  
  
 <span data-ttu-id="2ab4e-157">**Visualizar linhas**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-157">**Preview rows**</span></span>  
 <span data-ttu-id="2ab4e-158">Exiba os dados de amostra do arquivo simples, dividido em colunas e linhas, usando as opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-158">View sample data in the flat file, divided into columns and rows by using the options selected.</span></span>  
  
 <span data-ttu-id="2ab4e-159">**Redefinir Colunas**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-159">**Reset Columns**</span></span>  
 <span data-ttu-id="2ab4e-160">Remova todas as colunas, exceto as originais, clicando em **Redefinir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-160">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="2ab4e-161">Formato = Largura fixa</span><span class="sxs-lookup"><span data-stu-id="2ab4e-161">Format = Fixed Width</span></span>  
 <span data-ttu-id="2ab4e-162">**Fonte**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-162">**Font**</span></span>  
 <span data-ttu-id="2ab4e-163">Selecione a fonte em que os dados de visualização serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-163">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="2ab4e-164">**Colunas de dados de origem**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-164">**Source data columns**</span></span>  
 <span data-ttu-id="2ab4e-165">Ajuste a largura da linha deslizando o marcador de linha vertical vermelho e ajuste a largura das colunas clicando na régua na parte superior da janela de visualização</span><span class="sxs-lookup"><span data-stu-id="2ab4e-165">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="2ab4e-166">**Largura da linha**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-166">**Row width**</span></span>  
 <span data-ttu-id="2ab4e-167">Especifique o comprimento da linha antes de adicionar delimitadores para colunas individuais.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-167">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="2ab4e-168">Você também pode arrastar a linha vermelha vertical na janela de visualização para marcar o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-168">Or, drag the vertical red line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="2ab4e-169">O valor de largura da linha é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-169">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="2ab4e-170">**Redefinir Colunas**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-170">**Reset Columns**</span></span>  
 <span data-ttu-id="2ab4e-171">Remova todas as colunas, exceto as originais, clicando em **Redefinir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-171">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="2ab4e-172">Formato = Irregular à direita</span><span class="sxs-lookup"><span data-stu-id="2ab4e-172">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ab4e-173">Arquivos irregulares à direita são arquivos em que toda coluna tem uma largura fixa, à exceção da última coluna.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-173">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="2ab4e-174">Ela é delimitada pelo delimitador de linha.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-174">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="2ab4e-175">**Fonte**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-175">**Font**</span></span>  
 <span data-ttu-id="2ab4e-176">Selecione a fonte em que os dados de visualização serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-176">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="2ab4e-177">**Colunas de dados de origem**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-177">**Source data columns**</span></span>  
 <span data-ttu-id="2ab4e-178">Ajuste a largura da linha deslizando o marcador de linha vertical vermelho e ajuste a largura das colunas clicando na régua na parte superior da janela de visualização</span><span class="sxs-lookup"><span data-stu-id="2ab4e-178">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="2ab4e-179">**Delimitador de linha**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-179">**Row delimiter**</span></span>  
 <span data-ttu-id="2ab4e-180">Selecione na lista de delimitadores de linha disponíveis ou digite o texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-180">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="2ab4e-181">Valor</span><span class="sxs-lookup"><span data-stu-id="2ab4e-181">Value</span></span>|<span data-ttu-id="2ab4e-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ab4e-182">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ab4e-183">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-183">**{CR}{LF}**</span></span>|<span data-ttu-id="2ab4e-184">As linhas são delimitadas por uma combinação de retorno de carro e avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-184">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="2ab4e-185">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-185">**{CR}**</span></span>|<span data-ttu-id="2ab4e-186">As linhas são delimitadas por um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-186">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="2ab4e-187">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-187">**{LF}**</span></span>|<span data-ttu-id="2ab4e-188">As linhas são delimitadas por um avanço de linha.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-188">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="2ab4e-189">**Ponto-e-vírgula {;}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-189">**Semicolon {;}**</span></span>|<span data-ttu-id="2ab4e-190">As linhas são delimitadas por um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-190">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="2ab4e-191">**Dois-pontos {:}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-191">**Colon {:}**</span></span>|<span data-ttu-id="2ab4e-192">As linhas são delimitadas por dois-pontos.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-192">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="2ab4e-193">**Vírgula {,}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-193">**Comma {,}**</span></span>|<span data-ttu-id="2ab4e-194">As linhas são delimitadas por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-194">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="2ab4e-195">**Tabulação {t}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-195">**Tab {t}**</span></span>|<span data-ttu-id="2ab4e-196">As linhas são delimitadas por uma tabulação.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-196">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="2ab4e-197">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-197">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="2ab4e-198">As linhas são delimitadas por uma barra vertical.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-198">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="2ab4e-199">**Redefinir Colunas**</span><span class="sxs-lookup"><span data-stu-id="2ab4e-199">**Reset Columns**</span></span>  
 <span data-ttu-id="2ab4e-200">Remova todas as colunas, exceto as originais, clicando em **Redefinir Colunas**.</span><span class="sxs-lookup"><span data-stu-id="2ab4e-200">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab4e-201">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ab4e-201">See Also</span></span>  
 <span data-ttu-id="2ab4e-202">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2ab4e-202">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2ab4e-203">[Editor do Gerenciador de conexões de arquivos simples &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="2ab4e-203">[Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="2ab4e-204">[Editor do Gerenciador de conexões de arquivos simples &#40;página avançado&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="2ab4e-204">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="2ab4e-205">Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Visualização&#41;</span><span class="sxs-lookup"><span data-stu-id="2ab4e-205">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
