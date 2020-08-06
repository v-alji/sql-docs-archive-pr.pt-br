---
title: Exibir arquivos de log offline | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, viewing offline logs
- offline log files
ms.assetid: 9223e474-f224-4907-a4f2-081e11db58f5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2afc1992b54c78f69bfae1fc152b41c20bcd4ea1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576370"
---
# <a name="view-offline-log-files"></a><span data-ttu-id="44204-102">Exibir arquivos de log offline</span><span class="sxs-lookup"><span data-stu-id="44204-102">View Offline Log Files</span></span>
  <span data-ttu-id="44204-103">A partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], você pode exibir arquivos de log [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de uma instância local ou remota de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando a instância de destino for offline ou não inicia.</span><span class="sxs-lookup"><span data-stu-id="44204-103">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span>  
  
 <span data-ttu-id="44204-104">Você pode acessar os arquivos de log offline de Servidores Registrados, ou programaticamente por WMI e o WQL (Linguagem WQL) consulta.</span><span class="sxs-lookup"><span data-stu-id="44204-104">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44204-105">Você também pode usar estes métodos para conectar-se a uma instância que está online, mas que, por algum motivo, você não consegue se conectar por meio de uma conexão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44204-105">You can also use these methods to connect to an instance that is online, but for some reason, you cannot connect through a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="44204-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="44204-106">Before you Begin</span></span>  
 <span data-ttu-id="44204-107">Para conectar-se a arquivos de log offline, uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser instalada no computador que você está usando para exibir os arquivos de log offline, e no computador onde estão localizados os arquivos de log que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="44204-107">To connect to offline log files, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be installed on the computer that you are using to view the offline log files, and on the computer where the log files that you want to view are located.</span></span> <span data-ttu-id="44204-108">Se uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver instalada em ambos os computadores, você poderá exibir arquivos offline para instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], e para instâncias que estão executando versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em qualquer computador.</span><span class="sxs-lookup"><span data-stu-id="44204-108">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on both computers, you can view offline files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and for instances that are running earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on either computer.</span></span>  
  
 <span data-ttu-id="44204-109">Se você estiver usando os Servidores Registrados, a instância com a qual você deseja se conectar deverá estar registrada em **Grupos de Servidores Locais** ou **Servidores de Gerenciamento Central**.</span><span class="sxs-lookup"><span data-stu-id="44204-109">If you are using Registered Servers, the instance that you want to connect to must be registered under **Local Server Groups** or under **Central Management Servers**.</span></span> <span data-ttu-id="44204-110">(A instância pode ser registrada por si própria ou ser membro de um grupo de servidores.) Para obter mais informações sobre como adicionar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aos Servidores Registrados, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="44204-110">(The instance can be registered on its own or be a member of a server group.) For more information about how to add an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to Registered Servers, see the following topics:</span></span>  
  
