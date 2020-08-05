---
title: 'Lição 1: Conectando ao Mecanismo de Banco de Dados | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e8db82f0-50ed-4531-9209-940006ed34cb
author: rothja
ms.author: jroth
ms.openlocfilehash: 6cdc53bece6bfade5fb4a0ba7d97b7bd2e921d95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572553"
---
# <a name="lesson-1-connecting-to-the-database-engine"></a><span data-ttu-id="b0450-102">Lição 1: conexão ao mecanismo de banco de dados</span><span class="sxs-lookup"><span data-stu-id="b0450-102">Lesson 1: Connecting to the Database Engine</span></span>
  <span data-ttu-id="b0450-103">Quando você instala o [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], as ferramentas instaladas dependem da edição e de suas opções de instalação.</span><span class="sxs-lookup"><span data-stu-id="b0450-103">When you install the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], the tools that are installed depend upon the edition and your setup choices.</span></span> <span data-ttu-id="b0450-104">Esta lição analisa as principais ferramentas e mostra como conectar e executar uma função básica (autorizar mais usuários).</span><span class="sxs-lookup"><span data-stu-id="b0450-104">This lesson reviews the principal tools, and shows you how to connect and perform a basic function (authorizing more users).</span></span>  
  
  
  
##  <a name="tools-for-getting-started"></a><a name="tools"></a><span data-ttu-id="b0450-105">Ferramentas para Introdução</span><span class="sxs-lookup"><span data-stu-id="b0450-105">Tools For Getting Started</span></span>  
 <span data-ttu-id="b0450-106">O [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] transporta com uma variedade de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="b0450-106">The [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] ships with a variety of tools.</span></span> <span data-ttu-id="b0450-107">Este tópico descreve as primeiras ferramentas das que você precisará e o ajuda a selecionar a ferramenta certa para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0450-107">This topic describes the first tools you will need, and helps you select the right tool for the job.</span></span> <span data-ttu-id="b0450-108">Todas as ferramentas podem ser acessadas no menu **Iniciar** .</span><span class="sxs-lookup"><span data-stu-id="b0450-108">All tools can be accessed from the **Start** menu.</span></span> <span data-ttu-id="b0450-109">Algumas ferramentas, como [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], não são instaladas por padrão.</span><span class="sxs-lookup"><span data-stu-id="b0450-109">Some tools, such as [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], are not installed by default.</span></span> <span data-ttu-id="b0450-110">Você deve selecionar as ferramentas como parte dos componentes de cliente durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="b0450-110">You must select the tools as part of the client components during setup.</span></span> <span data-ttu-id="b0450-111">Para obter uma descrição completa das ferramentas descritas abaixo, pesquise-as nos Manuais Online do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0450-111">For a complete description of the tools described below, search for them in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span> [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] <span data-ttu-id="b0450-112">contém somente um subconjunto das ferramentas.</span><span class="sxs-lookup"><span data-stu-id="b0450-112">contains only a subset of the tools.</span></span>  
  
### <a name="basic-tools"></a><span data-ttu-id="b0450-113">Ferramentas básicas</span><span class="sxs-lookup"><span data-stu-id="b0450-113">Basic Tools</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b0450-114">é a ferramenta principal para administrar o [!INCLUDE[ssDE](../includes/ssde-md.md)] e gravar o código [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0450-114">is the principal tool for administering the [!INCLUDE[ssDE](../includes/ssde-md.md)] and writing [!INCLUDE[tsql](../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="b0450-115">Fica hospedado no shell [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0450-115">It is hosted in the [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] shell.</span></span> <span data-ttu-id="b0450-116">Ele não é incluído no [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] , mas está disponível como um download separado do [Centro de Download da Microsoft](https://go.microsoft.com/fwlink/?LinkId=144346).</span><span class="sxs-lookup"><span data-stu-id="b0450-116">It is not included in [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] but is available as a separate download from [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=144346).</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="b0450-117">Configuration Manager é instalado com [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e as ferramentas de cliente.</span><span class="sxs-lookup"><span data-stu-id="b0450-117">Configuration Manager installs with both [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the client tools.</span></span> <span data-ttu-id="b0450-118">Ela permite que você habilite protocolos de servidor, configure opções de protocolo como portas de TCP, configure serviços de servidor para iniciar automaticamente e configure computadores de cliente para conectar de sua maneira preferida.</span><span class="sxs-lookup"><span data-stu-id="b0450-118">It lets you enable server protocols, configure protocol options such as TCP ports, configure server services to start automatically, and configure client computers to connect in your preferred manner.</span></span> <span data-ttu-id="b0450-119">Esta ferramenta configura os mais avançados elementos de conectividade mas não habilita recursos.</span><span class="sxs-lookup"><span data-stu-id="b0450-119">This tool configures the more advanced connectivity elements but does not enable features.</span></span>  
  
