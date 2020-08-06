---
title: Definir um alias de SQL Server para o serviço de SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], creating
- SQL Server Agent, aliases
ms.assetid: 02d6295d-ab52-44f0-8f1b-f3910a507d8f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b178d91a47d907b182ef7962b98c7f22d4454094
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569622"
---
# <a name="set-a-sql-server-alias-for-the-sql-server-agent-service-sql-server-management-studio"></a><span data-ttu-id="c156b-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c156b-102">Set a SQL Server Alias for the SQL Server Agent Service (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c156b-103">Este tópico descreve como definir um [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que o Agent use para se conectar ao [!INCLUDE[ssDE](../includes/ssde-md.md)] usando o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c156b-103">This topic describes how to set a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alias for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to use to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="c156b-104">Por padrão, o serviço do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent se conecta a uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] em pipes nomeados usando nomes dinâmicos de servidor que não exigem configuração adicional de cliente.</span><span class="sxs-lookup"><span data-stu-id="c156b-104">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] over named pipes by using dynamic server names that require no additional client configuration.</span></span> <span data-ttu-id="c156b-105">Só será necessário configurar um alias de conexão com o servidor se você não estiver usando o transporte de rede padrão ou se estiver se conectando a uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que escute em um pipe nomeado alternativo.</span><span class="sxs-lookup"><span data-stu-id="c156b-105">You need to configure a server connection alias only if you are not using the default network transport or if you are connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="c156b-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c156b-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c156b-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c156b-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c156b-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c156b-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c156b-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="c156b-109">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="c156b-110">Para definir um Alias do SQL Server para o Serviço do SQL Server Agent usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c156b-110">To set a SQL Server Alias for the SQL Server Agent Service using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c156b-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c156b-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c156b-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c156b-112">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="c156b-113">Agent não funcionará corretamente a menos que você selecione um alias referente à instância local do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c156b-113">Agent will not work correctly unless you select an alias that refers to the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="c156b-114">O Pesquisador de Objetos só exibirá o nó [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent se você tiver permissão para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="c156b-114">Object Explorer only displays the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c156b-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="c156b-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c156b-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="c156b-116">Permissions</span></span>  
 <span data-ttu-id="c156b-117">Para executar suas funções, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent deve ser configurado de modo a usar as credenciais de uma conta que seja membro da função de servidor fixa **sysadmin** no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c156b-117">To perform its functions, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c156b-118">A conta deve ter as seguintes permissões do Windows:</span><span class="sxs-lookup"><span data-stu-id="c156b-118">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="c156b-119">Fazer logon como um serviço (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="c156b-119">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="c156b-120">Substituir um token de nível de processo (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="c156b-120">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="c156b-121">Ignorar verificação completa (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="c156b-121">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="c156b-122">Ajustar cotas de memória para um processo (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="c156b-122">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="c156b-123">Para obter mais informações sobre as permissões do Windows necessárias para a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] conta de serviço do Agent, consulte [selecionar uma conta para o serviço de SQL Server Agent](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) e [Configurar contas de serviço e permissões do Windows](configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c156b-123">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](../ssms/agent/select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c156b-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c156b-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-sql-server-alias-for-the-sql-server-agent-service"></a><span data-ttu-id="c156b-125">Para definir um alias do SQL Server para o serviço do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c156b-125">To set a SQL Server Alias for the SQL Server Agent Service</span></span>  
  
1.  <span data-ttu-id="c156b-126">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="c156b-126">In the **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c156b-127">Clique com o botão direito do mouse em **SQL Server Agent**e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c156b-127">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c156b-128">Na caixa de diálogo **Propriedades do SQL Server Agent**_server_name_ , em **selecionar uma página**, selecione **conexão**e</span><span class="sxs-lookup"><span data-stu-id="c156b-128">In the **SQL Server Agent Properties**_server_name_ dialog box, under **Select a page**, select **Connection**, and</span></span>  
  
4.  <span data-ttu-id="c156b-129">Na caixa **Servidor de host local do alias** , digite o alias do servidor ao qual o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent deve se conectar.</span><span class="sxs-lookup"><span data-stu-id="c156b-129">In the **Alias local host server** box, type the alias of the server to which [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should connect.</span></span>  
  
5.  <span data-ttu-id="c156b-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c156b-130">Click **OK**.</span></span>  
  
  
