---
title: Iniciar, parar, pausar, retomar, reiniciar o Mecanismo de Banco de Dados, SQL Server Agent ou SQL Server Browser serviço | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, start and stop services
- stopping SQL Server Agent
- parameters [SQL Server], startup options
- SQL Server, startup options
- Database Engine [SQL Server], starting and stopping services
- pausing SQL Server
- PowerShell [SQL Server], starting and stopping services
- single-user mode [SQL Server], starting in
- SQL Server Management Studio [SQL Server], starting or stopping services
- stopping SQL Server Browser service
- starting SQL Server Agent
- default instances [SQL Server], starting and stopping
- SQL Server Agent, starting and stopping
- command prompt [SQL Server], starting and stopping SQL Server services
- continuing SQL Server
- starting SQL Server Database Engine
- net stop commands [SQL Server]
- command prompt [SQL Server], SQL Browser service
- Configuration Manager, start and stop services
- resuming SQL Server
- startup options [SQL Server]
- named instances [SQL Server], starting and stopping
- net start commands [SQL Server]
- SQL Server, starting and stopping
- stopping SQL Server
- starting SQL Server Browser service
- SQL Server Database Engine setting startup options
- administering SQL Server, starting and stopping services
- Management Studio [SQL Server], starting or stopping services
ms.assetid: 32660a02-e5a1-411a-9e57-7066ca459df6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f4b102c8fd81923d7386c8e556896e715311a07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684319"
---
# <a name="start-stop-pause-resume-restart-the-database-engine-sql-server-agent-or-sql-server-browser-service"></a><span data-ttu-id="75950-102">Iniciar, parar, pausar, retomar, reiniciar o mecanismo de banco de dados, o SQL Server Agent ou o serviço SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="75950-102">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>
  <span data-ttu-id="75950-103">Este tópico descreve como iniciar, parar, pausar, retomar ou reiniciar o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente ou o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] serviço navegador do usando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , comandos **net** em um prompt de comando, [!INCLUDE[tsql](../../includes/tsql-md.md)] ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75950-103">This topic describes how to start, stop, pause, resume, or restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], **net** commands from a command prompt, [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
