---
title: Configurar o Database Mail | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- Sql12.swb.sqlimail.newaccount.f1
- Sql12.swb.sqlimail.manageexistingaccount.f1
- Sql12.swb.dbmail.manageexistingaccount.f1
- Sql12.swb.sqlimail.manageexistingprofile.f1
- Sql12.swb.sqlimail.newprofile.f1
- Sql12.swb.sqlimail.profileandaccountmanagement.f1
- Sql12.swb.dbmail.configuresystem.f1
- Sql12.swb.dbmail.profileandaccountmanagement.f1
- Sql12.swb.dbmail. manageprofilesecurity.profileview.f1
- Sql12.swb.dbmail.selectconfiguration.f1
- Sql12.swb.dbmail.newsqlimailaccount.f1
- Sql12.swb.sqlimail.manageprofilesecurity.profileview.f1
- Sql12.swb.sqlimail.newsqlimailaccount.f1
- Sql12.swb.dbmail.newaccount.f1
- Sql12.swb.dbmail.manageexistingprofile.f1
- Sql12.swb.sqlimail.configuresystem.f1
- Sql12.swb.sqlimail.selectconfiguration.f1
- Sql12.swb.dbmail.completewizard.f1
- Sql12.swb.sqlimail.welcome.f1
- sql12.swb.dbmail.sendtestemail.f1
- Sql12.swb.sqlimail.addaccounttoprofile.f1
- Sql12.swb.dbmail.welcome.f1
- Sql12.swb.dbmail.newprofile.f1
- Sql12.swb.dbmail.addaccounttoprofile.f1
- sql12.swb.dbmail.sendtestemail.test.f1
- Sql12.swb.sqlimail.completewizard.f1
- Sql12.swb.sqlimail.manageprofilesecurity.principalview.f1
- Sql12.swb.dbmail.manageprofilesecurity.principalview.f1
ms.assetid: 7edc21d4-ccf3-42a9-84c0-3f70333efce6
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbf9af4b5af3043c6ca8fa2cba01ebe43019fb41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583617"
---
# <a name="configure-database-mail"></a><span data-ttu-id="59475-102">Configurar o Database Mail</span><span class="sxs-lookup"><span data-stu-id="59475-102">Configure Database Mail</span></span>
  <span data-ttu-id="59475-103">Este tópico descreve como habilitar e configurar o Database Mail usando o Assistente para Configuração do Database Mail e cria um script de Configuração do Database Mail usando modelos.</span><span class="sxs-lookup"><span data-stu-id="59475-103">This topic describes how to enable and configure Database Mail using the Database Mail Configuration Wizard, and create a Database Mail Configuration script using templates.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="59475-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="59475-104">Before You Begin</span></span>  
 <span data-ttu-id="59475-105">Use a opção **DatabaseMail XPs** para habilitar o Database Mail neste servidor.</span><span class="sxs-lookup"><span data-stu-id="59475-105">Use the **DatabaseMail XPs** option to enable Database Mail on this server.</span></span> <span data-ttu-id="59475-106">Para obter mais informações, confira o tópico de referência [Opção Database Mail XPs de configuração de servidor](../../database-engine/configure-windows/database-mail-xps-server-configuration-option.md) .</span><span class="sxs-lookup"><span data-stu-id="59475-106">For more information, see [Database Mail XPs Server Configuration Option](../../database-engine/configure-windows/database-mail-xps-server-configuration-option.md) reference topic.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="59475-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="59475-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="59475-108">A habilitação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Service Broker em qualquer banco de dados exige um bloqueio de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="59475-108">Enabling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Service Broker in any database requires a database lock.</span></span> <span data-ttu-id="59475-109">Se o Service Broker tiver sido desabilitado no **msdb**, para habilitar o Database Mail primeiro interrompa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para que o Service Broker possa obter o bloqueio necessário.</span><span class="sxs-lookup"><span data-stu-id="59475-109">If Service Broker was deactivated in **msdb**, to enable Database Mail, first stop [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent so Service Broker can obtain the necessary lock.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="59475-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="59475-110">Security</span></span>  
 <span data-ttu-id="59475-111">Para configurar o Database Mail, é necessário ser membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="59475-111">To configure Database Mail you must be a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="59475-112">Para enviar Database Mail, é necessário ser membro da função de banco de dados **DatabaseMailUserRole** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="59475-112">To send Database Mail you must be a member of the **DatabaseMailUserRole** database role in the **msdb** database.</span></span>  
  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="59475-113">Usando o assistente para configuração do Database Mail</span><span class="sxs-lookup"><span data-stu-id="59475-113">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="59475-114">**Para configurar o Database Mail usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="59475-114">**To configure Database Mail using a wizard**</span></span>  
  
1.  <span data-ttu-id="59475-115">No Pesquisador de Objetos, expanda o nó da instância desejada para configurar o Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-115">In Object Explorer, expand the node for the instance  you want to configure Database mail.</span></span>  
  
2.  <span data-ttu-id="59475-116">Expanda o nó **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="59475-116">Expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="59475-117">Clique com o botão direito do mouse em **Database Mail**e clique em **Configurar o Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="59475-117">Right-click **Database Mail**, and then click **Configure Database Mail**.</span></span>  
  
4.  <span data-ttu-id="59475-118">Conclua os diálogos do Assistente:</span><span class="sxs-lookup"><span data-stu-id="59475-118">Complete the Wizard dialogs</span></span>  
  

  
  
  
###  <a name="welcome-page"></a><a name="Welcome"></a><span data-ttu-id="59475-119">Página inicial</span><span class="sxs-lookup"><span data-stu-id="59475-119">Welcome Page</span></span>  
 <span data-ttu-id="59475-120">Esta página descreve as etapas de configuração do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-120">This page describes the steps to configuring Database Mail.</span></span>  
  
 <span data-ttu-id="59475-121">**Não mostrar esta página novamente** -Marque esta página para ignorar a exibição deste botão de boas-vindas no futuro.</span><span class="sxs-lookup"><span data-stu-id="59475-121">**Do not show this page again** - Check this to skip this welcome page from displaying in the future.</span></span>  
  
 <span data-ttu-id="59475-122">**Avançar** – Segue para a página **Selecionar uma tarefa de configuração** .</span><span class="sxs-lookup"><span data-stu-id="59475-122">**Next** - Proceeds to the **Select a configuration task** page.</span></span>  
  
 <span data-ttu-id="59475-123">**Cancelar** – encerra o assistente sem configurar Database Mail</span><span class="sxs-lookup"><span data-stu-id="59475-123">**Cancel** - Terminates the wizard without configuring Database Mail</span></span>  
  
 
  
###  <a name="select-configuration-task"></a><a name="ConfigTask"></a><span data-ttu-id="59475-124">Selecionar tarefa de configuração</span><span class="sxs-lookup"><span data-stu-id="59475-124">Select Configuration Task</span></span>  
 <span data-ttu-id="59475-125">Use a página **Selecionar Tarefa de Configuração** para indicar qual tarefa você concluirá sempre que usar o assistente.</span><span class="sxs-lookup"><span data-stu-id="59475-125">Use the **Select Configuration Task** page, to indicate which task you will complete each time you use the wizard.</span></span> <span data-ttu-id="59475-126">Se você mudar de ideia antes de concluir o assistente, use o botão **Voltar** para voltar para essa página e selecionar outra tarefa.</span><span class="sxs-lookup"><span data-stu-id="59475-126">If you change your mind before you complete the wizard, use the **Back** button to return to this page and select a different task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59475-127">Se o Database Mail não foi habilitado, você receberá a mensagem: **O recurso Database Mail não está disponível.  Deseja habilitar este recurso?**</span><span class="sxs-lookup"><span data-stu-id="59475-127">If Database Mail has not been enabled, you will receive the message: **The Database Mail feature is not available.  Would you like to enable this feature?**</span></span> <span data-ttu-id="59475-128">Responder **Sim**equivale a habilitar o Database Mail usando a [opção Database Mail XPs](../../database-engine/configure-windows/database-mail-xps-server-configuration-option.md) do procedimento armazenado do sistema **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="59475-128">Responding **Yes**, is equivalent to enabling Database Mail by using the [Database Mail XPs option](../../database-engine/configure-windows/database-mail-xps-server-configuration-option.md) of the **sp_configure** system stored procedure.</span></span>  
  
 <span data-ttu-id="59475-129">**Instalar Database Mail executando as seguintes tarefas**</span><span class="sxs-lookup"><span data-stu-id="59475-129">**Set up Database Mail by performing the following tasks**</span></span>  
 <span data-ttu-id="59475-130">Execute todas as tarefas exigidas para instalar o Database Mail pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="59475-130">Perform all of the tasks required to set up Database Mail for the first time.</span></span> <span data-ttu-id="59475-131">Essa opção inclui todas as outras três opções.</span><span class="sxs-lookup"><span data-stu-id="59475-131">This option includes all of the other three options.</span></span>  
  
 <span data-ttu-id="59475-132">**Gerenciar contas e perfis do Database Mail**</span><span class="sxs-lookup"><span data-stu-id="59475-132">**Manage Database Mail accounts and profiles**</span></span>  
 <span data-ttu-id="59475-133">Crie novas contas e perfis do Database Mail ou exiba, altere ou exclua contas e perfis existentes do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-133">Create new Database Mail accounts and profiles or to view, change, or delete existing Database Mail accounts and profiles.</span></span>  
  
 <span data-ttu-id="59475-134">**Gerenciar segurança do perfil**</span><span class="sxs-lookup"><span data-stu-id="59475-134">**Manage profile security**</span></span>  
 <span data-ttu-id="59475-135">Configure quais usuários têm acesso a perfis do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-135">Configure which users have access to Database Mail profiles.</span></span>  
  
 <span data-ttu-id="59475-136">**Exibir ou alterar parâmetros do sistema**</span><span class="sxs-lookup"><span data-stu-id="59475-136">**View or change system parameters**</span></span>  
 <span data-ttu-id="59475-137">Configure parâmetros de sistema do Database Mail, como o tamanho máximo de arquivo para anexos.</span><span class="sxs-lookup"><span data-stu-id="59475-137">Configure Database Mail system parameters such as the maximum file size for attachments.</span></span>  
  

  
###  <a name="new-account-page"></a><a name="NewAccount"></a><span data-ttu-id="59475-138">Página nova conta</span><span class="sxs-lookup"><span data-stu-id="59475-138">New Account Page</span></span>  
 <span data-ttu-id="59475-139">Use esta página para criar uma nova conta do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-139">Use this page to create a new Database Mail account.</span></span> <span data-ttu-id="59475-140">Uma conta do Database Mail contém informações para enviar email a um servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-140">A Database Mail account contains information for sending e-mail to an SMTP server.</span></span>  
  
 <span data-ttu-id="59475-141">Uma conta do Database Mail contém as informações que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa para enviar mensagens de email a um servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-141">A Database Mail account contains the information that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses to send e-mail messages to an SMTP server.</span></span> <span data-ttu-id="59475-142">Cada conta contém informações de um servidor de email.</span><span class="sxs-lookup"><span data-stu-id="59475-142">Each account contains information for one e-mail server.</span></span>  
  
 <span data-ttu-id="59475-143">Uma conta do Database Mail só é usada no Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-143">A Database Mail account is only used for Database Mail.</span></span> <span data-ttu-id="59475-144">Uma conta do Database Mail não corresponde a uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou uma conta do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="59475-144">A Database Mail account does not correspond to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account or a Microsoft Windows account.</span></span> <span data-ttu-id="59475-145">O Database Mail pode ser enviado usando as credenciais do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]usando outras credenciais que você forneça ou anonimamente.</span><span class="sxs-lookup"><span data-stu-id="59475-145">Database Mail can be sent using the credentials of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], using other credentials that you supply, or anonymously.</span></span> <span data-ttu-id="59475-146">Quando a autenticação básica é usada, o nome do usuário e a senha em uma conta do Database Mail só são usados para autenticação no servidor de email.</span><span class="sxs-lookup"><span data-stu-id="59475-146">When using basic authentication, the user name and password in a Database Mail account are only used for authentication with the e-mail server.</span></span> <span data-ttu-id="59475-147">Uma conta não precisa corresponder a um usuário no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou a um usuário no computador que executa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59475-147">An account need not correspond to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user or a user on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="59475-148">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="59475-148">**Account name**</span></span>  
 <span data-ttu-id="59475-149">Digite o nome da nova conta.</span><span class="sxs-lookup"><span data-stu-id="59475-149">Type the name of the new account.</span></span>  
  
 <span data-ttu-id="59475-150">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="59475-150">**Description**</span></span>  
 <span data-ttu-id="59475-151">Digite uma descrição da conta.</span><span class="sxs-lookup"><span data-stu-id="59475-151">Type a description of the account.</span></span> <span data-ttu-id="59475-152">A descrição é opcional.</span><span class="sxs-lookup"><span data-stu-id="59475-152">The description is optional.</span></span>  
  
 <span data-ttu-id="59475-153">**Endereço de email**</span><span class="sxs-lookup"><span data-stu-id="59475-153">**E-mail address**</span></span>  
 <span data-ttu-id="59475-154">Digite o nome do endereço de email da conta.</span><span class="sxs-lookup"><span data-stu-id="59475-154">Type the name of the e-mail address for the account.</span></span> <span data-ttu-id="59475-155">Este é o endereço de email da conta que o enviou.</span><span class="sxs-lookup"><span data-stu-id="59475-155">This is the e-mail address that e-mail is sent from.</span></span> <span data-ttu-id="59475-156">Por exemplo, uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pode enviar emails do endereço SqlAgent@Adventure-Works.com.</span><span class="sxs-lookup"><span data-stu-id="59475-156">For example, an account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent may send e-mail from the address SqlAgent@Adventure-Works.com.</span></span>  
  
 <span data-ttu-id="59475-157">**Nome de exibição**</span><span class="sxs-lookup"><span data-stu-id="59475-157">**Display name**</span></span>  
 <span data-ttu-id="59475-158">Digite o nome que será exibido nas mensagens de email enviadas por essa conta.</span><span class="sxs-lookup"><span data-stu-id="59475-158">Type the name to show on e-mail messages sent from this account.</span></span> <span data-ttu-id="59475-159">O nome para exibição é opcional.</span><span class="sxs-lookup"><span data-stu-id="59475-159">The display name is optional.</span></span> <span data-ttu-id="59475-160">Este é o nome exibido em mensagens enviadas desta conta.</span><span class="sxs-lookup"><span data-stu-id="59475-160">This is the name displayed on messages sent from this account.</span></span> <span data-ttu-id="59475-161">Por exemplo, uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pode exibir o nome “SQL Server Agent Automated Mailer” em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="59475-161">For example, an account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent may display the name "SQL Server Agent Automated Mailer" on e-mail messages.</span></span>  
  
 <span data-ttu-id="59475-162">**Email de resposta**</span><span class="sxs-lookup"><span data-stu-id="59475-162">**Reply e-mail**</span></span>  
 <span data-ttu-id="59475-163">Digite o endereço de email que será usado em respostas a mensagens de email enviadas por esta conta.</span><span class="sxs-lookup"><span data-stu-id="59475-163">Type the e-mail address that will be used for replies to e-mail messages sent from this account.</span></span> <span data-ttu-id="59475-164">O email de resposta é opcional.</span><span class="sxs-lookup"><span data-stu-id="59475-164">The reply e-mail is optional.</span></span> <span data-ttu-id="59475-165">Por exemplo, respostas a uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent podem ir para o administrador de banco de dados, danw@Adventure-Works.com.</span><span class="sxs-lookup"><span data-stu-id="59475-165">For example, replies to an account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent may go to the database administrator, danw@Adventure-Works.com.</span></span>  
  
 <span data-ttu-id="59475-166">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="59475-166">**Server name**</span></span>  
 <span data-ttu-id="59475-167">Digite o nome ou o endereço IP do servidor SMTP que a conta usa para enviar email.</span><span class="sxs-lookup"><span data-stu-id="59475-167">Type the name or IP address of the SMTP server the account uses to send e-mail.</span></span> <span data-ttu-id="59475-168">Normalmente, isso está em um formato semelhante a `smtp.` *<your_company>* `.com` .</span><span class="sxs-lookup"><span data-stu-id="59475-168">Typically this is in a format similar to `smtp.`*<your_company>*`.com`.</span></span> <span data-ttu-id="59475-169">Para obter mais ajuda sobre isso, consulte o administrador de mail.</span><span class="sxs-lookup"><span data-stu-id="59475-169">For help with this, consult your mail administrator.</span></span>  
  
 <span data-ttu-id="59475-170">**Número da porta**</span><span class="sxs-lookup"><span data-stu-id="59475-170">**Port number**</span></span>  
 <span data-ttu-id="59475-171">Digite o número da porta do servidor SMTP para a conta.</span><span class="sxs-lookup"><span data-stu-id="59475-171">Type the port number of the SMTP server for this account.</span></span> <span data-ttu-id="59475-172">A maioria dos servidores SMTP usa a porta 25.</span><span class="sxs-lookup"><span data-stu-id="59475-172">Most SMTP servers use port 25.</span></span>  
  
 <span data-ttu-id="59475-173">**Esse servidor requer uma conexão segura (SSL)**</span><span class="sxs-lookup"><span data-stu-id="59475-173">**This server requires a secure connection (SSL)**</span></span>  
 <span data-ttu-id="59475-174">Criptografa a comunicação usando o Protocolo SSL.</span><span class="sxs-lookup"><span data-stu-id="59475-174">Encrypts communication using Secure Sockets Layer.</span></span>  
  
 <span data-ttu-id="59475-175">**Autenticação do Windows usando as credenciais do serviço Mecanismo de Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="59475-175">**Windows Authentication using Database Engine service credentials**</span></span>  
 <span data-ttu-id="59475-176">A conexão é feita com o servidor SMTP usando as credenciais configuradas para o serviço do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59475-176">Connection is made to the SMTP server using the credentials configured for the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="59475-177">**Autenticação básica**</span><span class="sxs-lookup"><span data-stu-id="59475-177">**Basic Authentication**</span></span>  
 <span data-ttu-id="59475-178">Especifique o nome do usuário e a senha exibidos pelo servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-178">Specify the user name and password required by the SMTP server.</span></span>  
  
 <span data-ttu-id="59475-179">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="59475-179">**User name**</span></span>  
 <span data-ttu-id="59475-180">Digite o nome de usuário que o Database Mail usa para fazer logon no servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-180">Type the user name that Database Mail uses to log in to the SMTP server.</span></span> <span data-ttu-id="59475-181">O nome do usuário será necessário se o servidor SMTP exigir autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="59475-181">The user name is required if the SMTP server requires basic authentication.</span></span>  
  
 <span data-ttu-id="59475-182">**Senha**</span><span class="sxs-lookup"><span data-stu-id="59475-182">**Password**</span></span>  
 <span data-ttu-id="59475-183">Digite a senha que o Database Mail usa para fazer logon no servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-183">Type the password that Database Mail uses to log in to the SMTP server.</span></span> <span data-ttu-id="59475-184">A senha será necessária se o servidor SMTP exigir autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="59475-184">The password is required if the SMTP server requires basic authentication.</span></span>  
  
 <span data-ttu-id="59475-185">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="59475-185">**Confirm password**</span></span>  
 <span data-ttu-id="59475-186">Digite a senha novamente para confirmar.</span><span class="sxs-lookup"><span data-stu-id="59475-186">Type the password again to confirm the password.</span></span> <span data-ttu-id="59475-187">A senha será necessária se o servidor SMTP exigir autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="59475-187">The password is required if the SMTP server requires basic authentication.</span></span>  
  
 <span data-ttu-id="59475-188">**Autenticação anônima**</span><span class="sxs-lookup"><span data-stu-id="59475-188">**Anonymous authentication**</span></span>  
 <span data-ttu-id="59475-189">O email é enviado ao servidor SMTP sem credenciais de logon.</span><span class="sxs-lookup"><span data-stu-id="59475-189">Mail is sent to the SMTP server without login credentials.</span></span> <span data-ttu-id="59475-190">Use essa opção quando o servidor SMTP não exigir autenticação.</span><span class="sxs-lookup"><span data-stu-id="59475-190">Use this option when the SMTP server does not require authentication.</span></span>  
  
 
  
###  <a name="manage-existing-account-page"></a><a name="ExistingAccount"></a><span data-ttu-id="59475-191">Página Gerenciar conta existente</span><span class="sxs-lookup"><span data-stu-id="59475-191">Manage Existing Account Page</span></span>  
 <span data-ttu-id="59475-192">Use esta página para gerenciar uma conta de Database Mail existente.</span><span class="sxs-lookup"><span data-stu-id="59475-192">Use this page to manage an existing Database Mail account.</span></span>  
  
 <span data-ttu-id="59475-193">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="59475-193">**Account name**</span></span>  
 <span data-ttu-id="59475-194">Selecione a conta a exibir, atualizar ou excluir.</span><span class="sxs-lookup"><span data-stu-id="59475-194">Select the account to view, update or delete.</span></span>  
  
 <span data-ttu-id="59475-195">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="59475-195">**Delete**</span></span>  
 <span data-ttu-id="59475-196">Excluir a conta selecionada.</span><span class="sxs-lookup"><span data-stu-id="59475-196">Delete the selected account.</span></span> <span data-ttu-id="59475-197">Você deve remover esta conta de perfis associados, ou excluir esses perfis, antes de excluir a conta selecionada.</span><span class="sxs-lookup"><span data-stu-id="59475-197">You must remove this account from associated profiles, or delete such profiles, before you delete the selected account.</span></span>  
  
 <span data-ttu-id="59475-198">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="59475-198">**Description**</span></span>  
 <span data-ttu-id="59475-199">Exiba ou atualize a descrição da conta.</span><span class="sxs-lookup"><span data-stu-id="59475-199">View or update the description of the account.</span></span> <span data-ttu-id="59475-200">A descrição é opcional.</span><span class="sxs-lookup"><span data-stu-id="59475-200">The description is optional.</span></span>  
  
 <span data-ttu-id="59475-201">**Endereço de email**</span><span class="sxs-lookup"><span data-stu-id="59475-201">**E-mail address**</span></span>  
 <span data-ttu-id="59475-202">Exiba ou atualize o nome do endereço de email da conta.</span><span class="sxs-lookup"><span data-stu-id="59475-202">View or update the name of the e-mail address for the account.</span></span> <span data-ttu-id="59475-203">Este é o endereço de email da conta que o enviou.</span><span class="sxs-lookup"><span data-stu-id="59475-203">This is the e-mail address that e-mail is sent from.</span></span> <span data-ttu-id="59475-204">Por exemplo, uma conta do agente de Microsoft SQL Server pode enviar email do endereço **SqlAgent@Adventure-Works.com** .</span><span class="sxs-lookup"><span data-stu-id="59475-204">For example, an account for Microsoft SQL Server Agent may send e-mail from the address **SqlAgent@Adventure-Works.com**.</span></span>  
  
 <span data-ttu-id="59475-205">**Nome de exibição**</span><span class="sxs-lookup"><span data-stu-id="59475-205">**Display name**</span></span>  
 <span data-ttu-id="59475-206">Exiba ou atualize o nome a ser exibido em mensagens de email enviadas desta conta.</span><span class="sxs-lookup"><span data-stu-id="59475-206">View or update the name to show on e-mail messages sent from this account.</span></span> <span data-ttu-id="59475-207">O nome para exibição é opcional.</span><span class="sxs-lookup"><span data-stu-id="59475-207">The display name is optional.</span></span> <span data-ttu-id="59475-208">Este é o nome exibido em mensagens enviadas desta conta.</span><span class="sxs-lookup"><span data-stu-id="59475-208">This is the name displayed on messages sent from this account.</span></span> <span data-ttu-id="59475-209">Por exemplo, uma conta do SQL Server Agent pode exibir o nome **SQL Server Agent Automated Mailer** em mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="59475-209">For example, an account for SQL Server Agent may display the name **SQL Server Agent Automated Mailer** on e-mail messages.</span></span>  
  
 <span data-ttu-id="59475-210">**Email de resposta**</span><span class="sxs-lookup"><span data-stu-id="59475-210">**Reply e-mail**</span></span>  
 <span data-ttu-id="59475-211">Exiba ou atualize o endereço de email que será usado em respostas a mensagens de email enviadas desta conta.</span><span class="sxs-lookup"><span data-stu-id="59475-211">View or update the e-mail address that will be used for replies to e-mail messages sent from this account.</span></span> <span data-ttu-id="59475-212">O email de resposta é opcional.</span><span class="sxs-lookup"><span data-stu-id="59475-212">The reply e-mail is optional.</span></span> <span data-ttu-id="59475-213">Por exemplo, as respostas a uma conta do SQL Server Agent podem ir para o administrador do banco de dados, **danw@Adventure-Works.com** .</span><span class="sxs-lookup"><span data-stu-id="59475-213">For example, replies to an account for SQL Server Agent may go to the database administrator, **danw@Adventure-Works.com**.</span></span>  
  
 <span data-ttu-id="59475-214">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="59475-214">**Server name**</span></span>  
 <span data-ttu-id="59475-215">Exibe ou atualiza o nome do servidor SMTP que a conta usa para enviar email.</span><span class="sxs-lookup"><span data-stu-id="59475-215">View or update the name of the SMTP server the account uses to send e-mail.</span></span> <span data-ttu-id="59475-216">Geralmente, está em um formato semelhante a **smtp.<your_company>.com**.</span><span class="sxs-lookup"><span data-stu-id="59475-216">Typically this is in a format similar to **smtp.<your_company>.com**.</span></span> <span data-ttu-id="59475-217">Para obter mais ajuda sobre isso, consulte o administrador de mail.</span><span class="sxs-lookup"><span data-stu-id="59475-217">For help with this, consult your mail administrator.</span></span>  
  
 <span data-ttu-id="59475-218">**Número da porta**</span><span class="sxs-lookup"><span data-stu-id="59475-218">**Port number**</span></span>  
 <span data-ttu-id="59475-219">Exiba ou atualize o número da porta do servidor SMTP desta conta.</span><span class="sxs-lookup"><span data-stu-id="59475-219">View or update the port number of the SMTP server for this account.</span></span> <span data-ttu-id="59475-220">A maioria dos servidores SMTP usa a porta 25.</span><span class="sxs-lookup"><span data-stu-id="59475-220">Most SMTP servers use port 25.</span></span>  
  
 <span data-ttu-id="59475-221">**Esse servidor requer uma conexão segura (SSL)**</span><span class="sxs-lookup"><span data-stu-id="59475-221">**This server requires a secure connection (SSL)**</span></span>  
 <span data-ttu-id="59475-222">Criptografa a comunicação usando o Protocolo SSL.</span><span class="sxs-lookup"><span data-stu-id="59475-222">Encrypts communication using Secure Sockets Layer.</span></span>  
  
 <span data-ttu-id="59475-223">**Autenticação do Windows usando as credenciais do serviço Mecanismo de Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="59475-223">**Windows Authentication using Database Engine service credentials**</span></span>  
 <span data-ttu-id="59475-224">A conexão é feita com o servidor SMTP usando as credenciais configuradas para o serviço do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59475-224">Connection is made to the SMTP server using the credentials configured for the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="59475-225">**Autenticação básica**</span><span class="sxs-lookup"><span data-stu-id="59475-225">**Basic Authentication**</span></span>  
 <span data-ttu-id="59475-226">Especifique o nome do usuário e a senha exibidos pelo servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-226">Specify the user name and password required by the SMTP server.</span></span>  
  
 <span data-ttu-id="59475-227">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="59475-227">**User name**</span></span>  
 <span data-ttu-id="59475-228">Exiba ou atualize o nome do usuário que o Database Mail usa para fazer logon no servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-228">View or update the user name that Database Mail uses to log in to the SMTP server.</span></span> <span data-ttu-id="59475-229">O nome do usuário será necessário se o servidor SMTP exigir autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="59475-229">The user name is required if the SMTP server requires basic authentication.</span></span>  
  
 <span data-ttu-id="59475-230">**Senha**</span><span class="sxs-lookup"><span data-stu-id="59475-230">**Password**</span></span>  
 <span data-ttu-id="59475-231">Altere a senha que o Database Mail usa para fazer logon no servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-231">Change the password that Database Mail uses to log in to the SMTP server.</span></span> <span data-ttu-id="59475-232">A senha será necessária se o servidor SMTP exigir autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="59475-232">The password is required if the SMTP server requires basic authentication.</span></span>  
  
 <span data-ttu-id="59475-233">**Confirmar senha**</span><span class="sxs-lookup"><span data-stu-id="59475-233">**Confirm password**</span></span>  
 <span data-ttu-id="59475-234">Digite a senha novamente para confirmar.</span><span class="sxs-lookup"><span data-stu-id="59475-234">Type the password again to confirm the password.</span></span> <span data-ttu-id="59475-235">A senha será necessária se o servidor SMTP exigir autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="59475-235">The password is required if the SMTP server requires basic authentication.</span></span>  
  
 <span data-ttu-id="59475-236">**Autenticação anônima**</span><span class="sxs-lookup"><span data-stu-id="59475-236">**Anonymous authentication**</span></span>  
 <span data-ttu-id="59475-237">O email é enviado ao servidor SMTP sem credenciais de logon.</span><span class="sxs-lookup"><span data-stu-id="59475-237">Mail is sent to the SMTP server without login credentials.</span></span> <span data-ttu-id="59475-238">Use essa opção quando o servidor SMTP não exigir autenticação.</span><span class="sxs-lookup"><span data-stu-id="59475-238">Use this option when the SMTP server does not require authentication.</span></span>  
  

  
###  <a name="new-profile-page"></a><a name="NewProfile"></a> <span data-ttu-id="59475-239">Página Novo Perfil</span><span class="sxs-lookup"><span data-stu-id="59475-239">New Profile Page</span></span>  
 <span data-ttu-id="59475-240">Use essa página para criar um perfil do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-240">Use this page to create a Database Mail profile.</span></span> <span data-ttu-id="59475-241">Um perfil do Database Mail é uma coleção de contas do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-241">A Database Mail profile is a collection of Database Mail accounts.</span></span> <span data-ttu-id="59475-242">Os perfis melhoram a confiabilidade nos casos em que um servidor de email não pode ser acessado, oferecendo contas alternativas do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-242">Profiles improve reliability in cases where an e-mail server becomes unreachable, by providing alternative Database Mail accounts.</span></span> <span data-ttu-id="59475-243">É necessário pelo menos uma conta do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-243">At least one Database Mail account is required.</span></span> <span data-ttu-id="59475-244">Para obter mais informações sobre como definir a prioridade das contas do Database Mail no perfil, veja [Criar um perfil do Database Mail](create-a-database-mail-profile.md).</span><span class="sxs-lookup"><span data-stu-id="59475-244">For more information about setting the priority of Database Mail accounts in the profile, see [Create a Database Mail Profile](create-a-database-mail-profile.md).</span></span>  
  
 <span data-ttu-id="59475-245">Use os botões **Mover para Cima** e **Mover para Baixo** para alterar a ordem na qual as contas do Database Mail são usadas.</span><span class="sxs-lookup"><span data-stu-id="59475-245">Use the **Move Up** and **Move Down** buttons to change the order in which Database Mail accounts are used.</span></span> <span data-ttu-id="59475-246">Essa ordem é determinada por um valor chamado número de sequência.</span><span class="sxs-lookup"><span data-stu-id="59475-246">This order is determined by a value called the sequence number.</span></span> <span data-ttu-id="59475-247">**Mover para Cima** diminui o número de sequência e **Mover para Baixo** aumenta o número de sequência.</span><span class="sxs-lookup"><span data-stu-id="59475-247">**Move Up** lowers the sequence number and **Move Down** increases the sequence number.</span></span> <span data-ttu-id="59475-248">O número de sequência determina a ordem na qual o Database Mail usa as contas no perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-248">The sequence number determines the order in which Database Mail uses accounts in the profile.</span></span> <span data-ttu-id="59475-249">Para uma nova mensagem de email, o Database Mail inicia com a conta que tem o número de sequência mais baixo.</span><span class="sxs-lookup"><span data-stu-id="59475-249">For a new e-mail message, Database Mail starts with the account that has the lowest sequence number.</span></span> <span data-ttu-id="59475-250">Se essa conta falhar, o Database Mail usará a conta com o próximo número de sequência mais alto, e assim por diante, até que o Database Mail envie a mensagem com êxito ou a conta com o número de sequência mais alto falhe.</span><span class="sxs-lookup"><span data-stu-id="59475-250">Should that account fail, Database Mail uses the account with the next highest sequence number, and so on until either Database Mail sends the message successfully, or the account with the highest sequence number fails.</span></span> <span data-ttu-id="59475-251">Se a conta com o número de sequência mais alto falhar, o Database Mail pausará as tentativas de envio de email pelo tempo configurado no parâmetro **AccountRetryDelay** no Database Mail e iniciará o processo de tentar enviar o email novamente, começando pelo número de sequência mais baixo.</span><span class="sxs-lookup"><span data-stu-id="59475-251">If the account with the highest sequence number fails, the Database Mail pauses attempts to send the mail for the amount of time configured in the Database Mail **AccountRetryDelay** parameter, then starts the process of attempting to send the mail again, starting with the lowest sequence number.</span></span> <span data-ttu-id="59475-252">Use o parâmetro **AccountRetryAttempts** do Database Mail para configurar o número de vezes em que o processo de email externo tenta enviar a mensagem de email usando cada conta no perfil especificado.</span><span class="sxs-lookup"><span data-stu-id="59475-252">Use the Database Mail **AccountRetryAttempts** parameter, to configure the number of times that the external mail process attempts to send the e-mail message using each account in the specified profile.</span></span> <span data-ttu-id="59475-253">Você pode configurar os parâmetros **AccountRetryDelay** e **AccountRetryAttempts** na página **Configurar Parâmetros do Sistema** do Assistente para Configuração do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-253">You can configure the **AccountRetryDelay** and **AccountRetryAttempts** parameters on the **Configure System Parameters** page of the Database Mail Configuration Wizard.</span></span>  
  
 <span data-ttu-id="59475-254">**Nome do perfil**</span><span class="sxs-lookup"><span data-stu-id="59475-254">**Profile name**</span></span>  
 <span data-ttu-id="59475-255">Digite o nome para o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-255">Type the name for the new profile.</span></span> <span data-ttu-id="59475-256">O perfil é criado com esse nome.</span><span class="sxs-lookup"><span data-stu-id="59475-256">The profile is created with this name.</span></span> <span data-ttu-id="59475-257">Não use o nome de um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="59475-257">Do not use the name of an existing profile.</span></span>  
  
 <span data-ttu-id="59475-258">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="59475-258">**Description**</span></span>  
 <span data-ttu-id="59475-259">Digite uma descrição para o perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-259">Type a description for the profile.</span></span> <span data-ttu-id="59475-260">A descrição é opcional.</span><span class="sxs-lookup"><span data-stu-id="59475-260">The description is optional.</span></span>  
  
 <span data-ttu-id="59475-261">**Contas SMTP**</span><span class="sxs-lookup"><span data-stu-id="59475-261">**SMTP accounts**</span></span>  
 <span data-ttu-id="59475-262">Escolha uma ou mais contas para o perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-262">Choose one or more accounts for the profile.</span></span> <span data-ttu-id="59475-263">A prioridade define a ordem na qual o Database Mail usa as contas.</span><span class="sxs-lookup"><span data-stu-id="59475-263">The priority sets the order in which Database Mail uses the accounts.</span></span> <span data-ttu-id="59475-264">Se nenhuma conta for listada, é necessário clicar em **Adicionar** para continuar e adicionar uma nova conta SMTP.</span><span class="sxs-lookup"><span data-stu-id="59475-264">If no accounts are listed, you must click **Add** to continue, and add a new SMTP account.</span></span>  
  
 <span data-ttu-id="59475-265">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="59475-265">**Add**</span></span>  
 <span data-ttu-id="59475-266">Adiciona uma conta ao perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-266">Add an account to the profile.</span></span>  
  
 <span data-ttu-id="59475-267">**Remover**</span><span class="sxs-lookup"><span data-stu-id="59475-267">**Remove**</span></span>  
 <span data-ttu-id="59475-268">Remove a conta selecionada do perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-268">Remove the selected account from the profile.</span></span>  
  
 <span data-ttu-id="59475-269">**Mover para Cima**</span><span class="sxs-lookup"><span data-stu-id="59475-269">**Move Up**</span></span>  
 <span data-ttu-id="59475-270">Aumente a prioridade da conta selecionada.</span><span class="sxs-lookup"><span data-stu-id="59475-270">Increase the priority of the selected account.</span></span>  
  
 <span data-ttu-id="59475-271">**Mover para Baixo**</span><span class="sxs-lookup"><span data-stu-id="59475-271">**Move Down**</span></span>  
 <span data-ttu-id="59475-272">Diminua a prioridade da conta selecionada.</span><span class="sxs-lookup"><span data-stu-id="59475-272">Decrease the priority of the selected account.</span></span>  
  

  
###  <a name="manage-existing-profile-page"></a><a name="ExistingProfile"></a><span data-ttu-id="59475-273">Página Gerenciar perfil existente</span><span class="sxs-lookup"><span data-stu-id="59475-273">Manage Existing Profile Page</span></span>  
 <span data-ttu-id="59475-274">Use esta página para gerenciar um perfil existente no Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-274">Use this page to manage an existing Database Mail profile.</span></span> <span data-ttu-id="59475-275">Um perfil do Database Mail é uma coleção de contas do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-275">A Database Mail profile is a collection of Database Mail accounts.</span></span> <span data-ttu-id="59475-276">Os perfis melhoram a confiabilidade nos casos em que um servidor de email não pode ser acessado, oferecendo contas alternativas do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-276">Profiles improve reliability in cases where an e-mail server becomes unreachable, by providing alternative Database Mail accounts.</span></span> <span data-ttu-id="59475-277">É necessário pelo menos uma conta do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-277">At least one Database Mail account is required.</span></span> <span data-ttu-id="59475-278">Para obter mais informações sobre como definir a prioridade das contas do Database Mail no perfil, veja [Criar um perfil do Database Mail](create-a-database-mail-profile.md).</span><span class="sxs-lookup"><span data-stu-id="59475-278">For more information about setting the priority of Database Mail accounts in the profile, see [Create a Database Mail Profile](create-a-database-mail-profile.md).</span></span>  
  
 <span data-ttu-id="59475-279">Use os botões **Mover para Cima** e **Mover para Baixo** para alterar a ordem na qual as contas do Database Mail são usadas.</span><span class="sxs-lookup"><span data-stu-id="59475-279">Use the **Move Up** and **Move Down** buttons to change the order in which Database Mail accounts are used.</span></span> <span data-ttu-id="59475-280">Essa ordem é determinada por um valor chamado número de sequência.</span><span class="sxs-lookup"><span data-stu-id="59475-280">This order is determined by a value called the sequence number.</span></span> <span data-ttu-id="59475-281">**Mover para Cima** diminui o número de sequência e **Mover para Baixo** aumenta o número de sequência.</span><span class="sxs-lookup"><span data-stu-id="59475-281">**Move Up** lowers the sequence number and **Move Down** increases the sequence number.</span></span> <span data-ttu-id="59475-282">O número de sequência determina a ordem na qual o Database Mail usa as contas no perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-282">The sequence number determines the order in which Database Mail uses accounts in the profile.</span></span> <span data-ttu-id="59475-283">Para uma nova mensagem de email, o Database Mail inicia com a conta que tem o número de sequência mais baixo.</span><span class="sxs-lookup"><span data-stu-id="59475-283">For a new e-mail message, Database Mail starts with the account that has the lowest sequence number.</span></span> <span data-ttu-id="59475-284">Se essa conta falhar, o Database Mail usará a conta com o próximo número de sequência mais alto, e assim por diante, até que o Database Mail envie a mensagem com êxito ou a conta com o número de sequência mais alto falhe.</span><span class="sxs-lookup"><span data-stu-id="59475-284">Should that account fail, Database Mail uses the account with the next highest sequence number, and so on until either Database Mail sends the message successfully, or the account with the highest sequence number fails.</span></span> <span data-ttu-id="59475-285">Se a conta com o número de sequência mais alto falhar, o Database Mail pausará as tentativas de envio de email pelo tempo configurado no parâmetro **AccountRetryDelay** no Database Mail e iniciará o processo de tentar enviar o email novamente, começando pelo número de sequência mais baixo.</span><span class="sxs-lookup"><span data-stu-id="59475-285">If the account with the highest sequence number fails, the Database Mail pauses attempts to send the mail for the amount of time configured in the Database Mail **AccountRetryDelay** parameter, then starts the process of attempting to send the mail again, starting with the lowest sequence number.</span></span> <span data-ttu-id="59475-286">Use o parâmetro **AccountRetryAttempts** do Database Mail para configurar o número de vezes em que o processo de email externo tenta enviar a mensagem de email usando cada conta no perfil especificado.</span><span class="sxs-lookup"><span data-stu-id="59475-286">Use the Database Mail **AccountRetryAttempts** parameter, to configure the number of times that the external mail process attempts to send the e-mail message using each account in the specified profile.</span></span> <span data-ttu-id="59475-287">Você pode configurar os parâmetros **AccountRetryDelay** e **AccountRetryAttempts** na página **Configurar Parâmetros do Sistema** do Assistente para Configuração do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-287">You can configure the **AccountRetryDelay** and **AccountRetryAttempts** parameters on the **Configure System Parameters** page of the Database Mail Configuration Wizard.</span></span>  
  
 <span data-ttu-id="59475-288">**Nome do perfil**</span><span class="sxs-lookup"><span data-stu-id="59475-288">**Profile name**</span></span>  
 <span data-ttu-id="59475-289">Selecione o nome do perfil a gerenciar.</span><span class="sxs-lookup"><span data-stu-id="59475-289">Select the name of the profile to manage.</span></span>  
  
 <span data-ttu-id="59475-290">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="59475-290">**Delete**</span></span>  
 <span data-ttu-id="59475-291">Exclui o perfil selecionado.</span><span class="sxs-lookup"><span data-stu-id="59475-291">Delete the selected profile.</span></span> <span data-ttu-id="59475-292">Você será solicitado a selecionar **Sim** para excluir o perfil selecionado e para optar por falhar em todas as mensagens não enviadas ou a selecionar **Não** para excluir o perfil selecionado apenas se não houver mensagens não enviadas.</span><span class="sxs-lookup"><span data-stu-id="59475-292">You will be prompted to select **Yes** to delete the selected profile and to fail any unsent messages, or to select **No** to delete the selected profile only if there are no unsent messages.</span></span>  
  
 <span data-ttu-id="59475-293">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="59475-293">**Description**</span></span>  
 <span data-ttu-id="59475-294">Exibe ou altera a descrição do perfil selecionado.</span><span class="sxs-lookup"><span data-stu-id="59475-294">View or change the description of the selected profile.</span></span> <span data-ttu-id="59475-295">A descrição é opcional.</span><span class="sxs-lookup"><span data-stu-id="59475-295">The description is optional.</span></span>  
  
 <span data-ttu-id="59475-296">**Contas SMTP**</span><span class="sxs-lookup"><span data-stu-id="59475-296">**SMTP accounts**</span></span>  
 <span data-ttu-id="59475-297">Escolha uma ou mais contas para o perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-297">Choose one or more accounts for the profile.</span></span> <span data-ttu-id="59475-298">A prioridade de failover define a ordem na qual o Database Mail usa a conta no caso de um failover.</span><span class="sxs-lookup"><span data-stu-id="59475-298">The failover priority sets the order in which Database Mail uses the account in case of a failover.</span></span>  
  
 <span data-ttu-id="59475-299">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="59475-299">**Add**</span></span>  
 <span data-ttu-id="59475-300">Adiciona uma conta ao perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-300">Add an account to the profile.</span></span>  
  
 <span data-ttu-id="59475-301">**Remover**</span><span class="sxs-lookup"><span data-stu-id="59475-301">**Remove**</span></span>  
 <span data-ttu-id="59475-302">Remove a conta selecionada do perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-302">Remove the selected account from the profile.</span></span>  
  
 <span data-ttu-id="59475-303">**Mover para Cima**</span><span class="sxs-lookup"><span data-stu-id="59475-303">**Move Up**</span></span>  
 <span data-ttu-id="59475-304">Aumenta a prioridade de failover da conta selecionada.</span><span class="sxs-lookup"><span data-stu-id="59475-304">Increase the failover priority of the selected account.</span></span>  
  
 <span data-ttu-id="59475-305">**Mover para Baixo**</span><span class="sxs-lookup"><span data-stu-id="59475-305">**Move Down**</span></span>  
 <span data-ttu-id="59475-306">Diminui a prioridade de failover da conta selecionada.</span><span class="sxs-lookup"><span data-stu-id="59475-306">Decrease the failover priority of the selected account.</span></span>  
  
 <span data-ttu-id="59475-307">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="59475-307">**Priority**</span></span>  
 <span data-ttu-id="59475-308">Exibe a prioridade de failover atual da conta.</span><span class="sxs-lookup"><span data-stu-id="59475-308">View the current failover priority of the account.</span></span>  
  
 <span data-ttu-id="59475-309">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="59475-309">**Account name**</span></span>  
 <span data-ttu-id="59475-310">Exibe o nome da conta.</span><span class="sxs-lookup"><span data-stu-id="59475-310">View the name of the account.</span></span>  
  
 <span data-ttu-id="59475-311">**Endereço de email**</span><span class="sxs-lookup"><span data-stu-id="59475-311">**E-mail Address**</span></span>  
 <span data-ttu-id="59475-312">Exibe o endereço de email da conta.</span><span class="sxs-lookup"><span data-stu-id="59475-312">View the e-mail address of the account.</span></span>  
  

  
###  <a name="add-account-to-profile-page"></a><a name="AddAccount"></a><span data-ttu-id="59475-313">Página Adicionar conta ao perfil</span><span class="sxs-lookup"><span data-stu-id="59475-313">Add Account to Profile Page</span></span>  
 <span data-ttu-id="59475-314">Use esta página para escolher a conta a ser adicionada ao perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-314">Use this page to choose the account to add to the profile.</span></span> <span data-ttu-id="59475-315">Escolha uma conta existente na caixa **Nome da conta** ou clique em **Nova Conta**.</span><span class="sxs-lookup"><span data-stu-id="59475-315">Either choose an existing account from the **Account name** box, or click **New Account**.</span></span>  
  
 <span data-ttu-id="59475-316">**Nome da Conta**</span><span class="sxs-lookup"><span data-stu-id="59475-316">**Account name**</span></span>  
 <span data-ttu-id="59475-317">Selecione o nome da conta a ser adicionada ao perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-317">Select the name of the account to add to the profile.</span></span>  
  
 <span data-ttu-id="59475-318">**Endereço de email**</span><span class="sxs-lookup"><span data-stu-id="59475-318">**E-mail address**</span></span>  
 <span data-ttu-id="59475-319">Visualize o endereço de email da conta selecionada.</span><span class="sxs-lookup"><span data-stu-id="59475-319">View the e-mail address for the selected account.</span></span> <span data-ttu-id="59475-320">Você não pode alterar o endereço de email nesta página.</span><span class="sxs-lookup"><span data-stu-id="59475-320">You cannot change the e-mail address from this page.</span></span> <span data-ttu-id="59475-321">Para alterar o endereço de email dessa conta, volte para a página principal do assistente e selecione a opção **Gerenciar contas e perfis do Database Mail** .</span><span class="sxs-lookup"><span data-stu-id="59475-321">To change the e-mail address for the account, go back to the main page of the wizard and select the **Manage Database Mail accounts and profiles** option.</span></span>  
  
 <span data-ttu-id="59475-322">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="59475-322">**Server name**</span></span>  
 <span data-ttu-id="59475-323">Visualize o nome do servidor de email da conta selecionada.</span><span class="sxs-lookup"><span data-stu-id="59475-323">View the mail server name for the selected account.</span></span> <span data-ttu-id="59475-324">Você não pode alterar o nome do servidor nesta página.</span><span class="sxs-lookup"><span data-stu-id="59475-324">You cannot change the server name from this page.</span></span> <span data-ttu-id="59475-325">Para alterar o nome do servidor dessa conta, volte para a página principal do assistente e selecione a opção **Gerenciar contas e perfis do Database Mail** .</span><span class="sxs-lookup"><span data-stu-id="59475-325">To change the server name for the account, go back to the main page of the wizard and select the **Manage Database Mail accounts and profiles** option.</span></span>  
  
 <span data-ttu-id="59475-326">**Nova Conta**</span><span class="sxs-lookup"><span data-stu-id="59475-326">**New Account**</span></span>  
 <span data-ttu-id="59475-327">Crie uma conta nova.</span><span class="sxs-lookup"><span data-stu-id="59475-327">Create a new account.</span></span>  
  

  
###  <a name="manage-accounts-and-profiles-page"></a><a name="AccountsProfiles"></a> <span data-ttu-id="59475-328">Página Gerenciar Contas e Perfis</span><span class="sxs-lookup"><span data-stu-id="59475-328">Manage Accounts and Profiles Page</span></span>  
 <span data-ttu-id="59475-329">Use esta página para escolher uma tarefa para gerenciar um perfil ou conta.</span><span class="sxs-lookup"><span data-stu-id="59475-329">Use this page to choose a task for managing a profile or account.</span></span>  
  
 <span data-ttu-id="59475-330">**Criar uma nova conta**</span><span class="sxs-lookup"><span data-stu-id="59475-330">**Create a new account**</span></span>  
 <span data-ttu-id="59475-331">Crie uma conta nova.</span><span class="sxs-lookup"><span data-stu-id="59475-331">Create a new account.</span></span>  
  
 <span data-ttu-id="59475-332">**Visualizar, alterar ou excluir uma conta existente**</span><span class="sxs-lookup"><span data-stu-id="59475-332">**View, change or delete an existing account**</span></span>  
 <span data-ttu-id="59475-333">Gerencie ou exclua uma conta existente.</span><span class="sxs-lookup"><span data-stu-id="59475-333">Manage or delete an existing account.</span></span>  
  
 <span data-ttu-id="59475-334">**Criar um novo perfil**</span><span class="sxs-lookup"><span data-stu-id="59475-334">**Create a new profile**</span></span>  
 <span data-ttu-id="59475-335">Crie um novo perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-335">Create a new profile.</span></span>  
  
 <span data-ttu-id="59475-336">**Exibir, alterar ou excluir um perfil existente. Você também pode gerenciar contas associadas ao perfil.**</span><span class="sxs-lookup"><span data-stu-id="59475-336">**View, change or delete an existing profile. You can also manage accounts associated with the profile.**</span></span>  
 <span data-ttu-id="59475-337">Atualize ou exclua um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="59475-337">Update or delete an existing profile.</span></span> <span data-ttu-id="59475-338">Essa opção também permite gerenciar contas associadas ao perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-338">This option also allows you to manage accounts associated with the profile.</span></span>  
  

  
###  <a name="manage-profile-security-public-tab"></a><a name="ProfileSecurityPublic"></a><span data-ttu-id="59475-339">Gerenciar a segurança do perfil, guia público</span><span class="sxs-lookup"><span data-stu-id="59475-339">Manage Profile Security, Public Tab</span></span>  
 <span data-ttu-id="59475-340">Use essa página para configurar um perfil público.</span><span class="sxs-lookup"><span data-stu-id="59475-340">Use this page to configure a public profile.</span></span>  
  
 <span data-ttu-id="59475-341">Perfis são públicos ou privados.</span><span class="sxs-lookup"><span data-stu-id="59475-341">Profiles are either public or private.</span></span> <span data-ttu-id="59475-342">Um perfil privado é acessível somente para usuários ou funções específicas.</span><span class="sxs-lookup"><span data-stu-id="59475-342">A private profile is accessible only to specific users or roles.</span></span> <span data-ttu-id="59475-343">Um perfil público permite a qualquer usuário ou função com acesso ao banco de dados do host de email (**msdb**) enviar um email usando esse perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-343">A public profile allows any user or role with access to the mail host database (**msdb**) to send e-mail using that profile.</span></span>  
  
 <span data-ttu-id="59475-344">Um perfil pode ser um perfil padrão.</span><span class="sxs-lookup"><span data-stu-id="59475-344">A profile may be a default profile.</span></span> <span data-ttu-id="59475-345">Nesse caso, usuários ou funções podem enviar e-mails por meio do perfil sem especificá-lo explicitamente.</span><span class="sxs-lookup"><span data-stu-id="59475-345">In this case, users or roles can send e-mail using the profile without explicitly specifying the profile.</span></span> <span data-ttu-id="59475-346">Se o usuário ou função que envia a mensagem de e-mail tiver um perfil privado padrão, o Database Mail irá utilizá-lo.</span><span class="sxs-lookup"><span data-stu-id="59475-346">If the user or role sending the e-mail message has a default private profile, Database Mail uses that profile.</span></span> <span data-ttu-id="59475-347">Se o usuário ou função não tiver nenhum perfil privado padrão, **sp_send_dbmail** usará o perfil público padrão para o banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="59475-347">If the user or role has no default private profile, **sp_send_dbmail** uses the default public profile for the **msdb** database.</span></span> <span data-ttu-id="59475-348">Se não houver nenhum perfil privado padrão para o usuário ou função e nenhum perfil público padrão para o banco de dados, **sp_send_dbmail** retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="59475-348">If there is no default private profile for the user or role and no default public profile for the database, **sp_send_dbmail** returns an error.</span></span> <span data-ttu-id="59475-349">Somente um perfil pode ser marcado como o perfil padrão.</span><span class="sxs-lookup"><span data-stu-id="59475-349">Only one profile can be marked as the default profile.</span></span>  
  
 <span data-ttu-id="59475-350">**Pública**</span><span class="sxs-lookup"><span data-stu-id="59475-350">**Public**</span></span>  
 <span data-ttu-id="59475-351">Selecione essa opção para tornar público o perfil especificado.</span><span class="sxs-lookup"><span data-stu-id="59475-351">Select this option to make the specified profile public.</span></span>  
  
 <span data-ttu-id="59475-352">**Nome do Perfil**</span><span class="sxs-lookup"><span data-stu-id="59475-352">**Profile Name**</span></span>  
 <span data-ttu-id="59475-353">Exibe o nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-353">Displays the name of the profile.</span></span>  
  
 <span data-ttu-id="59475-354">**Perfil padrão**</span><span class="sxs-lookup"><span data-stu-id="59475-354">**Default Profile**</span></span>  
 <span data-ttu-id="59475-355">Selecione essa opção para transformar o perfil especificado em perfil padrão.</span><span class="sxs-lookup"><span data-stu-id="59475-355">Select this option to make the specified profile the default profile.</span></span>  
  
 <span data-ttu-id="59475-356">**Mostrar somente os perfis públicos existentes**</span><span class="sxs-lookup"><span data-stu-id="59475-356">**Show only existing public profiles**</span></span>  
 <span data-ttu-id="59475-357">Selecione essa opção para mostrar somente perfis públicos no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="59475-357">Select this option to show only public profiles in the specified database.</span></span>  
  

  
###  <a name="manage-profile-security-private-tab"></a><a name="ProfileSecurityPrivate"></a><span data-ttu-id="59475-358">Gerenciar segurança de perfil, guia particular</span><span class="sxs-lookup"><span data-stu-id="59475-358">Manage Profile Security, Private Tab</span></span>  
 <span data-ttu-id="59475-359">Use essa página para configurar um perfil privado.</span><span class="sxs-lookup"><span data-stu-id="59475-359">Use this page to configure a private profile.</span></span>  
  
 <span data-ttu-id="59475-360">Perfis são públicos ou privados.</span><span class="sxs-lookup"><span data-stu-id="59475-360">Profiles are either public or private.</span></span> <span data-ttu-id="59475-361">Um perfil privado é acessível somente para usuários ou funções específicas.</span><span class="sxs-lookup"><span data-stu-id="59475-361">A private profile is accessible only to specific users or roles.</span></span> <span data-ttu-id="59475-362">Um perfil público permite a qualquer usuário ou função com acesso ao banco de dados do host de email (**msdb**) enviar um email usando esse perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-362">A public profile allows any user or role with access to the mail host database (**msdb**) to send e-mail using that profile.</span></span>  
  
 <span data-ttu-id="59475-363">Um perfil pode ser um perfil padrão.</span><span class="sxs-lookup"><span data-stu-id="59475-363">A profile may be a default profile.</span></span> <span data-ttu-id="59475-364">Nesse caso, usuários ou funções podem enviar e-mails por meio do perfil sem especificá-lo explicitamente.</span><span class="sxs-lookup"><span data-stu-id="59475-364">In this case, users or roles can send e-mail using the profile without explicitly specifying the profile.</span></span> <span data-ttu-id="59475-365">Se o usuário ou função que envia a mensagem de e-mail tiver um perfil privado padrão, o Database Mail irá utilizá-lo.</span><span class="sxs-lookup"><span data-stu-id="59475-365">If the user or role sending the e-mail message has a default private profile, Database Mail uses that profile.</span></span> <span data-ttu-id="59475-366">Se o usuário ou função não tiver nenhum perfil privado padrão, **sp_send_dbmail** usará o perfil público padrão para o banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="59475-366">If the user or role has no default private profile, **sp_send_dbmail** uses the default public profile for the **msdb** database.</span></span> <span data-ttu-id="59475-367">Se não houver nenhum perfil privado padrão para o usuário ou função e nenhum perfil público padrão para o banco de dados, **sp_send_dbmail** retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="59475-367">If there is no default private profile for the user or role and no default public profile for the database, **sp_send_dbmail** returns an error.</span></span>  
  
 <span data-ttu-id="59475-368">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="59475-368">**User name**</span></span>  
 <span data-ttu-id="59475-369">Selecione o nome de um usuário ou função no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="59475-369">Select the name of a user or role in the **msdb** database.</span></span>  
  
 <span data-ttu-id="59475-370">**Acesso**</span><span class="sxs-lookup"><span data-stu-id="59475-370">**Access**</span></span>  
 <span data-ttu-id="59475-371">Selecione se o usuário ou função tem acesso ao perfil especificado.</span><span class="sxs-lookup"><span data-stu-id="59475-371">Select whether the user or role has access to the specified profile.</span></span>  
  
 <span data-ttu-id="59475-372">**Nome do perfil**</span><span class="sxs-lookup"><span data-stu-id="59475-372">**Profile name**</span></span>  
 <span data-ttu-id="59475-373">Exibir nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-373">View the name of the profile.</span></span>  
  
 <span data-ttu-id="59475-374">**É Perfil Padrão**</span><span class="sxs-lookup"><span data-stu-id="59475-374">**Is Default Profile**</span></span>  
 <span data-ttu-id="59475-375">Selecione se o perfil é o perfil padrão para o usuário ou função.</span><span class="sxs-lookup"><span data-stu-id="59475-375">Select whether the profile is the default profile for the user or role.</span></span> <span data-ttu-id="59475-376">Cada usuário ou função pode ter apenas um perfil de padrão.</span><span class="sxs-lookup"><span data-stu-id="59475-376">Each user or role may have only one default profile.</span></span>  
  
 <span data-ttu-id="59475-377">**Mostrar somente os perfis particulares existentes deste usuário**</span><span class="sxs-lookup"><span data-stu-id="59475-377">**Show only existing private profiles for this user**</span></span>  
 <span data-ttu-id="59475-378">Selecione essa opção para exibir apenas perfis aos quais o usuário ou função especificados já tenham acesso.</span><span class="sxs-lookup"><span data-stu-id="59475-378">Select this option to display only profiles that the specified user or role already has access to.</span></span>  
  

  
###  <a name="configure-system-parameters"></a><a name="SystemParameters"></a><span data-ttu-id="59475-379">Configurar parâmetros do sistema</span><span class="sxs-lookup"><span data-stu-id="59475-379">Configure System Parameters</span></span>  
 <span data-ttu-id="59475-380">Use esta página para especificar parâmetros de sistema do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-380">Use this page to specify Database Mail system parameters.</span></span> <span data-ttu-id="59475-381">Exibe os parâmetros de sistema e o valor atual de cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="59475-381">View the system parameters and the current value of each parameter.</span></span> <span data-ttu-id="59475-382">Selecione um parâmetro para exibir uma breve descrição no painel de informações.</span><span class="sxs-lookup"><span data-stu-id="59475-382">Select a parameter to view a short description in the information pane.</span></span>  
  
 <span data-ttu-id="59475-383">**Tentativas de Repetição de Conta**</span><span class="sxs-lookup"><span data-stu-id="59475-383">**Account Retry Attempts**</span></span>  
 <span data-ttu-id="59475-384">O número de vezes que o processo de email externo tenta enviar a mensagem de email usando cada conta no perfil especificado.</span><span class="sxs-lookup"><span data-stu-id="59475-384">The number of times that the external mail process attempts to send the e-mail message using each account in the specified profile.</span></span>  
  
 <span data-ttu-id="59475-385">**Atraso na Repetição de Conta (segundos)**</span><span class="sxs-lookup"><span data-stu-id="59475-385">**Account Retry Delay (seconds)**</span></span>  
 <span data-ttu-id="59475-386">O tempo, em segundos em que o processo de email externo espera, depois de tentar enviar uma mensagem usando todas as contas no perfil, antes de tentar todas as contas novamente.</span><span class="sxs-lookup"><span data-stu-id="59475-386">The amount of time, in seconds, for the external mail process to wait after it tries to deliver a message using all accounts in the profile before it attempts all accounts again.</span></span>  
  
 <span data-ttu-id="59475-387">**Tamanho Máximo do Arquivo (Bytes)**</span><span class="sxs-lookup"><span data-stu-id="59475-387">**Maximum File Size (Bytes)**</span></span>  
 <span data-ttu-id="59475-388">O tamanho máximo de um anexo, em bytes.</span><span class="sxs-lookup"><span data-stu-id="59475-388">The maximum size of an attachment, in bytes.</span></span>  
  
 <span data-ttu-id="59475-389">**Extensões de Arquivo de Anexo Proibidas**</span><span class="sxs-lookup"><span data-stu-id="59475-389">**Prohibited Attachment File Extensions**</span></span>  
 <span data-ttu-id="59475-390">Uma lista separada por vírgula de extensões que não podem ser enviadas como um anexo a uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="59475-390">A comma-separated list of extensions which cannot be sent as an attachment to an e-mail message.</span></span> <span data-ttu-id="59475-391">Clique no botão Procurar (**...**) para adicionar outras extensões.</span><span class="sxs-lookup"><span data-stu-id="59475-391">Click the browse button (**...**) to add additional extensions.</span></span>  
  
 <span data-ttu-id="59475-392">**Tempo Mínimo de Vida do Executável do Database Mail (segundos)**</span><span class="sxs-lookup"><span data-stu-id="59475-392">**Database Mail Executable Minimum Lifetime (seconds)**</span></span>  
 <span data-ttu-id="59475-393">O período mínimo de tempo, em segundos, que o processo de email externo permanece ativo.</span><span class="sxs-lookup"><span data-stu-id="59475-393">The minimum amount of time, in seconds, that the external mail process remains active.</span></span> <span data-ttu-id="59475-394">O processo permanece ativo enquanto houver emails na fila do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-394">The process remains active as long as there are e-mails in the Database Mail queue.</span></span> <span data-ttu-id="59475-395">Esse parâmetro especifica o tempo que o processo permanece ativo se não houver nenhuma mensagem a processar.</span><span class="sxs-lookup"><span data-stu-id="59475-395">This parameter specifies the time the process remains active if there are no messages to process.</span></span>  
  
 <span data-ttu-id="59475-396">**Nível de log**</span><span class="sxs-lookup"><span data-stu-id="59475-396">**Logging level**</span></span>  
 <span data-ttu-id="59475-397">Especifique quais mensagens são registradas no log do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-397">Specify which messages are recorded in the Database Mail log.</span></span> <span data-ttu-id="59475-398">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="59475-398">Possible values are:</span></span>  
  
-   <span data-ttu-id="59475-399">Normal - só registra erros</span><span class="sxs-lookup"><span data-stu-id="59475-399">Normal - logs only errors</span></span>  
  
-   <span data-ttu-id="59475-400">Estendido - registra erros, avisos e mensagens informativas</span><span class="sxs-lookup"><span data-stu-id="59475-400">Extended - logs errors, warnings, and informational messages</span></span>  
  
-   <span data-ttu-id="59475-401">Detalhado - registra erros, avisos, mensagens informativas, mensagens de êxito e mensagens internas adicionais.</span><span class="sxs-lookup"><span data-stu-id="59475-401">Verbose - logs errors, warnings, informational messages, success messages, and additional internal messages.</span></span> <span data-ttu-id="59475-402">Use log detalhado para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="59475-402">Use verbose logging for troubleshooting.</span></span>  
  
 <span data-ttu-id="59475-403">O valor padrão é Estendido.</span><span class="sxs-lookup"><span data-stu-id="59475-403">Default value is Extended.</span></span>  
  
 <span data-ttu-id="59475-404">**Redefinir Tudo**</span><span class="sxs-lookup"><span data-stu-id="59475-404">**Reset All**</span></span>  
 <span data-ttu-id="59475-405">Selecione esta opção para restaurar os valores da página aos valores padrão originais.</span><span class="sxs-lookup"><span data-stu-id="59475-405">Select this option to reset the values on the page to the default values.</span></span>  
  

  
###  <a name="complete-the-wizard-page"></a><a name="CompleteWizard"></a><span data-ttu-id="59475-406">Concluir a página do assistente</span><span class="sxs-lookup"><span data-stu-id="59475-406">Complete the Wizard Page</span></span>  
 <span data-ttu-id="59475-407">Use essa página para ver as ações que o **Assistente para Configuração do Database Mail** executará.</span><span class="sxs-lookup"><span data-stu-id="59475-407">Use this page to review the actions that **Database Mail Configuration Wizard** will perform.</span></span> <span data-ttu-id="59475-408">Nenhuma alteração é feita até que você conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="59475-408">No changes are made until you finish the wizard.</span></span>  
  

  
###  <a name="send-test-e-mail-page"></a><a name="TestEmail"></a> <span data-ttu-id="59475-409">Send Test E-Mail Page</span><span class="sxs-lookup"><span data-stu-id="59475-409">Send Test E-Mail Page</span></span>  
 <span data-ttu-id="59475-410">Use a página **Enviar Email de Teste de**_<instance_name>_ para enviar uma mensagem de email usando o perfil especificado do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-410">Use the **Send Test E-Mail from**_<instance_name>_ page to send an e-mail message using the specified Database Mail profile.</span></span> <span data-ttu-id="59475-411">Só os membros da função de servidor fixa **sysadmin** podem enviar email de teste usando essa página.</span><span class="sxs-lookup"><span data-stu-id="59475-411">Only members of the **sysadmin** fixed server role can send test e-mail using this page.</span></span>  
  
 <span data-ttu-id="59475-412">**Perfil do Database Mail**</span><span class="sxs-lookup"><span data-stu-id="59475-412">**Database Mail Profile**</span></span>  
 <span data-ttu-id="59475-413">Selecione um perfil da lista do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="59475-413">Select a Database Mail profile from the list.</span></span> <span data-ttu-id="59475-414">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="59475-414">This is a required field.</span></span> <span data-ttu-id="59475-415">Se nenhum perfil for mostrado, não há nenhum perfil ou você não tem permissão para um perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-415">If no profiles are shown, there are no profiles or you do not have permission to a profile.</span></span> <span data-ttu-id="59475-416">Use o **Assistente para Configuração do Database Mail** para criar e configurar perfis.</span><span class="sxs-lookup"><span data-stu-id="59475-416">Use the **Database Mail Configuration Wizard** to create and configure profiles.</span></span> <span data-ttu-id="59475-417">Se nenhum perfil for listado, use o Assistente para Configuração do Database Mail para criar um perfil para seu uso.</span><span class="sxs-lookup"><span data-stu-id="59475-417">If no profiles are listed, use the Database Mail Configuration Wizard to create a profile for your use.</span></span>  
  
 <span data-ttu-id="59475-418">**Para**</span><span class="sxs-lookup"><span data-stu-id="59475-418">**To**</span></span>  
 <span data-ttu-id="59475-419">O endereço de email dos destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="59475-419">The e-mail address of the message recipients.</span></span> <span data-ttu-id="59475-420">Exige-se pelo menos um destinatário.</span><span class="sxs-lookup"><span data-stu-id="59475-420">At least one recipient is required.</span></span>  
  
 <span data-ttu-id="59475-421">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="59475-421">**Subject**</span></span>  
 <span data-ttu-id="59475-422">A linha de assunto para o email de teste.</span><span class="sxs-lookup"><span data-stu-id="59475-422">The subject line for the test e-mail.</span></span> <span data-ttu-id="59475-423">Altere o assunto padrão para identificar melhor seu email para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="59475-423">Change the default subject to better identify your email for troubleshooting.</span></span>  
  
 <span data-ttu-id="59475-424">**Corpo**</span><span class="sxs-lookup"><span data-stu-id="59475-424">**Body**</span></span>  
 <span data-ttu-id="59475-425">O corpo do email de teste.</span><span class="sxs-lookup"><span data-stu-id="59475-425">The body of the test e-mail.</span></span> <span data-ttu-id="59475-426">Altere o assunto padrão para identificar melhor seu email para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="59475-426">Change the default subject to better identify your email for troubleshooting.</span></span>  
  
 <span data-ttu-id="59475-427">A caixa de diálogo **Email de Teste do Database Mail** confirma que o Database Mail tentou enviar a mensagem de teste e fornece a **mailitem_id** para a mensagem de teste de email.</span><span class="sxs-lookup"><span data-stu-id="59475-427">The **Database Mail Test E-Mail** dialog box confirms that the test message that Database Mail attempted to send the message and provides the **mailitem_id** for the test e-mail message.</span></span> <span data-ttu-id="59475-428">Confirme com o destinatário para determinar se o email foi recebido.</span><span class="sxs-lookup"><span data-stu-id="59475-428">Check with the recipient to determine if the e-mail arrived.</span></span> <span data-ttu-id="59475-429">Geralmente, o email é recebido dentro de poucos minutos, mas o email pode ser atrasado por um desempenho lento da rede, por uma lista de pendências de mensagens no servidor de email ou caso o servidor esteja temporariamente indisponível.</span><span class="sxs-lookup"><span data-stu-id="59475-429">Normally e-mail is received in a few minutes, but the e-mail can be delayed because of slow network performance, a backlog of messages at the mail server, or if the server is temporarily unavailable.</span></span> <span data-ttu-id="59475-430">Use **mailitem_id** para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="59475-430">Use the **mailitem_id** for troubleshooting.</span></span>  
  
 <span data-ttu-id="59475-431">**Enviar email**</span><span class="sxs-lookup"><span data-stu-id="59475-431">**Sent e-mail**</span></span>  
 <span data-ttu-id="59475-432">A **mailitem_id** da mensagem de teste de email.</span><span class="sxs-lookup"><span data-stu-id="59475-432">The **mailitem_id** of the test e-mail message.</span></span>  
  
 <span data-ttu-id="59475-433">**Solucionar problemas**</span><span class="sxs-lookup"><span data-stu-id="59475-433">**Troubleshoot**</span></span>  
 <span data-ttu-id="59475-434">Clique para abrir os Manuais Online no tópico [Solucionando problemas do Database Mail](https://msdn.microsoft.com/library/ms188663.aspx).</span><span class="sxs-lookup"><span data-stu-id="59475-434">Click to open Books Online to the [Troubleshooting Database Mail](https://msdn.microsoft.com/library/ms188663.aspx)topic.</span></span>  
  

  
##  <a name="using-templates"></a><a name="Template"></a> <span data-ttu-id="59475-435">Usando modelos</span><span class="sxs-lookup"><span data-stu-id="59475-435">Using Templates</span></span>  
 <span data-ttu-id="59475-436">**Para criar um script de configuração do Database Mail**</span><span class="sxs-lookup"><span data-stu-id="59475-436">**To create a Database Mail configuration script**</span></span>  
  
1.  <span data-ttu-id="59475-437">No menu **Exibir** , selecione **Explorador de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="59475-437">On the **View** menu, select **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="59475-438">Na janela **Explorador de Modelos** , expanda a pasta **Database Mail** .</span><span class="sxs-lookup"><span data-stu-id="59475-438">In the **Template Explorer** window, expand the **Database Mail** folder.</span></span>  
  
3.  <span data-ttu-id="59475-439">Clique duas vezes em **Configuração Simples do Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="59475-439">Double-click **Simple Database Mail Configuration**.</span></span> <span data-ttu-id="59475-440">O modelo é aberto em uma nova janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="59475-440">The template opens in a new query window.</span></span>  
  
4.  <span data-ttu-id="59475-441">No menu **Consulta** , selecione **Especificar Valores para Parâmetros de Modelo**.</span><span class="sxs-lookup"><span data-stu-id="59475-441">On the **Query** menu, select **Specify Values for Template Parameters**.</span></span> <span data-ttu-id="59475-442">A janela **Substituir Parâmetros de Modelo** é exibida.</span><span class="sxs-lookup"><span data-stu-id="59475-442">The **Replace Template Parameters** window opens.</span></span>  
  
5.  <span data-ttu-id="59475-443">Digite os valores para **profile_name**, **account_name**, **SMTP_servername**, **email_address**e **display_name**.</span><span class="sxs-lookup"><span data-stu-id="59475-443">Type values for the **profile_name**, **account_name**, **SMTP_servername**, **email_address**, and **display_name**.</span></span> <span data-ttu-id="59475-444">O SQL Server Management Studio preenche o modelo com os valores fornecidos por você.</span><span class="sxs-lookup"><span data-stu-id="59475-444">SQL Server Management Studio fills in the template with the values you provide.</span></span>  
  
6.  <span data-ttu-id="59475-445">Execute o script para criar a configuração.</span><span class="sxs-lookup"><span data-stu-id="59475-445">Execute the script to create the configuration.</span></span>  
  
7.  <span data-ttu-id="59475-446">O script não concede nenhum acesso de usuário de banco de dados ao perfil.</span><span class="sxs-lookup"><span data-stu-id="59475-446">The script does not grant any database users access to the profile.</span></span> <span data-ttu-id="59475-447">Portanto, por padrão, o perfil pode ser usado apenas por membros da função de segurança fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="59475-447">Therefore, by default, the profile can only be used by members of the **sysadmin** fixed security role.</span></span> <span data-ttu-id="59475-448">Para obter mais informações sobre como conceder acesso a perfis, veja [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="59475-448">For more information about granting access to profiles, see [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql)</span></span>  
  
  
