---
title: Definir a conta de serviço para o Iniciador do Daemon de Filtro de Texto Completo | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text search [SQL Server], FDHOST Launcher (MSSQLFDLauncher) service account
- FDHOST Launcher (MSSQLFDLauncher) [SQL Server]
ms.assetid: 3ab1d101-7ae0-488f-9b57-468e2517b737
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d69e68f0b00e760c4b11d1f842f22911ac8dd2c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570582"
---
# <a name="set-the-service-account-for-the-full-text-filter-daemon-launcher"></a><span data-ttu-id="a52b8-102">Definir a conta de serviço do Iniciador do Daemon de Filtro de Texto Completo</span><span class="sxs-lookup"><span data-stu-id="a52b8-102">Set the Service Account for the Full-text Filter Daemon Launcher</span></span>
  <span data-ttu-id="a52b8-103">Este tópico descreve como definir a conta do serviço Iniciador do Daemon de Filtro de Texto Completo do SQL (MSSQLFDLauncher) usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a52b8-103">This topic describes how to set the service account for the SQL Full-text Filter Daemon Launcher service (MSSQLFDLauncher) by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="a52b8-104">O serviço Iniciador do Daemon do Filtro de Texto Completo do SQL é usado pela pesquisa de texto completo ssNoVersion para iniciar o processo do host do daemon de filtro, que manipula a filtragem da pesquisa de texto completo e a quebra de palavras.</span><span class="sxs-lookup"><span data-stu-id="a52b8-104">The SQL Full-text Filter Daemon Launcher service is used by full-text search ssNoVersionto start the filter daemon host process, which handles full-text search filtering and word breaking.</span></span> <span data-ttu-id="a52b8-105">Esse serviço deve estar em execução para usar a pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a52b8-105">This service must be running to use full-text search.</span></span>  
  
 <span data-ttu-id="a52b8-106">O Iniciador do Daemon de Filtro de Texto Completo do SQL é um serviço de reconhecimento de instâncias associado a uma instância específica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a52b8-106">The SQL Full-text Filter Daemon Launcher service is an instance-aware service that is associated with a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a52b8-107">O serviço Iniciador do Daemon de Filtro de Texto Completo do SQL propaga as informações da conta de serviço para cada processo do host do daemon de filtro.</span><span class="sxs-lookup"><span data-stu-id="a52b8-107">The SQL Full-text Filter Daemon Launcher service propagates the service account information to each filter daemon host process.</span></span>  
  
  
##  <a name="setting-the-service-account"></a><a name="setting"></a><span data-ttu-id="a52b8-108">Configurando a conta de serviço</span><span class="sxs-lookup"><span data-stu-id="a52b8-108">Setting the Service Account</span></span>  
  
#### <a name="to-set-the-sql-full-text-filter-daemon-launcher-service-account-for-full-text-search"></a><span data-ttu-id="a52b8-109">Para definir a conta do serviço Iniciador do Daemon de Filtro de Texto Completo do SQL para pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="a52b8-109">To set the SQL Full-text Filter Daemon Launcher service account for full-text search</span></span>  
  
1.  <span data-ttu-id="a52b8-110">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="a52b8-110">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="a52b8-111">Em **SQL Server Configuration Manager**, clique em **serviços SQL Server**, clique com o botão direito do mouse em **iniciador do daemon de filtro de texto completo do SQL ( *`instance name`* )** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a52b8-111">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click **SQL Full-text Filter Daemon Launcher (*`instance name`*)**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="a52b8-112">Clique na guia **Fazer Logon** da caixa de diálogo e selecione ou digite a conta em que será executado cada processo criado pelo serviço Iniciador do Daemon de Filtro de Texto Completo do SQL.</span><span class="sxs-lookup"><span data-stu-id="a52b8-112">Click the **Log On** tab of the dialog box, and then select or enter the account under which to run each process created by the SQL Full-text Filter Daemon Launcher service.</span></span>  
  