-   <span data-ttu-id="75950-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="75950-104">**Before you begin:**</span></span>  
  
    -   [<span data-ttu-id="75950-105">O que são estes serviços?</span><span class="sxs-lookup"><span data-stu-id="75950-105">What are these services?</span></span>](#Services)  
  
    -   [<span data-ttu-id="75950-106">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="75950-106">Additional Information</span></span>](#MoreInformation)  
  
    -   [<span data-ttu-id="75950-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="75950-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="75950-108">**Instruções usando:**</span><span class="sxs-lookup"><span data-stu-id="75950-108">**Instructions using:**</span></span>  
  
    -   [<span data-ttu-id="75950-109">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="75950-109">SQL Server Configuration Manager</span></span>](#SSCMProcedure)  
  
    -   [<span data-ttu-id="75950-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="75950-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   [<span data-ttu-id="75950-111">Comandos net em uma janela do prompt de comando</span><span class="sxs-lookup"><span data-stu-id="75950-111">net Commands from a Command Prompt window</span></span>](#CommandPrompt)  
  
    -   [<span data-ttu-id="75950-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="75950-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   [<span data-ttu-id="75950-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="75950-113">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="75950-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="75950-114">Before You Begin</span></span>  
  
###  <a name="what-is-the-ssdenoversion-service-the-ssnoversion-agent-service-and-the-ssnoversion-browser-service"></a><a name="Services"></a> <span data-ttu-id="75950-115">O que é o serviço [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser?</span><span class="sxs-lookup"><span data-stu-id="75950-115">What is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service?</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="75950-116">são programas executáveis usados como um serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="75950-116">components are executable programs that run as a Windows service.</span></span> <span data-ttu-id="75950-117">Programas executados como um serviço do Windows podem continuar operando sem exibir qualquer atividade na tela do computador.</span><span class="sxs-lookup"><span data-stu-id="75950-117">Programs that run as a Windows service can continue to operate without displaying any activity on the computer screen.</span></span>  
  
 <span data-ttu-id="75950-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)]serviço**</span><span class="sxs-lookup"><span data-stu-id="75950-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)] service**</span></span>  
 <span data-ttu-id="75950-119">O processo executável que é o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75950-119">The executable process that is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="75950-120">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] pode ser a instância padrão (limite de uma por computador) ou pode ser uma de muitas instâncias nomeadas do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75950-120">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be the default instance (limit one per computer), or can be one of many named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="75950-121">Use o Gerenciador de Configurações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para determinar quais instâncias do [!INCLUDE[ssDE](../../includes/ssde-md.md)] são instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="75950-121">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to determine which instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] are installed on the computer.</span></span> <span data-ttu-id="75950-122">A instância padrão (se você a instala) está listada como \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)\*\*.</span><span class="sxs-lookup"><span data-stu-id="75950-122">The default instance (if you install it) is listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)**.</span></span> <span data-ttu-id="75950-123">As instâncias nomeadas (se você instalá-las) são listadas como \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)\*\*.</span><span class="sxs-lookup"><span data-stu-id="75950-123">Named instances (if you install them) are listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)**.</span></span> <span data-ttu-id="75950-124">Por padrão, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o Express é instalado como \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLExpress)\*\*.</span><span class="sxs-lookup"><span data-stu-id="75950-124">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express is installed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)**.</span></span>  
  
 <span data-ttu-id="75950-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Serviço do agente**</span><span class="sxs-lookup"><span data-stu-id="75950-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service**</span></span>  
 <span data-ttu-id="75950-126">Um serviço Windows que executa tarefas administrativas agendadas, chamadas trabalhos e alertas.</span><span class="sxs-lookup"><span data-stu-id="75950-126">A Windows service that executes scheduled administrative tasks, which are called jobs and alerts.</span></span> <span data-ttu-id="75950-127">Para obter mais informações, consulte [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="75950-127">For more information, see [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="75950-128">Agent não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75950-128">Agent is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="75950-129">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="75950-129">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="75950-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Serviço browser**</span><span class="sxs-lookup"><span data-stu-id="75950-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service**</span></span>  
 <span data-ttu-id="75950-131">Um serviço Windows que escuta solicitações de entrada para recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornece informações de clientes sobre instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="75950-131">A Windows service that listens for incoming requests for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides clients information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span> <span data-ttu-id="75950-132">Uma única instância do serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser é usada para todas as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="75950-132">A single instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is used for all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer.</span></span>  
  
###  <a name="additional-information"></a><a name="MoreInformation"></a><span data-ttu-id="75950-133">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="75950-133">Additional Information</span></span>  
  
-   <span data-ttu-id="75950-134">Pausar o serviço [!INCLUDE[ssDE](../../includes/ssde-md.md)] impede que novos usuários se conectem ao [!INCLUDE[ssDE](../../includes/ssde-md.md)], mas os usuários que já estão conectados podem continuar trabalhando até que suas conexões sejam interrompidas.</span><span class="sxs-lookup"><span data-stu-id="75950-134">Pausing the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service prevents new users from connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but users who are already connected can continue to work until their connections are broken.</span></span> <span data-ttu-id="75950-135">Use a pausa quando você quiser esperar que os usuários concluam o trabalho antes de parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="75950-135">Use pause when you want to wait for users to complete work before you stop the service.</span></span> <span data-ttu-id="75950-136">Isso os permite que eles concluam as transações em andamento.</span><span class="sxs-lookup"><span data-stu-id="75950-136">This enables them to complete transactions that are in progress.</span></span> <span data-ttu-id="75950-137">Retomar permite que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] aceite novas conexões novamente.</span><span class="sxs-lookup"><span data-stu-id="75950-137">Resume allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to accept new connections again.</span></span> <span data-ttu-id="75950-138">Não é possível pausar ou retomar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service.</span><span class="sxs-lookup"><span data-stu-id="75950-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service cannot be paused or resumed.</span></span>  
  
-   <span data-ttu-id="75950-139">O Gerenciador de Configurações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] exibem o status atual dos serviços usando os ícones a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] display the current status of services by using the following icons.</span></span>  
  
     <span data-ttu-id="75950-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="75950-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager**</span></span>  
  
    -   <span data-ttu-id="75950-141">Uma seta verde no ícone próximo ao nome do serviço indica que ele foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="75950-141">A green arrow on the icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="75950-142">Um quadrado vermelho no ícone próximo ao nome do serviço indica que ele foi parado.</span><span class="sxs-lookup"><span data-stu-id="75950-142">A red square on the icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="75950-143">Duas linhas azuis verticais no ícone próximo ao nome do serviço indicam que ele foi pausado.</span><span class="sxs-lookup"><span data-stu-id="75950-143">Two vertical blue lines on the icon next to the service name indicates that the service is paused.</span></span>  
  
    -   <span data-ttu-id="75950-144">Quando o [!INCLUDE[ssDE](../../includes/ssde-md.md)]for reiniciado, um quadrado vermelho indicará que o serviço parou e uma seta verde indicará que ele foi iniciado com êxito.</span><span class="sxs-lookup"><span data-stu-id="75950-144">When restarting the [!INCLUDE[ssDE](../../includes/ssde-md.md)], a red square will indicate that the service stopped, and then a green arrow will indicate that he service started successfully.</span></span>  
  
     **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
    -   <span data-ttu-id="75950-145">Uma seta branca em um ícone de círculo verde próximo ao nome do serviço indica que ele foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="75950-145">A white arrow on a green circle icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="75950-146">Um quadrado branco nem um ícone de círculo vermelho próximo ao nome do serviço indica que ele foi parado.</span><span class="sxs-lookup"><span data-stu-id="75950-146">A white square on a red circle icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="75950-147">Duas linhas brancas verticais em um ícone de círculo azul próximo ao nome do serviço indicam que ele foi pausado.</span><span class="sxs-lookup"><span data-stu-id="75950-147">Two vertical white lines on a blue circle icon next to the service name indicates that the service is paused.</span></span>  
  
