---
title: Atualização de dados PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: ac8358a3-ee71-44c7-8ee6-ac7afe3ebaa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f7d5ed5c2f8882cbc0c47a1c711748d26e0193c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574333"
---
# <a name="powerpivot-data-refresh"></a><span data-ttu-id="d5822-102">Atualização de dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d5822-102">PowerPivot Data Refresh</span></span>
  <span data-ttu-id="d5822-103">Depois de criar uma pasta de trabalho que contém dados PowerPivot, você pode atualizar os dados periodicamente executando novamente uma consulta ou um comando para obter informações atualizadas das origens usadas inicialmente para criar a pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5822-103">After you create a workbook that contains PowerPivot data, you might want to periodically refresh the data by rerunning a query or command to get updated information from the sources you used originally to create the workbook.</span></span> <span data-ttu-id="d5822-104">Esse processo é denominado `data refresh`, e você pode atualizar dados sob demanda no [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] ou como uma operação agendada executada como um processo do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] em um servidor de aplicativo em um farm do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5822-104">This process is called `data refresh`, and you can refresh data on demand in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], or as a scheduled operation that runs as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process on an application server in a SharePoint farm.</span></span> <span data-ttu-id="d5822-105">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="d5822-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="d5822-106">Atualização de dados PowerPivot com SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="d5822-106">PowerPivot Data Refresh with SharePoint 2010</span></span>](../powerpivot-data-refresh-with-sharepoint-2010.md)  
  
-   [<span data-ttu-id="d5822-107">Configurar a conta de atualização de dados autônoma do PowerPivot &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="d5822-107">Configure the PowerPivot Unattended Data Refresh Account &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-unattended-data-refresh-account-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="d5822-108">Configurar credenciais armazenadas para a atualização de dados do PowerPivot &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="d5822-108">Configure Stored Credentials for PowerPivot Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="d5822-109">Agendar uma atualização de dados &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="d5822-109">Schedule a Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../schedule-a-data-refresh-powerpivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="d5822-110">Exibir o histórico de atualização de dados &#40;PowerPivot para SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="d5822-110">View Data Refresh History &#40;PowerPivot for SharePoint&#41;</span></span>](view-data-refresh-history-power-pivot-for-sharepoint.md)  
  
> [!NOTE]
>  <span data-ttu-id="d5822-111">O [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] e os Serviços do Excel do SharePoint Server 2013 usam uma arquitetura diferente para a atualização de dados dos modelos de dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d5822-111">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and SharePoint Server 2013 Excel Services use a different architecture for data refresh of PowerPivot data models.</span></span> <span data-ttu-id="d5822-112">A arquitetura com suporte do SharePoint 2013 utiliza os Serviços do Excel como componente primário para carregar modelos de dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d5822-112">The SharePoint 2013 supported architecture utilizes Excel Services as the primary component to load PowerPivot data models.</span></span> <span data-ttu-id="d5822-113">A arquitetura de atualização de dados anterior utilizada baseava-se em um servidor que executava o Serviço do Sistema PowerPivot e o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no modo do SharePoint para carregar modelos de dados.</span><span class="sxs-lookup"><span data-stu-id="d5822-113">The previous data refresh architecture used relied on a server running PowerPivot System Service and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in SharePoint mode to load data models.</span></span> <span data-ttu-id="d5822-114">Para saber mais, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5822-114">For more information, see the following:</span></span>  
> 
>  -   [<span data-ttu-id="d5822-115">Atualização de dados PowerPivot com SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="d5822-115">PowerPivot Data Refresh with SharePoint 2013</span></span>](power-pivot-data-refresh-with-sharepoint-2013.md)  
> -   [<span data-ttu-id="d5822-116">Atualizar pastas de trabalho e atualização de dados agendada &#40;SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="d5822-116">Upgrade Workbooks and Scheduled Data Refresh &#40;SharePoint 2013&#41;</span></span>](../instances/install-windows/upgrade-workbooks-and-scheduled-data-refresh-sharepoint-2013.md)  
  
  