4.  <span data-ttu-id="a52b8-113">Depois que você fechar a caixa de diálogo, clique em **Reiniciar** para reiniciar o serviço Iniciador do Daemon de Filtro de Texto Completo do SQL.</span><span class="sxs-lookup"><span data-stu-id="a52b8-113">After you close the dialog box, click **Restart** to restart the SQL Full-text Filter Daemon Launcher service.</span></span>  
  
  
##  <a name="if-the-sql-full-text-filter-daemon-launcher-service-does-not-start"></a><a name="error"></a><span data-ttu-id="a52b8-114">Se o serviço de Iniciador do Daemon de Filtro de Texto Completo do SQL não iniciar</span><span class="sxs-lookup"><span data-stu-id="a52b8-114">If the SQL Full-text Filter Daemon Launcher Service Does Not Start</span></span>  
 <span data-ttu-id="a52b8-115">Se o serviço Iniciador do Daemon de Filtro de Texto Completo do SQL não for iniciado, o motivo poderá ser uma ou mais das seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="a52b8-115">If the SQL Full-text Filter Daemon Launcher service does not start, one or more of the following might be the cause:</span></span>  
  
-   <span data-ttu-id="a52b8-116">A senha associada à conta do serviço Iniciador do Daemon de Filtro de Texto Completo do SQL expirou.</span><span class="sxs-lookup"><span data-stu-id="a52b8-116">The password associated with the SQL Full-text Filter Daemon Launcher service account has expired.</span></span>  
  
     <span data-ttu-id="a52b8-117">Se você utiliza uma conta de usuário local para o serviço Iniciador do Daemon de Filtro de Texto Completo do SQL e a senha expirar, será necessário.</span><span class="sxs-lookup"><span data-stu-id="a52b8-117">If you use a local user account for the SQL Full-text Filter Daemon Launcher service and your password expires, you need to:</span></span>  
  
    1.  <span data-ttu-id="a52b8-118">Definir uma nova senha do Windows para a conta.</span><span class="sxs-lookup"><span data-stu-id="a52b8-118">Set a new Windows password for the account.</span></span>  
  
    2.  <span data-ttu-id="a52b8-119">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, atualize o serviço Iniciador do Daemon de Filtro de Texto Completo do SQL para usar a nova senha.</span><span class="sxs-lookup"><span data-stu-id="a52b8-119">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, update the SQL Full-text Filter Daemon Launcher service to use the new password.</span></span>  
  
-   <span data-ttu-id="a52b8-120">A conta de usuário ou a senha da conta de serviço está incorreta.</span><span class="sxs-lookup"><span data-stu-id="a52b8-120">The user account or password of the service account is incorrect.</span></span>  
  
     <span data-ttu-id="a52b8-121">O serviço Iniciador do Daemon de Filtro de Texto Completo do SQL pode tentar fazer logon com uma conta de usuário e senha incorretas.</span><span class="sxs-lookup"><span data-stu-id="a52b8-121">The SQL Full-text Filter Daemon Launcher service might attempt to log in with an incorrect user account and password.</span></span> <span data-ttu-id="a52b8-122">Siga os procedimentos anteriores para verificar se a conta de usuário para o serviço não foi alterada.</span><span class="sxs-lookup"><span data-stu-id="a52b8-122">Follow the procedures above to verify that the user account for the service has not been changed.</span></span>  
  
-   <span data-ttu-id="a52b8-123">A conta usada para fazer logon no serviço não possui privilégios.</span><span class="sxs-lookup"><span data-stu-id="a52b8-123">The account used to log in to the service does not have privileges.</span></span>  
  
     <span data-ttu-id="a52b8-124">Talvez você esteja usando uma conta que não possui privilégios de logon no computador em que está instalada a instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="a52b8-124">You might be using an account that does not have login privileges on the computer where the server instance is installed.</span></span> <span data-ttu-id="a52b8-125">Verifique se está fazendo o logon com uma conta que possua direitos e permissões de Usuário no computador local.</span><span class="sxs-lookup"><span data-stu-id="a52b8-125">Verify that you are logging in with an account that has User rights and permissions on the local computer.</span></span>  
  
