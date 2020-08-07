---
title: Propriedades de SQL Server (guia alta disponibilidade AlwaysOn) | Microsoft Docs
description: Saiba como ativar ou desativar o recurso Grupos de Disponibilidade AlwaysOn no SQL Server 2014. Exiba os pré-requisitos que a instância de servidor deve atender a esse recurso.
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d8630923-a600-4f1c-aca1-027453a3ec82
author: mikeraymsft
ms.author: mikeray
ms.openlocfilehash: 3939b40a334746e9ee96441338e2e50791987103
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682029"
---
# <a name="sql-server-properties-alwayson-high-availability-tab"></a><span data-ttu-id="0e6b7-104">Propriedades do SQL Server (guia Alta disponibilidade AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="0e6b7-104">SQL Server Properties (AlwaysOn High Availability Tab)</span></span>
  <span data-ttu-id="0e6b7-105">Use a guia **Alta disponibilidade AlwaysOn** da caixa de diálogo **Propriedades do SQL Server** no Gerenciador de Configuração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para habilitar ou desabilitar o recurso Grupos de Disponibilidade AlwaysOn no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e6b7-105">Use the **AlwaysOn High Availability** tab of the **SQL Server Properties** dialog box in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to enable or disable the AlwaysOn Availability Groups feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="0e6b7-106">Habilitar os Grupos de Disponibilidade AlwaysOn é pré-requisito para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usar grupos de disponibilidade como uma solução de recuperação de desastres de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-106">Enabling AlwaysOn Availability Groups is a prerequisite for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use availability groups as a high availability and disaster recovery solution.</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="0e6b7-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0e6b7-107">Prerequisites</span></span>  
 <span data-ttu-id="0e6b7-108">Para estar habilitada para Grupos de Disponibilidade AlwaysOn, uma instância de servidor deve atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="0e6b7-108">To be enabled for AlwaysOn Availability Groups, a server instance must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="0e6b7-109">A instância de servidor deve residir em um nó WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="0e6b7-109">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="0e6b7-110">Para estar no mesmo grupo de disponibilidade, as instâncias devem estar no mesmo cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-110">To be in the same availability group, instances must be in the same WSFC cluster.</span></span> <span data-ttu-id="0e6b7-111">Um grupo de disponibilidade não pode abranger clusters de WSFC.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-111">An availability group cannot span WSFC clusters.</span></span>  
  
-   <span data-ttu-id="0e6b7-112">A instância de servidor deve estar executando uma edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que dá suporte a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e6b7-112">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
-   <span data-ttu-id="0e6b7-113">Habilitar Grupos de Disponibilidade AlwaysOn para somente uma instância de servidor de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-113">Enable AlwaysOn Availability Groups for only one server instance at a time.</span></span> <span data-ttu-id="0e6b7-114">Depois de habilitar os Grupos de Disponibilidade AlwaysOn, aguarde até que o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tenha reiniciado antes de habilitar a próxima instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-114">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has restarted before you enable the next server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e6b7-115">Para obter informações sobre suporte a recursos e informações sobre pré-requisitos adicionais, restrições e recomendações para [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], consulte os Manuais Online do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e6b7-115">For information about feature support and for information about additional prerequisites, restrictions, and recommendations for [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
## <a name="dialog-options"></a><span data-ttu-id="0e6b7-116">Opções da caixa de diálogo</span><span class="sxs-lookup"><span data-stu-id="0e6b7-116">Dialog Options</span></span>  
 <span data-ttu-id="0e6b7-117">**Nome do cluster de failover do Windows**</span><span class="sxs-lookup"><span data-stu-id="0e6b7-117">**Windows failover cluster name**</span></span>  
 <span data-ttu-id="0e6b7-118">Exibe o nome do cluster WSFC no qual o computador local é um nó.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-118">Displays the name of the WSFC cluster in which the local computer is a node.</span></span>  
  
 <span data-ttu-id="0e6b7-119">**Habilitar Grupos de Disponibilidade AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="0e6b7-119">**Enable AlwaysOn Availability Groups**</span></span>  
 <span data-ttu-id="0e6b7-120">Use essa caixa de seleção para habilitar ou desabilitar os Grupos de Disponibilidade AlwaysOn nessa instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0e6b7-120">Use this check box to enable or disable AlwaysOn Availability Groups on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as follows:</span></span>  
  
-   <span data-ttu-id="0e6b7-121">Se essa caixa de seleção estiver vazia, os Grupos de Disponibilidade AlwaysOn estarão desabilitados no momento.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-121">If this check box is empty, AlwaysOn Availability Groups is currently disabled.</span></span> <span data-ttu-id="0e6b7-122">Para habilitar os Grupos de Disponibilidade AlwaysOn, marque essa caixa de seleção, clique em **OK**e reinicie manualmente o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e6b7-122">To enable AlwaysOn Availability Groups, select this check box, click **OK**, and manually restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="0e6b7-123">Se essa caixa de seleção já estiver selecionada, os Grupos de Disponibilidade AlwaysOn estarão habilitados no momento.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-123">If this check box is already selected, AlwaysOn Availability Groups is currently enabled.</span></span> <span data-ttu-id="0e6b7-124">Para desabilitar os Grupos de Disponibilidade AlwaysOn, desmarque a caixa de seleção e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-124">To disable AlwaysOn Availability Groups, uncheck the check box and click **OK**.</span></span> <span data-ttu-id="0e6b7-125">Isso faz a instância de servidor ser reiniciada.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-125">This causes the server instance to restart.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="0e6b7-126">Depois de desabilitar os Grupos de Disponibilidade AlwaysOn, você deve remover as réplicas de disponibilidade locais da instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-126">After disabling AlwaysOn Availability Groups, you should remove any local availability replicas from the server instance.</span></span> <span data-ttu-id="0e6b7-127">Se você remover a última réplica de um determinado grupo de disponibilidade, também deverá remover o grupo.</span><span class="sxs-lookup"><span data-stu-id="0e6b7-127">If you remove the last replica of a given availability group, you should also remove the group.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="0e6b7-128">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="0e6b7-128">UI element list</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e6b7-129">Para obter mais informações sobre o acompanhamento depois de desabilitar os Grupos de Disponibilidade AlwaysOn e para obter informações sobre como criar e configurar grupos de disponibilidade, consulte os Manuais Online do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e6b7-129">For more information about follow up after you disable AlwaysOn Availability Groups and for information about how to create and configure availability groups, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
