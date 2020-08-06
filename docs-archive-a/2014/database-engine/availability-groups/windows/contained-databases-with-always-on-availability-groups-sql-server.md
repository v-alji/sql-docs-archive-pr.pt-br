---
title: Bancos de dados independentes com Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- contained database [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: cacce3ae-e940-4566-8298-6607c4268e74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74c8a0b41ee7224dad83fb41691a4898c15b7b38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569664"
---
# <a name="contained-databases-with-always-on-availability-groups-sql-server"></a><span data-ttu-id="72b81-102">Bancos de dados independentes com grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="72b81-102">Contained Databases with Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="72b81-103">Este tópico contém informações sobre como usar um banco de dados independente com o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72b81-103">This topic contains information about the using a contained database with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="72b81-104">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="72b81-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="72b81-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="72b81-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="72b81-106">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="72b81-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="72b81-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="72b81-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="72b81-108">Antes de adicionar um banco de dados independente a um grupo de disponibilidade, verifique se a opção de servidor `contained database authentication` está definida como `1` em cada instância de servidor que hospeda uma réplica de disponibilidade do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="72b81-108">Before adding a contained database to an availability group, ensure that the `contained database authentication` server option is set to `1` on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="72b81-109">Para obter mais informações, veja [Opção contained database authentication de configuração de servidor](../../configure-windows/contained-database-authentication-server-configuration-option.md) e [Opções de configuração do servidor &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="72b81-109">For more information, see [contained database authentication Server Configuration Option](../../configure-windows/contained-database-authentication-server-configuration-option.md) and [Server Configuration Options &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="72b81-110">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="72b81-110">Related Tasks</span></span>  
  
-   [<span data-ttu-id="72b81-111">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="72b81-111">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="72b81-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72b81-112">See Also</span></span>  
 <span data-ttu-id="72b81-113">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="72b81-113">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="72b81-114">Bancos de dados independentes</span><span class="sxs-lookup"><span data-stu-id="72b81-114">Contained Databases</span></span>](../../../relational-databases/databases/contained-databases.md)  
  
  
