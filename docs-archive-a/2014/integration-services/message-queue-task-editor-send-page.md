---
title: Editor da tarefa fila de mensagens (página Enviar) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.send.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 565aa079-ac44-4407-8efc-cddab839de30
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3534e1a8b475f22064ef7f2283c2e70eb561294f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686323"
---
# <a name="message-queue-task-editor-send-page"></a><span data-ttu-id="45e7b-102">Editor da Tarefa Fila de Mensagens (página Enviar)</span><span class="sxs-lookup"><span data-stu-id="45e7b-102">Message Queue Task Editor (Send Page)</span></span>
  <span data-ttu-id="45e7b-103">Use a página **Enviar** da caixa de diálogo **Editor da Tarefa Fila de Mensagens** para configurar uma tarefa de Fila de Mensagens para enviar mensagens de um pacote do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45e7b-103">Use the **Send** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to send messages from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="45e7b-104">Para obter informações sobre essa tarefa, consulte [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="45e7b-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="45e7b-105">Opções</span><span class="sxs-lookup"><span data-stu-id="45e7b-105">Options</span></span>  
 <span data-ttu-id="45e7b-106">**UseEncryption**</span><span class="sxs-lookup"><span data-stu-id="45e7b-106">**UseEncryption**</span></span>  
 <span data-ttu-id="45e7b-107">Indique se a mensagem deve ser criptografada.</span><span class="sxs-lookup"><span data-stu-id="45e7b-107">Indicate whether to encrypt the message.</span></span> <span data-ttu-id="45e7b-108">O padrão é `False`.</span><span class="sxs-lookup"><span data-stu-id="45e7b-108">The default is `False`.</span></span>  
  
 <span data-ttu-id="45e7b-109">**EncryptionAlgorithm**</span><span class="sxs-lookup"><span data-stu-id="45e7b-109">**EncryptionAlgorithm**</span></span>  
 <span data-ttu-id="45e7b-110">Se você escolher usar criptografia, especifique o nome do algoritmo de criptografia a ser utilizado.</span><span class="sxs-lookup"><span data-stu-id="45e7b-110">If you choose to use encryption, specify the name of the encryption algorithm to use.</span></span> <span data-ttu-id="45e7b-111">A tarefa Fila de Mensagens pode usar os algoritmos RC2 e RC4.</span><span class="sxs-lookup"><span data-stu-id="45e7b-111">The Message Queue task can use the RC2 and RC4 algorithms.</span></span> <span data-ttu-id="45e7b-112">O padrão é **RC2**.</span><span class="sxs-lookup"><span data-stu-id="45e7b-112">The default is **RC2**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45e7b-113">O algoritmo RC4 tem suporte somente para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="45e7b-113">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="45e7b-114">O novo material só pode ser criptografado por meio do algoritmo RC4 ou RC4_128 quando o banco de dados está no nível de compatibilidade 90 ou 100.</span><span class="sxs-lookup"><span data-stu-id="45e7b-114">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="45e7b-115">(Não recomendável.) Use um algoritmo mais recente; por exemplo, um dos algoritmos AES.</span><span class="sxs-lookup"><span data-stu-id="45e7b-115">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="45e7b-116">Na versão atual do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], o material criptografado por meio do algoritmo RC4 ou RC4_128 pode ser descriptografado em qualquer nível de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="45e7b-116">In the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="45e7b-117">Estes são os algoritmos de criptografia ao qual a tecnologia de serviço de Enfileiramento de Mensagens (também conhecido como MSMQ) oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="45e7b-117">These are the encryption algorithms that the Message Queuing (also known as MSMQ) technology supports.</span></span> <span data-ttu-id="45e7b-118">Atualmente, ambos algoritmos de criptografia são considerados criptograficamente fracos quando comparados a algoritmos mais novos, que não têm suporte no serviço de Enfileiramento de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="45e7b-118">Both of these encryption algorithms are now considered cryptographically weak compared to newer algorithms, which Message Queuing does not yet support.</span></span> <span data-ttu-id="45e7b-119">Então, você deve considerar cuidadosamente suas necessidades de criptografia ao enviar mensagens que usam a tarefa Fila de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="45e7b-119">Therefore, you should consider your cryptography needs carefully when sending messages using the Message Queue task.</span></span>  
  
 <span data-ttu-id="45e7b-120">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="45e7b-120">**MessageType**</span></span>  
 <span data-ttu-id="45e7b-121">Selecione o tipo de mensagem.</span><span class="sxs-lookup"><span data-stu-id="45e7b-121">Select the message type.</span></span> <span data-ttu-id="45e7b-122">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="45e7b-122">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="45e7b-123">Valor</span><span class="sxs-lookup"><span data-stu-id="45e7b-123">Value</span></span>|<span data-ttu-id="45e7b-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="45e7b-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="45e7b-125">**Mensagem do arquivo de dados**</span><span class="sxs-lookup"><span data-stu-id="45e7b-125">**Data file message**</span></span>|<span data-ttu-id="45e7b-126">A mensagem é armazenada em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="45e7b-126">The message is stored in a file.</span></span> <span data-ttu-id="45e7b-127">Selecionar este valor faz com que seja exibida a opção dinâmica **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="45e7b-127">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="45e7b-128">**Mensagem de variável**</span><span class="sxs-lookup"><span data-stu-id="45e7b-128">**Variable message**</span></span>|<span data-ttu-id="45e7b-129">A mensagem é armazenada em uma variável.</span><span class="sxs-lookup"><span data-stu-id="45e7b-129">The message is stored in a variable.</span></span> <span data-ttu-id="45e7b-130">Selecionar este valor faz com que seja exibida a opção dinâmica **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="45e7b-130">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="45e7b-131">**Mensagem de cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="45e7b-131">**String message**</span></span>|<span data-ttu-id="45e7b-132">A mensagem é armazenada em uma tarefa Fila de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="45e7b-132">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="45e7b-133">Selecionar este valor faz com que seja exibida a opção dinâmica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="45e7b-133">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="45e7b-134">Opções dinâmicas de MessageType</span><span class="sxs-lookup"><span data-stu-id="45e7b-134">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="45e7b-135">MessageType = Mensagem de arquivo de dados</span><span class="sxs-lookup"><span data-stu-id="45e7b-135">MessageType = Data file message</span></span>  
 <span data-ttu-id="45e7b-136">**DataFileMessage**</span><span class="sxs-lookup"><span data-stu-id="45e7b-136">**DataFileMessage**</span></span>  
 <span data-ttu-id="45e7b-137">Digite o caminho do arquivo de dados ou clique nas reticências **(…)** e localize o arquivo.</span><span class="sxs-lookup"><span data-stu-id="45e7b-137">Type the path of the data file, or click the ellipsis **(...)** and then locate the file.</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="45e7b-138">MessageType = Mensagem de variável</span><span class="sxs-lookup"><span data-stu-id="45e7b-138">MessageType = Variable message</span></span>  
 <span data-ttu-id="45e7b-139">**VariableMessage**</span><span class="sxs-lookup"><span data-stu-id="45e7b-139">**VariableMessage**</span></span>  
 <span data-ttu-id="45e7b-140">Digite os nomes de variáveis ou clique nas reticências **(...)** e, em seguida, selecione as variáveis.</span><span class="sxs-lookup"><span data-stu-id="45e7b-140">Type the variable names, or click the ellipsis **(...)** and then select the variables.</span></span> <span data-ttu-id="45e7b-141">As variáveis são separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="45e7b-141">Variables are separated by commas.</span></span>  
  
 <span data-ttu-id="45e7b-142">**Tópicos relacionados:** Selecionar variáveis</span><span class="sxs-lookup"><span data-stu-id="45e7b-142">**Related Topics:** Select Variables</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="45e7b-143">MessageType = Mensagem de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="45e7b-143">MessageType = String message</span></span>  
 <span data-ttu-id="45e7b-144">**StringMessage**</span><span class="sxs-lookup"><span data-stu-id="45e7b-144">**StringMessage**</span></span>  
 <span data-ttu-id="45e7b-145">Digite a mensagem de cadeia de caracteres ou clique nas reticências **(...)** e digite a mensagem na caixa de diálogo **Inserir Mensagem de Cadeia de Caracteres**.</span><span class="sxs-lookup"><span data-stu-id="45e7b-145">Type the string message, or click the ellipsis **(...)** and then type the message in the **Enter String Message** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e7b-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45e7b-146">See Also</span></span>  
 <span data-ttu-id="45e7b-147">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="45e7b-147">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="45e7b-148">[Editor da tarefa fila de mensagens &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="45e7b-148">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="45e7b-149">[Editor da tarefa fila de mensagens &#40;página receber&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="45e7b-149">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 [<span data-ttu-id="45e7b-150">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="45e7b-150">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
