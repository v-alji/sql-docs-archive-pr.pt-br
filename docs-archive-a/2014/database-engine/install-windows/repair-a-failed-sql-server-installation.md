---
title: Reparar uma instalação do SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 90c11b28-892b-44d6-978e-0eee48c75b7d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e382137a971b3f8b23cf1d814bff9908f04150
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681067"
---
# <a name="drop-a-sql-server-2014-installation"></a><span data-ttu-id="81636-102">Descartar uma instalação do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="81636-102">Drop a SQL Server 2014 Installation</span></span>
  <span data-ttu-id="81636-103">A operação de reparo pode ser usada nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="81636-103">Repair operation can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="81636-104">Reparar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] corrompida após instalação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="81636-104">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is corrupted after it was successfully installed.</span></span>  
  
-   <span data-ttu-id="81636-105">Reparar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se a operação de atualização for cancelada ou falhar depois que o nome da instância for mapeado para a instância recém-atualizada.</span><span class="sxs-lookup"><span data-stu-id="81636-105">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if the upgrade operation is cancelled or fails after the instance name is mapped to the newly-upgraded instance.</span></span>  
  
    -   <span data-ttu-id="81636-106">Se você encontrar a mensagem seguinte no log de resumo, poderá reparar a instância de atualização com falha:</span><span class="sxs-lookup"><span data-stu-id="81636-106">If you see the following message in the summary log, you can repair the failed upgrade instance:</span></span>  
  
         <span data-ttu-id="81636-107">Falha na atualização do "[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81636-107">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="81636-108">Para continuar, investigue o motivo da falha, corrija o problema e repare a instalação."</span><span class="sxs-lookup"><span data-stu-id="81636-108">To continue, investigate the reason for the failure, correct the problem, and then repair your installation."</span></span>  
  
    -   <span data-ttu-id="81636-109">Se você encontrar a mensagem a seguir no log de resumo, será necessário desinstalar e reinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81636-109">If you see the following message in the summary log, you need to uninstall and reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="81636-110">Você não pode reparar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81636-110">You cannot repair the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="81636-111">Falha na atualização do "[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81636-111">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="81636-112">Para continuar, investigue o motivo para a falha e corrija o problema".</span><span class="sxs-lookup"><span data-stu-id="81636-112">To continue, investigate the reason for the failure, correct the problem."</span></span>  
  
 <span data-ttu-id="81636-113">Quando você repara uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="81636-113">When you repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="81636-114">Todos os arquivos ausentes ou corrompidos são substituídos.</span><span class="sxs-lookup"><span data-stu-id="81636-114">All missing or corrupt files are replaced.</span></span>  
  
-   <span data-ttu-id="81636-115">Todas as chaves do Registro ausentes ou corrompidas são substituídas.</span><span class="sxs-lookup"><span data-stu-id="81636-115">All missing or corrupt registry keys are replaced.</span></span>  
  
-   <span data-ttu-id="81636-116">Todos os valores de configuração ausentes ou inválidos são definidos como valores padrão.</span><span class="sxs-lookup"><span data-stu-id="81636-116">All missing or invalid configuration values are set to default values.</span></span>  
  
 <span data-ttu-id="81636-117">Antes de você continuar, para clusters de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , examine as seguintes informações importantes:</span><span class="sxs-lookup"><span data-stu-id="81636-117">Before you continue, for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover clusters, review the following important information:</span></span>  
  
-   <span data-ttu-id="81636-118">O reparo dever ser executado em nós de cluster individuais.</span><span class="sxs-lookup"><span data-stu-id="81636-118">Repair must be run on individual cluster nodes.</span></span>  
  
