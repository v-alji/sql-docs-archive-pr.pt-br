---
title: Editor da tarefa Transferir Logons (página Logons) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.logins.f1
helpviewer_keywords:
- Transfer Logins Task Editor
ms.assetid: bf244c24-bd45-4ece-b66b-78b488f35c5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33fea6c78df75b7eebe8987f952dce33bdc4407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584192"
---
# <a name="transfer-logins-task-editor-logins-page"></a><span data-ttu-id="a5538-102">Editor da Tarefa Transferir Logons (página Logons)</span><span class="sxs-lookup"><span data-stu-id="a5538-102">Transfer Logins Task Editor (Logins Page)</span></span>
  <span data-ttu-id="a5538-103">Use a página **Logons** da caixa de diálogo **Editor da Tarefa de Transferir Logons** para especificar as propriedades para copiar um ou mais logons [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] de uma instância de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para outra.</span><span class="sxs-lookup"><span data-stu-id="a5538-103">Use the **Logins** page of the **Transfer Logins Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="a5538-104">Para obter mais informações sobre essa tarefa, consulte [Tarefa Transferir Logons](control-flow/transfer-logins-task.md).</span><span class="sxs-lookup"><span data-stu-id="a5538-104">For more information about this task, see [Transfer Logins Task](control-flow/transfer-logins-task.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a5538-105">Quando a tarefa de Transferir Logons é executada, os logons são criados no servidor de destino com senhas aleatórias e as senhas são desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="a5538-105">When the Transfer Logins task is executed, logins are created on the destination server with random passwords and the passwords are disabled.</span></span> <span data-ttu-id="a5538-106">Para usar esses logons, um membro da função de servidor fixa **sysadmin** deve alterar as senhas e habilitá-las.</span><span class="sxs-lookup"><span data-stu-id="a5538-106">To use these logins, a member of the **sysadmin** fixed server role must change the passwords and then enable them.</span></span> <span data-ttu-id="a5538-107">O logon do **sa** não pode ser transferido.</span><span class="sxs-lookup"><span data-stu-id="a5538-107">The **sa** login cannot be transferred.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5538-108">Opções</span><span class="sxs-lookup"><span data-stu-id="a5538-108">Options</span></span>  
 <span data-ttu-id="a5538-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="a5538-109">**SourceConnection**</span></span>  
 <span data-ttu-id="a5538-110">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="a5538-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="a5538-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="a5538-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="a5538-112">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="a5538-113">**LoginsToTransfer**</span><span class="sxs-lookup"><span data-stu-id="a5538-113">**LoginsToTransfer**</span></span>  
 <span data-ttu-id="a5538-114">Selecione os logons [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para copiar da fonte para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-114">Select the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins to copy from the source to the destination server.</span></span> <span data-ttu-id="a5538-115">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="a5538-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="a5538-116">Valor</span><span class="sxs-lookup"><span data-stu-id="a5538-116">Value</span></span>|<span data-ttu-id="a5538-117">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a5538-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5538-118">**AllLogins**</span><span class="sxs-lookup"><span data-stu-id="a5538-118">**AllLogins**</span></span>|<span data-ttu-id="a5538-119">Todos os logons [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no servidor de origem serão copiados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-119">All [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins on the source server will be copied to the destination server.</span></span>|  
|<span data-ttu-id="a5538-120">**SelectedLogins**</span><span class="sxs-lookup"><span data-stu-id="a5538-120">**SelectedLogins**</span></span>|<span data-ttu-id="a5538-121">Apenas os logons especificados com **LoginsList** serão copiados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-121">Only logins specified with **LoginsList** will be copied to the destination server.</span></span>|  
|<span data-ttu-id="a5538-122">**AllLoginsFromSelectedDatabases**</span><span class="sxs-lookup"><span data-stu-id="a5538-122">**AllLoginsFromSelectedDatabases**</span></span>|<span data-ttu-id="a5538-123">Todos os logons do banco de dados especificados com **DatabasesList** serão copiados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-123">All logins from the databases specified with **DatabasesList** will be copied to the destination server.</span></span>|  
  
 <span data-ttu-id="a5538-124">**LoginsList**</span><span class="sxs-lookup"><span data-stu-id="a5538-124">**LoginsList**</span></span>  
 <span data-ttu-id="a5538-125">Selecione os logons no servidor de origem serão copiados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-125">Select the logins on the source server to be copied to the destination server.</span></span> <span data-ttu-id="a5538-126">Esta opção somente está disponível quando **SelectedLogins** é selecionado para **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="a5538-126">This option is only available when **SelectedLogins** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="a5538-127">**DatabasesList**</span><span class="sxs-lookup"><span data-stu-id="a5538-127">**DatabasesList**</span></span>  
 <span data-ttu-id="a5538-128">Selecione os logons no servidor de origem que serão copiados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-128">Select the databases on the source server that contain logins to be copied to the destination server.</span></span> <span data-ttu-id="a5538-129">Esta opção somente está disponível quando **AllLoginsFromSelectedDatabases** é selecionado para **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="a5538-129">This option is only available when **AllLoginsFromSelectedDatabases** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="a5538-130">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="a5538-130">**IfObjectExists**</span></span>  
 <span data-ttu-id="a5538-131">Selecione como a tarefa deve tratar logons que tenham o mesmo nome já existente no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-131">Select how the task should handle logins of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="a5538-132">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="a5538-132">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="a5538-133">Valor</span><span class="sxs-lookup"><span data-stu-id="a5538-133">Value</span></span>|<span data-ttu-id="a5538-134">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a5538-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5538-135">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="a5538-135">**FailTask**</span></span>|<span data-ttu-id="a5538-136">A tarefa irá falhar se já existirem logons com o mesmo nome no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-136">Task fails if logins of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="a5538-137">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="a5538-137">**Overwrite**</span></span>|<span data-ttu-id="a5538-138">A tarefa irá substituir logons de mesmo nome no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-138">Task overwrites logins of the same name on the destination server.</span></span>|  
|<span data-ttu-id="a5538-139">**Ignorar**</span><span class="sxs-lookup"><span data-stu-id="a5538-139">**Skip**</span></span>|<span data-ttu-id="a5538-140">A tarefa irá ignorar os logons de mesmo nome que existem no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-140">Task skips logins of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="a5538-141">**CopySids**</span><span class="sxs-lookup"><span data-stu-id="a5538-141">**CopySids**</span></span>  
 <span data-ttu-id="a5538-142">Selecione se os identificadores de segurança associados aos logons devem ser copiados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a5538-142">Select whether the security identifiers associated with the logins should be copied to the destination server.</span></span> <span data-ttu-id="a5538-143">Será necessário definir**CopySids** para **True** se a tarefa Transferir Logons for usada junto com a tarefa Transferir Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="a5538-143">**CopySids** must be set to **True** if the Transfer Logins task is used along with the Transfer Database task.</span></span> <span data-ttu-id="a5538-144">Caso contrário, os logons copiados não serão reconhecidos pelo banco de dados transferido.</span><span class="sxs-lookup"><span data-stu-id="a5538-144">Otherwise, the copied logins will not be recognized by the transferred database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5538-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5538-145">See Also</span></span>  
 <span data-ttu-id="a5538-146">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a5538-146">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a5538-147">[Tarefas do Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a5538-147">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="a5538-148">[Editor da tarefa Transferir Logons &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a5538-148">[Transfer Logins Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="a5538-149">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="a5538-149">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="a5538-150">[Gerenciador de conexões SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a5538-150">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="a5538-151">[Senhas fortes](../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="a5538-151">[Strong Passwords](../relational-databases/security/strong-passwords.md) </span></span>  
 [<span data-ttu-id="a5538-152">Considerações sobre segurança para uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5538-152">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