### <a name="sample-database"></a><span data-ttu-id="b0450-120">Banco de dados de exemplos</span><span class="sxs-lookup"><span data-stu-id="b0450-120">Sample Database</span></span>  
 <span data-ttu-id="b0450-121">Os bancos de dados de exemplo e os exemplos não estão incluídos no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0450-121">The sample databases and samples are not included with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b0450-122">A maioria dos exemplos descritos nos Manuais Online do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usa o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0450-122">Most of the examples that are described in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online use the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
##### <a name="to-start-sql-server-management-studio"></a><span data-ttu-id="b0450-123">Para iniciar o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0450-123">To start SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="b0450-124">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]e clique em **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="b0450-124">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
##### <a name="to-start-sql-server-configuration-manager"></a><span data-ttu-id="b0450-125">Para iniciar o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b0450-125">To start SQL Server Configuration Manager</span></span>  
  
-   <span data-ttu-id="b0450-126">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="b0450-126">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
##  <a name="connecting-with-management-studio"></a><a name="connect"></a><span data-ttu-id="b0450-127">Conectando com Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0450-127">Connecting with Management Studio</span></span>  
 <span data-ttu-id="b0450-128">É fácil de se conectar ao [!INCLUDE[ssDE](../includes/ssde-md.md)] a partir de ferramentas que estão sendo executadas no mesmo computador se você souber o nome da instância e estiver se conectando como um membro do grupo de Administradores no computador.</span><span class="sxs-lookup"><span data-stu-id="b0450-128">It is easy to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] from tools that are running on the same computer if you know the name of the instance, and if you are connecting as a member of the Administrators group on the computer.</span></span> <span data-ttu-id="b0450-129">Os procedimentos seguintes devem ser executados no mesmo computador que hospeda o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0450-129">The following procedures must be performed on the same computer that hosts [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
##### <a name="to-determine-the-name-of-the-instance-of-the-database-engine"></a><span data-ttu-id="b0450-130">Para determinar o nome da instância do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="b0450-130">To determine the name of the instance of the Database Engine</span></span>  
  
1.  <span data-ttu-id="b0450-131">Faça logon no Windows como membro do grupo Administradores e abra o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0450-131">Log into Windows as a member of the Administrators group, and open [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b0450-132">Se você estiver se conectando ao  [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] em [!INCLUDE[wiprlhlong](../includes/wiprlhlong-md.md)] ou [!INCLUDE[nextref_longhorn](../includes/nextref-longhorn-md.md)] (ou mais recente), talvez precise clicar com o botão direito do mouse em [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] e depois clicar em **Executar como Administrador** para se conectar usando suas credenciais de Administrador.</span><span class="sxs-lookup"><span data-stu-id="b0450-132">If you are connecting to  [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] on [!INCLUDE[wiprlhlong](../includes/wiprlhlong-md.md)] or [!INCLUDE[nextref_longhorn](../includes/nextref-longhorn-md.md)] (or more recent), you may need to right-click [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and then click **Run as Administrator** in order to connect using your Administrator credentials.</span></span> <span data-ttu-id="b0450-133">Começando pelo [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], a instalação acrescenta logons selecionados ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; então, suas credenciais de Administrador não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="b0450-133">Starting in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], setup adds selected logins to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], so your Administrator credentials are not necessary.</span></span>  
  
