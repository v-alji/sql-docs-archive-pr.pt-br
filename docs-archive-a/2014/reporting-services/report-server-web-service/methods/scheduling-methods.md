---
title: Métodos de agendamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- schedules [Reporting Services], methods
- reports [Reporting Services], scheduling
- shared schedules [Reporting Services], methods
- methods [Reporting Services], scheduling
ms.assetid: 68ae13f9-d91e-4572-a82a-8fa42001569e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 735da4f22d523fd40dd031f55e203fa9a4204f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570432"
---
# <a name="scheduling-methods"></a><span data-ttu-id="9b4ef-102">Métodos de agendamento</span><span class="sxs-lookup"><span data-stu-id="9b4ef-102">Scheduling Methods</span></span>
  <span data-ttu-id="9b4ef-103">É possível usar esses métodos para criar e gerenciar agendas compartilhadas para execução e entrega de relatório e para planos de atualização do cache utilizados pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-103">You can use these methods to create and manage shared schedules for report execution and delivery, and to cache refresh plans utilized by the report server.</span></span>  
  
|<span data-ttu-id="9b4ef-104">Método</span><span class="sxs-lookup"><span data-stu-id="9b4ef-104">Method</span></span>|<span data-ttu-id="9b4ef-105">Ação</span><span class="sxs-lookup"><span data-stu-id="9b4ef-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateCacheRefreshPlan%2A>|<span data-ttu-id="9b4ef-106">Cria um plano de atualização do cache para um item.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-106">Creates a cache refresh plan for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateSchedule%2A>|<span data-ttu-id="9b4ef-107">Cria uma nova agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-107">Creates a new shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteCacheRefreshPlan%2A>|<span data-ttu-id="9b4ef-108">Exclui um plano de atualização do cache.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-108">Deletes a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteSchedule%2A>|<span data-ttu-id="9b4ef-109">Exclui uma agenda compartilhada com base em uma ID de agenda específica.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-109">Deletes a shared schedule based on a specific schedule ID.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheRefreshPlanProperties%2A>|<span data-ttu-id="9b4ef-110">Retorna as propriedades do plano de atualização do cache especificado.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-110">Returns the properties of the specified cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetScheduleProperties%2A>|<span data-ttu-id="9b4ef-111">Retorna os valores de propriedades de uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-111">Returns the values of properties of a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListCacheRefreshPlans%2A>|<span data-ttu-id="9b4ef-112">Retorna uma lista dos planos de atualização do cache associados a um item do catálogo.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-112">Returns a list of the cache refresh plans associated with a catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduledItems%2A>|<span data-ttu-id="9b4ef-113">Retorna uma lista de itens associados a uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-113">Returns a list of items that are associated with a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSchedules%2A>|<span data-ttu-id="9b4ef-114">Retorna uma lista de todas as agendas compartilhadas no servidor de relatório ou no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-114">Returns a list of all shared schedules at the report server or the SharePoint site.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduleStates%2A>|<span data-ttu-id="9b4ef-115">Retorna uma lista de estados de agenda com suporte.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-115">Returns a list of supported schedule states.</span></span>|  
|<xref:ReportService2010.ReportingService2010.PauseSchedule%2A>|<span data-ttu-id="9b4ef-116">Pausa a execução de uma determinada agenda.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-116">Pauses the execution of a given schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ResumeSchedule%2A>|<span data-ttu-id="9b4ef-117">Retoma uma agenda compartilhada que foi pausada.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-117">Resumes a shared schedule that has been paused.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheRefreshPlanProperties%2A>|<span data-ttu-id="9b4ef-118">Define as propriedades de um plano de atualização do cache.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-118">Sets the properties of a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetScheduleProperties%2A>|<span data-ttu-id="9b4ef-119">Define o valor de propriedades de uma agenda compartilhada.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-119">Sets the value of properties of a shared schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b4ef-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b4ef-120">See Also</span></span>  
 <span data-ttu-id="9b4ef-121">[Criando aplicativos usando o serviço Web e o .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="9b4ef-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="9b4ef-122">[Serviço Web Servidor de Relatórios](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="9b4ef-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="9b4ef-123">[Métodos do serviço Web Servidor de Relatórios](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="9b4ef-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="9b4ef-124">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b4ef-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
