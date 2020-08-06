---
title: Operadores | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- operators (users) [Database Engine]
- fail-safe operator [SQL Server]
- aliases [SQL Server], operators
- SQL Server Agent alerts, operators
- contact information [SQL Server Agent]
- net send [SQL Server]
- e-mail [SQL Server], SQL Server Agent operators
- pager notifications [SQL Server Agent]
- mail [SQL Server], SQL Server Agent operators
- operators (users) [Database Engine], defining
- jobs [SQL Server Agent], operators
- alerts [SQL Server], operators
ms.assetid: 38e8488f-2669-4cea-b9c3-5f394a663678
author: stevestein
ms.author: sstein
ms.openlocfilehash: d141a2db9a69603701200bc50dcac57ef402968a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683300"
---
# <a name="operators"></a><span data-ttu-id="8d238-102">Operadores</span><span class="sxs-lookup"><span data-stu-id="8d238-102">Operators</span></span>
  <span data-ttu-id="8d238-103">Operadores são aliases de pessoas ou grupos que podem receber notificações eletrônicas sobre a conclusão de trabalhos ou emissões de alertas.</span><span class="sxs-lookup"><span data-stu-id="8d238-103">Operators are aliases for people or groups that can receive electronic notification when jobs have completed or alerts have been raised.</span></span> <span data-ttu-id="8d238-104">O serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dá suporte à notificação de administradores através de operadores.</span><span class="sxs-lookup"><span data-stu-id="8d238-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service supports the notification of administrators through operators.</span></span> <span data-ttu-id="8d238-105">Os operadores habilitam a notificação e o monitoramento de recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="8d238-105">Operators enable notification and monitoring capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="operator-attributes-and-concepts"></a><span data-ttu-id="8d238-106">Atributos e conceitos do operador</span><span class="sxs-lookup"><span data-stu-id="8d238-106">Operator Attributes and Concepts</span></span>  
 <span data-ttu-id="8d238-107">Os atributos primários de um operador são:</span><span class="sxs-lookup"><span data-stu-id="8d238-107">The primary attributes of an operator are:</span></span>  
  
-   <span data-ttu-id="8d238-108">Nome do operador</span><span class="sxs-lookup"><span data-stu-id="8d238-108">Operator name</span></span>  
  
-   <span data-ttu-id="8d238-109">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="8d238-109">Contact information</span></span>  
  
### <a name="naming-an-operator"></a><span data-ttu-id="8d238-110">Nomeando um operador</span><span class="sxs-lookup"><span data-stu-id="8d238-110">Naming an Operator</span></span>  
 <span data-ttu-id="8d238-111">Todo operador deve ter um nome.</span><span class="sxs-lookup"><span data-stu-id="8d238-111">Every operator must have a name.</span></span> <span data-ttu-id="8d238-112">Os nomes de operador devem ser exclusivos dentro da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e não podem ultrapassar **128** caracteres.</span><span class="sxs-lookup"><span data-stu-id="8d238-112">Operator names must be unique within the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and can be no longer than **128** characters.</span></span>  
  
### <a name="contact-information"></a><span data-ttu-id="8d238-113">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="8d238-113">Contact Information</span></span>  
 <span data-ttu-id="8d238-114">As informações de contato de um operador definem como ele é notificado.</span><span class="sxs-lookup"><span data-stu-id="8d238-114">An operator's contact information defines how the operator is notified.</span></span> <span data-ttu-id="8d238-115">Os operadores podem ser notificados por email, pager ou através do comando **net send** :</span><span class="sxs-lookup"><span data-stu-id="8d238-115">Operators can be notified by e-mail, pager, or through the **net send** command:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8d238-116">As opções Pager e **net send** serão removidas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em uma versão futura do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d238-116">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8d238-117">Evite usar esses recursos em novo trabalho de desenvolvimento e planeje modificar os aplicativos que os usam atualmente.</span><span class="sxs-lookup"><span data-stu-id="8d238-117">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="8d238-118">**Notificação por email**</span><span class="sxs-lookup"><span data-stu-id="8d238-118">**E-mail notification**</span></span>  
  
     <span data-ttu-id="8d238-119">A notificação por email envia uma mensagem de email ao operador.</span><span class="sxs-lookup"><span data-stu-id="8d238-119">E-mail notification sends an e-mail message to the operator.</span></span> <span data-ttu-id="8d238-120">Para notificação por email, é necessário fornecer o endereço de email do operador.</span><span class="sxs-lookup"><span data-stu-id="8d238-120">For e-mail notification, you provide the e-mail address for the operator.</span></span>  
  
