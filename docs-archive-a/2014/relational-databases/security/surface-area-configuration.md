---
title: Configuração da área de superfície | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- reducing attackable surface area
- upgrading SQL Server, security
- surface area configuration [SQL Server]
- surface area configuration [SQL Server], about surface area configuration
- attackable surface area [SQL Server]
- installing SQL Server, security
ms.assetid: f741169c-1453-4ad2-830b-bf2be27d712f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ef64fbbeb2b8953ff3816db63572b499d42f012e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679766"
---
# <a name="surface-area-configuration"></a><span data-ttu-id="f73a7-102">Configuração da Área de Superfície</span><span class="sxs-lookup"><span data-stu-id="f73a7-102">Surface Area Configuration</span></span>
  <span data-ttu-id="f73a7-103">Na configuração padrão de novas instalações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], muitos recursos não estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="f73a7-103">In the default configuration of new installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], many features are not enabled.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f73a7-104">instala e inicia seletivamente somente os serviços e recursos principais, para reduzir o número de recursos que podem ser atacados por um usuário mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="f73a7-104">selectively installs and starts only key services and features, to minimize the number of features that can be attacked by a malicious user.</span></span> <span data-ttu-id="f73a7-105">Um administrador de sistema pode alterar esses padrões no momento da instalação e também seletivamente habilitar ou desabilitar recursos de uma instância em execução do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f73a7-105">A system administrator can change these defaults at installation time and also selectively enable or disable features of a running instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f73a7-106">Além disso, alguns componentes podem não estar disponíveis ao estabelecer conexão a partir de outros computadores até que os protocolos sejam configurados.</span><span class="sxs-lookup"><span data-stu-id="f73a7-106">Additionally, some components may not be available when connecting from other computers until protocols are configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f73a7-107">Ao contrário das novas instalações, nenhum serviço ou recurso existente é desativado durante uma atualização, mas as opções adicionais de configuração da área da superfície poderão ser aplicadas após a conclusão da atualização.</span><span class="sxs-lookup"><span data-stu-id="f73a7-107">Unlike new installations, no existing services or features are turned off during an upgrade, but additional surface area configuration options can be applied after the upgrade is completed.</span></span>  
  
## <a name="protocols-connection-and-startup-options"></a><span data-ttu-id="f73a7-108">Protocolos, conexão e opções de inicialização</span><span class="sxs-lookup"><span data-stu-id="f73a7-108">Protocols, Connection, and Startup Options</span></span>  
 <span data-ttu-id="f73a7-109">Use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para iniciar e interromper serviços, configurar opções de inicialização e habilitar protocolos e outras opções de conexão.</span><span class="sxs-lookup"><span data-stu-id="f73a7-109">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to start and stop services, configure the startup options, and enable protocols and other connection options.</span></span>  
  
