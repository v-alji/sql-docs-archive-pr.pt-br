---
title: Configurar protocolos de cliente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default protocols
- network protocols [SQL Server], client configuration
- TCP/IP [SQL Server], client protocols
- disabling client protocols
- ordering protocols [SQL Server]
- protocols [SQL Server], order for client computers
- configure client protocols
- client protocols [SQL Server]
- protocols [SQL Server], client configuration
ms.assetid: 3dfa2702-ba65-43b4-a777-6727846e133a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2eb223815c3e3af50813e02d3ded60573c327155
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583842"
---
# <a name="configure-client-protocols"></a><span data-ttu-id="0f9d6-102">configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="0f9d6-102">Configure Client Protocols</span></span>
  <span data-ttu-id="0f9d6-103">Este tópico descreve como configurar protocolos de cliente usados por aplicativos cliente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-103">This topic describes how to configure client protocols used by client applications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="0f9d6-104">O Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte à comunicação cliente com o protocolo de rede TCP/IP e o protocolo de pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports client communication with the TCP/IP network protocol and the named pipes protocol.</span></span> <span data-ttu-id="0f9d6-105">O protocolo de memória compartilhada também estará disponível se o cliente estiver se conectando a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-105">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="0f9d6-106">Há três métodos comuns de selecionar o protocolo.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-106">There are three common methods of selecting the protocol.</span></span>  
  
-   <span data-ttu-id="0f9d6-107">Configure todos os aplicativos cliente para usar o mesmo protocolo de rede definindo a ordem de protocolo no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-107">Configure all client applications to use the same network protocol by setting the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
-   <span data-ttu-id="0f9d6-108">Configure um único aplicativo cliente para usar um protocolo de rede diferente criando um alias.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-108">Configure a single client application to use a different network protocol by creating an alias.</span></span> <span data-ttu-id="0f9d6-109">Para obter mais informações, consulte [Criar ou excluir um alias de servidor para ser usado por um cliente &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="0f9d6-109">For more information, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="0f9d6-110">Alguns aplicativos cliente, como sqlcmd.exe, podem especificar o protocolo como parte da cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-110">Some client applications, such as sqlcmd.exe, can specify the protocol as part of the connection string.</span></span> <span data-ttu-id="0f9d6-111">Para obter mais informações, veja [Conectar-se ao Mecanismo de Banco de Dados com sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="0f9d6-111">For more information, see [Connect to the Database Engine With sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0f9d6-112">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0f9d6-112">Using SQL Server Configuration Manager</span></span>  
  
###  <a name="to-enable-or-disable-a-client-protocol"></a><a name="EnableDisable"></a> <span data-ttu-id="0f9d6-113">Para habilitar ou desabilitar um protocolo de cliente</span><span class="sxs-lookup"><span data-stu-id="0f9d6-113">To enable or disable a client protocol</span></span>  
  
1.  <span data-ttu-id="0f9d6-114">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expanda **Configuração do SQL Server Native Client**, clique com o botão direito do mouse em **Protocolos de Cliente** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0f9d6-115">Clique em um protocolo na caixa **Protocolos Desabilitados** e clique em **Habilitar** para habilitar um protocolo.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-115">Click a protocol in the **Disabled Protocols** box, and then click **Enable**, to enable a protocol.</span></span>  
  
3.  <span data-ttu-id="0f9d6-116">Clique em um protocolo na caixa **Protocolos Habilitados** e clique em **Desabilitar** para desabilitar um protocolo.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-116">Click a protocol in the **Enabled Protocols** box, and then click **Disable**, to disable a protocol.</span></span>  
  
###  <a name="to-change-the-default-protocol-or-the-protocol-order-for-client-computers"></a><a name="ChangeDefault"></a> <span data-ttu-id="0f9d6-117">Para alterar o protocolo padrão ou a ordem de protocolo para computadores cliente</span><span class="sxs-lookup"><span data-stu-id="0f9d6-117">To change the default protocol or the protocol order for client computers</span></span>  
  
1.  <span data-ttu-id="0f9d6-118">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expanda **Configuração do SQL Server Native Client**, clique com o botão direito do mouse em **Protocolos de Cliente** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-118">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0f9d6-119">Na caixa **Protocolos Habilitados**, clique em **Mover para Cima** ou **Mover para Baixo** para alterar a ordem na qual os protocolos são usados ao tentar uma conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f9d6-119">In the **Enabled Protocols** box, click **Move Up** or **Move Down**, to change the order in which protocols are tried, when attempting to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0f9d6-120">O primeiro protocolo na caixa **Protocolos Habilitados** é o protocolo padrão.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-120">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0f9d6-121">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager cria entradas de registro para as configurações de alias de servidor e biblioteca de rede de cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager creates registry entries for the server alias configurations and default client network library.</span></span> <span data-ttu-id="0f9d6-122">No entanto, o aplicativo não instala as bibliotecas nem os protocolos de rede do cliente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f9d6-122">However, the application does not install either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries or the network protocols.</span></span> <span data-ttu-id="0f9d6-123">As bibliotecas de rede do cliente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são instaladas durante a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; os protocolos de rede são instalados como parte da Instalação do Microsoft Windows (ou em **Redes** no **Painel de Controle**).</span><span class="sxs-lookup"><span data-stu-id="0f9d6-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries are installed during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup; the network protocols are installed as part of Microsoft Windows Setup (or through **Networks** in **Control Panel**).</span></span> <span data-ttu-id="0f9d6-124">Um protocolo de rede específico pode não estar disponível como parte da Instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-124">A particular network protocol may not be available as part of Windows Setup.</span></span> <span data-ttu-id="0f9d6-125">Para obter mais informações sobre como instalar esses protocolos de rede, consulte a documentação do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-125">For more information about installing these network protocols, see the vendor documentation.</span></span>  
  
###  <a name="to-configure-a-client-to-use-tcpip"></a><a name="Configure"></a> <span data-ttu-id="0f9d6-126">Para configurar um cliente para usar TCP/IP</span><span class="sxs-lookup"><span data-stu-id="0f9d6-126">To configure a client to use TCP/IP</span></span>  
  
1.  <span data-ttu-id="0f9d6-127">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expanda **Configuração do SQL Server Native Client**, clique com o botão direito do mouse em **Protocolos de Cliente** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-127">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0f9d6-128">Na caixa **Protocolos Habilitados**, clique nas setas para cima e para baixo para alterar a ordem na qual os protocolos são tentados, quando tentar se conectar ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-128">In the **Enabled Protocols** box, click the up and down arrows to change the order in which protocols are tried, when attempting to connect to SQL Server.</span></span> <span data-ttu-id="0f9d6-129">O primeiro protocolo na caixa **Protocolos Habilitados** é o protocolo padrão.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-129">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
 <span data-ttu-id="0f9d6-130">O protocolo de memória compartilhada é habilitado separadamente, marcando a caixa **Protocolo de Memória Compartilhada Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="0f9d6-130">The shared memory protocol is enabled separately by checking the **Enabled Shared Memory Protocol** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f9d6-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0f9d6-131">See Also</span></span>  
 [<span data-ttu-id="0f9d6-132">Configurar a opção de configuração do servidor remote login timeout</span><span class="sxs-lookup"><span data-stu-id="0f9d6-132">Configure the remote login timeout Server Configuration Option</span></span>](configure-the-remote-login-timeout-server-configuration-option.md)  
  
  
