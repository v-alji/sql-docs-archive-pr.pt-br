---
title: Exibir resultados da política de integridade de recursos (Utilitário do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 80cb14fb-f4c6-4be2-ba17-eb4e4cddd35f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4ab30ad0e87782f8187370a53747be4cf5d313d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680921"
---
# <a name="view-resource-health-policy-results-sql-server-utility"></a><span data-ttu-id="0aff2-102">Exibir resultados da política de integridade de recursos (Utilitário do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0aff2-102">View Resource Health Policy Results (SQL Server Utility)</span></span>
  <span data-ttu-id="0aff2-103">Use o painel (dashboard) do Utilitário do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para exibir parâmetros de recursos do Utilitário do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e de aplicativos da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="0aff2-103">Use the Utility dashboard in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="0aff2-104">Para obter mais informações, consulte [Recursos e tarefas do utilitário do SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="0aff2-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="view-sql-server-utility-resource-health-policy-results"></a><span data-ttu-id="0aff2-105">Exibir resultados da política de integridade de recursos do Utilitário do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0aff2-105">View SQL Server Utility resource health policy results.</span></span>  
  
1.  <span data-ttu-id="0aff2-106">No SSMS ( [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ), clique em **Exibir**e em **Gerenciador do Utilitário** para exibir o painel de navegação do Gerenciador do Utilitário.</span><span class="sxs-lookup"><span data-stu-id="0aff2-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS), click **View**, then click **Utility Explorer** to view the Utility Explorer navigation pane.</span></span> <span data-ttu-id="0aff2-107">Para exibir o painel de conteúdo, clique em **Exibir**e em **Conteúdo do Gerenciador do Utilitário**.</span><span class="sxs-lookup"><span data-stu-id="0aff2-107">To view the content pane, click **View**, then click **Utility Explorer Content**.</span></span>  
  
2.  <span data-ttu-id="0aff2-108">No painel de navegação, clique em ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Conectar ao Utilitário**.</span><span class="sxs-lookup"><span data-stu-id="0aff2-108">In the navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span> <span data-ttu-id="0aff2-109">Se você não criou um UCP (ponto de controle do utilitário) ou se não inscreveu instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou aplicativos da camada de dados no Utilitário do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , consulte [Recursos e tarefas do Utilitário do SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="0aff2-109">If you have not created a utility control point (UCP) or if you have not enrolled instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or data-tier applications into the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
3.  <span data-ttu-id="0aff2-110">Clique no nó do UCP para exibir dados de resumo das instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e de aplicativos da camada de dados (clique com o botão direito do mouse para atualizar).</span><span class="sxs-lookup"><span data-stu-id="0aff2-110">Click the UCP node to view summary data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="0aff2-111">Dados do painel são exibidos no painel de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0aff2-111">Dashboard data is displayed in the content pane.</span></span>  
  
4.  <span data-ttu-id="0aff2-112">Clique no nó **Instâncias Gerenciadas** para exibir dados de exibição de lista das instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (clique com o botão direito do mouse para atualizar).</span><span class="sxs-lookup"><span data-stu-id="0aff2-112">Click the **Managed Instances** node to view list view data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (right-click to refresh).</span></span> <span data-ttu-id="0aff2-113">Dados de exibição de lista são exibidos no painel de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0aff2-113">List view data is displayed in the content pane.</span></span>  
  
5.  <span data-ttu-id="0aff2-114">Clique no nó **Aplicativos da Camada de Dados Implantados** para exibir dados da exibição de lista dos aplicativos da camada de dados (clique com o botão direito do mouse para atualizar).</span><span class="sxs-lookup"><span data-stu-id="0aff2-114">Click the **Deployed Data-tier Applications** node to view list view data for data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="0aff2-115">Dados de exibição de lista são exibidos no painel de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0aff2-115">List view data is displayed in the content pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aff2-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0aff2-116">See Also</span></span>  
 <span data-ttu-id="0aff2-117">[Recursos e tarefas do Utilitário do SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="0aff2-117">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="0aff2-118">[Reduzir o ruído em políticas de utilização da CPU &#40;Utilitário do SQL Server&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0aff2-118">[Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span></span>  
 <span data-ttu-id="0aff2-119">[Detalhes do aplicativo da camada de dados implantado &#40;Utilitário do SQL Server&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0aff2-119">[Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span></span>  
 <span data-ttu-id="0aff2-120">[Detalhes de instâncias gerenciadas &#40;Utilitário do SQL Server&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0aff2-120">[Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="0aff2-121">Administração do Utilitário &#40;Utilitário do SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0aff2-121">Utility Administration &#40;SQL Server Utility&#41;</span></span>](../../database-engine/utility-administration-sql-server-utility.md)  
  
  
