---
title: Editor da tarefa FTP (página transferência de arquivos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.filetransfer.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 37e52220-feb2-474c-ad88-fa1b1059acd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8094051e93c4165be6ae186bde394f9271d60669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571450"
---
# <a name="ftp-task-editor-file-transfer-page"></a><span data-ttu-id="cb6de-102">Editor da Tarefa FTP (página Transferência de Arquivos)</span><span class="sxs-lookup"><span data-stu-id="cb6de-102">FTP Task Editor (File Transfer Page)</span></span>
  <span data-ttu-id="cb6de-103">Use a página **Transferência de Arquivos** da caixa de diálogo **Editor da Tarefa FTP** para configurar a operação FTP executada pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="cb6de-103">Use the **File Transfer** page of the **FTP Task Editor** dialog box to configure the FTP operation that the task performs.</span></span>  
  
 <span data-ttu-id="cb6de-104">Para obter informações sobre essa tarefa, consulte [Tarefa FTP](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="cb6de-104">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb6de-105">Opções</span><span class="sxs-lookup"><span data-stu-id="cb6de-105">Options</span></span>  
 <span data-ttu-id="cb6de-106">**IsRemotePathVariable**</span><span class="sxs-lookup"><span data-stu-id="cb6de-106">**IsRemotePathVariable**</span></span>  
 <span data-ttu-id="cb6de-107">Indique se o caminho remoto deve ser armazenado em uma variável.</span><span class="sxs-lookup"><span data-stu-id="cb6de-107">Indicate whether the remote path is stored in a variable.</span></span> <span data-ttu-id="cb6de-108">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="cb6de-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="cb6de-109">Valor</span><span class="sxs-lookup"><span data-stu-id="cb6de-109">Value</span></span>|<span data-ttu-id="cb6de-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb6de-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb6de-111">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="cb6de-111">**True**</span></span>|<span data-ttu-id="cb6de-112">O caminho de destino é armazenado em uma variável.</span><span class="sxs-lookup"><span data-stu-id="cb6de-112">The destination path is stored in a variable.</span></span> <span data-ttu-id="cb6de-113">Ao selecionar esse valor, a opção dinâmica **RemoteVariable**será exibida.</span><span class="sxs-lookup"><span data-stu-id="cb6de-113">Selecting the value displays the dynamic option, **RemoteVariable**.</span></span>|  
|<span data-ttu-id="cb6de-114">**Falso**</span><span class="sxs-lookup"><span data-stu-id="cb6de-114">**False**</span></span>|<span data-ttu-id="cb6de-115">O caminho de destino é especificado em um gerenciador de conexões de Arquivo.</span><span class="sxs-lookup"><span data-stu-id="cb6de-115">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="cb6de-116">Ao selecionar esse valor, a opção dinâmica **RemotePath**será exibida.</span><span class="sxs-lookup"><span data-stu-id="cb6de-116">Selecting the value displays the dynamic option, **RemotePath**.</span></span>|  
  
 <span data-ttu-id="cb6de-117">**OverwriteFileAtDestination**</span><span class="sxs-lookup"><span data-stu-id="cb6de-117">**OverwriteFileAtDestination**</span></span>  
 <span data-ttu-id="cb6de-118">Especifique se um arquivo no destino pode ser substituído.</span><span class="sxs-lookup"><span data-stu-id="cb6de-118">Specify whether a file at the destination can be overwritten.</span></span>  
  
 <span data-ttu-id="cb6de-119">**IsLocalPathVariable**</span><span class="sxs-lookup"><span data-stu-id="cb6de-119">**IsLocalPathVariable**</span></span>  
 <span data-ttu-id="cb6de-120">Indique se o caminho local deve ser armazenado em uma variável.</span><span class="sxs-lookup"><span data-stu-id="cb6de-120">Indicate whether the local path is stored in a variable.</span></span> <span data-ttu-id="cb6de-121">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="cb6de-121">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="cb6de-122">Valor</span><span class="sxs-lookup"><span data-stu-id="cb6de-122">Value</span></span>|<span data-ttu-id="cb6de-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb6de-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb6de-124">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="cb6de-124">**True**</span></span>|<span data-ttu-id="cb6de-125">O caminho de destino é armazenado em uma variável.</span><span class="sxs-lookup"><span data-stu-id="cb6de-125">The destination path is stored in a variable.</span></span> <span data-ttu-id="cb6de-126">Ao selecionar esse valor, a opção dinâmica **LocalVariable**será exibida.</span><span class="sxs-lookup"><span data-stu-id="cb6de-126">Selecting the value displays the dynamic option, **LocalVariable**.</span></span>|  
|<span data-ttu-id="cb6de-127">**Falso**</span><span class="sxs-lookup"><span data-stu-id="cb6de-127">**False**</span></span>|<span data-ttu-id="cb6de-128">O caminho de destino é especificado em um gerenciador de conexões de Arquivo.</span><span class="sxs-lookup"><span data-stu-id="cb6de-128">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="cb6de-129">Ao selecionar esse valor, a opção dinâmica **LocalPath**será exibida.</span><span class="sxs-lookup"><span data-stu-id="cb6de-129">Selecting the value displays the dynamic option, **LocalPath**.</span></span>|  
  
 <span data-ttu-id="cb6de-130">**Operação**</span><span class="sxs-lookup"><span data-stu-id="cb6de-130">**Operation**</span></span>  
 <span data-ttu-id="cb6de-131">Selecione a operação FTP a executar.</span><span class="sxs-lookup"><span data-stu-id="cb6de-131">Select the FTP operation to perform.</span></span> <span data-ttu-id="cb6de-132">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="cb6de-132">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="cb6de-133">Valor</span><span class="sxs-lookup"><span data-stu-id="cb6de-133">Value</span></span>|<span data-ttu-id="cb6de-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb6de-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb6de-135">**Enviar arquivos**</span><span class="sxs-lookup"><span data-stu-id="cb6de-135">**Send files**</span></span>|<span data-ttu-id="cb6de-136">Enviar arquivos.</span><span class="sxs-lookup"><span data-stu-id="cb6de-136">Send files.</span></span> <span data-ttu-id="cb6de-137">Ao selecionar esse valor, as opções dinâmicas **LocalVariable**, **LocalPathRemoteVariable** e **RemotePath**serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="cb6de-137">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="cb6de-138">**Receber arquivos**</span><span class="sxs-lookup"><span data-stu-id="cb6de-138">**Receive files**</span></span>|<span data-ttu-id="cb6de-139">Receber arquivos.</span><span class="sxs-lookup"><span data-stu-id="cb6de-139">Receive files.</span></span> <span data-ttu-id="cb6de-140">Ao selecionar esse valor, as opções dinâmicas **LocalVariable**, **LocalPathRemoteVariable** e **RemotePath**serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="cb6de-140">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="cb6de-141">**Criar diretório local**</span><span class="sxs-lookup"><span data-stu-id="cb6de-141">**Create local directory**</span></span>|<span data-ttu-id="cb6de-142">Criar um diretório local.</span><span class="sxs-lookup"><span data-stu-id="cb6de-142">Create a local directory.</span></span> <span data-ttu-id="cb6de-143">Ao selecionar esse valor, as opções dinâmicas **LocalVariable** e **LocalPath**serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="cb6de-143">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="cb6de-144">**Criar diretório remoto**</span><span class="sxs-lookup"><span data-stu-id="cb6de-144">**Create remote directory**</span></span>|<span data-ttu-id="cb6de-145">Criar um diretório remoto.</span><span class="sxs-lookup"><span data-stu-id="cb6de-145">Create a remote directory.</span></span> <span data-ttu-id="cb6de-146">Ao selecionar esse valor, as opções dinâmicas **RemoteVariable** e **RemotelPath**serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="cb6de-146">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotelPath**.</span></span>|  
|<span data-ttu-id="cb6de-147">**Remover diretório local**</span><span class="sxs-lookup"><span data-stu-id="cb6de-147">**Remove local directory**</span></span>|<span data-ttu-id="cb6de-148">Remover diretório local.</span><span class="sxs-lookup"><span data-stu-id="cb6de-148">Removes a local directory.</span></span> <span data-ttu-id="cb6de-149">Ao selecionar esse valor, as opções dinâmicas **LocalVariable** e **LocalPath**serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="cb6de-149">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="cb6de-150">**Remover diretório remoto**</span><span class="sxs-lookup"><span data-stu-id="cb6de-150">**Remove remote directory**</span></span>|<span data-ttu-id="cb6de-151">Remover um diretório remoto.</span><span class="sxs-lookup"><span data-stu-id="cb6de-151">Remove a remote directory.</span></span> <span data-ttu-id="cb6de-152">Ao selecionar esse valor, as opções dinâmicas **RemoteVariable** e **RemotePath**serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="cb6de-152">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="cb6de-153">**Excluir arquivos locais**</span><span class="sxs-lookup"><span data-stu-id="cb6de-153">**Delete local files**</span></span>|<span data-ttu-id="cb6de-154">Excluir arquivos locais.</span><span class="sxs-lookup"><span data-stu-id="cb6de-154">Delete local files.</span></span> <span data-ttu-id="cb6de-155">Ao selecionar esse valor, as opções dinâmicas **LocalVariable** e **LocalPath**serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="cb6de-155">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="cb6de-156">**Excluir arquivos remotos**</span><span class="sxs-lookup"><span data-stu-id="cb6de-156">**Delete remote files**</span></span>|<span data-ttu-id="cb6de-157">Excluir arquivos remotos.</span><span class="sxs-lookup"><span data-stu-id="cb6de-157">Delete remote files.</span></span> <span data-ttu-id="cb6de-158">Ao selecionar esse valor, as opções dinâmicas **RemoteVariable** e **RemotePath**serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="cb6de-158">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
  
 <span data-ttu-id="cb6de-159">**IsTransferASCII**</span><span class="sxs-lookup"><span data-stu-id="cb6de-159">**IsTransferASCII**</span></span>  
 <span data-ttu-id="cb6de-160">Indique se os arquivos transferidos para e do servidor FTP remoto devem ser transferidos em modo ASCII.</span><span class="sxs-lookup"><span data-stu-id="cb6de-160">Indicate whether files transferred to and from the remote FTP server should be transferred in ASCII mode.</span></span>  
  
## <a name="isremotepathvariable-dynamic-options"></a><span data-ttu-id="cb6de-161">Opções dinâmicas de IsRemotePathVariable</span><span class="sxs-lookup"><span data-stu-id="cb6de-161">IsRemotePathVariable Dynamic Options</span></span>  
  
### <a name="isremotepathvariable--true"></a><span data-ttu-id="cb6de-162">IsRemotePathVariable = True</span><span class="sxs-lookup"><span data-stu-id="cb6de-162">IsRemotePathVariable = True</span></span>  
 <span data-ttu-id="cb6de-163">**RemoteVariable**</span><span class="sxs-lookup"><span data-stu-id="cb6de-163">**RemoteVariable**</span></span>  
 <span data-ttu-id="cb6de-164">Selecione uma variável definida pelo usuário existente ou clique em \<**New variable...**> para criar uma variável definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="cb6de-164">Select an existing user-defined variable, or click \<**New variable...**> to create a user-defined variable.</span></span>  
  
 <span data-ttu-id="cb6de-165">**Tópicos relacionados:** [Variáveis do Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), Adicionar variável</span><span class="sxs-lookup"><span data-stu-id="cb6de-165">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="isremotepathvariable--false"></a><span data-ttu-id="cb6de-166">IsRemotePathVariable = False</span><span class="sxs-lookup"><span data-stu-id="cb6de-166">IsRemotePathVariable = False</span></span>  
 <span data-ttu-id="cb6de-167">**RemotePath**</span><span class="sxs-lookup"><span data-stu-id="cb6de-167">**RemotePath**</span></span>  
 <span data-ttu-id="cb6de-168">Selecione um gerenciador de conexões FTP existente ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="cb6de-168">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="cb6de-169">**Tópicos relacionados:** [Gerenciador de Conexões de FTP](connection-manager/ftp-connection-manager.md), [Editor do Gerenciador de Conexões de FTP](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="cb6de-169">**Related Topics:** [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
## <a name="islocalpathvariable-dynamic-options"></a><span data-ttu-id="cb6de-170">Opções dinâmicas de IsLocalPathVariable</span><span class="sxs-lookup"><span data-stu-id="cb6de-170">IsLocalPathVariable Dynamic Options</span></span>  
  
### <a name="islocalpathvariable--true"></a><span data-ttu-id="cb6de-171">IsLocalPathVariable = True</span><span class="sxs-lookup"><span data-stu-id="cb6de-171">IsLocalPathVariable = True</span></span>  
 <span data-ttu-id="cb6de-172">**LocalVariable**</span><span class="sxs-lookup"><span data-stu-id="cb6de-172">**LocalVariable**</span></span>  
 <span data-ttu-id="cb6de-173">Selecione uma variável definida pelo usuário existente ou clique em \<**New variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="cb6de-173">Select an existing user-defined variable, or click \<**New variable...**> to create a variable.</span></span>  
  
 <span data-ttu-id="cb6de-174">**Tópicos relacionados:** [Variáveis do Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), Adicionar variável</span><span class="sxs-lookup"><span data-stu-id="cb6de-174">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="islocalpathvariable--false"></a><span data-ttu-id="cb6de-175">IsLocalPathVariable = False</span><span class="sxs-lookup"><span data-stu-id="cb6de-175">IsLocalPathVariable = False</span></span>  
 <span data-ttu-id="cb6de-176">**LocalPath**</span><span class="sxs-lookup"><span data-stu-id="cb6de-176">**LocalPath**</span></span>  
 <span data-ttu-id="cb6de-177">Selecione um gerenciador de conexões de Arquivo existente ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="cb6de-177">Select an existing File connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="cb6de-178">**Tópicos relacionados:**[Gerenciador de Conexões de Arquivos Simples](connection-manager/file-connection-manager.md), [Editor do Gerenciador de Conexões de Arquivos Simples](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="cb6de-178">**Related Topics**: [Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6de-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cb6de-179">See Also</span></span>  
 <span data-ttu-id="cb6de-180">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cb6de-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cb6de-181">[Editor da tarefa FTP &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="cb6de-181">[FTP Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="cb6de-182">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="cb6de-182">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