#### <a name="to-start-sql-server-configuration-manager"></a><span data-ttu-id="f73a7-110">Para iniciar o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f73a7-110">To start SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="f73a7-111">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="f73a7-111">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    -   <span data-ttu-id="f73a7-112">Use a área **Serviços do SQL Server** para iniciar componentes e configurar as opções de inicialização automática.</span><span class="sxs-lookup"><span data-stu-id="f73a7-112">Use the **SQL Server Services** area to start components and configure the automatic starting options.</span></span>  
  
    -   <span data-ttu-id="f73a7-113">Use a área **Configuração de Rede do SQL Server** para habilitar protocolos de conexão e opções de conexão, como portas TCP/IP fixas, ou forçar a criptografia.</span><span class="sxs-lookup"><span data-stu-id="f73a7-113">Use the **SQL Server Network Configuration** area to enable connection protocols, and connection options such as fixed TCP/IP ports, or forcing encryption.</span></span>  
  
 <span data-ttu-id="f73a7-114">Para obter mais informações, consulte [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f73a7-114">For more information, see [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span></span> <span data-ttu-id="f73a7-115">A conectividade remota também pode depender da configuração correta de um firewall.</span><span class="sxs-lookup"><span data-stu-id="f73a7-115">Remote connectivity can also depend upon the correct configuration of a firewall.</span></span> <span data-ttu-id="f73a7-116">Para obter mais informações sobre como fazer isso, veja [Configurar o Firewall do Windows para permitir acesso ao SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="f73a7-116">For more information, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
## <a name="enabling-and-disabling-features"></a><span data-ttu-id="f73a7-117">Habilitando e desabilitando recursos</span><span class="sxs-lookup"><span data-stu-id="f73a7-117">Enabling and Disabling Features</span></span>  
 <span data-ttu-id="f73a7-118">A habilitação e desabilitação de recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser configuradas usando as facetas no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f73a7-118">Enabling and disabling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features can be configured using facets in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-configure-surface-area-using-facets"></a><span data-ttu-id="f73a7-119">Para configurar área da superfície usando as facetas</span><span class="sxs-lookup"><span data-stu-id="f73a7-119">To configure surface area using facets</span></span>  
  
1.  <span data-ttu-id="f73a7-120">No [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , conecte-se ao componente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f73a7-120">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] connect to a component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="f73a7-121">No Pesquisador de Objetos, clique com o botão direito do mouse no servidor e clique em **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="f73a7-121">In Object Explorer, right-click the server, and then click **Facets**.</span></span>  
  
3.  <span data-ttu-id="f73a7-122">Na caixa de diálogo **Exibir Facetas** , expanda a lista **Faceta** e selecione a faceta **Configuração da Área da Superfície** apropriada (**Configuração da Área da Superfície**, **Configuração da Área da Superfície para o Analysis Services**ou **Configuração da Área da Superfície para o Reporting Services**).</span><span class="sxs-lookup"><span data-stu-id="f73a7-122">In the **View Facets** dialog box, expand the **Facet** list, and select the appropriate **Surface Area Configuration** facet (**Surface Area Configuration**, **Surface Area Configuration for Analysis Services**, or **Surface Area Configuration for Reporting Services**).</span></span>  
  
4.  <span data-ttu-id="f73a7-123">Na área **Propriedades da faceta** , selecione os valores desejados para cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="f73a7-123">In the **Facet properties** area, select the values that you want for each property.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="f73a7-124">Para verificar a configuração de uma faceta periodicamente, use o Gerenciamento Baseado em Política.</span><span class="sxs-lookup"><span data-stu-id="f73a7-124">To periodically check the configuration of a facet, use Policy-Based Management.</span></span> <span data-ttu-id="f73a7-125">Para obter mais informações sobre o gerenciamento baseado em políticas, veja [Administrar servidores usando o gerenciamento baseado em políticas](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="f73a7-125">For more information about Policy-Based Management, see [Administer Servers by Using Policy-Based Management](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="f73a7-126">Você também pode definir opções do [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando o procedimento armazenado `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="f73a7-126">You can also set [!INCLUDE[ssDE](../../includes/ssde-md.md)] options using the `sp_configure` stored procedure.</span></span> <span data-ttu-id="f73a7-127">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f73a7-127">For more information, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
 <span data-ttu-id="f73a7-128">Para alterar a propriedade **EnableIntegrated Security** do [!INCLUDE[ssRS](../../includes/ssrs.md)], use as configurações de propriedades no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f73a7-128">To change the **EnableIntegrated Security** property of [!INCLUDE[ssRS](../../includes/ssrs.md)], use the property settings in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f73a7-129">Para alterar as propriedades **Eventos de agendamento e entrega de relatório** e **Serviço Web e acesso HTTP** , edite o arquivo de configuração **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="f73a7-129">To change the **Schedule events and report delivery** property and the **Web service and HTTP access** property, edit the **RSReportServer.config** configuration file.</span></span>  
  
## <a name="command-prompt-options"></a><span data-ttu-id="f73a7-130">Opções do prompt de comando</span><span class="sxs-lookup"><span data-stu-id="f73a7-130">Command-prompt Options</span></span>  
 <span data-ttu-id="f73a7-131">Use o cmdlet **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do PowerShell para invocar as Políticas de Configuração da Área da Superfície.</span><span class="sxs-lookup"><span data-stu-id="f73a7-131">Use the **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell cmdlet to invoke Surface Area Configuration Policies.</span></span> <span data-ttu-id="f73a7-132">Para obter mais informações, veja [Usar os cmdlets do Mecanismo de Banco de Dados](../../database-engine/use-the-database-engine-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="f73a7-132">For more information, see [Use the Database Engine cmdlets](../../database-engine/use-the-database-engine-cmdlets.md).</span></span>  
  
## <a name="soap-and-service-broker-endpoints"></a><span data-ttu-id="f73a7-133">Pontos de extremidade SOAP e do Service Broker</span><span class="sxs-lookup"><span data-stu-id="f73a7-133">SOAP and Service Broker Endpoints</span></span>  
 <span data-ttu-id="f73a7-134">Para desabilitar os pontos de extremidade, use o Gerenciamento Baseado em Política.</span><span class="sxs-lookup"><span data-stu-id="f73a7-134">To turn endpoints off, use Policy-Based Management.</span></span> <span data-ttu-id="f73a7-135">Para criar e alterar as propriedades de pontos de extremidade, use [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) e [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73a7-135">To create and alter the properties of endpoints, use [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) and [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f73a7-136">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="f73a7-136">Related Content</span></span>  
 [<span data-ttu-id="f73a7-137">Central de segurança do Mecanismo de Banco de Dados do SQL Server e Banco de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="f73a7-137">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="f73a7-138">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f73a7-138">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
