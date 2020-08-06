---
title: Modificar as contas dos serviços controlador e cliente | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 44a73ddb-18ad-415c-bfbe-126ab2e3290b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62a054749f1d53323bde5c9d05a1e7632b1dda85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682026"
---
# <a name="modify-the-controller-and-client-services-accounts"></a><span data-ttu-id="62b04-102">Modificar as contas dos serviços controlador e cliente</span><span class="sxs-lookup"><span data-stu-id="62b04-102">Modify the Controller and Client Services Accounts</span></span>
  <span data-ttu-id="62b04-103">Neste tópico, você aprenderá a modificar o controlador Distributed Replay e as contas de serviço cliente e depois reaplicar as ACLs (listas de controle de acesso).</span><span class="sxs-lookup"><span data-stu-id="62b04-103">In this topic, you will learn how to modify the Distributed Replay controller and client service accounts, and then reapply the access control lists (ACLs).</span></span>  
  
### <a name="to-start-or-stop-the-distributed-replay-services-using-computer-management"></a><span data-ttu-id="62b04-104">Para iniciar ou parar os serviços Distributed Replay usando o gerenciamento do computador</span><span class="sxs-lookup"><span data-stu-id="62b04-104">To start or stop the Distributed Replay services using Computer Management</span></span>  
  
1.  <span data-ttu-id="62b04-105">No computador em que os serviços Distributed Replay estão instalados, no prompt de comando, digite `dcomcnfg`.</span><span class="sxs-lookup"><span data-stu-id="62b04-105">On the computer on which the Distributed Replay services are installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
2.  <span data-ttu-id="62b04-106">Clique duas vezes em **Serviços**, role para baixo e clique com o botão direito do mouse em \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name> \*\*e, em seguida, clique em **Iniciar** ou **parar**.</span><span class="sxs-lookup"><span data-stu-id="62b04-106">Double-click **Services**, scroll down and right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name>**, and then click **Start** or **Stop**.</span></span>  
  
### <a name="to-modify-the-distributed-replay-controller-service"></a><span data-ttu-id="62b04-107">Para modificar o serviço controlador Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="62b04-107">To modify the Distributed Replay controller service</span></span>  
  
