---
title: Impedir a inicialização automática de uma instância do SQL Server (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, stopping
- SQL Server, automatic startup
- canceling automatic startup
- stopping SQL Server
- preventing automatic startups [SQL Server]
ms.assetid: 782663cf-f3d7-4cc6-b621-21e4550f0322
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f93f5abc749f589ab4208b3a4c9434ca63b8769
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574903"
---
# <a name="prevent-automatic-startup-of-an-instance-of-sql-server-sql-server-configuration-manager"></a><span data-ttu-id="d9891-102">Impedir a inicialização automática de uma instância do SQL Server (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="d9891-102">Prevent Automatic Startup of an Instance of SQL Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="d9891-103">Este tópico descreve como impedir que uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicie automaticamente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d9891-103">This topic describes how prevent an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from starting automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d9891-104">é normalmente configurado para iniciar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d9891-104">is normally configured to start automatically.</span></span> <span data-ttu-id="d9891-105">Você pode alterar isso definindo o modo de início da instância como manual.</span><span class="sxs-lookup"><span data-stu-id="d9891-105">You can change that by setting the start mode for the instance to manual.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d9891-106">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d9891-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-prevent-automatic-startup-of-an-instance-of-sql-server"></a><span data-ttu-id="d9891-107">Para evitar a inicialização automática de uma instância do SQL Server</span><span class="sxs-lookup"><span data-stu-id="d9891-107">To prevent automatic startup of an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="d9891-108">No menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], aponte para **Ferramentas de Configuração**e clique em **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="d9891-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="d9891-109">No SQL Server Configuration Manager, expanda **Serviços**e clique em **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d9891-109">In SQL Server Configuration Manager, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="d9891-110">No painel detalhes, clique com o botão direito do mouse em **MSSQLServer**e clique em **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="d9891-110">In the details pane, right-click **MSSQLServer**, and then click **Properties.**</span></span>  
  
4.  <span data-ttu-id="d9891-111">Na caixa de diálogo \*\* \<**_instancename_**> propriedades do SQL Server\*\* , na **caixa Propriedades** , defina o valor do **modo de início** como **manual**.</span><span class="sxs-lookup"><span data-stu-id="d9891-111">In the **SQL Server \<**_instancename_**> Properties** dialog box, in the **Properties** box, set the value of **Start Mode** to **Manual**.</span></span>  
  
5.  <span data-ttu-id="d9891-112">Clique em **OK** para fechar a caixa de diálogo **Propriedades de \<**_instancename_**> do SQL Server** e feche o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d9891-112">Click **OK** to close the **SQL Server \<**_instancename_**> Properties** dialog box, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9891-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9891-113">See Also</span></span>  
 [<span data-ttu-id="d9891-114">Iniciar, parar, pausar, retomar, reiniciar o mecanismo de banco de dados, o SQL Server Agent ou o serviço SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="d9891-114">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