-   [<span data-ttu-id="44204-111">Criar ou editar um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="44204-111">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="44204-112">Registrar um servidor conectado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="44204-112">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="44204-113">Criar um servidor de gerenciamento central e um grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="44204-113">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
 <span data-ttu-id="44204-114">Para obter mais informações sobre como exibir os arquivos de log offline programaticamente através de consultas WMI e WQL, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="44204-114">For more information about how to view offline log files programmatically through WMI and WQL queries, see the following topics:</span></span>  
  
-   <span data-ttu-id="44204-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (Este tópico mostra como recuperar valores para eventos registrados em um arquivo de log especificado.)</span><span class="sxs-lookup"><span data-stu-id="44204-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (This topic shows how to retrieve values for logged events in a specified log file.)</span></span>  
  
-   <span data-ttu-id="44204-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (Este tópico mostra como recuperar informações sobre todos os arquivos de log do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em uma instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="44204-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (This topic shows how to retrieve information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="44204-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="44204-117">Permissions</span></span>  
 <span data-ttu-id="44204-118">Para conectar-se a um arquivo de log offline, você deve ter as permissões a seguir nos computadores local e remoto:</span><span class="sxs-lookup"><span data-stu-id="44204-118">To connect to an offline log file, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="44204-119">Acesso de leitura ao namespace WMI **Root\Microsoft\SqlServer\ComputerManagement12** .</span><span class="sxs-lookup"><span data-stu-id="44204-119">Read access to the **Root\Microsoft\SqlServer\ComputerManagement12** WMI namespace.</span></span> <span data-ttu-id="44204-120">Por padrão, todos usuários têm acesso de leitura por meio da permissão Habilitar Conta.</span><span class="sxs-lookup"><span data-stu-id="44204-120">By default, everyone has read access through the Enable Account permission.</span></span> <span data-ttu-id="44204-121">Para obter mais informações, consulte o procedimento "Para verificar permissões de WMI" posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="44204-121">For more information, see the "To verify WMI permissions" procedure later in this section.</span></span>  
  
-   <span data-ttu-id="44204-122">Permissão de leitura para a pasta que contém os arquivos de logs de erros.</span><span class="sxs-lookup"><span data-stu-id="44204-122">Read permission to the folder that contains the error log files.</span></span> <span data-ttu-id="44204-123">Por padrão, os arquivos de logs de erros estão localizados no seguinte caminho (em que \<*Drive>\* representa a unidade na qual você instalou o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e \<*InstanceName*> é o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span><span class="sxs-lookup"><span data-stu-id="44204-123">By default the error log files are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="44204-124">**\<Drive>: \Arquivos de Programas\microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="44204-124">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="44204-125">Para verificar as configurações de segurança do namespace WMI, você pode usar o snap-in Controle WMI.</span><span class="sxs-lookup"><span data-stu-id="44204-125">To verify WMI namespace security settings, you can use the WMI Control snap-in.</span></span>  
  
#### <a name="to-verify-wmi-permissions"></a><span data-ttu-id="44204-126">Para verificar permissões do WMI</span><span class="sxs-lookup"><span data-stu-id="44204-126">To verify WMI permissions</span></span>  
  
1.  <span data-ttu-id="44204-127">Abra o snap-in Controle WMI.</span><span class="sxs-lookup"><span data-stu-id="44204-127">Open the WMI Control snap-in.</span></span> <span data-ttu-id="44204-128">Para fazer isto, execute um destes procedimentos, dependendo do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="44204-128">To do this, do either of the following, depending on the operating system:</span></span>  
  
    -   <span data-ttu-id="44204-129">Clique em **Iniciar**, digite `wmimgmt.msc` na caixa **Iniciar Pesquisa** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="44204-129">Click **Start**, type `wmimgmt.msc` in the **Start Search** box, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="44204-130">Clique em **Iniciar**, **executar**, digite `wmimgmt.msc` e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="44204-130">Click **Start**, click **Run**, type `wmimgmt.msc`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="44204-131">Por padrão, o snap-in Controle WMI gerencia o computador local.</span><span class="sxs-lookup"><span data-stu-id="44204-131">By default, the WMI Control snap-in manages the local computer.</span></span>  
  
     <span data-ttu-id="44204-132">Se você desejar conectar-se a um computador remoto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="44204-132">If you want to connect to a remote computer, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="44204-133">Clique com o botão direito do mouse em **Controle WMI (Local)** e clique em **Conectar-se a outro computador**.</span><span class="sxs-lookup"><span data-stu-id="44204-133">Right-click **WMI Control (Local)**, and then click **Connect to another computer**.</span></span>  
  
    2.  <span data-ttu-id="44204-134">Na caixa de diálogo **Alterar computador gerenciado** , clique em **Outro computador**.</span><span class="sxs-lookup"><span data-stu-id="44204-134">In the **Change managed computer** dialog box, click **Another computer**.</span></span>  
  
    3.  <span data-ttu-id="44204-135">Insira o novo nome do computador remoto e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="44204-135">Enter the remote computer name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="44204-136">Clique com o botão direito do mouse em **controle WMI (local)** ou **controle WMI (***RemoteComputerName***)** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="44204-136">Right-click **WMI Control (Local)** or **WMI Control (***RemoteComputerName***)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="44204-137">Na caixa de diálogo **Propriedades do Controle WMI** , clique na guia **Segurança** .</span><span class="sxs-lookup"><span data-stu-id="44204-137">In the **WMI Control Properties** dialog box, click the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="44204-138">Na árvore de namespace, localize e clique no seguinte namespace:</span><span class="sxs-lookup"><span data-stu-id="44204-138">In the namespace tree, locate and then click the following namespace:</span></span>  
  
     <span data-ttu-id="44204-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span><span class="sxs-lookup"><span data-stu-id="44204-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span></span>  
  
6.  <span data-ttu-id="44204-140">Clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="44204-140">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="44204-141">Verifique se a conta que será usada tem a permissão para **Habilitar Conta** .</span><span class="sxs-lookup"><span data-stu-id="44204-141">Make sure that the account that will be used has the **Enable Account** permission.</span></span> <span data-ttu-id="44204-142">Esta permissão permite acesso de leitura a objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="44204-142">This permission allows Read access to WMI objects.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="44204-143">Exibir Arquivos de Log</span><span class="sxs-lookup"><span data-stu-id="44204-143">View Log Files</span></span>  
 <span data-ttu-id="44204-144">O procedimento a seguir mostra como exibir arquivos de log offline através de Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="44204-144">The following procedure shows how to view offline log files through Registered Servers.</span></span> <span data-ttu-id="44204-145">O procedimento presume o seguinte:</span><span class="sxs-lookup"><span data-stu-id="44204-145">The procedure assumes the following:</span></span>  
  
 <span data-ttu-id="44204-146">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o qual você deseja se conectar já está registrada em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="44204-146">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to is already registered in Registered Servers.</span></span>  
  
##### <a name="to-view-log-files-for-instances-that-are-offline"></a><span data-ttu-id="44204-147">Para exibir arquivos de log para instâncias que estão offline</span><span class="sxs-lookup"><span data-stu-id="44204-147">To view log files for instances that are offline</span></span>  
  
1.  <span data-ttu-id="44204-148">Se você desejar exibir arquivos de log offline em uma instância local, tenha certeza de iniciar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] com permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="44204-148">If you want to view offline log files on a local instance, make sure that you start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] with elevated permissions.</span></span> <span data-ttu-id="44204-149">Para fazer isto, quando você iniciar o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], clique com o botão direito do mouse em **SQL Server Management Studio**e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="44204-149">To do this, when you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click **SQL Server Management Studio**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="44204-150">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="44204-150">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
3.  <span data-ttu-id="44204-151">Na árvore de console, localize a instância na qual você deseja exibir os arquivos offline.</span><span class="sxs-lookup"><span data-stu-id="44204-151">In the console tree, locate the instance on which you want to view the offline files.</span></span>  
  
