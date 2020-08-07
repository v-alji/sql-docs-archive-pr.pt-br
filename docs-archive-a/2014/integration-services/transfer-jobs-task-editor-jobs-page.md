---
title: Editor da tarefa Transferir trabalhos (página trabalhos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.jobs.f1
helpviewer_keywords:
- Transfer Jobs Task Editor
ms.assetid: e72b1dc7-8cda-4ee6-abb5-d438370f04df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d2d506da6997965e40d66521f7dccb8218e165fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584199"
---
# <a name="transfer-jobs-task-editor-jobs-page"></a><span data-ttu-id="7934c-102">Editor da Tarefa Transferir Trabalhos (página Trabalhos)</span><span class="sxs-lookup"><span data-stu-id="7934c-102">Transfer Jobs Task Editor (Jobs Page)</span></span>
  <span data-ttu-id="7934c-103">Use a página **Trabalhos** da caixa de diálogo **Editor da Tarefa de Transferir Trabalhos** para especificar as propriedades para cópia de um ou mais trabalhos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent de uma instância de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para outra.</span><span class="sxs-lookup"><span data-stu-id="7934c-103">Use the **Jobs** page of the **Transfer Jobs Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="7934c-104">Para obter mais informações sobre a tarefa Transferir Trabalhos, consulte [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span><span class="sxs-lookup"><span data-stu-id="7934c-104">For more information about the Transfer Jobs task, see [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7934c-105">Para acessar trabalhos no servidor de origem, é necessário que os usuários sejam membros pelo menos da função do banco de dados fixa **SQLAgentUserRole** no servidor.</span><span class="sxs-lookup"><span data-stu-id="7934c-105">To access jobs on the source server, users must be a member of at least the **SQLAgentUserRole** fixed database role on the server.</span></span> <span data-ttu-id="7934c-106">Para criar trabalhos no servidor de destino com êxito, é necessário que o usuário seja um membro da função de servidor fixa **sysadmin** ou uma das funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="7934c-106">To successfully create jobs on the destination server, the user must be a member of the **sysadmin** fixed server role or one of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles.</span></span> <span data-ttu-id="7934c-107">Para obter mais informações sobre as funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent e suas permissões, consulte [Funções de banco de dados fixas do SQL Server Agent](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7934c-107">For more information about [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles and their permissions, see [SQL Server Agent Fixed Database Roles](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7934c-108">Opções</span><span class="sxs-lookup"><span data-stu-id="7934c-108">Options</span></span>  
 <span data-ttu-id="7934c-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="7934c-109">**SourceConnection**</span></span>  
 <span data-ttu-id="7934c-110">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="7934c-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="7934c-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="7934c-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="7934c-112">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7934c-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="7934c-113">**TransferAllJobs**</span><span class="sxs-lookup"><span data-stu-id="7934c-113">**TransferAllJobs**</span></span>  
 <span data-ttu-id="7934c-114">Selecione se a tarefa deve copiar todas ou apenas os trabalhos de Agente [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] especificados do servidor de origem para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7934c-114">Select whether the task should copy all or only the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from the source to the destination server.</span></span>  
  
 <span data-ttu-id="7934c-115">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="7934c-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="7934c-116">Valor</span><span class="sxs-lookup"><span data-stu-id="7934c-116">Value</span></span>|<span data-ttu-id="7934c-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="7934c-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7934c-118">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="7934c-118">**True**</span></span>|<span data-ttu-id="7934c-119">Copia todas as tarefas.</span><span class="sxs-lookup"><span data-stu-id="7934c-119">Copy all jobs.</span></span>|  
|<span data-ttu-id="7934c-120">**Falso**</span><span class="sxs-lookup"><span data-stu-id="7934c-120">**False**</span></span>|<span data-ttu-id="7934c-121">Copia apenas os trabalhos especificados.</span><span class="sxs-lookup"><span data-stu-id="7934c-121">Copy only the specified jobs.</span></span>|  
  
 <span data-ttu-id="7934c-122">**JobsList**</span><span class="sxs-lookup"><span data-stu-id="7934c-122">**JobsList**</span></span>  
 <span data-ttu-id="7934c-123">Clique no botão Procurar **(...)** para selecionar os trabalhos a serem copiados.</span><span class="sxs-lookup"><span data-stu-id="7934c-123">Click the browse button **(...)** to select the jobs to copy.</span></span> <span data-ttu-id="7934c-124">Pelo menos um trabalho deve ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="7934c-124">At least one job must be selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7934c-125">Especifique a **SourceConnection** antes de selecionar trabalhos para copiar.</span><span class="sxs-lookup"><span data-stu-id="7934c-125">Specify the **SourceConnection** before selecting jobs to copy.</span></span>  
  
 <span data-ttu-id="7934c-126">A opção **JobsList** não estará disponível quando **TransferAllJobs** for definido como **True**.</span><span class="sxs-lookup"><span data-stu-id="7934c-126">The **JobsList** option is unavailable when **TransferAllJobs** is set to **True**.</span></span>  
  
 <span data-ttu-id="7934c-127">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="7934c-127">**IfObjectExists**</span></span>  
 <span data-ttu-id="7934c-128">Selecione como a tarefa deve tratar trabalhos que tenham o mesmo nome já existente no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7934c-128">Select how the task should handle jobs of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="7934c-129">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="7934c-129">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="7934c-130">Valor</span><span class="sxs-lookup"><span data-stu-id="7934c-130">Value</span></span>|<span data-ttu-id="7934c-131">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7934c-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7934c-132">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="7934c-132">**FailTask**</span></span>|<span data-ttu-id="7934c-133">A tarefa irá falhar se já existirem trabalhos com o mesmo nome no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7934c-133">Task fails if jobs of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="7934c-134">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="7934c-134">**Overwrite**</span></span>|<span data-ttu-id="7934c-135">A tarefa irá substituir trabalhos de mesmo nome no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7934c-135">Task overwrites jobs of the same name on the destination server.</span></span>|  
|<span data-ttu-id="7934c-136">**Ignorar**</span><span class="sxs-lookup"><span data-stu-id="7934c-136">**Skip**</span></span>|<span data-ttu-id="7934c-137">A tarefa irá ignorar os trabalhos de mesmo nome que existem no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7934c-137">Task skips jobs of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="7934c-138">**EnableJobsAtDestination**</span><span class="sxs-lookup"><span data-stu-id="7934c-138">**EnableJobsAtDestination**</span></span>  
 <span data-ttu-id="7934c-139">Selecione se os trabalhos copiados para o servidor de destino devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="7934c-139">Select whether the jobs copied to the destination server should be enabled.</span></span>  
  
 <span data-ttu-id="7934c-140">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="7934c-140">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="7934c-141">Valor</span><span class="sxs-lookup"><span data-stu-id="7934c-141">Value</span></span>|<span data-ttu-id="7934c-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="7934c-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7934c-143">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="7934c-143">**True**</span></span>|<span data-ttu-id="7934c-144">Habilita trabalhos no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7934c-144">Enable jobs on destination server.</span></span>|  
|<span data-ttu-id="7934c-145">**Falso**</span><span class="sxs-lookup"><span data-stu-id="7934c-145">**False**</span></span>|<span data-ttu-id="7934c-146">Desabilita trabalhos no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7934c-146">Disable jobs on destination server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7934c-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7934c-147">See Also</span></span>  
 <span data-ttu-id="7934c-148">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7934c-148">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7934c-149">[Tarefas do Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="7934c-149">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="7934c-150">[Editor da tarefa Transferir trabalhos &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="7934c-150">[Transfer Jobs Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="7934c-151">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="7934c-151">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="7934c-152">Gerenciador de Conexões SMO</span><span class="sxs-lookup"><span data-stu-id="7934c-152">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