2.  <span data-ttu-id="b0450-134">Na caixa de diálogo **Conectar ao Servidor** , clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b0450-134">In the **Connect to Server** dialog box, click **Cancel**.</span></span>  
  
3.  <span data-ttu-id="b0450-135">Se Servidores Registrados não aparecer, no menu **Exibir** , clique em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="b0450-135">If Registered Servers is not displayed, on the **View** menu, click **Registered Servers**.</span></span>  
  
4.  <span data-ttu-id="b0450-136">Com **Mecanismo de Banco de Dados** selecionado na barra de ferramentas Servidores Registrados, expanda **Mecanismo do Banco de Dados**, clique com o botão direito do mouse em **Grupos do Servidor Local**, aponte para **Tarefas**e clique em **Registrar Servidores Locais**.</span><span class="sxs-lookup"><span data-stu-id="b0450-136">With **Database Engine** selected on the Registered Servers toolbar, expand **Database Engine**, right-click **Local Server Groups**, point to **Tasks**, and then click **Register Local Servers**.</span></span> <span data-ttu-id="b0450-137">São exibidas todas as instâncias do [!INCLUDE[ssDE](../includes/ssde-md.md)] instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="b0450-137">All instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] installed on the computer are displayed.</span></span> <span data-ttu-id="b0450-138">A instância padrão é sem-nome e é mostrada como o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="b0450-138">The default instance is unnamed and is shown as the computer name.</span></span> <span data-ttu-id="b0450-139">Uma instância nomeada é exibida como o nome do computador seguido de uma barra invertida (\\) e do nome da instância.</span><span class="sxs-lookup"><span data-stu-id="b0450-139">A named instance displays as the computer name followed by a backward slash (\\) and then the name of the instance.</span></span> <span data-ttu-id="b0450-140">Para o [!INCLUDE[ssExpress](../includes/ssexpress-md.md)], a instância é chamada *<computer_name>* \sqlexpress, exceto se o nome for alterado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="b0450-140">For [!INCLUDE[ssExpress](../includes/ssexpress-md.md)], the instance is named *<computer_name>* \sqlexpress unless the name was changed during setup.</span></span>  
  
##### <a name="to-verify-that-the-database-engine-is-running"></a><span data-ttu-id="b0450-141">Para verificar se o Mecanismo de Banco de Dados está sendo executado</span><span class="sxs-lookup"><span data-stu-id="b0450-141">To verify that the Database Engine is running</span></span>  
  
1.  <span data-ttu-id="b0450-142">Em Servidores Registrados, se o nome de sua instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tiver um ponto verde, com uma seta branca próximo ao nome, o [!INCLUDE[ssDE](../includes/ssde-md.md)] está sendo executado e nenhuma ação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="b0450-142">In Registered Servers, if the name of your instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has a green dot with a white arrow next to the name, the [!INCLUDE[ssDE](../includes/ssde-md.md)] is running and no further action is necessary.</span></span>  
  
2.  <span data-ttu-id="b0450-143">Se o nome de sua instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tiver um ponto vermelho, com um quadrado branco próximo ao nome, o [!INCLUDE[ssDE](../includes/ssde-md.md)] foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="b0450-143">If the name of your instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has a red dot with a white square next to the name, the [!INCLUDE[ssDE](../includes/ssde-md.md)] is stopped.</span></span> <span data-ttu-id="b0450-144">Clique com o botão direito do mouse no nome do [!INCLUDE[ssDE](../includes/ssde-md.md)], clique em **Controle de Serviços**e em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="b0450-144">Right-click the name of the [!INCLUDE[ssDE](../includes/ssde-md.md)], click **Service Control**, and then click **Start**.</span></span> <span data-ttu-id="b0450-145">Depois de uma caixa de diálogo de confirmação, o [!INCLUDE[ssDE](../includes/ssde-md.md)] deverá iniciar e o círculo deverá ficar verde com uma seta branca.</span><span class="sxs-lookup"><span data-stu-id="b0450-145">After a confirmation dialog box, the [!INCLUDE[ssDE](../includes/ssde-md.md)] should start and the circle should turn green with a white arrow.</span></span>  
  
