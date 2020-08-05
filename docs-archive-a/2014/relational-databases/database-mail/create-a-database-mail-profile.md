---
title: Criar um perfil do Database Mail | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], public profiles
- profiles [SQL Server], Database Mail
- public profiles [Database Mail]
ms.assetid: 58ae749d-6ada-4f9c-bf00-de7c7a992a2d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0453d495c90c1e599bfc7777b4899f30e6659c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572104"
---
# <a name="create-a-database-mail-profile"></a><span data-ttu-id="df11c-102">Criar um perfil do Database Mail</span><span class="sxs-lookup"><span data-stu-id="df11c-102">Create a Database Mail Profile</span></span>
  <span data-ttu-id="df11c-103">Use o **Assistente para Configuração do Database Mail** ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] para criar perfis públicos e privados do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="df11c-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create Database Mail public and private profiles.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="df11c-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="df11c-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="df11c-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="df11c-105">Prerequisites</span></span>  
 <span data-ttu-id="df11c-106">Crie uma ou mais contas do Database Mail para o perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-106">Create one or more Database Mail accounts for the profile.</span></span> <span data-ttu-id="df11c-107">Para obter mais informações sobre como criar o Database Mail, veja [Criar uma conta do Database Mail](create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="df11c-107">For more information about creating Database Mail accounts, see [Create a Database Mail Account](create-a-database-mail-account.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="df11c-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="df11c-108">Security</span></span>  
 <span data-ttu-id="df11c-109">Um perfil público permite a qualquer usuário acessar o banco de dados **msdb** para enviar emails usando o perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-109">A public profile allows any user with access to the **msdb** database to send e-mail using that profile.</span></span> <span data-ttu-id="df11c-110">Um perfil particular pode ser usado por um usuário ou por uma função.</span><span class="sxs-lookup"><span data-stu-id="df11c-110">A private profile can be used by a user or by a role.</span></span> <span data-ttu-id="df11c-111">Conceder a funções o acesso a perfis cria uma arquitetura de mais fácil manutenção.</span><span class="sxs-lookup"><span data-stu-id="df11c-111">Granting roles access to profiles creates a more easily maintained architecture.</span></span> <span data-ttu-id="df11c-112">Para enviar emails, você deve ser membro da função **DatabaseMailUserRole** no banco de dados **msdb** e ter acesso a pelo menos um perfil do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="df11c-112">To send mail you must be a member of the **DatabaseMailUserRole** in the **msdb** database, and have access to at least one Database Mail profile.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="df11c-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="df11c-113">Permissions</span></span>  
 <span data-ttu-id="df11c-114">O usuário que cria as contas de perfis e executa procedimentos armazenados deve ser membro da função de servidor fixa sysadmin.</span><span class="sxs-lookup"><span data-stu-id="df11c-114">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  

  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="df11c-115">Usando o assistente para configuração do Database Mail</span><span class="sxs-lookup"><span data-stu-id="df11c-115">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="df11c-116">**Para criar um perfil do Database Mail**</span><span class="sxs-lookup"><span data-stu-id="df11c-116">**To Create a Database Mail profile**</span></span>  
  
-   <span data-ttu-id="df11c-117">No Pesquisador de Objetos, conecte-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usada para configurar o Database Mail e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="df11c-117">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="df11c-118">Expanda o nó **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="df11c-118">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="df11c-119">Clique duas vezes em Database Mail para abrir o Assistente de Configuração do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="df11c-119">Double click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="df11c-120">Na página **selecionar tarefa de configuração** , selecione a opção **gerenciar contas e perfis de Database Mail** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-120">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option and click **Next**.</span></span>  
  
-   <span data-ttu-id="df11c-121">Na página **Gerenciar Perfis e Contas** , selecione a opção **Criar um novo perfil** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-121">On the **Manage Profiles and Accounts** page, select **Create a new profile** option, and click **Next**.</span></span>  
  
-   <span data-ttu-id="df11c-122">Na página **Novo Perfil**, especifique o nome do Perfil, a Descrição e adicione contas a serem incluídas no perfil; depois, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-122">On the **New Profile** page, specify the Profile name, Description and add accounts to be included in the profile, and click **Next**.</span></span>  
  
-   <span data-ttu-id="df11c-123">Na página **Concluir o Assistente** , examine as ações a serem executadas e clique em **Concluir** para concluir a criação de um novo perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-123">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new profile.</span></span>  
  