-   <span data-ttu-id="8d238-121">**Notificação por pager**</span><span class="sxs-lookup"><span data-stu-id="8d238-121">**Pager notification**</span></span>  
  
     <span data-ttu-id="8d238-122">O envio de notificação por pager é implementado por email.</span><span class="sxs-lookup"><span data-stu-id="8d238-122">Paging is implemented by e-mail.</span></span> <span data-ttu-id="8d238-123">Para notificação por pager, é necessário fornecer o endereço de email em que o operador recebe mensagens de pager.</span><span class="sxs-lookup"><span data-stu-id="8d238-123">For pager notification, you provide the e-mail address where the operator receives pager messages.</span></span> <span data-ttu-id="8d238-124">Para configurar notificação por pager, você deve instalar o software no servidor de email que processa a entrada de mensagens e convertê-las em mensagens de pager.</span><span class="sxs-lookup"><span data-stu-id="8d238-124">To set up pager notification, you must install software on the mail server that processes inbound mail and converts it to a pager message.</span></span> <span data-ttu-id="8d238-125">O software pode aplicar várias abordagens, dentre as quais:</span><span class="sxs-lookup"><span data-stu-id="8d238-125">The software can take one of several approaches, including:</span></span>  
  
    -   <span data-ttu-id="8d238-126">Encaminhar o email para um servidor de email remoto no site do provedor de pager.</span><span class="sxs-lookup"><span data-stu-id="8d238-126">Forwarding the mail to a remote mail server at the site of the pager provider.</span></span>  
  
         <span data-ttu-id="8d238-127">O provedor de pager deve oferecer esse serviço, embora o software necessário geralmente esteja disponível como parte do sistema de email local.</span><span class="sxs-lookup"><span data-stu-id="8d238-127">The pager provider must offer this service, although the software required is generally available as part of the local mail system.</span></span> <span data-ttu-id="8d238-128">Para obter mais informações, consulte a documentação de seu pager.</span><span class="sxs-lookup"><span data-stu-id="8d238-128">For more information, see your pager documentation.</span></span>  
  
    -   <span data-ttu-id="8d238-129">Rotear o e-mail pela Internet para um servidor de e-mail no site do provedor de pager.</span><span class="sxs-lookup"><span data-stu-id="8d238-129">Routing the e-mail by way of the Internet to an e-mail server at the pager provider's site.</span></span>  
  
         <span data-ttu-id="8d238-130">Esta é uma variação da primeira abordagem.</span><span class="sxs-lookup"><span data-stu-id="8d238-130">This is a variation on the first approach.</span></span>  
  
    -   <span data-ttu-id="8d238-131">Processar o email de entrada e discar para o pager, por meio de um modem anexado.</span><span class="sxs-lookup"><span data-stu-id="8d238-131">Processing the inbound e-mail and dialing the pager by using an attached modem.</span></span>  
  
         <span data-ttu-id="8d238-132">Esse software é de propriedade dos provedores de serviços de pager.</span><span class="sxs-lookup"><span data-stu-id="8d238-132">This software is proprietary to pager service providers.</span></span> <span data-ttu-id="8d238-133">O software atua como um cliente de email que, periodicamente, processa sua caixa de entrada, interpretando todas ou parte das informações de endereço de email como número de pager ou correspondendo o nome do email a um número de pager em uma tabela de conversão.</span><span class="sxs-lookup"><span data-stu-id="8d238-133">The software acts as a e-mail client that periodically processes its inbox either by interpreting all or part of the e-mail address information as a pager number, or by matching the e-mail name to a pager number in a translation table.</span></span>  
  
         <span data-ttu-id="8d238-134">Se todos os operadores compartilharem um provedor de pager, você poderá usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para especificar qualquer formatação de email especial necessária ao sistema de pager-para-email.</span><span class="sxs-lookup"><span data-stu-id="8d238-134">If all of the operators share a pager provider, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to specify any special e-mail formatting that is required by the pager-to-e-mail system.</span></span> <span data-ttu-id="8d238-135">A formatação especial pode ser um prefixo ou um sufixo e estar contida nas seguintes linhas do email:</span><span class="sxs-lookup"><span data-stu-id="8d238-135">The special formatting can be a prefix or a suffix and can be included in the following lines of the e-mail:</span></span>  
  
         <span data-ttu-id="8d238-136">**Entidade:**</span><span class="sxs-lookup"><span data-stu-id="8d238-136">**Subject:**</span></span>  
  
         <span data-ttu-id="8d238-137">**Cc**:</span><span class="sxs-lookup"><span data-stu-id="8d238-137">**Cc**:</span></span>  
  
         <span data-ttu-id="8d238-138">**Para**:</span><span class="sxs-lookup"><span data-stu-id="8d238-138">**To**:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d238-139">Se usar um sistema de pager alfanumérico, você poderá abreviar o texto enviado, excluindo o texto de erro da notificação por pager.</span><span class="sxs-lookup"><span data-stu-id="8d238-139">If you use a low-capacity alphanumeric paging system, you can shorten the text that is sent by excluding the error text from the pager notification.</span></span> <span data-ttu-id="8d238-140">Um exemplo de sistema de pager alfanumérico de baixa-capacidade é aquele limitado a 64 caracteres por página.</span><span class="sxs-lookup"><span data-stu-id="8d238-140">An example of a low-capacity alphanumeric paging system is one that is limited to 64 characters per page.</span></span>  
  
