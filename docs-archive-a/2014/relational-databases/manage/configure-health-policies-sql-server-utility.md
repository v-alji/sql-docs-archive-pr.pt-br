---
title: Configurar políticas de integridade (Utilitário do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 030aac3b-8901-4c41-91ed-aba96420276c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c5ee466dd2d5bac2ea64364bfc78de8f2f5bea10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570696"
---
# <a name="configure-health-policies-sql-server-utility"></a><span data-ttu-id="19daf-102">Configurar políticas de integridade (Utilitário do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="19daf-102">Configure Health Policies (SQL Server Utility)</span></span>
  <span data-ttu-id="19daf-103">Use o painel do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para exibir parâmetros de recursos do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e aplicativos da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="19daf-103">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility dashboard in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="19daf-104">Para obter mais informações, consulte [Recursos e tarefas do utilitário do SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="19daf-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="19daf-105">Para exibir os resultados da política de integridade do Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , conecte-se a um ponto de controle de utilitário no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19daf-105">To view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility health policy results, connect to a utility control point from [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="19daf-106">Para obter mais informações, consulte [Usar o Gerenciador do Utilitário para gerenciar o Utilitário do SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="19daf-106">For more information, see [Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="19daf-107">As políticas de integridade do Utilitário podem ser configuradas para aplicativos da camada de dados e instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19daf-107">Utility health policies can be configured for data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="19daf-108">As políticas de integridade podem ser definidas globalmente para todos os aplicativos da camada de dados e instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou podem ser definidas individualmente para cada aplicativo da camada de dados e para cada instância gerenciada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19daf-108">Health policies can be defined globally for all data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, or they can be defined individually for each data-tier application and for each managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
## <a name="monitoring-policies-for-data-tier-applications"></a><span data-ttu-id="19daf-109">Monitorando políticas para aplicativos da camada de dados</span><span class="sxs-lookup"><span data-stu-id="19daf-109">Monitoring Policies for Data-tier Applications</span></span>  
 <span data-ttu-id="19daf-110">As políticas de superutilização e subutilização para aplicativos da camada de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="19daf-110">Overutilization and underutilization policies for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data-tier applications are as follows:</span></span>  
  
-   <span data-ttu-id="19daf-111">Utilização do processador de aplicativo da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="19daf-111">Data-tier application processor utilization.</span></span>  
  
-   <span data-ttu-id="19daf-112">Espaço de arquivo de aplicativo da camada de dados para arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="19daf-112">Data-tier application file space for database files.</span></span>  
  
-   <span data-ttu-id="19daf-113">Espaço de arquivo de aplicativo da camada de dados para volumes de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="19daf-113">Data-tier application file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="19daf-114">Utilização do processador do computador.</span><span class="sxs-lookup"><span data-stu-id="19daf-114">Computer processor utilization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19daf-115">O volume de armazenamento e a utilização do processador são políticas somente leitura para aplicativos da camada de dados.</span><span class="sxs-lookup"><span data-stu-id="19daf-115">Storage volume and processor utilization are read-only policies for data-tier applications.</span></span>  
  
 <span data-ttu-id="19daf-116">Para obter mais informações sobre como exibir ou alterar políticas de monitoramento globais para aplicativos da camada de dados, consulte [Administração do Utilitário &#40;Utilitário do SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="19daf-116">For more information about viewing or changing global monitoring policies for data-tier applications, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="19daf-117">Para obter mais informações sobre como exibir ou alterar as políticas de monitoramento para aplicativos da camada de dados individuais, consulte [Detalhes do aplicativo da camada de dados implantado &#40;Utilitário do SQL Server&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="19daf-117">For more information about viewing or changing monitoring policies for individual data-tier applications, see [Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span></span>  
  
## <a name="monitoring-policies-for-managed-instances-of-sql-server"></a><span data-ttu-id="19daf-118">Políticas de monitoramento para instâncias gerenciadas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="19daf-118">Monitoring Policies for Managed Instances of SQL Server</span></span>  
 <span data-ttu-id="19daf-119">As políticas de superutilização e de subutilização para instâncias gerenciadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="19daf-119">Overutilization and underutilization policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are as follows:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="19daf-120">.</span><span class="sxs-lookup"><span data-stu-id="19daf-120">instance processor utilization.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="19daf-121">para arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="19daf-121">instance file space for database files.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="19daf-122">para volumes de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="19daf-122">instance file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="19daf-123">Utilização do processador do computador.</span><span class="sxs-lookup"><span data-stu-id="19daf-123">Computer processor utilization.</span></span>  
  
 <span data-ttu-id="19daf-124">Para obter mais informações sobre como exibir ou alterar políticas de monitoramento globais para instâncias gerenciadas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Administração do Utilitário &#40;Utilitário do SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="19daf-124">For more information about viewing or changing global monitoring policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="19daf-125">Para obter mais informações sobre como exibir ou alterar as políticas de monitoramento para instâncias gerenciadas individuais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Detalhes de instâncias gerenciadas &#40;Utilitário do SQL Server&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="19daf-125">For more information about viewing or changing monitoring policies for individual managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19daf-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="19daf-126">See Also</span></span>  
 <span data-ttu-id="19daf-127">[Recursos e tarefas do Utilitário do SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="19daf-127">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="19daf-128">Reduzir o ruído em políticas de utilização da CPU &#40;Utilitário do SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19daf-128">Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;</span></span>](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md)  
  
  
