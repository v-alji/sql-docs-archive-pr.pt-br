---
title: Tarefa Notificar Operador (plano de manutenção) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.notifyoperator.f1
helpviewer_keywords:
- Notify Operator Task dialog box
ms.assetid: 39c0797c-ad2b-4591-85c9-a23a7f902895
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb59622c2a42de67193c75d545a6b8a2a08863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575119"
---
# <a name="notify-operator-task-maintenance-plan"></a><span data-ttu-id="228ec-102">Tarefa de Notificação do Operador (Plano de Manutenção)</span><span class="sxs-lookup"><span data-stu-id="228ec-102">Notify Operator Task (Maintenance Plan)</span></span>
  <span data-ttu-id="228ec-103">Use a caixa de diálogo **Tarefa de Notificação do Operador** para adicionar uma notificação automática a este plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="228ec-103">Use the **Notify Operators Task** dialog to add an automatic notification to this maintenance plan.</span></span> <span data-ttu-id="228ec-104">Para usar essa tarefa, é necessário ter o Database Mail habilitado e configurado de maneira adequada com o MSDB como um Banco de Dados Host de Email, além de ter um operador do Agente de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com um endereço de email válido.</span><span class="sxs-lookup"><span data-stu-id="228ec-104">To use this task you must have Database Mail enabled and properly configured with MSDB as a Mail Host Database, and have a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator with a valid e-mail address.</span></span>  
  
 <span data-ttu-id="228ec-105">Esta tarefa usa o procedimento armazenado sp_notify_operator.</span><span class="sxs-lookup"><span data-stu-id="228ec-105">This task uses the sp_notify_operator stored procedure.</span></span>  
  
## <a name="options"></a><span data-ttu-id="228ec-106">Opções</span><span class="sxs-lookup"><span data-stu-id="228ec-106">Options</span></span>  
 <span data-ttu-id="228ec-107">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="228ec-107">**Connection**</span></span>  
 <span data-ttu-id="228ec-108">Selecione a conexão de servidor a ser usada na execução desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="228ec-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="228ec-109">**Novo**</span><span class="sxs-lookup"><span data-stu-id="228ec-109">**New**</span></span>  
 <span data-ttu-id="228ec-110">Crie uma nova conexão com o servidor para usar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="228ec-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="228ec-111">A caixa de diálogo **Nova Conexão** é descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="228ec-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="228ec-112">**Operadores a notificar**</span><span class="sxs-lookup"><span data-stu-id="228ec-112">**Operators to notify**</span></span>  
 <span data-ttu-id="228ec-113">Especifique o destinatário do email.</span><span class="sxs-lookup"><span data-stu-id="228ec-113">Specify the recipient of the e-mail.</span></span>  
  
 <span data-ttu-id="228ec-114">**Assunto da mensagem de notificação**</span><span class="sxs-lookup"><span data-stu-id="228ec-114">**Notification message subject**</span></span>  
 <span data-ttu-id="228ec-115">Especifique o texto a ser incluído na linha do assunto da mensagem de notificação.</span><span class="sxs-lookup"><span data-stu-id="228ec-115">Specify the text to include in the notification message subject line.</span></span>  
  
 <span data-ttu-id="228ec-116">**Corpo da mensagem de notificação**</span><span class="sxs-lookup"><span data-stu-id="228ec-116">**Notification message body**</span></span>  
 <span data-ttu-id="228ec-117">Especifique o texto a ser incluído no corpo da mensagem de notificação.</span><span class="sxs-lookup"><span data-stu-id="228ec-117">Specify the text to include in the notification message body.</span></span>  
  
 <span data-ttu-id="228ec-118">**Exibir T-SQL**</span><span class="sxs-lookup"><span data-stu-id="228ec-118">**View T-SQL**</span></span>  
 <span data-ttu-id="228ec-119">Exiba as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] executadas no servidor para esta tarefa, com base nas opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="228ec-119">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="228ec-120">Quando o número de objetos afetados é grande, essa exibição pode ser demorada.</span><span class="sxs-lookup"><span data-stu-id="228ec-120">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="228ec-121">Caixa de diálogo Nova Conexão</span><span class="sxs-lookup"><span data-stu-id="228ec-121">New Connection Dialog Box</span></span>  
 <span data-ttu-id="228ec-122">**Nome da conexão**</span><span class="sxs-lookup"><span data-stu-id="228ec-122">**Connection name**</span></span>  
 <span data-ttu-id="228ec-123">Digite um nome para a nova conexão.</span><span class="sxs-lookup"><span data-stu-id="228ec-123">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="228ec-124">**Selecione ou digite um nome de servidor**</span><span class="sxs-lookup"><span data-stu-id="228ec-124">**Select or enter a server name**</span></span>  
 <span data-ttu-id="228ec-125">Selecione um servidor com o qual se conectar ao executar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="228ec-125">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="228ec-126">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="228ec-126">**Refresh**</span></span>  
 <span data-ttu-id="228ec-127">Atualize a lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="228ec-127">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="228ec-128">**Digite as informações para fazer logon no servidor**</span><span class="sxs-lookup"><span data-stu-id="228ec-128">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="228ec-129">Especifica como autenticar no servidor.</span><span class="sxs-lookup"><span data-stu-id="228ec-129">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="228ec-130">**Use a segurança integrada do Windows**</span><span class="sxs-lookup"><span data-stu-id="228ec-130">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="228ec-131">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] com a Autenticação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="228ec-131">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="228ec-132">**Usar nome de usuário e senha específicos**</span><span class="sxs-lookup"><span data-stu-id="228ec-132">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="228ec-133">Conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="228ec-133">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="228ec-134">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="228ec-134">This option is not available.</span></span>  
  
 <span data-ttu-id="228ec-135">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="228ec-135">**User name**</span></span>  
 <span data-ttu-id="228ec-136">Forneça um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usado na autenticação.</span><span class="sxs-lookup"><span data-stu-id="228ec-136">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="228ec-137">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="228ec-137">This option is not available.</span></span>  
  
 <span data-ttu-id="228ec-138">**Senha**</span><span class="sxs-lookup"><span data-stu-id="228ec-138">**Password**</span></span>  
 <span data-ttu-id="228ec-139">Forneça uma senha a ser usada na autenticação.</span><span class="sxs-lookup"><span data-stu-id="228ec-139">Provide a password to use when authenticating.</span></span> <span data-ttu-id="228ec-140">Essa opção não está disponível.</span><span class="sxs-lookup"><span data-stu-id="228ec-140">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228ec-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="228ec-141">See Also</span></span>  
 <span data-ttu-id="228ec-142">[Database Mail](../database-mail/database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="228ec-142">[Database Mail](../database-mail/database-mail.md) </span></span>  
 [<span data-ttu-id="228ec-143">sp_notify_operator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="228ec-143">sp_notify_operator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-notify-operator-transact-sql)  
  
  
