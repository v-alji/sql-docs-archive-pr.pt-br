---
title: Propriedades do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61f1f50ea7a49acc616a36a4eaf1d3d5fcdf269a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679668"
---
# <a name="reporting-services-properties"></a><span data-ttu-id="654bf-102">Propriedades do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="654bf-102">Reporting Services Properties</span></span>
  <span data-ttu-id="654bf-103">O servidor de relatório define um conjunto de propriedades do sistema globais para ele e um conjunto de propriedades de item associadas a um item individual armazenado no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="654bf-103">The report server defines a set of system properties that are global to the report server and a set of item properties that are associated with an individual item stored in the report server database.</span></span> <span data-ttu-id="654bf-104">As propriedades definidas pelo servidor de relatório não podem ser excluídas e, em alguns casos, são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="654bf-104">Properties defined by the report server cannot be deleted, and in some cases they are read-only.</span></span> <span data-ttu-id="654bf-105">Um aplicativo pode estender as propriedades do sistema e as propriedades do item acrescentando propriedades definidas pelo usuário adicionais a elas.</span><span class="sxs-lookup"><span data-stu-id="654bf-105">An application can extend system properties and item properties by adding additional user-defined properties to the system and item properties.</span></span>  
  
 <span data-ttu-id="654bf-106">Os métodos de serviço Web a seguir recuperam e definem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Propriedades.</span><span class="sxs-lookup"><span data-stu-id="654bf-106">The following Web service methods retrieve and set [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] properties.</span></span>  
  
|<span data-ttu-id="654bf-107">Método</span><span class="sxs-lookup"><span data-stu-id="654bf-107">Method</span></span>|<span data-ttu-id="654bf-108">Ação</span><span class="sxs-lookup"><span data-stu-id="654bf-108">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|<span data-ttu-id="654bf-109">Retorna os valores de uma ou mais propriedades de um item do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="654bf-109">Returns the values of one or more properties on an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|<span data-ttu-id="654bf-110">Retorna uma ou mais propriedades do sistema.</span><span class="sxs-lookup"><span data-stu-id="654bf-110">Returns one or more system properties.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|<span data-ttu-id="654bf-111">Define uma ou mais propriedades de um item no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="654bf-111">Sets one or more properties of an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|<span data-ttu-id="654bf-112">Define uma ou mais propriedades do sistema.</span><span class="sxs-lookup"><span data-stu-id="654bf-112">Sets one or more system properties.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="654bf-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="654bf-113">In This Section</span></span>  
  
|<span data-ttu-id="654bf-114">Tópico</span><span class="sxs-lookup"><span data-stu-id="654bf-114">Topic</span></span>|<span data-ttu-id="654bf-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="654bf-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="654bf-116">Propriedades do item do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="654bf-116">Report Server Item Properties</span></span>](reporting-services-properties-report-server-item-properties.md)|<span data-ttu-id="654bf-117">Descreve as propriedades específicas do item no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="654bf-117">Describes the item-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="654bf-118">Propriedades do sistema do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="654bf-118">Report Server System Properties</span></span>](reporting-services-properties-report-server-system-properties.md)|<span data-ttu-id="654bf-119">Descreve as propriedades específicas do sistema no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="654bf-119">Describes the system-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="654bf-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="654bf-120">See Also</span></span>  
 <span data-ttu-id="654bf-121">[Criando aplicativos usando o serviço Web e o .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="654bf-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="654bf-122">[Serviço Web Servidor de Relatórios](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="654bf-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="654bf-123">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="654bf-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
