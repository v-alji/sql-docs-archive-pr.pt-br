---
title: Microsoft SQL Server Reporting Services serviço compartilhado do SharePoint está instalado lado a lado (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6ae1017e-129b-4702-9ea7-00ac9b024062
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b8a26fedd892dfb26dea4616efd46d3b3748b508
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576121"
---
# <a name="microsoft-sql-server-reporting-services-sharepoint-shared-service-is-installed-side-by-side-upgrade-advisor"></a><span data-ttu-id="1ae45-102">O serviço compartilhado do SharePoint do Microsoft SQL Server Reporting Services está instalado lado a lado (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="1ae45-102">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side (Upgrade Advisor)</span></span>
  <span data-ttu-id="1ae45-103">O supervisor de atualização detectou que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] o serviço compartilhado do SharePoint está instalado lado a lado com uma versão anterior do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ae45-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="1ae45-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1ae45-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="1ae45-105">Componente</span><span class="sxs-lookup"><span data-stu-id="1ae45-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="1ae45-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="1ae45-106">Description</span></span>  
 <span data-ttu-id="1ae45-107">O supervisor de atualização detectou [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que o serviço compartilhado do SharePoint está instalado lado a lado com uma versão anterior do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que não é baseada na arquitetura do serviço compartilhado do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1ae45-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is not based on the SharePoint shared service architecture.</span></span> <span data-ttu-id="1ae45-108">Como o computador tem as tecnologias mais antigas e mais recentes do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint instaladas lado a lado, a atualização está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="1ae45-108">Because the computer has both older and newer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint related technologies installed side by side, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1ae45-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="1ae45-109">Corrective Action</span></span>  
 <span data-ttu-id="1ae45-110">Para continuar com a atualização, você deve desinstalar uma das instalações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] existentes.</span><span class="sxs-lookup"><span data-stu-id="1ae45-110">To continue with upgrade, you must uninstall one of the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installations.</span></span> <span data-ttu-id="1ae45-111">Depois de remover uma das instalações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], execute novamente o Supervisor de Atualização para confirmar se não há outros problemas de atualização.</span><span class="sxs-lookup"><span data-stu-id="1ae45-111">After removing one of the installations of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
  
