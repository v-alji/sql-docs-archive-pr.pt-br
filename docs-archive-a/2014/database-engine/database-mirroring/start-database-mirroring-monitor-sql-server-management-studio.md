---
title: Iniciar o Monitor de Espelhamento de Banco de Dados (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- monitoring database mirroring [SQL Server]
- Database Mirroring Monitor [SQL Server], starting
- database mirroring [SQL Server], monitoring
ms.assetid: 53165335-97ca-4f88-8e78-22f1839dee98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67c7b393b28d4d400535281c18c637146a5d8da7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568784"
---
# <a name="start-database-mirroring-monitor-sql-server-management-studio"></a><span data-ttu-id="4b5fa-102">Iniciar o Monitor de Espelhamento de Banco de Dados (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4b5fa-102">Start Database Mirroring Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="4b5fa-103">O Monitor de Espelhamento de Banco de Dados faz parte do Monitor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que é inicializado a partir do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b5fa-103">The Database Mirroring Monitor is part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Monitor, which is launched from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b5fa-104">O Monitor de Espelhamento de Banco de Dados não está disponível em todas as edições do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b5fa-104">Database Mirroring Monitor is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4b5fa-105">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="4b5fa-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
### <a name="to-launch-the-database-mirroring-monitor"></a><span data-ttu-id="4b5fa-106">Para iniciar o Monitor de Espelhamento de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="4b5fa-106">To launch the Database Mirroring Monitor</span></span>  
  
1.  <span data-ttu-id="4b5fa-107">Depois de se conectar à instância do servidor principal, no Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-107">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="4b5fa-108">Expanda os **Bancos de Dados**e selecione o banco de dados a ser monitorado.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-108">Expand **Databases**, and select the database to be monitored.</span></span>  
  
3.  <span data-ttu-id="4b5fa-109">Clique com o botão direito do mouse no banco de dados, selecione **Tarefas**e clique em **Iniciar o Monitor de Espelhamento de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-109">Right-click the database, select **Tasks**, and then click **Launch Database Mirroring Monitor**.</span></span>  
  
4.  <span data-ttu-id="4b5fa-110">Na caixa de diálogo **Monitor de Espelhamento de Banco de Dados** , clique em **Registrar Banco de Dados Espelho** para registrar um ou mais bancos de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-110">In the **Database Mirroring Monitor** dialog box, click **Register Mirrored Database** to register one or more mirrored database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4b5fa-111">Ao registrar um banco de dados em um parceiro, o banco de dados será automaticamente registrado no outro parceiro.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-111">When you register a database at one partner, the database is automatically registered at the other partner.</span></span> <span data-ttu-id="4b5fa-112">Se o monitor já tiver credenciais de conexão para a outra instância de parceiro, elas serão usadas para a conexão.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-112">If the monitor already has connection credentials for the other partner instance, those are used to connect.</span></span> <span data-ttu-id="4b5fa-113">Caso contrário o monitor tentará conectar usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-113">Otherwise the monitor attempts to connect using Windows Authentication.</span></span> <span data-ttu-id="4b5fa-114">Se você quiser alterar as credenciais usadas para conectar-se a qualquer instância de servidor, clique em **Mostrar a caixa de diálogo Gerenciar de conexões do servidor quando eu clicar em OK**.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-114">If you want to change the credentials used to connect to either server instance, click **Show the Manage Server Connections dialog box when I click OK**.</span></span>  
  
 <span data-ttu-id="4b5fa-115">Para obter mais informações sobre o Monitor de Espelhamento de Banco de Dados, veja [Visão geral do Monitor de Espelhamento de Banco de Dados](database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4b5fa-115">For more information about Database Mirroring Monitor, see [Database Mirroring Monitor Overview](database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b5fa-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4b5fa-116">See Also</span></span>  
 <span data-ttu-id="4b5fa-117">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4b5fa-117">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="4b5fa-118">Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4b5fa-118">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
  