1.  <span data-ttu-id="62b04-108">No computador controlador, pare o serviço controlador [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="62b04-108">On the controller computer, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="62b04-109">Em **Serviços**, clique com o botão direito do mouse em **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay**e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="62b04-109">Under **Services**, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**, and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="62b04-110">Na janela **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay** , na guia **Logon** , selecione **Esta conta**, digite ou clique em **Procurar** para inserir a nova conta de logon e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62b04-110">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
     <span data-ttu-id="62b04-111">**Importante**: Ao configurar o Distributed Replay Controller é possível especificar uma ou mais contas de usuário que serão usadas para executar os serviços de cliente do Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="62b04-111">**Important**: When you configure Distributed Replay Controller, you can specify one or more user accounts that will be used to run the Distributed Replay Client services.</span></span> <span data-ttu-id="62b04-112">Esta é a lista das contas com suporte:</span><span class="sxs-lookup"><span data-stu-id="62b04-112">The following is the list of supported accounts:</span></span>  
  
    -   <span data-ttu-id="62b04-113">Conta de usuário do domínio</span><span class="sxs-lookup"><span data-stu-id="62b04-113">Domain user account</span></span>  
  
    -   <span data-ttu-id="62b04-114">Conta de usuário local criada pelo usuário</span><span class="sxs-lookup"><span data-stu-id="62b04-114">User created local user account</span></span>  
  
    -   <span data-ttu-id="62b04-115">Administrador</span><span class="sxs-lookup"><span data-stu-id="62b04-115">Administrator</span></span>  
  
    -   <span data-ttu-id="62b04-116">Conta virtual e MSA (Conta de Serviço Gerenciada)</span><span class="sxs-lookup"><span data-stu-id="62b04-116">Virtual account and MSA (Managed Service Account)</span></span>  
  
    -   <span data-ttu-id="62b04-117">Serviços de rede, serviços locais e sistema</span><span class="sxs-lookup"><span data-stu-id="62b04-117">Network Services, Local Services, and System</span></span>  
  
     <span data-ttu-id="62b04-118">Não são aceitas contas de grupo (local ou domínio) e outras contas internas (como Todos).</span><span class="sxs-lookup"><span data-stu-id="62b04-118">Group accounts (local or domain) and other built-in accounts (like Everyone) are not accepted.</span></span>  
  
4.  <span data-ttu-id="62b04-119">Inicie o serviço controlador Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="62b04-119">Start the Distributed Replay controller service.</span></span>  
  
### <a name="to-modify-the-distributed-replay-client-service"></a><span data-ttu-id="62b04-120">Para modificar o serviço cliente do Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="62b04-120">To modify the Distributed Replay client service</span></span>  
  
1.  <span data-ttu-id="62b04-121">Antes de modificar o serviço cliente Distributed Replay, verifique se a conta do serviço cliente que você está alterando foi especificada durante a configuração (no parâmetro CTLRUSERS no computador controlador).</span><span class="sxs-lookup"><span data-stu-id="62b04-121">Before you modify the Distributed Replay client service, make sure the client service account you are changing was specified during setup (in the CTLRUSERS parameter on the controller computer).</span></span> <span data-ttu-id="62b04-122">Se a conta de serviço de cliente que você está alterando não foi especificada durante a instalação, execute as etapas a seguir primeiro:</span><span class="sxs-lookup"><span data-stu-id="62b04-122">If the client service account you are changing was not specified during setup, you must perform the following steps first:</span></span>  
  
    1.  <span data-ttu-id="62b04-123">Pare o serviço controlador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="62b04-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
    2.  <span data-ttu-id="62b04-124">No computador controlador em que o serviço controlador está instalado, no prompt de comando, digite `dcomcnfg`.</span><span class="sxs-lookup"><span data-stu-id="62b04-124">On the controller computer on which the controller service is installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
    3.  <span data-ttu-id="62b04-125">Na janela **Serviços de Componente**, navegue até **Raiz do Console -> Serviços de Componente -> Computadores -> Meu Computador -> Configuração de DCOM ->DReplayController**.</span><span class="sxs-lookup"><span data-stu-id="62b04-125">In the **Component Services** window, navigate to **Console Root -> Component Services -> Computers -> My Computer -> DCOM Config ->DReplayController**.</span></span>  
  
    4.  <span data-ttu-id="62b04-126">Clique com o botão direito do mouse em **DReplayController**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="62b04-126">Right-click **DReplayController**, and then click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="62b04-127">Na janela **Propriedades do DReplayController** , na guia **Segurança** , clique em **Editar** na seção **Permissões de Inicialização e Ativação** .</span><span class="sxs-lookup"><span data-stu-id="62b04-127">In the **DReplayController Properties** window, on the **Security** tab, click **Edit** in the **Launch and Activation Permissions** section.</span></span>  
  
    6.  <span data-ttu-id="62b04-128">Conceda à nova conta de logon do serviço cliente permissões de **Ativação Local e Remota** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62b04-128">Grant the new client service logon account **Local and Remote activation** permissions, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="62b04-129">Clique em **Editar** na seção **Permissões de Acesso** e conceda à nova conta de logon do serviço cliente permissões de **Acesso Local e Remoto** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62b04-129">Click **Edit** in the **Access Permissions** section, and grant the new client service logon account **Local and Remote access** permissions, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="62b04-130">Clique em **OK** para fechar a janela **Propriedades do DReplayController** .</span><span class="sxs-lookup"><span data-stu-id="62b04-130">Click **OK** to close the **DReplayController Properties** window.</span></span>  
  
    9. <span data-ttu-id="62b04-131">No computador controlador, adicione a conta de logon do serviço cliente alterado para o grupo **Usuários COM Distribuídos** .</span><span class="sxs-lookup"><span data-stu-id="62b04-131">On the controller computer, add the changed client service logon account to the **Distributed COM Users** group.</span></span>  
  
    10. <span data-ttu-id="62b04-132">Inicie o serviço controlador SQL Server Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="62b04-132">Start the SQL Server Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="62b04-133">Pare o serviço cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="62b04-133">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay client service.</span></span>  
  
3.  <span data-ttu-id="62b04-134">Na janela **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay** , na guia **Logon** , selecione **Esta conta**, digite ou clique em **Procurar** para inserir a nova conta de logon e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="62b04-134">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="62b04-135">Inicie o serviço cliente Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="62b04-135">Start the Distributed Replay client service.</span></span>  
  
  