4.  <span data-ttu-id="44204-152">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="44204-152">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="44204-153">Se a instância estiver em **Grupos de servidores Locais**, expanda **Grupos de servidores Locais**, expanda o grupo de servidores (se a instância for um membro de um grupo), clique com o botão direito do mouse na instância e clique em **Exibir o Log do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="44204-153">If the instance is under **Local Server Groups**, expand **Local Server Groups**, expand the server group (if the instance is a member of a group), right-click the instance, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="44204-154">Se a instância for o próprio Servidor de Gerenciamento Central, expanda **Servidores de Gerenciamento Central**, clique com o botão direito do mouse na instância, aponte para **Ações de Servidor de Gerenciamento Central**e clique em **Exibir Log do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="44204-154">If the instance is the Central Management Server itself, expand **Central Management Servers**, right-click the instance, point to **Central Management Server Actions**, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="44204-155">Se a instância estiver em **Servidores de Gerenciamento Central**, expanda **Servidores de Gerenciamento Central**, expanda o Servidor de Gerenciamento Central, clique com o botão direito do mouse na instância (ou expanda um grupo de servidores e clique com o botão direito do mouse na instância) e clique em **Exibir Log do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="44204-155">If the instance is under **Central Management Servers**, expand **Central Management Servers**, expand the Central Management Server, right-click the instance (or expand a server group and right-click the instance), and then click **View SQL Server Log**.</span></span>  
  
5.  <span data-ttu-id="44204-156">Se você estiver se conectando a uma instância local, a conexão será feita usando as credenciais de usuário atuais.</span><span class="sxs-lookup"><span data-stu-id="44204-156">If you are connecting to a local instance, the connection is made using the current user credentials.</span></span>  
  
     <span data-ttu-id="44204-157">Se você estiver se conectando a uma instância remota, na caixa de diálogo **Visualizador do Arquivo de Log – Conectar Como** , execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="44204-157">If you are connecting to a remote instance, in the **Log File Viewer - Connect As** dialog box, do either of the following:</span></span>  
  
    -   <span data-ttu-id="44204-158">Para se conectar como o usuário atual, verifique se a caixa de seleção **Conectar-se como outro usuário** está desmarcada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="44204-158">To connect as the current user, make sure that the **Connect as another user** check box is cleared, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="44204-159">Para se conectar como outro usuário, marque a caixa de seleção **Conectar-se como outro usuário** e clique em **Definir Usuário**.</span><span class="sxs-lookup"><span data-stu-id="44204-159">To connect as another user, select the **Connect as another user** check box, and then click **Set User**.</span></span> <span data-ttu-id="44204-160">Quando for solicitado, insira as credenciais de usuário (com o nome de usuário no formato *domain_name*\\*user_name*), clique em **OK**e em **OK** novamente para se conectar.</span><span class="sxs-lookup"><span data-stu-id="44204-160">When you are prompted, enter the user credentials (with the user name in the format *domain_name*\\*user_name*), click **OK**, and then click **OK** again to connect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="44204-161">Se os arquivos de log levarem muito tempo para carregar, você poderá clicar em **Parar** na barra de ferramentas do Visualizador do Arquivo de Log.</span><span class="sxs-lookup"><span data-stu-id="44204-161">If the log files take too long to load, you can click **Stop** on the Log File Viewer toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44204-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44204-162">See Also</span></span>  
 [<span data-ttu-id="44204-163">Visualizador do Arquivo de Log</span><span class="sxs-lookup"><span data-stu-id="44204-163">Log File Viewer</span></span>](log-file-viewer.md)  
  
  
