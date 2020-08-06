---
title: Editor de destino de processamento de partições (página avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.advanced.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 2039ee0f-069d-479d-90b2-2a12481b1162
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12845ecd644eabd949ea37fbb18ba6cc9cf342f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570101"
---
# <a name="partition-processing-destination-editor-advanced-page"></a><span data-ttu-id="2208b-102">Editor de Destino de Processamento de Partições (página Avançado)</span><span class="sxs-lookup"><span data-stu-id="2208b-102">Partition Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="2208b-103">Use a página **Avançado** da caixa de diálogo **Editor de Destino de Processamento de Partições** para configurar a manipulação de erros.</span><span class="sxs-lookup"><span data-stu-id="2208b-103">Use the **Advanced** page of the **Partition Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="2208b-104">Para saber mais sobre o destino de Processamento de Partições, consulte [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="2208b-104">To learn more about the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2208b-105">As tarefas descritas aqui não se aplicam a modelos de tabela do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2208b-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="2208b-106">Você não pode mapear colunas de entrada para as colunas de partição em modelos de tabela.</span><span class="sxs-lookup"><span data-stu-id="2208b-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="2208b-107">Você pode usar a tarefa Executar DDL do Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) para processar a partição.</span><span class="sxs-lookup"><span data-stu-id="2208b-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2208b-108">Opções</span><span class="sxs-lookup"><span data-stu-id="2208b-108">Options</span></span>  
 <span data-ttu-id="2208b-109">**Usar configuração de erro padrão.**</span><span class="sxs-lookup"><span data-stu-id="2208b-109">**Use default error configuration.**</span></span>  
 <span data-ttu-id="2208b-110">Especifique se a manipulação de erros padrão do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="2208b-110">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="2208b-111">Por padrão, esse valor é `True`.</span><span class="sxs-lookup"><span data-stu-id="2208b-111">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="2208b-112">**Ação de erro de chave**</span><span class="sxs-lookup"><span data-stu-id="2208b-112">**Key error action**</span></span>  
 <span data-ttu-id="2208b-113">Especifique como manipular registros que possuem valores de chave inaceitáveis.</span><span class="sxs-lookup"><span data-stu-id="2208b-113">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="2208b-114">Valor</span><span class="sxs-lookup"><span data-stu-id="2208b-114">Value</span></span>|<span data-ttu-id="2208b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2208b-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2208b-116">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="2208b-116">**ConvertToUnknown**</span></span>|<span data-ttu-id="2208b-117">Converta o valor de chave inaceitável em um valor Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="2208b-117">Convert the unacceptable key value to the Unknown value.</span></span>|  
|<span data-ttu-id="2208b-118">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="2208b-118">**DiscardRecord**</span></span>|<span data-ttu-id="2208b-119">Descarte o registro.</span><span class="sxs-lookup"><span data-stu-id="2208b-119">Discard the record.</span></span>|  
  
 <span data-ttu-id="2208b-120">**Ignorar erros**</span><span class="sxs-lookup"><span data-stu-id="2208b-120">**Ignore errors**</span></span>  
 <span data-ttu-id="2208b-121">Especifique se os erros devem ser ignorados.</span><span class="sxs-lookup"><span data-stu-id="2208b-121">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="2208b-122">**Parar se houver erro**</span><span class="sxs-lookup"><span data-stu-id="2208b-122">**Stop on error**</span></span>  
 <span data-ttu-id="2208b-123">Especifique se o processamento deve parar quando ocorrer erro.</span><span class="sxs-lookup"><span data-stu-id="2208b-123">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="2208b-124">**Número de erros**</span><span class="sxs-lookup"><span data-stu-id="2208b-124">**Number of errors**</span></span>  
 <span data-ttu-id="2208b-125">Especifique o limite de erros em que o processamento deve ser interrompido, caso tenha selecionado **Parar se houver erro**.</span><span class="sxs-lookup"><span data-stu-id="2208b-125">Specify the error threshold at which processing should stop, if you have selected **Stop on error**.</span></span>  
  
 <span data-ttu-id="2208b-126">**Ação se houver erro**</span><span class="sxs-lookup"><span data-stu-id="2208b-126">**On error action**</span></span>  
 <span data-ttu-id="2208b-127">Especifique a ação a ser tomada quando o limite de erros for atingido, caso tenha selecionado **Parar se houver erro**.</span><span class="sxs-lookup"><span data-stu-id="2208b-127">Specify the action to take when the error threshold is reached, if you have selected **Stop on error**.</span></span>  
  
|<span data-ttu-id="2208b-128">Valor</span><span class="sxs-lookup"><span data-stu-id="2208b-128">Value</span></span>|<span data-ttu-id="2208b-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="2208b-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2208b-130">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="2208b-130">**StopProcessing**</span></span>|<span data-ttu-id="2208b-131">Pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-131">Stop processing.</span></span>|  
|<span data-ttu-id="2208b-132">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="2208b-132">**StopLogging**</span></span>|<span data-ttu-id="2208b-133">Pare de registrar os erros.</span><span class="sxs-lookup"><span data-stu-id="2208b-133">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="2208b-134">**Chave não encontrada**</span><span class="sxs-lookup"><span data-stu-id="2208b-134">**Key not found**</span></span>  
 <span data-ttu-id="2208b-135">Especifique a ação a ser tomada mediante erro de chave não encontrada.</span><span class="sxs-lookup"><span data-stu-id="2208b-135">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="2208b-136">Por padrão, este valor é **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="2208b-136">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="2208b-137">Valor</span><span class="sxs-lookup"><span data-stu-id="2208b-137">Value</span></span>|<span data-ttu-id="2208b-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="2208b-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2208b-139">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="2208b-139">**IgnoreError**</span></span>|<span data-ttu-id="2208b-140">Ignore o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-140">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="2208b-141">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="2208b-141">**ReportAndContinue**</span></span>|<span data-ttu-id="2208b-142">Relate o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-142">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="2208b-143">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="2208b-143">**ReportAndStop**</span></span>|<span data-ttu-id="2208b-144">Relate o erro e pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-144">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="2208b-145">**Chave duplicada**</span><span class="sxs-lookup"><span data-stu-id="2208b-145">**Duplicate key**</span></span>  
 <span data-ttu-id="2208b-146">Especifique a ação a ser tomada mediante erro de chave duplicada.</span><span class="sxs-lookup"><span data-stu-id="2208b-146">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="2208b-147">Por padrão, esse valor é **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="2208b-147">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="2208b-148">Valor</span><span class="sxs-lookup"><span data-stu-id="2208b-148">Value</span></span>|<span data-ttu-id="2208b-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="2208b-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2208b-150">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="2208b-150">**IgnoreError**</span></span>|<span data-ttu-id="2208b-151">Ignore o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-151">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="2208b-152">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="2208b-152">**ReportAndContinue**</span></span>|<span data-ttu-id="2208b-153">Relate o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-153">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="2208b-154">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="2208b-154">**ReportAndStop**</span></span>|<span data-ttu-id="2208b-155">Relate o erro e pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-155">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="2208b-156">**Chave nula convertida em desconhecida**</span><span class="sxs-lookup"><span data-stu-id="2208b-156">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="2208b-157">Especifique a ação a ser tomada quando uma chave nula foi convertida no valor Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="2208b-157">Specify the action to take when a null key has been converted to the Unknown value.</span></span> <span data-ttu-id="2208b-158">Por padrão, esse valor é **IgnoreError**.</span><span class="sxs-lookup"><span data-stu-id="2208b-158">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="2208b-159">Valor</span><span class="sxs-lookup"><span data-stu-id="2208b-159">Value</span></span>|<span data-ttu-id="2208b-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="2208b-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2208b-161">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="2208b-161">**IgnoreError**</span></span>|<span data-ttu-id="2208b-162">Ignore o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-162">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="2208b-163">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="2208b-163">**ReportAndContinue**</span></span>|<span data-ttu-id="2208b-164">Relate o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-164">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="2208b-165">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="2208b-165">**ReportAndStop**</span></span>|<span data-ttu-id="2208b-166">Relate o erro e pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-166">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="2208b-167">**Chave nula não permitida**</span><span class="sxs-lookup"><span data-stu-id="2208b-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="2208b-168">Especifique a ação a ser tomada quando chaves nulas não forem permitidas, e uma chave nula for encontrada.</span><span class="sxs-lookup"><span data-stu-id="2208b-168">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="2208b-169">Por padrão, este valor é **ReportAndContinue**.</span><span class="sxs-lookup"><span data-stu-id="2208b-169">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="2208b-170">Valor</span><span class="sxs-lookup"><span data-stu-id="2208b-170">Value</span></span>|<span data-ttu-id="2208b-171">Descrição</span><span class="sxs-lookup"><span data-stu-id="2208b-171">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2208b-172">**IgnoreError**</span><span class="sxs-lookup"><span data-stu-id="2208b-172">**IgnoreError**</span></span>|<span data-ttu-id="2208b-173">Ignore o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-173">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="2208b-174">**ReportAndContinue**</span><span class="sxs-lookup"><span data-stu-id="2208b-174">**ReportAndContinue**</span></span>|<span data-ttu-id="2208b-175">Relate o erro e continue o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-175">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="2208b-176">**ReportAndStop**</span><span class="sxs-lookup"><span data-stu-id="2208b-176">**ReportAndStop**</span></span>|<span data-ttu-id="2208b-177">Relate o erro e pare o processamento.</span><span class="sxs-lookup"><span data-stu-id="2208b-177">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="2208b-178">**Caminho do log de erros**</span><span class="sxs-lookup"><span data-stu-id="2208b-178">**Error log path**</span></span>  
 <span data-ttu-id="2208b-179">Digite o caminho do log de erros ou selecione um destino usando o botão Procurar **(...)** .</span><span class="sxs-lookup"><span data-stu-id="2208b-179">Type the path for the error log, or select a destination by using the browse **(...)** button.</span></span>  
  
 <span data-ttu-id="2208b-180">**Procurar (...)**</span><span class="sxs-lookup"><span data-stu-id="2208b-180">**Browse (...)**</span></span>  
 <span data-ttu-id="2208b-181">Selecione um caminho para o log de erros.</span><span class="sxs-lookup"><span data-stu-id="2208b-181">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2208b-182">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2208b-182">See Also</span></span>  
 <span data-ttu-id="2208b-183">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2208b-183">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="2208b-184">Editor de Destino de Processamento de Partições &#40;Página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="2208b-184">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md)  
  
  
