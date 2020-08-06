---
title: Conectar-se a outro computador (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], other computers
ms.assetid: c4c1e94f-4f5f-431e-8b5b-d5ff97baf723
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3d478cebc1ca36ccb8f87b0355b7c8fe0a928cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583834"
---
# <a name="connect-to-another-computer-sql-server-configuration-manager"></a><span data-ttu-id="4a8dc-102">Conectar-se a um outro computador (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="4a8dc-102">Connect to Another Computer (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="4a8dc-103">Este tópico descreve como conectar-se a outro computador no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a8dc-103">This topic describes how to connect to another computer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4a8dc-104">Siga o primeiro procedimento para abrir o Windows Computer Management [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (mmc), conecte-se ao computador e expanda a árvore Serviços e Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-104">Follow the first procedure to open the Windows Computer Management [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (mmc), connect to the computer, and expand the Services and Applications tree.</span></span> <span data-ttu-id="4a8dc-105">Siga o segundo procedimento para criar um arquivo com um link para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-105">Follow the second procedure to create a file with a link to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a8dc-106">Algumas ações não podem ser executadas pelo Configuration Manager ao conectar-se remotamente.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-106">Some actions cannot be performed by Configuration Manager when connecting remotely.</span></span>  
  
 <span data-ttu-id="4a8dc-107">Para iniciar, parar, pausar ou retomar o serviço em outro computador, você também pode conectar-se ao servidor com o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique com o botão direito do mouse no servidor ou no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agente e clique na ação desejada.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-107">To start, stop, pause, or resume services on another computer, you can also connect to the server with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the server or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and then click the desired action.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-connect-to-another-computer-with-windows-computer-management"></a><span data-ttu-id="4a8dc-108">Para se conectar a outro computador com o Windows Computer Management</span><span class="sxs-lookup"><span data-stu-id="4a8dc-108">To connect to another computer with Windows Computer Management</span></span>  
  
1.  <span data-ttu-id="4a8dc-109">No menu **Iniciar** , clique com o botão direito do mouse em **Meu Computador**e clique em **Gerenciar.**</span><span class="sxs-lookup"><span data-stu-id="4a8dc-109">On the **Start** menu, right-click **My Computer**, and then click **Manage.**</span></span>  
  
2.  <span data-ttu-id="4a8dc-110">Em **Gerenciamento do Computador**, clique com o botão direito do mouse em **Gerenciamento do Computador (Local)** e clique em **Conectar a outro computador**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-110">In **Computer Management**, right-click **Computer Management (Local)**, and then click **Connect to another computer**.</span></span>  
  
3.  <span data-ttu-id="4a8dc-111">Na caixa de diálogo **Selecionar Computador** , na caixa de texto **Outro computador** , digite o nome do computador que você deseja administrar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-111">In the **Select Computer** dialog box, in the **Another computer** text box, type the name of the computer you want to manage, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4a8dc-112">O Computer Management exibe os serviços que estão sendo executados no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-112">Computer Management displays the services running on the remote computer.</span></span> <span data-ttu-id="4a8dc-113">O nó de nível superior é alterado para **Gerenciamento de Computador** \<*remotecomputer*>.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-113">The top-level node changes to **Computer Management** \<*remotecomputer*>.</span></span>  
  
4.  <span data-ttu-id="4a8dc-114">Na árvore de console, expanda **Serviços e Aplicativos**e expanda o **SQL Server Configuration Manager** para administrar os serviços do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-114">In the console tree, expand **Services and Applications**, and then expand **SQL Server Configuration Manager** to manage the remote computer's services.</span></span>  
  
#### <a name="to-save-a-link-to-sql-server-configuration-manager-for-another-computer"></a><span data-ttu-id="4a8dc-115">Para salvar um link no SQL Server Configuration Manager para outro computador</span><span class="sxs-lookup"><span data-stu-id="4a8dc-115">To save a link to SQL Server Configuration Manager for another computer</span></span>  
  