-   <span data-ttu-id="8d238-141">**notificação net send**</span><span class="sxs-lookup"><span data-stu-id="8d238-141">**net sendnotification**</span></span>  
  
     <span data-ttu-id="8d238-142">Envia uma mensagem ao operador por meio do comando **net send** .</span><span class="sxs-lookup"><span data-stu-id="8d238-142">This sends a message to the operator by means of the **net send** command.</span></span> <span data-ttu-id="8d238-143">Para **net send**, especifique o destinatário (computador ou usuário) de uma mensagem da rede.</span><span class="sxs-lookup"><span data-stu-id="8d238-143">For **net send**, specify the recipient (computer or user) of a network message.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d238-144">O comando **net send** usa o Microsoft Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="8d238-144">The **net send** command uses Microsoft Windows Messenger.</span></span> <span data-ttu-id="8d238-145">Para enviar alertas com êxito, esse serviço deve estar em execução em ambos os computadores, no computador em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está sendo executado e no computador utilizado pelo operador.</span><span class="sxs-lookup"><span data-stu-id="8d238-145">To successfully send alerts, this service must be running on both the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running and the computer that the operator uses.</span></span>  
  
## <a name="alerting-and-fail-safe-operators"></a><span data-ttu-id="8d238-146">Alertas e operadores à prova de falhas</span><span class="sxs-lookup"><span data-stu-id="8d238-146">Alerting and Fail-Safe Operators</span></span>  
 <span data-ttu-id="8d238-147">Você pode escolher quais operadores serão notificados em resposta a um alerta.</span><span class="sxs-lookup"><span data-stu-id="8d238-147">You can choose which operators are to be notified in response to an alert.</span></span> <span data-ttu-id="8d238-148">Por exemplo, você pode atribuir responsabilidades rotativas para a notificação de operadores agendando alertas.</span><span class="sxs-lookup"><span data-stu-id="8d238-148">For example, you can assign rotating responsibilities for operator notification by scheduling alerts.</span></span> <span data-ttu-id="8d238-149">Por exemplo, o Indivíduo A é notificado sobre alertas que ocorrem às segundas, quartas ou sextas e o Indivíduo B, sobre alertas ocorridos às terças, quintas ou sábados.</span><span class="sxs-lookup"><span data-stu-id="8d238-149">For example, Individual A is notified of alerts that occur on Monday, Wednesday, or Friday, and Individual B is notified of alerts that occur on Tuesday, Thursday, or Saturday.</span></span>  
  
 <span data-ttu-id="8d238-150">O operador à prova de falhas recebe uma notificação de alerta quando todas as notificações por pager aos operadores designados falham.</span><span class="sxs-lookup"><span data-stu-id="8d238-150">The fail-safe operator receives an alert notification after all pager notifications to the designated operators have failed.</span></span> <span data-ttu-id="8d238-151">Por exemplo, se você tiver definido três operadores para notificações por pager e nenhum deles puder ser alcançado via pager, o operador à prova de falhas será notificado.</span><span class="sxs-lookup"><span data-stu-id="8d238-151">For example, if you have defined three operators for pager notifications and none of the designated operators can be paged, the fail-safe operator is notified.</span></span>  
  
 <span data-ttu-id="8d238-152">O operador à prova de falhas é notificado quando:</span><span class="sxs-lookup"><span data-stu-id="8d238-152">The fail-safe operator is notified when:</span></span>  
  