-   <span data-ttu-id="75950-148">Ao usar o Gerenciador de Configurações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], somente opções que são possíveis estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="75950-148">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], only options that are possible will be available.</span></span> <span data-ttu-id="75950-149">Por exemplo, se o serviço já foi iniciado, **Iniciar** estará indisponível.</span><span class="sxs-lookup"><span data-stu-id="75950-149">For example, if the service is already started, **Start** will be unavailable.</span></span>  
  
-   <span data-ttu-id="75950-150">Durante a execução em um cluster, o serviço [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] é gerenciador melhor com o uso do Administrador de Cluster.</span><span class="sxs-lookup"><span data-stu-id="75950-150">When running on a cluster, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service is best managed by using Cluster Administrator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="75950-151">Segurança</span><span class="sxs-lookup"><span data-stu-id="75950-151">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="75950-152">Permissões</span><span class="sxs-lookup"><span data-stu-id="75950-152">Permissions</span></span>  
 <span data-ttu-id="75950-153">Por padrão, apenas membros do grupo de administradores local podem iniciar, interromper, pausar, retomar ou reiniciar um serviço.</span><span class="sxs-lookup"><span data-stu-id="75950-153">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="75950-154">Para conceder a capacidade de gerenciar serviços a não administradores, consulte [Como conceder aos usuários direitos para gerenciar serviços no Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="75950-154">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="75950-155">(O processo é semelhante em outras versões do Windows.)</span><span class="sxs-lookup"><span data-stu-id="75950-155">(The process is similar on other versions of Windows.)</span></span>  
  
 <span data-ttu-id="75950-156">Parar o usando [!INCLUDE[ssDE](../../includes/ssde-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] `SHUTDOWN` comando requer a associação nas funções de servidor fixas **sysadmin** ou **ServerAdmin** e não é transferível.</span><span class="sxs-lookup"><span data-stu-id="75950-156">Stopping the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using the [!INCLUDE[tsql](../../includes/tsql-md.md)]`SHUTDOWN` command requires membership in the **sysadmin** or **serveradmin** fixed server roles, and is not transferable.</span></span>  
  
##  <a name="using-ssnoversion-configuration-manager"></a><a name="SSCMProcedure"></a> <span data-ttu-id="75950-157">Usando o Gerenciador de Configurações [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75950-157">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="75950-158">Para iniciar, parar, pausar, retomar ou reiniciar a instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75950-158">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="75950-159">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="75950-159">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="75950-160">(Se a caixa de diálogo **Controle de Conta de Usuário** aparecer, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="75950-160">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="75950-161">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, no painel esquerdo, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="75950-161">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="75950-162">No painel de resultados, clique com o botão direito do mouse em **SQL Server (MSSQLServer)** ou em uma instância nomeada e clique em **Iniciar**, **Parar**, **Pausar**, **Retomar**ou **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="75950-162">In the results pane, right-click **SQL Server (MSSQLServer)** or a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="75950-163">Clique em **OK** para fechar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="75950-163">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75950-164">Para iniciar uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] com opções de inicialização, consulte [Configurar opções de inicialização do servidor &#40;SQL Server Configuration Manager&#41;](scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="75950-164">To start an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with startup options, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](scm-services-configure-server-startup-options.md).</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-ssnoversion-browser-or-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="75950-165">Para iniciar, parar, pausar, retomar ou reiniciar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser ou uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="75950-165">To start, stop, pause, resume, or restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser or an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="75950-166">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="75950-166">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="75950-167">(Se a caixa de diálogo **Controle de Conta de Usuário** aparecer, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="75950-167">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="75950-168">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, no painel esquerdo, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="75950-168">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="75950-169">No painel de resultados, clique com o botão direito do mouse em \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] navegador**ou \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente (MSSQLServer)** ou \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente (<instance_name>)\*\* para uma instância nomeada e, em seguida, clique em **Iniciar**, **parar**, **Pausar**, **retomar**ou **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="75950-169">In the results pane, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser**, or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (MSSQLServer)** or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (<instance_name>)** for a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="75950-170">Clique em **OK** para fechar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="75950-170">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75950-171">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não pode ser colocado em pausa.</span><span class="sxs-lookup"><span data-stu-id="75950-171">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot be paused.</span></span>  
  
##  <a name="using-ssnoversion-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="75950-172">Usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span><span class="sxs-lookup"><span data-stu-id="75950-172">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="75950-173">Para iniciar, parar, pausar, retomar ou reiniciar a instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75950-173">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="75950-174">No Pesquisador de Objetos, conecte-se à instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)], clique com o botão direito do mouse na instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] que você deseja iniciar e clique em **Iniciar**, **Parar**, **Pausar**, **Retomar**ou **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="75950-174">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
     <span data-ttu-id="75950-175">Ou, em Servidores Registrados, clique com o botão direito do mouse na instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] que você deseja iniciar, aponte para **Controle de Serviço**e clique em **Iniciar**, **Parar**, **Pausar**, **Retomar**ou **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="75950-175">Or, in Registered Servers, right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, point to **Service Control**, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="75950-176">(Se a caixa de diálogo **Controle de Conta de Usuário** aparecer, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="75950-176">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="75950-177">Quando solicitado a indicar se você deseja executar a ação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="75950-177">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
#### <a name="to-start-stop-or-restart-the-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="75950-178">Para iniciar, parar ou reiniciar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span><span class="sxs-lookup"><span data-stu-id="75950-178">To start, stop, or restart the an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="75950-179">No Pesquisador de objetos, conecte-se à instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] , clique com o botão direito do mouse em \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agente\*\*e clique em **Iniciar**, **parar**ou **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="75950-179">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent**, and then click **Start**, **Stop**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="75950-180">(Se a caixa de diálogo **Controle de Conta de Usuário** aparecer, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="75950-180">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="75950-181">Quando solicitado a indicar se você deseja executar a ação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="75950-181">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
##  <a name="from-the-command-prompt-window-using-net-commands"></a><a name="CommandPrompt"></a><span data-ttu-id="75950-182">Na janela do prompt de comando usando comandos net</span><span class="sxs-lookup"><span data-stu-id="75950-182">From the Command Prompt Window using net Commands</span></span>  
 <span data-ttu-id="75950-183">Os serviços do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser iniciados, interrompidos ou colocados em pausa com os comandos **net** do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="75950-183">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services can be started, stopped, or paused by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **net** commands.</span></span>  
  
###  <a name="to-start-the-default-instance-of-the-ssde"></a><a name="dbDefault"></a><span data-ttu-id="75950-184">Para iniciar a instância padrão do[!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75950-184">To start the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="75950-185">Em um prompt de comando, digite um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="75950-185">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="75950-186">**net start "SQL Server (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="75950-186">**net start "SQL Server (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="75950-187">-ou-</span><span class="sxs-lookup"><span data-stu-id="75950-187">-or-</span></span>  
  
     <span data-ttu-id="75950-188">**net start MSSQLSERVER**</span><span class="sxs-lookup"><span data-stu-id="75950-188">**net start MSSQLSERVER**</span></span>  
  
###  <a name="to-start-a-named-instance-of-the-ssde"></a><a name="dbNamed"></a> <span data-ttu-id="75950-189">Para iniciar uma instância nomeada do [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75950-189">To start a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="75950-190">Em um prompt de comando, digite um dos comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-190">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="75950-191">Substitua *\<instancename>* pelo nome da instância que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="75950-191">Replace *\<instancename>* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="75950-192">**net start "SQL Server (** *instancename* **)"**</span><span class="sxs-lookup"><span data-stu-id="75950-192">**net start "SQL Server (** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="75950-193">-ou-</span><span class="sxs-lookup"><span data-stu-id="75950-193">-or-</span></span>  
  
     <span data-ttu-id="75950-194">**net start MSSQL$** *instancename*</span><span class="sxs-lookup"><span data-stu-id="75950-194">**net start MSSQL$** *instancename*</span></span>  
  
###  <a name="to-start-the-ssde-with-startup-options"></a><a name="dbStartup"></a> <span data-ttu-id="75950-195">Para iniciar o [!INCLUDE[ssDE](../../includes/ssde-md.md)] com opções de inicialização</span><span class="sxs-lookup"><span data-stu-id="75950-195">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] with startup options</span></span>  
  
-   <span data-ttu-id="75950-196">Adicione opções de inicialização ao final da instrução **net start "SQL Server (MSSQLSERVER)"** , separadas por espaço.</span><span class="sxs-lookup"><span data-stu-id="75950-196">Add startup options to the end of the **net start "SQL Server (MSSQLSERVER)"** statement, separated by a space.</span></span> <span data-ttu-id="75950-197">Quando começar usando **net start**, as opções de inicialização usam uma barra (/) em vez de um hífen (-).</span><span class="sxs-lookup"><span data-stu-id="75950-197">When started using **net start**, startup options use a slash (/) instead of a hyphen (-).</span></span>  
  
     <span data-ttu-id="75950-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span><span class="sxs-lookup"><span data-stu-id="75950-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span></span>  
  
     <span data-ttu-id="75950-199">-ou-</span><span class="sxs-lookup"><span data-stu-id="75950-199">-or-</span></span>  
  
     <span data-ttu-id="75950-200">**net start MSSQLSERVER /f /m**</span><span class="sxs-lookup"><span data-stu-id="75950-200">**net start MSSQLSERVER /f /m**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75950-201">Para obter mais informações sobre as opções de inicialização, consulte [Opções de inicialização do serviço Mecanismo de Banco de Dados](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="75950-201">For more information about startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-the-default-instance-of-ssnoversion"></a><a name="agDefault"></a> <span data-ttu-id="75950-202">Para iniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent na instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75950-202">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="75950-203">Em um prompt de comando, digite um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="75950-203">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="75950-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="75950-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="75950-205">-ou-</span><span class="sxs-lookup"><span data-stu-id="75950-205">-or-</span></span>  
  
     <span data-ttu-id="75950-206">**net start SQLSERVERAGENT**</span><span class="sxs-lookup"><span data-stu-id="75950-206">**net start SQLSERVERAGENT**</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-a-named-instance-of-ssnoversion"></a><a name="agNamed"></a> <span data-ttu-id="75950-207">Para iniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em uma instância nomeada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75950-207">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="75950-208">Em um prompt de comando, digite um dos comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-208">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="75950-209">Substitua *instancename* pelo nome da instância que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="75950-209">Replace *instancename* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="75950-210">**net start "SQL Server Agent(** *instancename* **)"**</span><span class="sxs-lookup"><span data-stu-id="75950-210">**net start "SQL Server Agent(** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="75950-211">-ou-</span><span class="sxs-lookup"><span data-stu-id="75950-211">-or-</span></span>  
  
     <span data-ttu-id="75950-212">**net start SQLAgent$** *instancename*</span><span class="sxs-lookup"><span data-stu-id="75950-212">**net start SQLAgent$** *instancename*</span></span>  
  
 <span data-ttu-id="75950-213">Para obter informações sobre como executar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em modo detalhado para solução de problemas, consulte [sqlagent90 Application](../../tools/sqlagent90-application.md).</span><span class="sxs-lookup"><span data-stu-id="75950-213">For information about how to run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in verbose mode for troubleshooting, see [sqlagent90 Application](../../tools/sqlagent90-application.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-browser"></a><a name="Browser"></a> <span data-ttu-id="75950-214">Para iniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="75950-214">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span></span>  
  
-   <span data-ttu-id="75950-215">Em um prompt de comando, digite um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="75950-215">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="75950-216">**net start "SQL Server Browser"**</span><span class="sxs-lookup"><span data-stu-id="75950-216">**net start "SQL Server Browser"**</span></span>  
  
     <span data-ttu-id="75950-217">-ou-</span><span class="sxs-lookup"><span data-stu-id="75950-217">-or-</span></span>  
  
     <span data-ttu-id="75950-218">**net start SQLBrowser**</span><span class="sxs-lookup"><span data-stu-id="75950-218">**net start SQLBrowser**</span></span>  
  
###  <a name="to-pause-or-stop-services-from-the-command-prompt-window"></a><a name="pauseStop"></a> <span data-ttu-id="75950-219">Para pausar ou parar os serviços na janela Prompt de Comando</span><span class="sxs-lookup"><span data-stu-id="75950-219">To pause or stop services from the Command Prompt window</span></span>  
  
-   <span data-ttu-id="75950-220">Para pausar ou parar serviços, modifique os comandos das maneiras a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-220">To pause or stop services modify the commands in the following ways.</span></span>  
  
    -   <span data-ttu-id="75950-221">Para pausar um serviço, substitua **net start** por **net pause**.</span><span class="sxs-lookup"><span data-stu-id="75950-221">To pause a service, replace **net start** with **net pause**.</span></span>  
  
    -   <span data-ttu-id="75950-222">Para pausar um serviço, substitua **net start** com **net pause**.</span><span class="sxs-lookup"><span data-stu-id="75950-222">To stop a service, replace **net start** with use **net stop**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="75950-223">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="75950-223">Using Transact-SQL</span></span>  
 <span data-ttu-id="75950-224">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] pode ser parado com a instrução `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="75950-224">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be stopped by using the `SHUTDOWN` statement.</span></span>  
  
#### <a name="to-stop-the-ssde-using-tsql"></a><span data-ttu-id="75950-225">Para parar o [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75950-225">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
-   <span data-ttu-id="75950-226">Para aguardar a conclusão de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] e procedimentos armazenados em execução atualmente e parar o [!INCLUDE[ssDE](../../includes/ssde-md.md)], execute a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-226">To wait for currently running [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and stored procedures to finish, and then stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)], execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN;   
    ```  
  
-   <span data-ttu-id="75950-227">Para parar o [!INCLUDE[ssDE](../../includes/ssde-md.md)] imediatamente, execute a instrução a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-227">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] immediately, execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN WITH NOWAIT;   
    ```  
  
 <span data-ttu-id="75950-228">Para obter mais informações sobre a `SHUTDOWN` instrução, consulte [Shutdown &#40;TRANSACT-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="75950-228">For more information about the `SHUTDOWN` statement, see [SHUTDOWN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="75950-229">Uso do PowerShell</span><span class="sxs-lookup"><span data-stu-id="75950-229">Using PowerShell</span></span>  
  
#### <a name="to-start-and-stop-ssde-services"></a><span data-ttu-id="75950-230">Para iniciar e parar os serviços [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75950-230">To start and stop [!INCLUDE[ssDE](../../includes/ssde-md.md)] services</span></span>  
  
1.  <span data-ttu-id="75950-231">Em uma janela Prompt de Comando, inicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-231">In a Command Prompt window, start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell by executing the following command.</span></span>  
  
    ```ms-dos  
    sqlps  
    ```  
  
2.  <span data-ttu-id="75950-232">Em um prompt de comando do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell, executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-232">At a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell command prompt, by executing the following command.</span></span> <span data-ttu-id="75950-233">Substitua `computername` pelo nome do seu computador.</span><span class="sxs-lookup"><span data-stu-id="75950-233">Replace `computername` with the name of your computer.</span></span>  
  
    ```powershell  
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\computername  
    $Wmi = (Get-Item .).ManagedComputer
    ```  
  
3.  <span data-ttu-id="75950-234">Identifique o serviço que você deseja parar ou iniciar.</span><span class="sxs-lookup"><span data-stu-id="75950-234">Identify the service that you want to stop or start.</span></span> <span data-ttu-id="75950-235">Escolha uma das linhas a seguir.</span><span class="sxs-lookup"><span data-stu-id="75950-235">Pick one of the following lines.</span></span> <span data-ttu-id="75950-236">Substitua `instancename` pelo nome da instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="75950-236">Replace `instancename` with the name of the named instance.</span></span>  
  
    -   <span data-ttu-id="75950-237">Para obter uma referência à instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75950-237">To get a reference to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQLSERVER']  
        ```  
  
    -   <span data-ttu-id="75950-238">Para obter uma referência a uma instância nomeada do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75950-238">To get a reference to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQL$instancename']  
        ```  
  
    -   <span data-ttu-id="75950-239">Para obter uma referência ao serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent na instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75950-239">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLSERVERAGENT']  
        ```  
  
    -   <span data-ttu-id="75950-240">Para obter uma referência ao serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent em uma instância nomeada do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75950-240">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLAGENT$instancename']  
        ```  
  
    -   <span data-ttu-id="75950-241">Para obter uma referência ao serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="75950-241">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLBROWSER']  
        ```  
  
4.  <span data-ttu-id="75950-242">Conclua o exemplo para iniciar e parar o serviço selecionado.</span><span class="sxs-lookup"><span data-stu-id="75950-242">Complete the example to start and then stop the selected service.</span></span>  
  
    ```powershell  
    # Display the state of the service.  
    $DfltInstance  
    # Start the service.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="75950-243">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="75950-243">See Also</span></span>  
 <span data-ttu-id="75950-244">[Iniciar SQL Server com configuração mínima](start-sql-server-with-minimal-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="75950-244">[Start SQL Server with Minimal Configuration](start-sql-server-with-minimal-configuration.md) </span></span>  
 [<span data-ttu-id="75950-245">Recursos com suporte nas edições do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="75950-245">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
