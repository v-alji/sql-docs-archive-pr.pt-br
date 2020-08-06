---
title: Alterar a conta proxy para o conjunto de coleta do utilitário em um Instância Gerenciada de SQL Server (Utilitário do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ff37ba8b-a08c-4109-b6e2-5748c995a52c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19f60c607ed661ef42c1c1c0e48854cdfd69a912
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570697"
---
# <a name="change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server-sql-server-utility"></a><span data-ttu-id="533b3-102">Alterar a conta proxy para o conjunto de coleta do utilitário em uma instância gerenciada do SQL Server (Utilitário do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="533b3-102">Change the Proxy Account for the Utility Collection Set on a Managed Instance of SQL Server (SQL Server Utility)</span></span>
  <span data-ttu-id="533b3-103">Este tópico descreve como alterar a conta proxy para o Conjunto de Coleta do Utilitário em uma instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="533b3-103">This topic describes how to change the proxy account for the Utility Collection Set on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="533b3-104">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="533b3-104">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server"></a><span data-ttu-id="533b3-105">Para alterar a conta proxy do conjunto de coleta do utilitário em uma instância gerenciada do SQL Server</span><span class="sxs-lookup"><span data-stu-id="533b3-105">To change the proxy account for the utility collection set on a managed instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="533b3-106">Remova a instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span><span class="sxs-lookup"><span data-stu-id="533b3-106">Remove the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
    -   <span data-ttu-id="533b3-107">No **Gerenciador do Utilitário** no SSMS, clique no nó **Instâncias Gerenciadas** .</span><span class="sxs-lookup"><span data-stu-id="533b3-107">In **Utility Explorer** in SSMS, click on the **Managed Instances** node.</span></span>  
  
    -   <span data-ttu-id="533b3-108">Na exibição de lista do **Gerenciador do Utilitário**, clique com o botão direito do mouse no nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e selecione **Remover Instância Gerenciada...** . Para obter mais informações, veja [Remover uma instância do SQL Server do Utilitário do SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="533b3-108">In the **Utility Explorer** list view, right-click the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name, and select **Remove Managed Instance...**. For more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
2.  <span data-ttu-id="533b3-109">Inscreva a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] novamente.</span><span class="sxs-lookup"><span data-stu-id="533b3-109">Enroll the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility again.</span></span>  
  
    -   <span data-ttu-id="533b3-110">No **Gerenciador do Utilitário** no SSMS, clique com o botão direito do mouse no nó **Instâncias Gerenciadas** e selecione **Adicionar Instância Gerenciada...** .</span><span class="sxs-lookup"><span data-stu-id="533b3-110">In **Utility Explorer** in SSMS, right-click on the **Managed Instances** node, and select **Add Managed Instance...**.</span></span>  
  
    -   <span data-ttu-id="533b3-111">Siga os prompts para concluir o assistente, especificando a nova conta proxy.</span><span class="sxs-lookup"><span data-stu-id="533b3-111">Follow prompts to complete the wizard, specifying the new proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533b3-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="533b3-112">See Also</span></span>  
 <span data-ttu-id="533b3-113">[Recursos e tarefas do Utilitário do SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="533b3-113">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="533b3-114">Solucionar problemas do Utilitário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="533b3-114">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
