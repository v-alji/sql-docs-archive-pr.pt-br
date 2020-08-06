---
title: Instalação do PowerPivot para SharePoint 2010 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 8d47dde7-c941-4280-a934-e2fe3f9a938f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ba04dfdc69b1c510a800c062586e45f8873c8e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581662"
---
# <a name="powerpivot-for-sharepoint-2010-installation"></a><span data-ttu-id="c10cd-102">Instalação do PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="c10cd-102">PowerPivot for SharePoint 2010 Installation</span></span>
  <span data-ttu-id="c10cd-103">O [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] é uma coleção de componentes de servidor que fornece processamento de consultas e controle de gerenciamento em pastas de trabalho [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] que você publica no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c10cd-103">[!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] is a collection of server components that provide query processing and management control over [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks that you publish to SharePoint.</span></span> <span data-ttu-id="c10cd-104">Os serviços incluem o mecanismo Analysis Services e o Serviço de Sistema [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c10cd-104">Services include the Analysis Services engine and [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c10cd-105">Para obter informações sobre o [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] e a instalação com o SharePoint Server 2013, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c10cd-105">For information regarding [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] and installation with SharePoint Server 2013, see the following:</span></span>  
>   
>  -   <span data-ttu-id="c10cd-106">A seção "SQL Server 2012 SP1" da [visão geral da instalação de serviços do SQL Server](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span><span class="sxs-lookup"><span data-stu-id="c10cd-106">The "SQL Server 2012 SP1" section of [Overview of SQL Server Servicing Installation](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span></span>  
  
 <span data-ttu-id="c10cd-107">O Analysis Services oferece processamento do lado de servidor para pastas de trabalho do Excel que contêm dados do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c10cd-107">Analysis Services provides server-side processing for Excel workbooks that contain [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data.</span></span> <span data-ttu-id="c10cd-108">O Serviço do Sistema do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] trabalha com o Analysis Services, adicionando integração do SharePoint, balanceamento de carga e gerenciamento de conexão.</span><span class="sxs-lookup"><span data-stu-id="c10cd-108">[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service works alongside Analysis Services, adding SharePoint integration, load balancing and connection management.</span></span> [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]<span data-ttu-id="c10cd-109">estende os serviços do Excel emparelhando seu recurso de processamento de dados em grande escala com os serviços de processamento de dados que o Excel fornece.</span><span class="sxs-lookup"><span data-stu-id="c10cd-109">extends Excel Services by pairing its large scale data processing capability with the data rendering services that Excel provides.</span></span>  
  
 <span data-ttu-id="c10cd-110">Para instalar o [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], use a mídia de instalação do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c10cd-110">To install [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], use the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]installation media.</span></span>  
  
 <span data-ttu-id="c10cd-111">Para obter instruções sobre cenários de implantação avançada, consulte [lista de verificação de implantação: Reporting Services, Power View e PowerPivot para SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) e lista de verificação de [implantação: expansão adicionando servidores PowerPivot a um farm do SharePoint 2010](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span><span class="sxs-lookup"><span data-stu-id="c10cd-111">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Scale-out by adding PowerPivot Servers to a SharePoint 2010 farm](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c10cd-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c10cd-112">In This Section</span></span>  
 [<span data-ttu-id="c10cd-113">Instalar o PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="c10cd-113">Install PowerPivot for SharePoint 2010</span></span>](../../../2014/sql-server/install/install-powerpivot-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="c10cd-114">Instalar o Provedor Analysis Services OLE DB nos servidores do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c10cd-114">Install the Analysis Services OLE DB Provider on SharePoint Servers</span></span>](../../../2014/sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md)  
  
 [<span data-ttu-id="c10cd-115">Instalar o ADOMD.NET em servidores Web front-end executando a Administração Central</span><span class="sxs-lookup"><span data-stu-id="c10cd-115">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>](../../../2014/sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md)  
  
 [<span data-ttu-id="c10cd-116">Instalar o ADO.NET Data Services para dar suporte a exportações do feed de dados das listas do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c10cd-116">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>](../../../2014/sql-server/install/install-ado-net-data-services-to-support-data-feed-exports-of-sharepoint-lists.md)  
  
 [<span data-ttu-id="c10cd-117">Instalar o PowerPivot pelo prompt de comando</span><span class="sxs-lookup"><span data-stu-id="c10cd-117">Install PowerPivot from the Command Prompt</span></span>](../../../2014/sql-server/install/install-powerpivot-from-the-command-prompt.md)  
  
 [<span data-ttu-id="c10cd-118">Desinstalar o PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="c10cd-118">Uninstall PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/uninstall-power-pivot-for-sharepoint.md)  
  
 [<span data-ttu-id="c10cd-119">Reparar o PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="c10cd-119">Repair PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/repair-powerpivot-for-sharepoint.md)  
  
 [<span data-ttu-id="c10cd-120">PowerPivot para SharePoint de configuração inicial &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="c10cd-120">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../../2014/sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
## <a name="see-also"></a><span data-ttu-id="c10cd-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c10cd-121">See Also</span></span>  
 [<span data-ttu-id="c10cd-122">Administração e configuração de servidor do PowerPivot na Administração Central</span><span class="sxs-lookup"><span data-stu-id="c10cd-122">PowerPivot Server Administration and Configuration in Central Administration</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration)  
  
  
