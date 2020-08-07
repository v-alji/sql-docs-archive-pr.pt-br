---
title: Editor da tarefa leitor de dados do WMI (página Opções do WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.wmiquery.f1
helpviewer_keywords:
- WMI Data Reader Task Editor
ms.assetid: 4b8d4716-882d-41b0-b77e-e0e2741a2cd5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfb28e7f8f352f708085bf664757391a05869752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582498"
---
# <a name="wmi-data-reader-task-editor-wmi-options-page"></a><span data-ttu-id="7499e-102">Editor da Tarefa Leitor de Dados do WMI (página Opções do WMI)</span><span class="sxs-lookup"><span data-stu-id="7499e-102">WMI Data Reader Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="7499e-103">Use a página **Opções do WMI** da caixa de diálogo **Editor da Tarefa Leitor de Dados do WMI** para especificar a origem da consulta da linguagem WQL e o destino do resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="7499e-103">Use the **WMI Options** page of the **WMI Data Reader Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and the destination of the query result.</span></span>  
  
 <span data-ttu-id="7499e-104">Para obter informações sobre essa tarefa, consulte [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span><span class="sxs-lookup"><span data-stu-id="7499e-104">To learn about this task, see [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span></span> <span data-ttu-id="7499e-105">Para obter mais informações sobre a linguagem WQL, consulte o tópico Instrumentação de Gerenciamento do Windows, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045)(Consultando com WQL), na Biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="7499e-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="7499e-106">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="7499e-106">Static Options</span></span>  
 <span data-ttu-id="7499e-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="7499e-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="7499e-108">Selecione um gerenciador de conexões WMI na lista ou clique em \<**New WMI Connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="7499e-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="7499e-109">**Tópicos relacionados:** [Gerenciador de Conexões WMI](connection-manager/wmi-connection-manager.md), [Editor do Gerenciador de Conexões WMI](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="7499e-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="7499e-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="7499e-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="7499e-111">Selecione o tipo de origem da consulta WQL que a tarefa executa.</span><span class="sxs-lookup"><span data-stu-id="7499e-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="7499e-112">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7499e-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="7499e-113">Valor</span><span class="sxs-lookup"><span data-stu-id="7499e-113">Value</span></span>|<span data-ttu-id="7499e-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="7499e-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7499e-115">**Entrada Direta**</span><span class="sxs-lookup"><span data-stu-id="7499e-115">**Direct input**</span></span>|<span data-ttu-id="7499e-116">Defina a origem de consultas WQL.</span><span class="sxs-lookup"><span data-stu-id="7499e-116">Set the source to a WQL query.</span></span> <span data-ttu-id="7499e-117">Ao selecionar esse valor, a opção dinâmica **WQLQuerySourceType**será exibida.</span><span class="sxs-lookup"><span data-stu-id="7499e-117">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="7499e-118">**Conexão do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="7499e-118">**File connection**</span></span>|<span data-ttu-id="7499e-119">Selecione um arquivo que contém a consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="7499e-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="7499e-120">Ao selecionar esse valor, a opção dinâmica **WQLQuerySourceType**será exibida.</span><span class="sxs-lookup"><span data-stu-id="7499e-120">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="7499e-121">**Variável**</span><span class="sxs-lookup"><span data-stu-id="7499e-121">**Variable**</span></span>|<span data-ttu-id="7499e-122">Defina a origem de uma variável que defina a consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="7499e-122">Set the source to a variable that defines the WQL query.</span></span> <span data-ttu-id="7499e-123">Ao selecionar esse valor, a opção dinâmica **WQLQuerySourceType**será exibida.</span><span class="sxs-lookup"><span data-stu-id="7499e-123">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
  
 <span data-ttu-id="7499e-124">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="7499e-124">**OutputType**</span></span>  
 <span data-ttu-id="7499e-125">Especifique se a saída deve ser uma tabela de dados, valor de propriedade ou nome e valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="7499e-125">Specify whether the output should be a data table, property value, or property name and value.</span></span>  
  
 <span data-ttu-id="7499e-126">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="7499e-126">**OverwriteDestination**</span></span>  
 <span data-ttu-id="7499e-127">Especifique se é necessário manter, substituir ou adicionar aos dados originais no arquivo ou variável de destino.</span><span class="sxs-lookup"><span data-stu-id="7499e-127">Specifies whether to keep, overwrite, or append to the original data in the destination file or variable.</span></span>  
  
 <span data-ttu-id="7499e-128">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="7499e-128">**DestinationType**</span></span>  
 <span data-ttu-id="7499e-129">Selecione o tipo de destino da consulta WQL que a tarefa executa.</span><span class="sxs-lookup"><span data-stu-id="7499e-129">Select the destination type of the WQL query that the task runs.</span></span> <span data-ttu-id="7499e-130">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7499e-130">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="7499e-131">Valor</span><span class="sxs-lookup"><span data-stu-id="7499e-131">Value</span></span>|<span data-ttu-id="7499e-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="7499e-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7499e-133">**Conexão do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="7499e-133">**File connection**</span></span>|<span data-ttu-id="7499e-134">Selecione um arquivo no qual salvar os resultados da consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="7499e-134">Select a file to save the results of the WQL query in.</span></span> <span data-ttu-id="7499e-135">A seleção desse valor exibe a opção dinâmica **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="7499e-135">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
|<span data-ttu-id="7499e-136">**Variável**</span><span class="sxs-lookup"><span data-stu-id="7499e-136">**Variable**</span></span>|<span data-ttu-id="7499e-137">Defina a variável na qual armazenar os resultados da consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="7499e-137">Set the variable to store the results of the WQL query in.</span></span> <span data-ttu-id="7499e-138">A seleção desse valor exibe a opção dinâmica **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="7499e-138">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
  
## <a name="wqlquerysourcetype-dynamic-options"></a><span data-ttu-id="7499e-139">Opções dinâmicas de WQLQuerySourceType</span><span class="sxs-lookup"><span data-stu-id="7499e-139">WQLQuerySourceType Dynamic Options</span></span>  
  
### <a name="wqlquerysourcetype--direct-input"></a><span data-ttu-id="7499e-140">WQLQuerySourceType = Entrada direta</span><span class="sxs-lookup"><span data-stu-id="7499e-140">WQLQuerySourceType = Direct input</span></span>  
 <span data-ttu-id="7499e-141">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="7499e-141">**WQLQuerySource**</span></span>  
 <span data-ttu-id="7499e-142">Forneça uma consulta ou clique nas reticências (...) e digite uma consulta, usando a caixa de diálogo **Consulta WQL**.</span><span class="sxs-lookup"><span data-stu-id="7499e-142">Provide a query, or click the ellipsis (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysourcetype--file-connection"></a><span data-ttu-id="7499e-143">WQLQuerySourceType = Conexão do arquivo</span><span class="sxs-lookup"><span data-stu-id="7499e-143">WQLQuerySourceType = File connection</span></span>  
 <span data-ttu-id="7499e-144">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="7499e-144">**WQLQuerySource**</span></span>  
 <span data-ttu-id="7499e-145">Selecione um gerenciador de conexões de Arquivos na lista ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="7499e-145">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="7499e-146">**Tópicos relacionados:** [Gerenciador de conexões de arquivos](connection-manager/file-connection-manager.md), [Editor do Gerenciador de conexões de Arquivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="7499e-146">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysourcetype--variable"></a><span data-ttu-id="7499e-147">WQLQuerySourceType = Variável</span><span class="sxs-lookup"><span data-stu-id="7499e-147">WQLQuerySourceType = Variable</span></span>  
 <span data-ttu-id="7499e-148">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="7499e-148">**WQLQuerySource**</span></span>  
 <span data-ttu-id="7499e-149">Selecione uma variável na lista ou clique em \<**New variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="7499e-149">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="7499e-150">**Tópicos relacionados:** [Variáveis do Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Adicionar variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="7499e-150">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="destinationtype-dynamic-options"></a><span data-ttu-id="7499e-151">Opções dinâmicas de DestinationType</span><span class="sxs-lookup"><span data-stu-id="7499e-151">DestinationType Dynamic Options</span></span>  
  
### <a name="destinationtype--file-connection"></a><span data-ttu-id="7499e-152">DestinationType = Conexão do arquivo</span><span class="sxs-lookup"><span data-stu-id="7499e-152">DestinationType = File connection</span></span>  
 <span data-ttu-id="7499e-153">**Destino**</span><span class="sxs-lookup"><span data-stu-id="7499e-153">**Destination**</span></span>  
 <span data-ttu-id="7499e-154">Selecione um gerenciador de conexões de Arquivos na lista ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="7499e-154">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="7499e-155">**Tópicos relacionados:** [Gerenciador de conexões de arquivos](connection-manager/file-connection-manager.md), [Editor do Gerenciador de conexões de Arquivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="7499e-155">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="destinationtype--variable"></a><span data-ttu-id="7499e-156">DestinationType = Variável</span><span class="sxs-lookup"><span data-stu-id="7499e-156">DestinationType = Variable</span></span>  
 <span data-ttu-id="7499e-157">**Destino**</span><span class="sxs-lookup"><span data-stu-id="7499e-157">**Destination**</span></span>  
 <span data-ttu-id="7499e-158">Selecione uma variável na lista ou clique em \<**New variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="7499e-158">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="7499e-159">**Tópicos relacionados:** [Variáveis do Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Adicionar variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="7499e-159">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7499e-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7499e-160">See Also</span></span>  
 <span data-ttu-id="7499e-161">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7499e-161">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7499e-162">[Editor da tarefa leitor de dados do WMI &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="7499e-162">[WMI Data Reader Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="7499e-163">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="7499e-163">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="7499e-164">Tarefa Detector de Eventos do WMI</span><span class="sxs-lookup"><span data-stu-id="7499e-164">WMI Event Watcher Task</span></span>](control-flow/wmi-event-watcher-task.md)  
  
  
