---
title: Definir a conta de inicialização do serviço para SQL Server Agent (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- startup accounts [SQL Server]
- service startup accounts [SQL Server Agent]
ms.assetid: 46ffe818-ebb5-43a0-840b-923f219a2472
author: stevestein
ms.author: sstein
ms.openlocfilehash: 63e5ba7c24f1aa1a3f79f80e5ca28c02a0cd5812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680277"
---
# <a name="set-the-service-startup-account-for-sql-server-agent-sql-server-configuration-manager"></a><span data-ttu-id="122ef-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="122ef-102">Set the Service Startup Account for SQL Server Agent (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="122ef-103">A conta de inicialização de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent define a conta do Windows como a qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é executado, bem como suas permissões de rede.</span><span class="sxs-lookup"><span data-stu-id="122ef-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account defines the Windows account that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs as, as well as its network permissions.</span></span> <span data-ttu-id="122ef-104">Este tópico descreve como definir a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="122ef-104">This topic describes how to set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="122ef-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="122ef-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="122ef-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="122ef-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="122ef-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="122ef-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="122ef-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="122ef-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="122ef-109">Para definir a conta de inicialização de serviço para o SQL Server Agent usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="122ef-109">To set the Service Startup Account for SQL Server Agent using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="122ef-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="122ef-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="122ef-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="122ef-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="122ef-112">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não exige mais que a conta de inicialização do serviço seja membro do grupo Administradores da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="122ef-112">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer requires that the service startup account be a member of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Administrators group.</span></span> <span data-ttu-id="122ef-113">No entanto, a conta de inicialização do serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser membro da função de servidor fixa [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin.</span><span class="sxs-lookup"><span data-stu-id="122ef-113">However, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service startup account must be a member of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sysadmin fixed server role.</span></span> <span data-ttu-id="122ef-114">A conta também deverá ser membro da função TargetServersRole do banco de dados msdb no servidor mestre se o processamento de trabalhos multisservidor for usado.</span><span class="sxs-lookup"><span data-stu-id="122ef-114">The account must also be a member of the msdb database role TargetServersRole on the master server if multiserver job processing is used.</span></span>  
  
-   <span data-ttu-id="122ef-115">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="122ef-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="122ef-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="122ef-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="122ef-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="122ef-117">Permissions</span></span>  
 <span data-ttu-id="122ef-118">Para executar suas funções, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser configurado para usar as credenciais de uma conta que seja membro da `sysadmin` função de servidor fixa no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="122ef-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the `sysadmin` fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="122ef-119">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="122ef-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="122ef-120">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="122ef-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="122ef-121">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="122ef-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="122ef-122">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="122ef-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="122ef-123">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="122ef-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="122ef-124">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="122ef-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="122ef-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="122ef-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-service-startup-account-for-sql-server-agent"></a><span data-ttu-id="122ef-126">Para definir a conta de inicialização do serviço do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="122ef-126">To set the Service Startup Account for SQL Server Agent</span></span>  
  
1.  <span data-ttu-id="122ef-127">Em **Servidores Registrados**, clique no sinal de adição para expandir **Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="122ef-127">In **Registered Servers**, click the plus sign to expand **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="122ef-128">Clique no sinal de adição para expandir a pasta **Grupos do Servidor Local** .</span><span class="sxs-lookup"><span data-stu-id="122ef-128">Click the plus sign to expand the **Local Server Groups** folder.</span></span>  
  
3.  <span data-ttu-id="122ef-129">Clique com o botão direito do mouse na instância de servidor na qual você deseja definir a Conta de Inicialização de Serviço e selecione **SQL Server Configuration Manager...**.</span><span class="sxs-lookup"><span data-stu-id="122ef-129">Right-click the server instance where you want set up the Service Startup Account, and select **SQL Server Configuration Manager...**.</span></span>  
  
4.  <span data-ttu-id="122ef-130">Na caixa de diálogo **Controle de Conta de Usuário**, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="122ef-130">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="122ef-131">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, no painel de console, selecione **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="122ef-131">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, select **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="122ef-132">No painel de detalhes, clique com o botão direito do mouse em **SQL Server Agent**_(server_name)_, em que *server_name* é o nome da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instância do agente para o qual você deseja alterar a conta de inicialização do serviço e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="122ef-132">In the details pane, right-click **SQL Server Agent**_(server_name)_, where *server_name* is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance for which you want to change the service startup account, and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="122ef-133">Na caixa de diálogo **Propriedades** de **SQL Server Agent**_(server_name)_ , na guia **logon** , selecione uma das seguintes opções em **fazer logon como**:</span><span class="sxs-lookup"><span data-stu-id="122ef-133">In the **SQL Server Agent**_(server_name)_ **Properties** dialog box, in the **Log On** tab, select one of the following options under **Log on as**:</span></span>  
  
    -   <span data-ttu-id="122ef-134">**Conta interna**: selecione essa opção se os trabalhos precisarem somente de recursos do servidor local.</span><span class="sxs-lookup"><span data-stu-id="122ef-134">**Built-in account**: select this option if your jobs require resources from the local server only.</span></span> <span data-ttu-id="122ef-135">Para obter informações sobre como escolher um tipo de conta interna do Windows, consulte [Seleção de uma conta para o Serviço do SQL Server Agent.](https://msdn.microsoft.com/library/ms191543.aspx)</span><span class="sxs-lookup"><span data-stu-id="122ef-135">For information about how to choose a Windows built-in account type, see [Selecting an Account for SQL Server Agent Service.](https://msdn.microsoft.com/library/ms191543.aspx)</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="122ef-136"> O serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não oferece suporte à conta **Serviço Local** no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="122ef-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service does not support the **Local Service** account in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="122ef-137">**Esta conta**: selecione essa opção se os trabalhos necessitarem de recursos de toda a rede, inclusive recursos de aplicativos; se desejar encaminhar eventos para outros logs de aplicativos do Windows; ou se desejar notificar operadores por meio de email ou pagers.</span><span class="sxs-lookup"><span data-stu-id="122ef-137">**This account**: select this option if your jobs require resources across the network, including application resources; if you want to forward events to other Windows application logs; or if you want to notify operators through e-mail or pagers.</span></span>  
  
         <span data-ttu-id="122ef-138">Se você selecionar esta opção:</span><span class="sxs-lookup"><span data-stu-id="122ef-138">If you select this option:</span></span>  
  
        1.  <span data-ttu-id="122ef-139">Na caixa **Nome da Conta** , digite a conta que será usada para executar o SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="122ef-139">In the **Account Name** box, enter the account that will be used to run SQL Server Agent.</span></span> <span data-ttu-id="122ef-140">Opcionalmente, clique em **Procurar** para abrir a caixa de usuário **Selecionar Usuário ou Grupo** e selecione a conta a ser usada.</span><span class="sxs-lookup"><span data-stu-id="122ef-140">Alternately, click **Browse** to open the **Select User or Group** dialog box and select the account to use.</span></span>  
  
        2.  <span data-ttu-id="122ef-141">Na caixa **Senha** , digite a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="122ef-141">In the **Password** box, enter the password for the account.</span></span> <span data-ttu-id="122ef-142">Digite novamente a senha na caixa **Confirmar senha** .</span><span class="sxs-lookup"><span data-stu-id="122ef-142">Re-enter the password in the **Confirm password** box.</span></span>  
  
8.  <span data-ttu-id="122ef-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="122ef-143">Click **OK**.</span></span>  
  
9. <span data-ttu-id="122ef-144">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, clique no botão **Fechar** .</span><span class="sxs-lookup"><span data-stu-id="122ef-144">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click the **Close** button.</span></span>  
  
  
