---
title: Configurar um servidor de relatório para administração remota | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- WMI provider [Reporting Services], remote configuration
- configuration management [WMI]
- report servers [Reporting Services], configuring
- remote server administration [Reporting Services]
ms.assetid: 8c7f145f-3ac2-4203-8cd6-2a4694395d09
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c34db5299fc1b82a7896a41519e55466c3b3b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575607"
---
# <a name="configure-a-report-server-for-remote-administration"></a><span data-ttu-id="4d522-102">Configurar um servidor de relatório para administração remota</span><span class="sxs-lookup"><span data-stu-id="4d522-102">Configure a Report Server for Remote Administration</span></span>
  <span data-ttu-id="4d522-103">No [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você pode configurar instâncias de servidor de relatório local ou remotamente.</span><span class="sxs-lookup"><span data-stu-id="4d522-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can configure report server instances locally or remotely.</span></span> <span data-ttu-id="4d522-104">Para configurar uma instância remota do servidor de relatório, é possível usar a ferramenta Configuração do Reporting Services ou gravar código personalizado que use o provedor WMI (Instrumentação de Gerenciamento do Windows) do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d522-104">To configure a remote report server instance, you can use the Reporting Services Configuration tool or write custom code that uses the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider.</span></span> <span data-ttu-id="4d522-105">A ferramenta Configuração do Reporting Services fornece uma interface gráfica para o provedor WMI, de maneira que você possa configurar um servidor de relatório sem precisar gravar código.</span><span class="sxs-lookup"><span data-stu-id="4d522-105">The Reporting Services Configuration tool provides a graphical interface to the WMI provider so that you can configure a report server without having to write code.</span></span> <span data-ttu-id="4d522-106">Ao iniciar a ferramenta, você pode especificar um servidor remoto para se conectar.</span><span class="sxs-lookup"><span data-stu-id="4d522-106">When you start the tool, you can specify a remote server to connect to.</span></span>  
  
 <span data-ttu-id="4d522-107">Para poder usar a ferramenta para configurar um servidor de relatório remoto, siga as instruções deste tópico para habilitar portas no Firewall do Windows, conexões remotas e solicitações WMI remotas.</span><span class="sxs-lookup"><span data-stu-id="4d522-107">Before you can use the tool to configure a remote report server, you must follow the instructions in this topic to enable ports in Windows Firewall, enable remote connections, and enable remote WMI requests.</span></span>  
  
 <span data-ttu-id="4d522-108">A configuração apropriada ajuda a evitar o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="4d522-108">Proper configuration helps you avoid the following error:</span></span>  
  
 `The machine could not be found.`  
  
 `"The RPC server is unavailable. (Exception from HRESULT: 0x800706BA)".`  
  
## <a name="prerequisites"></a><span data-ttu-id="4d522-109">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="4d522-109">Prerequisites</span></span>  
 <span data-ttu-id="4d522-110">Para modificar as configurações do firewall, você deve fazer logon localmente e ser membro do grupo Administradores local.</span><span class="sxs-lookup"><span data-stu-id="4d522-110">To modify firewall settings, you must be logged on locally and you must be a member of the local Administrators group.</span></span> <span data-ttu-id="4d522-111">Não é possível modificar as configurações do firewall do Windows de um computador remoto via conexão remota.</span><span class="sxs-lookup"><span data-stu-id="4d522-111">You cannot modify the Windows firewall settings of a remote computer over a remote connection.</span></span>  
  
 <span data-ttu-id="4d522-112">Para habilitar a administração remota para um usuário que não seja administrador, você deve conceder à conta as permissões de Ativação Remota de DCOM (Distributed Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="4d522-112">If you want to enable remote administration for a non-administrator user, you must grant the account Distributed Component Object Model (DCOM) Remote Activation permissions.</span></span> <span data-ttu-id="4d522-113">As instruções sobre como configurar o servidor para acesso de não administrador estão descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4d522-113">Instructions for configuring the server for non-administrator access are provided in this topic.</span></span>  
  
 <span data-ttu-id="4d522-114">Algumas organizações têm políticas de grupo que impedem a administração remota do servidor em determinados sistemas operacionais ou para determinados usuários.</span><span class="sxs-lookup"><span data-stu-id="4d522-114">Some organizations have group policies that prevent remote server administration for certain operating systems or users.</span></span> <span data-ttu-id="4d522-115">Antes de começar a modificar as configurações do firewall, verifique com o administrador da rede se há restrições de administração remota.</span><span class="sxs-lookup"><span data-stu-id="4d522-115">Before you begin modifying firewall settings, check with your network administrator to verify whether there are restrictions on remote administration.</span></span>  
  
 <span data-ttu-id="4d522-116">Para obter mais informações, consulte [Conectando-se pelo Firewall do Windows](https://go.microsoft.com/fwlink/?LinkId=63615) na documentação do Platform SDK disponível no MSDN.</span><span class="sxs-lookup"><span data-stu-id="4d522-116">For more information, see [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) in the Platform SDK documentation on MSDN.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="4d522-117">Tarefas</span><span class="sxs-lookup"><span data-stu-id="4d522-117">Tasks</span></span>  
 <span data-ttu-id="4d522-118">As tarefas que habilitam a configuração remota do servidor de relatório incluem as seguintes:</span><span class="sxs-lookup"><span data-stu-id="4d522-118">Tasks that enable remote report server configuration include the following:</span></span>  
  
-   <span data-ttu-id="4d522-119">Habilitar portas no Firewall do Windows para permitir solicitações nas portas usadas pelo servidor de relatório e pela instância do Mecanismo de Banco de Dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4d522-119">Enable ports in Windows Firewall to allow requests on ports used by the report server and by the SQL Server Database Engine instance.</span></span>  
  
-   <span data-ttu-id="4d522-120">Habilitar conexões remotas com a instância do Mecanismo de Banco de Dados que hospeda o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4d522-120">Enable remote connections to the instance of the Database Engine instance that hosts the report server database.</span></span> <span data-ttu-id="4d522-121">Uma conexão remota é necessária para configurar a conexão com o banco de dados do servidor de relatório e gerenciar as chaves de criptografia.</span><span class="sxs-lookup"><span data-stu-id="4d522-121">A remote connection is necessary for configuring the report server database connection and managing the encryption keys.</span></span>  
  
-   <span data-ttu-id="4d522-122">Habilitar a passagem das solicitações WMI remotas pelo firewall do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="4d522-122">Enable remote WMI requests to pass through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows firewall.</span></span>  
  
-   <span data-ttu-id="4d522-123">Se você estiver configurando um servidor de relatório remoto para administração por um usuário que não seja administrador, deverá configurar permissões DCOM para habilitar o acesso WMI remoto a uma conta de usuário padrão do Windows.</span><span class="sxs-lookup"><span data-stu-id="4d522-123">If you are configuring a remote report server for administration by a non-administrative user, you must set DCOM permissions to enable remote WMI access to a standard Windows user account.</span></span> <span data-ttu-id="4d522-124">Pelo fato de a WMI usar DCOM como transporte para chamadas remotas, você deve definir as permissões do DCOM para que os usuários que não fizeram logon como administrador local possam configurar o servidor.</span><span class="sxs-lookup"><span data-stu-id="4d522-124">Because WMI uses DCOM as transport for remote calls, you must set the DCOM permissions so that users who are not logged on as the local administrator can configure the server.</span></span>  
  
-   <span data-ttu-id="4d522-125">Se você estiver configurando um servidor de relatório remoto para administração por um usuário não administrativo, também deverá configurar permissões WMI no namespace WMI do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4d522-125">If you are configuring a remote report server for administration by a non-administrative user, you must also set WMI permissions on the report server WMI namespace.</span></span> <span data-ttu-id="4d522-126">Por padrão, todos os membros do grupo Administrador local têm acesso ao namespace WMI do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="4d522-126">By default, all members of the local Administrator group have access to the report server WMI namespace.</span></span> <span data-ttu-id="4d522-127">Para conceder acesso a não administradores, você deve configurar permissões.</span><span class="sxs-lookup"><span data-stu-id="4d522-127">If you want to grant access to non-administrators, you must set permissions.</span></span>  
  
 <span data-ttu-id="4d522-128">As instruções sobre como executar essas tarefas são fornecidas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4d522-128">Instructions on how to perform these tasks are provided in this topic.</span></span>  
  
### <a name="to-open-ports-in-windows-firewall"></a><span data-ttu-id="4d522-129">Para abrir portas no Firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="4d522-129">To open ports in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="4d522-130">[Configure um firewall do Windows para acesso mecanismo de banco de dados](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span><span class="sxs-lookup"><span data-stu-id="4d522-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span></span>  
  
2.  <span data-ttu-id="4d522-131">[Configure um firewall para acesso ao servidor de relatório](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="4d522-131">[Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
### <a name="to-configure-remote-connections-to-the-report-server-database"></a><span data-ttu-id="4d522-132">Para configurar conexões remotas com o banco de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="4d522-132">To configure remote connections to the report server database</span></span>  
  
1.  <span data-ttu-id="4d522-133">Clique em **Iniciar**, aponte para **Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="4d522-133">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="4d522-134">No painel esquerdo, expanda **Configuração de Rede do SQL Server**e clique em **Protocolos** da instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d522-134">In the left pane, expand **SQL Server Network Configuration**, and then click **Protocols** for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="4d522-135">No painel de detalhes, habilite os protocolos TCP/IP e Pipes Nomeados e reinicie o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d522-135">In the details pane, enable the TCP/IP and Named Pipes protocols, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
### <a name="to-enable-remote-administration-in-windows-firewall"></a><span data-ttu-id="4d522-136">Para habilitar a administração remota no Firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="4d522-136">To enable remote administration in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="4d522-137">Faça logon como administrador local no computador para o qual deseja habilitar a administração remota.</span><span class="sxs-lookup"><span data-stu-id="4d522-137">Log on as a local administrator to the computer for which you want to enable remote administration.</span></span>  
  
2.  <span data-ttu-id="4d522-138">Se o servidor de relatório estiver em execução no Windows Vista, clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="4d522-138">If the report server is running on Windows Vista, right-click **Command Prompt** and select **Run as administrator**.</span></span> <span data-ttu-id="4d522-139">Em outros sistemas operacionais, abra uma janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4d522-139">For other operating systems, open a command prompt window.</span></span>  
  
3.  <span data-ttu-id="4d522-140">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4d522-140">Run the following command:</span></span>  
  
    ```  
    netsh.exe firewall set service type=REMOTEADMIN mode=ENABLE scope=ALL  
    ```  
  
     <span data-ttu-id="4d522-141">Você pode especificar diferentes opções para Escopo.</span><span class="sxs-lookup"><span data-stu-id="4d522-141">You can specify different options for Scope.</span></span> <span data-ttu-id="4d522-142">Para obter mais informações, consulte a documentação do Firewall do Windows.</span><span class="sxs-lookup"><span data-stu-id="4d522-142">For more information, see the Windows Firewall product documentation.</span></span>  
  
4.  <span data-ttu-id="4d522-143">Verifique se a administração remota está habilitada.</span><span class="sxs-lookup"><span data-stu-id="4d522-143">Verify that remote administration is enabled.</span></span> <span data-ttu-id="4d522-144">Você pode executar o seguinte comando para mostrar o status:</span><span class="sxs-lookup"><span data-stu-id="4d522-144">You can run the following command to show the status:</span></span>  
  
    ```  
    netsh.exe firewall show state  
    ```  
  
5.  <span data-ttu-id="4d522-145">Reinicialize o computador.</span><span class="sxs-lookup"><span data-stu-id="4d522-145">Reboot the computer.</span></span>  
  
### <a name="to-set-dcom-permissions-to-enable-remote-wmi-access-for-non-administrators"></a><span data-ttu-id="4d522-146">Para definir permissões DCOM a fim de habilitar o acesso WMI remoto para não administradores</span><span class="sxs-lookup"><span data-stu-id="4d522-146">To set DCOM permissions to enable remote WMI access for non-administrators</span></span>  
  
1.  <span data-ttu-id="4d522-147">No menu Iniciar, aponte para **Ferramentas Administrativas**e clique em **Serviços de Componentes**.</span><span class="sxs-lookup"><span data-stu-id="4d522-147">On the Start menu, point to **Administrative Tools**, click **Component Services**.</span></span>  
  
     <span data-ttu-id="4d522-148">Para o Windows Vista, no menu Iniciar, clique em **todos os programas**, clique em **executar**e, em seguida, digite `mmc comexp.msc` .</span><span class="sxs-lookup"><span data-stu-id="4d522-148">For Windows Vista, on the Start menu, click **All Programs**, click **Run**, and then enter `mmc comexp.msc`.</span></span>  
  
2.  <span data-ttu-id="4d522-149">Abra a pasta Serviços de Componentes.</span><span class="sxs-lookup"><span data-stu-id="4d522-149">Open the Component Services folder.</span></span>  
  
3.  <span data-ttu-id="4d522-150">Abra a pasta Computadores.</span><span class="sxs-lookup"><span data-stu-id="4d522-150">Open the Computers folder.</span></span>  
  
4.  <span data-ttu-id="4d522-151">Selecione Meu Computador.</span><span class="sxs-lookup"><span data-stu-id="4d522-151">Select My Computer.</span></span>  
  
5.  <span data-ttu-id="4d522-152">No menu **Ação** , selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4d522-152">On the **Action** menu, and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="4d522-153">Clique em **Segurança COM**.</span><span class="sxs-lookup"><span data-stu-id="4d522-153">Click **COM Security**.</span></span>  
  
7.  <span data-ttu-id="4d522-154">Em **Permissões de Inicialização e Ativação**, clique em **Editar Limites**.</span><span class="sxs-lookup"><span data-stu-id="4d522-154">In **Launch and Activation Permissions**, click **Edit Limits**.</span></span>  
  
8.  <span data-ttu-id="4d522-155">Caso não veja seu nome em **Permissão de Inicialização**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4d522-155">If you do not see your name in **Launch Permission**, click **Add**.</span></span>  
  
9. <span data-ttu-id="4d522-156">Digite o nome de sua conta de usuário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d522-156">Type the name of your user account, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="4d522-157">Em \*\*permissões para \<User or Group> \*\*, na coluna **permitir** , selecione **inicialização remota** e **ativação remota**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d522-157">In **Permissions for \<User or Group>**, in the **Allow** column, select **Remote Launch** and **Remote Activation**, and then click **OK**.</span></span>  
  
### <a name="to-set-permissions-on-the-report-server-wmi-namespace-for-non-administrators"></a><span data-ttu-id="4d522-158">Para definir permissões no namespace WMI do servidor de relatório para não administradores</span><span class="sxs-lookup"><span data-stu-id="4d522-158">To set permissions on the report server WMI namespace for non-administrators</span></span>  
  
1.  <span data-ttu-id="4d522-159">No menu Iniciar, aponte para **Ferramentas Administrativas**e clique em **Gerenciamento do Computador**.</span><span class="sxs-lookup"><span data-stu-id="4d522-159">On the Start menu, point to **Administrative Tools**, click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="4d522-160">Abra a pasta Serviços e Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4d522-160">Open the Services and Applications folder.</span></span>  
  
3.  <span data-ttu-id="4d522-161">Clique com o botão direito do mouse em **Controle WMI**e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4d522-161">Right-click **WMI Control**, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="4d522-162">Clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="4d522-162">Click **Security**.</span></span>  
  
5.  <span data-ttu-id="4d522-163">Abra a pasta Root.</span><span class="sxs-lookup"><span data-stu-id="4d522-163">Open the Root folder.</span></span>  
  
6.  <span data-ttu-id="4d522-164">Abra a pasta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d522-164">Open the Microsoft folder.</span></span>  
  
7.  <span data-ttu-id="4d522-165">Abra a pasta SQLServer.</span><span class="sxs-lookup"><span data-stu-id="4d522-165">Open the SQLServer folder.</span></span>  
  
8.  <span data-ttu-id="4d522-166">Abra a pasta ReportServer.</span><span class="sxs-lookup"><span data-stu-id="4d522-166">Open the ReportServer folder.</span></span>  
  
9. <span data-ttu-id="4d522-167">Abra a pasta da instância.</span><span class="sxs-lookup"><span data-stu-id="4d522-167">Open instance folder.</span></span> <span data-ttu-id="4d522-168">Se você instalou a instância padrão, a pasta será MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="4d522-168">If you installed the default instance, the folder is MSSQLSERVER.</span></span>  
  
10. <span data-ttu-id="4d522-169">Abra a pasta v10.</span><span class="sxs-lookup"><span data-stu-id="4d522-169">Open the v10 folder.</span></span>  
  
11. <span data-ttu-id="4d522-170">Selecione a pasta Admin e clique em **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="4d522-170">Select the Admin folder, and then click **Security**.</span></span>  
  
12. <span data-ttu-id="4d522-171">Clique em **Adicionar**e digite a conta de usuário que você usará para gerenciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="4d522-171">Click **Add**, and then type the user account you will use to manage the server.</span></span>  
  
13. <span data-ttu-id="4d522-172">Na coluna **Permitir** , selecione **Habilitar Conta**, **Ativação Remota**e **Ler Segurança**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d522-172">In the **Allow** column, select **Enable Account**, **Remote Enable**, and **Read Security**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d522-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d522-173">See Also</span></span>  
 [<span data-ttu-id="4d522-174">Reporting Services Configuration Manager &#40;Modo Nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="4d522-174">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
