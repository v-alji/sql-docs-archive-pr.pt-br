---
title: Fontes de dados e métodos de conexão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- connections [Reporting Services], data sources
- reports [Reporting Services], data
- data sources [Reporting Services], methods
ms.assetid: 50999b52-fc7c-4333-9fb0-d04c37a4c90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29dd8dd1c002ab3b7d4594a4e25ec44bdb2cc8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683402"
---
# <a name="data-sources-and-connection-methods"></a><span data-ttu-id="13ff2-102">Fontes de dados e métodos de conexão</span><span class="sxs-lookup"><span data-stu-id="13ff2-102">Data Sources and Connection Methods</span></span>
  <span data-ttu-id="13ff2-103">Você pode usar estes métodos para definir e gerenciar conexões e credenciais da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="13ff2-103">You can use these methods to set and manage data source connections and credentials.</span></span>  
  
|<span data-ttu-id="13ff2-104">Método</span><span class="sxs-lookup"><span data-stu-id="13ff2-104">Method</span></span>|<span data-ttu-id="13ff2-105">Ação</span><span class="sxs-lookup"><span data-stu-id="13ff2-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateDataSource%2A>|<span data-ttu-id="13ff2-106">Cria uma nova fonte de dados no banco de dados do servidor de relatório ou na biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="13ff2-106">Creates a new data source in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DisableDataSource%2A>|<span data-ttu-id="13ff2-107">Desabilita uma fonte de dados que está habilitada.</span><span class="sxs-lookup"><span data-stu-id="13ff2-107">Disables a data source that is enabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.EnableDataSource%2A>|<span data-ttu-id="13ff2-108">Habilita uma fonte de dados que está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="13ff2-108">Enables a data source that is disabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetDataSourceContents%2A>|<span data-ttu-id="13ff2-109">Retorna o conteúdo de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="13ff2-109">Returns the contents of a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSourcePrompts%2A>|<span data-ttu-id="13ff2-110">Obtém os avisos de fonte de dados de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="13ff2-110">Gets the data source prompts for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSources%2A>|<span data-ttu-id="13ff2-111">Retorna as fontes de dados de um item no catálogo.</span><span class="sxs-lookup"><span data-stu-id="13ff2-111">Returns the data sources for an item in the catalog.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListDependentItems%2A>|<span data-ttu-id="13ff2-112">Retorna uma lista dos itens de catálogo que fazem referência a um item de catálogo especificado.</span><span class="sxs-lookup"><span data-stu-id="13ff2-112">Returns a list of catalog items that reference a specified catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSubscriptionsUsingDataSource%2A>|<span data-ttu-id="13ff2-113">Retorna uma lista de assinaturas associadas a uma determinada fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="13ff2-113">Returns a list of subscriptions that are associated with a given data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetDataSourceContents%2A>|<span data-ttu-id="13ff2-114">Define as propriedades da conexão associadas a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="13ff2-114">Sets the connection properties that are associated with a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetItemDataSources%2A>|<span data-ttu-id="13ff2-115">Define as fontes de dados de um item em um banco de dados do servidor de relatório ou na biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="13ff2-115">Sets the data sources for an item in a report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForDataSourceDefinition%2A>|<span data-ttu-id="13ff2-116">Testa a conexão de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="13ff2-116">Tests the connection for a data source.</span></span> <span data-ttu-id="13ff2-117">Esse método oferece suporte aos testes diretos da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="13ff2-117">This method supports the direct testing of the data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForItemDataSource%2A>|<span data-ttu-id="13ff2-118">Testa a conexão de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="13ff2-118">Tests the connection for a data source.</span></span> <span data-ttu-id="13ff2-119">Esse método dá suporte aos testes de fontes de dados publicadas usadas por relatórios ou modelos e fontes de dados compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="13ff2-119">This method supports the testing of published data sources that are used by reports or models and shared data sources.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13ff2-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="13ff2-120">See Also</span></span>  
 <span data-ttu-id="13ff2-121">[Criando aplicativos usando o serviço Web e o .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="13ff2-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="13ff2-122">[Serviço Web Servidor de Relatórios](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="13ff2-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="13ff2-123">[Métodos do serviço Web Servidor de Relatórios](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="13ff2-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="13ff2-124">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="13ff2-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
