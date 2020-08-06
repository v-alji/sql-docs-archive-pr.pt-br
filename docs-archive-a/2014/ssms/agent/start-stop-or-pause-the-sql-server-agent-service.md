---
title: Iniciar, parar ou pausar o serviço do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, starting
- SQL Server Agent, pausing
- SQL Server Agent, stopping
ms.assetid: c95a9759-dd30-4ab6-9ab0-087bb3bfb97c
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2feb6a18c602271b1bec871fbfc9793979b100e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678560"
---
# <a name="start-stop-or-pause-the-sql-server-agent-service"></a><span data-ttu-id="37e6a-102">Start, Stop, or Pause the SQL Server Agent Service</span><span class="sxs-lookup"><span data-stu-id="37e6a-102">Start, Stop, or Pause the SQL Server Agent Service</span></span>
  <span data-ttu-id="37e6a-103">Este tópico descreve como iniciar, parar reiniciar o Serviço SQL Server Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37e6a-103">This topic describes how to start, stop, or restart the SQL Server Agent Service in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="37e6a-104">É possível configurar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para que se inicie automaticamente quando o sistema operacional for iniciado, mas você também poderá iniciá-lo manualmente quando precisar concluir trabalhos.</span><span class="sxs-lookup"><span data-stu-id="37e6a-104">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically when the operating system starts, or you can start it manually when you need to complete jobs.</span></span> <span data-ttu-id="37e6a-105">Você pode interromper ou pausar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para suspender trabalhos, notificações de operador e alertas.</span><span class="sxs-lookup"><span data-stu-id="37e6a-105">You can stop or pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to suspend jobs, operator notifications, and alerts.</span></span>  
  
 <span data-ttu-id="37e6a-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="37e6a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="37e6a-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="37e6a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="37e6a-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="37e6a-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="37e6a-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="37e6a-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="37e6a-110">Para iniciar, parar ou reiniciar o Serviço SQL Server Agent usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37e6a-110">To start, stop, or restart the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="37e6a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="37e6a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="37e6a-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="37e6a-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="37e6a-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]O Agent deve estar em execução como um serviço para automatizar tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="37e6a-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running as a service in order to automate administrative tasks.</span></span> <span data-ttu-id="37e6a-114">Para obter mais informações, consulte [Configure SQL Server Agent](configure-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="37e6a-114">For more information, see [Configure SQL Server Agent](configure-sql-server-agent.md).</span></span>  
  
-   <span data-ttu-id="37e6a-115">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="37e6a-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="37e6a-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="37e6a-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="37e6a-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="37e6a-117">Permissions</span></span>  
 <span data-ttu-id="37e6a-118">Para executar suas funções, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve ser configurado de modo a usar as credenciais de uma conta que seja membro da função de servidor fixa **sysadmin** no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37e6a-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="37e6a-119">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="37e6a-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="37e6a-120">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="37e6a-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="37e6a-121">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="37e6a-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="37e6a-122">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="37e6a-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="37e6a-123">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="37e6a-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="37e6a-124">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="37e6a-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="37e6a-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37e6a-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-stop-or-restart-the-sql-server-agent-service"></a><span data-ttu-id="37e6a-126">Para iniciar, parar ou reiniciar o Serviço SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="37e6a-126">To start, stop, or restart the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="37e6a-127">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja gerenciar o Serviço SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="37e6a-127">In **Object Explorer**, click the plus sign to expand the server where you want to manage SQL Server Agent Service.</span></span>  
  
2.  <span data-ttu-id="37e6a-128">Clique com o botão direito do mouse em **SQL Server Agent**e selecione **Iniciar**, **Parar**ou **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="37e6a-128">Right-click **SQL Server Agent**, and then select either **Start**, **Stop**, or **Restart**.</span></span>  
  
3.  <span data-ttu-id="37e6a-129">Na caixa de diálogo **Controle de Conta de Usuário**, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="37e6a-129">In the **User Account Control** dialog box, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="37e6a-130">Quando solicitado a indicar se você deseja executar a ação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="37e6a-130">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
 <span data-ttu-id="37e6a-131">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="37e6a-131">For more information, see:</span></span>  
  
-   [<span data-ttu-id="37e6a-132">Iniciar, parar, pausar, retomar, reiniciar o mecanismo de banco de dados, o SQL Server Agent ou o serviço SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="37e6a-132">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
-   [<span data-ttu-id="37e6a-133">Iniciar automaticamente o SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="37e6a-133">Autostart SQL Server Agent &#40;SQL Server Management Studio&#41;</span></span>](autostart-sql-server-agent-sql-server-management-studio.md)  
  
  
