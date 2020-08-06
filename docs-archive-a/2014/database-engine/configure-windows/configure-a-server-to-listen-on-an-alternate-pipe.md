---
title: Configurar um servidor para escutar em um pipe alternativo (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Named Pipes [SQL Server], configuring
- listening [SQL Server], pipes
- pipes [SQL Server], alternate
- alternate pipes [SQL Server]
ms.assetid: 914f7491-e2be-4b0d-b3aa-fe5409cdbafa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 57d70cf4cd1d7474b895aeb8cb144c885e8a0f99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569650"
---
# <a name="configure-a-server-to-listen-on-an-alternate-pipe-sql-server-configuration-manager"></a><span data-ttu-id="9738c-102">Configurar um servidor para escuta em um pipe alternativo (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="9738c-102">Configure a Server to Listen on an Alternate Pipe (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="9738c-103">Este tópico descreve como configurar um servidor para escutar em um pipe alternativo no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9738c-103">This topic describes how to configure a server to listen on an alternate pipe in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="9738c-104">Por padrão, a instância padrão do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] escuta em um pipe chamado \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="9738c-104">By default, the default instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on named pipe \\\\.\pipe\sql\query.</span></span> <span data-ttu-id="9738c-105">As instâncias nomeadas do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e do [!INCLUDE[ssEW](../../includes/ssew-md.md)] escutam em outros pipes.</span><span class="sxs-lookup"><span data-stu-id="9738c-105">Named instances of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] listen on other pipes.</span></span>  
  
 <span data-ttu-id="9738c-106">Há três modos de se conectar a um pipe nomeado específico com um aplicativo cliente:</span><span class="sxs-lookup"><span data-stu-id="9738c-106">There are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="9738c-107">Execute o serviço de navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no servidor.</span><span class="sxs-lookup"><span data-stu-id="9738c-107">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="9738c-108">Crie um alias no cliente, especificando o pipe nomeado.</span><span class="sxs-lookup"><span data-stu-id="9738c-108">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="9738c-109">Programe o cliente para se conectar usando uma cadeia de conexão personalizada.</span><span class="sxs-lookup"><span data-stu-id="9738c-109">Program the client to connect using a custom connection string.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9738c-110">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9738c-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-the-named-pipe-used-by-the-sql-server-database-engine"></a><span data-ttu-id="9738c-111">Configurar o pipe nomeado usado pelo Mecanismo de Banco de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="9738c-111">To configure the named pipe used by the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="9738c-112">No SQL Server Configuration Manager, no painel de console, expanda **Configuração de Rede do SQL Server** e clique para expandir **Protocolos para** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="9738c-112">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, and then click expand **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="9738c-113">No painel de detalhes, clique com o botão direito do mouse em **Pipes Nomeados**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9738c-113">In the details pane, right-click **Named Pipes**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9738c-114">Na guia **Protocolo** , na caixa **Nome do Pipe** , digite o pipe no qual você deseja que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] escute e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9738c-114">On the **Protocol** tab, in the **Pipe Name** box, type the pipe you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="9738c-115">No painel do console, clique em **Serviços do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="9738c-115">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="9738c-116">No painel de detalhes, clique com o botão direito do mouse em **SQL Server (** \<instance name> **)** e depois clique em **Reiniciar** para interromper e reiniciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9738c-116">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9738c-117">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está escutando em um pipe alternativo, há três modos de se conectar a um pipe nomeado específico com um aplicativo cliente:</span><span class="sxs-lookup"><span data-stu-id="9738c-117">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening on an alternate pipe, there are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="9738c-118">Execute o serviço de navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no servidor.</span><span class="sxs-lookup"><span data-stu-id="9738c-118">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="9738c-119">Crie um alias no cliente, especificando o pipe nomeado.</span><span class="sxs-lookup"><span data-stu-id="9738c-119">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="9738c-120">Programe o cliente para se conectar usando uma cadeia de conexão personalizada.</span><span class="sxs-lookup"><span data-stu-id="9738c-120">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9738c-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9738c-121">See Also</span></span>  
 <span data-ttu-id="9738c-122">[Criar ou excluir um alias de servidor para ser usado por um cliente &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span><span class="sxs-lookup"><span data-stu-id="9738c-122">[Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span></span>  
 [<span data-ttu-id="9738c-123">Configuração de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="9738c-123">Server Network Configuration</span></span>](server-network-configuration.md)  
  
  