##### <a name="to-connect-to-the-database-engine"></a><span data-ttu-id="b0450-146">Para conectar-se ao Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="b0450-146">To connect to the Database Engine</span></span>  
  
1.  <span data-ttu-id="b0450-147">No [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], no menu **Arquivo** , clique em **Conectar Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="b0450-147">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **File** menu, click **Connect Object Explorer**.</span></span>  
  
     <span data-ttu-id="b0450-148">A caixa de diálogo **Conectar ao Servidor** é exibida.</span><span class="sxs-lookup"><span data-stu-id="b0450-148">The **Connect to Server** dialog box opens.</span></span> <span data-ttu-id="b0450-149">A caixa **Tipo de servidor** exibe o tipo de componente que foi usado por último.</span><span class="sxs-lookup"><span data-stu-id="b0450-149">The **Server type** box displays the type of component that was last used.</span></span>  
  
2.  <span data-ttu-id="b0450-150">Selecione **Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="b0450-150">Select **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="b0450-151">Na caixa **Nome do servidor** , digite o nome da instância do [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0450-151">In the **Server name** box, type the name of the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="b0450-152">Para a instância padrão do SQL Server, o nome do servidor é o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="b0450-152">For the default instance of SQL Server, the server name is the computer name.</span></span> <span data-ttu-id="b0450-153">Para uma instância nomeada do SQL Server, o nome do servidor é o *<computer_name>***\\***<* instance_name>, como **ACCTG_SRVR \SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="b0450-153">For a named instance of SQL Server, the server name is the *<computer_name>***\\***<instance_name>,* such as **ACCTG_SRVR\SQLEXPRESS**.</span></span>  
  
4.  <span data-ttu-id="b0450-154">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="b0450-154">Click **Connect**.</span></span>  
  
##  <a name="authorizing-additional-connections"></a><a name="additional"></a><span data-ttu-id="b0450-155">Autorizando conexões adicionais</span><span class="sxs-lookup"><span data-stu-id="b0450-155">Authorizing Additional Connections</span></span>  
 <span data-ttu-id="b0450-156">Agora que você se conectou ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] como um administrador, uma de suas primeiras tarefas é autorizar que outros usuários se conectem.</span><span class="sxs-lookup"><span data-stu-id="b0450-156">Now that you have connected to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] as an administrator, one of your first tasks is to authorize other users to connect.</span></span> <span data-ttu-id="b0450-157">Você faz isso criando um logon e autorizando esse logon para acessar um banco de dados como um usuário.</span><span class="sxs-lookup"><span data-stu-id="b0450-157">You do this by creating a login and authorizing that login to access a database as a user.</span></span> <span data-ttu-id="b0450-158">Logons podem ser de autenticação do Windows, que usam credenciais do Windows ou logons de autenticação do SQL Server, que armazenam informações de autenticação no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e são independentes de suas credenciais do Windows.</span><span class="sxs-lookup"><span data-stu-id="b0450-158">Logins can be either Windows Authentication logins, which use credentials from Windows, or SQL Server Authentication logins, which store the authentication information in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and are independent of your Windows credentials.</span></span> <span data-ttu-id="b0450-159">Use a autenticação do Windows sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="b0450-159">Use Windows Authentication whenever possible.</span></span>  
  
##### <a name="create-a-windows-authentication-login"></a><span data-ttu-id="b0450-160">Crie um logon de autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="b0450-160">Create a Windows Authentication login</span></span>  
  
