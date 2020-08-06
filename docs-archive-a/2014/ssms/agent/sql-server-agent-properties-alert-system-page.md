---
title: Propriedades do SQL Server Agent (página Sistema de Alerta) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.alert.f1
ms.assetid: 3e6d3bfd-20ee-4593-86cc-f65b1c08c69d
author: stevestein
ms.author: sstein
ms.openlocfilehash: ff203be21efbd99b90f02261cfe94dd49bd0d849
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582257"
---
# <a name="sql-server-agent-properties-alert-system-page"></a><span data-ttu-id="70458-102">Propriedades do SQL Server Agent (página Sistema de Alerta)</span><span class="sxs-lookup"><span data-stu-id="70458-102">SQL Server Agent Properties (Alert System Page)</span></span>
  <span data-ttu-id="70458-103">Use esta página para ver e modificar as configurações de mensagens enviadas pelos alertas do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="70458-103">Use this page to view and modify the settings for messages sent by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70458-104">Opções</span><span class="sxs-lookup"><span data-stu-id="70458-104">Options</span></span>  
 <span data-ttu-id="70458-105">**Sessão de email**</span><span class="sxs-lookup"><span data-stu-id="70458-105">**Mail session**</span></span>  
 <span data-ttu-id="70458-106">As opções nessa seção configuram o Agent Mail do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70458-106">The options in this section configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span>  
  
 <span data-ttu-id="70458-107">**Habilitar perfil de email**</span><span class="sxs-lookup"><span data-stu-id="70458-107">**Enable mail profile**</span></span>  
 <span data-ttu-id="70458-108">Habilita o Agent Mail do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70458-108">Enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span> <span data-ttu-id="70458-109">Por padrão, o Agent Mail do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="70458-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail is not enabled.</span></span>  
  
 <span data-ttu-id="70458-110">**Sistema de email**</span><span class="sxs-lookup"><span data-stu-id="70458-110">**Mail System**</span></span>  
 <span data-ttu-id="70458-111">Define o sistema de email para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent usar.</span><span class="sxs-lookup"><span data-stu-id="70458-111">Sets the mail system for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="70458-112">Database Mail</span><span class="sxs-lookup"><span data-stu-id="70458-112">Database Mail</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70458-113">Após alterar o sistema de email, você deve reiniciar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="70458-113">After changing the e-mail system, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service for the change to take effect.</span></span>  
  
 <span data-ttu-id="70458-114">**Perfil de Email**</span><span class="sxs-lookup"><span data-stu-id="70458-114">**Mail Profile**</span></span>  
 <span data-ttu-id="70458-115">Define o perfil para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent usar.</span><span class="sxs-lookup"><span data-stu-id="70458-115">Sets the profile for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="70458-116">Você também pode selecionar **\<new Database Mail profile...>** para criar um novo perfil.</span><span class="sxs-lookup"><span data-stu-id="70458-116">You may also select **\<new Database Mail profile...>** to create a new profile.</span></span>  
  
 <span data-ttu-id="70458-117">**Emails por pager**</span><span class="sxs-lookup"><span data-stu-id="70458-117">**Pager e-mails**</span></span>  
 <span data-ttu-id="70458-118">As opções desta seção permitem configurar mensagens de email enviadas para endereços de pager para funcionarem com o seu sistema de paginação.</span><span class="sxs-lookup"><span data-stu-id="70458-118">The options in this section allow you to configure e-mail messages sent to pager addresses to work with your paging system.</span></span>  
  
 <span data-ttu-id="70458-119">**Formatação de endereço para emails de pager**</span><span class="sxs-lookup"><span data-stu-id="70458-119">**Address formatting for pager e-mails**</span></span>  
 <span data-ttu-id="70458-120">Essa seção permite que você especifique o formato dos endereços e a linha de assunto incluída nos emails de pager.</span><span class="sxs-lookup"><span data-stu-id="70458-120">This section allows you to specify the format of the addresses and the subject line included in pager e-mails.</span></span>  
  
 <span data-ttu-id="70458-121">**Linha Para**</span><span class="sxs-lookup"><span data-stu-id="70458-121">**To line**</span></span>  
 <span data-ttu-id="70458-122">Especifica as opções para a linha **Para** da mensagem</span><span class="sxs-lookup"><span data-stu-id="70458-122">Specifies the options for the **To** line of the message</span></span>  
  
 <span data-ttu-id="70458-123">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="70458-123">**Prefix**</span></span>  
 <span data-ttu-id="70458-124">Digite qualquer texto fixo que o seu sistema solicita no início da linha **Para** de mensagens enviadas a um pager.</span><span class="sxs-lookup"><span data-stu-id="70458-124">Type any fixed text that your system requires at the beginning of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="70458-125">**Pager**</span><span class="sxs-lookup"><span data-stu-id="70458-125">**Pager**</span></span>  
 <span data-ttu-id="70458-126">Inclui o endereço de email para a mensagem entre o prefixo e o sufixo.</span><span class="sxs-lookup"><span data-stu-id="70458-126">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="70458-127">**Suffix**</span><span class="sxs-lookup"><span data-stu-id="70458-127">**Suffix**</span></span>  
 <span data-ttu-id="70458-128">Digite qualquer texto fixo que o seu sistema de pagers solicita no fim da linha **Para** de mensagens enviadas a um pager.</span><span class="sxs-lookup"><span data-stu-id="70458-128">Type any fixed text that your paging system requires at the end of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="70458-129">**Linha Cc**</span><span class="sxs-lookup"><span data-stu-id="70458-129">**Cc line**</span></span>  
 <span data-ttu-id="70458-130">Especifica as opções para a linha **Cc** da mensagem.</span><span class="sxs-lookup"><span data-stu-id="70458-130">Specifies options for the **Cc** line of the message.</span></span>  
  
 <span data-ttu-id="70458-131">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="70458-131">**Prefix**</span></span>  
 <span data-ttu-id="70458-132">Digite qualquer texto fixo que o seu sistema solicita no início da linha **Cc** de mensagens enviadas a um pager.</span><span class="sxs-lookup"><span data-stu-id="70458-132">Type any fixed text that your system requires at the beginning of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="70458-133">**Pager**</span><span class="sxs-lookup"><span data-stu-id="70458-133">**Pager**</span></span>  
 <span data-ttu-id="70458-134">Inclui o endereço de email para a mensagem entre o prefixo e o sufixo.</span><span class="sxs-lookup"><span data-stu-id="70458-134">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="70458-135">**Suffix**</span><span class="sxs-lookup"><span data-stu-id="70458-135">**Suffix**</span></span>  
 <span data-ttu-id="70458-136">Digite qualquer texto fixo que o seu sistema de pagers solicita no fim da linha **Cc** de mensagens enviadas a um pager.</span><span class="sxs-lookup"><span data-stu-id="70458-136">Type any fixed text that your paging system requires at the end of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="70458-137">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="70458-137">**Subject**</span></span>  
 <span data-ttu-id="70458-138">Especifica as opções para o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="70458-138">Specifies the options for the subject of the message.</span></span>  
  
 <span data-ttu-id="70458-139">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="70458-139">**Prefix**</span></span>  
 <span data-ttu-id="70458-140">Digite qualquer texto fixo que o seu sistema de pagers solicita no início da linha **Assunto** de mensagens enviadas a um pager.</span><span class="sxs-lookup"><span data-stu-id="70458-140">Type any fixed text that your paging system requires at the beginning of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="70458-141">**Suffix**</span><span class="sxs-lookup"><span data-stu-id="70458-141">**Suffix**</span></span>  
 <span data-ttu-id="70458-142">Digite qualquer texto fixo que o seu sistema de pagers solicita no fim da linha **Assunto** de mensagens enviadas a um pager.</span><span class="sxs-lookup"><span data-stu-id="70458-142">Type any fixed text that your paging system requires at the end of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="70458-143">**Inclua o corpo de email em mensagem de notificação**</span><span class="sxs-lookup"><span data-stu-id="70458-143">**Include body of e-mail in notification message**</span></span>  
 <span data-ttu-id="70458-144">Inclui o corpo da mensagem de email na mensagem enviada ao pager.</span><span class="sxs-lookup"><span data-stu-id="70458-144">Includes the body of the e-mail message in the message sent to the pager.</span></span>  
  
 <span data-ttu-id="70458-145">**Operador à prova de falhas**</span><span class="sxs-lookup"><span data-stu-id="70458-145">**Fail-safe operator**</span></span>  
 <span data-ttu-id="70458-146">Essa seção permite que você especifique as opções para o operador à prova de falhas.</span><span class="sxs-lookup"><span data-stu-id="70458-146">This section allows you to specify the options for the fail-safe operator.</span></span>  
  
 <span data-ttu-id="70458-147">**Habilitar o operador à prova de falhas**</span><span class="sxs-lookup"><span data-stu-id="70458-147">**Enable fail-safe operator**</span></span>  
 <span data-ttu-id="70458-148">Especifica um operador à prova de falhas.</span><span class="sxs-lookup"><span data-stu-id="70458-148">Specifies a fail safe operator.</span></span>  
  
 <span data-ttu-id="70458-149">**Operador**</span><span class="sxs-lookup"><span data-stu-id="70458-149">**Operator**</span></span>  
 <span data-ttu-id="70458-150">Define o nome do operador para receber notificações à prova de falhas.</span><span class="sxs-lookup"><span data-stu-id="70458-150">Sets the name of the operator to receive fail-safe notifications.</span></span>  
  
 <span data-ttu-id="70458-151">**Notificar usando**</span><span class="sxs-lookup"><span data-stu-id="70458-151">**Notify using**</span></span>  
 <span data-ttu-id="70458-152">Define o método a usar ao notificar o operador à prova de falhas.</span><span class="sxs-lookup"><span data-stu-id="70458-152">Sets the method to use for notifying the fail-safe operator.</span></span>  
  
 <span data-ttu-id="70458-153">**Substituição de Token**</span><span class="sxs-lookup"><span data-stu-id="70458-153">**Token Replacement**</span></span>  
 <span data-ttu-id="70458-154">Essa seção permite que você habilite tokens de etapa de trabalho que podem ser usados em trabalhos executados pelos alertas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="70458-154">This section allows you to enable job step tokens that can be used in jobs run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="70458-155">Para obter mais informações sobre tokens de etapa de trabalho, consulte [Usar tokens em etapas de trabalho](use-tokens-in-job-steps.md).</span><span class="sxs-lookup"><span data-stu-id="70458-155">For more information about job step tokens, see [Use Tokens in Job Steps](use-tokens-in-job-steps.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="70458-156">Qualquer usuário do Windows com permissões de gravação no Log de Eventos do Windows pode acessar etapas de trabalho ativadas pelos alertas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="70458-156">Any Windows user with write permissions on the Windows Event Log may be able to access job steps that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="70458-157">Para evitar riscos de segurança, os tokens do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que podem ser usados em trabalhos ativados por alertas encontram-se desabilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="70458-157">To avoid this security risk, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tokens that can be used in jobs activated by alerts are disabled by default.</span></span> <span data-ttu-id="70458-158">Esses tokens são: **$(A-DBN)** , **$(A-SVR)** , **$(A-ERR)** , **$(A-SEV)** e **$(A-MSG)** .</span><span class="sxs-lookup"><span data-stu-id="70458-158">These tokens are: **$(A-DBN)**, **$(A-SVR)**, **$(A-ERR)**, **$(A-SEV)**, and **$(A-MSG)**.</span></span>  
>   
>  <span data-ttu-id="70458-159">Se precisar usar esses tokens, certifique-se de que apenas membros dos grupos de segurança confiáveis do Windows, como o grupo Administradores, tenham permissões de gravação no Log de Eventos do computador em que reside o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de habilitá-los.</span><span class="sxs-lookup"><span data-stu-id="70458-159">If you need to use these tokens, ensure that only members of trusted Windows security groups, such as the Administrators group, have write permissions on the Event Log of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resides before enabling them.</span></span>  
  
 <span data-ttu-id="70458-160">**Substitua os tokens para todas as respostas de trabalho a alertas**</span><span class="sxs-lookup"><span data-stu-id="70458-160">**Replace tokens for all job responses to alerts**</span></span>  
 <span data-ttu-id="70458-161">Marque essa caixa de seleção para habilitar a substituição de token para trabalhos que são ativados pelos alertas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70458-161">Select this check box to enable token replacement for jobs that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70458-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70458-162">See Also</span></span>  
 <span data-ttu-id="70458-163">[Operações](operators.md) </span><span class="sxs-lookup"><span data-stu-id="70458-163">[Operators](operators.md) </span></span>  
 <span data-ttu-id="70458-164">[Configurar o SQL Server Agent email a ser usado Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="70458-164">[Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span></span>  
 [<span data-ttu-id="70458-165">Database Mail</span><span class="sxs-lookup"><span data-stu-id="70458-165">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