-   <span data-ttu-id="a52b8-126">Outra instância do mesmo pipe nomeado já está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="a52b8-126">Another instance of the same named pipe is already running.</span></span>  
  
     <span data-ttu-id="a52b8-127">Os serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atua como um servidor de pipe nomeado para o cliente do serviço Iniciador do Daemon de Filtro de Texto Completo do SQL.</span><span class="sxs-lookup"><span data-stu-id="a52b8-127">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service acts as a named pipe server for the SQL Full-text Filter Daemon Launcher service client.</span></span> <span data-ttu-id="a52b8-128">Se o pipe nomeado já foi criado por outro processo antes de o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ser iniciado, um erro será registrado no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e no Log de Eventos do Windows, e a pesquisa de texto completo não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="a52b8-128">If the named pipe was already created by another process before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts, an error will be logged in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the Windows Event Log, and full-text search will not be available.</span></span>  <span data-ttu-id="a52b8-129">Determine qual processo ou aplicativo está tentando usar o mesmo pipe nomeado e interrompa o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a52b8-129">Determine what process or application is attempting to use the same named pipe and stop the application.</span></span>  
  
-   <span data-ttu-id="a52b8-130">O serviço Iniciador do Daemon de Filtro de Texto Completo do SQL não está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="a52b8-130">The SQL Full-text Filter Daemon Launcher service is not configured correctly.</span></span>  
  
     <span data-ttu-id="a52b8-131">O serviço pode não estar configurado corretamente no computador local.</span><span class="sxs-lookup"><span data-stu-id="a52b8-131">The service may not be configured correctly on the local computer.</span></span>  
  
     <span data-ttu-id="a52b8-132">Se a funcionalidade de pipes nomeados foi desabilitada no computador local ou se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi configurado para usar um pipe nomeado diferente do padrão, é possível que o serviço Iniciador do Daemon de Filtro de Texto Completo do SQL não seja iniciado.</span><span class="sxs-lookup"><span data-stu-id="a52b8-132">If named pipes functionality has been disabled on the local computer, or if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been configured to use a named pipe other than the default named pipe, the SQL Full-text Filter Daemon Launcher service might not start.</span></span>  
  
-   <span data-ttu-id="a52b8-133">O grupo de serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não tem permissão para iniciar o serviço Iniciador do Daemon de Filtro de Texto Completo do SQL.</span><span class="sxs-lookup"><span data-stu-id="a52b8-133">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service group does not have permission to start SQL Full-text Filter Daemon Launcher service.</span></span>  
  
     <span data-ttu-id="a52b8-134">Durante a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é concedido ao grupo de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissão padrão para gerenciar, consultar e iniciar o serviço Iniciador do Daemon de Filtro de Texto Completo do SQL.</span><span class="sxs-lookup"><span data-stu-id="a52b8-134">During the installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service group is granted default permission to manage, query, and start the SQL Full-text Filter Daemon Launcher service.</span></span> <span data-ttu-id="a52b8-135">Se as permissões do grupo de serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a conta de serviço Iniciador do Daemon de Filtro de Texto Completo do SQL tiverem sido removidas após a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o serviço Iniciador do Daemon de Filtro de Texto Completo do SQL não será iniciado e a pesquisa de texto completo será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a52b8-135">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service group permissions to the SQL Full-text Filter Daemon Launcher service account have been removed after [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation, the SQL Full-text Filter Daemon Launcher service will not start, and full-text search will be disabled.</span></span> <span data-ttu-id="a52b8-136">Certifique-se de que o grupo de serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tenha permissões na conta de serviço Iniciador do Daemon de Filtro de Texto Completo do SQL.</span><span class="sxs-lookup"><span data-stu-id="a52b8-136">Make certain the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service group has permissions to the SQL Full-text Filter Daemon Launcher service account.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="a52b8-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a52b8-137">See Also</span></span>  
 [<span data-ttu-id="a52b8-138">Tópicos de instruções sobre gerenciamento de serviços &#40;SQL Server Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="a52b8-138">Managing Services How-to Topics &#40;SQL Server Configuration Manager&#41;</span></span>](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md)  
 [<span data-ttu-id="a52b8-139">Atualizar pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="a52b8-139">Upgrade Full-Text Search</span></span>](upgrade-full-text-search.md)  
  
  