-   <span data-ttu-id="8d238-153">Os operadores responsáveis pelo alerta não puderem ser informados por pager.</span><span class="sxs-lookup"><span data-stu-id="8d238-153">The operators responsible for the alert could not be paged.</span></span>  
  
     <span data-ttu-id="8d238-154">São motivos de falha em alcançar operadores primários endereços de pager incorretos e operadores fora de serviço.</span><span class="sxs-lookup"><span data-stu-id="8d238-154">Reasons for failure to reach primary operators include incorrect pager addresses and off-duty operators.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8d238-155">O Agent não consegue acessar as tabelas do sistema no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="8d238-155">Agent cannot access system tables in the **msdb** database.</span></span>  
  
     <span data-ttu-id="8d238-156">A tabela do sistema **sysnotifications** especifica as responsabilidades de operador para os alertas.</span><span class="sxs-lookup"><span data-stu-id="8d238-156">The **sysnotifications** system table specifies operator responsibilities for alerts.</span></span>  
  
 <span data-ttu-id="8d238-157">O operador à prova de falhas é um recurso de segurança.</span><span class="sxs-lookup"><span data-stu-id="8d238-157">The fail-safe operator is a security feature.</span></span> <span data-ttu-id="8d238-158">Não é possível excluir o operador atribuído à responsabilidade de proteção contra falhas sem reatribuí-la a outro operador ou excluir a atribuição junto com operador.</span><span class="sxs-lookup"><span data-stu-id="8d238-158">You cannot delete the operator assigned to fail-safe duty without reassigning fail-safe duty to another operator, or deleting the fail-safe assignment altogether.</span></span>  
  
## <a name="notifying-an-operator"></a><span data-ttu-id="8d238-159">Notificando um operador</span><span class="sxs-lookup"><span data-stu-id="8d238-159">Notifying an Operator</span></span>  
 <span data-ttu-id="8d238-160">É necessário configurar um ou mais destes itens para notificar um operador:</span><span class="sxs-lookup"><span data-stu-id="8d238-160">You must set up one or more of the following in order to notify an operator:</span></span>  
  
-   <span data-ttu-id="8d238-161">Para enviar email com a funcionalidade Database Mail, é necessário ter acesso a um servidor de email que ofereça suporte a SMTP.</span><span class="sxs-lookup"><span data-stu-id="8d238-161">To send e-mail with Database Mail functionality, you must have access to an e-mail server that supports SMTP.</span></span>  
  
-   <span data-ttu-id="8d238-162">Para paginação, é necessário ter software e/ou hardware de pager-para-email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="8d238-162">For paging, you must have third-party pager-to-e-mail software and/or hardware.</span></span>  
  
-   <span data-ttu-id="8d238-163">Para usar **net send**, o operador deve ter feito logon no computador especificado e este deve permitir mensagens do Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="8d238-163">To use **net send**, the operator must be logged on to the specified computer, and the specified computer must allow messages from Windows Messenger.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8d238-164">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8d238-164">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d238-165">**Tarefas**</span><span class="sxs-lookup"><span data-stu-id="8d238-165">**Tasks**</span></span>|<span data-ttu-id="8d238-166">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="8d238-166">**Topic**</span></span>|  
|<span data-ttu-id="8d238-167">Tarefas relacionadas à criação de um operador</span><span class="sxs-lookup"><span data-stu-id="8d238-167">Tasks related to creating an operator</span></span>|[<span data-ttu-id="8d238-168">Criar um operador</span><span class="sxs-lookup"><span data-stu-id="8d238-168">Create an Operator</span></span>](create-an-operator.md)<br /><br /> [<span data-ttu-id="8d238-169">Designate a Fail-Safe Operator</span><span class="sxs-lookup"><span data-stu-id="8d238-169">Designate a Fail-Safe Operator</span></span>](designate-a-fail-safe-operator.md)|  
|<span data-ttu-id="8d238-170">Tarefas relacionadas à atribuição de alertas</span><span class="sxs-lookup"><span data-stu-id="8d238-170">Tasks related to assigning alerts</span></span>|[<span data-ttu-id="8d238-171">Atribuir alertas a um operador</span><span class="sxs-lookup"><span data-stu-id="8d238-171">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)<br /><br /> [<span data-ttu-id="8d238-172">Definir a resposta a um alerta &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8d238-172">Define the Response to an Alert &#40;SQL Server Management Studio&#41;</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)<br /><br /> [<span data-ttu-id="8d238-173">&#41;&#40;Transact-SQL de sp_add_notification</span><span class="sxs-lookup"><span data-stu-id="8d238-173">sp_add_notification &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)<br /><br /> [<span data-ttu-id="8d238-174">Atribuir alertas a um operador</span><span class="sxs-lookup"><span data-stu-id="8d238-174">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="8d238-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d238-175">See Also</span></span>  
 [<span data-ttu-id="8d238-176">Database Mail</span><span class="sxs-lookup"><span data-stu-id="8d238-176">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
