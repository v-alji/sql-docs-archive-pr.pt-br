---
title: Habilitar ou desabilitar um protocolo de rede de servidor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], disabling
- remote connections [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], disabling using Configuration Manager
- disabling network protocols, Configuration Manager
- network protocols [SQL Server], enabling
- enabling network protocols, Configuration Manager
- surface area configuration [SQL Server], connection protocols
- connections [SQL Server], enabling remote using Configuration Manager
ms.assetid: ec5ccb69-61c9-4576-8843-014b976fd46e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 737edae84ff284ed726ade69cb48e574b830611e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680624"
---
# <a name="enable-or-disable-a-server-network-protocol"></a><span data-ttu-id="391d8-102">Habilitar ou desabilitar um protocolo de rede de servidor</span><span class="sxs-lookup"><span data-stu-id="391d8-102">Enable or Disable a Server Network Protocol</span></span>
  <span data-ttu-id="391d8-103">Todos os protocolos de rede são instalados pela Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mas podem ou não ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="391d8-103">All network protocols are installed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, but may or may not be enabled.</span></span> <span data-ttu-id="391d8-104">Este tópico descreve como habilitar ou desabilitar um protocolo de rede de servidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="391d8-104">This topic describes how to enable or disable a server network protocol in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or PowerShell.</span></span> <span data-ttu-id="391d8-105">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] deve ser interrompido e reiniciado para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="391d8-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be stopped and restarted for the change to take effect.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="391d8-106">Durante instalação do [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , é adicionado um logon para o grupo BUILTIN\Users.</span><span class="sxs-lookup"><span data-stu-id="391d8-106">During setup of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] a login is added for the BUILTIN\Users group.</span></span> <span data-ttu-id="391d8-107">Assim, todos os usuários autenticados do computador podem acessar a instância do [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] como membros da função pública.</span><span class="sxs-lookup"><span data-stu-id="391d8-107">This allows all authenticated users of the computer to access the instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] as a member of the public role.</span></span> <span data-ttu-id="391d8-108">O logon BUILTIN\Users pode ser removido com segurança para restringir o acesso a [!INCLUDE[ssDE](../../includes/ssde-md.md)] aos usuários do computador que têm logons individuais ou que são membros de outros grupos do Windows com logons.</span><span class="sxs-lookup"><span data-stu-id="391d8-108">The BUILTIN\Users login can be safely removed to restrict [!INCLUDE[ssDE](../../includes/ssde-md.md)] access to computer users who have individual logins or are members of other Windows groups with logins.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="391d8-109">Os provedores de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e [!INCLUDE[msCoName](../../includes/msconame-md.md)] para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dão suporte ao TLS 1.0 e SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="391d8-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] data providers for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support TLS 1.0 and SSL 3.0.</span></span> <span data-ttu-id="391d8-110">Se você impor um protocolo diferente (como TLS 1.1 ou TLS 1.2) fazendo alterações na camada de sistema operacional SChannel, suas conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] poderão falhar.</span><span class="sxs-lookup"><span data-stu-id="391d8-110">If you enforce a different protocol (such as TLS 1.1 or TLS 1.2) by making changes in the operating system SChannel layer, your connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might fail.</span></span>  
  
 <span data-ttu-id="391d8-111">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="391d8-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="391d8-112">**Para habilitar ou desabilitar um protocolo de rede de servidor usando:**</span><span class="sxs-lookup"><span data-stu-id="391d8-112">**To enable or disable a server network protocol using:**</span></span>  
  
     [<span data-ttu-id="391d8-113">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="391d8-113">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="391d8-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="391d8-114">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="391d8-115">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="391d8-115">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-a-server-network-protocol"></a><span data-ttu-id="391d8-116">Para habilitar um protocolo de rede de servidor</span><span class="sxs-lookup"><span data-stu-id="391d8-116">To enable a server network protocol</span></span>  
  
1.  <span data-ttu-id="391d8-117">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, no painel de console, expanda **Configuração de Rede do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="391d8-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, expand **SQL Server  Network Configuration**.</span></span>  
  
2.  <span data-ttu-id="391d8-118">No painel de console, clique em **Protocolos para** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="391d8-118">In the console pane, click **Protocols for** *\<instance name>*.</span></span>  
  
3.  <span data-ttu-id="391d8-119">No painel de detalhes, clique com o botão direito do mouse no protocolo que você quer alterar e clique em **Habilitar** ou **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="391d8-119">In the details pane, right-click the protocol you want to change, and then click **Enable** or **Disable**.</span></span>  
  
4.  <span data-ttu-id="391d8-120">No painel do console, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="391d8-120">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="391d8-121">No painel de detalhes, clique com o botão direito do mouse em **SQL Server ( ***\<instance name>*** )** e clique em **reiniciar**para parar e reiniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] serviço.</span><span class="sxs-lookup"><span data-stu-id="391d8-121">In the details pane, right-click **SQL Server (***\<instance name>***)**, and then click **Restart**, to stop and restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
##  <a name="using-sql-server-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="391d8-122">Usando o SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="391d8-122">Using SQL Server PowerShell</span></span>  
  