-   <span data-ttu-id="81636-119">Para reparar um nó de cluster de failover após uma operação Preparar com falha, use **Remover nó** e execute a etapa Preparar novamente.</span><span class="sxs-lookup"><span data-stu-id="81636-119">To repair a failover cluster node after a failed Prepare operation, use **Remove node** and then perform the Prepare step again.</span></span> <span data-ttu-id="81636-120">Para obter mais informações, consulte [Adicionar ou remover nós em um cluster de failover do SQL Server &#40;Instalação&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="81636-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-from-the-installation-center"></a><span data-ttu-id="81636-121">Para reparar uma instalação com falha do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a partir da Central de Instalação</span><span class="sxs-lookup"><span data-stu-id="81636-121">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the Installation Center</span></span>  
  
1.  <span data-ttu-id="81636-122">Inicie o programa de instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (setup.exe) na mídia de instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81636-122">Launch the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program (setup.exe) from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span>  
  
2.  <span data-ttu-id="81636-123">Depois da verificação dos pré-requisitos e do sistema, o programa de Instalação exibirá a página Central de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81636-123">After prerequisites and system verification, the Setup program will display the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Center page.</span></span>  
  
3.  <span data-ttu-id="81636-124">Clique em **Manutenção** na área de navegação à esquerda e clique em **Reparar** para iniciar a operação de reparo.</span><span class="sxs-lookup"><span data-stu-id="81636-124">Click **Maintenance** in the left-hand navigation area, and then click **Repair** to start the repair operation.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="81636-125">Se a Central de Instalação foi iniciada usando o menu de início, você precisará fornecer o local da mídia de instalação neste momento.</span><span class="sxs-lookup"><span data-stu-id="81636-125">If the Installation Center was launched using the start menu, you will need to provide the location of the installation media at this time.</span></span>  
  
4.  <span data-ttu-id="81636-126">A regra de suporte à Instalação e as rotinas de arquivos serão executadas para garantir que o sistema tenha os pré-requisitos instalados e que o computador seja aprovado nas regras de validação da Instalação.</span><span class="sxs-lookup"><span data-stu-id="81636-126">Setup support rule and file routines will run to ensure that your system has prerequisites installed and that the computer passes Setup validation rules.</span></span> <span data-ttu-id="81636-127">Clique em **OK** ou em **Instalar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="81636-127">Click **OK** or **Install** to continue.</span></span>  
  
5.  <span data-ttu-id="81636-128">Na página Selecionar Instância, selecione a instância a ser reparada e clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="81636-128">On the Select Instance page, select the instance to repair, and then click **Next** to continue.</span></span>  
  
6.  <span data-ttu-id="81636-129">As regras de reparo são executadas para validar a operação.</span><span class="sxs-lookup"><span data-stu-id="81636-129">The repair rules will run to validate the operation.</span></span> <span data-ttu-id="81636-130">Para continuar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="81636-130">To continue, click **Next**.</span></span>  
  
7.  <span data-ttu-id="81636-131">A página Pronto para Reparar indica que a operação está pronta para continuar.</span><span class="sxs-lookup"><span data-stu-id="81636-131">The Ready to Repair page indicates that the operation is ready to proceed.</span></span> <span data-ttu-id="81636-132">Para continuar, clique em **Reparar**.</span><span class="sxs-lookup"><span data-stu-id="81636-132">To continue, click **Repair**.</span></span>  
  
8.  <span data-ttu-id="81636-133">A página de Progresso do Reparo mostra o status da operação de reparo.</span><span class="sxs-lookup"><span data-stu-id="81636-133">The Repair Progress page shows the status of the repair operation.</span></span> <span data-ttu-id="81636-134">A página Concluído indica que a operação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="81636-134">The Complete page indicates that the operation is finished.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-using-command-prompt"></a><span data-ttu-id="81636-135">Para reparar uma instalação com falha do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um prompt de comando</span><span class="sxs-lookup"><span data-stu-id="81636-135">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Command Prompt</span></span>  
  
1.  <span data-ttu-id="81636-136">Execute o seguinte comando em um prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="81636-136">Run the following command at a command prompt:</span></span>  
  
    ```  
    Setup.exe /q /ACTION=Repair /INSTANCENAME=instancename  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="81636-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81636-137">See Also</span></span>  
 <span data-ttu-id="81636-138">[Exibir e ler arquivos de log da Instalação do SQL Server](view-and-read-sql-server-setup-log-files.md) </span><span class="sxs-lookup"><span data-stu-id="81636-138">[View and Read SQL Server Setup Log Files](view-and-read-sql-server-setup-log-files.md) </span></span>  
 [<span data-ttu-id="81636-139">Tópicos de instruções sobre a instalação</span><span class="sxs-lookup"><span data-stu-id="81636-139">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
  
  