1.  <span data-ttu-id="4a8dc-116">No menu **Iniciar** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-116">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="4a8dc-117">Na caixa **abrir** , digite `mmc -a` para abrir o [!INCLUDE[msCoName](../../includes/msconame-md.md)] console de gerenciamento no modo de autor.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-117">In the **Open** box, type `mmc -a` to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console in author mode.</span></span>  
  
3.  <span data-ttu-id="4a8dc-118">No menu **Arquivo** , clique em **Adicionar/Remover Snap-in**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-118">On the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
4.  <span data-ttu-id="4a8dc-119">Na janela **Adicionar/Remover Snap-in** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-119">In the **Add/Remove Snap-in** window, click **Add**.</span></span>  
  
5.  <span data-ttu-id="4a8dc-120">Na janela **Adicionar Snap-in Autônomo** , clique em **Gerenciamento do Computador** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-120">In the **Add Standalone Snap-in** window, click **Computer Management** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="4a8dc-121">Na janela **Gerenciamento do Computador** , clique em **Outro computador**, digite o nome do computador remoto que deseja gerenciar e depois clique em **Terminar**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-121">In the **Computer Management** window, click **Another computer**, type the name of the remote computer you wish to manage, and then click **Finish**.</span></span>  
  
7.  <span data-ttu-id="4a8dc-122">Na janela **Adicionar Snap-in Autônomo** , clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-122">In the **Add Standalone Snap-in** window, click **Close**.</span></span>  
  
8.  <span data-ttu-id="4a8dc-123">Na janela **Adicionar/Remover Snap-in** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-123">In the **Add/Remove Snap-in** window, click **OK**.</span></span>  
  
9. <span data-ttu-id="4a8dc-124">Expanda **Gerenciamento do computador ( ***\<computer name>*** )** e **serviços e aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-124">Expand **Computer Management (***\<computer name>***)**, and **Services and Applications**.</span></span>  
  
10. <span data-ttu-id="4a8dc-125">Clique com o botão direito do mouse no **SQL Server Configuration Manager**e clique em **Nova Janela daqui**.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-125">Right-click **SQL Server Configuration Manager**, and then click **New Window from here**.</span></span>  
  
11. <span data-ttu-id="4a8dc-126">No menu **Janela**, clique em **Raiz do Console** para retornar à primeira janela e exclui-la.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-126">On the **Window** menu, click **Console Root**, to switch back to the first window, and delete the window.</span></span>  
  
12. <span data-ttu-id="4a8dc-127">No menu **arquivo** , clique em **salvar como**e salve o arquivo na pasta desejada, com um nome apropriado com a extensão de `.msc` arquivo.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-127">On the **File** menu, click **Save As**, and save the file in the desired folder, with an appropriate name with the `.msc` file extension.</span></span> <span data-ttu-id="4a8dc-128">Feche o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-128">Close the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span>  
  
13. <span data-ttu-id="4a8dc-129">Para abrir o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager no computador de destino, clique duas vezes no arquivo.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-129">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on the target computer, double-click the file.</span></span> <span data-ttu-id="4a8dc-130">Se desejar, salve um link no arquivo na área de trabalho ou no menu **Iniciar** .</span><span class="sxs-lookup"><span data-stu-id="4a8dc-130">If desired, save a link to the file on the desktop or in the **Start** menu.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4a8dc-131">Ao usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager em um computador remoto, o nome do computador não é óbvio e é possível parar erroneamente ou configurar o computador errado.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-131">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer, the computer name is not obvious and it is possible to mistakenly stop or configure the wrong computer.</span></span> <span data-ttu-id="4a8dc-132">Na guia **Serviço** , marque a caixa **Nome do Host** para confirmar o nome do computador antes de modificar um serviço.</span><span class="sxs-lookup"><span data-stu-id="4a8dc-132">On the **Service** tab, check the **Host Name** box to confirm the computer name before modifying a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8dc-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a8dc-133">See Also</span></span>  
 [<span data-ttu-id="4a8dc-134">Configurar o WMI para mostrar o status do servidor nas ferramentas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a8dc-134">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
