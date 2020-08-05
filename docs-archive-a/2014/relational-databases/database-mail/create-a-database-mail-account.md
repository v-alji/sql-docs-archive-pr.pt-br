---
title: Criar uma conta de email do Database Mail | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], accounts
- accounts [Database Mail]
ms.assetid: c07abbc6-fc6a-470b-8fa3-532f2e06b16a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec7d1c9147998b5a19cc0e6af13220bd64e165fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572105"
---
# <a name="create-a-database-mail-account"></a><span data-ttu-id="7c127-102">Criar uma conta do Database Mail</span><span class="sxs-lookup"><span data-stu-id="7c127-102">Create a Database Mail Account</span></span>
  <span data-ttu-id="7c127-103">Use o **Assistente para Configuração do Database Mail** ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] para criar uma conta do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="7c127-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create a Database Mail account.</span></span>  
  
-   <span data-ttu-id="7c127-104">**Antes de começar:**  [Pré-requisitos](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="7c127-104">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
-   <span data-ttu-id="7c127-105">**Para criar uma conta do Database Mail usando:**  [Assistente de Configuração do Database Mail](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="7c127-105">**To Create a Database Mail Account, using:**  [Database Mail Configuration Wizard](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="7c127-106">**Acompanhamento:**  [Próximas etapas para configurar o Database Mail](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="7c127-106">**Follow Up:**  [Next Steps to Configure the Database Mail](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7c127-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7c127-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7c127-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7c127-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="7c127-109">Determine o nome de servidor e o número de porta para o servidor de Protocolo SMTP que você usa para enviar e-mail. Se o servidor SMTP requer autenticação, determine o nome de usuário e a senha do servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="7c127-109">Determine the server name and port number for the Simple Mail Transfer Protocol (SMTP) server you use to send e-mail.If the SMTP server requires authentication, determine the user name and password for the SMTP server.</span></span>  
  
-   <span data-ttu-id="7c127-110">Opcionalmente, você também pode especificar o tipo do servidor e o número da porta para o servidor.</span><span class="sxs-lookup"><span data-stu-id="7c127-110">Optionally, you may also specify the type of the server and the port number for the server.</span></span> <span data-ttu-id="7c127-111">O tipo de servidor sempre é 'SMTP' em emails enviados.</span><span class="sxs-lookup"><span data-stu-id="7c127-111">The server type is always 'SMTP' for outgoing mail.</span></span> <span data-ttu-id="7c127-112">A maioria dos servidores SMTP usa a porta 25, a padrão.</span><span class="sxs-lookup"><span data-stu-id="7c127-112">Most SMTP servers use port 25, the default.</span></span>  
  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7c127-113">Usando o assistente para configuração do Database Mail</span><span class="sxs-lookup"><span data-stu-id="7c127-113">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="7c127-114">**Para criar uma conta do Database Mail usando um assistente**</span><span class="sxs-lookup"><span data-stu-id="7c127-114">**To create a Database Mail account using a Wizard**</span></span>  
  
-   <span data-ttu-id="7c127-115">No Pesquisador de Objetos, conecte-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser usada para configurar o Database Mail e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="7c127-115">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="7c127-116">Expanda o nó **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="7c127-116">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="7c127-117">Clique duas vezes em Database Mail para abrir o Assistente de Configuração do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="7c127-117">Double Click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="7c127-118">Na página **Selecionar Tarefa de Configuração** , selecione **Gerenciar contas e perfis do Database Mail**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7c127-118">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles**, and click **Next**.</span></span>  
  
-   <span data-ttu-id="7c127-119">Na página **Gerenciar Perfis e Contas** , selecione a opção **Criar uma nova conta** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7c127-119">On the **Manage Profiles and Accounts** page, select **Create a new account** and click **Next**.</span></span>  
  
-   <span data-ttu-id="7c127-120">Na página **Nova Conta** , especifique o nome de conta, descrição, informações de servidor de email e tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="7c127-120">On the **New Account** page, specify the account name, description, mail server information, and authentication type.</span></span> <span data-ttu-id="7c127-121">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7c127-121">Click **Next**</span></span>  
  
-   <span data-ttu-id="7c127-122">Na página **Concluir o Assistente** , examine as ações a serem executadas e clique em **Concluir** para concluir a criação da nova conta.</span><span class="sxs-lookup"><span data-stu-id="7c127-122">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new account.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7c127-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c127-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="7c127-124">**Para criar uma conta do Database Mail usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="7c127-124">**To Create a Database Mail account using Transact-SQL**</span></span>  
  
 <span data-ttu-id="7c127-125">Execute o procedimento armazenado **msdb.dbo.sysmail_add_account_sp** para criar a conta e especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="7c127-125">Execute the stored procedure **msdb.dbo.sysmail_add_account_sp** to create the account and specify the following information:</span></span>  
  
-   <span data-ttu-id="7c127-126">O nome da conta a criar.</span><span class="sxs-lookup"><span data-stu-id="7c127-126">The name of the account to create.</span></span>  
  
-   <span data-ttu-id="7c127-127">Uma descrição opcional da conta.</span><span class="sxs-lookup"><span data-stu-id="7c127-127">An optional description of the account.</span></span>  
  
-   <span data-ttu-id="7c127-128">O endereço de email a ser exibido em mensagens de email enviadas.</span><span class="sxs-lookup"><span data-stu-id="7c127-128">The e-mail address to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="7c127-129">O nome para exibição a aparecer nas mensagens de email enviadas.</span><span class="sxs-lookup"><span data-stu-id="7c127-129">The display name to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="7c127-130">O nome do servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="7c127-130">The server name of the SMTP server.</span></span>  
  
-   <span data-ttu-id="7c127-131">O nome de usuário a usar para fazer logon no servidor SMTP, se o servidor SMTP exigir autenticação.</span><span class="sxs-lookup"><span data-stu-id="7c127-131">The user name to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
-   <span data-ttu-id="7c127-132">A senha a usar para fazer logon no servidor SMTP, se o servidor SMTP exigir autenticação.</span><span class="sxs-lookup"><span data-stu-id="7c127-132">The password to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
 <span data-ttu-id="7c127-133">O exemplo a seguir cria uma nova conta do Database Mail.</span><span class="sxs-lookup"><span data-stu-id="7c127-133">The following example creates a new Database Mail account.</span></span>  
  
```  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
```  
  
##  <a name="follow-up-next-steps-to-configuring-the-database-mail"></a><a name="FollowUp"></a> <span data-ttu-id="7c127-134">Acompanhamento: Próximas etapas para configurar o Database Mail</span><span class="sxs-lookup"><span data-stu-id="7c127-134">Follow Up: Next Steps to Configuring the Database Mail</span></span>  
  
-   [<span data-ttu-id="7c127-135">Criar um perfil do Database Mail</span><span class="sxs-lookup"><span data-stu-id="7c127-135">Create a Database Mail Profile</span></span>](create-a-database-mail-profile.md)  
  
  
