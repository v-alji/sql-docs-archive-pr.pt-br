---
title: Editor de destino de processamento de dimensões (página avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.advanced.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5be80cbbfb6871594d7481ccc0f9444d014885e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582548"
---
# <a name="dimension-processing-destination-editor-advanced-page"></a><span data-ttu-id="1b7c7-102">Editor de Destino de Processamento de Dimensões (página Avançado)</span><span class="sxs-lookup"><span data-stu-id="1b7c7-102">Dimension Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="1b7c7-103">Use a página **Avançado** da caixa de diálogo **Editor de Destino de Processamento de Dimensões** para configurar o tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-103">Use the **Advanced** page of the **Dimension Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="1b7c7-104">Para saber mais sobre o destino de Processamento de Dimensões, consulte [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="1b7c7-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1b7c7-105">Opções</span><span class="sxs-lookup"><span data-stu-id="1b7c7-105">Options</span></span>  
 <span data-ttu-id="1b7c7-106">**Usar configuração de erro padrão.**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-106">**Use default error configuration.**</span></span>  
 <span data-ttu-id="1b7c7-107">Especifique se a manipulação de erros padrão do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-107">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="1b7c7-108">Por padrão, esse valor é `True`.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-108">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="1b7c7-109">**Ação de erro de chave**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-109">**Key error action**</span></span>  
 <span data-ttu-id="1b7c7-110">Especifique como manipular registros que possuem valores de chave inaceitáveis.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-110">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="1b7c7-111">Valor</span><span class="sxs-lookup"><span data-stu-id="1b7c7-111">Value</span></span>|<span data-ttu-id="1b7c7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b7c7-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b7c7-113">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-113">**ConvertToUnknown**</span></span>|<span data-ttu-id="1b7c7-114">Converta o valor de chave inaceitável para o valor `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-114">Convert the unacceptable key value to the `UnknownMember` value.</span></span>|  
|<span data-ttu-id="1b7c7-115">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-115">**DiscardRecord**</span></span>|<span data-ttu-id="1b7c7-116">Descarte o registro.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-116">Discard the record.</span></span>|  
  
 <span data-ttu-id="1b7c7-117">**Ignorar erros**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-117">**Ignore errors**</span></span>  
 <span data-ttu-id="1b7c7-118">Especifique se os erros devem ser ignorados.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-118">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="1b7c7-119">**Parar se houver erro**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-119">**Stop on error**</span></span>  
 <span data-ttu-id="1b7c7-120">Especifique se o processamento deve parar quando ocorrer erro.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-120">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="1b7c7-121">**Número de erros**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-121">**Number of errors**</span></span>  
 <span data-ttu-id="1b7c7-122">Caso tenha selecionado **Parar se houver erro**, especifique o limite de erros sob o qual o processamento deve parar.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-122">Specify the error threshold at which processing should stop, if you have selected **Stop on errors**.</span></span>  
  
 <span data-ttu-id="1b7c7-123">**Ação se houver erro**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-123">**On error action**</span></span>  
 <span data-ttu-id="1b7c7-124">Caso tenha selecionado **Parar se houver erro**, especifique a ação a ser tomada quando o limite de erros for atingido.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-124">Specify the action to take when the error threshold is reached, if you have selected **Stop on errors**.</span></span>  
  
|<span data-ttu-id="1b7c7-125">Valor</span><span class="sxs-lookup"><span data-stu-id="1b7c7-125">Value</span></span>|<span data-ttu-id="1b7c7-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b7c7-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b7c7-127">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-127">**StopProcessing**</span></span>|<span data-ttu-id="1b7c7-128">Pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-128">Stop processing.</span></span>|  
|<span data-ttu-id="1b7c7-129">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-129">**StopLogging**</span></span>|<span data-ttu-id="1b7c7-130">Pare de registrar os erros.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-130">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="1b7c7-131">**Chave não encontrada**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-131">**Key not found**</span></span>  
 <span data-ttu-id="1b7c7-132">Especifique a ação a ser tomada mediante erro de chave não encontrada.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-132">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="1b7c7-133">Por padrão, este valor é **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-133">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="1b7c7-134">Valor</span><span class="sxs-lookup"><span data-stu-id="1b7c7-134">Value</span></span>|<span data-ttu-id="1b7c7-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b7c7-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b7c7-136">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-136">**IgnoreError**</span></span>|<span data-ttu-id="1b7c7-137">Ignore o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-137">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="1b7c7-138">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-138">**ReportAndContinue**</span></span>|<span data-ttu-id="1b7c7-139">Relate o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-139">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="1b7c7-140">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-140">**ReportAndStop**</span></span>|<span data-ttu-id="1b7c7-141">Relate o erro e pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-141">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="1b7c7-142">**Chave duplicada**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-142">**Duplicate key**</span></span>  
 <span data-ttu-id="1b7c7-143">Especifique a ação a ser tomada mediante erro de chave duplicada.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-143">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="1b7c7-144">Por padrão, esse valor é **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-144">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="1b7c7-145">Valor</span><span class="sxs-lookup"><span data-stu-id="1b7c7-145">Value</span></span>|<span data-ttu-id="1b7c7-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b7c7-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b7c7-147">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-147">**IgnoreError**</span></span>|<span data-ttu-id="1b7c7-148">Ignore o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-148">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="1b7c7-149">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-149">**ReportAndContinue**</span></span>|<span data-ttu-id="1b7c7-150">Relate o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-150">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="1b7c7-151">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-151">**ReportAndStop**</span></span>|<span data-ttu-id="1b7c7-152">Relate o erro e pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-152">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="1b7c7-153">**Chave nula convertida em desconhecida**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-153">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="1b7c7-154">Especifique a ação a ser tomada quando uma chave nula tiver sido convertida no valor `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-154">Specify the action to take when a null key has been converted to the `UnknownMember` value.</span></span> <span data-ttu-id="1b7c7-155">Por padrão, esse valor é **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-155">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="1b7c7-156">Valor</span><span class="sxs-lookup"><span data-stu-id="1b7c7-156">Value</span></span>|<span data-ttu-id="1b7c7-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b7c7-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b7c7-158">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-158">**IgnoreError**</span></span>|<span data-ttu-id="1b7c7-159">Ignore o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-159">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="1b7c7-160">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-160">**ReportAndContinue**</span></span>|<span data-ttu-id="1b7c7-161">Relate o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-161">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="1b7c7-162">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-162">**ReportAndStop**</span></span>|<span data-ttu-id="1b7c7-163">Relate o erro e pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-163">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="1b7c7-164">**Chave nula não permitida**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-164">**Null key not allowed**</span></span>  
 <span data-ttu-id="1b7c7-165">Especifique a ação a ser tomada quando chaves nulas não forem permitidas, e uma chave nula for encontrada.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-165">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="1b7c7-166">Por padrão, este valor é **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-166">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="1b7c7-167">Valor</span><span class="sxs-lookup"><span data-stu-id="1b7c7-167">Value</span></span>|<span data-ttu-id="1b7c7-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b7c7-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b7c7-169">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-169">**IgnoreError**</span></span>|<span data-ttu-id="1b7c7-170">Ignore o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-170">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="1b7c7-171">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-171">**ReportAndContinue**</span></span>|<span data-ttu-id="1b7c7-172">Relate o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-172">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="1b7c7-173">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-173">**ReportAndStop**</span></span>|<span data-ttu-id="1b7c7-174">Relate o erro e pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-174">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="1b7c7-175">**Caminho do log de erros**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-175">**Error log path**</span></span>  
 <span data-ttu-id="1b7c7-176">Para selecionar um destino, digite o caminho do log de erros ou clique no botão **Procurar(...)**.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-176">Type the path of the error log, or click the **browse(...)** button to select a destination.</span></span>  
  
 <span data-ttu-id="1b7c7-177">**Procurar (...)**</span><span class="sxs-lookup"><span data-stu-id="1b7c7-177">**Browse (...)**</span></span>  
 <span data-ttu-id="1b7c7-178">Selecione um caminho para o log de erros.</span><span class="sxs-lookup"><span data-stu-id="1b7c7-178">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b7c7-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1b7c7-179">See Also</span></span>  
 <span data-ttu-id="1b7c7-180">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1b7c7-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="1b7c7-181">[Editor de destino de processamento de dimensões &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1b7c7-181">[Dimension Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="1b7c7-182">Editor de Destino de Processamento de Dimensões &#40;página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="1b7c7-182">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)  
  
  
