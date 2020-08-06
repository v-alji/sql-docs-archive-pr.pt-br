---
title: Editor da tarefa fila de mensagens (página receber) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.receive.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 7028756d-1dcc-480c-bbcd-e9654f0772a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f45aa579d37d1fdd3a3124eea972014ce839fdc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686324"
---
# <a name="message-queue-task-editor-receive-page"></a><span data-ttu-id="f4109-102">Editor da Tarefa Fila de Mensagens (página Receber)</span><span class="sxs-lookup"><span data-stu-id="f4109-102">Message Queue Task Editor (Receive Page)</span></span>
  <span data-ttu-id="f4109-103">Use a página **Receber** da caixa de diálogo **Editor da Tarefa Fila de Mensagens** para configurar uma tarefa Fila de Mensagens para receber mensagens do MSMQ (Serviço de Enfileiramento de Mensagens) [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4109-103">Use the **Receive** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to receive [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ) messages.</span></span>  
  
 <span data-ttu-id="f4109-104">Para obter informações sobre essa tarefa, consulte [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="f4109-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f4109-105">Opções</span><span class="sxs-lookup"><span data-stu-id="f4109-105">Options</span></span>  
 <span data-ttu-id="f4109-106">**RemoveFromMessageQueue**</span><span class="sxs-lookup"><span data-stu-id="f4109-106">**RemoveFromMessageQueue**</span></span>  
 <span data-ttu-id="f4109-107">Indique se a mensagem deve ser removida da fila depois de ser recebida.</span><span class="sxs-lookup"><span data-stu-id="f4109-107">Indicate whether to remove the message from the queue after it is received.</span></span> <span data-ttu-id="f4109-108">Por padrão, esse valor é definido como `False`.</span><span class="sxs-lookup"><span data-stu-id="f4109-108">By default, this value is set to `False`.</span></span>  
  
 <span data-ttu-id="f4109-109">**ErrorIfMessageTimeOut**</span><span class="sxs-lookup"><span data-stu-id="f4109-109">**ErrorIfMessageTimeOut**</span></span>  
 <span data-ttu-id="f4109-110">Indique se a tarefa falha quando a mensagem expira, exibindo uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="f4109-110">Indicate whether the task fails when the message times out, displaying an error message.</span></span> <span data-ttu-id="f4109-111">O padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="f4109-111">The default is `False`.</span></span>  
  
 <span data-ttu-id="f4109-112">**TimeoutAfter**</span><span class="sxs-lookup"><span data-stu-id="f4109-112">**TimeoutAfter**</span></span>  
 <span data-ttu-id="f4109-113">Se você optar por exibir uma mensagem de erro quando uma tarefa falha, especifique quantos segundos esperar antes de ser exibida a mensagem de tempo limite ultrapassado.</span><span class="sxs-lookup"><span data-stu-id="f4109-113">If you choose to display an error message on task failure, specify the number of seconds to wait before displaying the time-out message.</span></span>  
  
 <span data-ttu-id="f4109-114">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="f4109-114">**MessageType**</span></span>  
 <span data-ttu-id="f4109-115">Selecione o tipo de mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4109-115">Select the message type.</span></span> <span data-ttu-id="f4109-116">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4109-116">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="f4109-117">Valor</span><span class="sxs-lookup"><span data-stu-id="f4109-117">Value</span></span>|<span data-ttu-id="f4109-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4109-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f4109-119">**Mensagem do arquivo de dados**</span><span class="sxs-lookup"><span data-stu-id="f4109-119">**Data file message**</span></span>|<span data-ttu-id="f4109-120">A mensagem é armazenada em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="f4109-120">The message is stored in a file.</span></span> <span data-ttu-id="f4109-121">Selecionar este valor faz com que seja exibida a opção dinâmica **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="f4109-121">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="f4109-122">**Mensagem de variável**</span><span class="sxs-lookup"><span data-stu-id="f4109-122">**Variable message**</span></span>|<span data-ttu-id="f4109-123">A mensagem é armazenada em uma variável.</span><span class="sxs-lookup"><span data-stu-id="f4109-123">The message is stored in a variable.</span></span> <span data-ttu-id="f4109-124">Selecionar este valor faz com que seja exibida a opção dinâmica **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="f4109-124">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="f4109-125">**Mensagem de cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="f4109-125">**String message**</span></span>|<span data-ttu-id="f4109-126">A mensagem é armazenada em uma tarefa Fila de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="f4109-126">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="f4109-127">Selecionar este valor faz com que seja exibida a opção dinâmica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="f4109-127">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
|<span data-ttu-id="f4109-128">**Mensagem de cadeia de caracteres para variável**</span><span class="sxs-lookup"><span data-stu-id="f4109-128">**String message to variable**</span></span>|<span data-ttu-id="f4109-129">A mensagem</span><span class="sxs-lookup"><span data-stu-id="f4109-129">The message</span></span><br /><br /> <span data-ttu-id="f4109-130">Selecionar este valor faz com que seja exibida a opção dinâmica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="f4109-130">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="f4109-131">Opções dinâmicas de MessageType</span><span class="sxs-lookup"><span data-stu-id="f4109-131">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="f4109-132">MessageType = Mensagem de arquivo de dados</span><span class="sxs-lookup"><span data-stu-id="f4109-132">MessageType = Data file message</span></span>  
 <span data-ttu-id="f4109-133">**SaveFileAs**</span><span class="sxs-lookup"><span data-stu-id="f4109-133">**SaveFileAs**</span></span>  
 <span data-ttu-id="f4109-134">Digite o caminho do arquivo a ser usado ou clique no botão de reticências **(...)** e, em seguida, localize o arquivo.</span><span class="sxs-lookup"><span data-stu-id="f4109-134">Type the path of the file to use, or click the ellipsis button **(...)** and then locate the file.</span></span>  
  
 <span data-ttu-id="f4109-135">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="f4109-135">**Overwrite**</span></span>  
 <span data-ttu-id="f4109-136">Indique se os dados em um arquivo existente devem ser substituídos quando o conteúdo de uma mensagem de arquivo de dados é salvo.</span><span class="sxs-lookup"><span data-stu-id="f4109-136">Indicate whether to overwrite the data in an existing file when saving the contents of a data file message.</span></span> <span data-ttu-id="f4109-137">O padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="f4109-137">The default is `False`.</span></span>  
  
 <span data-ttu-id="f4109-138">**Filter**</span><span class="sxs-lookup"><span data-stu-id="f4109-138">**Filter**</span></span>  
 <span data-ttu-id="f4109-139">Especifique se deve ser aplicado um filtro à mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4109-139">Specify whether to apply a filter to the message.</span></span> <span data-ttu-id="f4109-140">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4109-140">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="f4109-141">Valor</span><span class="sxs-lookup"><span data-stu-id="f4109-141">Value</span></span>|<span data-ttu-id="f4109-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4109-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f4109-143">**Sem-filtro**</span><span class="sxs-lookup"><span data-stu-id="f4109-143">**No filter**</span></span>|<span data-ttu-id="f4109-144">A tarefa não filtra as mensagens.</span><span class="sxs-lookup"><span data-stu-id="f4109-144">The task does not filter messages.</span></span> <span data-ttu-id="f4109-145">Selecionar este valor faz com que seja exibida a opção dinâmica **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="f4109-145">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="f4109-146">**Do pacote**</span><span class="sxs-lookup"><span data-stu-id="f4109-146">**From package**</span></span>|<span data-ttu-id="f4109-147">A mensagem recebe somente mensagens do pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="f4109-147">The message receives only messages from the specified package.</span></span> <span data-ttu-id="f4109-148">Selecionar este valor faz com que seja exibida a opção dinâmica **Identifier**.</span><span class="sxs-lookup"><span data-stu-id="f4109-148">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="f4109-149">Opções dinâmicas do filtro</span><span class="sxs-lookup"><span data-stu-id="f4109-149">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="f4109-150">Filtrar = Sem-filtro</span><span class="sxs-lookup"><span data-stu-id="f4109-150">Filter = No filter</span></span>  
 <span data-ttu-id="f4109-151">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="f4109-151">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="f4109-152">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="f4109-152">This option is read-only.</span></span> <span data-ttu-id="f4109-153">Pode ser em branco ou conter o GUID de um pacote quando a propriedade Filtrar tiver sido definida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f4109-153">It may be blank or contain the GUID of a package when the Filter property was previously set.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="f4109-154">Filtrar = Do pacote</span><span class="sxs-lookup"><span data-stu-id="f4109-154">Filter = From package</span></span>  
 <span data-ttu-id="f4109-155">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="f4109-155">**Identifier**</span></span>  
 <span data-ttu-id="f4109-156">Se você escolher aplicar um filtro, digite o identificador exclusivo do pacote do qual mensagens podem ser recebidas ou clique no botão de reticências **(…)** e especifique o pacote.</span><span class="sxs-lookup"><span data-stu-id="f4109-156">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="f4109-157">**Tópicos relacionados:** [Selecionar um Pacote](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="f4109-157">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="f4109-158">MessageType = Mensagem de variável</span><span class="sxs-lookup"><span data-stu-id="f4109-158">MessageType = Variable message</span></span>  
 <span data-ttu-id="f4109-159">**Filter**</span><span class="sxs-lookup"><span data-stu-id="f4109-159">**Filter**</span></span>  
 <span data-ttu-id="f4109-160">Especifique se deve ser aplicado um filtro às mensagens.</span><span class="sxs-lookup"><span data-stu-id="f4109-160">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="f4109-161">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4109-161">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="f4109-162">Valor</span><span class="sxs-lookup"><span data-stu-id="f4109-162">Value</span></span>|<span data-ttu-id="f4109-163">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4109-163">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f4109-164">**Sem-filtro**</span><span class="sxs-lookup"><span data-stu-id="f4109-164">**No filter**</span></span>|<span data-ttu-id="f4109-165">A tarefa não filtra as mensagens.</span><span class="sxs-lookup"><span data-stu-id="f4109-165">The task does not filter messages.</span></span> <span data-ttu-id="f4109-166">Selecionar este valor faz com que seja exibida a opção dinâmica **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="f4109-166">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="f4109-167">**Do pacote**</span><span class="sxs-lookup"><span data-stu-id="f4109-167">**From package**</span></span>|<span data-ttu-id="f4109-168">A mensagem recebe somente mensagens do pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="f4109-168">The message receives only messages from the specified package.</span></span> <span data-ttu-id="f4109-169">Selecionar este valor faz com que seja exibida a opção dinâmica **Identifier**.</span><span class="sxs-lookup"><span data-stu-id="f4109-169">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
 <span data-ttu-id="f4109-170">**Variável**</span><span class="sxs-lookup"><span data-stu-id="f4109-170">**Variable**</span></span>  
 <span data-ttu-id="f4109-171">Digite o nome da variável ou clique em \<**New variable...**> e configure uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="f4109-171">Type the variable name, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="f4109-172">**Tópicos relacionados:** [Adicionar Variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="f4109-172">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="f4109-173">Opções dinâmicas do filtro</span><span class="sxs-lookup"><span data-stu-id="f4109-173">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="f4109-174">Filtrar = Sem-filtro</span><span class="sxs-lookup"><span data-stu-id="f4109-174">Filter = No filter</span></span>  
 <span data-ttu-id="f4109-175">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="f4109-175">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="f4109-176">Esta opção fica em branco.</span><span class="sxs-lookup"><span data-stu-id="f4109-176">This option is blank.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="f4109-177">Filtrar = Do pacote</span><span class="sxs-lookup"><span data-stu-id="f4109-177">Filter = From package</span></span>  
 <span data-ttu-id="f4109-178">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="f4109-178">**Identifier**</span></span>  
 <span data-ttu-id="f4109-179">Se você escolher aplicar um filtro, digite o identificador exclusivo do pacote do qual mensagens podem ser recebidas ou clique no botão de reticências **(…)** e especifique o pacote.</span><span class="sxs-lookup"><span data-stu-id="f4109-179">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="f4109-180">**Tópicos relacionados:** [Selecionar um Pacote](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="f4109-180">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="f4109-181">MessageType = Mensagem de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f4109-181">MessageType = String message</span></span>  
 <span data-ttu-id="f4109-182">**Comparar**</span><span class="sxs-lookup"><span data-stu-id="f4109-182">**Compare**</span></span>  
 <span data-ttu-id="f4109-183">Especifique se deve ser aplicado um filtro às mensagens.</span><span class="sxs-lookup"><span data-stu-id="f4109-183">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="f4109-184">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4109-184">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="f4109-185">Valor</span><span class="sxs-lookup"><span data-stu-id="f4109-185">Value</span></span>|<span data-ttu-id="f4109-186">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4109-186">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f4109-187">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="f4109-187">**None**</span></span>|<span data-ttu-id="f4109-188">As mensagens não são comparadas.</span><span class="sxs-lookup"><span data-stu-id="f4109-188">Messages are not compared.</span></span>|  
|<span data-ttu-id="f4109-189">**Correspondência exata**</span><span class="sxs-lookup"><span data-stu-id="f4109-189">**Exact match**</span></span>|<span data-ttu-id="f4109-190">As mensagens devem corresponder exatamente à cadeia de caracteres na opção **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="f4109-190">Messages must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="f4109-191">**Ignora maiúsculas e minúsculas**</span><span class="sxs-lookup"><span data-stu-id="f4109-191">**Ignore case**</span></span>|<span data-ttu-id="f4109-192">A mensagem deve corresponder à cadeia de caracteres da opção **CompareString** , mas a comparação não diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f4109-192">Message must match the string in the **CompareString** option, but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="f4109-193">**Contendo**</span><span class="sxs-lookup"><span data-stu-id="f4109-193">**Containing**</span></span>|<span data-ttu-id="f4109-194">A mensagem deve conter a cadeia de caracteres na opção **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="f4109-194">Message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="f4109-195">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="f4109-195">**CompareString**</span></span>  
 <span data-ttu-id="f4109-196">A menos que a opção **Comparar** esteja definida como **Nenhum**, forneça a cadeia de caracteres com a qual a mensagem é comparada.</span><span class="sxs-lookup"><span data-stu-id="f4109-196">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
### <a name="messagetype--string-message-to-variable"></a><span data-ttu-id="f4109-197">MessageType = Mensagem de cadeia de caracteres para variável</span><span class="sxs-lookup"><span data-stu-id="f4109-197">MessageType = String message to variable</span></span>  
 <span data-ttu-id="f4109-198">**Comparar**</span><span class="sxs-lookup"><span data-stu-id="f4109-198">**Compare**</span></span>  
 <span data-ttu-id="f4109-199">Especifique se deve ser aplicado um filtro às mensagens.</span><span class="sxs-lookup"><span data-stu-id="f4109-199">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="f4109-200">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4109-200">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="f4109-201">Valor</span><span class="sxs-lookup"><span data-stu-id="f4109-201">Value</span></span>|<span data-ttu-id="f4109-202">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4109-202">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f4109-203">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="f4109-203">**None**</span></span>|<span data-ttu-id="f4109-204">As mensagens não são comparadas.</span><span class="sxs-lookup"><span data-stu-id="f4109-204">Messages are not compared.</span></span>|  
|<span data-ttu-id="f4109-205">**Correspondência exata**</span><span class="sxs-lookup"><span data-stu-id="f4109-205">**Exact match**</span></span>|<span data-ttu-id="f4109-206">A mensagem deve corresponder exatamente à cadeia de caracteres na opção **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="f4109-206">The message must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="f4109-207">**Ignora maiúsculas e minúsculas**</span><span class="sxs-lookup"><span data-stu-id="f4109-207">**Ignore case**</span></span>|<span data-ttu-id="f4109-208">A mensagem deve corresponder à cadeia de caracteres da opção **CompareString** , mas a comparação não diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f4109-208">The message must match the string in the **CompareString** option but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="f4109-209">**Contendo**</span><span class="sxs-lookup"><span data-stu-id="f4109-209">**Containing**</span></span>|<span data-ttu-id="f4109-210">A mensagem deve conter a cadeia de caracteres na opção **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="f4109-210">The message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="f4109-211">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="f4109-211">**CompareString**</span></span>  
 <span data-ttu-id="f4109-212">A menos que a opção **Comparar** esteja definida como **Nenhum**, forneça a cadeia de caracteres com a qual a mensagem é comparada.</span><span class="sxs-lookup"><span data-stu-id="f4109-212">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
 <span data-ttu-id="f4109-213">**Variável**</span><span class="sxs-lookup"><span data-stu-id="f4109-213">**Variable**</span></span>  
 <span data-ttu-id="f4109-214">Digite o nome da variável para manter a mensagem recebida ou clique em \<**New variable...**> e configure uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="f4109-214">Type the name of the variable to hold the received message, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="f4109-215">**Tópicos relacionados:** [Adicionar Variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="f4109-215">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4109-216">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4109-216">See Also</span></span>  
 <span data-ttu-id="f4109-217">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f4109-217">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f4109-218">[Editor da tarefa fila de mensagens &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="f4109-218">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="f4109-219">[Editor da tarefa fila de mensagens &#40;Enviar página&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="f4109-219">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 <span data-ttu-id="f4109-220">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="f4109-220">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="f4109-221">Tarefa Fila de Mensagens</span><span class="sxs-lookup"><span data-stu-id="f4109-221">Message Queue Task</span></span>](control-flow/message-queue-task.md)  
  
  
