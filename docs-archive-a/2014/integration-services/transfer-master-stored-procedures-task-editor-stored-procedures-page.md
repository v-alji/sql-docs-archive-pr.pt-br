---
title: Editor da tarefa Transferir procedimentos armazenados mestres (página procedimentos armazenados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.storedprocedures.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: 5fcf171e-cc0b-4c24-8eb5-3a4b4775e64a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5f9fad408b54d4ef27d4c5d06b0d352f366ad9c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681756"
---
# <a name="transfer-master-stored-procedures-task-editor-stored-procedures-page"></a><span data-ttu-id="e9066-102">Editor da Tarefa Transferir Procedimentos Armazenados Mestres (páginas Procedimentos Armazenados)</span><span class="sxs-lookup"><span data-stu-id="e9066-102">Transfer Master Stored Procedures Task Editor (Stored Procedures Page)</span></span>
  <span data-ttu-id="e9066-103">Use a página **Procedimentos Armazenados** da caixa de diálogo **Editor da Tarefa Transferir Procedimentos Armazenados Mestres** para especificar propriedades para copiar um ou mais procedimentos armazenados definidos pelo usuário do banco de dados **mestre** em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para um banco de dados **mestre** em outra instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9066-103">Use the **Stored Procedures** page of the **Transfer Master Stored Procedures Task Editor** dialog box to specify properties for copying one or more user-defined stored procedures from the **master** database in one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to a **master** database in another instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e9066-104">Para obter mais informações sobre essa tarefa, consulte [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="e9066-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9066-105">Essa tarefa transfere apenas procedimentos armazenados definidos pelo usuário pertencentes ao **dbo** de um banco de dados **mestre** no servidor de origem para um banco de dados **mestre** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e9066-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="e9066-106">Os usuários devem receber a permissão CREATE PROCEDURE no banco de dados **mestre** no servidor de destino ou devem ser membros da função de servidor fixa **sysadmin** no servidor de destino para criar procedimentos armazenados ali.</span><span class="sxs-lookup"><span data-stu-id="e9066-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e9066-107">Opções</span><span class="sxs-lookup"><span data-stu-id="e9066-107">Options</span></span>  
 <span data-ttu-id="e9066-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="e9066-108">**SourceConnection**</span></span>  
 <span data-ttu-id="e9066-109">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="e9066-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="e9066-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="e9066-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="e9066-111">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e9066-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="e9066-112">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="e9066-112">**IfObjectExists**</span></span>  
 <span data-ttu-id="e9066-113">Selecione como a tarefa deve manipular procedimentos armazenados definidos pelo usuário de nome idêntico a outros já existentes no banco de dados **mestre** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e9066-113">Select how the task should handle user-defined stored procedures of the same name that already exist in the **master** database on the destination server.</span></span>  
  
 <span data-ttu-id="e9066-114">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e9066-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="e9066-115">Valor</span><span class="sxs-lookup"><span data-stu-id="e9066-115">Value</span></span>|<span data-ttu-id="e9066-116">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e9066-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e9066-117">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="e9066-117">**FailTask**</span></span>|<span data-ttu-id="e9066-118">Haverá falha na tarefa se já existirem procedimentos armazenados de nome igual no banco de dados **mestre** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e9066-118">Task fails if stored procedures of the same name already exist in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="e9066-119">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="e9066-119">**Overwrite**</span></span>|<span data-ttu-id="e9066-120">A tarefa irá substituir os procedimentos armazenados de nome igual no banco de dados **mestre** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e9066-120">Task overwrites stored procedures of the same name in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="e9066-121">**Ignorar**</span><span class="sxs-lookup"><span data-stu-id="e9066-121">**Skip**</span></span>|<span data-ttu-id="e9066-122">A tarefa irá ignorar os procedimentos armazenados de nome igual já existentes no banco de dados **mestre** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e9066-122">Task skips stored procedures of the same name that exist in the **master** database on the destination server.</span></span>|  
  
 <span data-ttu-id="e9066-123">**TransferAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="e9066-123">**TransferAllStoredProcedures**</span></span>  
 <span data-ttu-id="e9066-124">Selecione se todos os procedimentos armazenados definidos pelo usuário no banco de dados **mestre** no servidor de origem devem ser copiados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e9066-124">Select whether all user-defined stored procedures in the **master** database on the source server should be copied to the destination server.</span></span>  
  
|<span data-ttu-id="e9066-125">Valor</span><span class="sxs-lookup"><span data-stu-id="e9066-125">Value</span></span>|<span data-ttu-id="e9066-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="e9066-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e9066-127">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="e9066-127">**True**</span></span>|<span data-ttu-id="e9066-128">Copiar todos os procedimentos armazenados definidos pelo usuário no banco de dados **mestre** .</span><span class="sxs-lookup"><span data-stu-id="e9066-128">Copy all user-defined stored procedures in the **master** database.</span></span>|  
|<span data-ttu-id="e9066-129">**Falso**</span><span class="sxs-lookup"><span data-stu-id="e9066-129">**False**</span></span>|<span data-ttu-id="e9066-130">Copiar só os procedimentos armazenados especificados.</span><span class="sxs-lookup"><span data-stu-id="e9066-130">Copy only the specified stored procedures.</span></span>|  
  
 <span data-ttu-id="e9066-131">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="e9066-131">**StoredProceduresList**</span></span>  
 <span data-ttu-id="e9066-132">Selecione quais procedimentos armazenados definidos pelo usuário no banco de dados **mestre** no servidor de origem devem ser copiados para o banco de dados **mestre** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="e9066-132">Select which user-defined stored procedures in the **master** database on the source server should be copied to the destination **master** database.</span></span> <span data-ttu-id="e9066-133">Esta opção só fica disponível quando **TransferAllStoredProcedures** for definido como **False**.</span><span class="sxs-lookup"><span data-stu-id="e9066-133">This option is only available when **TransferAllStoredProcedures** is set to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9066-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9066-134">See Also</span></span>  
 <span data-ttu-id="e9066-135">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e9066-135">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e9066-136">[Tarefas do Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="e9066-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="e9066-137">[Editor da tarefa Transferir procedimentos armazenados mestres &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e9066-137">[Transfer Master Stored Procedures Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="e9066-138">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="e9066-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="e9066-139">Gerenciador de Conexões SMO</span><span class="sxs-lookup"><span data-stu-id="e9066-139">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
