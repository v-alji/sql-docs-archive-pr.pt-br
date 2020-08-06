---
title: Definir uma instância de SQL Server para iniciar automaticamente (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, automatic startup
- starting SQL Server, automatically
ms.assetid: aa2b6bde-e76d-4fea-a560-54a63745d9b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2fc21bd881c1588da47710c6d8437e31d3df2ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684338"
---
# <a name="set-an-instance-of-sql-server-to-start-automatically-sql-server-configuration-manager"></a><span data-ttu-id="b191d-102">Definir uma instância do SQL Server para iniciar automaticamente (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="b191d-102">Set an Instance of SQL Server to Start Automatically (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="b191d-103">Este tópico descreve como definir uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para iniciar automaticamente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b191d-103">This topic describes how to set an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to start automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="b191d-104">Durante a instalação, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] normalmente é configurado para iniciar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b191d-104">During setup, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is normally configured to start automatically.</span></span> <span data-ttu-id="b191d-105">Se isto não foi feito, você poderá alterar essa definição a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="b191d-105">If this was not done, you can change that setting at any time.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b191d-106">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b191d-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-set-an-instance-of-sql-server-to-start-automatically"></a><span data-ttu-id="b191d-107">Para configurar uma instância do SQL Server para iniciar automaticamente</span><span class="sxs-lookup"><span data-stu-id="b191d-107">To set an instance of SQL Server to start automatically</span></span>  
  
1.  <span data-ttu-id="b191d-108">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="b191d-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b191d-109">Como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager é um snap-in do programa Console de Gerenciamento [!INCLUDE[msCoName](../../includes/msconame-md.md)] e não um programa autônomo, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager não aparece como um aplicativo nas versões mais recentes do Windows.</span><span class="sxs-lookup"><span data-stu-id="b191d-109">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="b191d-110">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="b191d-110">**Windows 10**:</span></span>  
    >          <span data-ttu-id="b191d-111">Para abrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, na **página inicial**, digite SQLServerManager12. msc (para [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="b191d-111">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="b191d-112">Para versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] substitua 12 por um número menor.</span><span class="sxs-lookup"><span data-stu-id="b191d-112">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="b191d-113">Clique em SQLServerManager12.msc para abrir o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b191d-113">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="b191d-114">Para fixar o Configuration Manager na página inicial ou na barra de tarefas, clique com o botão direito do mouse em SQLServerManager12. msc e clique em **abrir local do arquivo**.</span><span class="sxs-lookup"><span data-stu-id="b191d-114">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="b191d-115">No explorador de arquivos do Windows, clique com o botão direito do mouse em SQLServerManager12. msc e clique em **fixar para iniciar** ou **fixar na barra de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="b191d-115">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="b191d-116">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="b191d-116">**Windows 8**:</span></span>  
    >          <span data-ttu-id="b191d-117">Para abrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, no botão **Pesquisar** , em **aplicativos**, digite **SQLServerManager \<version> . msc** `SQLServerManager12.msc` , como e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="b191d-117">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="b191d-118">Em **SQL Server Configuration Manager**, expanda **Serviços**e, a seguir, clique em **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b191d-118">In **SQL Server Configuration Manager**, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="b191d-119">No painel de detalhes, clique com o botão direito do mouse no nome da instância que deseja que seja iniciada automaticamente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b191d-119">In the details pane, right-click the name of the instance you want to start automatically, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b191d-120">Na caixa de diálogo **Propriedades do SQL Server \<***instancename***>** , defina **Modo de Início** como **Automático**.</span><span class="sxs-lookup"><span data-stu-id="b191d-120">In the **SQL Server \<***instancename***> Properties** dialog box, set **Start Mode** to **Automatic**.</span></span>  
  
5.  <span data-ttu-id="b191d-121">Clique em **OK**e em seguida feche o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Gerenciador de Configuração.</span><span class="sxs-lookup"><span data-stu-id="b191d-121">Click **OK**, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b191d-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b191d-122">See Also</span></span>  
 <span data-ttu-id="b191d-123">[Impedir a inicialização automática de uma instância do SQL Server &#40;SQL Server Configuration Manager&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span><span class="sxs-lookup"><span data-stu-id="b191d-123">[Prevent Automatic Startup of an Instance of SQL Server &#40;SQL Server Configuration Manager&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span></span>  
 <span data-ttu-id="b191d-124">[Conectar-se a outro computador &#40;SQL Server Configuration Manager&#41;](scm-services-connect-to-another-computer.md) </span><span class="sxs-lookup"><span data-stu-id="b191d-124">[Connect to Another Computer &#40;SQL Server Configuration Manager&#41;](scm-services-connect-to-another-computer.md) </span></span>  
 [<span data-ttu-id="b191d-125">Configurar o WMI para mostrar o status do servidor nas ferramentas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b191d-125">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
