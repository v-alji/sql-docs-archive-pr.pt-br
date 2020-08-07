---
title: Editor da tarefa transferir mensagens de erro (página mensagens) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.errormessages.F1
helpviewer_keywords:
- Transfer Error Messages Task Editor
ms.assetid: cb2226a0-3037-4fdf-966f-81eabc0da9cf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0d626f01e05a30777810b26880da5aedc3e7ad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584200"
---
# <a name="transfer-error-messages-task-editor-messages-page"></a><span data-ttu-id="d8316-102">Editor da Tarefa Transferir Mensagens de Erro (página Mensagens)</span><span class="sxs-lookup"><span data-stu-id="d8316-102">Transfer Error Messages Task Editor (Messages Page)</span></span>
  <span data-ttu-id="d8316-103">Use a página **Mensagens** da caixa de diálogo **Editor da Tarefa Transferir Mensagens de Erro** para especificar as propriedades de cópia de uma ou mais mensagens de erro [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] definidas pelo usuário de uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para outra.</span><span class="sxs-lookup"><span data-stu-id="d8316-103">Use the **Messages** page of the **Transfer Error Messages Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] user-defined error messages from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="d8316-104">Para obter mais informações sobre essa tarefa, consulte [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span><span class="sxs-lookup"><span data-stu-id="d8316-104">For more information about this task, see [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d8316-105">Opções</span><span class="sxs-lookup"><span data-stu-id="d8316-105">Options</span></span>  
 <span data-ttu-id="d8316-106">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="d8316-106">**SourceConnection**</span></span>  
 <span data-ttu-id="d8316-107">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="d8316-107">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="d8316-108">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="d8316-108">**DestinationConnection**</span></span>  
 <span data-ttu-id="d8316-109">Selecione um gerenciador de conexões SMO na lista ou clique em **\<New connection...>** para criar uma conexão com o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d8316-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="d8316-110">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="d8316-110">**IfObjectExists**</span></span>  
 <span data-ttu-id="d8316-111">Selecione se a tarefa deve substituir mensagens de erro definidas pelo usuário existentes, ignorar mensagens existentes ou causar falha se mensagens de erro de mesmo nome já existirem no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d8316-111">Select whether the task should overwrite existing user-defined error messages, skip existing messages, or fail if error messages of the same name already exist on the destination server.</span></span>  
  
 <span data-ttu-id="d8316-112">**TransferAllErrorMessages**</span><span class="sxs-lookup"><span data-stu-id="d8316-112">**TransferAllErrorMessages**</span></span>  
 <span data-ttu-id="d8316-113">Selecione se a tarefa deve copiar todas ou somente as mensagens especificadas definidas pelo usuário do servidor de origem para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d8316-113">Select whether the task should copy all or only the specified user-defined messages from the source server to the destination server.</span></span>  
  
 <span data-ttu-id="d8316-114">As opções desta propriedade estão listadas na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="d8316-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="d8316-115">Valor</span><span class="sxs-lookup"><span data-stu-id="d8316-115">Value</span></span>|<span data-ttu-id="d8316-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="d8316-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d8316-117">**Verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="d8316-117">**True**</span></span>|<span data-ttu-id="d8316-118">Copia todas as mensagens definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="d8316-118">Copy all user-defined messages.</span></span>|  
|<span data-ttu-id="d8316-119">**Falso**</span><span class="sxs-lookup"><span data-stu-id="d8316-119">**False**</span></span>|<span data-ttu-id="d8316-120">Copia só as mensagens definidas pelo usuário especificadas.</span><span class="sxs-lookup"><span data-stu-id="d8316-120">Copy only the specified user-defined messages.</span></span>|  
  
 <span data-ttu-id="d8316-121">**ErrorMessagesList**</span><span class="sxs-lookup"><span data-stu-id="d8316-121">**ErrorMessagesList**</span></span>  
 <span data-ttu-id="d8316-122">Clique no botão Procurar **(...)** para selecionar as mensagens de erro para copiar.</span><span class="sxs-lookup"><span data-stu-id="d8316-122">Click the browse button **(...)** to select the error messages to copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8316-123">É necessário especificar o **SourceConnection** antes que seja possível selecionar mensagens de erro para copiar.</span><span class="sxs-lookup"><span data-stu-id="d8316-123">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
 <span data-ttu-id="d8316-124">**ErrorMessageLanguagesList**</span><span class="sxs-lookup"><span data-stu-id="d8316-124">**ErrorMessageLanguagesList**</span></span>  
 <span data-ttu-id="d8316-125">Clique no botão Procurar **(...)** para selecionar os idiomas para os quais copiar mensagens de erro definidas pelo usuário para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="d8316-125">Click the browse button **(...)** to select the languages for which to copy user-defined error messages to the destination server.</span></span> <span data-ttu-id="d8316-126">Uma versão us_english (página de código 1033) da mensagem deve estar no servidor de destino para que seja possível transferir versões da mensagem em outro idioma para esse servidor.</span><span class="sxs-lookup"><span data-stu-id="d8316-126">A us_english (code page 1033) version of the message must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8316-127">É necessário especificar o **SourceConnection** antes que seja possível selecionar mensagens de erro para copiar.</span><span class="sxs-lookup"><span data-stu-id="d8316-127">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8316-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8316-128">See Also</span></span>  
 <span data-ttu-id="d8316-129">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d8316-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d8316-130">[Tarefas do Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="d8316-130">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="d8316-131">[Editor da tarefa transferir mensagens de erro &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d8316-131">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="d8316-132">[Gerenciador de conexões SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d8316-132">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="d8316-133">[Editor da tarefa transferir mensagens de erro &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d8316-133">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="d8316-134">Gerenciador de Conexões SMO</span><span class="sxs-lookup"><span data-stu-id="d8316-134">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
