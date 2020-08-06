---
title: Navegação direta para o servidor de relatório (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3d2814a4-318a-45ed-b093-1e852fab561f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ab4d146bba4bd87de56b30ad100b57f79eb68de3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583353"
---
# <a name="direct-browsing-to-report-server-upgrade-advisor"></a><span data-ttu-id="bc128-102">Navegação Direta para o Servidor de Relatórios (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="bc128-102">Direct Browsing to Report Server (Upgrade Advisor)</span></span>
  <span data-ttu-id="bc128-103">O supervisor de atualização detectou que a instalação atual do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] está navegando diretamente para o diretório virtual do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="bc128-103">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory.</span></span>  
  
||  
|-|  
|<span data-ttu-id="bc128-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bc128-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="bc128-105">Componente</span><span class="sxs-lookup"><span data-stu-id="bc128-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="bc128-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc128-106">Description</span></span>  
 <span data-ttu-id="bc128-107">O supervisor de atualização detectou que a instalação atual do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] está navegando diretamente para o diretório virtual do servidor de relatório, por exemplo, **http:// \<server name> /ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="bc128-107">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory, for example **http://\<server name>/ReportServer**.</span></span> <span data-ttu-id="bc128-108">Isto não tem suporte nas versões atuais do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc128-108">This is not supported in current versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc128-109">Essa regra é um aviso e a atualização não é bloqueada.</span><span class="sxs-lookup"><span data-stu-id="bc128-109">This rule is a warning and upgrade is not blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="bc128-110">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="bc128-110">Corrective Action</span></span>  
 <span data-ttu-id="bc128-111">Navegue usando a interface do usuário do SharePoint para bibliotecas de documentos ou use **http:// \<server name> /sharepoint site>/_vti_bin/ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="bc128-111">Browse using the SharePoint user interface for document libraries or use **http://\<server name>/sharepoint site>/_vti_bin/reportserver**.</span></span>  
  
  