-   <span data-ttu-id="df11c-124">**Para configurar um perfil privado do Database Mail:**</span><span class="sxs-lookup"><span data-stu-id="df11c-124">**To configure a Database Mail private profile:**</span></span>  
  
    -   <span data-ttu-id="df11c-125">Abra o Assistente para Configuração do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="df11c-125">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="df11c-126">Na página **Selecionar Tarefa de Configuração** , selecione a opção **Gerenciar contas e perfis do Database Mail** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-126">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="df11c-127">Na página **Gerenciar Perfis e Contas** , selecione a opção **Gerenciar segurança do perfil** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-127">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="df11c-128">Na guia **Perfis Privados** , marque a caixa de seleção do perfil a ser configurado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-128">In the **Private Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="df11c-129">Na página **Concluir o Assistente** , examine as ações a serem executadas e clique em **Concluir** para concluir a configuração do perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-129">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  
-   <span data-ttu-id="df11c-130">**Para configurar um perfil público do Database Mail:**</span><span class="sxs-lookup"><span data-stu-id="df11c-130">**To configure a Database Mail public profile:**</span></span>  
  
    -   <span data-ttu-id="df11c-131">Abra o Assistente para Configuração do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="df11c-131">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="df11c-132">Na página **Selecionar Tarefa de Configuração** , selecione a opção **Gerenciar contas e perfis do Database Mail** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-132">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="df11c-133">Na página **Gerenciar Perfis e Contas** , selecione a opção **Gerenciar segurança do perfil** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-133">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="df11c-134">Na guia **Perfis Públicos** , marque a caixa de seleção do perfil a ser configurado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="df11c-134">In the **Public Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="df11c-135">Na página **Concluir o Assistente** , examine as ações a serem executadas e clique em **Concluir** para concluir a configuração do perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-135">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  

  
## <a name="using-transact-sql"></a><span data-ttu-id="df11c-136">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="df11c-136">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-database-mail-private-profile"></a><a name="PrivateProfile"></a><span data-ttu-id="df11c-137">Para criar um perfil particular Database Mail</span><span class="sxs-lookup"><span data-stu-id="df11c-137">To Create a Database Mail private profile</span></span>  
  