1.  <span data-ttu-id="b0450-161">Na tarefa anterior, você se conectou ao [!INCLUDE[ssDE](../includes/ssde-md.md)] usando o [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0450-161">In the previous task, you connected to the [!INCLUDE[ssDE](../includes/ssde-md.md)] using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="b0450-162">No Pesquisador de Objetos, expanda sua instância de servidor, expanda **Segurança**, clique com o botão direito do mouse em **Logons**e clique em **Novo Logon**.</span><span class="sxs-lookup"><span data-stu-id="b0450-162">In Object Explorer, expand your server instance, expand **Security**, right-click **Logins**, and then click **New Login**.</span></span>  
  
     <span data-ttu-id="b0450-163">A caixa de diálogo **Logon – Novo** é exibida.</span><span class="sxs-lookup"><span data-stu-id="b0450-163">The **Login - New** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="b0450-164">Na página **geral** , na caixa **nome de logon** , digite um logon do Windows no formato \* \<domain> \\<logon \> \*.</span><span class="sxs-lookup"><span data-stu-id="b0450-164">On the **General** page, in the **Login name** box, type a Windows login in the format *\<domain>\\<login\>*.</span></span>  
  
3.  <span data-ttu-id="b0450-165">Na caixa **Banco de dados padrão** , selecione [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , caso esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="b0450-165">In the **Default database** box, select [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] if available.</span></span> <span data-ttu-id="b0450-166">Caso contrário, selecione **mestre**.</span><span class="sxs-lookup"><span data-stu-id="b0450-166">Otherwise select **master**.</span></span>  
  
4.  <span data-ttu-id="b0450-167">Na página **Funções do Servidor** , se o novo logon for um administrador, clique em **sysadmin**; caso contrário, deixe este espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="b0450-167">On the **Server Roles** page, if the new login is to be an administrator, click **sysadmin**, otherwise leave this blank.</span></span>  
  
5.  <span data-ttu-id="b0450-168">Na página **Mapeamento de Usuário** , selecione **Mapa** para o banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , caso ele esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="b0450-168">On the **User Mapping** page, select **Map** for the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database if it is available.</span></span> <span data-ttu-id="b0450-169">Caso contrário, selecione **mestre**.</span><span class="sxs-lookup"><span data-stu-id="b0450-169">Otherwise select **master**.</span></span> <span data-ttu-id="b0450-170">Observe que a caixa **Usuário** é populada com o logon.</span><span class="sxs-lookup"><span data-stu-id="b0450-170">Note that the **User** box is populated with the login.</span></span> <span data-ttu-id="b0450-171">Depois de fechada, a caixa de diálogo criará esse usuário no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b0450-171">When closed, the dialog box will create this user in the database.</span></span>  
  
6.  <span data-ttu-id="b0450-172">Na caixa **Esquema Padrão** , digite **dbo** para mapear o logon para o esquema de proprietário de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b0450-172">In the **Default Schema** box, type **dbo** to map the login to the database owner schema.</span></span>  
  
7.  <span data-ttu-id="b0450-173">Aceite as configurações padrão nas caixas **Protegíveis** e **Status** e clique em **OK** para criar o logon.</span><span class="sxs-lookup"><span data-stu-id="b0450-173">Accept the default settings for the **Securables** and **Status** boxes and click **OK** to create the login.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b0450-174">Essas são as informações básicas para começar.</span><span class="sxs-lookup"><span data-stu-id="b0450-174">This is basic information to get you started.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="b0450-175">fornece um ambiente de segurança avançado e a segurança é obviamente um aspecto importante das operações de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b0450-175">provides a rich security environment, and security is obviously an important aspect of database operations.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b0450-176">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="b0450-176">Next Lesson</span></span>  
 [<span data-ttu-id="b0450-177">Lição 2: Conectando de outro computador</span><span class="sxs-lookup"><span data-stu-id="b0450-177">Lesson 2: Connecting from Another Computer</span></span>](lesson-2-connecting-from-another-computer.md)  
  
  