#### <a name="to-enable-a-server-network-protocol-using-powershell"></a><span data-ttu-id="391d8-123">Para habilitar um protocolo de rede de servidor usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="391d8-123">To Enable a Server Network Protocol Using PowerShell</span></span>  
  
1.  <span data-ttu-id="391d8-124">Usando as permissões de administrador, abra um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="391d8-124">Using administrator permissions open a command prompt.</span></span>  
  
2.  <span data-ttu-id="391d8-125">Inicie o Windows PowerShell 2.0 na barra de tarefas ou clique em Iniciar, Todos os Programas, Acessórios, Windows PowerShell e Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="391d8-125">Start Windows PowerShell 2.0 from the taskbar, or click Start, then All Programs, then Accessories, then Windows PowerShell, then Windows PowerShell.</span></span>  
  
3.  <span data-ttu-id="391d8-126">Importe o módulo **sqlps** digitando`Import-Module "sqlps"`</span><span class="sxs-lookup"><span data-stu-id="391d8-126">Import the **sqlps** module by entering `Import-Module "sqlps"`</span></span>  
  
4.  <span data-ttu-id="391d8-127">Execute as instruções a seguir para habilitar os protocolos TCP e de pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="391d8-127">Execute the following statements to enable both the TCP and named pipes protocols.</span></span> <span data-ttu-id="391d8-128">Substitua `<computer_name>` pelo nome do computador que está executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="391d8-128">Replace `<computer_name>` with the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="391d8-129">Se estiver configurando uma instância nomeada, substitua `MSSQLSERVER` pelo nome da instância.</span><span class="sxs-lookup"><span data-stu-id="391d8-129">If you are configuring a named instance, replace `MSSQLSERVER` with the instance name.</span></span>  
  
     <span data-ttu-id="391d8-130">Para desabilitar protocolos, defina as propriedades `IsEnabled` como `$false`.</span><span class="sxs-lookup"><span data-stu-id="391d8-130">To disable protocols, set the `IsEnabled` properties to `$false`.</span></span>  
  
    ```powershell
    $smo = 'Microsoft.SqlServer.Management.Smo.'  
    $wmi = new-object ($smo + 'Wmi.ManagedComputer').  
  
    # List the object properties, including the instance names.  
    $Wmi  
  
    # Enable the TCP protocol on the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    $Tcp = $wmi.GetSmoObject($uri)  
    $Tcp.IsEnabled = $true  
    $Tcp.Alter()  
    $Tcp  
  
    # Enable the named pipes protocol for the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Np']"  
    $Np = $wmi.GetSmoObject($uri)  
    $Np.IsEnabled = $true  
    $Np.Alter()  
    $Np  
    ```  
  
#### <a name="to-configure-the-protocols-for-the-local-computer"></a><span data-ttu-id="391d8-131">Para configurar os protocolos para o computador local</span><span class="sxs-lookup"><span data-stu-id="391d8-131">To configure the protocols for the local computer</span></span>  
  
-   <span data-ttu-id="391d8-132">Quando o script é executado localmente e configura o computador local, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell pode tornar o script mais flexível determinando o nome do computador local dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="391d8-132">When the script is run locally and configures the local computer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell can make the script more flexible by dynamically determining the local computer name.</span></span> <span data-ttu-id="391d8-133">Para recuperar o nome de computador local, substitua a linha que define a variável `$uri` pela linha a seguir.</span><span class="sxs-lookup"><span data-stu-id="391d8-133">To retrieve the local computer name, replace the line setting the `$uri` variable with the following line.</span></span>  
  
    ```powershell
    $uri = "ManagedComputer[@Name='" + (Get-Item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    ```  
  
#### <a name="to-restart-the-database-engine-by-using-sql-server-powershell"></a><span data-ttu-id="391d8-134">Para reiniciar o Mecanismo de Banco de Dados usando o SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="391d8-134">To restart the Database Engine by using SQL Server PowerShell</span></span>  
  
-   <span data-ttu-id="391d8-135">Depois de habilitar ou desabilitar os protocolos, você deve parar e reiniciar o [!INCLUDE[ssDE](../../includes/ssde-md.md)] para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="391d8-135">After you enable or disable protocols, you must stop and restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for the change to take effect.</span></span> <span data-ttu-id="391d8-136">Execute as instruções a seguir para parar e iniciar a instância padrão usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="391d8-136">Execute the following statements to stop and start the default instance by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span></span> <span data-ttu-id="391d8-137">Para parar e iniciar uma instância nomeada, substitua `'MSSQLSERVER'` por `'MSSQL$<instance_name>'`.</span><span class="sxs-lookup"><span data-stu-id="391d8-137">To stop and start a named instance replace `'MSSQLSERVER'` with `'MSSQL$<instance_name>'`.</span></span>  
  
    ```powershell
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\<computer_name>  
    $Wmi = (Get-Item .).ManagedComputer  
    # Get a reference to the default instance of the Database Engine.  
    $DfltInstance = $Wmi.Services['MSSQLSERVER']  
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Start the service again.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache and display the state of the service.  
    $DfltInstance.Refresh(); $DfltInstance  
    ```  