-   <span data-ttu-id="df11c-138">Conecte à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df11c-138">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="df11c-139">Para criar um novo perfil, execute o procedimento armazenado no sistema [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="df11c-139">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="df11c-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="df11c-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="df11c-141">*@profile_name*= '*Nome do perfil*'</span><span class="sxs-lookup"><span data-stu-id="df11c-141">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="df11c-142">*@description*= '*Descrição*'</span><span class="sxs-lookup"><span data-stu-id="df11c-142">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="df11c-143">em que *@profile_name* é o nome do perfil e *@description* é a descrição do perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-143">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="df11c-144">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="df11c-144">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="df11c-145">Para cada conta, execute o procedimento armazenado [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="df11c-145">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="df11c-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="df11c-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="df11c-147">*@profile_name*= '*Nome do perfil*'</span><span class="sxs-lookup"><span data-stu-id="df11c-147">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="df11c-148">*@account_name*= '*Nome da conta*'</span><span class="sxs-lookup"><span data-stu-id="df11c-148">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="df11c-149">*@sequence_number*= '*número de sequência da conta dentro do perfil.*</span><span class="sxs-lookup"><span data-stu-id="df11c-149">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="df11c-150">'</span><span class="sxs-lookup"><span data-stu-id="df11c-150">'</span></span>  
  
     <span data-ttu-id="df11c-151">em que *@profile_name* é o nome do perfil e *@account_name* é o nome da conta a ser adicionada ao perfil, *@sequence_number* determina a ordem na qual as contas são usadas no perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-151">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="df11c-152">Para cada função de banco de dados ou usuário que enviará email usando este perfil, conceda acesso ao perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-152">For each database role or user that will send mail using this profile, grant access to the profile.</span></span> <span data-ttu-id="df11c-153">Para fazer isso, execute o procedimento armazenado [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="df11c-153">To do this, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="df11c-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="df11c-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="df11c-155">*@profile_name*= '*Nome do perfil*'</span><span class="sxs-lookup"><span data-stu-id="df11c-155">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="df11c-156">*@ principal_name* = “*Nome de usuário de banco de dados ou função*”</span><span class="sxs-lookup"><span data-stu-id="df11c-156">*@ principal_name* = '*Name of the database user or role*'</span></span>  
  
     <span data-ttu-id="df11c-157">*@is_default*= '*Status do perfil padrão* '</span><span class="sxs-lookup"><span data-stu-id="df11c-157">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="df11c-158">em que *@profile_name* é o nome do perfil e *@principal_name* é o nome do usuário ou da função do banco de dados, *@is_default* determina se esse perfil é o padrão para o usuário ou a função do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="df11c-158">where *@profile_name* is the name of the profile, and *@principal_name* is the name of the database user or role, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="df11c-159">O exemplo a seguir cria uma conta do Database Mail, cria um perfil privado do Database Mail, adiciona a conta ao perfil e concede acesso ao perfil à função de banco de dados **DBMailUsers** no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="df11c-159">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants access to the profile to the **DBMailUsers** database role in the **msdb** database.</span></span>  
  
```  
-- Create a Database Mail account  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @account_name = 'AdventureWorks Administrator',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to the DBMailUsers role  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @principal_name = 'ApplicationUser',  
    @is_default = 1 ;  
```  
  
 
  
###  <a name="to-create-a-database-mail-public-profile"></a><a name="PublicProfile"></a><span data-ttu-id="df11c-160">Para criar um perfil público Database Mail</span><span class="sxs-lookup"><span data-stu-id="df11c-160">To Create a Database Mail public profile</span></span>  
  
-   <span data-ttu-id="df11c-161">Conecte à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df11c-161">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="df11c-162">Para criar um novo perfil, execute o procedimento armazenado no sistema [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="df11c-162">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="df11c-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="df11c-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="df11c-164">*@profile_name*= '*Nome do perfil*'</span><span class="sxs-lookup"><span data-stu-id="df11c-164">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="df11c-165">*@description*= '*Descrição*'</span><span class="sxs-lookup"><span data-stu-id="df11c-165">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="df11c-166">em que *@profile_name* é o nome do perfil e *@description* é a descrição do perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-166">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="df11c-167">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="df11c-167">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="df11c-168">Para cada conta, execute o procedimento armazenado [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="df11c-168">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="df11c-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="df11c-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="df11c-170">*@profile_name*= '*Nome do perfil*'</span><span class="sxs-lookup"><span data-stu-id="df11c-170">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="df11c-171">*@account_name*= '*Nome da conta*'</span><span class="sxs-lookup"><span data-stu-id="df11c-171">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="df11c-172">*@sequence_number*= '*número de sequência da conta dentro do perfil.*</span><span class="sxs-lookup"><span data-stu-id="df11c-172">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="df11c-173">'</span><span class="sxs-lookup"><span data-stu-id="df11c-173">'</span></span>  
  
     <span data-ttu-id="df11c-174">em que *@profile_name* é o nome do perfil e *@account_name* é o nome da conta a ser adicionada ao perfil, *@sequence_number* determina a ordem na qual as contas são usadas no perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-174">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="df11c-175">Para conceder acesso público, execute o procedimento armazenado [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="df11c-175">To grant public access, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="df11c-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="df11c-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="df11c-177">*@profile_name*= '*Nome do perfil*'</span><span class="sxs-lookup"><span data-stu-id="df11c-177">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="df11c-178">*@ principal_name* = '**público** ou **0**'</span><span class="sxs-lookup"><span data-stu-id="df11c-178">*@ principal_name* = '**public** or **0**'</span></span>  
  
     <span data-ttu-id="df11c-179">*@is_default*= '*Status do perfil padrão* '</span><span class="sxs-lookup"><span data-stu-id="df11c-179">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="df11c-180">em que *@profile_name* é o nome do perfil, e *@principal_name* para indicar que este é um perfil público, *@is_default* determina se esse perfil é o padrão para o usuário ou função de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="df11c-180">where *@profile_name* is the name of the profile, and *@principal_name* to indicate this is a public profile, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="df11c-181">O exemplo a seguir cria uma conta do Database Mail, cria um perfil privado do Database Mail, adiciona a conta ao perfil e concede acesso público ao perfil.</span><span class="sxs-lookup"><span data-stu-id="df11c-181">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants public access to the profile.</span></span>  
  
```  
-- Create a Database Mail account  
  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Public Account',  
    @description = 'Mail account for use by all database users.',  
    @email_address = 'db_users@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @account_name = 'AdventureWorks Public Account',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to all users in the msdb database  
  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @principal_name = 'public',  
    @is_default = 1 ;  
```  
  

  
  
