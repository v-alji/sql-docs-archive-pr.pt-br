---
title: Criar um grupo e um servidor de gerenciamento central
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- configuration server
ms.assetid: da265482-3953-440a-ac23-0ab7e42a55eb
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f53b75966a14dbc6fd6cdc9bea0929ccac7780c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678540"
---
# <a name="create-a-central-management-server-and-server-group-sql-server-management-studio"></a><span data-ttu-id="dbddd-102">Criar um servidor de gerenciamento central e um grupo de servidores (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="dbddd-102">Create a Central Management Server and Server Group (SQL Server Management Studio)</span></span>
  <span data-ttu-id="dbddd-103">Este tópico descreve como designar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como servidor central de gerenciamento no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbddd-103">This topic describes how to designate an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a central management server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="dbddd-104">Os servidores de gerenciamento central armazenam uma lista de instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que é organizada em um ou mais grupos de servidores de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="dbddd-104">Central management servers store a list of instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is organized into one or more central management server groups.</span></span> <span data-ttu-id="dbddd-105">As ações executadas com um grupo de servidores de gerenciamento central afetarão todos os servidores do grupo.</span><span class="sxs-lookup"><span data-stu-id="dbddd-105">Actions that are taken by using a central management server group act on all servers in the server group.</span></span> <span data-ttu-id="dbddd-106">Isso inclui a conexão a servidores usando o Pesquisador de Objetos e a execução de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] e de políticas de Gerenciamento Baseado em Política em vários servidores ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="dbddd-106">This includes connecting to servers by using Object Explorer and executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and Policy-Based Management policies on multiple servers at the same time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbddd-107">As versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores ao [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] não podem ser designadas como um servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="dbddd-107">Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] cannot be designated as a central management server.</span></span>  
  
 <span data-ttu-id="dbddd-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="dbddd-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dbddd-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="dbddd-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dbddd-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="dbddd-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dbddd-111">**Para criar um Servidor Central de Gerenciamento e um Grupo de Servidores, usando:**</span><span class="sxs-lookup"><span data-stu-id="dbddd-111">**To create a Central Management Server and Server Group, using:**</span></span>  
  
     [<span data-ttu-id="dbddd-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dbddd-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dbddd-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="dbddd-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dbddd-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="dbddd-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dbddd-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="dbddd-115">Permissions</span></span>  
 <span data-ttu-id="dbddd-116">Duas funções no banco de dados msdb concedem acesso aos servidores de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="dbddd-116">Two database roles in the msdb database grant access to central management servers.</span></span> <span data-ttu-id="dbddd-117">Somente os membros da função ServerGroupAdministratorRole podem administrar o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="dbddd-117">Only members of the ServerGroupAdministratorRole role can manage the central management server.</span></span> <span data-ttu-id="dbddd-118">A associação à função ServerGroupReaderRole é necessária para conectar a um servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="dbddd-118">Membership in the ServerGroupReaderRole role is required to connect to a central management server.</span></span>  
  
 <span data-ttu-id="dbddd-119">Como as conexões mantidas por um servidor de gerenciamento central são executadas no contexto do usuário com o uso da Autenticação do Windows, as permissões efetivas nos servidores registrados podem variar.</span><span class="sxs-lookup"><span data-stu-id="dbddd-119">Because the connections that are maintained by a central management server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="dbddd-120">Por exemplo, o usuário pode ser membro da função de servidor fixa sysadmin na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, mas pode ter permissões limitadas na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span><span class="sxs-lookup"><span data-stu-id="dbddd-120">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dbddd-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dbddd-121">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="dbddd-122">Os procedimentos a seguir descrevem como executar as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="dbddd-122">The following procedures describe how to perform the following steps.</span></span>  
  
1.  <span data-ttu-id="dbddd-123">Crie um servidor central de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="dbddd-123">Create a central management server.</span></span>  
  
2.  <span data-ttu-id="dbddd-124">Adicione um ou mais grupos de servidores ao servidor central de gerenciamento e adicione um ou mais servidores registrados aos grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="dbddd-124">Add one or more server groups to the central management server and add one or more registered servers to the server groups.</span></span>  
  
#### <a name="create-a-central-management-server"></a><span data-ttu-id="dbddd-125">Criar um servidor central de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="dbddd-125">Create a central management server</span></span>  
  
1.  <span data-ttu-id="dbddd-126">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Servidores Registrados**.</span><span class="sxs-lookup"><span data-stu-id="dbddd-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="dbddd-127">Em Servidores Registrados, expanda **Mecanismo de Banco de Dados**, clique com o botão direito do mouse em **Servidores Centrais de Gerenciamento**e clique em **Registrar Servidor Central de Gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="dbddd-127">In Registered Servers, expand **Database Engine**, right-click **Central Management Servers**, and then  click **Register Central Management Server**.</span></span>  
  
3.  <span data-ttu-id="dbddd-128">Na caixa de diálogo **Novo Registro de Servidor** , selecione a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você deseja transformar em servidor central de gerenciamento central na lista suspensa de servidores.</span><span class="sxs-lookup"><span data-stu-id="dbddd-128">In the **New Server Registration** dialog box, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to become the central management server from the drop-down list of servers.</span></span> <span data-ttu-id="dbddd-129">Você deve usar a Autenticação do Windows para o servidor central de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="dbddd-129">You must use Windows Authentication for the central management server.</span></span>  
  
4.  <span data-ttu-id="dbddd-130">Em **Servidor Registrado**, digite um nome de servidor e uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="dbddd-130">In **Registered Server**, enter a server name and optional description.</span></span>  
  
5.  <span data-ttu-id="dbddd-131">Na guia de **Propriedades da Conexão** , revise ou modifique as propriedades da rede e da conexão.</span><span class="sxs-lookup"><span data-stu-id="dbddd-131">From the **Connection Properties** tab, review or modifiy the network  and connection properties.</span></span> <span data-ttu-id="dbddd-132">Para obter mais informações, consulte [Conectar ao Servidor &#40;página Propriedades da Conexão&#41; Mecanismo de Banco de Dados](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="dbddd-132">For more information, see [Connect to Server &#40;Connection Properties Page&#41; Database Engine](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span></span>  
  
6.  <span data-ttu-id="dbddd-133">Clique em **Testar**para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="dbddd-133">Click **Test**, to test the connection.</span></span>  
  
7.  <span data-ttu-id="dbddd-134">Clique em **Save** (Salvar).</span><span class="sxs-lookup"><span data-stu-id="dbddd-134">Click **Save**.</span></span> <span data-ttu-id="dbddd-135">A instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aparecerá na pasta **Servidores Centrais de Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="dbddd-135">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will appear under the **Central Management Servers** folder.</span></span>  
  
#### <a name="create-a-new-server-group-and-add-servers-to-the-group"></a><span data-ttu-id="dbddd-136">Criar um novo grupo de servidores e adicionar servidores ao grupo</span><span class="sxs-lookup"><span data-stu-id="dbddd-136">Create a new server group and add servers to the group</span></span>  
  
1.  <span data-ttu-id="dbddd-137">Em **Servidores Registrados**, expanda **Servidores Centrais de Gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="dbddd-137">From **Registered Servers**, expand **Central Management Servers**.</span></span> <span data-ttu-id="dbddd-138">Clique com o botão direito do mouse na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adicionada ao procedimento anterior e selecione **Novo Grupo de Servidores**.</span><span class="sxs-lookup"><span data-stu-id="dbddd-138">Right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] added in the procedure above and select **New Server Group**.</span></span>  
  
2.  <span data-ttu-id="dbddd-139">Em **Propriedades do Novo Grupo de Servidores**, digite um nome de grupo e uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="dbddd-139">In **New Server Group Properties**, enter a group name and optional description.</span></span>  
  
3.  <span data-ttu-id="dbddd-140">Em **Servidores Registrados**, clique com o botão direito do mouse no grupo de servidores e clique em **Novo Registro de Servidor**.</span><span class="sxs-lookup"><span data-stu-id="dbddd-140">From **Registered Servers**, right-click the server group and click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="dbddd-141">Em Novo Registro de Servidor, selecione uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbddd-141">From New Server Registration, select an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dbddd-142">Para obter mais informações, consulte [Criar um novo servidor registrado &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="dbddd-142">For more information, see [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span></span> <span data-ttu-id="dbddd-143">Adicione mais servidores conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="dbddd-143">Add more servers as appropriate.</span></span>  
  
#### <a name="to-execute-queries-against-several-configuration-targets-at-the-same-time"></a><span data-ttu-id="dbddd-144">Para executar consultas em vários destinos de configuração ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="dbddd-144">To execute queries against several configuration targets at the same time</span></span>  
  
-   <span data-ttu-id="dbddd-145">Depois de criar um servidor de gerenciamento central, um ou mais grupos de servidores e um ou mais servidores registrados, você poderá executar consultas simultâneas no grupo inteiro.</span><span class="sxs-lookup"><span data-stu-id="dbddd-145">After you create a central management server, one or more server groups, and one or more registered servers, you can execute queries against a whole group at the same time.</span></span> <span data-ttu-id="dbddd-146">Para obter mais informações sobre como executar instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] nos servidores em um grupo de servidores ao mesmo tempo, consulte [Executar instruções em vários servidores simultaneamente &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span><span class="sxs-lookup"><span data-stu-id="dbddd-146">For more information about how to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on the servers in a server group at the same time, see [Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbddd-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dbddd-147">See Also</span></span>  
 [<span data-ttu-id="dbddd-148">Administrar vários servidores usando os Servidores de Gerenciamento Centrais</span><span class="sxs-lookup"><span data-stu-id="dbddd-148">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
