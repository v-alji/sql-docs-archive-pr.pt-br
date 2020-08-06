---
title: Métodos de renderização e execução | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0bc793e9a18e993989563fd3526ff12272f775c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683395"
---
# <a name="rendering-and-execution-methods"></a><span data-ttu-id="0ed10-102">Métodos de renderização e execução</span><span class="sxs-lookup"><span data-stu-id="0ed10-102">Rendering and Execution Methods</span></span>
  <span data-ttu-id="0ed10-103">Você pode usar estes métodos para gerenciar a execução e o cache de itens e a renderização de relatórios.</span><span class="sxs-lookup"><span data-stu-id="0ed10-103">You can use these methods to manage item execution and caching, and report rendering.</span></span>  
  
|<span data-ttu-id="0ed10-104">Método</span><span class="sxs-lookup"><span data-stu-id="0ed10-104">Method</span></span>|<span data-ttu-id="0ed10-105">Ação</span><span class="sxs-lookup"><span data-stu-id="0ed10-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|<span data-ttu-id="0ed10-106">Invalida o cache de um item.</span><span class="sxs-lookup"><span data-stu-id="0ed10-106">Invalidates the cache for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|<span data-ttu-id="0ed10-107">Retorna a configuração de cache de um item e as configurações que descrevem quando a cópia do item armazenada em cache irá expirar.</span><span class="sxs-lookup"><span data-stu-id="0ed10-107">Returns the cache configuration for an item and the settings that describe when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|<span data-ttu-id="0ed10-108">Retorna a opção de execução e as configurações associadas de um item individual.</span><span class="sxs-lookup"><span data-stu-id="0ed10-108">Returns the execution option and associated settings for an individual item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|<span data-ttu-id="0ed10-109">Retorna uma lista de configurações de execução com suporte.</span><span class="sxs-lookup"><span data-stu-id="0ed10-109">Returns a list of supported execution settings.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|<span data-ttu-id="0ed10-110">Processa o relatório especificado e o renderiza em um formato especificado.</span><span class="sxs-lookup"><span data-stu-id="0ed10-110">Processes the specified report and renders it in a specified format.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|<span data-ttu-id="0ed10-111">Configura um item a ser armazenado em cache e fornece configurações que especificam quando a cópia do item armazenada em cache irá expirar.</span><span class="sxs-lookup"><span data-stu-id="0ed10-111">Configures an item to be cached and provides settings that specify when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|<span data-ttu-id="0ed10-112">Define as opções de execução e as propriedades de execução associadas de um item individual.</span><span class="sxs-lookup"><span data-stu-id="0ed10-112">Sets execution options and associated execution properties for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|<span data-ttu-id="0ed10-113">Gera um instantâneo da execução de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="0ed10-113">Generates an item execution snapshot for a specified item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ed10-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ed10-114">See Also</span></span>  
 <span data-ttu-id="0ed10-115">[Criando aplicativos usando o serviço Web e o .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="0ed10-115">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="0ed10-116">[Serviço Web Servidor de Relatórios](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="0ed10-116">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="0ed10-117">[Métodos do serviço Web Servidor de Relatórios](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="0ed10-117">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="0ed10-118">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0ed10-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
