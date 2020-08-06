---
title: Protocolos de rede e bibliotecas de rede | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- protocols [SQL Server]
- configuration options [SQL Server], protocols
- network libraries [SQL Server]
- protocols [SQL Server], about network protocols
- pipes [SQL Server]
- network protocols [SQL Server]
- default SQL Server configurations
- library [SQL Server]
- network protocols [SQL Server], about network protocols
- configuration options [SQL Server], libraries
ms.assetid: 8cd437f6-9af1-44ce-9cb0-4d10c83da9ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be012ea2bc9499a99ca7763446c6f26cf219a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582771"
---
# <a name="network-protocols-and-network-libraries"></a><span data-ttu-id="0de4f-102">Protocolos de rede e bibliotecas de rede</span><span class="sxs-lookup"><span data-stu-id="0de4f-102">Network Protocols and Network Libraries</span></span>
  <span data-ttu-id="0de4f-103">Um servidor pode escutar ou monitorar vários protocolos de rede ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="0de4f-103">A server can listen on, or monitor, multiple network protocols at one time.</span></span> <span data-ttu-id="0de4f-104">Entretanto, cada protocolo deve ser configurado.</span><span class="sxs-lookup"><span data-stu-id="0de4f-104">However, each protocol must be configured.</span></span> <span data-ttu-id="0de4f-105">Se um protocolo específico não for configurado, o servidor não poderá escutar naquele protocolo.</span><span class="sxs-lookup"><span data-stu-id="0de4f-105">If a particular protocol is not configured, the server cannot listen on that protocol.</span></span> <span data-ttu-id="0de4f-106">Após a instalação, você pode alterar as configurações de protocolo usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0de4f-106">After installation, you can change the protocol configurations using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="default-sql-server-network-configuration"></a><span data-ttu-id="0de4f-107">Configuração de rede padrão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0de4f-107">Default SQL Server Network Configuration</span></span>  
 <span data-ttu-id="0de4f-108">Uma instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é configurada para a porta TCP/IP 1433 e para o pipe nomeado \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="0de4f-108">A default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for TCP/IP port 1433, and named pipe \\\\.\pipe\sql\query.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0de4f-109">são configuradas para portas dinâmicas TCP, com um número de porta atribuído pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="0de4f-109">named instances are configured for TCP dynamic ports, with a port number assigned by the operating system.</span></span>  
  
 <span data-ttu-id="0de4f-110">Se não for possível usar endereços de porta dinâmicos (por exemplo, quando as conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precisam passar por um servidor de firewall configurado para passar por endereços de porta específicos).</span><span class="sxs-lookup"><span data-stu-id="0de4f-110">If you cannot use dynamic port addresses (for example, when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections must pass through a firewall server configured to pass through specific port addresses).</span></span> <span data-ttu-id="0de4f-111">Selecione um número de porta não atribuído.</span><span class="sxs-lookup"><span data-stu-id="0de4f-111">Select an unassigned port number.</span></span> <span data-ttu-id="0de4f-112">As atribuições de número da porta são gerenciadas pela Internet Assigned Numbers Authority e são listadas em [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span><span class="sxs-lookup"><span data-stu-id="0de4f-112">Port number assignments are managed by the Internet Assigned Numbers Authority and are listed at [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span></span>  
  
 <span data-ttu-id="0de4f-113">Para aumentar a segurança, a conectividade de rede não é habilitada completamente quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é instalado.</span><span class="sxs-lookup"><span data-stu-id="0de4f-113">To enhance security, network connectivity is not fully enabled when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span> <span data-ttu-id="0de4f-114">Para habilitar, desabilitar e configurar protocolos de rede depois que a Instalação for concluída, use a Área de Configuração de Rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0de4f-114">To enable, disable, and configure network protocols after Setup is complete, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Configuration area of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="server-message-block-protocol"></a><span data-ttu-id="0de4f-115">Protocolo SMB</span><span class="sxs-lookup"><span data-stu-id="0de4f-115">Server Message Block Protocol</span></span>  
 <span data-ttu-id="0de4f-116">Os servidores na rede de perímetro devem ter todos os protocolos desnecessários desabilitados, incluindo o SMB.</span><span class="sxs-lookup"><span data-stu-id="0de4f-116">Servers in the perimeter network should have all unnecessary protocols disabled, including server message block (SMB).</span></span> <span data-ttu-id="0de4f-117">Os servidores Web e DNS (Sistema de Nome de Domínio) não requerem SMB.</span><span class="sxs-lookup"><span data-stu-id="0de4f-117">Web servers and Domain Name System (DNS) servers do not require SMB.</span></span> <span data-ttu-id="0de4f-118">Este protocolo deve ser desabilitado para contra-atacar a ameaça de enumeração de usuário.</span><span class="sxs-lookup"><span data-stu-id="0de4f-118">This protocol should be disabled to counter the threat of user enumeration.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0de4f-119">A desabilitação do protocolo SMB impede que o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou Cluster do Windows acesse o compartilhamento de arquivos remoto.</span><span class="sxs-lookup"><span data-stu-id="0de4f-119">Disabling Server Message Block will block the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Windows Cluster service from accessing the remote file share.</span></span> <span data-ttu-id="0de4f-120">Não desabilite o SMB se você implementa ou planeja implementar uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="0de4f-120">Do not disable SMB if you do or plan to do one of the following:</span></span>  
> 
>  -   <span data-ttu-id="0de4f-121">Usar o modo de quorum da maioria do compartilhamento de arquivos e o nó de Custer do Windows</span><span class="sxs-lookup"><span data-stu-id="0de4f-121">Use Windows Cluster Node and File Share Majority Quorum mode</span></span>  
> -   <span data-ttu-id="0de4f-122">Especificar um compartilhamento de arquivos SMB como o diretório de dados durante a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0de4f-122">Specify an SMB file share as the data directory during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation</span></span>  
> -   <span data-ttu-id="0de4f-123">Criar um arquivo de banco de dados em um compartilhamento de arquivos SMB</span><span class="sxs-lookup"><span data-stu-id="0de4f-123">Create a database file on an SMB file share</span></span>  
  
#### <a name="to-disable-smb"></a><span data-ttu-id="0de4f-124">Para desabilitar o SMB</span><span class="sxs-lookup"><span data-stu-id="0de4f-124">To disable SMB</span></span>  
  
1.  <span data-ttu-id="0de4f-125">No menu **Iniciar** , aponte para **Configurações**e clique em **Conexões Discadas e de Rede**.</span><span class="sxs-lookup"><span data-stu-id="0de4f-125">On the **Start** menu, point to **Settings**, and then click **Network and Dial-up Connections**.</span></span>  
  
     <span data-ttu-id="0de4f-126">Clique com o botão direito do mouse na conexão com a Internet e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0de4f-126">Right-click the Internet-facing connection, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0de4f-127">Marque a caixa de seleção **Cliente para Redes Microsoft** e clique em **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="0de4f-127">Select the **Client for Microsoft Networks** check box, and then click **Uninstall**.</span></span>  
  
3.  <span data-ttu-id="0de4f-128">Siga as etapas de desinstalação.</span><span class="sxs-lookup"><span data-stu-id="0de4f-128">Follow the uninstall steps.</span></span>  
  
4.  <span data-ttu-id="0de4f-129">Selecione **Compartilhamento arquivos/impressoras p/ redes Microsoft**e clique em **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="0de4f-129">Select **File and Printer Sharing for Microsoft Networks**, and then click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="0de4f-130">Siga as etapas de desinstalação.</span><span class="sxs-lookup"><span data-stu-id="0de4f-130">Follow the uninstall steps.</span></span>  
  
#### <a name="to-disable-smb-on-servers-accessible-from-the-internet"></a><span data-ttu-id="0de4f-131">Para desabilitar o SMB em servidores acessíveis pela Internet</span><span class="sxs-lookup"><span data-stu-id="0de4f-131">To disable SMB on servers accessible from the Internet</span></span>  
  
-   <span data-ttu-id="0de4f-132">Nas propriedades da Conexão Local, use a caixa de diálogo **Transmission Control Protocol/Internet Protocol (TCP/IP) properties (Propriedades de protocolo TCP/IP)** para remover **Compartilhamento arquivos/impressoras p/ redes Microsoft** e **Cliente para Redes Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0de4f-132">In the Local Area Connection properties, use the **Transmission Control Protocol/Internet Protocol (TCP/IP) properties** dialog box to remove **File and Printer Sharing for Microsoft Networks** and **Client for Microsoft Networks**.</span></span>  
  
## <a name="endpoints"></a><span data-ttu-id="0de4f-133">Pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="0de4f-133">Endpoints</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0de4f-134">apresenta um novo conceito para conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; a conexão é representada na extremidade do servidor por um [!INCLUDE[tsql](../../includes/tsql-md.md)]*ponto de extremidade*.</span><span class="sxs-lookup"><span data-stu-id="0de4f-134">introduces a new concept for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections; the connection is represented on the server end by a [!INCLUDE[tsql](../../includes/tsql-md.md)]*endpoint*.</span></span> <span data-ttu-id="0de4f-135">As permissões podem ser concedidas, revogadas e negadas para pontos de extremidade [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0de4f-135">Permissions can be granted, revoked, and denied for [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints.</span></span> <span data-ttu-id="0de4f-136">Por padrão, todos os usuários têm permissões para acessar um ponto de extremidade, a menos que as permissões sejam negadas ou revogadas por um membro do grupo sysadmin ou pelo proprietário do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0de4f-136">By default, all users have permissions to access an endpoint unless the permissions are denied or revoked by a member of the sysadmin group or by the endpoint owner.</span></span> <span data-ttu-id="0de4f-137">A sintaxe de GRANT, REVOKE e DENY ENDPOINT usa um ID de ponto de extremidade que o administrador deve obter da exibição de catálogo do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0de4f-137">The GRANT, REVOKE, and DENY ENDPOINT syntax uses an endpoint ID that the administrator must get from the endpoint's catalog view.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0de4f-138">cria pontos de extremidade [!INCLUDE[tsql](../../includes/tsql-md.md)] para todos os protocolos de rede com suporte, bem como para a conexão de administrador dedicada.</span><span class="sxs-lookup"><span data-stu-id="0de4f-138">Setup creates [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints for all supported network protocols, as well as for the dedicated administrator connection.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="0de4f-139">criados pela Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="0de4f-139">endpoints created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup are as follows:</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="0de4f-140">computador local</span><span class="sxs-lookup"><span data-stu-id="0de4f-140">local machine</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="0de4f-141">pipes nomeados</span><span class="sxs-lookup"><span data-stu-id="0de4f-141">named pipes</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="0de4f-142">TCP padrão</span><span class="sxs-lookup"><span data-stu-id="0de4f-142">default TCP</span></span>  
  
 <span data-ttu-id="0de4f-143">Para obter mais informações sobre pontos de extremidade, veja [Configurar o Mecanismo de Banco de Dados para escutar em várias portas TCP](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) e [Exibições de catálogo de pontos de extremidade &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0de4f-143">For more information about endpoints, see [Configure the Database Engine to Listen on Multiple TCP Ports](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) and [Endpoints Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span></span>  
  
 <span data-ttu-id="0de4f-144">Para obter mais informações sobre configurações de rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte o seguinte tópico nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="0de4f-144">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network configurations, see the following topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="0de4f-145">Configuração de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="0de4f-145">Server Network Configuration</span></span>](../../database-engine/configure-windows/server-network-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="0de4f-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0de4f-146">See Also</span></span>  
 <span data-ttu-id="0de4f-147">[Configuração da Área de Superfície](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0de4f-147">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 <span data-ttu-id="0de4f-148">[Considerações sobre segurança para uma instalação do SQL Server](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="0de4f-148">[Security Considerations for a SQL Server Installation](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="0de4f-149">Planejando uma instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0de4f-149">Planning a SQL Server Installation</span></span>](../../../2014/sql-server/install/planning-a-sql-server-installation.md)  
  
  
